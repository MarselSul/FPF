# Mathematical Modeling DPF

> Methods for constructing mathematical representations of a question, connecting unknown relations, observations and available actions, and revising the resulting models.

- **Author:** Anatoly Levenchuk, with AI-assisted development and review
- **Version:** 15 September 2026
- **Status:** Eternal alpha: a growing language of general modeling methods.
- **License:** © 2026 Anatoly Levenchuk. Original framework text: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). Cited sources retain their own terms.
- **Publication:** [FPF ecosystem repository](https://github.com/ailev/FPF)

Begin with the question your model must answer. Use the Table of Contents to find a relevant pattern, then open its Problem frame, Solution, worked cases and checklist. Readme gives selected entries; Preface explains the connected methods and their limits.

The code **MMP** names this DPF. Its numbers are stable pattern addresses; § shows position in this edition. References beginning MATH name patterns in [Mathematical Thinking](https://github.com/ailev/FPF/blob/main/Foundational%20Thinking%20DPF%20Suite/MATHEMATICAL-PRACTICE-DPF.md) (September 2026). References such as C.29 name patterns in [FPF](https://github.com/ailev/FPF/blob/main/FPF-Spec.md) (September 2026). ME references name patterns in [Method Engineering](https://github.com/ailev/FPF/blob/main/Engineering%20DPF%20Suite/METHOD-ENGINEERING-PRINCIPLES-FRAMEWORK.md) (11 September 2026). Open the cited publication when that contribution is needed. When using another version, revisit a conclusion if its cited operation or condition has changed.

To cite this edition: Anatoly Levenchuk, *Mathematical Modeling DPF*, 15 September 2026, [FPF ecosystem repository](https://github.com/ailev/FPF).

# Table of Contents

## Public units

| Unit | Title | Use |
| --- | --- | --- |
| Readme | [Mathematical Modeling - Readme](#mathematical-modeling---readme) | Find a first pattern for your question. |
| Preface | [Mathematical Modeling - Preface](#mathematical-modeling---preface) | Understand the connected methods, their rationale, sources and limits. |

## General model-forming methods

| § | ID & Title | Status | Keywords & Search Queries | Dependencies |
| :--- | :--- | :--- | :--- | :--- |
| 1 | [MMP.10 - Construct and Revise a Constraint Formulation](#mmp10---construct-and-revise-a-constraint-formulation) | Usable, evolving | objects; representation; domains; constraints; recovery; multiplicity; optimization. How can the objects and conditions of a working question be expressed so that mathematical answers still refer to the intended possibilities? | B.5.FM for initial formulation; MATH.1/.5 for construction and representation; C.29.1 for transferring results; MMP.11 for unknown relations. |
| 2 | [MMP.11 - Construct a Model Family from Known Relations](#mmp11---construct-a-model-family-from-known-relations) | Usable, evolving | unknown relation; family; grounded structure; parameterization; completeness; identifiability. How can an unknown contribution vary without losing known relations, and which remaining ambiguity changes the requested consequence? | MMP.10 for admissible representation; A.3.3.TR for state; C.16.IR for observation-based inference; C.28.MR for intervention; MMP.9 for reduction. |
| 3 | [MMP.7 - Construct a Probability Model of the Recorded Data](#mmp7---construct-a-probability-model-of-the-recorded-data) | Usable, evolving | observation; recorded data; selection; missing records; censoring; noise; probability law. What distribution does the recording procedure produce from the modeled possibilities? | C.16.IR for interpretation and inference; MMP.11 for unknown relations; MMP.8 when the record informs a choice. |
| 4 | [MMP.8 - Formulate Choices under Incomplete Information](#mmp8---formulate-choices-under-incomplete-information) | Usable, evolving | available information; action; policy; decision timing; objective; conditional requirement; average performance. What can be chosen with information available in time, and which conditions must that choice satisfy? | MMP.7 for reports; A.3.3.TR for change; MMP.10 for constraints; ME for changing the corresponding way of working. |
| 5 | [MMP.9 - Derive a Reduced Evolution Model](#mmp9---derive-a-reduced-evolution-model) | Usable, evolving | reduction; hidden state; closure; memory; approximation; error; sufficient bound. What contribution is left by eliminated detail, and which replacement preserves the consequence needed? | A.3.3.TR for evolution; C.29.1 for preserved structure; MMP.11 for a replacement family; B.5.RR for affected revision. |

# Mathematical Modeling - Readme

## Practical entries

Bring the question you need a model to answer. It may concern an unexplained observation, a proposed intervention, a design, a prediction or the way work is performed. A useful first result can be a relation that makes calculation possible, a conditional answer, a reason to reject a proposal or a more precise question.

These entries are selected examples. Use the Table of Contents and the pattern bodies when your question differs. The bodies explain their mathematical prerequisites and when another subject contribution is needed. FPF supplies common reasoning methods; Mathematical Thinking supplies constructions used in mathematics itself and in its applications. Read their named patterns when an entry calls for those contributions.

You can ask an assisting agent: “Explain the result and give feedback in the language of my work, without framework jargon.”

### MMP-START - Find what must be modeled

- **Situation:** You know relevant facts or formulas but cannot yet turn a working difficulty into a mathematical question.
- **Question:** Which distinctions and relations would let the answer change what you understand or do?
- **First useful result or blocker:** A small account that yields a consequence, or a named relation still needed. For a moving cart, total distance does not determine its final position. Given the starting position, signed displacements can answer that question under a straight-line motion account; a question about visits along the way needs more than the final sum.
- **Start with:** FPF B.5.FM to choose the participants, propose their relations and work a consequence back to the question. B.5.TU helps when a theory supplies an unfamiliar account. C.29.1 connects the mathematical construction with what it represents. When the object and requirements are recognizable but their expression is missing, continue with MMP.10.
- **Stop or return:** Use a sufficient consequence. If a changed question separates cases that the model treats as one, recover that difference before adding computation. Return to the relevant practice for a missing physical law, observation relation or operation.

### MMP-REPRESENT - Express the intended possibilities

- **Situation:** Requirements are understood, but convenient variables omit allowed objects or admit unintended ones.
- **Question:** What must a variable assignment satisfy to describe an admissible candidate and support the requested answer?
- **First useful result or blocker:** Variables, domains, joint conditions and an interpretation. An optional assignment has three possibilities per request: absent, option 0 or option 1. Two unconstrained bits can create duplicate records of that same assignment and distort its count.
- **Start with:** [MMP.10 - Construct and Revise a Constraint Formulation](#mmp10---construct-and-revise-a-constraint-formulation). Describe a candidate object, choose its representation, derive conditions making the representation valid, and express the requirements and requested result.
- **Stop or return:** Obtain and interpret the needed witness, bound, count or other result. If the representation is restricted, carry that restriction into the answer. Revisit derived conditions when a requirement changes.

### MMP-RECORD - Model what the procedure actually records

- **Situation:** Data reflect selection, rounding, missed events or an unrecorded part of the observing procedure.
- **Question:** What probability law describes the available records under the proposed account?
- **First useful result or blocker:** A distribution for the report, with its unresolved quantities retained. A record saying only “below threshold” and a procedure that keeps no records of such events call for different probability calculations.
- **Start with:** [MMP.7 - Construct a Probability Model of the Recorded Data](#mmp7---construct-a-probability-model-of-the-recorded-data). Compose the source and recording laws; sum or integrate alternatives that the record leaves unobserved; condition on selection when the procedure selects cases.
- **Stop or return:** Use the resulting law for the stated inference or prediction. Return to the observing procedure when a required relation is missing or a report conflicts with the modeled possibilities. Statistical estimation has its own additional operations.

### MMP-INFORMATION - Choose using the information available in time

- **Situation:** A proposed answer depends on an unknown value or on a report that may arrive after the action.
- **Question:** Does one fixed choice work, or can a usable instruction choose from the information actually available?
- **First useful result or blocker:** A fixed choice, an observation-dependent instruction, or a circumstance that defeats the requested guarantee. If the best preload differs for two loads, computing the best value for each known load does not supply a preload to set before they can be distinguished.
- **Start with:** [MMP.8 - Formulate Choices under Incomplete Information](#mmp8---formulate-choices-under-incomplete-information). Separate decisions from circumstances, specify observation timing, and formulate the required performance. Derive the permitted actions for each observationally indistinguishable group, or evaluate the stated probabilistic requirement.
- **Stop or return:** Interpret the instruction as a possible way of working. If it needs unavailable information, change the observation, timing, action or requirement. Compare the benefit and cost of that change through C.11.DUA.

### MMP-REDUCE - Derive the contribution lost by simplification

- **Situation:** You retain a few quantities from a larger model, but their change still depends on what was removed.
- **Question:** Can elimination, memory, added state, approximation or a bound supply the consequence the work needs?
- **First useful result or blocker:** A reduced law or sufficient bound, with its initial conditions and use horizon. The change of a mean can depend on a variance; two populations with the same mean can therefore require different predictions.
- **Start with:** [MMP.9 - Derive a Reduced Evolution Model](#mmp9---derive-a-reduced-evolution-model). Derive the retained quantity's change from the source law, identify the unavailable contribution and construct its replacement.
- **Stop or return:** Use the supported prediction or bound. Reopen the affected reduction when inputs, initial conditions, observation times or the required consequence change. A small numerical step cannot repair an omitted modeling contribution.

### MMP-INTERVENE - Calculate what a changed mechanism would do

- **Situation:** An observational model is being used to predict a change in how the situation is produced.
- **Question:** Which mechanism does the proposed intervention replace, and what follows while the other relations remain applicable?
- **First useful result or blocker:** The changed model and its conditional consequence. A command that fixes a variable replaces a relation that formerly determined it; merely observing that variable at the same value retains the former relation.
- **Start with:** FPF C.28 and C.28.MR. Identify the causal question, construct the mechanism replacement and derive the consequence under its conditions. Use A.3.3.TR when a state-change rule must first be assembled from the interacting contributions.
- **Stop or return:** Apply the conditional result or obtain the causal relation it still needs. If the actual intervention changes another mechanism too, revise that contribution. An observation fit alone leaves that causal question unresolved.

### MMP-REPAIR - Revise the answer after a question or premise changes

- **Situation:** A new observation, a corrected premise or a changed question calls an earlier model-based answer into question.
- **Question:** Which relation or operation accounts for the consequential difference?
- **First useful result or blocker:** A localized discrepancy and a usable repair or remaining alternative. Two agreeing programs can preserve the same wrong modeling premise; changing their numerical settings would leave that premise intact.
- **Start with:** FPF B.5.RR to locate where the reasoning uses the changed premise or needs a new contribution, retain sufficient alternatives and derive the revised consequence. Use B.5.RA if the argument must first be recovered. When the failure concerns the connection between physical, mathematical and computational accounts, B.5.MPC.R supplies the comparison and repair of that connection.
- **Stop or return:** Use the repaired answer or a sufficient conditional conclusion. Use C.11.DUA when deciding whether distinguishing the remaining explanations is worth its cost.

### MMP-OBSERVATION-TO-ACTION - Turn an observing model into a workable instruction

- **Situation:** A proposed way of working includes an observation followed by a decision, but their combined benefit is unclear.
- **Question:** What instruction can use that report, and which change to the work is worth making?
- **First useful result or blocker:** An instruction with its required information, timing and supported performance, or a missing contribution that prevents its use.
- **Start with:** MMP.8 to formulate the information-dependent choice. If that question needs a reporting probability law that has not been derived, obtain it through MMP.7. When the observing and acting methods must change, use ME.7 in [Method Engineering (ME)](https://github.com/ailev/FPF/blob/main/Engineering%20DPF%20Suite/METHOD-ENGINEERING-PRINCIPLES-FRAMEWORK.md). Describe the proposed whole, identify the participating methods, and examine the relations needed for one method to produce the report the other can use. Keep unresolved conditions in the resulting proposal.
- **Stop or return:** Use a sufficient instruction. Return to the observation model after the recording procedure changes, and to the decision question after its timing, allowed choices or performance requirement changes.

#### Example - A noisy report and a changed success requirement

Start with what successful work means. In MMP.8:5.2, one of two requests needs a scarce resource, and allocation must follow a report. With perfect timely information, an instruction can follow the report. Without a distinguishing report, each fixed allocation fails in one admitted circumstance.

For the noisy procedure, MMP.7 supplies a necessary intermediate result. Two channels may produce the report, but the record does not identify the channel. Sum over that unrecorded choice to obtain the reporting law for each actual circumstance. MMP.8:5.2 performs this calculation: following the report succeeds with probabilities 0.8 and 0.7 in the two circumstances. No prior probability for which circumstance is actual is needed for those conditional results.

Now construct what can be done with that report. MMP.8 compares the four deterministic instructions on a two-valued report. A requirement of at least 0.65 success in each circumstance admits following it. A zero-failure requirement does not. Changing the requirement to average success, with one circumstance occurring with probability 0.95, makes always allocating to that request preferable among the four instructions. The preferred instruction changed because the question changed; the observing procedure stayed the same.

Return this answer to the proposed work. The report must be produced before allocation, and the receiving participant must be able to follow the instruction. If obtaining a better report costs more than the improvement is worth, C.11.DUA can support a sufficient existing choice or acceptance of the remaining risk. If the observation itself changes the situation, first represent that intervention through C.28.MR and derive the reporting and outcome laws for the changed situation.

ME.7:4.1 helps examine the proposed composition: what each method contributes, how the report reaches the acting participant, and which timing and support conditions the whole needs. Its result can be a supported composition or a proposal with unresolved conditions. Retain the resource demands and timing when revising the mathematical question. The useful result is a change the work can perform, a supported explanation of why the present method suffices, or the specific contribution still needed to choose.

### MMP-SUFFICIENT-ANSWER - Answer the working question before reconstructing every detail

- **Situation:** A model omits internal distinctions, and reconstructing them may cost more than the requested answer needs.
- **Question:** Which consequences are shared by the remaining possibilities, and do they already decide the question?
- **First useful result or blocker:** A justified bound that settles a stated threshold, or the distinction whose unresolved value still changes the answer.
- **Start with:** [MMP.9](#mmp9---derive-a-reduced-evolution-model) for lost evolution information; [MATH.20](https://github.com/ailev/FPF/blob/main/Foundational%20Thinking%20DPF%20Suite/MATHEMATICAL-PRACTICE-DPF.md#math20---bound-an-unknown-by-comparable-constructions) for bounds; FPF C.29.1 for subject interpretation and C.11.DUA when further inquiry is a live choice.
- **Stop or return:** Use a settled answer under the supplied premises. A changed threshold, observation, law or time horizon returns to the affected comparison; unresolved detail matters through its effect on the intended use.

#### Worked connection for MMP-SUFFICIENT-ANSWER

**Connection to keep in view:** State the consequence needed → test what the smaller description retains → bound the unresolved alternatives → interpret the bound → use a settled answer or recover the distinction that matters.

**1. Make the receiving question specific.** A supplied account has two nonnegative populations with laws x'=-x and y'=-2y, where time uses the unit in which these rates are stated. The initial total is 1, but its split is unknown. Is the total remaining at time 3 below 0.1? This case starts with those laws; establishing a physical or other subject law is a different contribution.

**2. Recover the omitted contribution.** With z=x+y, MMP.9 gives z'=-x-2y. The same z=1 can have derivative -1 or -2, so the current total alone does not determine its rate of change. This result identifies the missing distinction and supplies alternatives for a bounding calculation.

**3. Derive an answer shared by those alternatives.** Put x(0)=a and y(0)=1-a, with 0≤a≤1. The equations give `z(t)=a*exp(-t)+(1-a)*exp(-2t)`. MATH.20 uses this convex combination to derive exp(-2t)≤z(t)≤exp(-t) for t≥0. At time 3, exp(-3)<0.05<0.1. The upper bound settles the question for every initial split. No estimate of a is needed for this answer.

**4. Return the consequence to the work.** C.29.1 asks what the populations, rates, total and threshold represent and which assumptions permit the interpretation. Under the supplied account, the condition is satisfied at time 3. Using that consequence in a real decision also uses the subject premises that made these equations applicable.

**5. Reopen what changes the answer.** Suppose the next question is whether z(1)<0.2. The bounds straddle 0.2. The same formula reduces the decision to a<(0.2-exp(-2))/(exp(-1)-exp(-2)), approximately 0.278. An available bound on a may settle this. Obtaining more about a is useful when it can change the decision enough to justify its cost; C.11.DUA helps make that choice. Changed evolution laws instead return to step 2, since the old enclosure may fail.

A different population or physical decay process can use this example when it supplies the stated laws and interpretation. The reusable connection is broader: reduction exposes a lost distinction, a mathematical comparison bounds its effects, and the receiving question decides whether those effects need further work.

# Mathematical Modeling - Preface

## MMP.Preface:1 - Problem frame - Make a mathematical question useful

You may know the relevant formulas and still be unable to build a model for the question in front of you. The candidate objects may be unclear. A recorded value may hide part of the observing procedure. A proposed decision may use information that arrives too late. A detailed model may become affordable only after removing something its answer depends on.

Mathematical Modeling develops methods for constructing and revising such mathematical questions. Its subject can be a physical situation, a working method, a computational process or another mathematical construction. The useful result may be a prediction, an explanation, an admissible arrangement, an instruction, a bound or a question that directs further inquiry. Start with what that result would let you understand or do.

This edition contains five patterns. Together with Mathematical Thinking, it supplies the currently published members of the Foundational Thinking DPF Suite. The selected repertoire will expand these modeling methods and add Physical Thinking, Computational Thinking and Notational Engineering. The Table of Contents identifies the methods available here; obtaining a contribution outside them still needs another source or collaborator.

The mathematical account and the subject supply different parts of the reasoning. A relation describing a material, an observing procedure or a permitted action needs its corresponding subject knowledge. A mathematical construction then helps express the relation and derive consequences. The answer returns to the original question with the conditions under which that interpretation holds. The [First Principles Framework (FPF)](https://github.com/ailev/FPF/blob/main/FPF-Spec.md) develops this connection in B.5.FM and the C.29 family; the bodies here develop particular model-forming operations within it. Find a named FPF pattern by its full code in FPF-Spec.md and open its Problem frame and Solution. If GitHub cannot display the large file, use its View raw or Download raw file action, then search that copy.

The needed preparation depends on the operation. Finite arrangements can use sets, functions and elementary counting. Probabilistic recording needs conditional probability and sums or integrals. Evolution and reduction can require differential equations. Each body states its prerequisites and works small cases. When a collaborator or assisting agent supplies the mathematics, ask for the meaning of its inputs, its conditions and the result the next part of your work can use. You can ask for that explanation in the language of your work.

Begin with the [Readme](#mathematical-modeling---readme) when the useful entry is unclear. Enter a body directly when its Problem frame matches the difficulty.

## MMP.Preface:2 - Problem and forces - Choose what the model must retain

A model can answer a mathematically well-formed question that differs from the one the work needs. This often happens before calculation: a convenient variable excludes an allowed arrangement, a mean hides a distinction needed for action, or a fitted relation describes observation while the question concerns an intervention.

Several choices therefore shape the construction:

| Working tension | Consequential choice |
| --- | --- |
| A familiar representation and the intended objects | Which distinctions must variables, domains and conditions preserve? |
| Supported structure and an unknown relation | What may vary, and what must remain true throughout that variation? |
| An event and its recorded description | Which unobserved, selected or combined alternatives can produce this record? |
| Knowing a circumstance and choosing before it is known | Which information may the instruction actually use? |
| A detailed account and an affordable answer | Which eliminated contribution needs reconstruction, approximation or a bound? |
| Resolving every unknown and settling the present question | Which remaining differences can change the required consequence? |
| Agreement in one use and a changed use | Which premise, mechanism or interpretation must be reconsidered? |

The requested answer determines how far to develop the model. A bound can settle a threshold question while leaving parameters unresolved. A proposal for a new working method can instead require distinctions that an earlier prediction ignored. C.11.DUA helps decide whether another calculation, observation or refinement is worth its possible contribution.

## MMP.Preface:3 - Solution - Connect the contributions the question needs

### MMP.Preface:3.1 - Form the first account and recover its interpretation

If there is no mathematical question yet, use B.5.FM: identify the participants, propose the relations relevant to the difficulty, work a small consequence and return it to the question. B.5.TU helps when an available theory supplies those relations. Mathematical Thinking provides constructions of objects, operations, representations and arguments when the needed mathematics itself must be developed.

Recover what a request to use a model means in this situation. A structure satisfying stated axioms answers a different question from a representation used to predict an observed process. Both can be useful mathematical work. E.10 clarifies the intended use when the word *model* conceals it; keep the subject's established vocabulary when it is already clear.

A drawing, formula, program or learned representation also needs an operation that obtains the requested answer. A person may reason from a diagram; software may solve equations; an experimental arrangement may exhibit a behavior. Make the required interpretation available when another participant must continue the work. A.6.3.RT.OE helps make an expression usable for that operation, and C.29.2 develops a computational formulation when computation is needed. The obtaining procedure can itself become a subject of mathematical investigation.

### MMP.Preface:3.2 - Represent admissible objects and construct missing relations

[MMP.10](#mmp10---construct-and-revise-a-constraint-formulation) starts from intended candidate objects and their requirements. It chooses a representation, derives the conditions that make the representation valid and expresses the required answer. These steps matter for sets, sequences, functions and quantitative objects alike. If several records describe one object, a count or probability over records can require correction before it answers the subject question.

[MMP.11](#mmp11---construct-a-model-family-from-known-relations) starts with supported relations and an unknown contribution among them. It constructs adjustable families that retain the needed properties and inserts that contribution into the connected model. A known total, a monotone response and a normalized probability law require different mathematical constructions. Their common modeling question is how to permit the unknown variation while retaining what is supported.

Choose the form from the next operation. Direct constraints may already describe all useful candidates. A parameterization can make changes preserve the constraints automatically, but may introduce duplicate descriptions or omit parts of the allowed family. Retain that difference when interpreting a fitted value, an impossibility result or an observed agreement.

### MMP.Preface:3.3 - Construct change and observation together when they interact

For an evolving situation, A.3.3.TR constructs a state-change rule from the contributing relations, including simultaneous constraints, alternatives and events. If situations assigned the same state need different continuations under the same modeled inputs, revise the state or retain the alternatives. The computation's chosen solution order need not be the represented order of physical change.

[MMP.7](#mmp7---construct-a-probability-model-of-the-recorded-data) derives a probability law for the record produced by an observing procedure. Compose the source and recording laws, retain shared unknowns, sum or integrate unrecorded alternatives, and account for selection. The resulting law can supply a statistical inference or prediction method. C.16.IR addresses what a supplied observation relation resolves, including bounds and consequential ambiguity; an estimation method supplies its further inferential operations.

Observation can also change the situation. C.28 and C.28.MR help formulate that intervention and replace the affected mechanism. Derive the reporting or outcome law for the changed model. A relation fitted to the former observation process remains useful only for the consequences its assumptions support.

### MMP.Preface:3.4 - Turn uncertainty into a question about available action

[MMP.8](#mmp8---formulate-choices-under-incomplete-information) separates circumstances from choices and specifies when information arrives. It then formulates whether the work needs a fixed decision or an instruction depending on an available report, and whether performance is required for each admitted circumstance or on average under a stated probability law.

This formulation can expose a change needed in the work itself: observe earlier, distinguish another circumstance, permit another action or revise the requirement. [Method Engineering (ME)](https://github.com/ailev/FPF/blob/main/Engineering%20DPF%20Suite/METHOD-ENGINEERING-PRINCIPLES-FRAMEWORK.md) develops the observing and acting methods and their composition. Their timing and resource demands return as premises of the mathematical question.

An information-dependent instruction needs both an obtainable report and a participant able to act on it at the stated time. Check this condition for the combined method. A correct reporting law and a correct decision calculation can still describe an instruction that the proposed work cannot perform.

### MMP.Preface:3.5 - Simplify, diagnose and revise for the required consequence

[MMP.9](#mmp9---derive-a-reduced-evolution-model) starts with a source evolution law and quantities to retain. It derives their change, identifies the contribution that depends on removed detail and constructs a replacement through elimination, memory, added state, approximation or a sufficient bound. Initial conditions, inputs and the requested horizon determine whether the replacement serves the question. MMP.11 can supply a family for a still-unknown replacement relation.

When a premise or question changes, B.5.RR identifies the reasoning that depends on it and derives the revised consequence. If the argument must first be recovered, use B.5.RA. B.5.MPC.R develops the comparison when the difficulty concerns a connection among physical, mathematical and computational accounts. The repair may belong to subject assumptions, observation, mathematical formulation or computation.

These contributions admit several entry points and returns. A changed reporting procedure can require a new probability law while leaving the choice criterion intact. A changed criterion can require another instruction while leaving the reporting law intact. A changed intervention can require revising the model's mechanisms. Preserve each still-useful result and reconsider the part whose conditions changed.

### MMP.Preface:3.6 - Use the model-forming result across the Suite

The [Foundational Thinking Suite Reference](https://github.com/ailev/FPF/blob/main/Foundational%20Thinking%20DPF%20Suite/FOUNDATIONAL-THINKING-DPF-SUITE-REFERENCE.md) explains the shared architecture and worked combinations. Mathematical Thinking constructs the objects and arguments a formulation needs. Physical or other subject methods supply the supported relations. Computational methods obtain the consequence, and the subject interpretation determines what that consequence lets the work do. Notational methods make these operations recoverable by their participants.

A particularly useful boundary concerns an unknown relation. MMP.11 can construct a family respecting supported conditions without selecting one fitted member. MMP.7 supplies a probabilistic recording law when that is the question, while C.16.IR can expose what a supplied indication or bound resolves. The appropriate next step can therefore be inference, a discriminating observation, an already sufficient bound, or action under the remaining uncertainty.

The selected expansion adds eight bodies to the five available here: inverse formulation, inference, model criticism, causal identification, discriminating inquiry, surrogate construction, coupling models, and constructing decision-sufficient state for continuing choice. The last extends MMP.8's existing histories and continuing instructions; the histories themselves do not automatically provide a smaller sufficient state. General portfolio comparison and improvement remain with the existing FPF methods.

These are planned additions. Use another source or collaborator for a needed inference method or subject premise that the present bodies do not supply.

## MMP.Preface:4 - Archetypal Grounding - A report, an instruction and a changed question

The Readme's [observation-to-action entry](#mmp-observation-to-action---turn-an-observing-model-into-a-workable-instruction) works the connection between MMP.7, MMP.8 and Method Engineering. One of two requests needs a scarce resource. Allocation follows a report produced through an unrecorded choice of channel.

MMP.7's operation first sums over the channel to obtain the reporting law. In the worked case, following the report succeeds with conditional probabilities 0.8 and 0.7 in the two circumstances. MMP.8 then asks what performance the instruction must supply. At least 0.65 success in each circumstance permits following the report. Zero failure does not. An average-success criterion with one circumstance occurring with probability 0.95 instead favours a fixed allocation among the four deterministic instructions considered.

The calculation changes the proposed way of working: whether to obtain and follow the report depends on the requirement, the circumstances it distinguishes and its cost. The receiving participant must get it before allocation. The complete elementary comparison is in [MMP.8:5.2 - Decide which participant gets a scarce resource](#mmp852---decide-which-participant-gets-a-scarce-resource). The Readme explains the return to the work when observation itself changes the situation. Each changed condition selects the contribution to revise.

### MMP.Preface:4.1 - A total is sufficient until the question changes

Suppose material passes through two cycles in two intermediate buffers. Each incoming portion retains 80% of its amount. Its fractions going to each buffer are unknown but constant across the cycles and independent of the portion's amount. Initially the amounts are `(10, 0)`. Both buffers have sufficient capacity; the material remains there until a receiver is selected and the later transfer begins. Transfer losses are neglected. How much capacity does that receiver need for all the material?

MMP.10 represents one cycle by `x_next = A*x`, where the two components of x are the amounts in the buffers. Nonnegative entries of A express the fractions received; each column sums to 0.8. MMP.11 retains the family defined by those conditions. Direct constraints suffice: choosing one fitted matrix would add information the situation has not supplied.

MMP.9 derives a simpler relation for the total `S = x_1 + x_2`: `S_next = 0.8*S`. After two cycles the total is 6.4, so capacity 7 suffices. The unknown distribution does not need to be resolved for this answer.

Now transfer only from the first buffer. One admissible model, `A = 0.8*I`, leaves 6.4 there. Another, `A = 0.8*[[0,0],[1,1]]`, leaves none there. Both give the same total. Capacity 7 still suffices, but the total alone cannot justify using a cheaper receiver of capacity 4. Return to the retained model family to ask which differences can affect the local amount. A further observation is useful if resolving those differences can change the receiver choice enough to justify its cost; C.16.IR and C.11.DUA support that question. The revised use changes what the model must preserve while leaving the total calculation valid for its original question.

Other bodies show different mathematical work: representing partial functions without distorting the requested count, deriving a bound after removing population detail, and constructing an unknown response while preserving its shape. Use their worked cases to learn the corresponding operations and their limits. The choice among those operations follows the difficulty, not the example's subject.

## MMP.Preface:5 - Conformance Checklist - Can the result do its intended work?

For the combination being used, ask:

- What question does the result answer, and how will that answer be interpreted or used?
- What do the chosen mathematical objects represent? Which cases, operations and distinctions are retained or excluded?
- Which relations come from the subject, which follow mathematically, and which remain hypotheses or adjustable contributions?
- What operation obtains the answer, and what information or capability does its performer need?
- Do the connected contributions agree on the situation, timing, admissible variation and required consequence?
- Does a restriction, ambiguity or approximation still permit the proposed use? If the question changes, which part must be reconsidered?

A small use may already have these answers in one body and its worked argument. Carry that answer forward. Seek an additional check or observation when its result can change the decision enough to justify the cost, using C.11.DUA.

## MMP.Preface:6 - Common Anti-Patterns and How to Avoid Them

The methods address consequential failures visible in their constructions. An encoding with ignored fields can give several records for one object; MMP.10 shows how that affects counting and interpretation. A probability law for the source event can omit the procedure that selected the available records; MMP.7 reconstructs that procedure's contribution. A decision rule can accidentally depend on information unavailable at the time of action; MMP.8 constructs the allowed dependence.

Two further failures concern changing a model. Removing variables can leave a missing contribution in the retained evolution; MMP.9 derives that contribution before choosing its replacement. A flexible fitted function can violate a property known about the modeled relation; MMP.11 constructs the variation within that property and exposes any additional restriction.

Their repairs are specific. More numerical accuracy will not recover an excluded candidate object or an omitted relation. A different equation solver can help when the obtaining operation is the actual difficulty. Locate the consequential discrepancy before deciding what to change.

## MMP.Preface:7 - Consequences, biases and limits

The language makes intermediate modeling results available for subsequent work: an admissible representation, a reporting law, a feasible instruction, a reduced evolution law or a family retaining known relations. Their explicit conditions help collaborators divide the work and change one contribution while retaining others.

Construction costs time and mathematical effort. A familiar adequate model or direct calculation can be sufficient. A reusable model family or derivation becomes valuable when the work needs several cases, revisions or explanations. A remaining ambiguity can also be useful if it tells the team which proposed consequence is unresolved.

The worked cases favour small constructions whose reasoning is inspectable. Larger instances can require specialist mathematics, computational resources and subject knowledge. A proof of existence, a practical obtaining procedure and a reliable implementation have different requirements. Statistical estimation, causal identification from observational evidence and specialist physical laws have substantial methods beyond the constructions developed here.

Prediction, explanation and intervention can also favour different accounts. Use C.2.8 and Explanation Design (EXD) when the recipient's recoverable understanding is at issue. A predictive success supplies the performance it demonstrates; explaining a phenomenon or changing a mechanism requires the corresponding content. Several models can contribute to the same project, with comparison and improvement supplied by the existing FPF methods.

## MMP.Preface:8 - Architectural Rationale - Organize by model-forming operations

The organization follows difficulties that arise before and during the construction of a mathematical question. An arrangement, a recorded observation and a changing quantity can require different operations. A solver catalogue begins after many of these choices; a universal modeling cycle usually leaves their detailed construction to the reader. Addressable methods preserve that detail while allowing different combinations.

MMP.10 constructs an expression of admissible cases. MMP.11 constructs a varying relation inside supported structure. MMP.7 derives the law of a recording procedure. MMP.8 formulates choice with information and uncertainty. MMP.9 derives what must replace removed detail in an evolution law. These results can supply one another without requiring every project to use every method.

Common reasoning remains in FPF: constructing a first account, applying a theory, connecting a mathematical result to its subject, describing change, replacing a mechanism and revising an argument. Mathematical Thinking develops the mathematical constructions. MMP develops the model-forming operation that uses those contributions; it keeps the actual subject premises visible. This division allows mathematical, physical and computational thinking to support one another while retaining their different questions.

The same division applies to modeling a working method. A function, path or state rule can describe an aspect of that method. Its mathematical properties become useful only through the correspondence with the work: what counts as input, which operations are available, what state can change and what result is returned. Method Engineering uses the consequence to retain, compose or change the working methods. A mathematical transformation may preserve returned values while changing time, information or execution demands; include the demands relevant to the proposed use.

A more detailed construction can need its own pattern and further refinements. A profile can combine several methods with additional conditions for a narrower practice, and one method can participate in several profiles. Specialization, composition and reuse describe different relations.

Reconsider a boundary when a recurring difficulty requires an unavailable operation, when two bodies develop the same operation, or when their combination leaves a needed contribution implicit. Preserve still-useful arguments, examples and source qualifications while changing the organization.

## MMP.Preface:9 - Source use and currentness

[Nguyen and Frigg's Scientific Representation](https://www.cambridge.org/core/elements/scientific-representation/A5C2A74998C15C36D4B204E4B3E70B1C), especially its comparison of inference and representation, helps separate deriving a consequence within a model from using it about a subject. This is a useful philosophical account of representation; the language's practical operations do not require adopting it as the only account of models.

The historical [SIMULA account by Nygaard and Dahl](https://www.cs.tufts.edu/comp/150FP/archive/kristen-nygaard/hopl-simula.pdf), printed pages 457-458, connects system description with simulation programming and reasoning from a description. [Modelica's equations and initialization](https://specification.modelica.org/maint/3.7/equations.html) provide a maintained example in which simultaneous relations and their computational treatment are distinct. These contributions support recovering the interpretation and obtaining operation rather than imposing one representation medium or execution order.

The individual bodies keep the operative sources for their mathematical construction. MMP.10 compares direct constraints with representation and refinement work in MiniZinc and Conjure. MMP.7 uses statistical workflow and observation/selection constructions. MMP.8 compares fixed and information-dependent choices. MMP.9 uses closure and reduction research. MMP.11 compares constrained construction with data-driven discovery and hybrid known/unknown relations. Each source contributes at its stated scope; the resulting organization and elementary cross-practice examples are conceptual synthesis.

Source changes matter when they alter an operation, its assumptions, its practical cost or the conclusion it supports. Return to the affected body's comparison in that case. A new implementation can change how cheaply a result is obtained while leaving the mathematical relation intact; a newly recognized observation or intervention effect can instead require a different model.

## MMP.Preface:10 - Relations to continued inquiry and work

B.5.QD helps turn a result, obstruction or unresolved difference into a further question. A model can therefore contribute before it supplies a final numerical answer: it may expose a new distinction, make a comparison possible or suggest a different way of working. Choose further inquiry in relation to the work it could enable.

When the difficulty is acquiring or transferring the ability to use such constructions, Human Capability Development (HCD), Explanation Design (EXD) and the relevant development methods address that learning and use. Their question differs from whether one displayed calculation is correct. Retain the preparation and support a participant needs when dividing work among people and AI agents.

For evaluating alternatives and improving them, reuse FPF's characteristic, comparison and development methods. Define the consequences that matter for the question, including approximation, explanatory use, effort and ability to revise the model when relevant. Different models may supply different contributions. The next modeling operation follows the deficiency or opportunity that comparison identifies.

# General model-forming methods

## MMP.10 - Construct and Revise a Constraint Formulation

> **Type:** Method pattern
> **Status:** Usable, evolving
> **Normativity:** Normative within the stated use

### MMP.10:1 - Problem frame

Use this pattern when you know conditions that a possible object or situation must satisfy, but still need to express its possibilities mathematically. You may be looking for an arrangement, a quantity, a shape or a rule of action. Choosing variables already makes decisions: a number can express an amount, but an ordered list, a set of members and an unknown function permit different operations and different possible answers.

Start by describing one candidate object and what would make it admissible. Choose a way to represent it, then distinguish two kinds of condition: those needed for the representation to denote such an object, and those expressing the requirements on that object. This produces a mathematical problem that can be reasoned about or handed to an appropriate computational method.

The result consists of variables with their domains, joint conditions, the requested operation on their solutions and a way to interpret the answer. It can be enough to find one feasible case; another question may require all possible values, a preferred case or a count. The chosen representation must support that particular result.

You need to understand the objects and requirements in the original question, elementary logical conditions and the mathematics used to express them. A mathematical collaborator can construct the expressions while you resolve their intended meaning. When a suitable formulation already exists, use it. When the missing contribution is a physical relation, an observation law or a rule of change, obtain that relation through the relevant method before translating it. B.5.FM supplies the broader first-model construction; MMP.7 and MMP.9 develop observation and reduced-evolution constructions.

### MMP.10:2 - Problem

A convenient variable can leave out the possibility that matters. A single interval cannot represent an activity that may pause. A membership bit cannot record repeated membership. Coefficients of a straight line cannot describe every continuous curve. These restrictions may be useful, but they change which cases the formulation can answer for.

Representation can also add possibilities. A table intended to describe a function can allow two values for one argument unless its conditions exclude that case. Extra fields can create several records of the same object. A calculation over those records can then answer a different counting or probability question.

The difficulty is to construct the mathematical expression of the intended possibilities, including their joint restrictions and the requested result. Solving the resulting equations addresses the problem only after that construction has been made.

### MMP.10:3 - Forces

| Force | Consequence for the construction |
| --- | --- |
| Faithful possibilities and useful operations | A familiar representation may make calculation easy while excluding an intended case or hiding a useful relation. |
| Structured objects and scalar tools | A function, set or sequence may need several scalar variables and additional conditions to represent its structure. |
| Shared restrictions and local descriptions | Separate bounds on individual variables can lose a condition on their combination. |
| Simple answer and rich solution set | A single witness needs less from the representation than counting, sampling or claiming that no witness exists. |
| Reuse and changed requirements | A derived constraint that helped an earlier formulation may exclude valid cases after the requirement changes. |

### MMP.10:4 - Solution

**Describe the possible object → choose its representation → derive the representation conditions → express the requirements and question → obtain and interpret a result → revise the affected construction.**

#### MMP.10:4.1 - Recover what varies and what the question asks

Describe a candidate before choosing scalar variables. Is it an amount, a collection, a sequence, an assignment, a function or another mathematical object? Which distinctions can change the answer? A set retains membership; a multiset also retains multiplicity; a sequence retains positions. Choose among them from the question.

Separate supplied quantities from unknowns. Among unknowns, distinguish what is to be inferred, what can be chosen and what can vary independently of that choice. If a choice uses an observation, specify when the observation becomes available; MMP.8 constructs the resulting information-dependent requirement. An unknown value does not become a freely selectable design variable merely by appearing in the same equation.

State the requested result. Existence asks whether at least one admissible object can be constructed. Inference asks what a quantity can be across admissible objects. Selection adds a preference among them. Counting and sampling depend on how individual objects are distinguished. Keep those requests separate while choosing the representation.

#### MMP.10:4.2 - Construct variables that represent the object

Choose an expression from which a candidate can be recovered. Give each variable a domain and any unit or reference point needed by its operations. A machine label ranges over names; arithmetic on the label requires a separate meaning. A count ranges over nonnegative integers; an amount may be divisible. State a finite bound when the task supplies one. Adding a bound solely to finish a search restricts the question to that bound.

For a structured object, compare representations by the operations you need. A function on a finite set can use one output variable for each input. Alternatively, a table of Boolean indicators can say which input-output pairs belong to its graph. The first expression makes function evaluation easy to state. The second makes some relations among pairs visible, but needs conditions to make the table a function. For a partial function, represent undefinedness as well as defined values.

Keep a shared quantity shared. If several equations use the same unknown offset, one offset variable must occur in all of them. Introducing a separate offset in each equation creates additional possibilities. Conversely, equating genuinely separate values can remove possibilities.

For a function or shape over an infinite domain, choosing finitely many coefficients also chooses a family. Identify that family and whether it expresses the intended possibilities or is a deliberate restriction. For example, the conditions on a continuous function may allow curved solutions even when no affine function satisfies them. A useful restricted family can be sufficient for finding a witness; failure inside it leaves the larger family unresolved.

#### MMP.10:4.3 - Derive structural conditions and translate requirements

Ask what must hold for a variable assignment to describe one candidate of the intended kind. With Boolean entries `r_ij` describing the graph of a total function, require `sum_j r_ij = 1` for every input i. For a partial function, replace this with `sum_j r_ij <= 1`; an all-zero row then means undefined at that input. For an injective function, additional conditions on columns express the extra requirement.

These conditions have different reasons. One value per input comes from choosing a total function. Injectivity comes from the particular problem, if it requires injectivity. Keep their reasons recoverable so that a later change from total to partial or from injective to unrestricted has a local repair.

Express the original requirements using the represented objects. Conjoin conditions that must hold for the same assignment. Use disjunction for allowed alternatives and implication when choosing an option imposes a condition. An implication alone supplies no timing; use time quantities or an explicit sequence when order matters. Preserve a coupled condition such as `x+y=1` rather than replacing it by separate bounds on x and y.

When a bijection between representations is established, MATH.7 supplies transport of operations, relations and compound expressions. For a representation with several records per object, C.29.1 supplies the more general correspondence. Use the decoding of a record to express the requirement on its object. If a condition is rewritten to fit the receiving notation, derive that expression from the original relation and the structural conditions. This is where a missing index, an undefined value or a lost alternative can change the formulation.

Additional constraints can expose consequences and help the obtaining method. Derive them from the retained requirements, and preserve that dependence. Fewer variables or more constraints do not alone establish a faster method; compare the actual resulting work when efficiency matters.

#### MMP.10:4.4 - Make the answer correspond to the question

Define how to recover the requested object or quantity from a satisfying assignment. Then work in both directions: represent an intended admissible case, and interpret an allowed assignment. Use the construction and its conditions to establish the reach of this correspondence. A small case can expose a mistake; a claim about every case needs the corresponding argument.

Match that reach to the requested result:

- To use a witness, its recovered object must satisfy the original requirements.
- To conclude that no intended object exists from inconsistency of the formulation, every intended object must have a representation in it.
- To infer all possible values, translate the quantity as well as the admissible cases; C.16.IR supplies the projection question.
- To optimize, translate the objective and preference as well as feasibility. Distinguish a bound from a value attained by an object.
- To count or sample objects, account for multiple representations of the same object. One representation per object is one solution; weighting or grouping representations can be another.

Auxiliary variables can change what a returned number means. Suppose a finite nonempty set of finish times `f_i` is determined by the other variables. Introduce a real auxiliary T used only in `T >= f_i` and the objective of minimizing T. Lowering T to `max_i f_i` then preserves feasibility, so at an attained optimum T equals the latest finish. If T must instead be an integer and the latest finish is 1/2, its minimum is 1. A merely feasible intermediate T can also exceed the latest finish. Recover the actual latest finish as `max_i f_i`; infer equality with T only when its domain and other conditions permit that lowering.

Choose an obtaining method for the constructed question. Manual substitution may suffice; another problem needs a numerical method, symbolic derivation or search. C.29.2 separates the required mathematical result from the procedure and its execution. Use that method's actual conclusion: finding no case within a time budget differs from establishing inconsistency. Preserve any restriction or approximation when returning the result to the original question through C.29.1.

#### MMP.10:4.5 - Revise the formulation from the changed requirement

Locate the changed participant, domain, relation or requested result. Changing a supplied amount can retain the same representation. Allowing interruptions changes what an activity description must express. Changing a total function to a partial one changes structural conditions. Changing existence to counting can make duplicate records material.

Revisit constraints derived from the old requirement as well as the original formula. Reconstruct the affected expressions and answer interpretation, retaining the unaffected ones. If a solving tool cannot support the needed object, construct a suitable representation or choose another obtaining method; keep any deliberate restriction visible in the returned conclusion.

Stop with a usable formulation and interpretation, an adequate answer, or a named missing relation or operation. Choose further derivation, observation or computation according to what it can change in the work and its cost; C.11.DUA supplies that decision. When the formulated object is itself a working method, return its proposed change to ME for interpretation and use. The mathematical model supplies a reason for the change; the working method still has to be performed under its stated conditions.

### MMP.10:5 - Archetypal Grounding

#### MMP.10:5.1 - Construct an unknown rule from requirements on its repetitions

A device has three labeled modes A, B and C. The required rule changes the mode on every use and returns to the starting mode after three uses. The question is to construct a deterministic rule, with no additional internal state. The rule itself is the unknown object.

Let `S={A,B,C}`. Choose one output variable `p_i in S` for each input i. The requirements become `p_i != i` and `p_(p_(p_i)) = i` for every i. Function composition gives the meaning of the repeated application. MATH.1 constructs composable paths; MATH.5 extends an interpretation of their elementary steps to the compounds.

To express the rule by selected pairs instead, choose `r_ij in {0,1}`. Add `sum_j r_ij=1` for each row, `r_ii=0`, and, for all i,j,k, `(r_ij=1 AND r_jk=1) implies r_ki=1`. The row condition makes a function. The implication expresses the return after three uses: the first two selected transitions determine a required third.

Recover p by taking the unique selected column in each row. Conversely, p creates the table by selecting exactly its output pair in each row. These constructions are inverse. The triple-application requirement is therefore the same in both formulations, with MATH.7 carrying that relation. A rule A→B→C→A and its reverse both satisfy it.

There are precisely two such rules. From `p^3=id`, p is invertible with inverse `p^2`. Its cycles have lengths dividing three. Since a one-element cycle is forbidden, the three modes form one three-element cycle, with two possible orientations. This reasoning proves completeness; listing two examples alone would not.

Change the device to four modes, retaining the three-use return and no unchanged mode. A permutation of four elements cannot partition them into cycles all of length three, so no rule exists under these conditions. Change instead to a return after two uses. The conditions become `p_(p_i)=i` and `p_i!=i`; the indicator formulation requires symmetry `r_ij=r_ji`. It admits three pairings of four modes. Remove the former three-use implication: leaving it in the formulation would make the new, feasible requirement appear impossible.

The result is a rule that can be implemented and its stated scope: deterministic changes of the visible mode without hidden state. A proposal with additional state describes a different device and needs a new account of its operation.

#### MMP.10:5.2 - Preserve existence while repairing a count

An optional assignment gives each of two named requests either no selected option or one of options 0 and 1. Different requests may select the same option. This is a partial function from the two requests to `{0,1}`. Each request has three possibilities, so there are nine assignments.

Suppose the storage format gives each request two bits: d says whether an option is defined, and q gives its value when defined. When `d=0`, q is ignored. All sixteen four-bit records denote valid partial assignments. Every assignment has a record, so the representation can support an existence query with translated requirements.

It does not preserve the count. The empty assignment has four records, each of the four assignments defined on exactly one request has two records, and each of the four total assignments has one record. Thus `4 + 4*2 + 4 = 16`. Uniform selection among records gives probability `4/16` to the empty assignment and `1/16` to each total assignment, rather than the `1/9` obtained by uniform selection among assignments.

For a count or uniform assignment sample, one repair is the structural condition `d=0 implies q=0` for each request. There are now three admissible bit pairs per request and nine records, one per assignment. Another is a single variable with domain `{absent,0,1}` per request. If the sixteen-record storage representation must remain, group or weight its records using the multiplicities instead. To sample the nine assignments uniformly, give each record of an assignment with m records probability `1/(9*m)`. The probabilities of all m records then sum to `1/9` for that assignment. Thus each record of the empty assignment receives `1/36`, each record of a one-request assignment `1/18`, and each total-assignment record `1/9`. C.29.1 supplies the required correspondence; MMP.7 supplies a probability law when sampling is the intended operation.

The original existence use can remain sufficient. The new count or sampling question exposes the need for the additional construction. No change in the underlying possible assignments is intended.

#### MMP.10:5.3 - Keep quantities and domain restrictions together

A preparation requires one litre containing 35 percent solute by volume, using solutions A and B at 20 and 80 percent. Assume solute is conserved and component volumes add in this preparation. Those subject assumptions supply the relations. Let x and y be the respective volumes in litres; choose nonnegative real domains because the amounts can initially be divided freely.

The joint conditions are `x+y=1` and `0.2*x+0.8*y=0.35`. Substitution gives `x=0.75`, `y=0.25`. Both the total and solute requirements hold for those amounts. Separate bounds `0<=x<=1` and `0<=y<=1` would lose their required total.

Now only whole half-litre doses may be used. Change the representation to `x=m/2`, `y=n/2`, with nonnegative integers m and n. The volume equation becomes `m+n=2`. Its possibilities `(m,n)=(2,0),(1,1),(0,2)` give solute amounts 0.2, 0.5 and 0.8 litre. None supplies 0.35 litre. Rounding the former solution changes the preparation; it does not satisfy its original condition.

If the required concentration changes to 50 percent, one dose of each solution works. The subject relations and unit remain, while the requirement and feasible assignment change. If mixing changes volume or solute, obtain the replacement subject relation before revising its mathematical expression.

### MMP.10:6 - Bias-Annotation

Tool familiarity can make scalar variables appear inevitable and conceal a different object or useful operation. Begin with the candidate object and its requirements. Compare representations when that comparison can change the answer or obtaining effort.

Compactness can hide duplicate records or omitted possibilities. Judge the representation by the requested result and the work needed to obtain it.

### MMP.10:7 - Conformance Checklist

- Can the reader identify a candidate object before interpreting the variables, including what is supplied, unknown or selectable?
- Do domains, units, shared quantities and definedness express the intended possibilities?
- Which conditions make the representation denote an object, and which express requirements on it?
- Do conditions that must hold together refer to the same assignment? Are alternatives and conditional restrictions preserved?
- Can intended cases be represented and satisfying assignments be interpreted at the reach required by the question?
- Does the requested value, preference, count or probability survive the representation, including auxiliary values and duplicate records?
- What does the obtaining method actually establish, and which changed requirement reopens which construction?

### MMP.10:8 - Common Anti-Patterns and How to Avoid Them

| Failure | Why it changes the result | Repair |
| --- | --- | --- |
| Use separate bounds in place of a joint relation. | The same assignment can violate the lost total or coupling. | Retain the relation with its shared variables. |
| Number labels and use their arithmetic as a subject law. | Addition or order on the labels may describe no operation on the labeled objects. | Supply the intended operation or use names as names. |
| Read an empty restricted search as absence in the original problem. | Intended cases may lie outside the chosen bound or family. | Return the restricted conclusion or extend the representation. |
| Count records as objects after adding auxiliary fields. | Multiple records can describe one object and alter the count or sampling law. | Canonicalize, group or weight by the needed correspondence. |
| Keep a consequence of a replaced requirement. | It can remove the newly allowed cases, as in the changed rule in :5.1. | Re-derive the affected constraints. |

### MMP.10:9 - Consequences

The mathematical problem becomes available for reasoning, computation and revision without leaving the interpretation of its variables implicit. A solver result can be returned as the arrangement, quantity or unresolved distinction that the work needs.

Constructing and maintaining a second representation has a cost. Direct formulation is often sufficient when the objects and their restrictions already have a clear expression. A structured intermediate formulation becomes useful when it preserves meaning across several receiving notations, helps revise requirements or exposes a calculation that the first representation hid. Any efficiency advantage depends on the resulting obtaining method.

### MMP.10:10 - Architectural Rationale

Mathematical modeling often starts with choosing how possible objects will be expressed. The choice determines which restrictions must be added and which results can be recovered. Separating representation conditions, subject requirements and the operation on solutions makes revisions local: a changed requirement need not replace the representation, and a new representation need not change the intended possibilities.

An operation can itself be the unknown object. The finite-rule case therefore treats repeated action as a requirement on a function and uses composition to express it. The same organization applies to other structured objects, while their mathematics supplies the needed constructions and proofs. MATH.7 explains reversible transport after the maps are available; this pattern develops the modeling choice and construction of those expressions, including cases that need a many-to-one correspondence.

The connection to computation runs in both directions. A mathematical formulation supplies the problem a procedure must answer. The operations supported by a procedure can suggest a different expression of that problem. Meaning is retained through the representation conditions and answer interpretation, while performance is judged on the resulting work.

### MMP.10:11 - SoTA-Echoing

The [MiniZinc Handbook 2.10.1, modeling and efficiency sections](https://docs.minizinc.org/en/stable/efficient.html) develops alternative models, derived constraints and interactions with solving methods. Adopt comparison of the resulting work; a smaller variable count alone does not settle it. A direct scalar formulation remains economical when its meaning is already clear.

[Akgun and colleagues, Conjure (2023), sections 2-4](https://www.ijcai.org/proceedings/2023/0765.pdf) separates representation selection from expression refinement and introduces structural constraints during refinement. Adopt this construction when structured objects would otherwise disappear into unexplained scalar choices. Conjure's finite combinatorial scope and model-selection heuristic remain specific to that approach. They do not establish a general best representation or performance guarantee.

The [Essence language reference, function and relation domains](https://conjure.readthedocs.io/en/latest/essence.html) makes such choices as partiality and cardinality explicit. This informs :4.2-4.3; its particular syntax is optional. The ordinary alternative is to express those conditions directly in a familiar mathematical notation.

For infinitely many possible objects, a finite parameterization needs its own coverage or approximation argument. Consider continuous nonnegative functions f on `[0,1]`, with `f(0)=f(1)=0` and integral one. An affine parameterization permits only the zero function after the endpoint conditions, so it fails. The quadratic `f(t)=6*t*(1-t)` satisfies every requirement. This authored countercase explains why the finite structured-model sources do not settle general parameterization. C.29.1 supplies the interpretation of a restriction; the relevant mathematical method supplies a suitable larger family or approximation.

To apply the formulation in another subject, obtain the relations and mathematical operations needed to express its requirements. Reconsider the representation when a new requirement, result kind or obtaining method changes what it needs to preserve or make affordable.

### MMP.10:12 - Relations

- **B.5.FM and B.5.TU:** construct a first account and connect a subject theory to the encountered problem. This pattern translates its candidate objects and conditions into a mathematical formulation.
- **MATH.1 and MATH.5:** construct composable paths and extend an assignment on elementary steps to compounds while preserving operations and equations. MATH.16 chooses a mathematical construction from the maps it must support. MATH.7 transports structure when the required bijections have been constructed.
- **C.29.1 and C.29.2:** supply correspondence, answer recovery and the separation of a mathematical result from its obtaining procedure and execution.
- **C.16.IR:** determines what a compatible set permits one to infer through projection and constancy of the requested quantity.
- **MMP.7 and MMP.8:** construct observation probabilities and information-dependent choices. A formulation's variables retain those probabilistic and temporal meanings.
- **MMP.9:** derives a reduced evolution law when retained quantities depend on eliminated contributions. The resulting law can supply relations used here.
- **C.11.DUA and E.22/E.23:** choose worthwhile further inquiry and organize evaluation and improvement of a formulation or its obtaining work.
- **ME:** uses the mathematical result when constructing or changing a working method. Its performance in the subject remains distinct from the formal properties of its description.

### MMP.10:End

## MMP.11 - Construct a Model Family from Known Relations

> **Type:** Method pattern
> **Status:** Usable, evolving
> **Normativity:** Normative within the stated use

### MMP.11:1 - Problem frame

Use this pattern when part of a model is supported, but a function or other relation is still unknown. You may know which quantities interact, what must be conserved, or how a response begins and ends, while lacking its form between those conditions. You need candidate models that retain this knowledge while allowing the missing contribution to vary.

Begin by locating the unknown contribution in the relations needed for the question. Say what it takes as input, what it supplies and which properties its variation must preserve. Construct a family for that contribution, then put it back into the model. For a response that rises from zero to one, a family of curves constrained by those properties gives a different starting point from an unrestricted fitted curve.

The first useful result is a family of models, its remaining adjustable parts and the restrictions introduced by its construction. It may already give a sufficient bound. When observations are available, the same construction lets you ask which functions, parameters or consequences those observations can distinguish.

You need the subject grounds for the retained relations and enough mathematics to construct and use the family, or access to that mathematical contribution. A known adequate relation can be used directly. An unknown numerical parameter inside a suitable family normally needs its estimation method. Use this pattern when the family itself needs construction or revision. B.5.FM and B.5.TU help when the missing contribution is the subject account or theory from which a relation should come.

### MMP.11:2 - Problem

A familiar formula can exclude the response being sought. Giving a learner unrestricted freedom can create the opposite problem: the fitted response may violate a known relation. Fitting two interacting contributions independently can also destroy a property that depends on their connection.

Agreement with recorded outputs leaves another difficulty. Several parameter settings may define the same function, and several functions may produce the same observations. Some receiving questions distinguish those alternatives; others need only a consequence on which they agree. Choosing one fitted instance can conceal this difference.

The modeling work is to construct the adjustable contribution in a form that retains the supported relations, then determine what that family can establish for the present question. The construction itself may impose additional restrictions, so its expressive limits belong to the answer.

### MMP.11:3 - Forces

| Force | Tension |
| --- | --- |
| Retained knowledge and flexibility | A structural relation can rule out impossible candidates; an unsupported restriction can remove the needed one. |
| Local fitting and coupled behavior | A contribution can fit its own samples while disrupting the model in which it is used. |
| Simple representation and family coverage | A small parameterization is easier to fit but can omit admissible functions. |
| Parameter recovery and useful inference | Parameters may remain ambiguous while a required consequence is determined. |
| Prediction and intervention | Two accounts can agree during observation and differ after one mechanism is changed. |

### MMP.11:4 - Solution

Locate the missing relation, separate what is retained from what may vary, construct the adjustable family, and derive its contribution to the receiving question. Observation or computation is then selected for what remains unresolved.

#### MMP.11:4.1 - Locate the contribution that may change

State the result wanted from the model. Identify the unknown relation and the quantities it connects. Keep its inputs, output, domain, units and permitted dependence explicit enough to substitute a candidate into the surrounding relations. A function of present state, a function of its history and a random response law admit different constructions. If equal proposed inputs require different deterministic outputs in the admitted circumstances, revise the inputs or retain those alternatives. Greater flexibility of a single-valued function cannot supply both outputs. For a dynamic model, A.3.3.TR supplies the corresponding reconsideration of state.

Recover the grounds and application range of the relations you retain. A balance may be required by the chosen boundary; monotonicity may hold only over one operating range; a shape assumption may be provisional. Keep an allowed discrepancy when the subject account supplies one. A convenient property is not automatically a property of the subject.

Use the smallest part that can be varied without silently changing another retained claim. If an adjustable term can absorb a known contribution, include that possibility in the inference question. Section :5.2 shows an ambiguity between two gross transfers even when their net effect is known.

#### MMP.11:4.2 - Construct the permitted variation

Translate each retained property into a mathematical condition, then choose a construction that satisfies it. MMP.10 supplies the general work of representing candidate objects and their conditions. Here the object being constructed is a family of relations to insert into the model. Direct conditions may already give a workable representation of that family. Constructing through free elements is useful when their variation should preserve the conditions; compare its obtaining and revision operations with those of the direct representation.

A useful construction separates a fixed part from free variation. If a linear operator L must satisfy `L(g)=b`, find one particular solution g0 and choose a correction h with `L(h)=0`. Then `g=g0+h` retains the condition. This describes every solution only if the admitted corrections cover the whole null space in the chosen function domain. Restricting h to a few basis functions supplies a smaller family. Establish the linearity and domain before using this construction.

For a sign, bound or shape condition, construct through a map whose output has that property. Nonnegative weights can be normalized to probabilities. Integrating a nonnegative function can produce a nondecreasing response. Work out the domain and boundary of the resulting family: strict positivity excludes zeros, and an integral of an ordinary integrable function produces an absolutely continuous curve. Section :5.1 develops one such construction and its restriction.

When a property depends on coupling, construct the coupled contribution. Using the same transfer with opposite signs in two balance equations preserves their total. Two separately fitted right-hand sides have no such identity unless their joint conditions supply it. Use A.3.3.TR to assemble a change rule from the interacting relations.

A penalty during fitting offers a different construction: it discourages violations while allowing them. Use it when that allowance fits the question. If the account requires an identity, either build it into the representation or use an obtaining method that enforces it. The size of a training penalty does not by itself establish the identity.

#### MMP.11:4.3 - Choose the representation and its range

Choose a representation whose operations fit the required use and available resources. A table can represent a finite function. A basis expansion or program can retain a useful structure. A neural representation can supply a flexible adjustable function. The meaning of its inputs and outputs, and the retained relations, remain part of the model.

Check two different questions. Does every admitted parameter setting produce a relation allowed by the construction? Does the construction cover all relations needed for the present conclusion? A witness may need only one candidate; an impossibility claim over all admissible models needs coverage of that whole family or another sufficient argument.

State restrictions introduced by knots, basis functions, regularity, network architecture or domain truncation when they can change the answer. A numerical fit inside the restricted family answers for that family. If its consequence is sufficient, a more flexible family may add only cost. If the missing case matters, change the representation.

Different parameters can denote the same function. Recover the function or consequence needed by the receiving use rather than demanding unique parameters by default. Section :5.3 gives a normalization redundancy. Use MATH.7 when a change of representation has constructed inverse maps; use C.29.1 when correspondence is more general.

#### MMP.11:4.4 - Put the family into the model before using its fit

Substitute the adjustable contribution into the relations that consume it. Derive the resulting observable or answer condition with shared quantities kept shared. An error measured on an isolated contribution and an error in the coupled output are different fitting questions.

Choose the insertion point from what must remain meaningful. In a component model, inserting an unknown relation before algebraic elimination can retain a named component's inputs, outputs and connections. Adding a correction after elimination can be simpler, but the correction then acts on the transformed relations. Recover how it affects the properties needed by the original question. A reduced model may use MMP.9 to derive the contribution its simplification leaves open.

Represent how observations are produced. MMP.7 derives a probability law for records when probability is needed; C.16.IR uses the supplied indication relation to obtain compatible cases or bounds. Fitting an unobserved internal term as if it were measured supplies an extra premise. If that premise is unavailable, fit or constrain through the observable relation instead.

For a dynamic or implicitly defined model, obtain the consequence through its coupled equations and conditions. A good component fit does not settle whether the resulting evolution, initialization or constraints are usable. Apply the mathematical and computational method appropriate to the stated consequence; C.29.2 helps formulate its obtaining operation.

#### MMP.11:4.5 - Determine which remaining differences matter

Ask what the available observations constrain: the adjustable parameters, the unknown function over a stated domain, or a particular consequence. Use C.16.IR on the resulting observation relation. The function can remain undetermined away from the observed inputs even when its recorded values are fixed.

When ambiguity could change the answer, construct two admitted candidates with the same relevant observations and different receiving consequences. Such candidates show what further information must distinguish. If all compatible candidates or a sufficient bound give the same answer to the present question, use that answer without resolving unrelated differences.

Repeated numerical fits can discover alternatives. Agreement of finitely many fitted instances leaves unsearched alternatives possible. A claim of uniqueness needs its mathematical or statistical grounds; a sufficient decision can require much less. Numerical search failure also differs from a proof that the family is inconsistent with the observations.

Change the question explicitly when a new use requires it. An intervention may distinguish models with the same observational behavior. C.28.MR supplies the replacement of the affected mechanism under its causal premises. Explanation or modification of a working method can require structure beyond that needed for prediction; characterize the required explanatory use through C.2.8 and Explanation Design (EXD).

#### MMP.11:4.6 - Use the consequence or revise the family

Return the result with the family, input range and conditions that affect its use. It may be a candidate relation, a bound, a conditional prediction, a supported instruction or a located missing contribution. When the model is used to change a working method, Method Engineering receives the consequence and the relations the proposed change must preserve.

Revise the part whose restriction prevents the needed result: the subject premise, permitted dependence, representation, observation relation or obtaining method. Use B.5.RR to carry a changed premise or question through the reasoning. General comparison, portfolios and improvement use the existing C.16, C.11 and E.22/E.23 methods when those questions arise.

Stop when the receiving use has a sufficient answer or the missing contribution is clear enough to obtain. Use C.11.DUA when deciding whether another observation, a richer family or further computation can improve that use enough to warrant its cost. A more detailed family is valuable only through what it enables.

### MMP.11:5 - Archetypal Grounding

#### MMP.11:5.1 - Construct a response from its known shape

A normalized input u lies in [0,1]. The subject account supports a nondecreasing response r with `r(0)=0` and `r(1)=1`. Its intermediate shape is unknown. Begin with these properties, rather than choosing a straight line as the only candidate.

Choose an integrable h with `h(u)>=0` almost everywhere and `H=integral_0^1 h(v) dv>0`. Define

`r(u)=integral_0^u h(v) dv / H`.

The endpoints follow by substitution. For `u2>=u1`, the difference is the nonnegative integral of h over [u1,u2], divided by H. Thus every member is nondecreasing. These curves are absolutely continuous. Every absolutely continuous nondecreasing response with these endpoints has such a representation using its almost-everywhere derivative, but a jump response is outside this family. The needed regularity must come from the question or remain a declared restriction.

For a small calculable family, use linear segments through (0,0), (1/4,q), (1/2,1/2) and (1,1). Their slopes are `4*q`, `2-4*q` and 1. They are nonnegative exactly when `0<=q<=1/2`. This is a construction of admissible candidates, not a conclusion from measurements alone.

Suppose observations establish only the three values at 0, 1/2 and 1. Every q in that interval agrees with them. The consequence `r(1/4)<=0.6` follows for this whole family; it also follows for every nondecreasing response with the given midpoint. There is no need to identify q for that question.

Now the receiving use asks whether `r(1/4)>0.3`. Candidates q=0.2 and q=0.4 satisfy the same observations and give opposite answers. Another repetition at the three old input values does not distinguish these ideal candidates. An observation near the disputed input may help; its precision and cost belong to that new question. Alternatively, a supported additional shape relation could narrow the family.

#### MMP.11:5.2 - Retain an exchange balance without inventing its mechanism

Two nonnegative amounts x and y exchange a conserved total N. The forward and reverse rates are unknown. Use locally Lipschitz nonnegative rate functions a(x,y) and b(x,y), defined on a neighborhood of the nonnegative states being used, and construct

`q=x*a(x,y)-y*b(x,y)`,

`x_dot=-q`, `y_dot=q`.

Adding the two equations gives zero change in x+y for every admitted a and b. At x=0, `x_dot=y*b(0,y)>=0`; at y=0, `y_dot=x*a(x,0)>=0`. With these regularity conditions the continuous-time solution preserves nonnegativity. These are properties of the coupled construction. The applicability of conserved exchange to the subject remains a premise.

Even complete knowledge of q need not identify the gross transfers. For any nonnegative locally Lipschitz h, define

`a_new=a+y*h`, `b_new=b+x*h`.

The two added contributions to q are `x*y*h` and `-y*x*h`, which cancel. The whole observed evolution is unchanged. This is an algebraic family of alternatives, not merely several successful numerical fits.

For a dimensionless instance, take a=b=1. The alternative h=1 gives `a_new=1+y` and `b_new=1+x`, yet both models have `q=x-y`. At x=2, y=1 they both predict `x_dot=-1`.

Change the question: a proposed intervention suppresses only the reverse transfer while leaving the forward rate law applicable. Under that causal premise, C.28.MR replaces the reverse contribution by zero. The first model gives `x_dot=-2`; the second gives `x_dot=-4` at the same state. Ordinary observations of x and y under the unchanged mechanisms cannot choose between these accounts. A prediction under the old operation can still be useful; the proposed intervention needs a contribution that distinguishes the mechanisms or a sufficient bound covering them.

For dimensional quantities, a and b have inverse-time units, while h has inverse-amount-inverse-time units. Restoring units prevents treating the added terms as arbitrary dimensionless corrections.

#### MMP.11:5.3 - Construct probabilities while keeping boundary outcomes

A report has three possible outcomes. Let `w_i>=0` and let their sum W be positive. Set `p_i=w_i/W`. Every candidate has nonnegative probabilities summing to one. Conversely, every probability vector on these outcomes is represented by choosing w=p. Thus this construction includes zero-probability outcomes.

The weights (0,1,3) and (0,2,6) both give probabilities (0,1/4,3/4). The parameter vector is redundant even if the probability vector becomes fully determined. There is no need to distinguish those weights when the receiving question uses only the law.

A strictly positive parameterization, such as exponentiating every finite unconstrained parameter before normalization, excludes zero probabilities. It can approximate a zero closely but cannot express it with finite parameters. If the subject account rules out the first outcome, retain that zero in the construction and normalize weights for the remaining outcomes. Whether a very small nonzero value would suffice depends on the receiving question.

The constructed p is a family member, not yet an estimate from data. MMP.7 composes it with selection, rounding or other recording behavior. The appropriate statistical method then determines what the observations support. Changing the recording procedure can change that inference without changing the underlying outcome family.

### MMP.11:6 - Bias-Annotation

Familiar formulas can turn an assumed shape into an unnoticed restriction. Flexible fitting can conceal a different commitment: the selected inputs, architecture and loss still determine which functions can be obtained. Recover those choices when they affect the receiving result.

A respected subject law can also be applied outside its range or boundary. Preserve its grounds and allowed discrepancy. If no supported structural restriction is available, an unrestricted family can be a reasonable candidate for a bounded use; further structure must earn its place through the subject question.

### MMP.11:7 - Conformance Checklist

- The unknown contribution has interpretable arguments, result, domain and permitted dependence.
- The retained relations have subject grounds and an application range.
- The construction shows why admitted adjustable values preserve the required properties.
- Restrictions introduced by representation are carried into conclusions that depend on family coverage.
- Coupled effects and the actual observation relation determine the fitting or inference question.
- Remaining parameter, function and consequence ambiguities are distinguished when they change use.
- A changed intervention or receiving question reopens the relevant contribution.
- The result can be used, qualified or passed to a named next method without requiring unrelated identification work.

### MMP.11:8 - Common Anti-Patterns and How to Avoid Them

| Failure | Consequence | Repair |
| --- | --- | --- |
| Fit each contribution independently despite a shared identity | The fitted whole can violate the identity. | Build the shared quantity or joint condition into the family. |
| Treat a penalty as an enforced relation | A small fitting loss can conceal a consequential violation. | Match the construction and obtaining method to the allowed discrepancy. |
| Treat a finite fitted family as all admissible relations | A failure inside it becomes an unsupported impossibility claim. | State its restrictions and widen or bound the family when the question needs it. |
| Identify parameters when only a consequence is needed | Work is spent resolving distinctions that do not change use. | Apply the observation relation to the receiving consequence. |
| Transfer an observational fit to an intervention without modeling the mechanism change | Models agreeing on observed behavior can imply different intervention effects. | Construct the mechanism replacement and the alternatives it can distinguish. |

### MMP.11:9 - Consequences

The family carries usable knowledge through variation and fitting. It can supply a bound before a particular model is selected, or reveal why more observations of the same kind will leave the important ambiguity intact.

The cost is constructing and checking the representation. Strong restrictions reduce the search but can exclude useful candidates. A flexible family can retain more possibilities while increasing inference cost and leaving more uncertainty. Compare these costs against the result the work actually needs.

### MMP.11:10 - Architectural Rationale

Constructing the free part through the retained relations makes the reason for a property inspectable. A shared transfer preserves a total because the same quantity enters with opposite signs. A shape-constrained response preserves monotonicity because its increments are integrals of nonnegative values. Those reasons remain available when coefficients or learned functions change.

Separating function, representation and receiving consequence also permits economical inference. Many representations of the same function need not be distinguished. Functions that agree on the needed consequence may remain as alternatives. A new intervention can make a formerly irrelevant difference decisive.

The insertion point is therefore an architectural choice in the model. It determines what the adjustable contribution can change, which relations constrain it and which results still have the interpretation the work needs. A symbolic expression and a trained network can each participate in this construction when their mathematical role is recoverable.

### MMP.11:11 - SoTA-Echoing

**How much of the relation should be left free?** The historical [SINDy work, Brunton, Proctor and Kutz (2016), Discussion and Appendix B](https://robotics.caltech.edu/wiki/images/a/a3/BPK_PNAS.pdf), binds sparse discovery to the chosen coordinates and function library. The [universal differential equations construction, section 2.3](https://arxiv.org/html/2001.04385v4), combines retained mechanisms with an adjustable function. Sections :4.1-4.3 adopt this choice of where freedom belongs. A small fixed family can be sufficient when its restrictions fit the question. The flexible construction trades additional representation and inference work for retaining variations the small family omits.

**How should a required relation survive fitting?** For the conservation question in :5.2, :4.2 selects a shared transfer with opposite signs over independently fitted change laws for x and y with only a finite conservation penalty. The latter can fit observations while violating the required total elsewhere. The shared construction preserves that total for every admitted choice of its rate functions. Accept the extra derivation and restriction to conserved exchange in return for that identity; obtain the subject grounds for conservation first. When the question allows a specified discrepancy, a penalty or simpler approximate relation can be sufficient at lower construction cost. Carry its discrepancy into the requested consequence rather than requiring the identity anyway. Direct constraints enforcing the relation remain another option under MMP.10.

**Where does the adjustable part enter?** [Dyad's model-discovery documentation](https://help.juliahub.com/dyad/stable/analyses/udes.html) supports component-level insertion before structural simplification. [Micluta-Campeanu and colleagues (2026), sections 2.1-2.2](https://arxiv.org/html/2603.15943v1), demonstrate post-simplification correction followed by optional reduction and symbolic replacement. Section :4.4 retains both placements, chosen by their effect on the needed relations. Their thermal application supplies one use, not the scope of this method.

**What does fitting resolve?** [Loman and Baker (2025), sections 3.1, 3.3, 3.5 and B.5](https://arxiv.org/html/2510.14140), distinguish functions, parameters and predictions. Section 3.1 also constructs an algebraic compensation between an unknown function and a mechanistic parameter that preserves observed dynamics. Adopt that construction of indistinguishable alternatives in :4.5; :5.2 adapts it to coupled directional rates. Their finite fitted-ensemble comparisons in :2.4 and Appendix B can reveal alternatives, but agreement of sampled fits does not prove uniqueness over the admitted family. Constructing two admissible alternatives with different receiving consequences already establishes the consequential ambiguity, without fitting an ensemble.

Revisit the chosen family when new subject knowledge changes its restrictions, a different observation changes what is distinguishable, a new use needs a formerly discarded difference, or another construction supplies the needed result at lower cost.

### MMP.11:12 - Relations

- **MMP.10** constructs representations and the conditions making them admissible. **MMP.9** derives an unknown contribution caused by reduction and can use a constructed family to replace it.
- **A.3.3.TR** composes a rule of change; **C.29.1** relates model consequences to their receiving use; **C.29.2** constructs the needed computation.
- **MMP.7** supplies the recording probability law. **C.16.IR** determines what the resulting indication relation resolves. **MMP.8** uses the available information in a choice question.
- **C.28.MR** constructs the changed mechanism for an intervention. **B.5.RR** revises reasoning after a changed premise or question.
- **C.2.8 and Explanation Design (EXD)** characterize the explanatory contribution needed by a reader. **Method Engineering (ME)** uses a model consequence to develop or revise the corresponding way of working.
- **C.11.DUA** compares a further modeling contribution with its cost; general model comparison and improvement use the existing framework methods.

### MMP.11:End

## MMP.7 - Construct a Probability Model of the Recorded Data

> **Type:** Method pattern
> **Status:** Usable, evolving
> **Normativity:** Normative within the stated use

### MMP.7:1 - Problem frame

Use this pattern when inference depends on how events, responses or quantities become records, and that procedure has not yet been expressed in the probability model. A feedback log may contain successes more often than failures. A timed trial can end before its event occurs. Several readings can share one calibration error. In each case, fitting a familiar distribution to the visible numbers can answer a different question from the one you intended.

Start with one possible event and follow what the observing procedure would record. Include the possibility that it leaves no record, reports an interval or shares an influence with another observation. Repeat for a contrasting event. These cases reveal what the mathematical outcome must contain before you choose its distribution.

The result is a probability law for the recorded outcome under stated assumptions, together with its relation to the quantity being inferred. It can supply a likelihood, a distribution of future records or a reason the intended inference remains ambiguous. This pattern develops probabilistic formulation within mathematical modeling. The subject practice supplies the meaning of the event, the observation procedure and plausible relations among quantities.

You need conditional probability and sums over alternatives; continuous cases also use densities and integration. A collaborator can supply those operations when you can describe the observation procedure and interpret the returned law. If an existing model already represents that procedure and answers the question, use it. When only compatible ranges are needed, C.16.IR can provide a sufficient answer without probabilities.

### MMP.7:2 - Problem

The distribution of a subject property and the distribution of its records can differ. Selection changes which cases appear. Coarsening combines several possible values into one report. A common influence makes observations dependent. These transformations remain part of the inference even when a dataset presents every row in the same format.

A formula such as independent errors around a predicted value already makes choices about those transformations. If the choices are left implicit, more data and more accurate computation can reinforce a mistaken interpretation.

The difficulty is to construct the law of the observations from the modeled subject and its recording procedure, preserving the dependencies that matter to the question.

### MMP.7:3 - Forces

| Choice | What changes in the inference |
| --- | --- |
| Target population and included cases | A result about reported cases may require a selection model before it describes the target population. |
| Retain or remove unobserved quantities | Keeping them can clarify construction; summing or integrating them out can simplify computation. |
| Separate and shared influences | Conditional independence can hold while observations remain dependent after a shared influence is removed. |
| Rich observation model and obtainable information | Extra parameters can represent real effects while leaving the desired answer less identifiable. |
| Probabilistic answer and sufficient conditional answer | A likelihood can be useful before choosing an estimator or a prior. A bound may already settle the action. |

### MMP.7:4 - Solution

Construct the possible recorded outcomes from the observation procedure. Combine the subject and recording laws, remove the unobserved alternatives by the appropriate probability operation, and inspect what the resulting law permits you to infer. Return to the procedure or assumptions when its output does not answer the working question.

#### MMP.7:4.1 - Choose the target and the recorded outcome separately

State what the answer concerns: a rate in a population, a property before measurement, a future response, or another quantity selected by the work. Specify the population, conditions and time range when they change its meaning. Use C.16 for the characteristic being measured and C.16.MR for the relation from the property to an indication.

Describe one complete outcome of the observing procedure. It may contain a value and an inclusion flag, a duration and a timeout flag, or several related readings. The mathematical outcome space must distinguish every report the procedure can produce that affects the inference.

State what the observation plan fixes. Following a known cohort produces information about excluded cases that a sample drawn only from submitted reports may lack. Stopping after a specified time, after a specified number of records, or after an event can produce different data laws. Recover the actual plan before treating any count as fixed.

#### MMP.7:4.2 - Construct the joint law from the modeled dependencies

Introduce variables for the quantities used by that procedure. Explain their domains and meanings before assigning distributions. Let Z denote an underlying event or value and O its recorded outcome. Parameters theta describe quantities held fixed in the proposed probability model. When these laws are represented by probability masses or by densities under an appropriate reference measure, write the subject law as p_theta(z) and the conditional recording law as k_theta(o given z). Their joint expression is:

`p_theta(z,o) = p_theta(z) k_theta(o given z).`

Each factor needs an interpretation. The first describes variation in the subject under the stated conditions; the second describes how the procedure records it. A deterministic recorder assigns probability one to its specified output and zero to the other outputs. This accommodates rounding and threshold reports as well as random response or selection.

Use a sequence of conditional laws when more stages matter. Multiplication follows the chain rule. Omitting a variable from a conditional law asserts that, given the retained variables, it does not change that law. Make that assumption from the modeled relation; separate rows in a file provide no independence argument.

Keep an unknown fixed parameter as unknown. Give it a probability distribution only when that additional modeling choice is justified for the intended inference. A shared but unknown calibration offset can remain a parameter in a joint likelihood. A distribution over possible offsets supports a different, explicitly extended model.

#### MMP.7:4.3 - Obtain the law for what was actually recorded

The general operation averages the chance of an observed event over the underlying cases. Let K_theta(B given z) be the chance that the report falls in a set B, given underlying value z. Then:

`P_theta(O in B) = integral K_theta(B given z) P_theta(dz).`

Here P_theta(dz) means averaging with the probability law of Z: a weighted sum for discrete cases or an integral for continuous ones. A deterministic recorder O=g(Z) has K equal to one when g(z) lies in B and zero otherwise. This constructs its output law even when the joint pair (Z,O) has no ordinary joint density, as with O=Z for a continuously varying Z.

When the masses or densities used in :4.2 are available, the same averaging operation gives the law of a particular report. For discrete unobserved alternatives, sum:

`p_theta(o) = sum_z p_theta(z) k_theta(o given z).`

For continuous alternatives, integrate the product of the subject density and the recording factor. A report produced exactly when Z lies in a fixed set A has recording factor one inside A and zero outside; its probability reduces to the integral of the density over A. If the procedure chooses which set to report, retain that choice in k_theta(A given z).

For example, let Z be equally likely to be 0 or 1. A truthful recorder reports {0,1} always when Z=0 and with probability 1/2 when Z=1; otherwise it reports {1}. The probability of receiving {0,1} is `1/2 + (1/2)(1/2) = 3/4`, although the probability that Z lies in {0,1} is one. The recording factor makes the difference.

For an individually observed continuous value, use a density with respect to the stated measurement convention. A point density and the probability of an interval have different meanings.

When inclusion in the dataset is itself a condition of sampling, retain its normalization. If Z has density or mass p_theta(z), and s_theta(z) is its probability of inclusion, the included-case law is:

`p_theta(z given included) = p_theta(z) s_theta(z) / P_theta(included).`

The denominator is obtained by summing or integrating the numerator over all admitted z and must be positive. If it depends on theta, dropping it changes the inference. When the counts or identities of excluded cases are also observed, include that information in the joint outcome instead of silently discarding it by conditioning. Section :5.1 shows the change.

Keep shared influences shared during elimination. For observations conditionally independent given an unknown B, integrating one joint product over B generally differs from multiplying separately integrated factors. The latter construction assigns a fresh B to each observation. Use it only when that is the observing arrangement.

#### MMP.7:4.4 - Connect the law to inference and prediction

When the observation laws have a common probability-mass or density representation, insert the recorded outcome o into p_theta(o). As a function of theta, this gives a likelihood, up to a factor independent of theta. It need not sum or integrate to one over theta. Estimation or a posterior distribution requires the chosen inferential method and its assumptions; the observation law is the input to that work.

Before drawing an inference, check whether the recording rule admits the received report for any parameter value. A continuous reading can be admitted even though its single-point probability is zero; determine admissibility from the modeled observation mechanism and the cases it permits. If no admitted case produces the report, return the conflict and locate which assumptions or recording steps need reconsideration, using C.16.IR:4.4. For example, a fixed signal with one fixed additive offset and one unchanged threshold must produce identical bits on repetition. A mixed sequence contradicts that joint account. It cannot be repaired by fitting a different signal within the same family.

Identify how the requested quantity depends on theta or on a future outcome. Two parameter settings can induce the same law for every possible record while assigning different values to the target. Constructing such a pair shows that this observation model cannot identify that distinction. C.16.IR supplies the corresponding compatible-case reasoning; numerical fitting alone cannot resolve it.

For a future record, specify whether its recording procedure is the same. For the underlying population quantity, return through the subject law rather than interpreting a selected-case rate as the population rate. A proposed intervention requires its changed relations under C.28; changing a predictor value in a fitted association is insufficient when the intervention changes how the data arise.

#### MMP.7:4.5 - Test a consequence and revise the construction

Check normalization and a small case that follows the procedure. Enumerate a finite outcome space or generate subject cases and pass them through the recorder. Compare that construction with the probabilities or summaries derived from the observation law. C.29.2 supplies a computational construction when enumeration or integration needs further work.

Then change one consequential condition: the inclusion rule, timeout, shared calibration or receiving question. Change the relevant relation and carry its effect through the calculation. This tests whether the description exposes the observation mechanism rather than merely memorizing one formula.

A simulation agreeing with the formula checks their agreement under the modeled assumptions. An available observation can challenge those assumptions; selected domain assurance determines which empirical comparison is worth performing. C.11.DUA helps choose between further observation, a conditional answer and acting with remaining uncertainty. Preserve a sufficient result without demanding another dataset merely because an influence remains unknown.

### MMP.7:5 - Archetypal Grounding

#### MMP.7:5.1 - Infer a success rate from a selectively submitted log

A team asks what fraction of attempts succeed. In a proposed model, each attempt succeeds with probability p. Every success is logged; each failure is logged independently with probability 1/4. Initially the team has a fixed-size sample of independently drawn log entries, with no information about how many attempts produced the source log.

The event variable Y is success or failure. The recording flag R says whether the attempt enters the log. Their joint probabilities are:

| Outcome | Probability |
| --- | --- |
| Success, logged | p |
| Failure, logged | (1-p)/4 |
| Failure, unlogged | 3(1-p)/4 |

The included-case success probability is `q = p / [p + (1-p)/4] = 4p/(1+3p)`. If the observed fraction of successes is 1/2, the likelihood estimate of q is 1/2, and transforming it gives `p_hat = q_hat/(4-3q_hat) = 1/5`. Sampling uncertainty remains; this calculation corrects which rate is being estimated.

The first useful result is the distinction between a 50% rate among reports and the estimated 20% rate among attempts under the supplied reporting assumptions. If the failure-reporting probability is unknown, several combinations of that probability and p can produce the same q. The log alone then leaves the population rate unresolved.

Now the procedure changes: a register names a fixed cohort of N attempts and links each submitted report to its attempt. Model those attempts as independent, each with the same success probability p, retaining the stated reporting rule. Since every success is reported, an unreported attempt is a failure. If there are k success reports, the likelihood for p is proportional to `p^k (1-p)^(N-k)`; the failure-reporting factors do not depend on p. The estimate becomes k/N. Conditioning only on reported entries would throw away information the revised procedure provides.

This is a change in the team's observing method. ME can describe the linked-attempt register and responsibility for recording it. Whether to introduce it depends on what resolving the population rate would change in the team's work.

#### MMP.7:5.2 - Preserve a common influence across readings

Two sensors measure quantities x1 and x2 with one shared calibration offset b. Their readings are `Y1=x1+b+E1` and `Y2=x2+b+E2`, with independent zero-mean errors of variance sigma squared. Begin by retaining b as a common parameter. The joint conditional density factors given b; each factor uses that same value.

For the difference, `Y1-Y2=x1-x2+E1-E2`: the offset cancels. Its error variance is `2 sigma^2`. A measurement of the difference can therefore be useful while either absolute value remains uncertain.

For repeated measurements of one x, suppose an additional justified model describes the common offset as a zero-mean random variable B with variance tau squared, independent of the errors. The average of n readings has variance `tau^2 + sigma^2/n`. Integrating a separate offset for every reading would incorrectly produce `(tau^2+sigma^2)/n`. Repetition reduces independent noise but leaves this common calibration contribution.

If the instrument is independently recalibrated before every reading, the arrangement changes. A separate-offset model can then be appropriate. The governing operation is to trace which influences are shared and preserve that sharing in the probability construction.

#### MMP.7:5.3 - Use a timed-out trial as an interval report

A test asks how long an event takes. Each independent trial is observed until its event or a fixed timeout c. Record both `V=min(T,c)` and a flag D indicating whether the event occurred before timeout. As an illustrative subject assumption, let T have exponential density `lambda exp(-lambda t)` for t at least zero, with lambda positive.

An event at time t before c contributes the density `lambda exp(-lambda t)`. A timeout contributes `P(T>=c)=exp(-lambda c)`, obtained by integrating the density over the unobserved tail. For m completed trials and total observed time S, including the timeout durations, the likelihood is proportional to `lambda^m exp(-lambda S)`.

With completions at times 1 and 2 and one timeout at 4, `S=7` and `m=2`. Maximizing this illustrative likelihood gives `lambda_hat=2/7`. Treating the timeout as a third event instead gives 3/7; dropping it gives 2/3. The flag determines which operation is correct.

If only completed trials enter a database and neither the number nor identities of timed-out trials are available, the observed-time density instead conditions on completion: divide the event density by `1-exp(-lambda c)` on the interval before c. A changed recording rule changes the model even when the stored times look the same. The exponential assumption is dispensable: a different duration law supplies its own event density and tail probability.

### MMP.7:6 - Bias-Annotation

The visible dataset invites treating its rows as the whole observation procedure. Begin from how a row, absence or interval report is produced. A second temptation is to add one independent error to every row; trace shared influences before factorizing. More detailed modeling can also conceal missing knowledge, so retain uncertainty in the recording mechanism when the available information does not determine it.

### MMP.7:7 - Conformance Checklist

- Can a reader identify the target and all possible reports that affect the inference?
- Do the subject and recording factors describe the stated procedure, including what it fixes and what it reveals?
- Are unobserved alternatives removed by a justified sum, integral or conditioning operation?
- Does the joint law preserve common influences and any information about excluded cases?
- Is the first result interpreted as a likelihood, estimate, prediction, bound or unresolved distinction with its respective conditions?
- Can the formulation be changed when the observing procedure or receiving question changes?

### MMP.7:8 - Common Anti-Patterns and How to Avoid Them

| Failure in this work | Repair |
| --- | --- |
| Reported-case frequency is substituted for population frequency despite selective reporting. | Derive the included-case law and the relation to the target rate. |
| An interval report is replaced by an event at its endpoint. | Sum or integrate the joint subject-and-recording law over the underlying values that can produce the report. |
| A common influence is independently removed from every observation. | Keep it in the joint law before elimination. |
| A likelihood is read as a probability distribution over the unknown parameter. | Supply the inferential method that turns it into the requested result. |
| A fitted model is trusted because its simulator reproduces its own assumptions. | Separate computational agreement from the subject comparison needed for the use. |

### MMP.7:9 - Consequences

The constructed law allows computation to answer the intended observation question and can expose an ambiguity before expensive fitting. A changed reporting procedure becomes a model change that can be analyzed. The work may also show that the target needs assumptions or information absent from the records; a narrower conditional answer can remain useful.

### MMP.7:10 - Architectural Rationale

The observation procedure connects the subject to the data used in inference. Keeping that connection explicit makes deterministic coarsening, random selection and shared uncertainty instances of one construction. It also separates modeling choices from the later choice of an inference algorithm.

The factors are chosen for the procedure and question. Their order as a probability factorization does not establish a causal direction in the represented world. Several factorizations can describe one joint law; the subject account and intervention question determine any causal interpretation.

This method uses C.16's measurement and resolvability work while supplying the probability operations those patterns leave to statistical modeling. Its examples require different transformations: conditioning after selection, joint elimination and tail integration. The transferable operation survives replacing the logged activity, sensor or timed event.

### MMP.7:11 - SoTA-Echoing

[Gelman, Vehtari and McElreath, Statistical Workflow (2025), sections 1.1-1.7](https://sites.stat.columbia.edu/gelman/research/published/Statistical_Workflow_article.pdf), emphasize measurement, assumptions, shared information and the distinction between model parameters and inferential targets. Adopt the connection of those decisions to model construction and revision. Their comparison of Bayesian and other workflows supports leaving the inference method explicit; it does not select one estimator for every observation law.

[Rubin, Inference and missing data (1976)](https://doi.org/10.1093/biomet/63.3.581), is a historical foundation for specifying when a missing-data mechanism can be ignored. Adopt the requirement to establish the applicable conditions rather than assuming that absence is harmless. Its qualifications depend on the inferential method. The examples here derive their recording laws directly and require no blanket ignorability claim.

The [Stan User's Guide 2.39 treatment of truncation and censoring](https://mc-stan.org/docs/stan-users-guide/truncation-censoring.html) provides executable constructions for restricted observations and tail reports. Adapt those probability operations to :4.3 and :5.3. The guide's programming and inference conventions are useful implementations, not prerequisites of the method. A direct finite calculation or another suitable implementation can supply the same law.

The three demonstrations are elementary constructions for this pattern. They explain the modeling operations under stated assumptions; they are not empirical reports about the activities or devices used as examples.

### MMP.7:12 - Relations

C.16.MR constructs the relation from a sought property to its indication; this pattern makes its probability law usable for inference. C.16.IR identifies what the resulting observations can resolve. C.29.2 constructs a computation for marginalization, estimation or prediction when needed, and C.29.3 addresses its realization. C.28 governs a causal use of the result. MMP.8 uses the observation model to determine the information available to a decision. B.5.MPC.R coordinates a repair spanning subject interpretation, mathematical formulation and computation. ME uses the result when the observing procedure itself is being changed.

### MMP.7:End

## MMP.8 - Formulate Choices under Incomplete Information

> **Type:** Method pattern
> **Status:** Usable, evolving
> **Normativity:** Normative within the stated use

### MMP.8:1 - Problem frame

Use this pattern when a mathematical problem mixes quantities you may choose with quantities you do not control, or when a proposed solution depends on information that arrives too late. A solver can find a configuration for each possible circumstance while leaving you unable to select one in advance. A simulation can show a successful continuation because it chose an environmental value that the acting system cannot choose.

Begin with one proposed action. Ask what will be known when it must be chosen, which quantities remain outside that choice, and what result the action must achieve. Construct two possible circumstances that look the same at that moment. If the proposal assigns different actions to them, it needs another observation, a different decision time or a different policy.

The result is a mathematical formulation of the available choices and the requirement they must satisfy, including their dependence on information. It can establish a feasible fixed choice, a policy, a counterexample to the proposal or the missing contribution. This is a general modeling method for design, prediction and control questions. It develops the formulation before a solver or a control algorithm is selected.

The finite examples need elementary sets, inequalities and the meanings of 'there exists' and 'for every'. More demanding cases can require optimization, stochastic processes or control theory. If the answer condition and available information are already correctly formulated, use C.29.2 or the applicable computational method to obtain the result.

### MMP.8:2 - Problem

A mathematical unknown can represent a decision, an unobserved state, an external input or a quantity constrained by other relations. Treating every unknown as a free decision lets the solution change the problem's circumstances to make the requested result possible.

Timing introduces another error. A family of solutions indexed by the true circumstance can be mathematically valid while requiring an observation that the acting system never receives. Separately optimizing every future case then grants foresight that the described method lacks.

The difficulty is to translate the work's choices, information and requirements into a mathematical question with the corresponding dependencies and quantifiers.

### MMP.8:3 - Forces

| Choice | Consequence |
| --- | --- |
| One decision or an adaptive rule | An adaptive rule can use later observations but needs a realizable way to receive and act on them. |
| Possible success or required success | A successful case can support possibility while leaving a guarantee unresolved. |
| Unknown state and random state | An uncertainty set permits several values; probabilities require an additional model. |
| Strong requirement and useful feasibility | A guarantee across an oversized circumstance set can reject useful choices; changing the set changes the claim. |
| Mathematical existence and an obtainable rule | A policy's existence can matter before an affordable construction is known. |

### MMP.8:4 - Solution

Separate choices from circumstances, express the relations that must hold, and state which information each choice may use. Formulate the requested result over those objects, then test the formulation against a small contrasting pair of circumstances. Preserve any useful conditional answer when a stronger requirement is unavailable.

#### MMP.8:4.1 - Name choices, circumstances and consequences

Start from the question in the work. Identify what a participant can change and what is supplied by the subject or environment. Let a denote the choice and w the circumstance. Give both their domains and meanings. A choice can be an arrangement, an input, a rule for later actions or another object the work can construct.

Use the subject relations to connect them to a result. For a deterministic model, a consequence may be written y=f(a,w). An implicit relation R(a,w,y) can retain several possible consequences. Additional unknowns can describe forces, flows, internal states or other quantities jointly constrained by the model. Acausal equations can constrain these quantities without making them free controls.

State what the question requires of the result. If it asks whether every permitted behavior meets a condition, a solver's ability to find one favorable y does not settle it. If the work can select among the permitted consequences, represent the mechanism that gives it that choice. A.3.3.TR supplies the relevant state-change or interaction rule.

#### MMP.8:4.2 - Recover the order and availability of information

Describe what is observed before each decision and what arrives afterward. Express the available observation as h(w) when it is a deterministic description of the circumstance. It may reveal only part of w. For a random or noisy observation, specify its probability law for each admitted w. An unknown fixed w can index a family P_w of observation laws without having a probability distribution itself. A joint law is needed when the question also treats w as random and averages over it. MMP.7 constructs the recording law.

A policy pi selects an action from the information available: `a=pi(h(w))`. Two circumstances with the same h(w) must therefore receive the same action. This uses MATH.2's condition that an answer remains constant on cases identified by a description. Here the observation determines those groups. The information restriction is often called nonanticipativity: the policy does not use distinctions the decision-maker has yet to observe.

For repeated interaction, use the observation history available at each decision. A policy may remember earlier observations or actions. Omitting that memory is a substantive model choice. Global termination is unnecessary when the question concerns a continuing response; specify the response or progress condition that matters under the admitted inputs.

If an earlier action changes what can be observed, make h depend on that action and describe the cost and timing of observation. If action also changes the circumstance distribution or evolution, include that relation. C.28 supplies the causal-use question and the policy's permitted pre-action information; C.28.MR constructs the mechanism replacement. A changed distribution cannot be inferred from a favorable selection of historical cases alone.

#### MMP.8:4.3 - State the required quantifiers and performance criterion

For a deterministic success condition G(a,w), these are different questions:

| Working question | Mathematical statement |
| --- | --- |
| Is there some successful combination? | There exist a and w with G(a,w). |
| Does every circumstance have a successful action, if it were known? | For every w, there exists a with G(a,w). |
| Can one action be selected now that succeeds throughout the admitted circumstances? | There exists a such that, for every w, G(a,w). |
| Can an observation-dependent rule succeed throughout those circumstances? | There exists an allowed policy pi such that, for every w, G(pi(h(w)),w). |

Choose the statement from the work's requirement. The first two can expose possibilities or limits even when the latter two fail. A stronger claim can require a different action or information source.

When the receiving use permits failures with a stated probability, name the event and the randomness over which that probability is calculated. For unknown fixed w and random observation O, the question may require `P_w(failure of pi(O)) <= epsilon` for every admitted w. If w itself is modeled as random and the question concerns performance averaged over circumstances, use the joint law of w and O. An expected cost needs the same choice of what is averaged. Neither a probability nor an objective follows just from listing possible circumstances. Feasibility, expected performance, tail risk and worst-case performance are alternative questions with different consequences. Use the common choice and characterization methods to decide which matters to the work.

Preserve dependence within the circumstance set. Independently combining several ranges can create impossible circumstances and overstate a requirement. Conversely, excluding an inconvenient circumstance changes the range of the conclusion and needs a subject reason or an agreed narrower use.

#### MMP.8:4.4 - Construct or refute a usable choice

For each circumstance w, let A(w) be the actions satisfying the requirement under the modeled relations. For a fixed robust choice, seek an action in the intersection of A(w) over the admitted circumstances. An empty intersection refutes that fixed-choice requirement.

For an observation-dependent choice, group circumstances by the observation they produce. For each obtainable observation o, intersect A(w) over the circumstances with h(w)=o. An action in this intersection works throughout that observationally indistinguishable group. In a finite problem, choosing one such action for each observation constructs a policy. One empty intersection proves that this observation cannot support the required policy.

For a noisy observation and an all-cases guarantee, construct the allowed pairs (w,o) from the observation mechanism's admitted realizations. This relation, rather than a positive probability for each individual report, determines compatibility. For example, if O=w+E with E uniform on [-1,1] and all errors in that closed interval are admitted, the boundary error E=1 remains in an all-cases guarantee despite having probability zero. An almost-sure or specified-probability requirement is a different claim; state that choice.

For a received report o, first check that at least one circumstance is compatible with it. If none is compatible, return the conflict between the report and the observation model under C.16.IR:4.4. A universal statement over an empty set supplies no guarantee for the situation that produced the report. With a nonempty compatible set, intersect A(w) over its members. For a probability-of-success requirement, instead calculate the event under the conditional family or joint law chosen in :4.3; the set of allowed pairs alone supplies no probability weights.

For infinite spaces or long-running interaction, these relations still specify the question, but a usable policy requires the corresponding mathematical and computational construction. A pointwise existence argument does not automatically provide an effective rule. C.29.2 addresses that obtaining work; the present method retains the information restrictions in what it asks the computation to produce.

When several outcomes remain possible for one action and circumstance, apply the required quantifier to those outcomes as well. Derive or inspect a violating outcome when refuting a guarantee. If the missing factor is an unmodeled selection mechanism, obtain it or retain the conditional answer rather than allowing the solver to invent a favorable mechanism.

#### MMP.8:4.5 - Interpret the result and change the working method

Follow the resulting action or policy through one modeled case and a consequential change. Return the consequence to the original requirement. If a planned response depends on a distinction absent from the available observation, revise the observation, defer the decision, choose a more tolerant action or change the stated goal with the responsible party.

Compare these options by what they change and cost. A more informative observation can enlarge the feasible policy set, but it may arrive too late or cost more than a sufficient fixed choice. C.11.DUA supplies that comparison. An infeasible guarantee can still leave a useful bounded, conditional or risk-qualified proposal.

For a working-method change, explain who or what supplies the observation, what result it provides, when it becomes available and what the receiving action does with it. ME supplies the composition and change of those methods. The mathematical policy then describes an obtainable contribution, rather than relying on an unstated observer or decision-maker.

### MMP.8:5 - Archetypal Grounding

#### MMP.8:5.1 - Choose a preload before or after learning an external load

An ideal static arrangement has a downward load w, an adjustable upward preload a and a residual y=w-a. A later use requires `abs(y)<=1/4`. The load is either 1 or 2, and a can be any value from 0 to 2. The relation is a supplied illustrative mechanical model; the pattern's work is to formulate the choice and its information.

If w=1, acceptable choices form `[3/4,5/4]`; if w=2, they form `[7/4,2]` after the actuator limit is applied. Both sets are nonempty, so each known load has a feasible choice. Their intersection is empty. No one preload chosen before distinguishing the loads can meet the requirement for both.

Suppose a reading available before adjustment reports which of the two loads is present. The policy `a=w` then meets the requirement. A reading received only after the preload is locked cannot support that policy at the relevant decision.

Now the tolerance is relaxed to 3/5. The acceptable intervals overlap from 7/5 to 8/5, so `a=3/2` works before any reading. Additional measurement is unnecessary for this revised requirement. The change is in the required result, not the sophistication of the computation.

#### MMP.8:5.2 - Decide which participant gets a scarce resource

Two work requests, L and R, may need the only available resource. Exactly one needs it. Allocation succeeds when the resource goes to that request. The instruction must choose L or R deterministically from one report received before allocation.

With no distinguishing report, there are two constant instructions: always allocate to L or always allocate to R. Each fails in one circumstance. A truthful timely report permits an instruction that follows it and succeeds in both. A report arriving after allocation cannot supply that choice.

Now the timely report is noisy. The observing procedure independently chooses one of two channels with equal probability, then sends its L/R report without naming the channel. The model supplies these conditional reporting probabilities; the remaining probability in each row produces the opposite report:

| Channel | Actual request needing the resource | Probability of a correct report |
| --- | --- | ---: |
| 1 | L | 0.9 |
| 1 | R | 0.5 |
| 2 | L | 0.7 |
| 2 | R | 0.9 |

Use MMP.7 to remove the unrecorded channel by summing over it. For fixed circumstance L, `P(report L)=0.5*0.9+0.5*0.7=0.8`. For fixed R, `P(report R)=0.5*0.5+0.5*0.9=0.7`. No probability for which request actually needs the resource was needed for this construction.

There are four deterministic instructions from one two-valued report:

| Instruction | Success probability in fixed L | Success probability in fixed R |
| --- | ---: | ---: |
| Always allocate to L | 1 | 0 |
| Always allocate to R | 0 | 1 |
| Follow the report | 0.8 | 0.7 |
| Choose opposite to the report | 0.2 | 0.3 |

If the requirement is success probability at least 0.65 in each admitted circumstance, following the report satisfies it. None of these instructions gives a zero-failure guarantee. The conditional laws are sufficient to make both statements while the circumstance remains unknown and fixed.

Change the question to average success in a stream of requests modeled as L with probability 0.95 and R with probability 0.05, retaining the channel procedure. Following the report gives `0.95*0.8+0.05*0.7=0.795`. Always allocating to L gives 0.95; always allocating to R gives 0.05, and choosing opposite to the report gives 0.205. The instruction with greatest average success among the four is now always L. It still fails in fixed R.

Choose the performance requirement from the work's purpose before adopting an instruction. The observing model supplies conditional probabilities; the decision about the work determines whether performance in each circumstance or an average matters.

To retain the zero-failure requirement, the work could obtain a truthful report in time or provide enough resource to serve both requests. Compare the cost of those changes with the consequences of accepting a mistaken allocation, using C.11.DUA. A changed channel, recorded channel identity or permission to randomize the instruction changes the information or choice set; formulate the revised question accordingly.

#### MMP.8:5.3 - Find a strategy, rather than an answer chosen with future knowledge

A program repeatedly receives a bit b and emits a bit a. A requirement asks it to emit the same bit. If receipt precedes emission, the rule `a=b` works on every round. If emission must precede receipt, each possible future bit has a matching answer, but no deterministic rule using only the earlier history can guarantee a match against every admitted next bit.

To see the failure, hold the earlier history fixed. The rule chooses either 0 or 1. Both next input bits are still admitted, including the opposite one. That continuation refutes the guarantee for this history. Inspecting more successful traces cannot remove it.

A changed requirement may ask for success probability under independent fair input bits. Any earlier choice then matches with probability 1/2 in one round, including a randomized earlier choice independent of the next bit. Success in every one of N such rounds has probability 2^(-N). These probabilistic claims use the new input assumption. They do not establish success against every input stream.

This is a continuing computational interaction. The construction determines how each response may depend on incoming information. The same observation-order construction identifies what a distributed team or controller would need to know before acting.

### MMP.8:6 - Bias-Annotation

Optimization tools encourage viewing every variable they can assign as an available choice. Recover the subject meaning of each unknown before interpreting a solution. A second bias is to make robustness the default goal. State the receiving requirement first; a conditional answer or an explicitly accepted risk may be more useful than an infeasible all-circumstances guarantee.

### MMP.8:7 - Conformance Checklist

- Are choices, circumstances and consequences distinguished by what the acting system can actually change?
- Does each choice depend only on information available at its decision time?
- Do the quantifiers express the intended possibility, guarantee, policy or probabilistic question?
- Are dependent circumstances and remaining possible outcomes preserved in the formulation?
- Does a witness, empty intersection, policy or bound have the claimed meaning?
- Does the interpreted result support an action, a changed method or a specific unresolved contribution?

### MMP.8:8 - Common Anti-Patterns and How to Avoid Them

| Failure in this work | Repair |
| --- | --- |
| A solver changes an external load or unknown state to satisfy the goal. | Treat it as a circumstance and apply the required quantifier. |
| A separately optimal action for every future is presented as one available strategy. | Group cases by the information available at the decision; require a common action within each group. |
| An existentially chosen consequence stands in for all allowed behavior. | Retain the behavior relation and test the quantifier required by the goal. |
| A larger uncertainty set is called safer without examining its subject meaning or cost. | Check the joint possible circumstances and choose the requirement for the actual use. |
| Better observation is required after a sufficient common action is already available. | Compare what the additional information can change before commissioning it. |

### MMP.8:9 - Consequences

The formulation prevents computation from supplying unavailable control or foresight. It can expose a useful change to observation, timing or the requirement before optimization begins. It can also be harder to solve than its scenario-wise surrogate; that extra difficulty reflects the question the work actually asked.

### MMP.8:10 - Architectural Rationale

Quantifier order and permitted dependence express different aspects of the working problem. 'For each circumstance there is an action' concerns a family of possible solutions. An executable policy also needs a way to select its action from obtainable information. Grouping indistinguishable circumstances makes that additional condition visible and gives a constructive test for finite cases.

This mathematical formulation can describe physical adjustment, resource allocation or computational interaction. Its source premises and available actions differ across those practices. The method keeps those differences explicit while reusing the same reasoning about choices and information. It complements FPF's continuation and computation methods by constructing the mathematical answer condition they consume.

### MMP.8:11 - SoTA-Echoing

[Boyd and Vandenberghe, Convex Optimization, section 4.1](https://www.stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf), distinguish the feasible set from the objective and transformations of a problem. Adopt that separation in :4.1 and :4.3. The present finite constructions do not require convexity; the book's convex solution guarantees apply only under their conditions.

[Ben-Tal, Goryashko, Guslitzer and Nemirovski, Adjustable robust solutions of uncertain linear programs (2004)](https://doi.org/10.1007/s10107-003-0454-y), develop adjustable decisions alongside choices fixed before uncertainty is revealed. Adapt this distinction into the information-dependent formulation; do not transfer linear-program tractability to unrestricted policies.

[Duchi, Optimization with uncertain data (2018), sections 1 and 6](https://web.stanford.edu/class/ee364b/lectures/robust_notes.pdf), compares uncertainty-set requirements with probabilistic ones and makes choosing the uncertainty set a modeling question. Adopt that choice explicitly; no worst-case objective is imposed by this pattern.

[Vayanos, Georghiou and Yu, Robust Optimization with Decision-Dependent Information Discovery, version 3 (2022)](https://arxiv.org/abs/2004.08490v3), treats actions that affect when uncertainty can be observed. Carry that extension into :4.2 and the return to method design. Its specialized algorithms are further methods, not assumed capabilities of every reader.

The interval, allocation and bit-response examples are constructed demonstrations of the method under their stated assumptions.

### MMP.8:12 - Relations

B.5.FM and C.29 connect the work's question to its mathematical formulation. A.22.CGUS exposes allowed continuations; A.3.3.TR constructs the behavior relation. MMP.7 supplies a missing observation law for probabilistic uses. MATH.2 explains the identification of cases that preserve a requested answer; here grouping by available information determines which actions a policy can distinguish. C.29.2 obtains a computation for the formulated question and C.29.3 examines realization. C.28 governs causal claims when acting changes the represented world. ME uses the result to compose observation, decision and action methods with their needed contributions and timing.

### MMP.8:End

## MMP.9 - Derive a Reduced Evolution Model

> **Type:** Method pattern
> **Status:** Usable, evolving
> **Normativity:** Normative within the stated use

### MMP.9:1 - Problem frame

Use this pattern when a supplied model describes how a state changes, but predicting the quantities you need would be easier with less state, shorter memory or a simpler update. After removing detail, the proposed update still depends on something you removed. You need to derive what can replace that contribution while retaining a useful answer.

Start with the quantity you want to keep and compute its change from the supplied model. Circle the part that cannot be obtained from the proposed smaller state. For an average, this may be the variance of the underlying values. For one observed component, it may be the effect of unobserved components. That expression identifies the construction needed next.

The result can be a smaller evolution law, a history-dependent rule, an approximation with a stated error, or bounds sufficient for the question. Keep the initial information, inputs and time range on which it depends. A model that is already affordable and sufficient can be used directly. If the original change law is missing, recover or construct it in the subject practice before using this reduction method.

You need the mathematics used by the supplied law: substitution and recurrence for discrete changes; differentiation and integration for differential equations; expectations when reducing a probability distribution. A mathematical collaborator may perform those operations from your stated question and model. This is reduction within mathematical modeling. A.3.3.PI supplies the general test of which information a prediction needs; C.29.1 supplies the comparison that transfers the reduced result back to the source question.

### MMP.9:2 - Problem

A description can retain today's quantity while losing what determines tomorrow's. Differentiating a mean can introduce higher moments. Solving for an unobserved component can make its past influence explicit. Dropping a quickly decaying component can retain a lasting change it caused before decaying.

The missing contribution is often called an **unclosed term**: the proposed retained state does not determine it. A **closure** supplies a way to obtain or approximate that contribution from the information the reduced model carries. Its choice changes the resulting evolution.

Finding the unclosed term locates the difficulty. The remaining work is to derive a usable replacement and determine what that replacement permits the model to answer.

### MMP.9:3 - Forces

| Choice | Consequence for the construction |
| --- | --- |
| Smaller state and longer memory | Eliminating coordinates can replace present-state work with a history calculation. |
| Detailed trajectory and selected result | A bound on one output can be cheaper than a replacement for the whole trajectory. |
| Additional moments and finite closure | Deriving another moment can expose yet another missing moment. |
| Short-lived component and lasting effect | A small or fast component can make a consequential accumulated contribution. |
| Fit to supplied trajectories and use inside a new evolution | Once the replacement supplies the next state, its errors can change the states it later receives. |
| Several adequate replacements and available effort | An existing bound or larger model can cost less than developing a new closure. |

### MMP.9:4 - Solution

**Choose the retained result → derive its change → expose the unclosed contribution → construct a replacement or bound → use it over the required horizon → revise the part that changes the answer.**

The work may end at a useful bound. It may also show that the smaller description would cost more than continuing with the source model.

#### MMP.9:4.1 - Express the retained result and its change

Name the source state z, its initial possibilities and the admitted inputs u. Specify the answer and horizon: a quantity at time T, a threshold crossing, a response to an input, or a distributional feature. Construct the retained description x=r(z) from those needs. A.3.3.PI:4.1-4.2 tests whether merged source states can still answer that question; use an already sufficient result from that test.

For a discrete source update z_next=F(z,u), substitute it into the retained description:

`x_next = r(F(z,u)).`

For a differentiable r and a differential law z_dot=F(z,u), the chain rule gives:

`x_dot = Dr(z) F(z,u).`

Dr is the derivative of r. If r also depends explicitly on time, include its time derivative. A discontinuous readout or event needs its own change relation rather than this differentiable formula. A.3.3.TR supplies composition of the relevant changes.

Rewrite the result using x, the admitted inputs and whatever other information the smaller model proposes to carry. The part still depending on discarded quantities is the unclosed contribution. One convenient decomposition is `x_dot=f0(x,u)+c(z,u)`, where f0 is the part you will compute directly and c is the remaining contribution. Another decomposition can be useful; what matters is the complete retained law and what information obtains each term.

If every term is obtainable from the retained information, construct the closed update through A.3.3.PI and compare it through C.29.1. Continue here when the replacement itself still needs construction.

#### MMP.9:4.2 - Derive the discarded contribution before approximating it

Try to express the discarded variables through their own evolution, initial conditions and the retained history. In a discrete law, iterate the discarded update and substitute each earlier term until the dependence has a usable form. In a differential law, solve or integrate the discarded equation under the supplied retained history, then substitute the result into the retained equation.

For constant compatible matrices and supplied initial values, consider:

`x_dot=A*x+B*y`, `y_dot=C*x+D*y`.

Solving the second equation while treating x(s) as its input gives:

`y(t)=exp(D*t)*y0 + integral_0^t exp(D*(t-s))*C*x(s) ds`.

Substitution gives the retained law:

`x_dot(t)=A*x(t)+B*exp(D*t)*y0 + integral_0^t B*exp(D*(t-s))*C*x(s) ds`.

The first added term carries the discarded initial condition. The integral carries the past influence of x through y. With a forcing term in the discarded equation, its propagated contribution also appears in the integral. These terms identify what a proposed memory approximation would replace. Unknown y0 remains an initial uncertainty; it cannot be set to zero solely because y is being removed.

Look for a less costly way to compute the derived expression. Equal decay modes can be combined; a sum of exponentials can be updated through a few auxiliary variables. For example, `v(t)=integral_0^t exp(-lambda*(t-s))*x(s) ds` satisfies `v_dot=x-lambda*v`, v(0)=0. This replaces storage of the whole history with an evolving value. Carry a nonzero initial contribution separately or incorporate its matching initial condition. Count the required auxiliary values and update work before claiming a computational saving.

For nonlinear discarded dynamics the same elimination question remains, but the response to retained history may require solving a nonlinear problem. Use the derived dependence to select an approximation, retained variable or bound; an implicit formula that still requires the original computation has not yet supplied a cheaper model.

#### MMP.9:4.3 - Choose and construct a useful replacement

Use the expression just derived to decide which information or calculation earns its cost.

**Retain a quantity that obtains the missing contribution.** If c depends on a small additional observable v, derive v's update from the source law and repeat the closure test for the pair (x,v). This operation can reveal a useful finite system or a growing hierarchy. For members obeying `Z_dot=-Z^2`, the mean m has `m_dot=-mean(Z^2)`. Retaining `q=mean(Z^2)` gives `q_dot=-2*mean(Z^3)`. The new equation exposes the next assumption needed; adding q alone does not finish the closure.

**Compute the effect through memory.** Use the history expression from :4.2. To truncate old history, bound its omitted contribution for the admitted histories. To replace the memory kernel by a simpler one, bound or estimate the resulting difference on those histories, then propagate that difference through the retained evolution. A slowly decaying kernel can make distant history consequential. An auxiliary-state representation can be cheaper than truncation when a few modes express that kernel.

**Bound the requested output.** If the use asks for a threshold or interval, derive bounds directly from the source law and available initial information. For a population, solve or bound the member response as a function of its initial value, then average using known ranges or moments. Monotonicity, convexity or conservation can give a bound without choosing a complete distribution. The nonlinear example in :5.2 constructs such bounds. Use C.29.1:4.5 to turn them into the corresponding decision, or to expose the still-unresolved range.

**Approximate a contribution whose accumulated effect is small.** Identify the parameter and the class over which smallness is claimed: initial values, inputs, horizon and required error. Derive or bound the contribution integrated over that horizon. A small coefficient can multiply a large hidden value, and a fast transient can shift the later state. If a transient only matters near the start, retain its effect in an adjusted initial value and state when the later approximation begins. :5.3 shows both constructions.

A learned closure is another possible approximation to the missing contribution. Specify what its inputs contain and how its output enters the retained update. Pairs of retained inputs and source contributions can support fitting, but different hidden states can give different contributions at the same retained input. A fitted conditional mean then answers a distribution-dependent question; it is not an all-cases replacement of those contributions. When probability is needed, MMP.7 helps construct the law of the sampled or recorded training cases. Use the resulting closure at its intended inputs and horizon before drawing the corresponding predictive conclusion.

Compare the candidates through the existing characterization and choice methods: the required output or bound, obtaining cost, initial information and conditions. There is no need to develop every alternative. C.11.DUA helps choose whether more derivation, data or computation can change the decision.

#### MMP.9:4.4 - Evaluate the replacement inside the retained evolution

Write the model that will actually be used, including its initial values, any auxiliary variables, input rule and observation interpretation. Construct the requested output from that model. Substituting the closure into known source trajectories tests a different computation from letting it generate successive retained states.

Compare the retained source result and the reduced result for the same admitted initial case and input. For an identity, use the derivation to establish the covered equality. For an approximation, propagate the discrepancy to the requested output and horizon through C.29.1:4.5. A numerical scheme adds its own approximation; include it when it can change the answer. A.3.3.PI:4.5 supplies the repeated-use and changed-condition questions.

For a probabilistic model, choose the distributional feature the work needs. Agreement of a mean can coexist with different variance, correlations or event probabilities. A further observable is worth checking when it can change the planned use. State which result the comparison supports rather than extending one fitted statistic to the whole model.

When inputs are chosen from observations, retain the information the choice rule uses. If reduction removes that information, formulate the revised choice under MMP.8 before claiming that the same intervention or control method remains available. A changed intervention also requires the corresponding source law or mechanism under C.28.MR.

#### MMP.9:4.5 - Return the result and revise the construction when needed

Return the reduced law, sufficient bound or located obstacle with the assumptions that affect its use. An existing derivation and calculation can carry this information. Explain which discarded contribution was replaced, how to initialize and run the replacement, and which question it answers.

If a bound settles the working question, use it. If the result is too weak, locate why: uncertain initial influence, unresolved higher moment, long memory, error amplification, or information unavailable to an action. Improve that contribution or retain more of the source model. A mathematical construction can also show that the proposed simplification offers no saving.

Reopen the affected construction when the source law, initial class, inputs, observation, horizon or required output changes. Keep conclusions whose conditions still hold. In a model of a working method, ME can use the comparison to design a different method or representation; the actual work must still provide the quantities and relations assumed in the model.

### MMP.9:5 - Archetypal Grounding

#### MMP.9:5.1 - Replace many response components by two evolving quantities

Suppose a dimensionless model has an observed x and n hidden response components:

`x_dot=-x+sum_i y_i+u(t)`, `y_i_dot=c_i*x-2*y_i`,

where the nonnegative c_i sum to one. Initial values and a prescribed input u(t) are supplied. The question asks for x over a finite horizon; each y_i separately is irrelevant to that result.

Retaining x alone leaves the unclosed contribution sum_i y_i. Solve each hidden equation and sum:

`sum_i y_i(t)=exp(-2*t)*sum_i y_i(0)+integral_0^t exp(-2*(t-s))*x(s) ds`.

All hidden contributions have the same decay kernel. Define v=sum_i y_i. Differentiating the sum gives the two-variable model:

`x_dot=-x+v+u(t)`, `v_dot=x-2*v`, `v(0)=sum_i y_i(0)`.

The derived equations and initial sum preserve x for every supplied input for which these linear equations have their solution. For n>1 this uses two evolving quantities instead of n+1. The required hidden initial information is their sum. Arbitrarily setting v(0)=0 would already change x_dot(0) when the actual sum is nonzero.

The initial sum requires n terms once. Each subsequent evaluation of the reduced right-hand side uses x, v and u(t); it no longer recomputes n component contributions. This saves repeated arithmetic when those components would otherwise be advanced separately.

Now one component has decay rate 3 instead of 2. Summing produces `v_dot=x-2*v-y_1`; the old two-variable model has lost a contribution. Retain y_1 separately and update it by `y_1_dot=c_1*x-3*y_1`, or separate the two decay groups. The change determines which added state is needed. The same grouping can combine any components that share their response kernel; different kernels remain distinct until another justified approximation combines them.

#### MMP.9:5.2 - Answer about a nonlinear population without a closed mean equation

A finite population has nonnegative member values X_i with `X_i_dot=-X_i^2`. The available initial information is 0<=X_i(0)<=M and mean m0. The requested output is the mean m(t).

Differentiating the mean gives:

`m_dot=-mean(X_i^2)=-m^2-Var(X_i)`.

Replacing this by m_dot=-m^2 sets the variance contribution to zero. Populations with the same mean can have different variance, so first ask whether a bound already answers the question.

Each member has `X_i(t)=X_i(0)/(1+t*X_i(0))` for t>=0. Since X_i(0)<=M, averaging gives the lower bound `m0/(1+M*t)`. The response `a/(1+t*a)` is concave for nonnegative a and t>=0; the mean of the responses is at most the response of the mean. Thus:

`m0/(1+M*t) <= m(t) <= m0/(1+m0*t)`.

With M=2, m0=1 and t=1, the mean lies between 1/3 and 1/2. A requirement m(1)<=0.55 is established without a variance model or a complete initial distribution.

Change the requirement to m(1)<=0.4. A population whose members all start at 1 has m(1)=1/2. An equally divided population starting at 0 and 2 has m(1)=1/3. Both fit the supplied initial information, so it cannot settle the changed requirement. Information about the initial population or a different acceptable requirement would change the next move. Treating the zero-variance closure as the whole population would conceal this distinction.

#### MMP.9:5.3 - Decide whether a fast transient can be omitted

For a dimensionless model with epsilon>0,

`x_dot=y`, `epsilon*y_dot=-y`,

the solutions for t>=0 are `y(t)=y0*exp(-t/epsilon)` and `x(t)=x0+epsilon*y0*(1-exp(-t/epsilon))`.

Suppose the admitted initial values satisfy abs(y0)<=Y. Replacing the model by constant x0 gives an error at most epsilon*Y for every t>=0. With epsilon=0.01 and Y=1, that is 0.01. It can meet a tolerance 0.02 while failing to establish tolerance 0.001. The coefficient alone is insufficient if the initial class changes: y0=1/epsilon leaves a later change approaching one.

When y0 is known and the use concerns only later times, a different approximation is constant `x0+epsilon*y0`. Its error is at most `epsilon*Y*exp(-t/epsilon)`. For tolerance `0<eta<epsilon*Y`, it meets that tolerance at all times starting from `t_start=epsilon*log(epsilon*Y/eta)`. With eta=0.001 in the preceding case, t_start is about 0.0231. The adjusted initial value has retained the transient's later effect; it does not reproduce the initial interval.

If y0 is unknown, the adjusted value is also unknown. Its stated range can still yield a useful interval for x. The choice between an early transient calculation, a later approximation and a bound follows the requested result and available initial information.

### MMP.9:6 - Bias-Annotation

Compact equations can conceal transferred effort. Removing variables may require a history integral, extra initial information or an expensive closure. Compare the work needed to obtain the requested result. A familiar equilibrium substitution or learned fit is a candidate construction whose lost contribution must remain visible in that comparison.

### MMP.9:7 - Conformance Checklist

- Can the retained quantity's change be derived from the supplied law, with its initial and input conditions?
- Which contribution is unavailable from the proposed retained information, and how does the replacement obtain, approximate or bound it?
- Does an added variable have its own usable update and initialization? If a hierarchy remains, where is the closing assumption?
- For a memory or small-parameter approximation, what bounds the omitted effect on the requested output over the stated horizon?
- Is the comparison made in the model's intended repeated use, with the relevant numerical and observation conditions?
- Does the resulting law or bound settle the working question? If not, which changed contribution could do so at worthwhile cost?

### MMP.9:8 - Common Anti-Patterns and How to Avoid Them

| Observed difficulty in the construction | Repair |
| --- | --- |
| Replacing the mean of a nonlinear response by the response at the mean loses heterogeneity. | Derive the missing moment term, then retain, model or bound its effect; :5.2 may already settle the output question. |
| Hidden state is eliminated together with its initial effect. | Carry the initial-condition term in the memory formula or initialize the corresponding auxiliary value. |
| A small coefficient is used as the entire error argument. | Bound the multiplied state, accumulated contribution and admitted initial class, as in :5.3. |
| A closure is judged only on inputs from the source trajectory. | Insert it into the retained evolution and compare the requested result at its intended horizon. |
| Adding a moment is presented as completing a model although its equation needs another moment. | Continue the derivation until a usable closure or sufficient bound is obtained; otherwise retain the unresolved contribution. |

### MMP.9:9 - Consequences

A reduced model can expose which information determines the answer and make repeated calculation cheaper. Bounds can support a decision before a full reduced trajectory is available. Derivation also identifies a reusable limitation: which initial conditions, inputs or new questions require restoring discarded content.

The cost can move into initialization, memory, closure construction or verification at the required horizon. Where that cost exceeds using the source model, the larger account remains a useful option.

### MMP.9:10 - Architectural Rationale

Reduction is organized around the requested result and the source law's unclosed contribution. This makes the choice between retained state, memory, approximation and bounds depend on what each construction obtains. Beginning with one favored approximation would select what to discard before establishing its effect.

A.3.3.PI supplies the question-relative information test. This method develops the subsequent mathematical construction of a replacement contribution. C.29.1 supplies the common exact-or-bounded transfer and error propagation; those rules also apply to constructions outside model reduction.

Linear response, nonlinear aggregation and fast transients require different constructions. A new source law requires deriving its own discarded contribution; it need not resemble one of these examples. When the deriving operation itself requires a further subject method, retain that mathematical dependency rather than presenting a technique's name as an already obtained closure.

### MMP.9:11 - SoTA-Echoing

The practice question is how to replace unresolved dynamics economically while retaining the needed result. **Adopt** construction from the source law and evaluation within the reduced evolution, including memory, initial information and question-relative outputs. A serious alternative fits an instantaneous missing term on source trajectories and judges primarily that fit. It can be cheaper and adequate for a limited use, but it can miss errors generated when the closure supplies its own future inputs.

[Sanderse, Stinis, Maulik and Ahmed, Scientific machine learning for closure models in multiscale problems, version 2 (2024), sections 2.1-2.2, 3.2 and 7.1](https://arxiv.org/html/2403.02913v2), is a comparative synthesis of closure constructions. It distinguishes an unclosed term from its replacement, and fitting the term from testing the evolving reduced model. **Adapt** these distinctions in :4.1-4.4. Its memory discussion supports preserving initial and historical effects during elimination. An exact elimination identity still needs an affordable way of obtaining its result; :4.2 makes that cost question explicit. The linear elimination, population bounds and transient estimates above are elementary derivations developed here, not empirical validation claims.

[Freitas, Um, Desbrun, Buzzicotti and Biferale, A posteriori closure of turbulence models: are symmetries preserved? (2026 preprint), sections 3-5](https://www.geometry.caltech.edu/pubs/FUDBB26.pdf), provides a current countercase. A learned shell-model closure reproduces selected statistics while missing other correlations and scale-invariance properties. **Adopt** its consequence in :4.4: select the observables that the receiving use needs instead of extending fit of one statistic to all requested behavior. Missing memory is a proposed explanation in that case; it does not establish a universal cause or require every reduced model to carry the same memory construction.

The selected method spends effort on the omitted contribution and the use it can change; it need not reproduce every property of the detailed model. A sufficient analytic bound can be cheaper than training or testing another closure. Reopen the comparison when changed inputs, initial conditions, horizon or requested observables expose a consequential error, or when another construction obtains the same needed result at lower cost.

### MMP.9:12 - Relations

- **A.3.3.TR and A.3.3.PI:** compose source changes, determine the information needed for the future question and update the retained account. MMP.9 constructs a remaining closure or bound after those operations expose the gap.
- **C.29.1 and MATH.2:** compare the retained construction with the source and determine which answers survive identification; use their exact or bounded transfer where applicable.
- **MMP.7 and MMP.8:** construct observation laws and information-limited choices when a learned or controlled reduced model uses them. Their conditions determine which data law or action rule is actually being compared.
- **C.28.MR and B.5.MPC.R:** reconsider the relevant mechanism or connected accounts when an intervention or model change alters the source law.
- **C.11.DUA:** decide whether further derivation, observation or comparison is worth its cost for the receiving decision.
- **E.22 and E.23:** frame the question for evaluating a candidate, then organize repeated improvement under that evaluation when needed.
- **EXD and C.2.8:** EXD develops an explanation for the recipient's question; C.2.8 compares what structure that recipient can recover from its expression under stated conditions. Prediction and explanation can require different retained results.
- **ME:** use the mathematical result to construct or change the working method it describes.

### MMP.9:End
