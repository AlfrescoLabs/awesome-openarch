<p align="center">
  <img src="images/banner.svg" alt="Awesome OpenArch" width="800" />
</p>

<p align="center">
  <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg?style=flat" alt="License: CC0 1.0" /></a>
  <a href="https://github.com/AlfrescoLabs/awesome-openarch/actions/workflows/links.yml"><img src="https://github.com/AlfrescoLabs/awesome-openarch/actions/workflows/links.yml/badge.svg" alt="Link check" /></a>
  <img src="https://img.shields.io/badge/Projects-17-38bdf8.svg?style=flat" alt="Projects listed: 17" />
  <a href="https://github.com/AlfrescoLabs/awesome-openarch"><img src="https://img.shields.io/github/stars/AlfrescoLabs/awesome-openarch?style=flat&logo=github" alt="GitHub stars" /></a>
  <a href="https://github.com/AlfrescoLabs/awesome-openarch/commits/main"><img src="https://img.shields.io/github/last-commit/AlfrescoLabs/awesome-openarch?style=flat" alt="Last commit" /></a>
  <a href="https://github.com/AlfrescoLabs/awesome-openarch/discussions"><img src="https://img.shields.io/github/discussions/AlfrescoLabs/awesome-openarch?style=flat&logo=github" alt="Discussions" /></a>
</p>

<p align="center">
  <a href="https://github.com/Hyland/OpenArch"><b>OpenArch</b></a> |
  <a href="CONTRIBUTING.md"><b>Contribute</b></a> |
  <a href="https://github.com/AlfrescoLabs/awesome-openarch/discussions"><b>Discussions</b></a> |
  <a href="https://github.com/topics/openarch"><b>Topic: openarch</b></a>
</p>

