# Mathematical Modeling Practice DPF

> Selected methods for physical balance models, bounded observation association and shared-state interaction.

- **Author:** Anatoly Levenchuk, with AI-assisted development and review
- **Version:** September 2026
- **Status:** Eternal alpha: five published techniques; the broader modeling repertoire is under development.
- **License:** © 2026 Anatoly Levenchuk. Original framework text: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). Cited sources retain their own terms.
- **Publication:** [FPF ecosystem repository](https://github.com/ailev/FPF)

Begin with the question your model must answer. Use the Table of Contents to find a relevant pattern, then open its Problem frame, Solution, worked cases and checklist. Readme gives selected entries; Preface explains the connected methods and their limits.

The code **MMP** names this DPF. Its numbers are stable pattern addresses; § shows position in this edition. References beginning MATH name patterns in [Mathematical Practice](https://github.com/ailev/FPF/blob/main/MATHEMATICAL-PRACTICE-DPF.md) (September 2026). References such as C.29 name patterns in [FPF](https://github.com/ailev/FPF/blob/main/FPF-Spec.md) (September 2026). ME references name patterns in [Method Engineering](https://github.com/ailev/FPF/blob/main/Engineering%20DPF%20Suite/METHOD-ENGINEERING-PRINCIPLES-FRAMEWORK.md) (11 September 2026). Open the cited publication when that contribution is needed. When using another version, revisit a conclusion if its cited operation or condition has changed.

To cite this edition: Anatoly Levenchuk, *Mathematical Modeling Practice DPF*, September 2026, [FPF ecosystem repository](https://github.com/ailev/FPF).

# Table of Contents

## Public units

| Unit | Title | Use |
| --- | --- | --- |
| Readme | [Mathematical Modeling Practice - Readme](#mathematical-modeling-practice---readme) | Find a first pattern for your question. |
| Preface | [Mathematical Modeling Practice - Preface](#mathematical-modeling-practice---preface) | Understand the connected methods, their rationale, sources and limits. |

## Part A - Formulate and simplify physical models

| § | ID & Title | Status | Keywords & Search Queries | Dependencies |
| :--- | :--- | :--- | :--- | :--- |
| 1 | [MMP.1 - Complete a Balance Model with Constitutive Relations](#mmp1---complete-a-balance-model-with-constitutive-relations) |  | balance; constitutive relation; storage; exchange; state; history. Which physical relation is missing before the model can return a temperature, voltage or rate? | C.29.BB for boundary balances; MMP.2 when choosing a simplification; MATH.14 for linear solution. |
| 2 | [MMP.2 - Choose Scales and Retained Terms for the Requested Answer](#mmp2---choose-scales-and-retained-terms-for-the-requested-answer) |  | scales; dimensionless ratio; regime; initial transient; boundary layer; approximation. Which omitted term can change the requested value, maximum, average or decision? | MMP.1 for the physical formulation; MMP.3 for a steady network and its spatial output. |
| 3 | [MMP.3 - Construct a Steady Conductance Network](#mmp3---construct-a-steady-conductance-network) |  | thermal network; resistor network; acausal equations; boundary; reduction; recovery; hot spot. How can component relations yield a steady value or bound at the point that matters? | MMP.1 for component response; MMP.2 for time and spatial scope; MATH.14 for elimination and recovery. |

## Part B - Model observations and interacting work

| § | ID & Title | Status | Keywords & Search Queries | Dependencies |
| :--- | :--- | :--- | :--- | :--- |
| 1 | [MMP.4 - Associate Observations under Motion Bounds](#mmp4---associate-observations-under-motion-bounds) |  | identity; reachable interval; data association; motion bound; shared offset; feasible path. Which complete pairing can satisfy the observations together, and does unresolved identity affect the answer? | MATH.15 for matching and uniqueness; C.16.IR for observation interpretation; C.11.DUA when further inquiry needs comparison. |
| 2 | [MMP.5 - Model Overlapping Work with Shared State](#mmp5---model-overlapping-work-with-shared-state) |  | shared state; saved observation; interleaving; atomic step; lost update; reservation; reduction. What can intervening work change, and which operating condition preserves the required result? | MATH.1/.2 for path composition and identification; C.29 for subject correspondence; ME.7/.12 for method design and coherence. |

# Mathematical Modeling Practice - Readme

## Practical entries

This edition provides five selected modeling techniques: closing a physical balance with response laws, scaling a differential model, constructing a steady conductance network, associating observations under motion bounds, and examining overlapping work through shared state. Start here when one of these difficulties fits your question; each pattern states the conditions under which its method applies.

The broader Mathematical Modeling Practice repertoire is still being developed. General model-family selection, statistical model construction and general numerical modeling are not yet taught in this edition. For the common work of constructing a first account, consult B.5.FM in [FPF](https://github.com/ailev/FPF/blob/main/FPF-Spec.md); C.29 helps connect mathematical work to the subject question. The entries below lead to the five available techniques.

Open the cited pattern for its instructions, conditions and worked cases. The [Preface](#mathematical-modeling-practice---preface) explains how the contributions connect and what this repertoire currently supplies.

When working with an assisting agent, you can ask: “Explain the result and give feedback in the language of our work, without framework jargon. Preserve the meaning of the sources.” Ask it to show the calculation or the modeling assumption when that is what you need to understand or change.

### MM-CLOSE - Turn a balance into a calculable response

- **Situation:** An energy or charge balance is available, but it does not yet determine the temperature, voltage or response you need.
- **Question:** Which relation supplies the unresolved term, and under what conditions does it apply?
- **First useful result or blocker:** A formulation that determines the requested rate or steady value, or a missing response relation that prevents that calculation. With heat capacity 20 J/K, conductance 2 W/K, surroundings at 20 degrees Celsius and heating of 12 W, a body at 30 degrees Celsius cools at 0.4 K/s.
- **Start with:** [MMP.1 - Complete a Balance Model with Constitutive Relations](#mmp1---complete-a-balance-model-with-constitutive-relations), :4.1-:4.5. Identify storage and exchange, supply their relations, and substitute them into the balance with the conditions needed for the question.
- **Stop or return:** Use the rate or value if it answers the question. A different material, preparation or consequential state can require a different relation. A question about when a steady answer is adequate continues through MMP.2.

### MM-SCALE - Decide which terms the answer needs

- **Situation:** A proposed simplification works in one place or time interval but may fail in another.
- **Question:** Does the omitted contribution change the requested value, range or decision?
- **First useful result or blocker:** An approximation with its usable time or spatial range, or a term that must be retained. For the cooling model in MMP.2, a steady temperature of 20 degrees Celsius is within 1 K of the changing temperature after about 23.026 seconds, but not throughout the interval starting at time zero.
- **Start with:** [MMP.2 - Choose Scales and Retained Terms for the Requested Answer](#mmp2---choose-scales-and-retained-terms-for-the-requested-answer), :4.1-:4.5. Rescale the equation and its conditions together, then compare the effect of an omission on the output.
- **Stop or return:** Stop when the available comparison settles the use. A changed output, forcing time, boundary or observation location can require restoring a term. A new response law returns to MMP.1.

### MM-NETWORK - Calculate a value in a connected arrangement

- **Situation:** Components exchange heat or electrical current, and you need a steady value at a specified place.
- **Question:** Which balances and component relations determine that value, including any internal value removed during calculation?
- **First useful result or blocker:** Coupled equations and a recovered value or bound, or a boundary condition that prevents the requested answer. In MMP.3's two-heater case, the junction temperatures are 60 and 40 degrees Celsius. To obtain the hot-face temperature, add the rise across its slab.
- **Start with:** [MMP.3 - Construct a Steady Conductance Network](#mmp3---construct-a-steady-conductance-network), :4.1-:4.6. Choose junctions and paths, join their balances, check the steady formulation, then solve and recover the requested output.
- **Stop or return:** Use a bound that already settles the limit. If the required maximum occurs inside a reduced component, recover its temperature or supply a spatial model or bound. An isolated component with net heating requires revisiting the outlets or steady assumption.

### MM-ASSOCIATE - Determine which observation belongs to which object

- **Situation:** Position observations arrive without persistent labels, and proximity alone leaves identity uncertain.
- **Question:** Which pairings satisfy both the motion bounds and the shared measurement conditions?
- **First useful result or blocker:** A unique feasible correspondence, two feasible alternatives, a conflict, or a partial search result. Markers at -3 and +3 metres, moving at most 1 metre in one second, can be uniquely paired with later positions -2.2 and +2.4 metres.
- **Start with:** [MMP.4 - Associate Observations under Motion Bounds](#mmp4---associate-observations-under-motion-bounds), :4.1-:4.5. Construct reachable positions, find complete pairings and test any common offset or other shared condition. MATH.15 supplies the pairing construction.
- **Stop or return:** If all feasible pairings give the answer needed by the work, use that answer. If identity changes the action, seek a worthwhile distinction. A changed population or motion rule requires changing the formulation before reusing the pairing test.

### MM-OVERLAP - Find an outcome hidden by the usual order of work

- **Situation:** Two activities use something in common, and each participant may act on a value observed before the other changed it.
- **Question:** Which outcomes do the permitted interventions allow, and what operating change would preserve the required result?
- **First useful result or blocker:** A calculated counterexample, a property established for the stated model, or an unresolved part of the exploration. Two read-then-write increases can finish with only one increase; protecting the arithmetic alone can still leave a booking decision stale.
- **Start with:** [MMP.5 - Model Overlapping Work with Shared State](#mmp5---model-overlapping-work-with-shared-state), :4.1-:4.6. Keep saved observations, shared values and participant positions, construct permitted steps, then compare the original and changed arrangements.
- **Stop or return:** Return the result with the operating conditions that make the modeled steps applicable. Include waiting, failure or retry when those change the decision. ME.7 and ME.12 use the result to revise or check the working method.

### MM-THERMAL - Turn a cooling arrangement into a usable temperature limit

- **Situation:** A connected thermal arrangement must stay below a temperature limit, and a convenient average or junction temperature may conceal the point that matters.
- **Question:** Which formulation and calculation can answer the temperature question over the stated operating conditions?
- **First useful result or blocker:** A temperature bound for the requested point, or the missing physical relation, time condition or calculation that prevents that use.
- **Start with:** MMP.1 for storage and exchange relations; MMP.2 for the needed time and spatial detail; MMP.3 for a steady conductance network and output recovery. Use the required MATH constructions inside that calculation.
- **Stop or return:** Stop when the result settles the limit. Return to the contribution that changed: a heat path, retained state, operating interval, spatial output or calculation. A bound that leaves temperatures on both sides of the limit gives an unresolved answer.

The two-heater example in MMP.3 joins balance and exchange relations, solves for a mean and a contrast, and recovers the hotter junction. A slab relation then bounds the hottest point in either slab. Under the stated input ranges, separate upper bounds put that point below 65.183 degrees Celsius, enough for a 66-degree criterion. Retaining dependence on the shared powers tightens the bound below 64.592 degrees, settling a 65-degree criterion without new measurements.

That calculation presupposes steady operation. A startup-temperature question needs accumulation and initial states before a time-dependent calculation can answer it. MMP.1 supplies that formulation move; MMP.2 shows how the requested time interval can determine whether the steady approximation suffices. Its single-body settling time applies to that single-body model. The connected network needs the corresponding transient solution or bound.

The same distinction matters after network reduction: an eliminated internal junction may contain the hottest point. MATH.14 and MMP.3 retain its recovery expression. Read [the Preface's worked use](#mmppreface4---worked-use---carry-a-temperature-question-through-the-model) for the connected calculation and its returns.

# Mathematical Modeling Practice - Preface

## MMP.Preface:1 - Problem frame - Make a model answer a working question

You may have a conservation law, a solver, a set of measurements or a diagram of a working method and still lack the model needed for the next decision. The balance may omit a component's response. The calculation may return an average where the question concerns a maximum. Measurements that look individually plausible may conflict when they must share one calibration. A diagram may conceal what another participant can change between two actions.

The aim of Mathematical Modeling Practice is to help construct a mathematical account, obtain a result and return it to the subject of the question. This edition supplies five selected techniques: physical balance closure, scale-dependent simplification of differential models, steady conductance-network construction, bounded-motion observation association and overlapping work represented by shared state. The patterns can be used separately and in combinations within their stated conditions.

The general repertoire is incomplete. In particular, this edition does not yet teach general model-family selection, statistical model construction or general numerical modeling. FPF's B.5.FM supplies the common first-model construction, and C.29 connects mathematical work to a subject question. Use those entries for the shared reasoning while obtaining any further mathematical modeling technique from an appropriate source.

Begin with the unresolved question. The Readme helps select a first pattern; the Table of Contents also supports questions outside its examples. This Preface explains the shared approach and its branches. The bodies supply the constructions and their conditions.

The reader needs enough knowledge of the subject to interpret its quantities and proposed behavior. The physical examples use units, balances and elementary equations; the scale examples additionally use derivatives and supplied exponential solutions. The observation examples need interval arithmetic. The shared-state examples need arithmetic and finite sequences. A participant can obtain a mathematical or physical contribution from a collaborator or tool while retaining the inputs, assumptions and result needed to use it.

## MMP.Preface:2 - Problem and forces - Preserve the question through the formulation

A mathematical formulation selects objects and relations through which the subject can be investigated. In a thermal model, T is a variable; its intended interpretation may be the uniform temperature of a body, the value at one face or a spatial average. Those choices can give different answers about the same device.

The modeling problem is to preserve the requested distinction through that selection and the ensuing calculation. This includes deciding which physical response, observation relation or operating intervention belongs in the formulation. Once the equations or transition rules are supplied, mathematical work determines their consequences. Returning those consequences to a device or activity uses the interpretation and conditions with which the model was constructed.

| Tension | Choice that changes the work |
| --- | --- |
| A general balance and a specific response | Which storage or exchange relation determines the requested quantity? |
| Manageable calculation and consequential detail | Which state, location, time interval or intervention can change the answer? |
| Separately plausible contributions and a usable whole | Can the conditions of all components, observations or activities hold together? |
| A point estimate and a decision under variation | Does the work need one value, a bound, several alternatives or a probability-based answer? |
| Available information and further effort | Can the existing relations or ranges settle the question before another measurement or larger calculation? |
| Reuse and changed conditions | Which contribution must be revisited when the question or arrangement changes? |

Choose the formulation and effort from the needed result. A range can support a decision. A small counterexample can show which condition needs repair. A supplied approximation can be sufficient for a late-time value even when an early transient remains unresolved.

## MMP.Preface:3 - Solution - Connect the subject, construction, calculation and use

### MMP.Preface:3.1 - Formulate a physical response

[MMP.1](#mmp1---complete-a-balance-model-with-constitutive-relations) begins where a balance leaves a response unspecified. It connects stored energy with temperature, or charge with voltage, and supplies exchange relations for the selected paths. The result is an equation whose terms have physical interpretations, together with initial or boundary conditions when the question requires them.

[MMP.3](#mmp3---construct-a-steady-conductance-network) joins such contributions into a steady linear network. Each internal transfer enters its two junction balances with opposite signs. Boundary conditions determine whether an absolute value is available, while elimination can reduce the calculation and retain a way to recover an internal output.

These equations express component relations before a solver chooses a calculation order. A change in that order can reuse the same physical account. A change in a contact, material response or heat outlet can require changing the account itself.

### MMP.Preface:3.2 - Choose what may be omitted

[MMP.2](#mmp2---choose-scales-and-retained-terms-for-the-requested-answer) compares the terms of a supplied formulation at the scales relevant to the output. It carries initial and boundary conditions through the rescaling, then asks what a proposed omission changes in the requested value or decision.

That result returns to formulation. An omitted thermal store can affect the initial cooling rate, so MMP.1 restores its state and evolution. A slab's hot-face temperature can exceed its junction temperature, so MMP.3 supplies the spatial rise or retains a spatial model. An adequate bound can make that additional formulation unnecessary for the present decision.

There are two different reductions here. Mathematical elimination preserves the selected solution information through a recovery expression. A physical approximation neglects a contribution under stated conditions and needs an estimate or other comparison reaching the requested output. The example in section 4 uses both.

### MMP.Preface:3.3 - Connect observations through what can coexist

[MMP.4](#mmp4---associate-observations-under-motion-bounds) constructs feasible pairings between two sets of positions. A motion bound supplies reachable intervals and a path witnessing an allowed pair. Mathematical Practice MATH.15 supplies complete matching and the test for alternative pairings.

The measurement account can impose a condition on the whole pairing. If all readings share one offset, the selected pairs must admit the same offset. The graph calculation supplies candidate associations; the joint condition decides which can coexist. The resulting alternatives can then be queried for the quantity needed by the work.

The same separation supports economical inquiry: uncertainty about identity need not prevent answering a distance question. Preserve the alternatives when they matter, and seek another distinction only when its possible answer can change the action.

### MMP.Preface:3.4 - Model interaction and return to a changed working method

[MMP.5](#mmp5---model-overlapping-work-with-shared-state) constructs a state containing shared values, participants' saved observations and their positions in the work. Permitted steps specify who can observe or change which value and when. Inspecting permitted sequences can reveal a counterexample. A complete exploration or general argument can establish the required property for the stated model.

This branch uses mathematical path composition and justified reduction. It also needs a subject interpretation: an indivisible reservation in the model requires an operating arrangement that supplies it. A model of two people making promises can use the same mathematics as a concurrent program, while the means of enforcing the modeled conditions differ.

Method Engineering ME.7 receives a changed ordering, overlap or resource condition when a proposed method is redesigned. ME.12 helps locate disagreement between a method description and what its arrangement supports. The counter and reservation constructions in MMP.5 show how mathematical analysis changes the proposed way of working.

### MMP.Preface:3.5 - Reuse the common reasoning contributions

FPF C.29 connects the selected mathematical objects and relations with the subject. C.29.1 governs transfer between mathematical accounts. C.29.2 and C.29.3 address a calculable construction and its execution when those steps need further work. MMP supplies particular formulation and modeling methods at the points where these general instructions require subject-specific operations.

Mathematical Practice supplies reusable constructions such as elimination, matching, path composition and operation-preserving identification. A solved mathematical system may still need the output expression that turns its variables into the requested value. Keep that return available when a collaborator or solver performs the calculation.

Use existing characterization, portfolio and improvement methods when comparing several models: define the relevant error, cost and other properties, compare the models through FPF A.19.CPM and retain useful alternatives through C.18 or G.5 where needed. E.22 and E.23 support improvement. Further inquiry follows C.11.DUA when its possible contribution and burden need comparison. MMP's particular error and feasibility calculations supply inputs to those methods.

## MMP.Preface:4 - Worked use - Carry a temperature question through the model

A design question asks whether the hottest point in either slab of a two-heater arrangement stays below a stated limit during steady operation.

**Supply the paths and response.** Each heater sends all its power through a uniform slab with insulated sides into an isothermal junction. Each junction exchanges heat with common surroundings through conductance G>0; a path of conductance K>=0 joins the junctions. These are the modeled outlets. MMP.1 supplies the distinction between balance and path response; MMP.3 joins them into

`P1 = G*(T1-T_a) + K*(T1-T2)`,

`P2 = G*(T2-T_a) + K*(T2-T1)`.

**Calculate and recover the junctions.** Let m=(T1+T2)/2 be the mean and d=(T1-T2)/2 the half-difference. Adding and subtracting the equations gives

`m = T_a + (P1+P2)/(2*G)` and `d = (P1-P2)/(2*(G+2*K))`.

Return through `T1=m+d` and `T2=m-d`. For T_a=20 degrees Celsius, P1=10 W, P2=2 W, G=0.2 W/K and K=0.1 W/K, the junctions are 60 and 40 degrees Celsius. Their mean of 50 degrees would miss the hotter junction.

**Reach the physical point named in the question.** Under steady one-dimensional conduction with constant conductivity and no internal generation, the hot-face rise across a slab is `P*L/(k*A)`. For P<=10.2 W, L<=0.007 m, k>=100 W/(m*K) and A>=0.0011 square metres, the rise is below 0.65 K. This step carries the answer from a network junction to the slab's hot face.

**Compare the limit using the input ranges.** MMP.3:5.1 uses hard ranges for ambient temperature, powers and conductances. Separate upper bounds give a hottest-point bound below 65.183 degrees Celsius. That settles a 66-degree criterion. For a 65-degree criterion, retaining the shared powers in the joint calculation tightens the bound below 64.592 degrees, which settles that criterion without a new measurement. The bound alone leaves a 64-degree criterion unresolved.

**Return when the use changes.** A startup question needs changing-state equations and initial conditions. MMP.1 supplies that formulation, and MMP.2 compares a steady approximation with the transient needed for the requested time interval. The settling time of a single body cannot be assigned to this network without a corresponding network calculation. If the change instead removes a thermal contact, revisit the paths. If it asks for a value at an eliminated internal junction, use the retained recovery expression.

The connected use is: interpret the quantity, supply the physical relations, choose an adequate formulation, calculate, recover the requested output and revise the contribution that changes the answer. Each step can be assigned to a different participant while keeping these dependencies explicit.

## MMP.Preface:5 - Worked use - Test an association as a whole

Two point objects A and B have earlier positions 0 and 2 metres. After one second, an instrument returns readings 2 and 0 metres in that order. Each object's speed is at most 1 m/s. The readings share an offset b in [-2,2] metres, with no other observation error in this account. Both objects are observed once at each time, and crossings are allowed.

MMP.4 first derives reachable intervals [-1,1] for A and [1,3] for B. Converting each reading separately to its possible position gives [0,4] and [-2,2]. Every earlier object can therefore be paired with either reading at this preliminary stage. MATH.15 finds two complete graph pairings.

For A paired with the reading of 2 metres and B with the reading of 0 metres, the first motion condition requires b in [1,3] and the second requires b in [-3,-1]. No common b exists. This pairing fails.

The other pairing associates A with the reading of 0 metres and B with the reading of 2 metres. Both admit b in [-1,1]. Choosing b=0 gives stationary paths and realizes both observations. Excluding the first pairing and witnessing the second establishes a unique association under the stated account.

The offset remains unresolved within [-1,1]. Nevertheless, the distance between the objects at the later time is always 2 metres, because their positions are -b and 2-b. A distance question can stop there. A question about A's absolute position may require retaining that interval or finding a worthwhile additional observation.

This example connects physical possibilities, a combinatorial construction and a condition on the complete measurement account. A faster matching algorithm cannot supply the shared-offset test that was omitted from a formulation.

## MMP.Preface:6 - Checks and common failures - Keep the needed result available

For the combination being used, ask:

- Which quantity or property must the work obtain, at what place and time?
- What physical or operating relations give the mathematical variables their intended use?
- Which initial, boundary, observation or shared conditions constrain the calculation?
- Does a simplification retain the requested output, or provide an adequate comparison for what it omits?
- Does the reported result cover one case, a bounded family, every admitted case or a statistical statement?
- Which changed condition would require another formulation rather than another calculation?

Reuse the applicable component results. A new input value within the same relation can need only recalculation. A changed relation or requested output reopens the contributions it affects.

The worked uses locate recurring failures. Reporting the mean in section 4 loses the requested maximum; recover the contrast and the spatial contribution. Accepting each pair separately in section 5 loses the common offset; solve the joint condition. In MMP.5, one atomic box can hide a permitted intervention; retain the steps the operating arrangement actually allows.

## MMP.Preface:7 - Consequences, perspectives and limits

The gain is a calculable account whose assumptions, result and useful revisions remain understandable. The same formulation can support another solver or a changed numerical input. Its limits also become actionable: a missing response law, incompatible boundary, consequential transient or unresolved observation can direct the next contribution.

The initial repertoire favors small constructions that can be worked by hand and inspected before automation. It serves readers with enough subject knowledge to propose and interpret the modeled relations.

The current physical-modeling branch develops linear storage and exchange examples, scale comparisons and steady networks. The observation branch covers independent point motion on a line and its stated measurement models. The shared-state branch develops finitely branching work under a step bound, with separate arguments where a parameterized family is covered.

Other questions need further techniques. Learning a constitutive law, fitting a surrogate, resolving a new differential problem, estimating a stochastic model, modeling collisions or proving unbounded progress each requires its corresponding construction. The supplied techniques remain useful within their conditions while those larger repertoires develop.

A model may also leave several answers or useful descriptions. Apply the common comparison and improvement methods to the receiving decision. Improving pointwise accuracy can require more computation or make a model harder to explain. Complementary models can serve different operations.

## MMP.Preface:8 - Architectural Rationale - Organize around formulation decisions

The language is organized by reusable modeling difficulties rather than by a list of equation types or application industries. A balance needing a response relation occurs in thermal and electrical work. A lost shared condition occurs in observation association. Hidden intervention points occur in software, human work and mixed arrangements. Each pattern gives the construction that changes the answer in its declared situations.

Mathematical Practice is a separate language because its constructions can be used within mathematics and across many subjects. MMP uses those constructions while adding the choice of physical or operating quantities, conditions and interpretation. FPF retains the common coordination of mathematical accounts, calculations and their use. This separation lets a better matching method or elimination technique become available to several modeling uses without restating it in each one.

Organizing only around physical balance models would make the observation and interaction methods harder to find. Each body provides its selected modeling construction and the calculations needed to understand the worked uses. It links to MATH for mathematical techniques that can also serve other subjects. This lets the reader obtain a needed mathematical contribution and reuse it with another modeling method.

The physical, observation and interacting-work branches share contributions and can overlap. MMP.2's output-based approximation question, for example, can recur in more than one physical model. Publication Parts group the text for reading; the actual dependencies are the supply and return relations described in section 3.

A direct calculation remains preferable when the complete applicable model is already available and the question is small. A domain simulator or a specialized modeling language becomes useful when its components and solution support save formulation effort. In either case, keep access to the component meaning and output recovery needed to interpret a result or change the model.

## MMP.Preface:9 - Source use and currentness

The sources contribute different parts of the modeling work. [Howison's Practical Applied Mathematics](https://people.maths.ox.ac.uk/fowler/courses/tech/sdh.pdf), in its 2004 author version, is a historical foundation for combining balances, constitutive relations and dimensionless comparisons. MMP.1 and MMP.2 develop those moves in small complete constructions.

[Sanderse and colleagues' 2024 closure-model review](https://arxiv.org/html/2403.02913v2) explains how unresolved states can leave a response dependent on history, changing the closure model needed. [Callaham and colleagues' 2021 work on dominant balances](https://www.nature.com/articles/s41467-021-21331-z) identifies local dominant balances from observed or simulated fields. For the worked small problems, direct rescaling and analytic comparisons suffice; those alternatives matter when the response or the active processes are not already supplied.

The [Dyad component tutorial](https://help.juliahub.com/dyad/stable/tutorials/creating-components.html) supports joining potential, flow, balance and component relations before selecting an analysis. [Dörfler and Bullo's Kron-reduction construction](https://motion.me.ucsb.edu/pdf/2011d-db.pdf) supplies elimination that carries both connections and internal inputs. MMP.3 adds recovery for the physical location the question names, using the [slab-conduction relation](https://openstax.org/books/university-physics-volume-2/pages/1-6-mechanisms-of-heat-transfer) under its geometric conditions.

[Rodin's Venus Homotopically](https://philsci-archive.pitt.edu/12116/1/vh.pdf) distinguishes identification supported by a connecting construction from a choice of names. MMP.4 develops feasible paths, alternative exclusion and shared observation conditions. Its source section compares richer interval-constraint and probabilistic-association methods and states when their different results are wanted.

[Lamport's PlusCal tutorial](https://lamport.azurewebsites.net/tla/tutorial/session7.html) connects the choice of indivisible steps with lost updates and justified reduction. MMP.5 uses that construction for interacting work and distinguishes model checking and proof from the operating conditions that make their results usable.

These contributions are combined according to the question each method answers. The pattern source sections retain the relevant alternatives and the conditions for replacing the small constructions. A newer solver can change the affordable calculation without changing the subject account; a new physical response, observation model or operating behavior can require changing that account.

## MMP.Preface:10 - Relations to further reasoning and work

The [FPF specification](https://github.com/ailev/FPF/blob/main/FPF-Spec.md) supplies the common reasoning patterns cited here. [Mathematical Practice](https://github.com/ailev/FPF/blob/main/MATHEMATICAL-PRACTICE-DPF.md) supplies the mathematical constructions. [Method Engineering](https://github.com/ailev/FPF/blob/main/Engineering%20DPF%20Suite/METHOD-ENGINEERING-PRINCIPLES-FRAMEWORK.md) uses modeling results in method design and coherence checks.

Broader physical inquiry also asks which principles, explanations or possible interventions deserve investigation. Algorithmic and notational work asks how a construction can be computed and expressed so that another participant can use or change it. These questions enter modeling when they supply a missing response law, computation or representation, or when a model's result exposes a new difficulty.

A contradiction, failed approximation or new usable construction can make a further question worthwhile. FPF B.5.QD develops that question; B.5.RA helps recover an unfamiliar argument and B.5.RR follows changes through reasoning. Return the new result to the activity that motivated it, or use it to construct another method of inquiry or action.

# Part A - Formulate and simplify physical models

## MMP.1 - Complete a Balance Model with Constitutive Relations

> **Type:** Method
> **Normativity:** Normative

### MMP.1:1 - Problem frame

Use this pattern when a physical balance contains a quantity whose value is still unspecified by the chosen state and inputs. An energy balance, for example, can determine stored energy while leaving the temperature unknown. You need the relation between energy and temperature, and often a relation for heat exchange, before the model can answer a temperature question.

This is a physical-modeling contribution within Mathematical Modeling Practice. Start with one unresolved term in the balance. Name the physical quantity it denotes and the state or input values from which it must be obtained. Supply an applicable relation for that term, or determine which answers remain possible while it is unknown.

A *constitutive relation* describes a material's or component's response under stated conditions. Heat capacity, a conductor's heat-flow relation and a capacitor's charge-voltage relation are examples. Such a relation complements the balance by specifying how its terms depend on the chosen variables.

The lumped examples below require algebra, physical units and the meaning of a rate of change. A spatially distributed formulation also requires the relevant calculus. If the complete formulation is already supplied and appropriate to the question, proceed to its mathematical solution. Developing a previously unavailable material law or fitting a learned relation requires the corresponding physical or statistical method.

### MMP.1:2 - Problem

A balance relates accumulation, transfer and production. It can leave several possible responses compatible with the same input. Choosing a convenient formula for an unresolved response changes what the model predicts.

The missing relation can be easy to overlook. A temperature equation may silently assume constant heat capacity. An exchange term may already contain a linear-response approximation. A steady calculation may have removed storage even though the question concerns the period immediately after an input changes.

The working result is a formulation that states the supplied response relations, conditions and requested output. It may determine that output, retain a family of possible outputs, or expose the particular relation needed to continue.

### MMP.1:3 - Forces

| Concern | Consequence for formulation |
| --- | --- |
| Conservation and response | A shared balance can describe components with different material responses. |
| State resolution and available relations | One temperature per body is simpler than a temperature field; the chosen exchange and storage laws must support that resolution. |
| Supplied knowledge and new investigation | An available applicable relation may suffice; a consequential unknown can justify a further measurement or a different model. |
| Instantaneous response and retained history | A response may depend on additional state or past inputs, which a static formula omits. |
| Full state and required answer | Some outputs can be obtained while other quantities remain unresolved. |
| Steady and changing conditions | Removing accumulation changes the question the equations can answer. |

### MMP.1:4 - Solution

**Recover the balance → expose its unresolved terms → supply response relations → add input and boundary conditions → derive the formulation → obtain the requested result under those conditions.**

#### MMP.1:4.1 - Recover the quantity being balanced

Use the balance for the selected body, component or region. FPF C.29.BB supplies the construction across a boundary, including accumulation and transfers. Keep its signs and units consistent.

For a body receiving power P and losing heat at rate q, write

`dU/dt = P - q`,

where U is stored energy. This equation alone specifies neither the temperature associated with U nor the exchange rate associated with a temperature difference.

Name the output and time or operating condition needed by the question. An initial heating rate, a steady temperature and a maximum temperature over an interval are different outputs of the formulation.

#### MMP.1:4.2 - State how the unresolved quantities depend on the chosen variables

For each unresolved balance term, seek a relation whose inputs and result are identified physical quantities.

If temperature T is the state, a relation U(T) supplies storage. For a body with constant heat capacity C over the temperature range in use,

`U(T) - U(T_ref) = C*(T-T_ref)`

implies `dU/dt = C*dT/dt`. The reference energy disappears from this derivative. If heat capacity depends on temperature, use the corresponding U(T) or its derivative instead of carrying a constant C beyond its range.

For an admitted linear heat-loss path to surroundings at temperature T_a, use

`q = G*(T-T_a)`,

with G measured in watts per kelvin. Identify the path represented by G and the conditions under which it is being treated as linear.

These are two supplied relations: one for storage and one for exchange. Changing either can change the answer while leaving energy conservation intact.

#### MMP.1:4.3 - Choose the relation with its conditions of use

Obtain a relation from the applicable theory, component description, characterization or model being compared. Retain the conditions that change its use: for instance, the temperature range, material phase, direction of exchange or the approximation of uniform temperature inside a body.

A stipulated relation can support a conditional comparison before its applicability to an actual component is settled. An already applicable component relation can support a calculation without new measurement. When choosing between relations affects the intended action, use the common comparison and inquiry methods to decide what further work is worth doing.

A reduced or learned response can also supply a term. Identify what it takes as input and what it returns. If two allowed preparations have the same retained state and inputs but different responses that matter to the answer, the relation needs another distinguishing variable or retained history. Supply the evolution law and initial value for an added state, or use a response law with the required history. In :5.4, the temperature of an intermediate thermal store supplies the missing distinction.

A formula of the present body temperature alone cannot return both of those responses. If the unresolved dependence leaves a sufficient range of answers, retain that range instead of adding a state solely to obtain a single value.

#### MMP.1:4.4 - Supply the conditions needed for this formulation

Distinguish quantities that evolve inside the model from imposed inputs and boundary values. In the single-body example, T evolves; P(t) and T_a(t) may be prescribed by the surrounding arrangement.

A changing-temperature question requires an initial condition, such as T(0)=T_0. A distributed temperature model also needs the boundary conditions appropriate to the selected spatial equation. Their physical meaning can be an imposed temperature or a specified exchange relation at a boundary.

For a steady calculation, set accumulation to zero as part of the selected operating assumption. Retain the changing-state formulation when the output depends on the transient. A steady answer can be mathematically available while the time needed to approach it remains unanswered.

#### MMP.1:4.5 - Substitute the relations and identify what can be solved

Substitute the chosen response laws into the balance. For constant positive C and G, the single-body formulation becomes

`C*dT/dt = P(t) - G*(T-T_a(t))`,

together with its initial condition when a trajectory is requested.

At a specified state and input, this determines an instantaneous rate. With constant inputs and a steady operating assumption, it gives

`0 = P - G*(T-T_a)`.

Thus `T = T_a + P/G` under those conditions. This substitution provides the first usable calculation; a complete time-dependent solution is a further mathematical contribution.

For a network of linear equations, Mathematical Practice MATH.14 supplies elimination with recovery of the original unknowns and requested output. Check consistency rather than relying on an equation count. Two equations such as `x+y=1` and `x+y=2` are inconsistent; one equation `x+y=1` already fixes the output x+y despite leaving both coordinates unresolved.

If a response remains unknown, retain its admitted values or functional alternatives. Determine whether that variation changes the requested output. Return a result common to those alternatives when it suffices, or name the missing relation that changes the answer.

#### MMP.1:4.6 - Test the formulation and return to the affected premise

Check the meanings and units of the substituted terms. In the thermal example, C*dT/dt and G*(T-T_a) must both be powers. Under its passive linear-path assumption, G>0 makes heat loss positive when the body is warmer than its surroundings.

Use a simple condition that exposes the chosen laws. With P=0 and T=T_a, the thermal model gives zero rate. With P=0 and T>T_a, it gives cooling. A different result calls for inspecting signs, inputs or the response assumption before interpreting the calculation.

Keep the distinction between this calculation and reliance on an actual component's behavior. Revisit only a consequential unresolved applicability question. A change of material, range, spatial resolution or retained history can require a new relation; a change of numerical inputs within the same conditions may require only recalculation.

### MMP.1:5 - Archetypal Grounding

#### MMP.1:5.1 - Obtain a cooling rate and a changed-input steady answer

A body is represented by a uniform temperature T and heat capacity C=20 J/K. A homogeneous conducting link connects it to a reservoir at T_a=20 degrees Celsius. The link has length L=0.001 m, cross-sectional area A=0.000005 square metres and conductivity k=400 W/(m*K). These properties are stipulated over the temperature range in use.

Treat heat flow as one-dimensional along the link, with insulated sides and negligible contact resistance. Over the time interval being modeled, take the link's temperature profile to adjust rapidly enough that its own heat storage can be neglected. These conditions select the conduction relation

`q = (k*A/L)*(T-T_a)`,

so G=k*A/L=2 W/K. The material property and geometry supply G; the balance alone did not determine it. If the link's storage affects the requested transient, use a formulation retaining it, as in :5.4.

Initially T=30 degrees Celsius. With P=0, the formulation is

`20*dT/dt = -2*(T-20)`.

At that temperature the rate is -1 K/s. The steady calculation gives T=20 degrees Celsius.

Now supply P=12 W while retaining the same relations. The steady value is 26 degrees Celsius. At T=30 degrees Celsius, the instantaneous rate is (12-20)/20=-0.4 K/s. The added power reduces cooling at that state; it does not make the temperature rise there. To find the time to enter a specified temperature range, solve the changing-state equation with its initial condition.

#### MMP.1:5.2 - See what the balance leaves unresolved

A constant net input of 2 W acts on a body whose reference energy is zero at t=0. Its energy balance gives U(t)=2t joules.

Consider two admitted component descriptions over the same range:

- C=2 J/K, with U=C*(T-T_ref), gives a temperature rise of t kelvin when t is expressed in seconds.
- C=4 J/K gives a temperature rise of t/2 kelvin.

Both satisfy the same energy balance. The stored-energy question is settled under the input assumption; the temperature question depends on which heat-capacity relation applies. If only C in [2,4] J/K is known, the rise after one second lies in [0.5,1] K. A decision that accepts that entire interval needs no sharper capacity value.

#### MMP.1:5.3 - Apply the same formulation move to a capacitor

A supplied current I_in enters a node connected to an ideal capacitor and a resistor R in parallel; their other terminals share a reference node. Let V be the input node's voltage relative to that reference, and Q the charge on the capacitor plate connected to the input node. Treat charge storage in the connecting wires as negligible. Charge balance gives

`dQ/dt = I_in - I_out`.

The selected component relations are Q=C_e*V and I_out=V/R, with constant positive C_e and R. Substitution gives

`C_e*dV/dt = I_in - V/R`.

With C_e=0.5 F, R=3 ohms and I_in=2 A, the steady voltage is 6 V. At V=0, its rate of increase is 4 V/s. Charge balance supplied the relation between currents and accumulation; the capacitor and resistor laws supplied the response. A current-limited or voltage-dependent component would require its corresponding relation before using the same calculation.

#### MMP.1:5.4 - Retain a consequential state of the heat path

Consider a path with an intermediate thermal store at temperature T_l. Conductances G_1 and G_2 connect that store to the body and the reservoir respectively. The transfer relations are

`q_1 = G_1*(T-T_l)` and `q_2 = G_2*(T_l-T_a)`.

With heat capacity C_l for the intermediate store, the supplied two-store model is

`C*dT/dt = P-q_1`,

`C_l*dT_l/dt = q_1-q_2`.

Take C=20 J/K, C_l=2 J/K, G_1=G_2=4 W/K, T=30 degrees Celsius, T_a=20 degrees Celsius and P=0. A preparation with T_l=20 degrees Celsius gives q_1=40 W and a body cooling rate of -2 K/s. A preparation with T_l=30 degrees Celsius gives q_1=0 and zero initial body rate. The same body temperature and input therefore leave two different answers when the path's state is omitted.

Keeping T_l and its initial value lets the model distinguish the preparations. If only the steady result is required, set both storage rates to zero. The path equation then gives T_l=(T+T_a)/2 and q_1=2*(T-T_a), recovering the simpler conductance. For a transient, dropping the path's storage requires an approximation appropriate to its adjustment time and the requested answer.

The richer formulation adds one state, its initial condition, heat capacity and evolution equation. Use it when the differing rates matter; retain the simpler formulation for a question it already answers adequately.

### MMP.1:6 - Bias-Annotation

The examples use a few lumped temperature or voltage states. Their linear constitutive relations use the current states without additional history. Distributed fields, nonlinear responses, material transitions and unresolved scales can need a larger formulation.

The method also starts from an available balance. Some useful models begin from a different structure, such as allowed state transitions or a statistical observation relation. Their construction follows the relevant modeling method.

### MMP.1:7 - Conformance Checklist

- The balanced physical quantity and every introduced response quantity have recoverable meanings and units.
- Each substituted response law retains the conditions that matter to the requested use.
- Evolving state, prescribed inputs and initial or boundary conditions are distinguished.
- A steady assumption is used only for the question it can answer.
- Consistency and the requested output are examined; equation count alone does not settle them.
- A changed answer can be traced to a changed input, response relation or condition.
- Further characterization is selected for a consequential unresolved question.

### MMP.1:8 - Common Anti-Patterns and How to Avoid Them

**Read a material law out of conservation.** The two capacities in :5.2 conserve the same energy but predict different temperature rises. Supply the response relation or retain the resulting range.

**Hide a closure inside a familiar formula.** Writing C*dT/dt already treats C as the applicable heat capacity. Recover that assumption before reusing the expression for a new material or range.

**Replace the transient question with equilibrium.** The initial rate and steady temperature in :5.1 answer different questions. Keep storage and the initial condition when time matters.

**Treat more equations as closure.** A repeated or contradictory relation can add a row without determining a usable answer. Test what the combined formulation permits.

### MMP.1:9 - Consequences

The output is a formulation whose balances, response relations and conditions can be used and changed separately. It supports a first rate, steady value or other requested consequence, or shows the particular unresolved relation on which that consequence depends.

The work requires enough subject knowledge to choose meaningful state variables and applicable response laws. It can reduce later rework by making those choices available at the point where another mathematical or computational method uses the formulation.

### MMP.1:10 - Architectural Rationale

A balance constrains physical changes. A constitutive relation describes the response that makes those constraints calculable in the chosen variables. Keeping their contributions separate explains why the same conservation principle admits different materials and components.

A complete state problem needs its response relations and the appropriate initial or boundary data. A requested consequence can require less. The interval in :5.2 shows how a useful answer can survive an unresolved property.

The model's representation determines which responses must be supplied. A single temperature omits internal gradients. A reduced description can omit variables whose effect later appears as additional state, history or a fitted response. Restoring a consequential omitted dependence is a change to the formulation, not merely a more accurate value for an existing coefficient.

### MMP.1:11 - SoTA-Echoing

**How does a balance become a temperature equation?** Howison's [*Practical Applied Mathematics*, author version of 31 May 2004, §1.3](https://people.maths.ox.ac.uk/fowler/courses/tech/sdh.pdf) explicitly adds energy-temperature and heat-flux relations to conservation. Adopt the separation of balance and constitutive contribution; :4 and :5 make it usable for lumped components. The book is a historical foundation for this construction. Its treatment also shows that a response assumption can be implicit, as when inviscid-fluid forces are represented by isotropic pressure. Detailed fluid equations require their own physical and mathematical preparation.

**Which response law belongs to a physical path?** [OpenStax's treatment of heat-transfer mechanisms](https://openstax.org/books/university-physics-volume-2/pages/1-6-mechanisms-of-heat-transfer) supplies conduction through a material under the stated geometry and conditions. In :5.1, its conduction law gives G=k*A/L from the path's material and dimensions. The example states when heat stored in the path can be neglected. Convection, radiation or a different geometry can require another exchange relation.

**What changes when the missing response comes from unresolved scales?** [Sanderse, Stinis, Maulik and Ahmed's 2024 review, version 2](https://arxiv.org/html/2403.02913v2) compares closure-model forms, learning objectives, discretization and retained memory. Its §7.1 explains how omitted degrees of freedom can leave a history-dependent response. Adopt the need to specify the missing contribution and its inputs before selecting a learned relation. Fitting a closure and using it inside a computation require their corresponding methods.

**How much of the heat path must this question retain?** Apply that closure choice in :4.3 and the constructed case in :5.4. A relation using only the present body temperature is cheaper to supply and calculate, and it gives the steady answer in that case. The competing formulation retains the path's thermal state. It recovers the different initial cooling rates of a warm and a cold path at the cost of another state, initial value, capacity and equation. Retain the dependence that changes the requested answer. Reopen the choice when preparation, forcing time scale, resolution or output makes an omitted response consequential; :4.6 locates that return. Learned or nonlocal closures can supply other responses, with their own fitting and solution procedures.

### MMP.1:12 - Relations

- FPF [C.29.BB - Construct a Balance across a Boundary](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#c29bb---construct-a-balance-across-a-boundary) supplies the common balance construction used in :4.1.
- FPF [B.5.FM - Construct a First Model for the Working Question](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#b5fm---construct-a-first-model-for-the-working-question) supplies the initial question and model-construction route; this pattern develops a particular physical formulation.
- [MATH.14 - Eliminate Linear Unknowns and Recover the Answer](https://github.com/ailev/FPF/blob/main/MATHEMATICAL-PRACTICE-DPF.md#math14---eliminate-linear-unknowns-and-recover-the-answer) supplies reduction and recovery once the linear equations are formed.
- FPF [C.16.IR - Determine What an Indication Can Resolve](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#c16ir---determine-what-an-indication-can-resolve) supplies interpretation when the receiving question concerns observations and unresolved influences.
- FPF C.11.DUA selects additional examination when its expected contribution justifies the work; the numerical or physical characterization method supplies that examination.

### MMP.1:End

## MMP.2 - Choose Scales and Retained Terms for the Requested Answer

> **Type:** Method
> **Normativity:** Normative

### MMP.2:1 - Problem frame

Use this pattern when you have a model of a subject and need to decide which terms or state changes can be neglected for a particular answer. A settled temperature may suffice for a late-time question while giving a poor answer immediately after heating starts. A transport model may need diffusion near a boundary even when advection dominates over most of its length.

Start with the output, the part of the subject and the time interval about which the answer will be used. Choose scales that make the competing terms comparable. Examine a proposed simplification over that use, including its initial and boundary conditions. The first result is a retained formulation and the range of questions for which the available comparison supports it.

A *scale* is a reference magnitude used to express a variable or term relative to the question. A *regime* here is a range of conditions over which the same selected processes and approximations describe the behavior needed for the answer. The regime can vary across space or time within one modeled arrangement.

The worked cases require units, algebra, derivatives and elementary exponential functions. Their solution formulas are supplied. Deriving a new asymptotic expansion or solving a larger differential problem requires the corresponding mathematical method. If an applicable approximation already meets the same output requirement over the same conditions, use that result; reopen the selection when those conditions change.

### MMP.2:2 - Problem

Raw coefficient sizes depend on the units and scales used to write an equation. Even a small dimensionless coefficient can multiply a large derivative near a boundary or during a rapid change. Removing that term may prevent the simplified problem from meeting a condition that matters to the answer.

The importance of an omission also depends on the requested output. An error confined to a narrow region can have a small effect on a spatial average and a large effect on the value inside that region. A late-time approximation can answer a question at the end of an interval while failing over the whole interval.

The working difficulty is to choose a useful simplification with its operating range. Keeping every term can demand unnecessary analysis or computation; discarding one without examining its contribution can change the result on which the next action depends.

### MMP.2:3 - Forces

| Concern | Consequence for the choice |
| --- | --- |
| Question scale and intrinsic scale | The time available in the question can differ from a component's response time. |
| Bulk behavior and local change | A thin layer or short transient can govern a local output. |
| Equation and conditions | Dropping a derivative can remove the ability to satisfy an initial or boundary condition. |
| Available comparison and its cost | A supplied bound or solved case may settle the choice; a new simulation is useful only for a consequential remaining question. |
| Pointwise and aggregate outputs | An approximation can serve one output while exceeding the tolerance of another. |

### MMP.2:4 - Solution

**Name the output and its range → choose reference magnitudes → rescale the complete problem → examine the proposed omissions → compare their effect on the output → retain or revise the formulation.**

#### MMP.2:4.1 - Name the answer the simplification must preserve

State what quantity is needed, where and when it is needed, and what difference would change its use. This can be an allowable temperature error, a limit on a spatial average, or the distinction between reaching and missing a condition.

Distinguish a value at one time from a guarantee over an interval. Also distinguish an average from a maximum or a value at a named location. Express an available tolerance in the output's units. When a decision threshold rather than a numerical accuracy target governs the use, compare whether the approximation can change that decision.

Retain a conditional answer if a missing tolerance or applicability condition prevents a stronger conclusion. Obtaining a useful range can be enough to continue.

#### MMP.2:4.2 - Choose magnitudes from the subject and the question

Identify the lengths, durations and changes in quantities that the formulation compares. Use a difference from the relevant reference when the law concerns a difference: for cooling, use T-T_a relative to the surroundings, rather than the numerical Celsius value of T.

For a body with positive constant heat capacity C and conductance G, take the surroundings' temperature T_a as constant. The cooling model

`C*dT/dt = -G*(T-T_a)`

has an intrinsic response time

`tau = C/G`.

A question about a duration H introduces another time scale. If the initial temperature rise is Delta_T_0>0, set

`theta = (T-T_a)/Delta_T_0` and `s = t/H`.

The transformed equation and initial condition are

`(tau/H)*dtheta/ds = -theta`, with `theta(0)=1`.

The ratio tau/H compares the model's response time with the question's duration. The dimensional coefficient G/C alone does not make that comparison: 0.1 per second and 6 per minute describe the same response.

If a relevant scale is initially unknown, derive it from the competing terms or retain several candidate scales. A physical assumption such as a uniform body temperature or constant material property remains part of the formulation supplied through MMP.1.

#### MMP.2:4.3 - Rescale the conditions as well as the equation

Substitute the same scales into the domain, initial values, boundary conditions, imposed inputs and output expression. Keep the meaning of each rescaled quantity available for interpreting the answer.

For an imposed input that changes over a duration h, retain h/H or compare h with the response time. A large overall observation interval can still contain a short consequential forcing event.

When a coefficient is itself supplied by another model, carry that model's relevant conditions too. For example, a transport calculation using a velocity field must retain how the field was obtained if changing scale can change it. Matching one transport ratio is insufficient to reuse a solution whose geometry or boundary forcing has changed.

The result of this step is the whole rescaled problem needed by the selected output. Units disappear from its dimensionless variables; the physical assumptions and imposed conditions remain.

#### MMP.2:4.4 - Examine what happens when a term is removed

Write the proposed reduced equation and try to use its required conditions. When removing a time derivative loses the initial state, identify the initial transient over which that state still matters. When removing a spatial derivative prevents a boundary condition from being satisfied, inspect the region near that boundary.

Compare complete term magnitudes, including the variables or derivatives they multiply. If a field changes by order one over a dimensionless width delta, its first derivative can be of order 1/delta and its second of order 1/delta squared. A term with a small coefficient can therefore remain comparable to another term in a narrow region.

Use this term comparison to locate a possible error, then test its effect on the requested output in :4.5. If an available bound already makes that effect acceptable, keep the simpler answer. Otherwise retain the needed terms, restrict the approximation to a range where it suffices, or construct an approximation that resolves and joins the relevant regions. The latter choice needs its mathematical construction.

#### MMP.2:4.5 - Compare the omission in the requested output

Use the least costly available comparison that can settle the choice. It may be a solved case, a bound, a local term estimate, a supplied approximation result or a calculation of the competing formulation. A local estimate proposes where simplification may work; a claim about the whole output requires a comparison that reaches that output.

For the cooling problem with constant T_a in :4.2, the supplied solution gives the error of replacing the temperature by its steady value:

`error(t) = Delta_T_0*exp(-t/tau)`.

For a spatial question, evaluate the requested point, maximum or integral. An integral can suppress a localized discrepancy that remains large at a particular point.

These are comparisons with the supplied model. Its applicability to an actual subject is a separate premise: use the relevant physical or other subject knowledge to settle a consequential uncertainty there. C.11.DUA helps select further inquiry when its contribution relative to its cost is unresolved.

If the available range of omission errors leaves the same usable answer, stop refinement. If it straddles a consequential threshold, keep the richer formulation or select a worthwhile calculation or observation that can resolve that question.

#### MMP.2:4.6 - Return the answer with the conditions that change its use

Interpret the result in the original variables. Keep the selected region, time range, input conditions and output tolerance with it when another participant needs them to use the approximation.

A changed numerical input inside the same applicable regime may require only recalculation. A changed observation time, forcing speed, boundary condition or output location can require restoring a term or changing scale. A changed material law returns to MMP.1 or the corresponding formulation method.

The ordinary result is the usable model and interpreted answer, or the located condition still preventing that use.

### MMP.2:5 - Archetypal Grounding

#### MMP.2:5.1 - Choose a late-time cooling answer without losing the initial transient

Take the constant-property model from MMP.1 with C=20 J/K, G=2 W/K, fixed T_a=20 degrees Celsius and T(0)=30 degrees Celsius, with no heating. Its response time is tau=10 seconds. The supplied solution is

`T(t) = 20 + 10*exp(-t/10)`

when t is measured in seconds. Substitution into the differential equation and T(0)=30 verifies this solution.

Suppose the requested temperature error is at most 1 K. At t=1 second, replacing T by the steady value 20 gives an error of about 9.048 K. At t=100 seconds, the error is about 0.000454 K. The same steady approximation is inadequate for the first question and sufficient for the second under the supplied model.

Solving the inequality

`10*exp(-t/10) <= 1`

gives `t >= 10*ln(10)`, about 23.026 seconds. The steady answer is therefore within the tolerance throughout the later interval starting there. It does not meet that tolerance throughout [0,100] seconds: at its start the error is 10 K.

For H=100 seconds the dimensionless equation is `0.1*dtheta/ds=-theta`. Dropping storage gives theta=0, which cannot satisfy theta(0)=1. That mismatch locates the transient that the late-time use excludes. When a new heating input changes on a time scale comparable with or shorter than tau, restore the changing-state equation with the state at that change.

#### MMP.2:5.2 - Keep diffusion for a boundary value while simplifying an average

Consider steady transport of a passive dissolved substance along a channel of length L. The model uses constant speed u>0, constant diffusivity D>0 and uniform concentration across each section. The concentration c satisfies

`D*d2c/dx2 - u*dc/dx = 0`, with `c(0)=0` and `c(L)=c_b>0`.

The boundary arrangement maintains the stated concentrations. This is a stipulated one-dimensional model; its formulation supplies these conditions.

Set X=x/L, theta=c/c_b and epsilon=D/(u*L). The whole problem becomes

`epsilon*d2theta/dX2 - dtheta/dX = 0`, with `theta(0)=0` and `theta(1)=1`.

For L=1 metre, u=1 metre per second and D=0.01 square metres per second, epsilon=0.01. Removing diffusion gives dtheta/dX=0. Using the inlet condition then gives theta=0 everywhere, failing the maintained concentration at the other end.

The supplied solution of the full problem is

`theta(X) = (exp((X-1)/epsilon)-exp(-1/epsilon))/(1-exp(-1/epsilon))`.

It satisfies both boundary conditions. Differentiating it gives `epsilon*theta''=theta'`, verifying the equation. At X=0.99, theta is about 0.3679, so the zero approximation fails a pointwise tolerance of 0.02. At X=0.9, theta is only about 0.0000454.

Near the outlet, the concentration changes over length D/u=0.01 metre. In the corresponding dimensionless width epsilon, the derivative term and the diffusion term are both of order 1/epsilon. The small coefficient has not made the complete diffusion term small there.

Now ask only for the average concentration along the channel. The dimensionless average obtained by integrating the same solution is

`mean(theta) = epsilon - exp(-1/epsilon)/(1-exp(-1/epsilon))`,

approximately 0.01. For the decision, the simpler bound `0<=mean(theta)<epsilon` suffices: the full solution is nonnegative, and the subtracted fraction is positive. At epsilon=0.01, the zero approximation therefore has average error below 0.01*c_b, within the tolerance 0.02*c_b. Evaluating the small exponential correction is unnecessary for that answer. The near-outlet question instead retains diffusion or a suitable boundary-layer approximation.

The change in requested output, rather than a change in physical parameters, changes which approximation is useful.

### MMP.2:6 - Bias-Annotation

The worked cases use deterministic differential models with supplied solution formulas. This makes the comparison between omission and output visible. Stochastic models, uncertain parameters or learned responses can require a distributional error, an interval or a comparison over several allowed cases.

The term comparison is tied to the chosen formulation. Changing variables or rewriting the governing equation can change which terms appear separately. Interpret a claimed dominant process through the subject meaning of that representation.

### MMP.2:7 - Conformance Checklist

- The output, location or interval, and consequential difference are clear.
- Reference magnitudes make the relevant term comparison dimensionless.
- The rescaled formulation retains its initial, boundary and input conditions.
- A removed derivative's effect on those conditions has been examined.
- The comparison reaches the requested output and its stated range.
- A sufficient error range can stop refinement.
- Reuse after a changed question preserves the conditions on which the approximation depended.

### MMP.2:8 - Common Anti-Patterns and How to Avoid Them

**Treat a small written coefficient as a negligible process.** The same thermal rate coefficient is 0.1 per second or 6 per minute. Compare it with the question's duration. In the channel case, include the large near-boundary derivatives when comparing terms.

**Use a late-time result over the whole history.** The steady thermal answer is accurate at 100 seconds and inaccurate at the initial state. Keep the time range used by the error comparison.

**Transfer an average-error result to a local question.** The channel's zero approximation has small average error and large error near its outlet. Recompute the output whose value the next action actually uses.

**Choose an approximation from the equation while dropping its conditions.** The reduced transport equation cannot satisfy both maintained endpoint concentrations. Keep those conditions in the original problem and assess the resulting discrepancy in the requested output. Restore diffusion or construct a local approximation when that discrepancy makes the answer inadequate. A sufficient bound on the mean error can instead finish the average question, as in :5.2.

### MMP.2:9 - Consequences

The practitioner obtains a cheaper formulation where it suffices and retains complexity where it changes the requested result. The result also locates useful changes of scale: the early transient, thin layer or other regime that needs a different account.

This work depends on enough subject and mathematical knowledge to identify meaningful scales and compare consequences. A complex regime map can be costly to derive or infer. Its cost is warranted by the uses that need to distinguish those regimes.

### MMP.2:10 - Architectural Rationale

Scale selection connects the subject question to a mathematical simplification. The equation supplies possible responses; the subject and receiving question determine which response differences matter. This is why a coefficient ratio alone cannot settle the use of an approximation.

Initial and boundary conditions belong to the mathematical problem being simplified. Removing a derivative can reduce the number of conditions the reduced equation can satisfy. The resulting discrepancy can remain localized while still deciding a local answer.

An approximation's error belongs to a specified output and range. The thermal and transport cases show why one global label such as accurate would conceal a useful difference between accepted uses.

### MMP.2:11 - SoTA-Echoing

**How should a model be simplified when a scale ratio is small?** Howison's [*Practical Applied Mathematics*, author version of 2004, §3.1, especially pp.41-42](https://people.maths.ox.ac.uk/fowler/courses/tech/sdh.pdf), develops dimensionless comparison and shows how removing diffusion prevents the cylinder temperature condition from being satisfied. Adopt the whole-problem comparison, including boundary data and a coupled velocity account. The simple channel case in :5.2 adapts this issue into an explicitly solvable construction.

**What if the active processes vary over a large set of states?** [Callaham et al. (2021)](https://www.nature.com/articles/s41467-021-21331-z) evaluate governing-equation terms and identify local balances through clustering and sparse representation. They also show that interpretation depends on the equation representation. This supplies a serious alternative to an analyst choosing a few candidate scales: use available fields to identify different active-term combinations. Its gain is a map across many regimes; its cost includes data or simulation fields, term evaluation and learned regime identification.

For the small problems in :5, select rescaling and the supplied analytic comparison: they answer the chosen output without constructing a learned regime map. For spatially or temporally varied data where the candidate balance is not known, the alternative can justify that additional work.

Adapt both approaches through the output test in :4.5. A local active-term description still needs a consequence for the requested value, average or threshold before it supports that answer. Reopen the choice when new forcing, spatial resolution or a changed output makes a previously omitted process consequential. Sanderse et al.'s [2024 closure-model review](https://arxiv.org/html/2403.02913v2) adds the related issue that omitted state can require retained history; MMP.1 develops that formulation return.

### MMP.2:12 - Relations

- [MMP.1 - Complete a Balance Model with Constitutive Relations](#mmp1---complete-a-balance-model-with-constitutive-relations) supplies the physical storage and response formulation used in the cooling example; return there when the response law or retained state changes.
- FPF [C.29.1 - Mathematical Result Transfer](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#c291---mathematical-result-transfer) supplies the comparison between original and transformed mathematical accounts when a change may affect their conditions or requested output.
- FPF [B.5.MPC.R - Repair a Physical-Mathematical-Computational Connection](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#b5mpcr---repair-a-physical-mathematical-computational-connection) locates the contributing formulation or computation to revise when a connected answer fails.

- FPF C.11.DUA selects further examination when the value of the unresolved comparison is worth its cost. The selected mathematical, statistical or subject method supplies that examination.

### MMP.2:End

## MMP.3 - Construct a Steady Conductance Network

> **Type:** Method
> **Normativity:** Normative

### MMP.3:1 - Problem frame

Use this pattern when an arrangement can be described by connected parts, specified inputs and linear exchange paths, and you need a steady temperature, voltage or related flow. You know enough about the arrangement to select those paths and response laws, but still need to turn them into coupled equations and return the answer to the place or component named in the question.

This is the steady conductance-network branch of mathematical modeling. Assign one temperature or voltage to each junction; exchange through a path depends on the values at both ends. Each path has a fixed nonnegative conductance. Heat-transfer and resistor networks provide the worked uses. Other balance networks can require different response laws or additional variables.

Begin with the requested location and quantity. A question about the hottest point of a heater can require more than the temperature assigned to a whole junction. A reduced network can retain the surrounding flows while concealing the internal temperature that determines the answer.

The result is a network formulation and a calculated value, bound or unresolved condition for the requested use. Needed preparation is conservation of energy or charge, physical units, elementary simultaneous equations and interval bounds. The matrix explanation in :10 additionally uses basic linear algebra.

If an applicable network already supplies the requested answer, use it directly. When the question concerns a transient peak, retain storage and use the appropriate time-dependent formulation. MMP.1 supplies constitutive closure; MMP.2 helps decide when a steady approximation serves the specified time and tolerance.

### MMP.3:2 - Problem

The physical arrangement does not arrive as a system of equations. Choosing one temperature per part, an exchange path or an imposed boundary value determines which distinctions the calculation can retain.

Several failures can then produce a plausible number for the wrong question. Averaging two temperatures removes their contrast. A missing path changes the balance. Excluding an internal junction from the final unknowns can hide a heat source or a local maximum. More precise input values do not restore a spatial variation that the formulation omitted.

The modeling work is to construct the equations with their physical interpretation, preserve the information needed by the question, and identify which changed condition requires rebuilding them.

### MMP.3:3 - Forces

| Concern | Consequence for construction |
| --- | --- |
| Simple junctions and spatial variation | One temperature per junction reduces the equations; a requested point inside a body may need an additional relation or bound. |
| Shared exchanges and local balances | The same transfer joins two balances with opposite signs. |
| Boundary data and steady existence | A heat input needs an outlet in a steady model; an isolated component can leave an absolute temperature undetermined. |
| Fewer unknowns and retained output | Elimination can preserve boundary behavior while an internal answer still requires recovery. |
| Useful bounds and refinement cost | A conservative bound can settle the decision; a tighter one is useful when the distinction changes the intended action. |
| Reusable component laws and changed arrangements | A component relation may remain valid while connections, inputs or boundary conditions change. |

### MMP.3:4 - Solution

**Locate the requested result → choose junctions and exchange paths → join their balances → check steady solvability → solve and recover the output → bound omitted variation → use the answer or revise the affected premise.**

#### MMP.3:4.1 - Choose junctions for the physical question

Sketch the bodies or components, their contacts and their connections to the surroundings. Name the requested location, quantity and operating condition. For a thermal arrangement, this may be the hottest point of either heater slab after a steady state has been reached.

Assign one unknown temperature to each part being treated as isothermal. A part with a consequential temperature gradient needs several temperatures, a spatial model, or a bound relating its junction temperature to the requested point.

For each exchange path, supply its conductance and the relation it represents. MMP.1 describes how geometry, material behavior or an available component description supplies that relation. Separate imposed boundary temperatures from unknown junction temperatures.

Identify all heat inputs and outlets represented in this construction. A comparison can use stipulated paths and properties conditionally. Reliance on a particular device requires resolving the applicability questions that can change the intended use.

#### MMP.3:4.2 - Write a balance at each junction

For a thermal network, let T_i be the unknown temperature of junction i and P_i its specified net heat input. A positive P_i adds heat; a negative one removes it at the specified rate.

Let K_ij=K_ji be the conductance between unknown junctions i and j, and G_ia the conductance from i to an imposed-temperature boundary a at T_a. All conductances in this method are fixed and nonnegative; zero denotes an absent path.

Take the heat flow from i towards j as K_ij*(T_i-T_j). The same physical transfer appears with the opposite sign at j. With no accumulation, the balance is

`P_i = sum_a G_ia*(T_i-T_a) + sum_j K_ij*(T_i-T_j)`.

Each term is a power. Write one such equation for each unknown junction. On adding the equations, every exchange between unknown junctions cancels. The remaining heat input must leave through the boundary paths.

For a resistor network, use node voltage, injected current and electrical conductance in the corresponding current balance. Supply the electrical connections and component laws for that use; :5.3 works the substitution.

#### MMP.3:4.3 - Join relations before choosing a calculation order

The two ends of a finite-conductance path can have different temperatures. An ideal junction assigns a common temperature to its connected terminals. Taking the terminal flows outwards from the junction, their sum equals its specified net heat input in the steady model. Represent a consequential contact resistance as an exchange path between distinct temperatures.

Write these relations independently of which variable a solver will calculate first. This is the acausal form: component equations describe mutual constraints, and a selected analysis determines how to solve them.

The same description can support manual substitution or an equation-based modeling tool. When using a tool, inspect the generated variables and relations for the requested calculation. A component removed during symbolic simplification may still need a recovery expression for the output.

#### MMP.3:4.4 - Check the boundary conditions and steady solution

Under the stated fixed nonnegative conductances, an unknown-junction component has a unique temperature solution when it has a path of positive conductances to at least one imposed-temperature boundary. Trace those paths before relying on a numerical solution. Section :10 explains this condition.

For an isolated connected component, adding its balances gives `sum_i P_i=0`. A nonzero net input is incompatible with a steady solution in that construction. Revise the heat outlets, the input account or the steady assumption.

When the isolated component has zero net input, the connected linear equations determine temperature differences but leave a common additive temperature free. A difference or internal flow may therefore be answerable while an absolute-temperature question still needs a physical condition. The boundary condition supplies physical information; choosing a convenient number for the unknown temperature does not supply it.

For a different relation class, use its own existence and solution conditions. Nonlinear exchange, storage or an active component can change the formulation.

#### MMP.3:4.5 - Solve while retaining the requested information

Use direct substitution, useful coordinates or linear elimination. MATH.14 supplies elimination, consistency checks and recovery of requested outputs.

In a symmetric two-junction network, the mean and half-difference of temperatures separate total heating from unequal heating. Retain both if the maximum is requested; :5.1 derives the result.

When eliminating an internal junction, substitute its recovered temperature into the surrounding flow equations. Retain both the resulting conductances and the contributions of any input at that junction. Section :5.2 shows how an internal heater becomes two input terms in the reduced network.

Keep the recovery expression when the requested output includes an eliminated temperature. Substitute the calculated values back into the original balances. A zero-coupling or equal-input case can expose a wrong sign or a lost distinction.

For a numerical solution, judge the calculation error against the requested output tolerance. An algebraically correct reduction still needs an adequate numerical solution.

#### MMP.3:4.6 - Relate the network result to the requested point

A junction temperature can stand for the cooler face of a slab while the question concerns its hotter face. Supply the relation between them.

For a uniform slab with insulated sides, no internal heat generation and constant conductivity k>0, let q>=0 be the steady one-dimensional heat flow through every cross-section. Then

`T_hot - T_cool = q*L/(k*A)`,

where L is its length along the heat path and A its cross-sectional area. Obtain q from the relevant flow account. It equals a heater's power only when all that power crosses the slab.

Propagate input ranges and this spatial contribution using their actual meaning. Hard bounds support a worst-case bound. For statistical intervals, retain the coverage and dependence assumptions used in the propagation. Keep dependencies between shared quantities when seeking a tight bound.

A separate upper bound for each positive contribution can be sufficient even when the bound is conservative. Compare the resulting bound with the criterion. If it settles the intended action, further precision has no role in that decision.

#### MMP.3:4.7 - Return the answer and locate a useful revision

State the result for the requested point, operating condition and stated inputs. If it does not settle the question, identify the unresolved contribution that could change the answer: for example, the contact conductance, a spatial rise or the time needed to approach steady state.

Choose further modeling or characterization for that contribution when its expected value justifies the work. Improving measurement precision addresses uncertainty in measured inputs. An omitted physical variation instead needs a model term or a justified bound.

For a changed arrangement, return to its paths and conditions. Unequal conductances to the surroundings change the mean/contrast equations. A slab side loss changes the heat crossing the slab. A transient adds accumulation. Changing input values within the same formulation may require only recalculation.

### MMP.3:5 - Archetypal Grounding

#### MMP.3:5.1 - Bound the hottest point in a two-heater arrangement

Two heaters deliver powers P1 and P2 through uniform, insulated-sided slabs into isothermal junctions. Each junction loses heat to common surroundings at T_a through the same conductance G>0; the junctions exchange heat through K>=0. These are all the modeled heat paths, and stored energy is constant. Each slab carries its heater's entire power.

The balances are

`P1 = G*(T1-T_a) + K*(T1-T2)`,

`P2 = G*(T2-T_a) + K*(T2-T1)`.

Add the equations to find the mean m=(T1+T2)/2. Subtract them to find the half-difference d=(T1-T2)/2:

`m = T_a + (P1+P2)/(2*G)`,

`d = (P1-P2)/(2*(G+2*K))`.

Recover `T1=m+d`, `T2=m-d` and `max(T1,T2)=m+abs(d)`.

With T_a=20 degrees Celsius, P1=10 W, P2=2 W, G=0.2 W/K and K=0.1 W/K, the result is m=50 degrees Celsius, d=10 K, T1=60 degrees Celsius and T2=40 degrees Celsius. The ambient losses are 8 W and 4 W; the internal transfer is 2 W from junction 1 to junction 2. The first balance is 10=8+2 and the second is 2=4-2.

Equalizing the powers while keeping their sum fixed leaves m unchanged and removes d. For fixed unequal powers and fixed G, increasing K reduces abs(d). At K=0, the separate answers are T_a+P1/G and T_a+P2/G.

The question concerns the hottest point in either slab. For each slab, suppose L<=0.007 m, A>=0.0011 square metres, k>=100 W/(m*K), and its heater power is at most 10.2 W. The hot-face rise above its junction is bounded by

`P*L/(k*A) <= 10.2*0.007/(100*0.0011) = 0.6490909... K < 0.7 K`.

Now allow the stipulated hard ranges T_a=20+/-0.5 degrees Celsius, P1=10+/-0.2 W, P2=2+/-0.2 W, G=0.2+/-0.01 W/K and K=0.1+/-0.01 W/K. Positive denominators give the conservative bounds

`m <= 20.5 + 12.4/(2*0.19) < 53.131579 degrees Celsius`,

`abs(d) <= 8.4/(2*(0.19+2*0.09)) < 11.351352 K`.

Thus the hottest point is below

`53.131579 + 11.351352 + 0.7 = 65.182931 degrees Celsius`.

This bound satisfies a stipulated 66-degree criterion. It leaves a 64-degree criterion unresolved. The latter result selects a possible refinement question; it does not show that the device exceeds 64 degrees.

The separate maxima of m and abs(d) need not occur for the same inputs. That makes their sum conservative but still an upper bound. A tighter calculation retains the shared P1 and P2.

If the required criterion is 65 degrees, the first bound is inconclusive. A tighter calculation on the same inputs can settle it. Throughout these ranges P1>P2, so junction 1 is hotter, with

`T1 = T_a + ((G+K)*P1 + K*P2)/(G*(G+2*K))`.

Both power coefficients are positive. In the equivalent m+d expression, increasing G decreases both positive terms and increasing K decreases the contrast. The largest T1 therefore uses the upper T_a, P1 and P2 and the lower G and K:

`T1 <= 20.5 + 12.4/0.38 + 8/0.74 = 63.942389758... degrees Celsius`.

Adding the slab-rise bound gives a hottest-point bound below 64.591481 degrees Celsius. This settles 65 degrees without new measurements; 64 degrees remains unresolved by this bound. The earlier calculation already settled 66 degrees and needed no such refinement.

#### MMP.3:5.2 - Reduce a heated junction without losing its contribution

A steady junction h receives power P and connects only to b and c through conductances g_b>0 and g_c>0. For given temperatures T_b and T_c, its balance gives

`P = g_b*(T_h-T_b) + g_c*(T_h-T_c)`,

`T_h = (P + g_b*T_b + g_c*T_c)/(g_b+g_c)`.

Define `g_eff = g_b*g_c/(g_b+g_c)`. Substituting T_h into the outward flows yields

`q_hb = g_b*P/(g_b+g_c) + g_eff*(T_c-T_b)`,

`q_hc = g_c*P/(g_b+g_c) + g_eff*(T_b-T_c)`.

Their sum is P. The reduced network therefore has conductance g_eff between b and c, plus heat inputs g_b*P/(g_b+g_c) and g_c*P/(g_b+g_c) at those junctions. Insert these expressions into the surrounding balances.

With P=0, this gives the usual series-conductance relation. With heating, retaining only g_eff discards the input and changes the network's heat balance.

For P=12 W, g_b=g_c=1 W/K, T_b=30 degrees Celsius and T_c=20 degrees Celsius, recovery gives T_h=31 degrees Celsius. The outward flows are 1 W to b and 11 W to c, adding to 12 W.

A calculation reporting only the two boundary temperatures would miss the internal maximum. Against a stipulated 30.5-degree limit, the omitted temperature changes the answer. Keep the recovered T_h if the maximum is part of the output.

Repeated elimination uses the same substitution when the relevant linear subsystem is solvable. A transient internal junction requires storage and its changing state, or a steady approximation appropriate to the requested time window. Nonlinear exchange requires its own solution or approximation.

#### MMP.3:5.3 - Formulate a resistor network

Two circuit nodes connect to a common reference conductor through resistances of 2 ohms each. A 1-ohm resistor connects the nodes. Ideal current sources inject 3 A into node 1 and 1 A into node 2, returning through the reference conductor. Treat the resistors as linear and the node charge as constant.

Let V1 and V2 be voltages relative to that conductor. Conductances are G=0.5 siemens to the reference and K=1 siemens between nodes. Current balance gives

`3 = 0.5*V1 + (V1-V2)`,

`1 = 0.5*V2 + (V2-V1)`.

The same mean/half-difference calculation gives m=4 V and d=0.4 V, hence V1=4.4 V and V2=3.6 V. The connecting resistor carries 0.8 A from node 1 to node 2. The reference paths carry 2.2 A and 1.8 A, so the balances are 3=2.2+0.8 and 1=1.8-0.8.

The algebra is shared with :5.1; its variables now denote voltages and charge-transfer rates. Choosing zero volts at the reference sets the voltage convention. The thermal case instead requires the surroundings' physical temperature to answer an absolute-temperature question.

#### MMP.3:5.4 - Recognize when a steady answer is unavailable or partial

Take two thermal junctions joined by K=1 W/K and isolated from the surroundings. Supply P1=2 W and P2=0. Their balances would require

`2 = T1-T2` and `0 = T2-T1`.

Adding them gives 2=0. The selected network cannot maintain steady stored energy. A time-dependent model, a missing heat outlet or a changed input is needed to continue the physical question.

Now let the second junction remove 2 W, so P2=-2 W. The equations agree and fix T1-T2=2 K. Every pair T1=t+2, T2=t satisfies them. Heat flow is determined; the hottest absolute temperature is not. The result is already sufficient for a question about the temperature difference. An absolute-temperature use needs the additional physical condition.

### MMP.3:6 - Bias-Annotation

The selected branch assumes a finite set of junctions, reciprocal linear exchange with nonnegative conductances, prescribed inputs and a steady operating condition. Spatial gradients enter through additional relations or bounds.

These assumptions make component connection and elimination tractable. Fluid transport, radiation, variable material response and active circuits can require different equations. The construction here helps identify the changed contribution; the corresponding modeling method supplies it.

The examples favor small networks that can be inspected by hand. For a large numerical calculation, use a solver suited to the matrix structure, conditioning and requested accuracy. A reduction can connect previously unconnected retained nodes and make the remaining matrix denser.

### MMP.3:7 - Conformance Checklist

- The requested quantity, location and steady operating condition are recoverable.
- Each junction and path has its physical meaning, exchange law and units.
- Internal exchanges have opposite signs in neighboring balances and cancel in the total.
- The stated boundary paths or unresolved common temperature agree with the solution claim.
- Elimination retains input contributions and recovers every internal quantity needed by the output.
- A point inside a lumped body has a relation or bound connecting it to the junction result.
- Propagation respects the meaning of ranges and any dependencies needed by the conclusion.
- A changed result leads to the relevant input, path, relation, resolution or operating condition.

### MMP.3:8 - Common Anti-Patterns and How to Avoid Them

**Use the mean as the maximum.** The unequal inputs in :5.1 leave a 10 K half-difference. Recover both temperatures or retain m+abs(d) for the maximum.

**Remove a source with its internal node.** In :5.2, the input becomes two terms in the boundary balances. Carry those terms through elimination.

**Accept the boundary answer for an internal question.** The same reduced case preserves the surrounding flows while its 31-degree internal junction exceeds both boundary temperatures. Recover the internal output.

**Force an isolated heated system to be steady.** The nonzero total input in :5.4 contradicts the sum of the steady balances. Inspect the time dependence or omitted outlet before solving again.

**Polish inputs while leaving out the requested location.** A more precise junction temperature still needs the slab relation when the question concerns its hot face. Add or bound that spatial contribution.

### MMP.3:9 - Consequences

The construction connects an arrangement to an answer about its components and locations. It makes the effect of a changed input, connection or boundary condition available for calculation.

It also permits a useful division of work. A subject practitioner supplies the component interpretation and response laws; a mathematical or computational contributor solves the equations; the receiving practitioner uses the recovered output under the stated conditions.

The cost is choosing the junction resolution and obtaining adequate relations. Retaining recovery expressions and output bounds can keep this cost below that of solving a more detailed model for every question.

### MMP.3:10 - Architectural Rationale

Balances connect the components, and response laws make the transfers calculable. Writing their joint relations before a calculation order preserves this separation when manual work is replaced by a solver. The common balance construction remains in FPF C.29.BB; MMP.1 supplies closure and MATH.14 supplies linear elimination.

The boundary-path condition has a useful mathematical explanation. Write the unknown-temperature equations as A*T=b. The diagonal entry A_ii is the sum of conductances incident on i, including its boundary paths; an off-diagonal A_ij is -K_ij. The right side is P_i+sum_a G_ia*T_a.

For a real vector x of temperature changes, expanding the quadratic form gives

`x^T*A*x = sum_{i<j} K_ij*(x_i-x_j)^2 + sum_{i,a} G_ia*x_i^2`.

Every term is nonnegative. A zero sum requires equal x along each positive internal path and x_i=0 at every node with a positive boundary path. If every connected component reaches a boundary, only x=0 satisfies this condition; A is positive definite and the finite linear system has a unique solution for every b.

An isolated connected component instead allows a common nonzero x. Its matrix kernel consists of constant vectors. The right side is compatible precisely when its entries sum to zero, giving the partial answer in :5.4.

This reasoning explains the formulation's solvability under its stated assumptions. It leaves the physical adequacy of the chosen paths and steady condition to their corresponding inquiry.

Elimination preserves the selected boundary equations, while recovery carries the internal answer. A spatial bound serves a different relation: it connects a junction's lumped temperature to a physical location omitted by that resolution. Keeping both relations visible permits reduction without losing the question.

### MMP.3:11 - SoTA-Echoing

**How can component equations remain reusable across different calculations?** The current [Dyad component tutorial](https://help.juliahub.com/dyad/stable/tutorials/creating-components.html) distinguishes connector potentials and flows and writes a resistor using constitutive and balance relations. Adopt this relation-first construction in :4.2-:4.3. It allows the same component description to enter different connected models and analyses.

**What does network reduction preserve?** Dörfler and Bullo's [*Kron Reduction of Graphs with Applications to Electrical Networks*](https://motion.me.ucsb.edu/pdf/2011d-db.pdf), published in 2013, is a mathematical foundation for eliminating internal nodes. Its opening construction transforms both conductances and internal injections. Section :5.2 works the corresponding thermal substitution and retains internal-temperature recovery for a different receiving question. Use direct solution when reduction offers no benefit; fewer retained unknowns can come with denser couplings.

**How is a temperature at a physical point recovered from a lumped answer?** [OpenStax, *University Physics*, volume 2, §1.6](https://openstax.org/books/university-physics-volume-2/pages/1-6-mechanisms-of-heat-transfer) supplies the steady slab-conduction relation. Here it bounds the hot-face rise under the stated one-dimensional geometry and insulated sides. A distributed formulation is the alternative when that bound cannot answer the requested spatial question.



### MMP.3:12 - Relations

- FPF [C.29.BB - Construct a Balance across a Boundary](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#c29bb---construct-a-balance-across-a-boundary) supplies the balance and cancellation used in :4.2.
- [MMP.1 - Complete a Balance Model with Constitutive Relations](#mmp1---complete-a-balance-model-with-constitutive-relations) supplies storage and exchange relations.
- [MMP.2 - Choose Scales and Retained Terms for the Requested Answer](#mmp2---choose-scales-and-retained-terms-for-the-requested-answer) selects a regime or approximation for the requested place, time and tolerance.
- [MATH.14 - Eliminate Linear Unknowns and Recover the Answer](https://github.com/ailev/FPF/blob/main/MATHEMATICAL-PRACTICE-DPF.md#math14---eliminate-linear-unknowns-and-recover-the-answer) supplies the general elimination, output and recovery methods.
- FPF [A.22.CGUS - Constraint-Governed Unfolding Structure](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#a22cgus---constraint-governed-unfolding-structure) describes alternative next actions and their enabling conditions. After an insufficient network bound, these can include refining an input range or changing the spatial model.
- FPF [C.29.1 - Mathematical Result Transfer](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#c291---mathematical-result-transfer) supplies the result-transfer question when changed coordinates or a reduction alter which outputs remain recoverable.
- FPF [C.16.MR - Construct a Measurement Relation](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#c16mr---construct-a-measurement-relation) supplies the relation needed when a measured indication is used to determine a model input.
- FPF [B.5.MPC.R - Repair a Physical-Mathematical-Computational Connection](https://github.com/ailev/FPF/blob/main/FPF-Spec.md#b5mpcr---repair-a-physical-mathematical-computational-connection) supplies the return when the interpreted answer and the physical or computational account no longer agree.

### MMP.3:End

# Part B - Model observations and interacting work

## MMP.4 - Associate Observations under Motion Bounds

> **Type:** Method
> **Normativity:** Normative

### MMP.4:1 - Problem frame

Use this pattern when two sets of position observations may concern the same moving objects and you need to establish their correspondence. A supported bound on motion can exclude some pairs. The remaining pairs must cover the observed population and satisfy the conditions of the measurements together.

Start with the elapsed time, the position ranges and the motion bound for each earlier object. Construct where each object could be at the later time. This gives candidate pairs and, sometimes, the identification already needed.

The method covers point objects moving independently on a line, with the same objects observed once each at two times. Its first branch admits every combination of positions within the supplied intervals. Its second retains one additive offset shared by all later readings. Both allow objects to cross. The useful result is a unique correspondence under that account, two feasible alternatives, a conflict among the premises and observations, or a qualified partial calculation.

The reader needs interval arithmetic, speed and elapsed time. [MATH.15 - Find a Complete Matching and Test Uniqueness](https://github.com/ailev/FPF/blob/main/MATHEMATICAL-PRACTICE-DPF.md#math15---find-a-complete-matching-and-test-uniqueness) supplies the finite pairing and search methods. Small cases can be enumerated by hand.

Use an already supported identifier directly when it settles the question. Missed detections, additional objects, interacting motion, uncertain observation times or probabilistic errors require their corresponding observation and motion relations. The construction can still test a proposed restricted account, with the conclusion kept conditional on it.

### MMP.4:2 - Problem

A nearby later observation can belong to another object. Choosing the nearest observation for each earlier one can also allocate the same observation twice.

A collective pairing repairs only part of the problem. Separate position intervals can hide a common instrument error. Each pair may then have a possible explanation, while their explanations require incompatible values of that error.

The modeling task is to construct the admissible pairs from the physical and observation conditions, retain the relations shared across pairs, and determine which correspondence those conditions support. A graph algorithm receives this formulation; it does not choose the motion or measurement assumptions.

### MMP.4:3 - Forces

| Force | Tension |
| --- | --- |
| Local compatibility and population coverage | An allowed pair needs compatible motion, while a full association must account for every observed object once. |
| Compact ranges and shared influences | Intervals simplify reachability, but independently combining their values can lose a common calibration constraint. |
| A feasible account and identification | One association explains the observations; identification requires excluding the remaining associations allowed by the account. |
| More detailed motion and cost of solution | A speed bound permits simple interval calculations; path interactions or acceleration conditions can require a different feasibility method. |
| Unresolved identity and a useful answer | Different identities can leave a requested quantity unchanged; further identification work is useful only when that difference matters. |

### MMP.4:4 - Solution

**Recover the observation and motion conditions → construct reachable intervals → form a complete pairing → test shared conditions → return the supported correspondence or unresolved difference → revise the contribution that changes the answer.**

#### MMP.4:4.1 - State what the observations and motion account admit

Let X_i be the earlier position interval for object i, and Y_j a later position interval. Use closed, nonempty intervals in the same coordinate system and units. A singleton represents a supplied position without uncertainty in this account.

There are n earlier and n later observations. Each of the same n objects contributes exactly one observation to each set. The elapsed time is Δt > 0.

For each earlier object, let v_i ≥ 0 bound its speed throughout the interval. The admitted paths satisfy

    |x_i(t)-x_i(s)| <= v_i*|t-s|

for every two times in that interval. Every path satisfying this condition is allowed, independently of the other objects' paths. This permits crossings and supplies no acceleration or collision restriction.

Recover the meaning of the position ranges. In the first branch, every combination of positions from the X and Y intervals is admitted: the joint domain is their Cartesian product. Independent motion does not establish this measurement condition. With a shared offset or another coupled observation relation, retain that relation for :4.4.

A hard error range and a confidence interval support different conclusions. Use the range according to the observation method that supplied it. If its interpretation or another premise is unresolved, the calculation describes what follows from the proposed account.

State what the receiving work needs. It may need every object's later identity, the identity of only one object, or a quantity that several associations share.

#### MMP.4:4.2 - Derive reachable intervals and construct a pair witness

Write X_i=[x_i^-,x_i^+]. During Δt, the maximum admitted displacement is v_i*Δt, so the later reachable interval is

    R_i = [x_i^- - v_i*Δt, x_i^+ + v_i*Δt].

Allow pair (i,j) precisely when R_i intersects Y_j. For intervals, this is the test

    max(lower(R_i),lower(Y_j)) <= min(upper(R_i),upper(Y_j)).

The test has a constructive meaning. Choose z in the intersection. Choose the nearest point x of X_i to z: x is z when z lies inside X_i, and the nearer endpoint otherwise. Then |z-x| <= v_i*Δt. The straight path from x to z over Δt satisfies the speed bound and both observations.

For X=[0,1], v*Δt=0.5 and Y=[1.4,1.6], the reachable interval is [-0.5,1.5]. Choose z=1.4 from the intersection and x=1 from X; the displacement 0.4 satisfies the motion bound.

Under the Cartesian-product observation account, these endpoint choices can coexist for disjoint pairs. Their straight paths can also coexist because independent point motion permits crossings. With coupled measurement or path conditions, the intersection test supplies only preliminary pairs; those additional conditions still need a joint witness.

With numerical enclosures, disjoint outer intervals exclude a pair, but overlapping enclosures may leave the original intersection unresolved. Before using an overlap as a feasible pair, establish a witness satisfying the original position ranges and speed bound. Otherwise retain it as a preliminary pair and refine the calculation when it can change the requested answer. Keep an admitted touching endpoint rather than dropping it through rounding.

For example, X={0} and v*Δt=1 cannot reach the supplied position Y={1+2^(-54)}. An outer numerical enclosure [1,1+2^(-52)] for Y overlaps [-1,1], but its point 1 does not belong to Y. That overlap supplies no feasible path for the original observation.

#### MMP.4:4.3 - Apply one-to-one coverage and the required uniqueness test

Form a bipartite graph with earlier observations on the left, later observations on the right, and the allowed pairs as edges. Complete coverage means n disjoint pairs.

Use MATH.15 to find a complete matching. For a small graph, list the assignments and discard any containing a forbidden pair. For a larger graph, alternating reassignment can complete a pairing without listing every possibility. If an exhausted search produces a left subset with too few right neighbors, no complete association exists in the graph.

When the Cartesian-product observation and independent-motion conditions apply, each complete matching with pair witnesses satisfying the original conditions has jointly compatible positions and paths constructed through :4.2. Use MATH.15's uniqueness test if identity matters. Two such matchings establish ambiguity. Excluding every alternative establishes uniqueness under the stated account.

With an additional shared condition, pass candidate matchings to :4.4 before drawing either conclusion. Failure of a complete graph matching's joint test leaves the other graph matchings available for testing.

A search interrupted before the required exclusions yields a partial result. Preserve its established candidates and exclusions rather than classifying the observation account as inconsistent.

#### MMP.4:4.4 - Retain and solve a shared measurement condition

Consider a common additive offset in the later readings. Earlier positions x_i are supplied without uncertainty. Each later reading r_j obeys

    r_j = later_position_j + b, with b in B=[b_min,b_max].

There are no other observation errors in this branch. The same b applies to every later reading. Keep the population and independent-motion conditions from :4.1.

The marginal position interval for reading r_j is [r_j-b_max,r_j-b_min]. It can be used to construct preliminary edges through :4.2. For a complete matching π, the speed bound for each selected pair requires

    b in [r_π(i)-x_i-v_i*Δt, r_π(i)-x_i+v_i*Δt].

Intersect these intervals over all selected pairs with B:

    B_π = B intersect all_i [r_π(i)-x_i-v_i*Δt, r_π(i)-x_i+v_i*Δt].

A nonempty B_π supplies an offset common to the whole matching. Choose b from that intersection. Set each later position to r_π(i)-b and use the straight paths from its earlier x_i. These values jointly satisfy the readings and motion bounds.

For numerical approximations, apply :4.2's distinction: a nonempty outer enclosure of B_π leaves feasibility open until one b is shown to satisfy the original shared-offset inequalities. An empty outer enclosure excludes the matching.

An empty intersection excludes this matching. Classify only the matchings whose intersection is nonempty. For a small set, MATH.15:4.5 enumerates candidates. During that enumeration, an empty intersection for already selected pairs also excludes every completion: adding more intervals cannot make it nonempty.

A different shared-error model requires its own joint calculation. For example, an offset shared by both earlier and later readings changes the displacement relation; it is not the later-only convention above. Retain the actual observation relation and use C.16.IR to determine what its compatible cases resolve.

#### MMP.4:4.5 - Return the distinction needed by the work

A unique jointly feasible matching establishes correspondence within the admitted observation and motion account. It may leave the paths, intermediate positions or offset unresolved. Two jointly feasible matchings establish an ambiguity in association; keep enough of their endpoint or shared-offset witnesses to show that both satisfy the conditions.

Excluding every candidate establishes that the supplied observations and conditions are inconsistent. Locate a conflict that can guide a correction. The cause could concern the population, elapsed time, motion bound or measurement relation; the graph alone does not identify it.

Use the result at the scope that the receiving question needs. If all feasible associations yield the same requested answer, stop with that answer. Section :5.2 shows a current separation that is known while identity remains ambiguous.

If different feasible cases would change the action, compare a discriminating observation, an already available feature, a revised premise or acting with the remaining uncertainty. C.11.DUA helps when their value and effort need comparison. A repeated observation is useful only if its possible result can distinguish what matters.

#### MMP.4:4.6 - Revise the affected construction

A changed speed bound, interval or elapsed time changes the corresponding reachable intervals and edges. MATH.15 can reuse a surviving matching while revisiting any affected uniqueness claim.

A changed shared-error relation can change joint feasibility even when every graph edge remains. Recalculate the relevant B_π or its replacement. A changed population premise requires a new coverage formulation before matching.

A supported no-passing condition changes which paths can coexist. Apply it to candidate associations rather than adding it silently after the crossing-permitted calculation. If the requested output alone changes, first inspect the retained feasible cases for that output.

### MMP.4:5 - Archetypal Grounding

#### MMP.4:5.1 - Identify two observed markers through reachable motion

Two point markers are observed at -3 m and +3 m. One second later their positions are -2.2 m and +2.4 m. Each speed is at most 1 m/s. All positions are supplied without uncertainty under the population conditions of :4.1.

The reachable intervals are [-4,-2] and [2,4]. Only -3→-2.2 and +3→+2.4 are allowed. They form the unique complete matching.

Straight paths with speeds 0.8 m/s and 0.6 m/s witness feasibility. The calculation identifies which later marker can continue each earlier one under these conditions; it leaves their intermediate motion unspecified.

Now keep the earlier observations but change the later positions to -2.2 m and -2.0 m. Each later position has an admitted predecessor, but both can come only from the first earlier marker. The second has no partner, so complete coverage fails. The contradiction concerns the combined observations and premises, not merely the order in which pairs were tried.

#### MMP.4:5.2 - Keep identity unresolved when the requested separation is known

Observe two point objects at -0.1 m and +0.1 m at both times, one second apart, with the same 1 m/s bound.

Stationary paths give one matching. Straight crossing paths give the other, each at speed 0.2 m/s. Both satisfy the admitted account. Choosing the nearest later point returns the stationary matching but does not exclude the crossing one.

If the question is the distance between the objects at the later observation time, both matchings give 0.2 m. That question is settled without another observation. If the question is which earlier object occupies the right position, the two witnesses disagree.

A supported no-passing condition would reject the crossing association: continuous paths that reverse their order must meet. That changed physical premise resolves the association; it is additional to the speed-bound account. A question about minimum separation during the interval remains a different question from separation at its endpoint.

#### MMP.4:5.3 - Reject a pairing that needs two different instrument offsets

Two stationary objects have earlier positions 0 m and 10 m. Later readings share b in [-1,1] m.

Readings 1 m and 11 m give marginal position intervals [0,2] and [10,12]. Each can be paired only with its nearby stationary object. The matching requires b=1 from both readings, so B_π={1}; it is jointly feasible.

Change the second reading to 9 m. The marginal intervals are now [0,2] and [8,10], and the graph still has a unique complete matching. The first pair requires b=1 and the second b=-1. Their intersection is empty.

Return the conflicting requirements b=1 and b=-1 to the measurement account. Use the actual observation arrangement to decide which premise needs revision.

#### MMP.4:5.4 - Continue after the first shared-offset candidate fails

Let earlier objects A and B have positions x_A=0 m and x_B=2 m, Δt=1 s, and both speed bounds 1 m/s. Later readings, in their received order, are r_1=2 m and r_2=0 m. Their common offset lies in [-2,2] m.

The marginal intervals are [0,4] and [-2,2]. Both intersect each earlier object's reachable interval, so all four graph edges are present.

Try matching A→1 and B→2. The first pair requires b in [1,3], while the second requires b in [-3,-1]. Their intersection is empty, so this candidate fails.

The other matching, A→2 and B→1, requires b in [-1,1] for each pair. It survives with B_π=[-1,1]. Choosing b=0 gives stationary paths and realizes both readings. Both graph matchings have now been tested, so this is the unique joint association.

Identity is resolved while the common offset remains an interval. Stopping after the failed first matching would instead have returned a false inconsistency.

### MMP.4:6 - Bias-Annotation

Visual proximity encourages an early identification even when the motion account admits another path. The crossing case supplies two different path arrangements compatible with the observations.

A calibration parameter can disappear when readings are converted independently to intervals. State which values can coexist before treating separate ranges as a joint model.

The convenient order of a matching search can become mistaken for a physical preference. Search order controls which candidate is obtained first; the observation and motion conditions determine which candidates are feasible.

### MMP.4:7 - Conformance Checklist

- The population, observation times, coordinate convention, interval meaning and speed bounds are recoverable.
- Reachable intervals and allowed edges follow from the stated motion account.
- Every returned association covers each observation exactly once.
- Each claimed feasible association has endpoints and paths satisfying all shared conditions, including a common offset when present.
- Uniqueness, ambiguity, inconsistency and incomplete search have their corresponding mathematical basis.
- The returned conclusion answers the requested identity or quantity question under its observation premises.
- A proposed further observation can change a relevant unresolved answer.

### MMP.4:8 - Common Anti-Patterns and How to Avoid Them

**Identify by nearest position.** The crossing case admits another correspondence. Test reachability and collective coverage before relying on proximity.

**Treat marginal intervals as independently selectable.** In :5.3 this accepts readings that require two values for one offset. Retain the shared unknown and intersect its requirements.

**Reject the account after its first candidate fails.** In :5.4 the second graph matching is feasible. Complete the relevant search or return its remaining uncertainty.

**Force identification for an already resolved quantity.** In :5.2 endpoint separation is fixed while identity is ambiguous. Use that common answer when it is the one needed.

### MMP.4:9 - Consequences

The method turns motion and measurement assumptions into an association that can be used, disputed or revised. A shortage of partners rules out complete graph coverage; a failed shared-condition test excludes the tested candidate.

The simple branch has a graph solution because it deliberately admits independent endpoint choices and crossing paths. More realistic interactions or observation dependencies can improve identification while increasing the work required to establish feasibility.

The association result supports subsequent estimation or action under its premises. It also indicates when the next useful contribution concerns the observation model rather than a more elaborate matching algorithm.

### MMP.4:10 - Architectural Rationale

The formulation joins three different constructions. Motion converts a position range into a reachable interval. The population premise becomes one-to-one graph coverage. The measurement relation determines whether the selected endpoints can occur together.

For the Cartesian-product branch, the nearest-point choice and straight paths show sufficiency of interval intersection, not only necessity. That is why a complete graph matching supplies paths and measurement values satisfying this restricted account.

The shared-offset branch keeps a continuous unknown with a discrete association. Intersection is sufficient here because one scalar offset and independent paths provide the whole remaining condition. A more general relation can require another feasible-set construction.

The pattern uses the mathematical matching method and C.16.IR's common interpretation method. Its own contribution is the motion-and-observation formulation, the witnesses that connect the mathematical result to that account, and the revision of those premises when the result fails.

### MMP.4:11 - SoTA-Echoing

**What makes an identification informative?** [Rodin, *Venus Homotopically*, sections 3, 6 and 8](https://philsci-archive.pitt.edu/12116/1/vh.pdf) distinguishes a naming convention from identity supported by a connecting construction, and possible paths from an actual trajectory. Adapt this distinction in :4.2 and :4.5: construct an admissible path as a feasibility witness, and establish identification by excluding the other correspondences admitted by the observation and motion conditions.

**When should the small interval-and-matching construction be replaced?** The [Codac v1 dynamic localization lesson](https://codac.io/v1/tutorial/07-data-association/index.html), accompanying Rohou, Desrochers and Jaulin's ICRA 2020 work, combines evolution equations, observation equations and unknown landmark association in a constraint network. It supplies an implemented alternative for a longer history and richer geometry. The small model here permits direct enumeration and explicit witnesses; the constraint approach keeps coupled continuous and discrete variables when that enumeration becomes impractical. A contracted enclosure must still be interpreted according to what its method establishes about existence and remaining alternatives.

**When are probabilities part of the answer?** The [Stone Soup joint probabilistic data association tutorial](https://stonesoup.readthedocs.io/en/stable/auto_tutorials/08_JPDATutorial.html) combines probabilities of globally consistent associations, including missed detections. Use that family when a probabilistic motion, detection and clutter account is supplied and the receiving question needs its estimates. Membership in the hard intervals used here supplies feasibility, with no probability ranking among the feasible pairings.

These alternatives differ in the observation conditions and the result sought. The shared-offset cases show why selecting a fast graph solver alone cannot repair a lost measurement dependency. Reconsider the method when the motion relation, error dependence, population, observation window or requested output changes.

### MMP.4:12 - Relations

- **MATH.15** supplies finite matching, shortage witnesses, uniqueness tests and search with a shared condition. This pattern constructs their motion and observation inputs.
- **C.16.MR and C.16.IR** construct a measurement relation and determine what its jointly compatible cases resolve. The shared-offset branch supplies a concrete interpretation calculation.
- **C.29** connects the mathematical account and its consequence to the working question. **C.29.2** helps construct a required computation; **C.29.3** connects it with input preparation, execution and readout.
- **B.5.MPC.R** coordinates a revision that crosses the physical account, mathematical formulation and computation.
- **C.11.DUA** helps compare the value of reducing a consequential ambiguity with the effort of the next contribution.

### MMP.4:End

## MMP.5 - Model Overlapping Work with Shared State

> **Type:** Method
> **Normativity:** Normative

### MMP.5:1 - Problem frame

Use this pattern when separately reasonable activities read or change something in common, and their order may change the result. Two people can promise the same remaining appointment; two programs can each increase a total while one increase disappears.

Build a discrete state model of the work. Represent what each participant has observed, what it can do next, and what others can change in between. Calculate the permitted sequences and use their results to change the proposed way of working.

The construction here covers a finite initial-state set and finitely branching activity within a stated step bound. It can establish a result for that bounded model, produce a sequence that defeats it, or leave a specified part unexplored. Repeated work beyond the bound needs a further argument. The shared-counter construction in :5.1 also gives a calculation valid for an arbitrary initial integer.

The reader needs variable substitution, conditional rules and finite enumeration. [MATH.1 - Build a Structure of Composable Paths](https://github.com/ailev/FPF/blob/main/MATHEMATICAL-PRACTICE-DPF.md#math1---build-a-structure-of-composable-paths) supplies the composition of compatible steps.

If established operating conditions already fix the relevant order and settle the result, use that account. Continuous interaction, uncertain observation, delayed messages or hardware memory behavior require the corresponding state and transition conditions when they can change this answer.

### MMP.5:2 - Problem

A description can call each activity a single step even though another participant can intervene during it. Composing those whole activities then omits the very sequences that cause the failure.

The opposite response expands every internal detail. The number of sequences grows, while many added steps cannot affect the requested result.

The modeling problem is to choose a useful grain of action: expose the intervention that matters, preserve what participants remember, and justify any subsequent simplification. The resulting sequence must also be interpreted back into a possible working arrangement.

### MMP.5:3 - Forces

| Force | Tension |
| --- | --- |
| Convenient whole actions and interference | A whole-action description is easy to compose; another participant may act between its read and its update. |
| Shared values and saved readings | The shared value can change while a participant continues using an earlier observation. |
| All permitted orders and calculation cost | One bad order can defeat a universal claim; establishing that no such order exists needs coverage or an argument. |
| Detailed execution and a useful abstraction | Finer steps can expose a failure or add only distinctions irrelevant to the requested output. |
| A corrected model and a changed practice | Altering an ordering rule can repair the calculation; the work must be able to enforce that rule. |

### MMP.5:4 - Solution

**Name the required result → recover shared state and remembered observations → choose steps and their conditions → calculate permitted interleavings → change the relation that causes the failure → return the result and its implementation conditions.**

#### MMP.5:4.1 - Select the question and the state it needs

State the required property. Distinguish a final result after all selected activities complete from a condition that must hold throughout their execution. For example, “both updates are included when both participants finish” and “confirmed appointments never exceed capacity” are different questions.

Choose initial states and a finite scope. Name the participants, the work they may do, and any environmental actions admitted within that scope. A bound of four actions leaves later retries outside the conclusion.

Represent enough state to determine the next permitted step and its effects. Include:

- the shared values each participant can read or change;
- each participant's saved readings or other local values used later;
- its position in the activity, such as before reading, ready to update, or finished;
- any permission or resource condition that enables an action.

A saved reading and the shared value are separate variables whenever one may change without the other. If two situations with the same proposed model state can admit different relevant next steps, add the missing distinction or represent both possibilities.

Also define how model values answer the working question. A count of promises might matter more than the value currently displayed in the booking system.

#### MMP.5:4.2 - Choose the grain of a step

For each action, state when it is enabled, which values it reads, and how it changes the state. Values not mentioned in its update remain unchanged. Make each participant's local order explicit.

One transition is indivisible *in this model*: other transitions occur before or after it. This choice requires an operating interpretation. A calculation performed from a copied number may be local, while obtaining that number and replacing the shared total can be separate interactions.

Use separate steps wherever a permitted intervention changes the requested result. Conversely, several operations can be one step when the operating arrangement excludes relevant intervention, or when a correspondence argument shows that all inserted interventions preserve the property.

In :5.1, replacing two read-and-write activities with two indivisible increments removes a possible result.

An uncertain operating condition can remain a stated model premise. The result then says what follows if that condition holds and identifies what must change for another interpretation.

#### MMP.5:4.3 - Construct and inspect permitted sequences

From each initial state:

1. List the enabled next steps, including the admitted environmental steps.
2. Apply each choice to form a successor state and retain the chosen step with it.
3. Continue from each successor until the selected activities finish, no step is enabled, or the scope bound is reached.
4. Return to the most recent prefix with an untried choice and continue that branch.
5. Finish when every relevant branch has been considered, or return the unexplored choices if calculation stops earlier.

MATH.1 supplies composition of steps whose ending and starting states match. Each resulting path is one permitted interleaving: an order that preserves each participant's local sequence while mixing steps from different participants.

For a property required throughout the work, inspect each reached prefix. For a final-result question, inspect completed states. Keep a state with unfinished work and no enabled step as a blocked case. A path that reaches the chosen step bound without completion has not established termination.

One permitted counterexample settles that the bounded model does not guarantee the property. To establish the property for every permitted case, exhaust the selected possibilities or give an argument covering those not enumerated. Sampling several schedules can find a failure but leaves the remaining schedules open.

An earlier exploration of a reached state can be reused when all future behavior and the checked property depend only on that state. For a bounded search, that exploration must cover at least as many remaining steps as the present path allows. If the question depends on the history, such as whether a promise was withdrawn, retain that history distinction in the state or in the traversal.

#### MMP.5:4.4 - Change the working relation and compare the results

Read a failing path as a sequence of working events. Locate the step where a premise relied on by one participant has changed, an update is lost, or a required condition is crossed.

Change the smallest relevant relation. Depending on the failure, this may mean ordering two activities, protecting a shared read-and-update interval, rechecking a condition when acting, or reserving the resource before promising it. Derive the revised transitions from the proposed arrangement and calculate the same property again.

Keep the difference between the changes visible. Serializing whole activities restricts order. Making one update indivisible changes the permitted intervention points. Retrying introduces additional work and paths. These changes can have different costs and effects on completion even when they restore the same final value.

A model counterexample may instead reveal an implausible transition. Correct the correspondence to the work, preserving interventions that really are possible. Removing a permitted failure merely to obtain the desired answer would answer a different question.

#### MMP.5:4.5 - Simplify only with respect to the required property

Try removing a local step or merging states when the calculation is too large. State which observations the receiving question keeps, then show how the omitted distinctions can be restored or moved without changing the answer.

For example, if a participant computes with a saved local number and nobody else can inspect or modify that number, moving another participant's step across this calculation can leave the shared result unchanged. Section :5.3 works this reduction for the counter. A question about intermediate local values would need a different comparison.

If the search bound counts original operations, preserve that count through the reduction or use only expansions that meet the original bound. A question observing a prefix inside a combined step may require retaining that intermediate state.

Use MATH.2 when a proposed state quotient needs its operation-compatibility test. Use C.29.1 when transferring the result between the mathematical accounts. Preserve the direction of the conclusion: an enlarged set of possible behaviors can support exclusion of a failure when none occurs, but an added behavior may be unrealizable in the work.

#### MMP.5:4.6 - Return to the proposed method

Return the property, the model conditions on which it depends, and the useful result: a counterexample, a bounded guarantee, a blocked case or a partial exploration. Give the recipient the state distinctions and steps needed to understand that result.

Use C.29 to check the correspondence between the calculation and the activity. For a guarantee about the work, the model must cover the relevant working cases; for a claimed possible failure, its counterexample needs a realizable interpretation. A conditional design result can remain useful while that interpretation is being developed.

When the result changes a proposed way of working, use [ME.7](https://github.com/ailev/FPF/blob/main/Engineering%20DPF%20Suite/METHOD-ENGINEERING-PRINCIPLES-FRAMEWORK.md#me7---resolve-a-proposed-method-whole-into-obtaining-relations-or-a-candidate-account) to revise its ordering, overlap or resource conditions. If a description claims protection that the operating arrangement lacks, [ME.12](https://github.com/ailev/FPF/blob/main/Engineering%20DPF%20Suite/METHOD-ENGINEERING-PRINCIPLES-FRAMEWORK.md#me12---verify-method-and-methoddescription-coherence) locates that disagreement and the description or arrangement to correct.

Stop when the result answers the present design question. Model waiting, interruption, failures or repeated work next when those can change the decision; a final-value calculation alone leaves those questions open.

### MMP.5:5 - Archetypal Grounding

#### MMP.5:5.1 - Find a lost update and compare two repairs

Two participants A and B each increase a shared integer x once. Initially x=n. Each first reads x into its own local variable, then writes that saved value plus one.

The state contains x, local a and b, and positions k_A,k_B in {0,1,2}. Position 0 means ready to read, 1 ready to write, and 2 finished. Both positions start at 0. Set a=b=0 initially; each is overwritten before use.

| Step | Enabled when | Update; all other values stay unchanged |
| --- | --- | --- |
| A_read | k_A=0 | a:=x; k_A:=1 |
| A_write | k_A=1 | x:=a+1; k_A:=2 |
| B_read | k_B=0 | b:=x; k_B:=1 |
| B_write | k_B=1 | x:=b+1; k_B:=2 |

The required final property is: if both positions are 2, x=n+2. Exactly six complete orders preserve the read-before-write condition within each participant:

| Order | Final x |
| --- | --- |
| A_read, A_write, B_read, B_write | n+2 |
| A_read, B_read, A_write, B_write | n+1 |
| A_read, B_read, B_write, A_write | n+1 |
| B_read, B_write, A_read, A_write | n+2 |
| B_read, A_read, B_write, A_write | n+1 |
| B_read, A_read, A_write, B_write | n+1 |

In the second order, both participants save n. A writes n+1; B later writes n+1 from its own saved value. Each completed its instruction, but the combined result contains only one increase. This calculation holds for every integer n.

One repair orders whole activities: allow B_read only after k_A=2. The sole complete order gives n+2. A second repair implements each increase as one indivisible transition x:=x+1; its two possible orders both give n+2.

The repairs have different implementation conditions. The first needs the enforced precedence. The second needs a shared update that admits no conflicting intervention within the increase. Replacing the four-step model by the two-step model is justified only for that changed arrangement.

These calculations establish final values of completed work. Whether a participant is eventually scheduled, or can fail before completion, remains a further question.

#### MMP.5:5.2 - Preserve capacity when two people offer the same appointment

There is one remaining appointment and two booking assistants. Assistant i first reads the current number c of confirmations into a local value t_i. Later it promises the appointment if t_i<1 and records its confirmation.

Let q_A,q_B be confirmation flags, initially 0, and c=0. Confirmation by i sets q_i:=1 and c:=c+1 in one step. Each assistant acts once. The claim is q_A+q_B<=1 throughout.

The allowed order read_A, read_B, confirm_A, confirm_B gives both saved values 0. Both confirmations occur, and q_A+q_B=c=2. Here even an indivisible increment of c fails to preserve capacity: the decision used an old count.

Change the confirmation step to inspect the current c. If c<1, atomically set q_i:=1 and c:=c+1; otherwise finish with no confirmation. Starting from c=0, the first successful step makes c=1. Every later step declines. Since c=q_A+q_B is preserved by every update, the capacity claim follows for every order in this model.

The operating method must make reservation and the successful promise correspond. A spoken promise issued before a reservation can still create the failure, even if the later database transaction declines.

A more detailed model separates reservation flags r_i from spoken-promise flags p_i. All start at 0. A successful protected reservation sets r_i:=1 and increases c once; communication sets p_i:=1 only when r_i=1. With no cancellation or reuse in this scope, every transition preserves c=r_A+r_B<=1 and p_i<=r_i. Thus the number of promises p_A+p_B also stays at most one. Interruption after reservation can leave capacity unused; releasing or reusing it needs corresponding additional steps.


#### MMP.5:5.3 - Remove local calculation steps without losing the counter result

Refine each activity in :5.1 into read x, add one to the saved local value, and write that local value to x. There are twenty complete orders of these two three-step activities.

Only the read and write interact with shared x. A's local addition changes a and A's position. B's steps in this example neither inspect nor change those components; they read or change x and B's own state. Moving a step of B across A's addition therefore preserves both effects and their enabling conditions. The corresponding statement holds with A and B exchanged.

Move each local addition next to its participant's write. The resulting six read/write orders are exactly those in :5.1; each can also be expanded by inserting the local addition before its write. Thus the possible final shared values remain {n+1,n+2}.

Each reduced read represents one original operation; each reduced write represents the local addition followed by the write. A complete four-transition reduced schedule therefore contains six original operations. It lies outside a search limited to four original operations and inside one allowing six. Count those original operations when applying the bound.

The local addition can be absorbed for this final-value question. It cannot be discarded from a question asking what value A has computed before B reads, because that question observes the distinction just removed.

### MMP.5:6 - Bias-Annotation

A serial narrative can hide intervention points. Try a path in which both participants obtain their inputs before either changes the shared object.


### MMP.5:7 - Conformance Checklist

- The required final or throughout-execution property and finite scope are stated.
- Saved observations are separate from shared values wherever their divergence affects later action.
- Steps have enabled conditions, updates and unchanged values; the permitted interventions have an operating interpretation.
- A conclusion about all permitted orders follows from complete exploration or a general argument; a bounded or partial search states what it covered.
- A counterexample is connected to the ordering, shared value or model assumption that produces it.
- A changed order or grain of action is recalculated against the same property.
- A simplification preserves the observations used by that property.
- The result distinguishes a model conclusion from its supported or conditional application to the work.

### MMP.5:8 - Common Anti-Patterns and How to Avoid Them

**Use whole activities as indivisible steps by default.** This removes four failing orders in :5.1. Split the read and write when another participant can intervene.

**Protect the update but leave the decision stale.** An indivisible increase still permits two promises in :5.2. Inspect the condition at the protected reservation step.

**Explore successful completions and ignore blocked work.** A model can satisfy its final-value implication because nobody finishes. Retain unfinished states with no enabled continuation and ask about progress when the decision needs it.

**Keep every internal operation.** The twenty schedules in :5.3 add no final-value distinction. Show the commuting reduction before removing the local steps.

### MMP.5:9 - Consequences

The model makes the effects of overlap inspectable. A small failing sequence can identify the condition that the working method must preserve.

The same mathematics applies to people, programs and mixed arrangements when their observations and interventions support the chosen transitions. The implementation of an indivisible reservation or an enforced order differs across those arrangements.

The cost grows with the number of distinguishable states and choices. Property-preserving reduction can make the calculation affordable; a change in the property can require restoring the omitted detail.

### MMP.5:10 - Architectural Rationale

The mathematical object is a transition system; the modeling method constructs its correspondence to interacting work. Its state retains each participant's saved observations when they determine a later update.

The question determines which distinctions must survive. Treating a whole read-and-write activity as one indivisible step hides the failing order. Separating a purely local addition adds orders without changing the possible final shared values. The paired examples show how to choose and justify the detail needed.

MATH supplies path composition and tests for identifying states. This pattern supplies the shared-state formulation, the choice of intervention points and the return from the calculation to a change in the working method. Method Engineering uses that result when designing or checking the proposed arrangement.

### MMP.5:11 - SoTA-Echoing

**How much execution detail changes the answer?** [Lamport's PlusCal tutorial, Session 7](https://lamport.azurewebsites.net/tla/tutorial/session7.html) contrasts indivisible increments with separate reads and writes, then examines a finer local calculation. It shows how to choose which operations are treated as indivisible and when a finer description can be reduced. Sections :4.2, :4.5 and :5.1/:5.3 adapt that contribution to a hand-executable model and its return to the work. The four-step example is the same standard lost-update construction, expressed with an arbitrary initial integer.

**When does manual enumeration need stronger support?** [A High-Level View of TLA+](https://lamport.azurewebsites.net/tla/high-level-view.html) provides state-based specification, finite model checking and proof as related routes. Use an executable specification when the required reachable-state exploration exceeds hand calculation; use a suitable proof when the claimed family exceeds the explored finite scope. A final-state property and eventual progress need their distinct premises and checks.

**Can transactions supply the required working condition?** [PostgreSQL 18, Transaction Isolation](https://www.postgresql.org/docs/18/transaction-iso.html) distinguishes stable transaction snapshots from serializable outcomes. A snapshot can retain an obsolete condition while concurrent transactions change the situation. Serializable execution can reject a conflicting transaction and requires the application to handle retry. This is an implemented alternative to physically serializing whole activities. It changes the model's commit, rejection and repetition behavior; irreversible promises still need to be related to successful commitment.

Choose calculation support and operating protection separately: exploration or proof answers the model question; serialization or transactional isolation supplies an operating condition. Reopen the formulation when a participant can observe a formerly local value, intervene inside a step, act from another snapshot, retry, fail, or change a property that the simplification omitted.

### MMP.5:12 - Relations

- **MATH.1** supplies compatible path composition; **MATH.2** tests whether merging states preserves the selected operations.
- **C.29** connects the mathematical construction with the work; **C.29.1** governs transfer between mathematical accounts, including a justified reduction.
- **C.29.2 and C.29.3** support constructing a computation and relating prepared inputs, execution and readout when a solver is used.
- **ME.7 and ME.12** use the result to revise a proposed method arrangement or repair disagreement between its description and operation.
- **C.11.DUA** helps decide whether a further calculation, observation or trial can improve the decision enough to warrant its burden.

### MMP.5:End
