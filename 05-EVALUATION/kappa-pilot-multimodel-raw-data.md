# Multi-model Kappa Pilot — Raw Outputs (GPT-5.4 + Gemini-3)

> Verbatim per-principle grades from two non-Claude raters scoring the same 10 SKILL.md files at 25-principle scale, both with `pragmatic-practitioner` persona. The GPT-5.4 section was generated 2026-04-26 (server-side JSON Schema enforcement); the Gemini-3 section was added later the same day (prompt-engineered JSON + client-side validation).

**Aggregated analysis:** [`kappa-pilot-multimodel.md`](./kappa-pilot-multimodel.md)
**v0.2 Claude baseline:** [`kappa-pilot.md`](./kappa-pilot.md) (Claude-pragmatic / strict / charitable)

This file has two sections: **GPT-5.4 outputs** (below) and **Gemini-3-pro-preview outputs** (further below).

---

# GPT-5.4 raw outputs

**Date:** 2026-04-26
**Method:** `codex exec --output-schema rubric-schema.json -m gpt-5.4 -c model_reasoning_effort="high"` per skill, sequential.
**Total wall-clock:** 17 min 12 sec (mean 110 s/call). Schema-violation retries: 0.

---

## 01-obra-tdd

**Archetype:** Procedural — The skill is an execution workflow, not a passive reference: it defines an ordered `RED -> GREEN -> REFACTOR` process, mandatory verification points, and restart conditions. It is narrowly procedural even though it also contains explanatory material and examples.

**Aggregate grade:** B- — This skill is strong on practical TDD enforcement, verification gates, and behavioral discipline, so it would work decently in production as an execution aid. It falls well short on the newer PaaP process-contract features such as durable state, progress reporting, self-observation, spawn-awareness, and formal output/composition structure.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A- | high | The YAML description routes clearly to implementation work and establishes timing: use it before writing implementation code. The anti-triggers are present in the body rather than the description field itself, so rout... |
| 2 | Route before work | B | medium | The skill does front-load usage guidance and exceptions before the main loop, which is good enough in practice. It does not define an explicit routing phase with STOP conditions and path selection as a first-class step. |
| 3 | Modes | N/A | high | This is a linear TDD discipline with one dominant execution path. The examples vary by use case, but the workflow itself does not branch into distinct named modes. |
| 4 | State | C+ | medium | There is no explicit durable state or resume protocol, which is a real gap for long-running feature work. Pragmatically, the repo's tests and code act as implicit working state, so this is weak rather than catastrophic. |
| 5 | Parallel | N/A | high | The TDD loop is intentionally sequential: you write one failing test, make it pass, then refactor. There are no independent subtasks that should be launched in parallel. |
| 6 | Personas/voice | A | high | The skill has real behavioral discipline rather than generic expertise framing. The `Iron Law`, anti-rationalization language, and restart commands create a strong operating persona that would hold up in practice. |
| 7 | Files = bus | C | medium | The workflow relies on repo artifacts implicitly, but it does not explicitly use files as handoff contracts between phases. For a small skill that can still work, but it misses the stronger process discipline this pri... |
| 8 | Synthesis | C | low | There is no explicit synthesis phase with merge rules or conflict handling. That omission is understandable because the process is mostly single-threaded, but the principle is not really implemented. |
| 9 | Human gate | B- | medium | The skill identifies genuine escalation points for human judgment, especially exceptions and unclear testing situations. It does not express these as explicit wait-state checkpoints embedded in the main workflow. |
| 10 | Exit = question | B | medium | Several phase exits are effectively binary even if not written as formal questions: test fails correctly, test passes, other tests still pass. The structure is operationally clear, but the exit criteria are phrased as... |
| 11 | Output spec | C+ | medium | The skill is clear about what good tests and good verification look like, but it never specifies a final deliverable format for the agent's output. In practice this still guides behavior, yet the output contract is lo... |
| 12 | Gates = 3 parts | A | high | The RED and GREEN verification gates each include a check, concrete failure conditions, and a recovery path. This is one of the strongest parts of the skill and would work reliably in production. |
| 13 | External storage | N/A | high | The skill is compact enough to live comfortably in one file. It does not cross the size or complexity threshold where externalized prompt assets become necessary. |
| 14 | Context scope | A | high | Scope control is explicit and practical: it says when to use the skill, what exceptions exist, and what rationalizations do not qualify. That gives the agent a clear operating boundary. |
| 15 | Progress | D | high | The skill has checkpoints, but it does not instruct the agent to emit progress updates or track meaningful status metrics during execution. That is a real collaboration gap for longer runs. |
| 16 | Errors | B+ | medium | Error handling is practical and specific in the verification steps and troubleshooting sections. It falls short of a clean error-to-action table for the whole skill, but it still gives the agent concrete responses to ... |
| 17 | Autonomy | A- | high | The default behavior is decisive: use TDD for essentially all implementation work unless a narrow exception applies. Human interruption is reserved for genuine exceptions or uncertainty, which is the right practical b... |
| 18 | Path resolution | D | high | The skill references an external document without any resolution strategy or fallback. That is fragile if the file is absent or differently named in another repo. |
| 19 | Composition | B+ | low | There is no formal composed-skills metadata, but the skill also does not really orchestrate other skills as dependencies. Pragmatically this avoids composition failure, though it does not implement the v0.3 compositio... |
| 20 | Output-first | C+ | medium | The skill defines the process very clearly before defining a concrete output artifact. It knows the behavioral goal, but not an explicit agent-facing output schema. |
| 21 | Decision class drives gating | C- | medium | The skill distinguishes some escalations in practice, but it never classifies decisions into mechanical, taste, and user-challenge buckets with different gate behavior. That makes the judgment policy implicit rather t... |
| 22 | Voice + writing rules | A | high | The writing rules are embedded directly in the skill body through hard constraints, anti-rationalization phrasing, and disciplined language. It is not just informative prose; it actively shapes behavior. |
| 23 | Host-portable | C+ | medium | The skill is conceptually portable, but its examples and commands lean heavily toward a JavaScript/npm workflow and it does not declare harness-agnostic tool constraints. It avoids absolute machine paths, which helps,... |
| 24 | Self-observation | F | high | There is no mechanism to record prior executions, learn from them, or reload those lessons later. The skill may be disciplined, but it is stateless across runs. |
| 25 | Spawn-detection | D | medium | Nothing in the skill adapts behavior for spawned non-interactive use versus direct human interaction. In agent-to-agent invocation, the repeated `ask your human partner` guidance would need explicit fallback behavior ... |


## 02-tob-auditor

**Archetype:** Procedural — The skill is built around an ordered audit workflow with explicit phases, branching modes, stop conditions, and a final reporting procedure. It contains reference material, but its dominant mode is executing a process rather than serving as passive documentation.

