# Agent team

For Mona's Project Pulse dashboard, I will use a custom four-agent team defined under `.github/agents/`. The team will be orchestrated with GitHub Copilot CLI in a Codespace, with the Orchestrator coordinating the work, assigning file scopes, and sequencing each phase before the specialists execute.

## Team overview

- Orchestrator — Model: Claude Opus 4.7 (copilot)
  - Responsibility: coordinate the overall build, break the work into phases, delegate to the right specialist, and verify that the combined result is coherent.
  - Definition: `.github/agents/orchestrator.agent.md`

- Planner — Model: Claude Opus 4.7 (copilot)
  - Responsibility: investigate the codebase and requirements, identify dependencies and edge cases, and create the structured implementation plan for Project Pulse.
  - Definition: `.github/agents/planner.agent.md`

- Coder — Model: GPT-5.5 (copilot)
  - Responsibility: implement the dashboard logic, fix bugs, add app support files when needed, and validate the behavior within the assigned file scope.
  - Definition: `.github/agents/coder.agent.md`

- Designer — Model: Gemini 3.1 Pro (copilot)
  - Responsibility: shape the user experience, information hierarchy, visual design, layout, accessibility, and styling for the Project Pulse interface.
  - Definition: `.github/agents/designer.agent.md`

## How the team will work together

1. The Planner researches the repo and produces the execution plan for Project Pulse.
2. The Orchestrator turns that plan into phases and assigns each specialist a clear file scope.
3. The Designer focuses on the dashboard layout, styling, and UX details.
4. The Coder implements the actual UI structure, logic, and any required app configuration.
5. The Orchestrator checks the integrated result, resolves overlaps, and ensures the whole dashboard is consistent before handing it back.

This division keeps the work organized: planning and coordination happen upfront, implementation happens in parallel where safe, and the final product is verified as one coherent dashboard experience.
