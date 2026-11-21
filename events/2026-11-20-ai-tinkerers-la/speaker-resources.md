# AI Tinkerers LA — Six demos, open resources, and practical lessons
### Community-share edition | November 20, 2026 · The KINN, Venice, Los Angeles

**Who this is for:** AI developers, founders, students, technical implementers, product teams, and curious builders.  
**Event:** [AI Tinkerers LA — Tinkerers Holiday Party Edition (Still Demos!)](https://la.aitinkerers.org/p/ai-tinkerers-la-tinkerers-holiday-party-edition-still-demos) · [AI Tinkerers LA community](https://la.aitinkerers.org/)  
**Prepared:** November 21, 2026 · Independent recap based on attendee notes, the event program, and linked public project documentation. **Not an official transcript, presenter endorsement, or production-readiness review.**

> **The central theme:** The interesting engineering is increasingly *around* the model: interoperability, coordination, security boundaries, specifications, creative workflows, and domain-specific tools.

## Executive scan

| Presenter | Demonstration | Core lesson |
|---|---|---|
| **Greg Schoeninger** · Oxen.ai | Run alternative AI models through a familiar desktop interface | Separate model access from the workflow and be deliberate about portability |
| **Kraig van der Klomp** · MonarchWorks | Independent agents play rock-paper-scissors through coordinated messages | Multi-agent systems need real-time communication, isolation, timing, and stopping rules |
| **Daniel Ahn** · Gallatin AI / SweeTrust demonstration | Prompt-injection and unauthorized-action attacks against an AI agent | Treat model-generated instructions as untrusted; keep action permissions outside the model |
| **Joshua Laferriere, M.S.** · AI Unified Process | Requirements → entity models → use cases → implementation and tests | Good specifications help make AI-generated software verifiable |
| **Sam Wasserman** · Imagination Studio | Local AI film-production pipeline with planning, generation, and editing tools | Build from actual creative workflow problems, not model novelty alone |
| **Sean McDonald** · Timepoint AI | Simulation services through MCP; creative AI projects with his children | Specialized tools expand what agents can do; AI can also deepen learning and imagination |

## 1 · Greg Schoeninger — Model interoperability with Oxen.ai

**What was shown.** Greg demonstrated **Oxen Hitch**, a menu-bar utility that connects Claude Desktop through Oxen's model gateway, allowing experimentation with models from different providers. Oxen also works on model APIs, fine-tuning, and versioned datasets. This was an experimental integration, not a claim that all model combinations are officially supported by the desktop provider.

**Why it matters.** A product's interface, its model provider, and the surrounding agent workflow are separate concerns. A good integration can allow model choice to evolve without forcing users to rebuild their entire workflow.

**Public resources**
- [Oxen Hitch — public GitHub repository](https://github.com/Oxen-AI/OxenHitch) · [Latest releases](https://github.com/Oxen-AI/OxenHitch/releases)
- [Oxen.ai platform](https://www.oxen.ai/) · [Oxen AI GitHub](https://github.com/Oxen-AI)
- [Oxen Harness — separate agentic coding harness](https://github.com/gschoeni/oxen-harness)

**Useful experiment:** Compare two models on the *same* small tool-calling task, recording output quality, latency, cost, and failure cases. **Caution:** Hitch changes desktop gateway behavior; read its documentation, understand compatibility and credential handling, and protect existing chat data before experimenting. A public repository is not automatically a production-support guarantee.

## 2 · Kraig van der Klomp — Agent communities, timing, and communication

**What was shown.** Kraig used a live **rock-paper-scissors match among LLM agents** built with MonarchWorks' Innovate: independent players, a referee, a scorer, and fans exchanging messages through a shared feed. Behind the entertaining demo were real design questions: who controls the clock, which agent may see which information, how to handle state, and how to stop notifications from triggering endlessly.

**Why it matters.** Giving several models distinct roles is easy; making the system coordinated, observable, restartable, and bounded is substantially harder. The presenter emphasized external coordination and message filtering.

**Public resources**
- [Official AI Tinkerers talk](https://la.aitinkerers.org/talks/rsvp_q8vyo_1hS_I)
- [MonarchWorks Innovate](https://www.monarchworks.ai/innovate/how-it-works) *(commercial/project platform; open-source status not established)*
- [Centrifugo — open-source real-time messaging server](https://github.com/centrifugal/centrifugo) · [Documentation](https://centrifugal.dev/docs/getting-started/introduction)

**Useful experiment:** Create two independent agents and a controller; assign jobs, stream events to a dashboard, and add event IDs, retry limits, permissions, and a deterministic stop condition. Measure whether every action can be explained afterward.

## 3 · Daniel Ahn — How AI agents get fooled, and how to constrain them

**What was shown.** Daniel described a **Grok/agent-payment Morse-code prompt-injection case** and demonstrated attacks against an agent with action-taking abilities. He explored limiting agent authority through an external broker, spending ceilings, recipient allowlists, and checks against the user's original intent. The demonstration connected these ideas to **Sui** and the **Move** smart-contract language.

**Why it matters.** Reading untrusted content and executing a privileged action are fundamentally different trust levels. **An AI agent should not be allowed to grant itself permission**, and an LLM judge alone is not a secure authorization boundary.

**Public resources**
- [Official AI Tinkerers talk](https://la.aitinkerers.org/talks/rsvp_3mPSNFpCvk4)
- [SweeTrust — public TypeScript trust-rails library](https://github.com/sweeai/sweetrust) · [npm package](https://www.npmjs.com/package/sweetrust)
- [Sui blockchain developer documentation](https://docs.sui.io/) · [Sui implementation on GitHub](https://github.com/MystenLabs/sui)

**Useful experiment:** In a *synthetic, no-money* environment, feed an agent a document containing an unauthorized instruction. The agent may propose an action, but an independent policy guard must refuse it and write an auditable reason. Do not equate a successful demo with a security audit.

## 4 · Joshua Laferriere, M.S. — Spec-driven development

**What was shown.** Joshua discussed a requirements-first workflow: define objectives, describe entities and relationships, write business and system use cases, then ask AI tools to implement against those expectations. He also described testability, UML-style modeling, requirements traceability, and learning from reverse-engineering existing codebases. The talk referenced tools such as GitHub Spec Kit, Sphinx-Needs, and AI Unified Process.

**Why it matters.** Coding agents can produce code quickly, but they cannot decide what success means unless the team specifies it. Clear requirements and observable acceptance criteria make code review, regression testing, and handoff easier.

**Public resources**
- [AI Unified Process — methodology](https://unifiedprocess.ai/) · [AIUP Marketplace — open-source agent skills](https://github.com/AI-Unified-Process/marketplace) · [Workflow](https://github.com/AI-Unified-Process/marketplace/blob/main/docs/workflow.md)
- [GitHub Spec Kit — open-source toolkit](https://github.com/github/spec-kit) · [Spec Kit documentation](https://github.github.io/spec-kit/)
- [Sphinx-Needs — requirements management](https://sphinx-needs.readthedocs.io/en/stable/)

**Useful experiment:** On one small bug or feature, write a one-page **user goal → system behavior → acceptance criteria → tests** specification before generating code. Compare the review effort and number of rework cycles with an ad-hoc prompt. Avoid adopting an entire process suite before validating the value.

## 5 · Sam Wasserman — Imagination Studio and practical local AI filmmaking

**What was shown.** Drawing on his filmmaking background, Sam presented **Imagination Studio by keys + Wasserman**: tools for story and shot planning, camera/actor blocking, image and video generation, sound and voice workflows, and optional agent-driven orchestration. The theme was creative control and practical film-production problems, not simply generating clips. The demonstration described remote access to local rendering hardware.

**Why it matters.** The strongest creative AI tools integrate with the way people already work: directing, planning, checking takes, editing, and controlling assets. Running locally can offer control over workflows and assets, but quality, supported hardware, installation complexity, and model licenses still matter.

**Public resources**
- [Imagination Studio — open-source GitHub project](https://github.com/Keys-Wasserman/Imagination-Studio-by-keys-Wasserman) · [Installation guide](https://github.com/Keys-Wasserman/Imagination-Studio-by-keys-Wasserman/blob/main/docs/installation.md) · [User guide](https://github.com/Keys-Wasserman/Imagination-Studio-by-keys-Wasserman/blob/main/docs/user-guide.md)
- [ComfyUI — open-source visual generative-AI workflows](https://github.com/comfyanonymous/ComfyUI)
- [Tailscale — secure networking for remote systems](https://tailscale.com/)

**Useful experiment:** Pick *one* production bottleneck—e.g., storyboard-to-shot continuity or separating dialogue from music—and test a small workflow. Check the repository's current hardware requirements and every model/component license before installing the complete stack.

## 6 · Sean McDonald — Timepoint AI, simulation, and a positive vision of AI

**What was shown.** Sean introduced **Timepoint AI**, which provides simulation and scenario tooling for agents through **Model Context Protocol (MCP)**. Rather than building historical context, characters, timelines and scenario infrastructure on every request, an agent can call a specialized service. He then shared creative coding and interactive music projects with his children, highlighting how AI can support learning, self-expression, and imagination.

**Why it matters.** There are two complementary ideas: **(1)** specialized services can make AI workflows more capable and reusable, and **(2)** technology's value is also in the human creativity it enables. The optimistic, intergenerational message was an important part of the evening.

**Public resources**
- [Timepoint AI](https://timepointai.com/) · [Developer docs and MCP connection](https://timepointai.com/developers) · [MCP overview](https://timepointai.com/mcp)
- [Timepoint Flash — public multi-agent historical-scene repository](https://github.com/timepointai/timepoint-flash) *(review the repository's own license before reuse)*
- [Model Context Protocol — official documentation](https://modelcontextprotocol.io/)

**Useful experiment:** Have an AI assistant call a bounded simulation service and return *assumptions, scenario paths, sources, and uncertainty* rather than a confident prediction. **Licensing note:** Some Timepoint research components are **source-available under Business Source License 1.1**, which is not equivalent to unrestricted open-source licensing. The vendor describes results as simulations, not reported facts.

## Quick resource map: where to start

| If you're interested in… | Start with… | Type |
|---|---|---|
| Model routing / alternate providers | [Oxen Hitch](https://github.com/Oxen-AI/OxenHitch) | Public GitHub project; inspect compatibility/license |
| Coordinating event-driven AI workers | [Centrifugo](https://github.com/centrifugal/centrifugo) | Open source |
| Agent authorization and auditability | [SweeTrust](https://github.com/sweeai/sweetrust) | Open source |
| Requirements-first AI coding | [AIUP Marketplace](https://github.com/AI-Unified-Process/marketplace) · [Spec Kit](https://github.com/github/spec-kit) | Open source |
| Local creative video pipelines | [Imagination Studio](https://github.com/Keys-Wasserman/Imagination-Studio-by-keys-Wasserman) · [ComfyUI](https://github.com/comfyanonymous/ComfyUI) | Open source; separate model licenses |
| Domain-specific simulation agents | [Timepoint AI MCP docs](https://timepointai.com/developers) | Hosted service; some source-available research |

## Three cross-cutting lessons to carry forward

1. **Specify the outcome.** Explain what a workflow should do, what it must never do, and how to tell whether it worked.
2. **Make agents observable and governable.** Capture provenance and actions, set boundaries, prevent feedback loops, and require independent authorization for sensitive effects.
3. **Optimize for useful people-centered workflows.** Whether the user is a developer, filmmaker, analyst, or child learning music, the best tools reduce friction without removing human judgment and creativity.

## Community and attribution

Thanks to the six presenters, [AI Tinkerers LA](https://la.aitinkerers.org/), [Oxen.ai](https://www.oxen.ai/), [Timepoint AI](https://timepointai.com/), and [The KINN](https://www.thekinn.co/) for making the evening possible.

**Source integrity:** This is a concise independent *paraphrase*, not a verbatim transcript. Technical terms were checked against official event pages and public project documentation on November 21, 2026. The talk recordings and live claims were not independently audited. Availability, features, licensing, and prices can change; verify the linked projects before use. No private conversations, unpublished work, confidential diagrams, API keys, or attendee contact information are included.