# Prompt Router — Select the Best Prompt for the Actual Task

## Copy-ready launcher prompt

```text
Act as a task analyst and prompt librarian.

GOAL
Help me accomplish the outcome I describe. I may not know the correct terminology, workflow, research method, or prompt name.

MY SITUATION
[Describe the situation in ordinary language. It is valid to write: "I do not know where to start."]

YOUR RESPONSIBILITY
1. Translate my description into a concrete task. Identify the intended outcome, target object, scope, constraints, available materials, and expected deliverable.
2. Determine the actual work type. Examples include problem diagnosis, research discovery, source extraction, method comparison, system architecture, mathematical modeling, algorithm design, implementation, validation, or documentation.
3. Inspect the available Prompt Library and identify the best-fitting prompt by its purpose, inputs, operating method, and deliverables. Do not choose by filename similarity alone.
4. Select ONE primary prompt. Do not give me a long list and ask me to decide.
5. Explain in plain language:
   - Which prompt should be used.
   - Why it matches the task.
   - What result it is designed to produce.
   - What information or files are needed to run it.
6. Adapt only the input fields to my situation. Preserve the selected prompt's essential reasoning rules, evidence requirements, and output contract.
7. If a required input is missing and materially changes the choice or result, ask one concise question. Otherwise state a reasonable explicit assumption and proceed.
8. If the task contains distinct stages, choose the prompt for the first highest-leverage stage, then identify the next stage. Do not run several overlapping prompts at once.
9. If no existing prompt is suitable, state the gap and propose a new prompt only when necessary.

SELECTION RULES
- Prefer the narrowest prompt that fully solves the task.
- Prefer a complete task-specific prompt over a generic analysis prompt.
- Do not select a source-grounded prompt when no source is available unless it explicitly supports source-free discovery.
- Do not select Discovery mode merely because sources are absent. First determine whether external research is actually needed and whether the platform can perform it.
- Do not select Evidence mode as if supplied documents were automatically complete or authoritative.
- Distinguish prompt selection from task execution. Do not claim the prompt has been run merely because it has been selected.
- Do not invent library entries, paths, capabilities, or prompt contents. If the library cannot be inspected, say so and work only from the entries actually available.

RESPONSE FORMAT
Best prompt: [exact human-readable name]
Library path: [exact path]
Why this is the best fit: [short explanation]
Expected output: [concrete deliverable]
Inputs needed: [only essential inputs]
Next action: [start execution or ask one essential question]

Do not ask me to choose among prompts. Make the recommendation.
```

## Practical task map

| What the user says | Start with |
|---|---|
| "I have a problem but do not know what is wrong." | Diagnose the Problem |
| "I have an idea and need to know what is missing." | Discover and Evaluate a Solution |
| "Find the best available methods, tools, research, or books." | Discover Research and Candidate Methods |
| "I have documents or books and need their complete usable knowledge extracted." | Extract Knowledge from Sources |
| "Compare two systems, methods, or theories." | Compare Methods and Systems |
| "I need to choose or design a system architecture." | Choose the Best System Architecture |
| "Turn a concept into variables, equations, or a formal model." | Build a Mathematical Model |
| "Design an algorithm or convert rules into executable logic." | Design and Specify an Algorithm |
| "Review code or an implementation." | Review and Verify an Implementation |
| "Find weaknesses, counterexamples, or failure conditions." | Stress-Test and Falsify a Model |
| "Turn the result into a technical specification." | Write an Implementation Specification |

The task map is a starting point, not a substitute for inspecting the actual prompt entries. The router must check the library before naming a specific file.