**Aggregate grade:** B- — This would likely work well in production as a practical security-audit skill because routing, scope control, and reporting are strong. It falls short of higher PaaP grades because key process primitives are missing or weak: file-backed intermediates, explicit gate structures, runtime path resolution, self-observation, and spawn-aware behavior.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | B+ | high | The routing signal is strong on positive triggers and the body adds clear anti-triggers, so the skill would usually be invoked correctly in practice. The main gap is that the YAML `description` itself does not carry t... |
| 2 | Route before work | A | high | The skill explicitly starts by classifying the request into remote versus local analysis before substantive analysis begins. It also defines early stop conditions before deeper work. |
| 3 | Modes | A | high | There are two legitimate execution paths, and they are explicitly named with clear selection criteria. The mode split is operational, not cosmetic. |
| 4 | State | N/A | medium | This is a single-run audit workflow with no real resume boundary, handoff phase, or durable long-horizon execution requirement. In normal use it can complete in one pass without persisted state. |
| 5 | Parallel | C+ | medium | The work naturally contains parallelizable units such as per-workflow scanning and per-vector checks, but the skill never tells the agent to run them in parallel. It will still work, just less efficiently and with mor... |
| 6 | Personas/voice | B+ | medium | The skill has real behavioral discipline through the rationalization-rejection section, which helps prevent common audit mistakes. It does not define a sharper persona or stronger operating laws beyond those guardrails. |
| 7 | Files = bus | C+ | high | The workflow is multi-phase, but intermediate data is only described conceptually and passed in-memory until the final report. That is workable for a modest audit, but it is not robust PaaP-style bus design. |
| 8 | Synthesis | B+ | medium | The reporting phase includes useful merge rules such as grouping by workflow, ordering by severity, and noting amplifying interactions. What is missing is a more explicit conflict-resolution rule for ambiguous or comp... |
| 9 | Human gate | B- | medium | The skill is mostly mechanical, so full autonomy is sensible, but it does not define explicit wait points for genuine ambiguity. The one visible question prompt is advisory rather than a formal gate. |
| 10 | Exit = question | B | high | Phase exits are operationally clear through stop conditions, which is good enough to run reliably. The gap is that they are written as instructions rather than crisp binary exit questions. |
| 11 | Output spec | A+ | high | The output specification is unusually strong: exact section order, per-finding schema, summary tables, clean-repo behavior, and remote-analysis variants are all defined. A competent agent should produce consistent del... |
| 12 | Gates = 3 parts | C+ | medium | There are checks and failure actions in a few places, especially around remote fetch failures and empty results. The skill does not systematize quality gates as check plus failure condition plus recovery path across t... |
| 13 | External storage | N/A | medium | The skill is sizable but still functions as a single coherent instruction document rather than an oversized prompt pack. It already externalizes deeper reference material without clearly crossing the threshold where t... |
| 14 | Context scope | A | high | Scope control is one of the skill's strongest traits: it defines when to use it, when not to use it, what directories to scan, and what Bash may or may not do. That materially reduces misuse and false-positive analysi... |
| 15 | Progress | A- | high | The skill requires meaningful progress checkpoints with counts and summaries, which is enough for useful operator visibility. It does not specify richer running telemetry, but the essentials are there. |
| 16 | Errors | B+ | high | The remote-analysis path has concrete error mappings for authentication, missing repositories, and empty workflow directories. That is good practical coverage, though it is narrower and less systematic than a full err... |
| 17 | Autonomy | A | high | The skill makes sensible choices automatically, including mode inference, stopping on clean no-hit cases, and not asking the user for unnecessary confirmations. It reads like something that can run end-to-end with min... |
| 18 | Path resolution | C- | high | The skill uses relative-style placeholders rather than hardcoded author-machine paths, which is directionally right. The problem is that `{baseDir}` is assumed rather than resolved at runtime with a fallback, so refer... |
| 19 | Composition | N/A | high | The skill references internal markdown documents but does not invoke or orchestrate other skills. Because there is no cross-skill composition, composed-skill metadata is not needed here. |
| 20 | Output-first | C | high | The output contract is excellent, but it arrives late in Step 5 after most of the process description. Under PaaP, the output spec should anchor the skill before the workflow phases begin. |
| 21 | Decision class drives gating | C | medium | The skill discusses severity judgment and context factors, but it never classifies decisions into mechanical, taste, and user-challenge classes with corresponding gate behavior. In practice this means the agent has le... |
| 22 | Voice + writing rules | C+ | medium | There are some writing constraints for the report and some anti-rationalization guidance, which helps. What is missing is a first-class voice system with tone rules, banned phrases, and explicit prose-shaping constrai... |
| 23 | Host-portable | A- | medium | The skill is mostly portable: tool permissions are declared cleanly, references are not hardcoded to a personal machine, and the core method is host-agnostic. The small gap is reliance on specific tool names and `gh a... |
| 24 | Self-observation | F | high | There is no mechanism for recording prior runs, reading those records back, or adapting future audits from prior mistakes. The skill is stateless across executions. |
| 25 | Spawn-detection | F | high | The skill can clearly be invoked by another agent, but it does not distinguish spawned versus interactive execution. There is no machine-readable fallback mode or suppression of user-facing prompts when embedded in a ... |


## 03-anthropic-skill-creator

**Archetype:** Procedural — This skill is a staged workflow for drafting, testing, reviewing, benchmarking, and iterating on other skills. Its value comes from ordered phases, checkpoints, and loop control rather than serving as a static reference or primarily aesthetic spec.

**Aggregate grade:** B+ — This is a production-credible procedural skill with strong workflow design, concrete filesystem contracts, useful parallelization, and a real human review loop. It misses the A range because several PaaP v0.3 formalisms are still loose or absent, especially explicit gate structure, decision classes, machine-readable composition, full host portability, and durable self-observation beyond the current iteration loop.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A- | high | The frontmatter description does real routing work: it names concrete entry conditions like creating, editing, benchmarking, and optimizing a skill. The main gap is that it lacks explicit anti-triggers, so the boundar... |
| 2 | Route before work | A | high | The skill explicitly tells the agent to first determine where the user is in the lifecycle and only then enter the relevant stage. That is the right control structure for a process skill. |
| 3 | Modes | A- | medium | There are several real execution paths and the skill names them clearly: new skill creation, improving an existing skill, quick informal collaboration, description optimization, and environment-specific variants. The ... |
| 4 | State | A | high | This is a long-horizon skill and it writes durable process state to disk across iterations, including eval definitions, metadata, timing, grading, benchmarks, and user feedback. It also has an implicit resume protocol... |
| 5 | Parallel | A | high | The skill strongly and explicitly exploits parallelism where it matters most: paired eval runs and background work during execution. It even calls out the anti-pattern of serial launches. |
| 6 | Personas/voice | B+ | medium | There is useful behavioral guidance for how to talk to users with different technical fluency, which is a real production concern. What is missing is a sharper persona contract or explicit subagent role discipline ins... |
| 7 | Files = bus | A- | high | The process passes information through concrete files and directories rather than relying on ephemeral context. It is not using a numbered file convention, but functionally it does use the filesystem as the handoff bus. |
| 8 | Synthesis | B+ | medium | The skill has a real merge step: aggregate metrics, do an analyst pass, and combine quantitative results with human feedback for revision. The weak spot is that conflict resolution rules are implied rather than stated... |
| 9 | Human gate | A | high | Human judgment is treated as irreducible at the right moments: confirming intent, approving test cases, reviewing outputs, and signing off on trigger eval sets. The skill genuinely waits for the user before proceeding... |
| 10 | Exit = question | B | medium | Several phase exits are operationally clear, but they are not consistently expressed as binary answerable questions. In practice the loop is workable, but the exit discipline is looser than the rubric wants. |
| 11 | Output spec | B+ | medium | The skill gives strong format contracts for many artifacts such as eval JSON, metadata, timing, grading, and benchmark files. It is weaker on defining a single unified output contract for the agent's overall deliverab... |
| 12 | Gates = 3 parts | C+ | medium | The skill has lots of checks and branch advice, but its gates are usually missing the full trio of explicit check, failure condition, and recovery path. Recovery exists in places, yet not as a consistent gate pattern. |
| 13 | External storage | A | medium | For a long skill, it sensibly pushes specialized prompts, schemas, assets, and scripts into separate files and tells the agent when to load them. That keeps the core SKILL.md focused enough to operate. |
| 14 | Context scope | A | high | Scope boundaries are strong throughout: it defines what the skill is for, when to skip assertions, when to skip benchmarking, when to avoid other testing skills, and how behavior changes by host environment. That mate... |
| 15 | Progress | B+ | medium | The skill does ask for progress communication at meaningful moments, especially during long-running optimization and after launching review artifacts. It would be stronger with more explicit checkpoint cadence and met... |
| 16 | Errors | C+ | high | There is decent fallback prose for missing browser, missing display, no subagents, and timeouts. But the skill does not provide an explicit error table that maps named failure modes to specific actions. |
| 17 | Autonomy | A- | high | The skill gives sensible defaults, infers next steps from the user's current stage, and only asks for judgment when it really matters. It stays flexible instead of over-interrogating the user. |
| 18 | Path resolution | B | medium | Most references are runtime-relative and practical, but there are still host-specific hardcoded conventions like `/tmp/`, `~/Downloads`, and `open` commands. That is workable in the intended environment but not fully ... |
| 19 | Composition | C | medium | The skill clearly leans on adjacent helpers like specialized agent instructions and separate scripts, but it does not declare composition metadata in frontmatter or make composed dependencies explicit in a machine-rea... |
| 20 | Output-first | B- | medium | The skill starts from workflow and only later introduces artifact formats and deliverable structures. It still specifies outputs well enough to function, but the output contract is not front-loaded as the primary orga... |
| 21 | Decision class drives gating | C | medium | The skill informally distinguishes objective checks from subjective human review, which is useful, but it never formalizes mechanical versus taste versus escalation classes. As a result the gating logic works by conve... |
| 22 | Voice + writing rules | A- | high | The skill contains substantive writing guidance: adapt jargon to user sophistication, prefer explanation over rigid commands, avoid overfitty MUST-style prompting, and explain the why. That is first-class prompt craft... |
| 23 | Host-portable | C+ | high | The skill does make a serious effort to adapt across Claude Code, Claude.ai, and Cowork, which is better than most. It still remains tightly Claude-centric and uses host-specific commands and assumptions rather than a... |
| 24 | Self-observation | B- | medium | There is a real read-back loop inside the iteration cycle: prior outputs, prior feedback, prior workspaces, and benchmark history are reused to avoid repeating mistakes. It falls short of a broader persistent executio... |
| 25 | Spawn-detection | B- | medium | The skill clearly adapts to whether subagents and browsers exist, which covers some of the same operational ground as spawn awareness. It does not explicitly detect 'called by another agent' versus 'interactive human'... |


## 04-tapestry-article-extractor

**Archetype:** Procedural — This skill defines an execution workflow with ordered steps, fallbacks, and a concrete end artifact. It is meant to be run as a process, not read primarily as reference material or judged mainly on creative output.

**Aggregate grade:** B- — This is a practically useful procedural skill with solid extraction logic, fallbacks, and decent error handling, but it leaves a lot of PaaP rigor on the table around routing formalism, gating, composition, voice discipline, and self-observation.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | B+ | high | The YAML description routes the skill to a clear class of requests and names the desired outcome. The main gap is missing anti-triggers or explicit "do not use" boundaries. |
| 2 | Route before work | B- | medium | The skill does some front-loaded routing through its activation criteria and tool-selection priority, but it does not define a formal first-phase classification or stop conditions before execution. In practice it work... |
| 3 | Modes | A | high | There are multiple legitimate execution paths, and they are named and criteria-driven. The selection rule is simple and practical: use the best available extractor, then degrade gracefully. |
| 4 | State | N/A | high | This is a short, one-shot extraction task that finishes in a single run and does not need resume behavior. |
| 5 | Parallel | N/A | high | The workflow is inherently linear: select a tool, extract, clean, save, and preview. There are no independent subtasks that would benefit from explicit parallelization. |
| 6 | Personas/voice | D | high | There is no persona discipline, behavioral contract, or voice specification beyond generic procedural prose. For a utility skill this is not crippling, but the principle is mostly unmet. |
| 7 | Files = bus | B | medium | The workflow does pass work between phases through files, especially `temp_article.txt` and the final output file. It lacks the stronger numbered-artifact pattern and richer multi-file handoff structure the rubric pre... |
| 8 | Synthesis | B- | medium | This skill is mostly linear, so synthesis pressure is low. The closest thing to synthesis is the explicit precedence rule between extraction methods, but there is no formal merge or conflict-resolution step because ou... |
| 9 | Human gate | A- | medium | There is no true human gate, but this task also does not contain an obvious irreducible taste, ethics, or irreversible-action decision that would require one. The optional follow-up questions are appropriately non-blo... |
| 10 | Exit = question | B- | medium | The skill implies binary checks such as extraction success and preview quality, but it does not phrase phase exits as explicit answerable questions. It is workable in production, just less crisp under stress. |
| 11 | Output spec | B+ | high | The skill specifies what the saved file should contain, what should be removed, and what should be shown to the user afterward. The remaining gap is precision: it lacks a stricter final-output template and section-by-... |
| 12 | Gates = 3 parts | B- | medium | There are partial quality gates with checks, common failure modes, and fallback actions, especially around missing tools and extraction failure. What is missing is a consistent check/failure/recovery triad for every m... |
| 13 | External storage | N/A | high | The skill is compact enough to live comfortably in one file and does not appear to cross the size threshold where prompt assets should be externalized. |
| 14 | Context scope | B+ | high | The skill clearly defines what it is for and gives concrete request examples. The main missing piece is stronger negative scoping about what kinds of URLs or extraction jobs it should not handle. |
| 15 | Progress | B+ | high | For a short utility skill, the progress reporting is practical: it announces the chosen tool, saved location, and preview. It does not define richer checkpoint reporting, but it gives enough visibility for the job size. |
| 16 | Errors | A- | high | The skill explicitly lists common failure cases and recommended actions, which is unusually concrete for a lightweight utility skill. It falls just short of exemplary because the mapping is prose-based rather than a s... |
| 17 | Autonomy | A | high | The skill defaults intelligently, chooses the best available tool, and only asks the user optional follow-ups after delivering the core outcome. That is strong practical autonomy. |
| 18 | Path resolution | N/A | high | The skill does not depend on external repo paths or referenced support files that need runtime resolution. Its outputs are generated locally from a title-derived filename. |
| 19 | Composition | C- | medium | The skill gestures at composition by mentioning another skill, but it does not declare composed skills in metadata or define runtime resolution and invocation rules. Because the composition is only suggestive rather t... |
| 20 | Output-first | C+ | high | The output expectations are documented, but they appear after most of the process design rather than leading it. The skill is usable, yet the structure is process-first rather than output-first. |
| 21 | Decision class drives gating | C | medium | The skill implicitly treats tool choice as a mechanical decision and preview quality as something the user can inspect, but it never formalizes decision classes or connects them to different gating behavior. The pract... |
| 22 | Voice + writing rules | D | high | There are no first-class writing rules, banned phrases, or output voice constraints. For a utility extractor this matters less than for a narrative skill, but the rubric criterion is still mostly unmet. |
| 23 | Host-portable | B+ | medium | The skill is reasonably portable across agent hosts because it uses relative/local outputs and a generic `allowed-tools` declaration. It loses points for environment assumptions like global npm or pip installs and she... |
| 24 | Self-observation | F | high | The skill does not store execution learnings or read back any prior run data. There is no self-observation loop. |
| 25 | Spawn-detection | D | medium | This skill could plausibly be called by another agent, but it does not adapt output format, questioning behavior, or defaults for spawned versus interactive use. The omission is real, though not fatal for the core ext... |


## 05-expo-deployment

**Archetype:** Reference — This file is primarily a deployment reference sheet: commands, config snippets, and links to deeper docs. It is meant to be consulted selectively, not executed as a gated end-to-end workflow.

**Aggregate grade:** C — As a practical deployment cheat sheet this is useful and likely to help in production, but as a PaaP skill it is missing too much of the process-facing contract: weak routing boundaries, no output/progress protocol, no self-observation, and brittle reference-path handling.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | B+ | high | The YAML description clearly signals the domain and major deployment targets, so routing is workable in practice. It does not include anti-triggers or explicit non-use cases, which keeps it short of an A-range score. |
| 2 | Route before work | N/A | high | This principle is procedural-only in the rubric, and this skill is better classified as reference material than an executable process. |
| 3 | Modes | B- | medium | The skill does present distinct practical paths by platform and deployment target, which functions like lightweight modes. What is missing is explicit mode selection criteria up front, so the user or host must infer w... |
| 4 | State | N/A | high | Durable run state and resume behavior are not expected for this kind of static deployment reference. |
| 5 | Parallel | N/A | high | The file does not define parallel agent subtasks, and reference documentation does not require them. |
| 6 | Personas/voice | N/A | high | Persona discipline is not expected for a plain reference sheet. |
| 7 | Files = bus | N/A | high | The skill does not operate as a multi-phase process passing artifacts between stages. |
| 8 | Synthesis | N/A | high | There is no parallel research or multi-output merge step to synthesize. |
| 9 | Human gate | N/A | high | The skill is informational and does not define an execution flow with irreversible actions that must pause for user approval. |
| 10 | Exit = question | N/A | high | There are no defined phases or exits to evaluate. |
| 11 | Output spec | D | medium | The document is well structured as reference content, but it does not specify what an agent should output when using the skill: no response shape, section requirements, or concise answer contract. In production this s... |
| 12 | Gates = 3 parts | N/A | high | No quality gates are defined because this is not a procedural workflow skill. |
| 13 | External storage | N/A | high | The file is comfortably below the rubric's rough size threshold for mandatory prompt decomposition. |
| 14 | Context scope | B- | high | The scope is mostly clear: Expo deployment via EAS across major platforms. The boundary is not crisp enough, though; there are no explicit non-goals, and the description mentions API routes without any substantive API... |
| 15 | Progress | F | high | There is no instruction for reporting progress, checkpointing findings, or surfacing status while the skill is being used. That omission matters even for reference skills when embedded in an agent workflow. |
| 16 | Errors | N/A | high | The rubric does not require error tables for the reference archetype. |
| 17 | Autonomy | N/A | high | Autonomy rules are primarily relevant to procedural or creative execution, not static reference content. |
| 18 | Path resolution | C- | high | The file uses relative paths, which is good for portability, but it does not define any runtime resolution or fallback behavior. It also contains inconsistent path references, which is a practical failure mode. |
| 19 | Composition | C+ | medium | The skill clearly depends on companion reference files, so composition exists in practice. However, it does not declare those dependencies in structured metadata such as `composed_skills`, and they are plain file ment... |
| 20 | Output-first | C- | medium | The document leads with setup steps and command examples before defining the expected deliverable or answer shape. As a practical cheat sheet this is usable, but by PaaP standards the output contract comes too late or... |
| 21 | Decision class drives gating | N/A | high | Decision classification is a procedural gating mechanism and is not relevant to this reference-style skill. |
| 22 | Voice + writing rules | N/A | high | The file is neutral technical documentation and does not need dedicated voice constraints under the reference archetype. |
| 23 | Host-portable | A- | high | This is one of the stronger areas: the skill avoids hardcoded machine paths, uses standard relative references, and relies on common CLI commands. It loses a small amount for path inconsistency and assuming specific c... |
| 24 | Self-observation | F | high | There is no mechanism to record past executions, retain lessons, or read them back on later runs. The skill behaves as static documentation only. |
| 25 | Spawn-detection | N/A | high | Spawn-awareness is a procedural conditional principle and is not required for this reference archetype. |


## 06-kdense-biopython

**Archetype:** Reference — This SKILL.md is primarily a topic-organized reference guide for Biopython modules and companion docs, not an end-to-end executable workflow. It is meant to be consulted selectively by task domain, so most procedural gating/state principles do not apply.

**Aggregate grade:** B- — As a production reference skill, this is useful and competently routed: it scopes the domain well, organizes the Biopython surface area cleanly, and points to practical companion docs. It drops to B- because the PaaP-specific execution contract is weak on output specification, progress behavior, and especially the total absence of self-observation.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A | high | The YAML description does real routing work: it names the core use cases and includes practical anti-routing to other tools for neighboring jobs. The only small gap is that the body reinforces positive triggers more t... |
| 2 | Route before work | N/A | high | This is a Reference archetype skill, not a procedural workflow, so route-before-execution is not a required design element here. |
| 3 | Modes | B+ | medium | The skill exposes multiple legitimate lookup paths by module area and gives selection criteria based on task type. It does not explicitly label these as modes or define a top-level mode-selection schema, but in practi... |
| 4 | State | N/A | high | There is no long-horizon execution loop here; the skill is a static reference guide. |
| 5 | Parallel | N/A | high | The skill does not define independent subtasks that would benefit from parallel execution; it is a lookup-oriented reference. |
| 6 | Personas/voice | N/A | high | Reference skills are not expected to carry behavioral persona scaffolding under this rubric. |
| 7 | Files = bus | N/A | high | The reference files are documentation sources, not inter-phase handoff artifacts in a workflow. |
| 8 | Synthesis | N/A | high | The skill does not define parallel research branches that must be merged under explicit synthesis rules. |
| 9 | Human gate | N/A | high | There is no procedural checkpointing or irreversible action flow in this skill. |
| 10 | Exit = question | N/A | high | The skill is not organized into executable phases with exit criteria; it is a consultable guide. |
| 11 | Output spec | C+ | medium | The skill gives usable guidance on how to answer a user request by selecting a module and extracting code patterns, but it never defines a concrete answer format, section structure, or response constraints. In product... |
| 12 | Gates = 3 parts | N/A | high | This skill does not define procedural quality gates, so the three-part gate requirement is not relevant. |
| 13 | External storage | N/A | high | The SKILL.md is not large enough to trigger the v0.3 externalization requirement for oversized skill bodies. |
| 14 | Context scope | A- | high | Scope control is strong: the description and body define the problem domain clearly and point to adjacent tools for nearby use cases. The main gap is that the body emphasizes when to use more than when not to use. |
| 15 | Progress | C | medium | There is a sensible lookup workflow, but there is no explicit instruction to surface progress to the user while working through references. In practice an agent can use it, but the skill itself does not enforce meanin... |
| 16 | Errors | N/A | high | Although the document has a troubleshooting section, the rubric does not require explicit error-table handling for Reference archetype skills. |
| 17 | Autonomy | N/A | high | Autonomy defaults are not a required dimension for Reference archetype skills under this rubric. |
| 18 | Path resolution | B+ | high | The skill uses portable relative paths for its companion docs, which is the right default. It loses a notch because it does not specify any fallback behavior if `references/` files are missing or differently located. |
| 19 | Composition | B | medium | This skill is modular and clearly composes internal reference documents by topic, which works in practice. It does not use explicit `composed_skills:` metadata or runtime composition semantics, so it falls short of fu... |
| 20 | Output-first | C+ | medium | The document front-loads capability areas and reference locations before workflow advice, which is directionally correct. But it still never defines a concrete final deliverable shape for the agent's answer, so the ou... |
| 21 | Decision class drives gating | N/A | high | This skill has no procedural gating system, so decision-class-driven escalation does not apply. |
| 22 | Voice + writing rules | N/A | high | Reference skills are not required to embed first-class prose-style rules under this rubric. |
| 23 | Host-portable | B | high | The skill is mostly portable because it uses relative paths and generally generic tooling examples. It loses points for host-specific phrasing like "using the Read tool" and for assuming shell commands without a harne... |
| 24 | Self-observation | F | high | There is no mechanism to record prior executions, learn from them, or read those learnings back on subsequent runs. This principle is simply absent. |
| 25 | Spawn-detection | N/A | high | Spawn-awareness is a procedural conditional principle and this skill is a reference guide rather than an invocable workflow with interactive gates. |


## 07-chrisvoncsefalvay-d3

**Archetype:** Reference — This SKILL.md primarily acts as a reusable D3 reference and pattern library rather than an end-to-end executable process. It contains routing guidance and example implementations, but not phase gates, durable workflow state, or interactive checkpoints.

**Aggregate grade:** B- — This is a useful, portable D3 reference with clear scope boundaries, practical mode selection, and solid example coverage, but it falls short on formal output contract, progress semantics, resource-composition discipline, and v0.3 self-observation.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | B+ | high | The YAML description does real routing work by naming concrete triggers, chart families, and environments. The main gap is that the negative routing is mostly in the body rather than the YAML description itself. |
| 2 | Route before work | N/A | high | Reference skills are read for guidance rather than executed as a staged process, so a dedicated routing-first phase is not expected here. |
| 3 | Modes | A | high | The skill names distinct execution modes and gives criteria for choosing between them. This is strong, practical mode design rather than vague branching. |
| 4 | State | N/A | high | The skill does not define a long-horizon workflow, so durable state and resume mechanics are not part of its design target. |
| 5 | Parallel | N/A | high | Nothing in this skill involves orchestrating independent subtasks, so explicit parallelization is not relevant. |
| 6 | Personas/voice | N/A | high | Reference skills are not expected to define operational personas or sub-agent behavioral contracts. |
| 7 | Files = bus | N/A | high | There is no multi-phase execution pipeline here, so passing artifacts across numbered files is out of scope. |
| 8 | Synthesis | N/A | high | The skill does not collect parallel outputs that need explicit merge rules or conflict resolution. |
| 9 | Human gate | N/A | high | Reference material is consulted, not paused on human checkpoints, so explicit AskUserQuestion gates are not expected. |
| 10 | Exit = question | N/A | high | The skill does not define staged exits, so binary exit questions are not applicable. |
| 11 | Output spec | B- | medium | The skill gives concrete code structure, templates, and examples, which helps produce working output in practice. The gap is that it never defines a formal final deliverable contract for what the agent should return t... |
| 12 | Gates = 3 parts | N/A | high | There are no explicit quality gates in this reference skill, and reference archetypes are not expected to define them. |
| 13 | External storage | B | medium | The skill is long enough to justify offloading material, and it does externalize supporting references and templates. Still, a large amount of reference content remains inline, so the separation is only partial. |
| 14 | Context scope | A | high | Scope is explicit and useful: it says what D3 is good for and where to use something else. That makes invocation boundaries clear in production. |
| 15 | Progress | D | high | There is no guidance for status updates, checkpoints, or reporting partial progress. An agent following this skill would likely stay silent until completion. |
| 16 | Errors | N/A | high | Error-table requirements do not apply to reference skills under this rubric. |
| 17 | Autonomy | N/A | high | Autonomy rules for execution behavior are not required because this skill is primarily consulted as documentation. |
| 18 | Path resolution | C+ | medium | The skill uses relative paths rather than hardcoded machine paths, which is good. But it does not describe runtime resolution, existence checks, or fallbacks if those resource folders are missing. |
| 19 | Composition | C+ | medium | This is somewhat ambiguous because the skill does not compose other skills, only bundled resources. Still, it lacks any formal composition metadata or explicit runtime contract for those dependencies. |
| 20 | Output-first | C+ | medium | The document starts with overview and workflow structure before defining a target output contract. In practice the output is implied by examples, but not specified first-class up front. |
| 21 | Decision class drives gating | N/A | high | This skill does not implement procedural gates, so decision-class-specific gating logic is not relevant. |
| 22 | Voice + writing rules | N/A | high | Reference skills are not expected to carry creative voice rules or banned-phrase policies. |
| 23 | Host-portable | A | high | The skill is intentionally environment-agnostic and repeatedly emphasizes portability across frameworks. It also avoids hardcoded author-machine paths. |
| 24 | Self-observation | F | high | There is no mechanism for recording prior executions, lessons learned, or reading them back on later runs. The skill is stateless across sessions. |
| 25 | Spawn-detection | N/A | high | Spawn-awareness is a procedural concern and this skill does not define interactive execution behavior to adapt. |


## 08-anthropic-canvas-design

**Archetype:** Hybrid — The skill has a real two-step workflow, but its success is dominated by aesthetic judgment, output constraints, and creative direction rather than procedural gating. I therefore treat it as Hybrid with Creative as the dominant mode.

**Aggregate grade:** B — This skill is strong where creative skills usually live or die: scope, output specification, and aesthetic discipline. It drops to a solid B because operational robustness is thin, especially around progress reporting, error handling, and portable dependency/path behavior.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | B+ | high | The YAML description gives a concrete trigger surface: posters, art, design, and other static visual pieces. It also includes one meaningful negative constraint around originality, but it does not define stronger anti... |
| 2 | Route before work | N/A | high | Under the chosen Hybrid/Creative reading, this skill is not expected to implement a separate routing phase before execution. |
| 3 | Modes | C+ | medium | There are multiple legitimate paths here, but they are implicit rather than formalized as named modes with decision criteria. The reader can infer variants like single-page versus multi-page or quiet versus bold typog... |
| 4 | State | N/A | high | The skill is aimed at producing a bounded artifact, not maintaining long-horizon work with resumable execution state. |
| 5 | Parallel | N/A | high | The work is described as a single creative flow, not a set of independent subtasks that should be launched concurrently. |
| 6 | Personas/voice | B | medium | The skill has strong behavioral discipline around sophistication, minimalism, and craftsmanship, which is useful in practice. What it lacks is a sharper named persona or explicit rejection framework beyond repeated ex... |
| 7 | Files = bus | N/A | high | Although outputs are written to files, the skill does not operate as a multi-phase procedural system that passes work products through numbered bus files. |
| 8 | Synthesis | N/A | high | There is no parallel research or agent branch structure that would need explicit merge rules. |
| 9 | Human gate | N/A | high | The skill does not define a genuine stop-and-wait checkpoint for user judgment, which is acceptable under the chosen creative dominant mode. |
| 10 | Exit = question | N/A | high | This skill does not structure its progress as binary exit questions, which is not required for the dominant creative archetype. |
| 11 | Output spec | A | high | The deliverables are unusually concrete for a creative skill: file types, page count default, philosophy length, visual/text ratio, and output pairing are all spelled out. There is some mild looseness around PDF versu... |
| 12 | Gates = 3 parts | N/A | high | The skill does not define procedural quality gates with check, failure condition, and recovery path, and that is outside the main expectation for a creative-dominant skill. |
| 13 | External storage | N/A | high | The provided skill text is well under the threshold where prompt bodies clearly need to be split into auxiliary files. |
| 14 | Context scope | A | high | The skill is clear about what it is for and what it is not for. It repeatedly narrows the target to art objects, visual philosophy, sparse text, and non-amateur execution, which reduces misuse. |
| 15 | Progress | D | high | There is no instruction to provide interim status, checkpoint summaries, or any measurable progress reporting. For a potentially long creative generation task, that omission is material. |
| 16 | Errors | C | medium | The skill does contain some concrete failure warnings and local corrective advice, which helps in practice. But it never reaches the standard of an explicit error table mapping specific failures to specific actions. |
| 17 | Autonomy | B+ | medium | The default behavior is sensible: create one page unless asked otherwise, infer text treatment from context, and keep the piece sophisticated. It still leaves some operational ambiguity around font acquisition and too... |
| 18 | Path resolution | C | high | A relative path is better than a hardcoded author path, but there is no fallback if the directory is absent. The instruction to download fonts adds another unresolved dependency with no resolution logic. |
| 19 | Composition | N/A | high | The skill does not compose other skills or declare a composed skill contract. |
| 20 | Output-first | A- | high | The skill defines artifact types and end products before the main workflow, which is the right orientation. It then adds more output constraints throughout the body, so the spec is slightly distributed rather than per... |
| 21 | Decision class drives gating | N/A | high | The skill does not classify decisions into mechanical, taste, and user-challenge classes, which is acceptable for the chosen dominant mode. |
| 22 | Voice + writing rules | A | high | This is one of the skill's strongest areas. It has explicit tone rules, banned outcomes, anti-template guidance, and repeated qualitative standards that strongly shape outputs. |
| 23 | Host-portable | B- | medium | The skill is partly portable because it uses relative paths and generic output artifacts. It loses points because it assumes capabilities like searching a local font directory and downloading fonts without a harness-a... |
| 24 | Self-observation | N/A | high | There is no execution-history read/write loop, but that principle is not required for the chosen creative-dominant archetype. |
| 25 | Spawn-detection | N/A | high | The skill does not adapt behavior for spawned versus interactive invocation, and I do not treat that as required under the creative-dominant archetype here. |


## 09-anthropic-frontend-design

**Archetype:** Creative — This skill is primarily an aesthetic brief for generating distinctive frontend output, where taste, visual direction, and anti-generic design rules dominate. It has a light sequence, but it does not define the gates, state, or execution mechanics needed for Procedural to be the dominant archetype.

**Aggregate grade:** B- — This skill would likely produce strong frontend work in practice because its aesthetic direction, anti-generic rules, and autonomy are solid. It falls short of the A range because it lacks formal modes, progress reporting, error handling, and a tighter output contract.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A- | high | The YAML description routes well in practice: it names concrete trigger cases and the kind of output expected. It loses a small amount for lacking explicit anti-triggers about when not to use the skill. |
| 2 | Route before work | N/A | high | This is not a Procedural skill, so a dedicated routing phase is not required by the archetype. |
| 3 | Modes | C+ | medium | The skill clearly has multiple legitimate paths, both in visual direction and implementation stack, but it never formalizes them as named modes with selection criteria. In practice that leaves too much variance to the... |
| 4 | State | N/A | high | The skill is a short creative generation brief and does not imply long-horizon resumable work. |
| 5 | Parallel | N/A | high | The skill does not define independent subtasks that would benefit from explicit parallel execution. |
| 6 | Personas/voice | B+ | high | It establishes a strong behavioral discipline around boldness, intentionality, and anti-generic design, which is useful in production. It stops short of a named persona, iron laws, or explicit rationalizations-to-reje... |
| 7 | Files = bus | N/A | high | The skill is not a multi-phase procedural workflow that passes artifacts between stages. |
| 8 | Synthesis | N/A | high | No parallel research or multi-agent branches are defined, so there is nothing to synthesize formally. |
| 9 | Human gate | N/A | high | The skill does not define irreversible actions or explicit checkpoints where it must stop for human judgment. |
| 10 | Exit = question | N/A | high | There are no procedural phase exits in this skill to express as binary questions. |
| 11 | Output spec | B+ | high | The skill gives a practical output target: working code with strong aesthetic properties and several anti-template rules. It is still not an exact output contract with required sections, file expectations, or length/s... |
| 12 | Gates = 3 parts | N/A | high | The skill contains no quality gates, so the three-part gate requirement is not applicable by archetype. |
| 13 | External storage | N/A | high | The skill is short and does not approach the size threshold where prompt decomposition becomes necessary. |
| 14 | Context scope | B+ | high | It explains what the skill is for, what inputs the user may provide, and the design dimensions to consider. The missing piece is a sharper 'not for' boundary, especially around cases where an existing design system or... |
| 15 | Progress | F | high | There are no instructions for status updates, checkpoints, or visible progress reporting. In production that makes collaboration weaker, especially for larger frontend builds. |
| 16 | Errors | F | high | The skill has no explicit error table or fallback behavior for common failure modes such as unavailable fonts, missing motion libraries, accessibility conflicts, or mismatch with existing UI conventions. That is a rea... |
| 17 | Autonomy | A- | high | The skill strongly encourages autonomous choice of aesthetic direction and implementation detail instead of over-asking the user. It would be stronger with explicit defaults for ambiguous cases, but in practice it is ... |
| 18 | Path resolution | N/A | medium | The skill does not meaningfully rely on external file paths at runtime; it only mentions a license file in metadata and a library by name. That is not enough to trigger the path-resolution requirement. |
| 19 | Composition | N/A | high | The skill does not invoke or declare any composed skills. |
| 20 | Output-first | B- | medium | The intended output is clear enough, but it is not framed first as a formal deliverable contract. The skill leads with design-thinking process and only then specifies the implementation target, which is workable but n... |
| 21 | Decision class drives gating | N/A | high | The skill does not define a procedural gating model, so decision classes are not part of its design. |
| 22 | Voice + writing rules | A- | high | This is one of the skill's strongest areas: it gives explicit stylistic imperatives, bans common bad defaults, and pushes intentional design language into the core instructions. It misses only a more formalized set of... |
| 23 | Host-portable | B | high | Most of the skill is portable because it is framework- and output-focused rather than harness-specific. The main portability blemish is the host-specific line about Claude, which weakens clean reuse across Codex, Curs... |
| 24 | Self-observation | N/A | high | The skill contains no execution-memory loop, but that requirement does not apply to the Creative archetype under the matrix. |
| 25 | Spawn-detection | N/A | high | Spawn-awareness is a procedural conditional principle and is not expected for this creative brief. |


## 10-anthropic-algorithmic-art

**Archetype:** Hybrid — This skill mixes a real two-step workflow with a strongly aesthetic, output-driven brief. Its dominant mode is Creative: the main value is the quality of the philosophy, code aesthetic, and artifact spec, while the procedural spine is secondary.

**Aggregate grade:** B+ — Creative-dominant craftsmanship is strong here: routing, scope, output contract, and writing rules are all production-useful. The score is held below the A range by weak observability, no real error-recovery structure, and only partial host/path portability.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A- | high | The YAML description does real routing work: it names the medium, techniques, and trigger phrases. The small gap is that the anti-triggers are stronger in the body than in the description field itself. |
| 2 | Route before work | N/A | high | This is a Hybrid skill with a creative-dominant mode, so a separate pre-execution routing phase is not expected by the archetype. |
| 3 | Modes | N/A | high | The skill presents one main execution path rather than multiple named modes with decision criteria. |
| 4 | State | N/A | medium | The task is scoped as a single-pass creative generation flow and does not obviously require a resume protocol. |
| 5 | Parallel | N/A | high | The workflow is intentionally serial: philosophy first, then implementation. |
| 6 | Personas/voice | A- | high | The skill has strong behavioral discipline and output voice rules centered on computational craftsmanship and poetic generative thinking. It falls slightly short of exemplary because it does not formalize the persona ... |
| 7 | Files = bus | N/A | high | Although the outputs are files, the skill is not built around a procedural multi-phase file-bus pattern, and that is not expected for the dominant archetype. |
| 8 | Synthesis | N/A | high | The skill chains one creative step into the next, but it does not run parallel branches that require explicit merge rules. |
| 9 | Human gate | N/A | high | The dominant mode is creative generation with reversible outputs, so a hard human gate is not required by archetype. |
| 10 | Exit = question | N/A | high | The skill uses staged instructions, but formal binary exit questions are a procedural expectation rather than a creative one. |
| 11 | Output spec | A | high | The output contract is concrete and production-usable: exact artifacts, paragraph counts, fixed-versus-variable UI, required controls, and single-file constraints are all specified. The only reason this is not A+ is t... |
| 12 | Gates = 3 parts | N/A | high | The document has many strong requirements, but explicit three-part quality gates are not expected for the dominant creative archetype. |
| 13 | External storage | N/A | medium | The skill is not clearly beyond the size threshold where prompt/reference externalization becomes mandatory. |
| 14 | Context scope | A | high | Scope is clear and practical: it says what the skill is for, what it is not for, and repeatedly narrows the target to pure generative, process-first work. That clarity would keep most production runs on-track. |
| 15 | Progress | D | high | There are stage labels, but there is no instruction to emit progress updates or checkpoint summaries while executing. In practice the skill would still work, but it gives the host little observability. |
| 16 | Errors | C | high | The skill does name common failure modes through explicit avoid lists, which is better than nothing. It still misses the core requirement: a structured error-to-action mapping with recovery steps. |
| 17 | Autonomy | A- | high | The skill is decisive: it defines defaults, fixed UI, output format, and a clear implementation path without requiring routine human input. The small gap is that it does not specify what to do when the user's brief is... |
| 18 | Path resolution | C | high | Using relative template paths is the right baseline, but the skill does not describe runtime resolution or fallback behavior if those files are missing or located differently. It also names a host-specific tool directly. |
| 19 | Composition | N/A | high | The skill does not declare or invoke other skills, so composition metadata is not in play. |
| 20 | Output-first | B+ | high | Deliverables are stated early, and the rest of the document mostly serves those deliverables. The minor gap is that the most exact output contract appears after substantial process guidance instead of fully up front. |
| 21 | Decision class drives gating | N/A | high | The skill does leave room for taste, but it does not run a procedural decision-class system, which is not expected for its dominant archetype. |
| 22 | Voice + writing rules | A | high | This is one of the strongest parts of the skill. It gives clear prose constraints, repetition rules, anti-redundancy guidance, and tone expectations that materially shape output quality. |
| 23 | Host-portable | C- | high | The produced artifact is portable browser output and the template paths are relative, which helps. But the skill body is still visibly tuned to Claude/Anthropic conventions and names host-specific behavior directly. |
| 24 | Self-observation | N/A | high | Persistent execution analytics and read-back loops are not expected for a creative-dominant generation skill. |
| 25 | Spawn-detection | N/A | high | The skill does not define spawned-agent behavior, but that adaptation is a procedural concern rather than a creative one for this archetype. |


---

# Gemini-3-pro-preview raw outputs (added 2026-04-26)

> Same protocol as the GPT-5.4 section above. Gemini CLI 0.32.1, `gemini-3-pro-preview`, pragmatic-practitioner persona, prompt-engineered JSON (no server-side schema enforcement available in CLI). All 10 calls succeeded on first attempt with no retries.

**Total wall-clock:** 11 min 53 sec (mean ~71 s/call)

---


## 01-obra-tdd

**Archetype:** Hybrid — The skill functions primarily as a Creative behavioral constraint that overrides the AI's default coding persona, while utilizing Reference elements to enforce the Red-Green-Refactor process.

**Aggregate grade:** A- — An exceptionally strong behavioral constraint skill that perfectly leverages tone, anti-patterns, and strict process mapping to combat LLM laziness, only slightly weakened by minor omissions in progress reporting and hardcoded pathing.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A | high | The YAML description explicitly defines when the skill should be triggered (before writing implementation code), acting as clear routing logic rather than a generic tagline. |
| 2 | Route before work | N/A | high | Skill acts as a behavioral constraint and reference, not a sequential procedural pipeline. |
| 3 | Modes | N/A | high | No multiple execution paths or modes exist in this behavioral discipline. |
| 4 | State | N/A | high | Skill dictates real-time coding behavior without requiring durable state across long horizons. |
| 5 | Parallel | N/A | high | No independent subtasks to parallelize. |
| 6 | Personas/voice | A+ | high | Implements an exceptionally strong persona designed to combat AI laziness, utilizing explicit rules, 'Iron Laws', and anti-rationalization tables instead of generic framing. |
| 7 | Files = bus | N/A | high | Not a multi-phase data processing pipeline requiring a file bus. |
| 8 | Synthesis | N/A | high | No parallel subtasks to merge or synthesize. |
| 9 | Human gate | N/A | high | Not a procedural pipeline requiring formal phase gates, though it bounds autonomy via human exceptions. |
| 10 | Exit = question | N/A | high | Not a procedural pipeline with formal phase exits. |
| 11 | Output spec | B+ | medium | Provides clear constraints for the generated code and test outputs using 'Good/Bad' contrasting examples, though it lacks a rigid layout spec for the AI's conversational response. |
| 12 | Gates = 3 parts | N/A | high | Not a sequential pipeline with formal quality gates. |
| 13 | External storage | N/A | high | Skill is under the ~400 line threshold requiring externalized prompts. |
| 14 | Context scope | A | high | Explicitly bounds its own applicability, stating exactly when to apply the rules (Always) and when they can be bypassed (Exceptions). |
| 15 | Progress | C+ | medium | While the skill defines a tight cycle (Red->Verify->Green->Verify) and provides a 'Verification Checklist', it lacks explicit instructions on how to communicate progress to the user during these phases. |
| 16 | Errors | A | high | Includes a highly effective 'When Stuck' error-handling table that maps specific failure states to concrete recovery actions. |
| 17 | Autonomy | A | high | Clearly bounds autonomy by explicitly defining situations where human permission is required, overriding default AI behavior. |
| 18 | Path resolution | C | medium | References an external file but uses a hardcoded relative/at-mention format rather than dynamic runtime resolution or fallback paths. |
| 19 | Composition | N/A | high | Does not explicitly compose or invoke other predefined skills. |
| 20 | Output-first | B | medium | The core output expectation ('The Iron Law') is stated early, though specific code output examples are located midway through the document. |
| 21 | Decision class drives gating | N/A | high | Not a procedural pipeline with decision classification gating. |
| 22 | Voice + writing rules | A+ | high | Masterful integration of tone and voice rules directly into the skill content. The 'Common Rationalizations' table effectively functions as an anti-AI-vocabulary/behavior list. |
| 23 | Host-portable (v0.3) | A | high | Uses standard framework-agnostic commands and avoids hardcoded absolute system paths, ensuring portability across multiple environments. |
| 24 | Self-observation (v0.3) | N/A | high | As a creative/behavioral constraint, it does not persist execution records or analytics. |
| 25 | Spawn-detection (v0.3) | N/A | high | Does not differentiate between spawn and interactive execution contexts. |


## 02-tob-auditor

**Archetype:** Procedural — The skill defines a strict, multi-step execution pipeline (Steps 0-5) to perform an audit, processing inputs sequentially rather than serving purely as an inert reference or a creative guideline.

**Aggregate grade:** C+ — The skill is a robust, well-scoped diagnostic prompt with excellent routing, error handling, and output specs, but it misses several core PaaP architectural requirements (State, Files=Bus, Gates, Self-observation).

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A+ | high | The description clearly specifies exact use cases and the skill includes explicit 'When to Use' and 'When NOT to Use' sections acting as precise routing logic. |
| 2 | Route before work | A | high | Step 0 acts as a routing phase, classifying the input as local or remote and fetching necessary remote context before substantive audit work begins. |
| 3 | Modes | A | high | The skill explicitly defines criteria-driven execution paths (local vs. remote modes) with clear handling for each. |
| 4 | State | C- | high | The skill instructs the agent to 'capture' and 'record' extensive security context across multiple files but fails to mandate writing this state to disk, risking context window degradation. |
| 5 | Parallel | N/A | high | The skill instructs scanning files, but does not dictate launching discrete sub-agents or parallel independent tasks. |
| 6 | Personas/voice | A+ | high | The skill uses 'Rationalizations to Reject' to heavily enforce a strict security auditor persona, grounding the agent in specific behavioral discipline rather than generic 'expert' framing. |
| 7 | Files = bus | F | high | The skill explicitly relies on passing data between steps in-memory ('capture' in Step 3, then 'check each vector against the security context captured in Step 3' in Step 4) instead of using intermediate files. |
| 8 | Synthesis | B+ | high | Step 5 provides detailed, structured rules for synthesizing the raw findings into a cohesive report, including severity grouping and clean-repo edge cases. |
| 9 | Human gate | D | high | The process executes end-to-end without a single 'AskUserQuestion' checkpoint to allow human intervention or validation during the audit. |
| 10 | Exit = question | C | medium | Has binary exit conditions early on ('If no workflow files are found... stop'), but lacks question-based exits between the substantive phases (Step 3 to 4, Step 4 to 5). |
| 11 | Output spec | A+ | high | The output specification in Step 5 is exhaustive, dictating exact headings, section order, severity judgment, and data flow trace formatting. |
| 12 | Gates = 3 parts | F | high | The skill lacks explicit quality gates containing a check, a failure condition, and a recovery path. |
| 13 | External storage | A | high | The skill effectively utilizes external markdown files for granular vector definitions and reference profiles, keeping the core prompt streamlined. |
| 14 | Context scope | A | high | Context scope is strongly defined with explicit instructions on what boundaries to respect during the audit. |
| 15 | Progress | A | high | The skill instructs the agent to emit status updates with quantitative stats after specific checkpoints. |
| 16 | Errors | A | high | Includes a dedicated error handling section mapping specific API failure codes to specific reporting actions. |
| 17 | Autonomy | A | high | The skill defaults intelligently to local mode if an explicit remote URL is not provided, avoiding unnecessary questions to the user. |
| 18 | Path resolution | A | high | Avoids hardcoded absolute paths by using a `{baseDir}` abstraction to resolve external references at runtime. |
| 19 | Composition | N/A | high | The skill operates standalone and does not invoke or compose other agent skills. |
| 20 | Output-first | D | high | The detailed output specification is placed at the very end of the prompt (Step 5) rather than being defined before the workflow phases. |
| 21 | Decision class | F | high | The skill does not categorize decisions into Mechanical, Taste, or User Challenge classes to drive gating behavior. |
| 22 | Voice + writing | B+ | medium | While it lacks a strict 'banned words' list, the reporting format and severity judgment rules implicitly enforce a highly structured, objective tone. |
| 23 | Host-portable | A | high | The skill is portable, specifying standard allowed tools and avoiding OS-specific hardcoded paths. |
| 24 | Self-observation | F | high | The skill contains no mechanism for maintaining a record of its previous executions or learning from them. |
| 25 | Spawn-detection | F | high | The skill lacks any instructions to detect if it was spawned by another agent versus a human user to adapt its output accordingly. |


## 03-anthropic-skill-creator

**Archetype:** Procedural — The skill outlines a complex, multi-step, iterative workflow with explicit phases, parallel execution branching, human gates, and file-based state management.

**Aggregate grade:** B+ — A highly pragmatic, production-ready skill that excels in state management, parallel execution, and host portability, with only minor structural omissions like explicit error tables.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | B+ | high | The description clearly explains when to invoke the skill for various sub-tasks (create, edit, measure, benchmark). It lacks explicit negative triggers (when NOT to use it). |
| 2 | Route before work | A | high | The skill instructs the agent to explicitly determine the user's current stage in the process before starting substantive work. |
| 3 | Modes | B+ | medium | Execution paths branch based on context (new vs. existing skill, Claude.ai vs. Cowork), which act as functional modes, though they aren't formally named 'Modes' in the text. |
| 4 | State | A- | high | The skill heavily relies on writing state to disk, allowing it to seamlessly resume or read past state across different iterations. |
| 5 | Parallel | A+ | high | Provides explicit, forceful instructions to launch baseline and test runs in parallel within the same turn. |
| 6 | Personas/voice | B | medium | Includes guidance on adapting communication based on the user's technical literacy, though it lacks a formalized 'Iron Law' or rejection rationalizations. |
| 7 | Files = bus | A | high | Data, metadata, and evaluations are systematically passed through clearly structured, numbered JSON and Markdown files. |
| 8 | Synthesis | A- | high | Explicitly details how to synthesize parallel run data, both algorithmically (via a python script) and analytically (an 'analyst pass'). |
| 9 | Human gate | A | high | Implements strict waiting periods where human evaluation is irreducible, ensuring the agent halts execution appropriately. |
| 10 | Exit = question | B- | medium | Exits are clear (driven by user feedback files), but they are not framed as strict binary questions for internal phase transitions. |
| 11 | Output spec | A | high | Provides rigorous schemas, formatting templates, and anatomy breakdowns for the generated artifacts. |
| 12 | Gates = 3 parts | B+ | high | The feedback review acts as a gate with a clear check (read feedback), failure condition (specific complaints), and recovery path (focus improvements on those). |
| 13 | External storage | A+ | high | Extensively externalizes subagent prompts and large schemas to reference files, keeping the main skill lean. |
| 14 | Context scope | B | medium | Defines what the skill is for thoroughly, but lacks explicit boundaries on what the skill should explicitly reject or is NOT for. |
| 15 | Progress | A | high | Mandates progress updates to the user during long-running background tasks. |
| 16 | Errors | C- | high | Lacks a structured error table mapping specific failures to specific recovery actions, relying on general prose instead. |
| 17 | Autonomy | A- | high | Guides the agent to proactively suggest defaults, use its own judgment on baseline selection, and draft assertions asynchronously. |
| 18 | Path resolution | A- | high | Uses relative or generated dynamic paths seamlessly, avoiding hardcoded user directories (except standard ~/Downloads). |
| 19 | Composition | C | medium | Mentions using other tools (MCPs) but fails to define them formally in a `composed_skills` YAML block. |
| 20 | Output-first | B- | medium | The exact output specification (SKILL.md anatomy) is buried halfway through the document rather than presented prior to the phase execution. |
| 21 | Decision class | C- | low | Does not classify decisions formally into Mechanical/Taste/Challenge categories, though it implicitly handles taste via human review. |
| 22 | Voice + writing rules | B | medium | Contains excellent guidance on pedagogical theory of mind, though it lacks an explicit list of banned 'AI' phrases. |
| 23 | Host-portable | A+ | high | Flawlessly adapts logic based on the host environment (Cowork vs Claude.ai) with specific feature flagging and workarounds. |
| 24 | Self-observation | A | high | Explicitly loops back to read user feedback from previous executions and carries that context forward into new iterations. |
| 25 | Spawn-detection | N/A | high | The skill is designed strictly for interactive co-development with a human user and is not intended to be spawned headlessly by another agent. |


## 04-tapestry-article-extractor

**Archetype:** Procedural — The skill outlines a multi-step execution workflow for downloading and extracting content, relying on fallbacks and sequential tool execution.

**Aggregate grade:** C — While the skill is a functional and portable shell script wrapper with good error handling, it lacks the structural PaaP disciplines like routing, gating, output-first design, and state observation.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | B+ | high | The YAML description contains clear positive routing indicators, but lacks explicit negative anti-triggers. |
| 2 | Route before work | D | high | The skill jumps directly into tool installation checks and extraction without a preliminary routing, classification, or stop-condition check phase. |
| 3 | Modes | N/A | high |  |
| 4 | State | N/A | high |  |
| 5 | Parallel | N/A | high |  |
| 6 | Personas/voice | F | high | No persona, behavioral discipline, or 'Iron Law' is defined for the agent executing the script. |
| 7 | Files = bus | C | medium | It uses a temporary file to hold intermediate state, but it relies heavily on bash variables rather than a formal numbered file bus architecture. |
| 8 | Synthesis | N/A | high |  |
| 9 | Human gate | C | high | It mentions asking the user if the result looks correct at the end, but lacks an explicit blocking gate before taking irreversible action. |
| 10 | Exit = question | F | high | There are no phase exits defined as binary, answerable questions. |
| 11 | Output spec | B | high | Defines what to include and what to remove in the output, but lacks rigid formatting rules or section constraints. |
| 12 | Gates = 3 parts | C+ | medium | Contains checks and fallbacks for failed extraction, but they are not formalized as explicit 3-part quality gates. |
| 13 | External storage | N/A | high |  |
| 14 | Context scope | B | high | Provides clear scenarios for when to use the skill, but missing explicit negative constraints. |
| 15 | Progress | B- | medium | Instructs the agent to display a success message and preview at the end, but lacks mid-flight progress indicators. |
| 16 | Errors | A- | high | Contains a dedicated Error Handling section that explicitly maps specific failure modes to concrete recovery actions. |
| 17 | Autonomy | B+ | high | Demonstrates strong autonomy via automated tool fallback logic and sensible clean-up defaults. |
| 18 | Path resolution | N/A | high |  |
| 19 | Composition | D | high | Casually references invoking another skill without declaring it in YAML or formalizing the composition path. |
| 20 | Output-first | F | high | The Output Format is defined near the very bottom of the document, after all the extraction methodologies. |
| 21 | Decision class | N/A | high |  |
| 22 | Voice + writing | F | high | No tone, banned phrases, or prose-structure rules are provided. |
| 23 | Host-portable | A- | high | Relies on standard bash commands, uses `allowed-tools`, and dynamically checks for dependencies with `command -v`. |
| 24 | Self-observation | F | high | The skill makes no attempt to observe or record its own executions or learn from past runs. |
| 25 | Spawn-detection | N/A | high |  |


## 05-expo-deployment

**Archetype:** Reference — The skill functions as a static cheat sheet or documentation library for EAS commands and deployment processes rather than an executable, step-by-step procedure or creative guideline.

**Aggregate grade:** D — The skill is a barebones documentation cheat sheet masquerading as an agentic skill; it completely lacks the output specifications, routing constraints, or systemic instructions required by the PaaP rubric.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | D | high | The description is a basic tagline rather than routing logic. It lacks explicit triggers or anti-triggers to tell the harness when NOT to invoke it. |
| 2 | Route before work | N/A | high |  |
| 3 | Modes | N/A | high |  |
| 4 | State | N/A | high |  |
| 5 | Parallel | N/A | high |  |
| 6 | Personas/voice | N/A | high |  |
| 7 | Files = bus | N/A | high |  |
| 8 | Synthesis | N/A | high |  |
| 9 | Human gate | N/A | high |  |
| 10 | Exit = question | N/A | high |  |
| 11 | Output spec | F | high | The skill completely lacks an output specification. It provides commands to the agent but sets zero constraints on how the agent should format or deliver its output to the user. |
| 12 | Gates = 3 parts | N/A | high |  |
| 13 | External storage | N/A | high |  |
| 14 | Context scope | C | high | Briefly states what the skill covers, but entirely lacks explicit anti-scope or what it is NOT for. |
| 15 | Progress | F | high | It does not define any rules or checkpoints for the agent to report progress to the user while employing the reference material. |
| 16 | Errors | N/A | high |  |
| 17 | Autonomy | N/A | high |  |
| 18 | Path resolution | B | high | Uses relative paths appropriately for portability, but fails to define fallback behavior if these referenced files are missing at runtime. |
| 19 | Composition | D | high | References external markdown modules but fails to declare them in the YAML metadata as `composed_skills:` with name, phase, or purpose. |
| 20 | Output-first | F | high | The skill lacks an output specification entirely, making it impossible to adhere to the output-first principle. |
| 21 | Decision class | N/A | high |  |
| 22 | Voice + writing | N/A | high |  |
| 23 | Host-portable | B | medium | Uses relative paths and standard CLI commands, making it generally portable across host environments, though it lacks explicit harness-agnostic design details. |
| 24 | Self-observation | F | high | Does not maintain or read from a record of previous executions or learnings. |
| 25 | Spawn-detection | N/A | high |  |


## 06-kdense-biopython

**Archetype:** Reference — The skill acts as a library/API documentation wrapper for Biopython, intended to be read and searched rather than executed as a step-by-step procedural workflow.

**Aggregate grade:** C — While strong on routing and context scoping, the skill completely ignores universal requirements like output specification, progress reporting, and self-observation.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A+ | high | The description clearly states what the skill is best for and provides explicit anti-triggers, suggesting alternative tools (gget, bioservices) for specific use cases. |
| 2 | Route before work | N/A | high | As a Reference skill, there is no procedural workflow or routing phase prior to work execution. |
| 3 | Modes | N/A | high | The skill does not define different execution modes as it is purely a reference document. |
| 4 | State | N/A | high | Reference skills do not execute long-horizon tasks requiring durable state. |
| 5 | Parallel | N/A | high | There are no procedural subtasks to execute in parallel. |
| 6 | Personas/voice | N/A | high | Reference skills do not typically define personas or behavioral discipline for sub-agents. |
| 7 | Files = bus | N/A | high | There are no multi-phase executions passing data via files. |
| 8 | Synthesis | N/A | high | No parallel subtasks to merge. |
| 9 | Human gate | N/A | high | No procedural execution requiring human judgment checkpoints. |
| 10 | Exit = question | N/A | high | No phases to exit from. |
| 11 | Output spec | F | high | The skill completely lacks an exact format, named sections, or constraints for how the AI should present the synthesized reference information to the user. |
| 12 | Gates = 3 parts | N/A | high | No procedural quality gates exist in a reference skill. |
| 13 | External storage | A | high | The skill correctly offloads detailed module documentation into separate markdown files in a references directory. |
| 14 | Context scope | A | high | The skill provides a clear and explicit 'When to Use This Skill' section that defines its scope. |
| 15 | Progress | F | high | The skill does not instruct the agent to provide progress updates or status reports to the user while performing reference lookups or writing code. |
| 16 | Errors | N/A | high | While there is a troubleshooting section, explicit error tables mapping to agent actions are procedural. |
| 17 | Autonomy | N/A | high | Reference skills are not autonomous execution agents. |
| 18 | Path resolution | C+ | medium | The skill uses relative paths for its references, which is good, but it assumes the runtime execution context will match these paths without providing a robust resolution or fallback mechanism. |
| 19 | Composition | F | high | Although the description mentions other tools (gget, bioservices), the skill lacks explicit YAML composition declarations or runtime resolution for invoking them. |
| 20 | Output-first | F | high | The skill does not define an output specification for the agent to work towards. |
| 21 | Decision class | N/A | high | No procedural gating or decision classification. |
| 22 | Voice + writing rules | N/A | high | Voice and writing rules are generally not applicable for pure reference skills. |
| 23 | Host-portable | A | high | The skill relies on standard shell utilities like grep and python package managers, avoiding hardcoded host-specific absolute paths. |
| 24 | Self-observation | F | high | The skill lacks any mechanism for recording previous executions, maintaining a learnings file, or reading back past mistakes. |
| 25 | Spawn-detection | N/A | high | Reference skills are not typically invoked as autonomous spawned processes needing interactive vs non-interactive detection. |


## 07-chrisvoncsefalvay-d3

**Archetype:** Reference — The skill is a comprehensive library and API documentation for D3.js reformatted as a SKILL.md, designed to be read as reference material rather than executed end-to-end.

**Aggregate grade:** C+ — While the skill functions as an excellent, portable library reference with clear scoping and externalized boilerplate, it falls short on PaaP agentic requirements like upfront output specs, self-observation loops, and robust path resolution fallbacks.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A | high | The YAML description explicitly states what the skill is for (custom charts, complex SVG) and includes routing hints indicating when it should be triggered. |
| 2 | Route before work | N/A | high | This principle does not apply. |
| 3 | Modes | N/A | high | This principle does not apply. |
| 4 | State | N/A | high | This principle does not apply. |
| 5 | Parallel | N/A | high | This principle does not apply. |
| 6 | Personas/voice | N/A | high | This principle does not apply. |
| 7 | Files = bus | N/A | high | This principle does not apply. |
| 8 | Synthesis | N/A | high | This principle does not apply. |
| 9 | Human gate | N/A | high | This principle does not apply. |
| 10 | Exit = question | N/A | high | This principle does not apply. |
| 11 | Output spec | C | high | The skill provides standard structural templates for D3 code but lacks a formal, strict output specification defining exact format, named sections, or anti-templates for the agent's final output. |
| 12 | Gates = 3 parts | N/A | high | This principle does not apply. |
| 13 | External storage | A | high | The skill exceeds 400 lines and successfully delegates extensive boilerplate and patterns to external files in the references/ and assets/ directories. |
| 14 | Context scope | A | high | The skill explicitly defines what it is for (custom visualizations) and sets clear boundaries on what it is NOT for (3D visualizations). |
| 15 | Progress | N/A | high | This principle does not apply. |
| 16 | Errors | N/A | high | This principle does not apply. |
| 17 | Autonomy | N/A | high | This principle does not apply. |
| 18 | Path resolution | C | medium | The skill references external paths relatively, which is good, but it fails to define runtime path resolution or fallback behaviors if those directories or files are missing. |
| 19 | Composition | N/A | high | This principle does not apply. |
| 20 | Output-first | D | high | The skill provides no upfront output specification before diving into the core workflow and reference material. |
| 21 | Decision class | N/A | high | This principle does not apply. |
| 22 | Voice + writing | N/A | high | This principle does not apply. |
| 23 | Host-portable | B+ | high | The skill is inherently portable by avoiding absolute paths and explicitly supporting multiple JavaScript environments, though it lacks explicit harness-agnostic tool configurations. |
| 24 | Self-observation | F | high | The skill lacks any mechanism for recording or reading back its own previous executions, mistakes, or session learnings. |
| 25 | Spawn-detection | N/A | high | This principle does not apply. |


## 08-anthropic-canvas-design

**Archetype:** Creative — The skill is heavily focused on aesthetic judgment, visual output specifications, and voice rules for an artistic persona, rather than strict procedural gates or state management.

**Aggregate grade:** B — A highly effective and richly detailed Creative skill that produces outstanding aesthetic guidelines, though it falls short on robust operational features like explicit progress updates, error handling, and realistic host-tool constraints for graphic rendering.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A- | high | The description clearly defines when to use the skill (posters, art, static pieces) and includes a strong anti-trigger to avoid copying existing artists. |
| 2 | Route before work | N/A | high | Routing before work is a principle specific to the Procedural archetype. |
| 3 | Modes | N/A | high | There are no distinct execution modes required for this linear creative task. |
| 4 | State | N/A | high | State management is specific to long-horizon Procedural skills. |
| 5 | Parallel | N/A | high | The tasks here (philosophy -> canvas -> refinement) are strictly sequential. |
| 6 | Personas/voice | A | high | Provides exceptionally strong and specific persona framing for the creative output, emphasizing master-level craftsmanship and avoiding cartoony aesthetics. |
| 7 | Files = bus | N/A | high | Passing data via numbered files is a Procedural-only principle. |
| 8 | Synthesis | N/A | high | Synthesis rules apply to merging parallel subtasks, which this skill does not have. |
| 9 | Human gate | N/A | high | Human gating checkpoints are a Procedural-only principle. |
| 10 | Exit = question | N/A | high | Phase exits as answerable questions is a Procedural-only principle. |
| 11 | Output spec | A | high | Defines exact file formats (.md, .pdf, .png), layout constraints, and structural requirements for both the text and visual artifacts. |
| 12 | Gates = 3 parts | N/A | high | Quality gates (check + fail + recover) are a Procedural-only principle. |
| 13 | External storage | N/A | high | The skill is well under the ~400 line threshold. |
| 14 | Context scope | B+ | high | Clearly scopes the skill for high-end artistic creation and explicitly bans layouts, templates, and amateur/cartoony outputs. |
| 15 | Progress | D | medium | Fails to instruct the agent to provide any progress updates or intermediate status between the heavily conceptual philosophy stage and the generation stage. |
| 16 | Errors | D | high | Lacks any explicit error handling instructions or tables, particularly concerning graphic generation failures or missing fonts. |
| 17 | Autonomy | A | high | Requires the agent to make highly autonomous, iterative creative decisions, including a mandatory self-reflection pass without user intervention. |
| 18 | Path resolution | B- | medium | References a relative path (`./canvas-fonts`) which is good for portability, but does not provide fallback instructions if the directory cannot be found. |
| 19 | Composition | N/A | high | Composition is for Procedural and Reference archetypes invoking other skills. |
| 20 | Output-first | B | medium | The skill outlines output requirements effectively, though they are somewhat intertwined with the procedural steps rather than strictly front-loaded. |
| 21 | Decision class | N/A | high | Decision classification gating is a Procedural-only principle. |
| 22 | Voice + writing | A | high | Provides rigorous, excellent writing rules for the manifesto, dictating tone, brevity, and focus on visual expression. |
| 23 | Host-portable | C | medium | Instructs the generation of complex visual assets (.pdf/.png) without specifying tool constraints or acknowledging varying host capabilities. It assumes the agent has a 'magic' way to render these on the canvas. |
| 24 | Self-observation | N/A | high | Self-observation is a Procedural and Reference archetype principle. |
| 25 | Spawn-detection | N/A | high | Spawn detection is a Procedural-only principle. |


## 09-anthropic-frontend-design

**Archetype:** Creative — The skill is driven entirely by output specifications, aesthetic voice rules, and qualitative constraints rather than a multi-step procedural workflow.

**Aggregate grade:** B+ — A strong Creative archetype skill that excels at setting qualitative constraints, anti-templates, and a bold persona, but drops points on missing progress reporting and error handling.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A | high | The description clearly defines the exact triggers (build web components, pages, styling) and the specific value proposition (avoiding generic AI aesthetics) to help the harness route requests accurately. |
| 2 | Route before work | N/A | high | Does not apply to Creative archetypes, which are typically single-path output generators. |
| 3 | Modes | N/A | high | The skill has a single, cohesive conceptual path rather than distinct operational modes. |
| 4 | State | N/A | high | Creative generation tasks of this nature do not require durable state or resume protocols. |
| 5 | Parallel | N/A | high | Code generation for a specific UI component or page is inherently linear and does not spawn parallel subtasks. |
| 6 | Personas/voice | A- | high | The skill establishes a strong design persona by dictating bold aesthetic choices and explicitly banning timid or generic defaults. It lacks formal 'Iron Law' tables but effectively achieves the same goal through its ... |
| 7 | Files = bus | N/A | high | Data passing via numbered files is not relevant for a single-phase creative skill. |
| 8 | Synthesis | N/A | high | There are no parallel subtasks that require merging or conflict resolution. |
| 9 | Human gate | N/A | high | Creative generation does not require mid-process human checkpoints for ethics or irreversible actions. |
| 10 | Exit = question | N/A | high | There are no discrete phase exits in this creative skill. |
| 11 | Output spec | B+ | medium | Provides strong qualitative constraints and anti-templates for the output, though it relies on the code itself as the format rather than dictating a strict structural Markdown response. |
| 12 | Gates = 3 parts | N/A | high | The skill does not implement a quality gating system. |
| 13 | External storage | N/A | high | The skill is well under the 400-line threshold and does not require externalizing prompts. |
| 14 | Context scope | A | high | The skill clearly bounds its purpose (creating distinctive frontend interfaces) and explicitly states what it is not for (generic, unopinionated 'AI slop'). |
| 15 | Progress | D | medium | Although labeled Universal, the skill completely omits any instruction for the agent to report its chosen aesthetic direction or plan before dumping code. It largely ignores the principle. |
| 16 | Errors | F | high | There is no error table or error handling instruction for common frontend generation issues (e.g., missing assets, framework conflicts, or unsupported styling properties). |
| 17 | Autonomy | A- | high | Empowers the agent to autonomously commit to an extreme aesthetic and make opinionated design choices without asking the user for permission on every detail. |
| 18 | Path resolution | N/A | high | The skill does not reference external paths or files. |
| 19 | Composition | N/A | high | Creative archetypes do not typically compose other skills. |
| 20 | Output-first | A | high | The entire skill document serves as a detailed qualitative specification for the final output, prioritizing the shape and style of the generated code. |
| 21 | Decision class | N/A | high | No procedural decision gates exist in this skill. |
| 22 | Voice + writing | A+ | high | Exceptional use of anti-patterns and specific stylistic bans. It explicitly lists overused traits to avoid and enforces a strong creative standard. |
| 23 | Host-portable | A | high | The skill is entirely conceptual and structural, containing no host-specific subprocess calls, hardcoded system paths, or harness-dependent logic. |
| 24 | Self-observation | N/A | high | Creative generation tasks generally do not maintain persistent execution logs for self-correction across runs. |
| 25 | Spawn-detection | N/A | high | The skill does not rely on interactive loops or user checkpoints that would need to be suppressed if spawned by another agent. |


## 10-anthropic-algorithmic-art

**Archetype:** Creative — The skill's primary focus is aesthetic output generation (algorithmic philosophy and p5.js art) driven by voice and output specifications rather than a procedural state machine.

**Aggregate grade:** C+ — While the skill excels in voice, persona, and output formatting for its creative task, it misses fundamental PaaP structural requirements like progress updates, error handling, and robust path resolution.

**Per-principle:**

| # | Principle | Grade | Conf | Reasoning |
|:--:|---|:--:|:--:|---|
| 1 | Description as router | A- | high | The YAML description provides clear triggers for when to use the skill and a specific anti-trigger regarding copyright. |
| 2 | Route before work | N/A | high | Not applicable. |
| 3 | Modes | N/A | high | Not applicable. |
| 4 | State | N/A | high | Not applicable. |
| 5 | Parallel | N/A | high | Not applicable. |
| 6 | Personas/voice | A | high | The skill establishes a strong, specialized persona ('jazz musician quoting another song') and mandates master-level craftsmanship. |
| 7 | Files = bus | N/A | high | Not applicable. |
| 8 | Synthesis | N/A | high | Not applicable. |
| 9 | Human gate | N/A | high | Not applicable. |
| 10 | Exit = question | N/A | high | Not applicable. |
| 11 | Output spec | A | high | Provides detailed structural requirements for the HTML artifact, delineating exactly what must be fixed versus variable. |
| 12 | Gates = 3 parts | N/A | high | Not applicable. |
| 13 | External storage | N/A | high | Not applicable. |
| 14 | Context scope | B | medium | Defines the purpose well but lacks explicit boundaries on what the skill should explicitly refuse to do, other than avoiding direct copying. |
| 15 | Progress | F | high | The skill completely lacks instructions for providing status updates or progress milestones during generation. |
| 16 | Errors | F | high | There is no error table or explicit failure handling mechanism defined in the skill. |
| 17 | Autonomy | B | medium | Encourages creative autonomy and establishes sensible defaults, but lacks explicit fallback logic if the user's request is totally ambiguous. |
| 18 | Path resolution | D | high | Hardcodes references to template files without runtime resolution or fallback paths if these files are missing. |
| 19 | Composition | N/A | high | Not applicable. |
| 20 | Output-first | C | high | Outputs are well-defined, but they are presented in the middle of the prompt rather than being specified at the very top before the execution phases. |
| 21 | Decision class | N/A | high | Not applicable. |
| 22 | Voice + writing | A | high | Integrates strong rules regarding redundancy avoidance and framing instructions directly into the skill body. |
| 23 | Host-portable | B | medium | Generally avoids harness-specific commands, but relying on hardcoded relative paths to template files creates a portability risk. |
| 24 | Self-observation | N/A | high | Not applicable. |
| 25 | Spawn-detection | N/A | high | Not applicable. |

