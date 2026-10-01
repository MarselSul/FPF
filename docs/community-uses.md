# Uses and community projects

Reviewed 2 October 2026.

People apply FPF to difficult engineering questions and build tools that make its patterns easier to consult. This selection brings together a practitioner's account, reusable agent integrations, a versioned distribution, and experimental extensions.

Each entry explains the contribution and links to English-language primary material. The evidence labels distinguish reported application from published implementation and prototype work. Inclusion acknowledges a contribution; it does not imply endorsement or certification. These independent projects belong to the wider FPF ecosystem. They are separate from the project's own FPF Library publications. This page reviews public artifacts; the integrations were not installed or executed.

## Evidence labels

- **Reported use:** A participant describes applying FPF to a concrete task, with an account or resulting artifact
- **Published integration:** Software, a skill, or a service with inspectable implementation artifacts; artifacts reviewed here, software not executed
- **Prototype:** A draft extension or bounded experiment whose intended contribution can be inspected

These describe the available evidence, not a quality ranking.

## A reported application

<a id="legacy-monolith"></a>

### Choosing what to fix in a legacy monolith

**Category:** Engineering decisions\
**Evidence:** Reported use\
**By:** Ivan Zakutnii

Ivan Zakutnii used an FPF-based Claude Code workflow to compare three responses to a legacy monolith: repair tests and CI, undertake a DDD refactor, or strengthen static analysis. Team constraints ruled out the refactor; failing tests and more than 350 analyzer findings supported a combined testing-and-linting approach. The session produced a documented decision and a Jira story. His account makes the practical contribution visible: alternatives, constraints, and supporting checks became a reviewable work item. The tool was then called Quint Code and is now maintained as Haft.

