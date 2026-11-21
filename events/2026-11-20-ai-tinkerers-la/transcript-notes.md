# Edited transcript notes — AI Tinkerers LA (November 20, 2026)

**What this is:** a **speaker-organized, corrected paraphrase** of an imperfect automatic transcript supplied by an attendee. This is *not* a verbatim transcript, recording, or officially approved set of quotations. The original full transcript is deliberately **not** published here because it includes recognition errors and presentations involving children. Where the recording is unclear, we preserve uncertainty rather than inventing detail.

For concise takeaways, use [Executive brief](executive-brief.md); for verified project links, use [Speaker resources](speaker-resources.md). [Event page](https://la.aitinkerers.org/p/ai-tinkerers-la-tinkerers-holiday-party-edition-still-demos).

## Presentation 1 — Greg Schoeninger · Oxen.ai

- Talk theme: multi-model use through an existing AI desktop interface, with Oxen's gateway and Oxen Hitch.
- Demo described routing requests through alternate model/provider endpoints while keeping a familiar front-end.
- Related concerns included dataset management and model fine-tuning, as distinct from the desktop gateway.
- Caveat: desktop configuration and chat history can be affected; a functioning demonstration does not establish official vendor support for every configuration.
- **Resource:** [Oxen Hitch](https://github.com/Oxen-AI/OxenHitch).

## Presentation 2 — Kraig van der Klomp · MonarchWorks

- Talk theme: communication patterns for multiple agents.
- Demo used rock-paper-scissors to show two competing player agents, referee/scoring roles, audience-style agents, and shared messaging.
- He described using an external UI/controller for timing rather than relying on agent-generated internal clocks.
- Agent-triggered messages need filtering, cooldowns and stop conditions to avoid runaway interactions.
- **Resource:** [Centrifugo](https://github.com/centrifugal/centrifugo).

## Presentation 3 — Daniel Ahn · Gallatin AI

- Talk theme: AI agents can be manipulated when they read untrusted text and have authority to act.
- Presenter described a Morse-code-themed prompt-injection/agent-payment example, then demonstrated boundaries for a transaction-capable agent.
- Protections discussed: spending/action limits, recipient allowlists, a broker holding capabilities, pre-registered intent and additional evaluation.
- Treat model-based evaluation as *supporting evidence*, not as sufficient authorization.
- **Resources:** [SweeTrust](https://github.com/sweeai/sweetrust) and [Sui developer documentation](https://docs.sui.io/).
- **Unverified:** exact loss figures and historical attack details in the spoken example are not independently established here.

## Presentation 4 — Joshua Laferriere, M.S. · AI Unified Process

- Talk theme: go beyond vague code prompts by articulating system requirements before implementation.
- Described requirements, entity models, use cases, design, automated tests and traceability.
- Discussed UML-like representations and reverse-engineering existing application behavior.
- **Resources:** [AI Unified Process Marketplace](https://github.com/AI-Unified-Process/marketplace), [GitHub Spec Kit](https://github.com/github/spec-kit), [Sphinx-Needs](https://sphinx-needs.readthedocs.io/en/stable/).
- **Unverified:** several tool names were garbled by speech-to-text; omitted until confirmed.

## Presentation 5 — Sam Wasserman · Imagination Studio

- Talk theme: integrate generative AI with *actual film-production workflows*.
- Started from creative friction including mixed audio stems, difficult editing, acting and camera blocking, continuity and render constraints.
- The shared platform connects project/shot preparation with image, video, voice/audio, local GPU execution and traditional editing.
- He discussed Apple Silicon, NVIDIA DGX Spark, and remote access to local hardware; hardware and speed figures were presenter-reported and configuration-dependent.
- **Resources:** [Imagination Studio](https://github.com/Keys-Wasserman/Imagination-Studio-by-keys-Wasserman) and [ComfyUI](https://github.com/comfyanonymous/ComfyUI).
- **Not known:** whether the audience's live, end-to-end render completed successfully after the transcribed segment.

## Presentation 6 — Sean McDonald · Timepoint AI

- Introduced **Timepoint AI** as simulation/tooling infrastructure accessible through Model Context Protocol (MCP): scenario timelines, historical context, characters and related simulation assets for agents.
- Shifted to a hopeful perspective on AI, supported by family demos of creative coding and an interactive music/synthesizer experience.
- Central idea: new tools can make people more capable and imaginative, not just accelerate professional tasks.
- **Resources:** [Timepoint AI](https://timepointai.com/), [Timepoint MCP](https://timepointai.com/mcp), [Model Context Protocol](https://modelcontextprotocol.io/).
- We deliberately omit children's names, identifying details, photos and direct quotations. The synthesizer's name was not reliable in the automatic transcript.

## Normalizations and source-quality boundaries

| Auto-transcription variants | Normalized concept | Evidence confidence |
| --- | --- | --- |
| “cloud”, “clod” | Claude desktop/software | High contextual confidence |
| “Oxen Hitch” with misheard variations | [Oxen Hitch](https://github.com/Oxen-AI/OxenHitch) | Public repo exists |
| “centrifuge” in the context of the messaging server | [Centrifugo](https://github.com/centrifugal/centrifugo) | Public project exists |
| “Sui / Suvi / Suey” | [Sui](https://docs.sui.io/) blockchain | High confidence |
| “spec kids” and “sphinx knees” | [Spec Kit](https://github.com/github/spec-kit) and [Sphinx-Needs](https://sphinx-needs.readthedocs.io/en/stable/) | Public projects exist |
| “koog”, “coup”, “cube” | Interactive synthesizer demo | **Name not established** |

Other uncertain model/version numbers, timing, exact product prices and sensational exploit figures were not silently corrected or independently repeated as facts.

**Attribution & privacy:** No private messages, attendees' contact details, screenshots of restricted material, unpublished project information, or full event transcript are reproduced. If a presenter finds an error, [submit a correction](../../CONTRIBUTING.md) and we can amend these notes with attribution.
