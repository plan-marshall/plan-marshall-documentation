# plan-marshall documentation

Every document of [plan-marshall-mcp](https://github.com/plan-marshall/plan-marshall-mcp) (PM-MCP), a local MCP
server that takes over the process logic of plan-marshall through a hypermedia-driven workflow. This repository
holds no code and builds no artifact.

| Document | What it is |
|---|---|
| [Use Cases](doc/UseCases.adoc) | What a person does with the system and gets out of it (`doc/use-cases/`) |
| [Requirements](doc/Requirements.adoc) | The normative requirements (`doc/requirements/`) |
| [Specification](doc/Specification.adoc) | The technical specifications of what is not implemented yet (`doc/specification/`) |
| [Engine Specification](https://github.com/plan-marshall/pm-mcp-core/blob/main/doc/Specification.adoc) | The technical specifications of the engine, beside its code in `pm-mcp-core`, with its implementation watch and the traceability of its requirements |
| [Design](https://github.com/plan-marshall/pm-mcp-clients/blob/main/doc/design/README.adoc) | How the use cases look and behave in each client; the specification of the clients, in `pm-mcp-clients` |
| [Implementation Watch](doc/ImplementationWatch.adoc) | Defect archetypes and fixtures to guard during implementation (`doc/implementation-watch/`) |
| [Roadmap](doc/roadmap.adoc) | The delivery staging |
| [Concepts](doc/Concepts.adoc) | Why the system is built the way it is |
| [Developer Guide](doc/DeveloperGuide.adoc) | How the implemented system is built, extended and tested |
| [User Guide](doc/UserGuide.adoc) | How the implemented system is installed, configured and operated |
| [Log Messages](https://github.com/plan-marshall/pm-mcp-core/blob/main/doc/LogMessages.adoc) | The log message reference of the engine, in `pm-mcp-core` |

The code lives in [plan-marshall-mcp](https://github.com/plan-marshall/plan-marshall-mcp) (the daemon assembly and
the end-to-end tests), [pm-mcp-core](https://github.com/plan-marshall/pm-mcp-core) (the plain-Java engine),
[pm-mcp-clients](https://github.com/plan-marshall/pm-mcp-clients) (the client contract and the client binaries) and
[pm-mcp-parent](https://github.com/plan-marshall/pm-mcp-parent) (the parent POM).

The documents are proprietary; see [LICENSE.md](LICENSE.md).