A curated list of community projects, integrations and talks built around
[Hyland OpenArch](https://github.com/Hyland/OpenArch).

OpenArch is an open source data layer for AI. It stores content, metadata, permissions and
embeddings from any repository, and answers permission-aware queries, including vector search.

This list only links. Each project lives in its author's repository. Projects listed here are
community work and are not supported by Hyland unless the entry says so.

## Contents

- [Get started](#get-started)
- [The OpenArch ecosystem](#the-openarch-ecosystem)
- [Apps and UIs](#apps-and-uis)
- [Connectors and integrations](#connectors-and-integrations)
- [Storage and server plugins](#storage-and-server-plugins)
- [AI and agents](#ai-and-agents)
- [Partner solutions](#partner-solutions)
- [Talks and recordings](#talks-and-recordings)
- [Contributing](#contributing)

## Get started

| I want to | Start here |
| --- | --- |
| Learn what OpenArch is and run it | [Hyland/OpenArch](https://github.com/Hyland/OpenArch) |
| Try permission-aware RAG on Alfresco or Nuxeo content | [Content Lake App Deployment](https://github.com/AlfrescoLabs/content-lake-app-deployment) |
| Connect a new source to OpenArch | [Sample directory connector](https://github.com/AlfrescoLabs/content-lake-app/tree/main/plugins/examples/sample-directory-connector) |
| See a talk first | [TTL #183 - One Data Layer for AI, Any Repository](https://community.hyland.com/discussion/501550/ttl-183-recording-hyland-openarch-one-data-layer-for-ai-any-repository) |

## The OpenArch ecosystem

Content comes in from repositories and connectors. OpenArch keeps it with its permissions.
Apps and AI agents query it as the signed-in user.

```mermaid
graph LR
    subgraph Sources["Sources and ingestion"]
        ACS[Alfresco]
        NUX[Nuxeo]
        CLA[Content Lake App]
        OC[OpenCrawling]
        SDC[Sample directory connector]
        DS14[14 data sources]
        FGA[Flexible GraphRAG App]
    end

    OA((OpenArch))
    GS[(OpenArch Graph Storage<br/>Neo4j / ArcadeDB)]

    subgraph Apps["Apps, UIs and AI"]
        STU[OpenArch Studio]
        CLUI[Content Lake App UI]
        ACLUI[Alfresco Content Lake UI]
        MCP[Content Lake MCP server]
        NCB[Nuxeo Copilot Bridge]
        KGA[KG Spaces for Alfresco UI]
        KGN[KG Spaces for Nuxeo UI]
        FGUI[Flexible GraphRAG UIs]
        FGMCP[Flexible GraphRAG MCP server]
    end

    ACS --> CLA
    NUX --> CLA
    CLA --> OA
    OC --> OA
    SDC --> CLA
    DS14 --> FGA
    FGA --> OA
    OA -. optional .- GS
    OA --> STU
    OA --> CLUI
    OA --> ACLUI
    OA --> MCP
    OA --> NCB
    FGA --> KGA
    FGA --> KGN
    FGA --> FGUI
    FGA --> FGMCP

    click CLA "https://github.com/AlfrescoLabs/content-lake-app"
    click OC "https://github.com/opencrawling/opencrawling"
    click SDC "https://github.com/AlfrescoLabs/content-lake-app/tree/main/plugins/examples/sample-directory-connector"
    click FGA "https://github.com/stevereiner/flexible-graphrag"
    click OA "https://github.com/Hyland/OpenArch"
    click GS "https://github.com/stevereiner/openarch-graph-storage"
    click STU "https://github.com/haaldinger/openarch-studio"
    click CLUI "https://github.com/AlfrescoLabs/content-lake-app-ui"
    click ACLUI "https://github.com/AlfrescoLabs/alfresco-content-lake-ui"
    click MCP "https://github.com/AlfrescoLabs/content-lake-app"
    click NCB "https://www.prime-force.com"
    click KGA "https://github.com/stevereiner/kg-spaces-aca"
    click KGN "https://github.com/stevereiner/kg-spaces-nuxeo"
    click FGUI "https://github.com/stevereiner/flexible-graphrag"
    click FGMCP "https://github.com/stevereiner/flexible-graphrag"

    classDef source fill:#d1fae5,stroke:#059669,color:#064e3b
    classDef core fill:#38bdf8,stroke:#0369a1,color:#0f172a,font-weight:bold
    classDef app fill:#ede9fe,stroke:#7c3aed,color:#3b0764
    class ACS,NUX,CLA,OC,SDC,DS14,FGA source
    class OA,GS core
    class STU,CLUI,ACLUI,MCP,NCB,KGA,KGN,FGUI,FGMCP app
    style Sources fill:transparent,stroke:#94a3b8,stroke-dasharray:4 4
    style Apps fill:transparent,stroke:#94a3b8,stroke-dasharray:4 4
```

## Status

| Badge | Meaning |
| --- | --- |
| ![Prototype](https://img.shields.io/badge/-Prototype-f59e0b?style=flat) | Try it, expect changes. |
| ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Used in demos or real setups. |
| ![Commercial](https://img.shields.io/badge/-Commercial-2563eb?style=flat) | Partner product, not open source. |

## Apps and UIs

| Project | Author | What it does | Status | License |
| --- | --- | --- | --- | --- |
| [OpenArch Studio](https://github.com/haaldinger/openarch-studio) | Heath Aldinger | AI document workspace: Docling extraction, cited RAG chat, reranked search and a knowledge graph. React + FastAPI, local models, calls OpenArch as the signed-in user. | ![Prototype](https://img.shields.io/badge/-Prototype-f59e0b?style=flat) | Apache-2.0 |
| [Content Lake App](https://github.com/AlfrescoLabs/content-lake-app) | AlfrescoLabs | Syncs Alfresco and Nuxeo content into OpenArch and adds permission-aware RAG on top. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [Content Lake App UI](https://github.com/AlfrescoLabs/content-lake-app-ui) | AlfrescoLabs | Demo UI for the Content Lake App with dual sign-in (Alfresco + Nuxeo). | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [Alfresco Content Lake UI](https://github.com/AlfrescoLabs/alfresco-content-lake-ui) | AlfrescoLabs | UI extension for ACA or ADW to use the Content Lake App from Alfresco. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [Content Lake App Deployment](https://github.com/AlfrescoLabs/content-lake-app-deployment) | AlfrescoLabs | Self-contained Docker deployment for the Content Lake App. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [Flexible GraphRAG App](https://github.com/stevereiner/flexible-graphrag) | Steve Reiner | Python (FastAPI) backend that ingests documents from 14 sources, including Alfresco and Nuxeo, into OpenArch. Adds GraphRAG, hybrid search and AI chat over OpenArch plus property graph and RDF stores. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [Flexible GraphRAG UIs](https://github.com/stevereiner/flexible-graphrag) | Steve Reiner | Angular, React and Vue frontends for the Flexible GraphRAG App. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [KG Spaces for Alfresco](https://github.com/stevereiner/kg-spaces-aca) | Steve Reiner | UI extension for ACA or ADW to use the Flexible GraphRAG App from Alfresco. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [KG Spaces for Nuxeo](https://github.com/stevereiner/kg-spaces-nuxeo) | Steve Reiner | Angular UI companion app for Nuxeo Web UI to use Flexible GraphRAG from Nuxeo. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [KG Spaces Deployment](https://github.com/stevereiner/kg-spaces-deployment) | Steve Reiner | Docker Compose that deploys the Flexible GraphRAG App, Flexible GraphRAG UIs, KG Spaces UIs, OpenArch, and Alfresco and/or Nuxeo. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |

## Connectors and integrations

| Project | Author | What it does | Status | License |
| --- | --- | --- | --- | --- |
| [OpenCrawling](https://github.com/opencrawling/opencrawling) | Piergiorgio Lucidi | Open ingestion platform (Java, Spring AI). The OpenArch integration ([PR #175](https://github.com/opencrawling/opencrawling/pull/175)) adds an output connector with Parquet embeddings, OpenArch as a source and an MCP search tool. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [Sample directory connector](https://github.com/AlfrescoLabs/content-lake-app/tree/main/plugins/examples/sample-directory-connector) | AlfrescoLabs | Minimal example connector for the Content Lake App. Good starting point for a new source. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [Python OpenArch API](https://github.com/stevereiner/python-openarch-api) | Steve Reiner | Python client for the OpenArch REST API: documents by id and path, HXQL query, vector search and aggregations, users and groups, security policies, upload and download. Sync and async clients on httpx, Pydantic v2 models. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |

## Storage and server plugins

| Project | Author | What it does | Status | License |
| --- | --- | --- | --- | --- |
| [OpenArch Graph Storage](https://github.com/stevereiner/openarch-graph-storage) | Steve Reiner | Keeps the OpenArch document tree, versions and ACLs in Neo4j or ArcadeDB instead of MongoDB, so knowledge graph entities can link to documents in the same database. Available as a non-default option in [KG Spaces Deployment](https://github.com/stevereiner/kg-spaces-deployment). | ![Prototype](https://img.shields.io/badge/-Prototype-f59e0b?style=flat) | Apache-2.0 |

## AI and agents

| Project | Author | What it does | Status | License |
| --- | --- | --- | --- | --- |
| [Content Lake App MCP server](https://github.com/AlfrescoLabs/content-lake-app) | AlfrescoLabs | MCP server in `rag-service` with `secureSearch`, `getDocument` and `listSources` tools. ACL-filtered, behind the same auth as the app. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |
| [Flexible GraphRAG MCP server](https://github.com/stevereiner/flexible-graphrag) | Steve Reiner | MCP server (`flexible-graphrag-mcp`) for Claude Desktop and other MCP clients: tools for ingesting, hybrid search and AI query over the Flexible GraphRAG App, with per-user permission filtering. | ![Working](https://img.shields.io/badge/-Working-16a34a?style=flat) | Apache-2.0 |

## Partner solutions

| Solution | Partner | What it does | Status |
| --- | --- | --- | --- |
| [Nuxeo Copilot Bridge](https://www.prime-force.com) | Prime Force | Brings Hyland Nuxeo into Microsoft 365 Copilot over MCP, always as the signed-in user. Its Ask AI feature is built on OpenArch. | ![Commercial](https://img.shields.io/badge/-Commercial-2563eb?style=flat) |

## Talks and recordings

Newest first.

| Event | Talk |
| --- | --- |
| Open Source Conference Luxembourg 2026 | [Sovereign RAG on Your Own Repository: Letting the Search Engine Enforce Permissions](https://pretalx.com/open-source-conference-luxembourg-2026/talk/3Q8XYD/) |
| Hyland Tech Talk Live #183 | [Hyland OpenArch: One Data Layer for AI, Any Repository](https://community.hyland.com/discussion/501550/ttl-183-recording-hyland-openarch-one-data-layer-for-ai-any-repository) |
| Hyland Tech Talk Live #180 | [The Hyland AI Ready Hub: Permission-Aware AI for Alfresco and Nuxeo](https://community.hyland.com/discussion/499982/ttl-180-recordings-the-hyland-ai-ready-hub-permission-aware-ai-for-alfresco-and-nuxeo) |
| Hyland Tech Talk Live #174 | [Hyland's Next Open Source Project](https://community.hyland.com/discussion/495323/ttl-174-recording-hylands-next-open-source-project) |

## Contributing

Found something missing? See [CONTRIBUTING.md](CONTRIBUTING.md), or open a "Suggest a project" issue.
You can also tag your repository with the GitHub topic [`openarch`](https://github.com/topics/openarch)
so others can find it.

## License

This list is released under [CC0 1.0](LICENSE). Each linked project has its own license.
