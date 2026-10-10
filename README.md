# plan-marshall documentation

Every document of [plan-marshall-mcp](https://github.com/plan-marshall/plan-marshall-mcp) (PM-MCP), a local MCP
server that takes over the process logic of plan-marshall through a hypermedia-driven workflow. This repository
holds no code and builds no artifact.

| Document | What it is |
|---|---|
| [Use Cases](doc/UseCases.adoc) | What a person does with the system and gets out of it (`doc/use-cases/`) |
| [Requirements](doc/Requirements.adoc) | The normative requirements (`doc/requirements/`) |
| [Specification](doc/Specification.adoc) | The technical specifications of what is not implemented yet (`doc/specification/`) |
| [Design](doc/Design.adoc) | How the use cases look and behave on the screen (`doc/design/`) |
| [Implementation Watch](doc/ImplementationWatch.adoc) | Defect archetypes and fixtures to guard during implementation (`doc/implementation-watch/`) |
| [Roadmap](doc/roadmap.adoc) | The delivery staging |
| [Concepts](doc/Concepts.adoc) | Why the system is built the way it is |
| [Developer Guide](doc/DeveloperGuide.adoc) | How the implemented system is built, extended and tested |
| [Log Messages](doc/LogMessages.adoc) | The log message reference |

The code lives in [plan-marshall-mcp](https://github.com/plan-marshall/plan-marshall-mcp) (the daemon assembly and
the end-to-end tests), [pm-mcp-core](https://github.com/plan-marshall/pm-mcp-core) (the plain-Java engine),
[pm-mcp-clients](https://github.com/plan-marshall/pm-mcp-clients) (the client contract and the client binaries) and
[pm-mcp-parent](https://github.com/plan-marshall/pm-mcp-parent) (the parent POM).

The documents are proprietary; see [LICENSE.md](LICENSE.md).