**Sources:** [First-person case, 13 December 2025](https://ivanzakutnii.com/en/blog/crucible-code-for-thinkers/) · [Current Haft project](https://github.com/m0n0x41d/haft)

**Reading note:** The author reports a 25-minute session testing a direction already under consideration. The documented output is the decision and work item.

## Tools and skills

<a id="vibevm"></a>

### VibeVM

**Category:** Packaging and distribution\
**Evidence:** Published integration\
**By:** Oleg Chirukhin and the VibeVM project

VibeVM packages FPF as an installable, versioned dependency through `vibe install ai.lev/fpf`. Its packages cover Core, DPF Suites and independent domain frameworks. Compact startup indexes lead agents to individual contracts, checklists, and deeper source sections through `spec://` addresses. A lookup skill specifies selective, contract-first reading and pattern citations. The contribution is a concrete distribution and navigation layer for a large reasoning corpus, with an upstream revision recorded for each package. The verified edition is a 29 September 2026 snapshot.

**Sources:** [FPF package](https://github.com/vibespecs/ai.lev.fpf) · [Registry](https://raw.githubusercontent.com/vibespecs/index/main/primary.jsonl) · [Pattern corpus](https://raw.githubusercontent.com/vibespecs/ai.lev.fpf-common/main/vibevm/vibespecs/pub/corpus.json) · [Lookup skill](https://raw.githubusercontent.com/vibespecs/ai.lev.fpf-common/main/vibevm/vibespecs/skills/fpf-lookup/SKILL.md)

**Edition note:** Package version 2026.929.0 pins upstream `d131d30a44e78523e78da9d22aefd83e59f5e4a4`. This is not a claim of continuous synchronization. Installation and agent behavior were not tested in this review.

<a id="fpf-agent"></a>

### FPF-agent

**Category:** Agent integration and reusable analysis\
**Evidence:** Published integration\
**By:** Vitaly Pokrovskiy

FPF-agent provides a task-oriented assistant for Claude Code and Codex. Five specialized agents and ten recurring task routes combine selective source loading with semantic-search fallback. The integration applies FPF internally while returning results in ordinary working language: responsibility maps, contract breakdowns, comparison criteria, and evidence gaps. Rebuilding scripts, bilingual documentation, smoke tests, and a small model evaluation accompany the implementation. Its useful contribution is a practical layer between a large specification and recurring analytical tasks, with concrete output forms a person can review and reuse.

**Sources:** [Current project](https://github.com/pokrovskiyv/FPF-agent) · [English architecture overview](https://github.com/pokrovskiyv/FPF-agent/blob/75a2702900de72e2dfe882a1b05184a5a9f4886d/docs/wiki/en/architecture/overview.md) · [English output contract](https://github.com/pokrovskiyv/FPF-agent/blob/75a2702900de72e2dfe882a1b05184a5a9f4886d/docs/wiki/en/architecture/plain-language-contract.md)

**Reading note:** Project-use reports and the limited structural-task evaluation come from the maintainer. The inspectable contribution is the integration and its output forms.

<a id="fpf-reference"></a>

### FPF Reference

**Category:** Browser reference and MCP integration\
**Evidence:** Published integration\
**By:** venikman

FPF Reference makes the specification available through the fpf.sh website, a local CLI, and a hosted MCP endpoint. Its implementation compiles an FPF snapshot into an index of patterns, routes, relations, and anchors. People and agents can retrieve an exact pattern or assemble a bounded work packet rather than repeatedly supplying the whole specification. The useful contribution is a shared, addressable reference surface across reading and agent workflows. Published source hashes and commit identifiers also let a user inspect which edition a retrieved passage comes from.

**Sources:** [Reference website](https://fpf.sh/) · [MCP interface and setup](https://mcp.fpf.sh/) · [Implementation](https://github.com/venikman/fpf-memory) · [Publication manifest](https://github.com/venikman/fpf-memory/blob/main/published/current/manifest.json)

**Edition note:** The inspected publication identifies the 8 September 2026 upstream edition. Current parity with upstream was not established. The current MCP name is `fpf_reference`; the project documents the legacy `fpf_memory` endpoint as blocked and provides a migration route.

<a id="codealive"></a>

### CodeAlive FPF problem solving skill

**Category:** Reusable agent skill\
**Evidence:** Published integration\
**By:** CodeAlive AI

CodeAlive's FPF problem-solving skill gives coding agents a task-oriented route into the specification. Questions about comparing alternatives, evidence, or responsibility lead to relevant sections; the agent reads an index and then the narrowest useful source file. A Python splitter generates the source hierarchy, and a maintenance guide explains how to update navigation when FPF changes. The skill now belongs to CodeAlive's broader ai-driven-development collection and also appears in its CEO AI OS. It demonstrates how selective source reading can fit into an existing collection of work skills.

**Sources:** [Current skill](https://github.com/CodeAlive-AI/ai-driven-development/tree/main/skills/fpf-problem-solving) · [Skill instructions](https://github.com/CodeAlive-AI/ai-driven-development/blob/main/skills/fpf-problem-solving/SKILL.md) · [Source splitter](https://github.com/CodeAlive-AI/ai-driven-development/blob/main/skills/fpf-problem-solving/scripts/split_spec.py) · [CEO AI OS](https://github.com/CodeAlive-AI/ceo-ai-os)

**Use note:** Follow the current collection and its update guide. The inspected collection README records upstream commit `b112256466bff620bbee2b72ab8cfe4ad976e60d`. Packaging terms do not replace the terms applying to the FPF source text.

<a id="knowledge-graph"></a>

### FPF Knowledge Graph Toolkit

**Category:** Knowledge graph and portable agent skill\
**Evidence:** Published integration\
**By:** Anatoly Maslennikov

The FPF Knowledge Graph Toolkit converts the specification into linked, Obsidian-ready notes with pattern, relation, and term indexes. A portable English/Russian skill supports tasks such as framing a problem, challenging a design, comparing options, and auditing alignment. Its distinctive contribution is traceability: a revision-bound source package, source-line metadata, conversion tools, and validation accompany the transformed material. A published development-branch review also shows the author using the skill to assess its own design. The toolkit offers people and agents a shared navigation structure while retaining a route back to the source.

**Sources:** [Project and English README](https://github.com/anatoly-m-maslennikov/levenchuk-fpf-knowledge-graph-toolkit) · [Reviewed README snapshot](https://github.com/anatoly-m-maslennikov/levenchuk-fpf-knowledge-graph-toolkit/blob/a80e23e96d82b91545b4a1663ddfdcd1fbd0acfb/Readme.md) · [Development-branch self-review](https://github.com/anatoly-m-maslennikov/levenchuk-fpf-knowledge-graph-toolkit/blob/d6cbc4966c48ba40478771032d33ac26acfc8c2e/fpf-reports/20260828T112658Z-fpf-composition-review-current-fpf-skill-design.md)

**Edition note:** The inspected toolkit pins FPF to 25 August 2026. The self-review is an author-produced usage artifact on a development branch; test reports were not independently reproduced.

## Domain extensions and experiments

<a id="backend-dpf"></a>

### Backend Programming Principle Framework

**Category:** Third-party Domain Principle Framework\
**Evidence:** Prototype\
**By:** Ilyas Landikov

The Backend Programming Principle Framework is a third-party DPF draft for recurring backend questions: service promises, state ownership, idempotent effects, failures and retries, and observability as evidence. The inspected draft's five domain patterns translate those questions into recognition guidance, worked examples, and routes to governing FPF Core patterns. The draft also exposes its source traditions and architecture decisions, so readers can inspect how the domain extension was constructed. Its distinctive contribution is domain-specific reasoning guidance for backend engineers, rather than another interface for retrieving the original specification.

**Sources:** [Draft branch](https://github.com/ilandikov/FPF/blob/feat/dpf-backend/DPF-Backend-Programming.md) · [Reviewed draft snapshot](https://github.com/ilandikov/FPF/blob/728e6b5b4f9dc99360ad8ab4a32869e6b01ffb23/DPF-Backend-Programming.md)

**Status note:** Edition BPF-0.1-draft is explicitly a draft seed; the short name BPF is provisional. It is an extension artifact, not evidence of a deployed backend or inclusion in the official FPF Library.

<a id="thinking-map"></a>

### FPF Agentic Thinking Map

**Category:** Runtime adaptation\
**Evidence:** Prototype\
**By:** Consolidare Continuum

FPF Agentic Thinking Map turns selected FPF ideas into a small Python runtime for bounded agent workflows. It keeps workflow state, evidence freshness, transition checks, and authorization outside the model's conversational memory. An agent proposes a move; ordinary code checks whether that transition is allowed. Public examples and experiments explore compact state slices and authorization failures, including a discovered receipt-expiry bug and its regression test. Its contribution is an inspectable attempt to make selected boundaries executable, with explicit adoption limits, rather than rely entirely on a model remembering instructions.

**Sources:** [Implementation and English documentation](https://github.com/Consolidare-Continuum/fpf-agentic-thinking-map) · [Adoption boundaries](https://github.com/Consolidare-Continuum/fpf-agentic-thinking-map/blob/main/docs/deep/SOURCES.md) · [Authorization experiment](https://github.com/Consolidare-Continuum/fpf-agentic-thinking-map/blob/main/docs/deep/IGNITION_LOCK_WIND_TUNNEL.md)

**Reading note:** The experiments are author-run and configuration-dependent. The project explicitly adapts selected ideas; it is not a conformance implementation of all FPF patterns.

## Suggest a use or project

[Open a GitHub issue](https://github.com/ailev/FPF/issues/new?title=Community%20use%20or%20project) or propose a pull request to this page. Describe the problem, what you did, FPF's specific contribution, the resulting artifact or experience, and important limits. Include an English-language primary account or substantive documentation that readers can examine directly. Qualitative reports, useful drafts and unsuccessful experiments can qualify.

The selection requires an explicit connection to this FPF and a distinct, inspectable contribution. A citation, star count or fork alone is insufficient. Preserve authorship, licensing and the boundary between the source framework and an adaptation.

## Maintaining this selection

Each entry records its author, category, evidence type, primary sources and any relevant source edition or compatibility limit. The review date above applies to this selection. Review an entry when a source moves, a project is archived, an interface changes or its FPF basis changes materially. An older source edition can still demonstrate a useful mechanism; it does not establish compatibility with current FPF.

Update this Markdown source through the normal FPF publication procedure. The website and its highlighted cards derive from the published edition; adding an example requires no change to an assumed number of projects. The README provides a short entry route to this selection.
