# AI Development Workflow

Use this document with Antigravity or Codex. The agent is a coding assistant; the students remain responsible for the code.

## 1. First prompt for a new workspace

```text
Read AGENTS.md, README.md and all relevant files in docs/.
Do not write code yet.

Summarize:
1. the product goal;
2. the MVP boundaries;
3. the architecture;
4. the current roadmap stage;
5. the constraints you must not violate.

Then propose the smallest first implementation task.
Wait for approval before editing files.
```

## 2. Prompt template for each task

```text
We are implementing Stage [NUMBER] from docs/ROADMAP.md.

Task:
[Describe one specific feature.]

Before coding:
- inspect the existing files;
- explain the implementation plan;
- list files you intend to change;
- identify the JavaScript concepts involved.

Constraints:
- follow AGENTS.md and docs/;
- use HTML, CSS and Vanilla JavaScript only;
- do not implement future stages;
- keep the code understandable to a beginner;
- do not rewrite unrelated working code.

After coding:
- explain the changed functions and data flow;
- provide manual browser test steps;
- report any limitations;
- update documentation if architecture or behavior changed.
```

## 3. Mentor mode prompt

```text
Do not solve this task for me immediately.
Act as a JavaScript mentor for a beginner student.

Explain the problem in simple language.
Give one small hint at a time.
Ask me to predict what the code should do.
Only show a complete solution after I have tried or explicitly ask for it.
Use concepts from our current curriculum.
```

## 4. Code review prompt

```text
Review the current implementation against AGENTS.md and the relevant docs.

Check:
- correctness and edge cases;
- whether the code uses only the approved stack;
- whether game state is the source of truth;
- whether game rules are duplicated in event handlers;
- beginner readability;
- accessibility and console errors;
- whether the relevant acceptance criteria pass.

Do not modify files yet. List findings by severity and suggest the smallest fixes.
```

## 5. Rules for students

- Never accept code that you cannot explain.
- Ask the agent to explain unfamiliar syntax.
- Change one feature at a time.
- Test after every meaningful change.
- Compare the result with the roadmap acceptance criteria.
- If the agent changes architecture, ask why and update the docs only after agreement.
- Do not paste secrets or personal information into prompts.

## 6. Suggested team workflow

1. Teacher selects one roadmap stage.
2. Students discuss the desired behavior before asking AI.
3. AI proposes a plan.
4. Students approve or adjust the plan.
5. AI implements a small part.
6. Students run and test it.
7. Students explain the code to a partner or teacher.
8. Teacher marks the acceptance criteria.
