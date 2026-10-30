# Awesome OpenArch

A curated list of community projects, integrations and talks built around
[Hyland OpenArch](https://github.com/Hyland/OpenArch).

OpenArch is an open source data layer for AI. It stores content, metadata, permissions and
embeddings from any repository, and answers permission-aware queries, including vector search.

This list only links. Each project lives in its author's repository. Projects listed here are
community work and are not supported by Hyland unless the entry says so.

Found something missing? See [CONTRIBUTING.md](CONTRIBUTING.md). You can also tag your repository
with the GitHub topic [`openarch`](https://github.com/topics/openarch) so others can find it.

## Contents

- [Apps and UIs](#apps-and-uis)
- [Connectors and integrations](#connectors-and-integrations)
- [Storage and server plugins](#storage-and-server-plugins)
- [AI and agents](#ai-and-agents)
- [Partner solutions](#partner-solutions)
- [Talks and recordings](#talks-and-recordings)

Status values: **Prototype** (try it, expect changes), **Working** (used in demos or real setups),
**Commercial** (partner product, not open source).

## Apps and UIs

| Project | Author | What it does | Status | License |
| --- | --- | --- | --- | --- |
| [OpenArch Studio](https://github.com/haaldinger/openarch-studio) | Heath Aldinger | Permission-aware AI document workspace on top of OpenArch: Docling extraction, cited RAG chat, reranked search, knowledge graph. React + FastAPI, local models. Calls OpenArch as the signed-in user. | Prototype | Apache-2.0 |
| [Content Lake App](https://github.com/AlfrescoLabs/content-lake-app) | AlfrescoLabs | Syncs Alfresco and Nuxeo content into OpenArch and adds permission-aware RAG on top. | Working | Apache-2.0 |
| [Content Lake App UI](https://github.com/AlfrescoLabs/content-lake-app-ui) | AlfrescoLabs | Demo UI for the Content Lake App with dual sign-in (Alfresco + Nuxeo). | Working | Apache-2.0 |
| [Alfresco Content Lake UI](https://github.com/AlfrescoLabs/alfresco-content-lake-ui) | AlfrescoLabs | UI extension for ACA or ADW to use the Content Lake App from Alfresco. | Working | Apache-2.0 |
| [Content Lake App Deployment](https://github.com/AlfrescoLabs/content-lake-app-deployment) | AlfrescoLabs | Self-contained Docker deployment for the Content Lake App. | Working | Apache-2.0 |

## Connectors and integrations

| Project | Author | What it does | Status | License |
| --- | --- | --- | --- | --- |
| [OpenCrawling](https://github.com/opencrawling/opencrawling) | Piergiorgio Lucidi | Open ingestion platform (Java, Spring AI). The OpenArch integration ([PR #175](https://github.com/opencrawling/opencrawling/pull/175)) adds an output connector with Parquet embeddings, OpenArch as a source and an MCP search tool. | Working | Apache-2.0 |
| [Sample directory connector](https://github.com/AlfrescoLabs/content-lake-app/tree/main/plugins/examples/sample-directory-connector) | AlfrescoLabs | Minimal example connector for the Content Lake App. Good starting point for a new source. | Working | Apache-2.0 |

## Storage and server plugins

| Project | Author | What it does | Status | License |
| --- | --- | --- | --- | --- |
| [OpenArch Graph Storage](https://github.com/stevereiner/openarch-graph-storage) | Steve Reiner | Storage backend that keeps the OpenArch document tree, versions and ACLs in Neo4j or ArcadeDB instead of MongoDB, so knowledge graph entities can link to documents in the same database. | Prototype | Apache-2.0 |

## AI and agents

| Project | Author | What it does | Status | License |
| --- | --- | --- | --- | --- |
| [Content Lake App MCP server](https://github.com/AlfrescoLabs/content-lake-app) | AlfrescoLabs | MCP server in `rag-service` with `secureSearch`, `getDocument` and `listSources` tools. ACL-filtered, behind the same auth as the app. | Working | Apache-2.0 |

## Partner solutions

| Solution | Partner | What it does | Status |
| --- | --- | --- | --- |
| [Nuxeo Copilot Bridge](https://www.prime-force.com) | Prime Force | Brings Hyland Nuxeo into Microsoft 365 Copilot over MCP, always as the signed-in user. Its Ask AI feature is built on OpenArch. | Commercial |

## Talks and recordings

- [Open Source Conference Luxembourg 2026 - Sovereign RAG on Your Own Repository: Letting the Search Engine Enforce Permissions](https://pretalx.com/open-source-conference-luxembourg-2026/talk/3Q8XYD/)
- [TTL #183 - Hyland OpenArch: One Data Layer for AI, Any Repository](https://community.hyland.com/discussion/501550/ttl-183-recording-hyland-openarch-one-data-layer-for-ai-any-repository)
- [TTL #180 - The Hyland AI Ready Hub: Permission-Aware AI for Alfresco and Nuxeo](https://community.hyland.com/discussion/499982/ttl-180-recordings-the-hyland-ai-ready-hub-permission-aware-ai-for-alfresco-and-nuxeo)
- [TTL #174 - Hyland's Next Open Source Project](https://community.hyland.com/discussion/495323/ttl-174-recording-hylands-next-open-source-project)

## License

This list is released under [CC0 1.0](LICENSE). Each linked project has its own license.
