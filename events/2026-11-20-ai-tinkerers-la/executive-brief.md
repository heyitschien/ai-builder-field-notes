# Executive brief — six AI Tinkerers LA lessons

**Event:** November 20, 2026 at [The KINN, Venice](https://la.aitinkerers.org/p/ai-tinkerers-la-tinkerers-holiday-party-edition-still-demos)  
**Audience:** builders, engineering teams, founders, technical support/implementation practitioners and students.

## The headline

**The hard part of useful AI is increasingly the system around the model.** Across six presentations, the important themes were routing, multi-agent coordination, permission boundaries, explicit specifications, local creative workflow integration, and specialized services through MCP.

| Presenter | Demonstration | Engineering takeaway |
| --- | --- | --- |
| **Greg Schoeninger — Oxen.ai** | Oxen Hitch and model routing in a familiar desktop environment | Keep model selection flexible; distinguish gateways from full agent orchestration |
| **Kraig van der Klomp — MonarchWorks** | Rock-paper-scissors with independent AI agents, referee, scorer and fans | Use a deterministic coordinator, message observability, isolation and loop limits |
| **Daniel Ahn — Gallatin AI** | Attacks on an action-taking agent and authorization protections | Keep irreversible permissions outside the LLM; audit and limit privileged actions |
| **Joshua Laferriere, M.S.** | Requirements-first, use-case-driven software generation | Write explicit behavior and acceptance tests before generating code |
| **Sam Wasserman** | Imagination Studio, a local AI film-production pipeline | Integrate tools around real creator needs: blocking, audio, shots, and editing |
| **Sean McDonald — Timepoint AI** | Simulation assets delivered via MCP and family-led AI coding demos | Specialize agent services; also design AI to encourage human creativity and learning |

## Five practical engineering principles

1. **Model output is not permission.** Validate tool arguments, scope, authorization, and limits in independent code.
2. **Coordination is software engineering.** Give agents separate roles but use external event/timing controls, retries, deduplication, and termination criteria.
3. **Make implementation observable.** Logs should show who requested what, which model/tool acted, and why the operation succeeded or failed.
4. **Specifications make AI work reviewable.** Requirements, user goals, system use cases, and tests should connect.
5. **The real measure is usefulness.** Preserve creative control, operator judgment, handoff, reproducibility, and a path to improvement.

## Suggested experiments (not claims that these were built at the event)

- **Multi-agent message demo:** two workers and an external controller; display event IDs and stop a deliberate repeat-notification loop.
- **Agent safety fixture:** read a malicious sample document and confirm that a policy check blocks a simulated unauthorized action.
- **Spec-to-test comparison:** run the same small feature with and without acceptance criteria; compare defects, rework, and review time.
- **MCP tool call:** connect a narrow simulation or domain service and report assumptions, provenance and uncertainty.
- **Creative workflow test:** select one film-production pain point and check whether local tooling offers real control.

## Choose a starting point

| Need | Public resource |
| --- | --- |
| Model gateway / provider experiments | [Oxen Hitch](https://github.com/Oxen-AI/OxenHitch) |
| Agent event bus | [Centrifugo](https://github.com/centrifugal/centrifugo) |
| Enforced authority and audit receipts | [SweeTrust](https://github.com/sweeai/sweetrust) |
| Specifications and coding agent skills | [AI Unified Process](https://github.com/AI-Unified-Process/marketplace) and [Spec Kit](https://github.com/github/spec-kit) |
| Local creative AI | [Imagination Studio](https://github.com/Keys-Wasserman/Imagination-Studio-by-keys-Wasserman) and [ComfyUI](https://github.com/comfyanonymous/ComfyUI) |
| Agent simulation services | [Timepoint MCP](https://timepointai.com/mcp) |

For presenter-specific explanations, restrictions, and documentation, see [Speaker resources](speaker-resources.md). Talk claims are paraphrased from imperfect attendee notes; independent verification is limited to the linked public projects and event page.
