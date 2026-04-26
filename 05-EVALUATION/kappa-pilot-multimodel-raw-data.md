# Multi-model Kappa Pilot — Raw GPT-5.4 Outputs

> Verbatim per-principle grades from `gpt-5.4` via Codex CLI, 10 SKILL.md files, `pragmatic-practitioner` persona, `model_reasoning_effort=high`. JSON Schema-validated server-side; no schema-violation retries.

**Date:** 2026-04-26
**Method:** `codex exec --output-schema rubric-schema.json -m gpt-5.4 -c model_reasoning_effort="high"` per skill, sequential.
**Total wall-clock:** 17 min 12 sec (mean 110 s/call)
**Aggregated analysis:** [`kappa-pilot-multimodel.md`](./kappa-pilot-multimodel.md)
**Comparison baseline:** [`kappa-pilot.md`](./kappa-pilot.md) (v0.2 Claude-pragmatic / strict / charitable)

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

