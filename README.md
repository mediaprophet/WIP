# WIP — Work in Progress & Ecosystem Directory

This repository tracks the active architecture, core platforms, libraries, toolchains, semantic namespaces, and asset organizations currently under development across the **QualiaDB / Webizen** human-centric computing ecosystem.

- **Previous Historical Snapshot:** [`20250723_STATUS.md`](20250723_STATUS.md) (July 2025 status archive)
- **Last Updated:** November 2026

---

## Table of Contents

1. [Overview](#overview)
2. [Core Platform & Database Foundation](#1-core-platform--database-foundation)
3. [GPU Compute, Hardware & Native UI Framework](#2-gpu-compute-hardware--native-ui-framework)
4. [Language & Developer Tooling](#3-language--developer-tooling)
5. [Hypermedia Production, Authoring & Asset Engines](#4-hypermedia-production-authoring--asset-engines)
6. [Operating Environment, Host Infrastructure & Web Engines](#5-operating-environment-host-infrastructure--web-engines)
7. [Semantic Namespaces, Solid Off-Ramp, Civics Platforms & Biomedical Ontologies](#6-semantic-namespaces-solid-off-ramp-civics-platforms--biomedical-ontologies)
8. [Living-World (`intenteco`) & Made-World (`qualia-poiesis`) Asset Organizations](#7-living-world-intenteco--made-world-qualia-poiesis-asset-organizations)
9. [Civic & Civics Scenarios, Simulations & Foundational Modules](#8-civic--civics-scenarios-simulations--foundational-modules)
10. [Licensing & Human-Rights Governance](#licensing--human-rights-governance)

---

## Overview

The **QualiaDB / Webizen** ecosystem is a local-first, Rust- and WASM-native human-centric computing platform designed around a foundational premise: software running on a device has a fiduciary obligation to the **natural person** who owns and operates that hardware. Rather than treating human data, relationships, and creative works as platform-owned telemetry, the stack separates personal **Sanctuary** custody from cooperative **Permissive Commons** publishing, grounded in international human rights instruments (UDHR Article 27(2), ICESCR Article 15(1)(c)), moral rights, and cryptographic identifier separation.

---

## 1. Core Platform & Database Foundation

### QualiaDB (`qualiaDB`)
The core local-first semantic database, reasoning engine, scientific/simulation substrate, and personal AI runtime that underpins the entire ecosystem.
- **Semantic Graph & Storage:** Compact 48-byte `NQuin` records and memory-mapped unified **Q42 v3** volumes (`Q42\0`, 256-byte header) with embedded `Q42LEX` lexicon, `BIDX` object-range indexes, and LZ4 `QualiaSuperBlock` storage.
- **Query & Reasoning:** Live SPARQL 1.1 / SPARQL-Star engine, GeoSPARQL, QISP (`Tensor10D`), deterministic zero-heap Prolog/SLG resolution (42 MiB sentinel), N3Logic, SHACL validation, and deontic/paraconsistent governance rules.
- **Local AI & GPU Inference:** In-process `.p64` / GGUF autoregressive inference and **WGSL Forge** kernel generation without requiring Python or external model servers.
- **Multi-Scale Domains (`L0`–`L6`):** Continuum (`L0`), Rigid/Articulated PGA & XPBD (`L1`), Soft-Body/Fluid (`L2`), Molecular/Chemical (`L3`), Cellular/Biological (`L4`), Ecological/Geomorphic (`L5`), and Quantum Physics & Quantum Chemistry (`L6`).
- **Repository:** [github.com/mediaprophet/qualiaDB](https://github.com/mediaprophet/qualiaDB)

---

## 2. GPU Compute, Hardware & Native UI Framework

### Etalon (`etalon`)
A pure-Rust GPU and compute API (evolved from `wgpu` and `naga`) serving as the required graphics, shader-translation, and compute backbone across QualiaDB, Aether, and Hypermedia Production.
- **Architecture:** Includes `naga` (shader translator), `etalon-core` (validated safe boundary), `etalon-hal` (Vulkan, Metal, DX12, GLES/WebGL2 backends), `etalon-types`, and `etalon-naga-bridge`.
- **Role:** Powers native Vulkan/Metal/DX12 rendering, `< 32`-step holographic 10D v2 phase-space raymarching, and WGSL Forge compute workloads across desktop and browser targets.
- **Repository:** [github.com/mediaprophet/etalon](https://github.com/mediaprophet/etalon)

### Anvil (`anvil`)
Tier-0 `#![no_std]` hardware capability ontology and GPU/NPU instruction router sitting side-by-side with QualiaDB as a hardware enabler for Etalon.
- **Architecture:** `anvil-core` (`#![no_std]`), `anvil-gpu` (adapter report and Naga/WGSL specialization hints), `anvil-npu` (NPU/WebNN graph-slot handles), `anvil-wasm`, and `anvil-scraper`.
- **Role:** Publishes hardware capability facts (`.q42` SuperBlock ontology and 64-byte `NodeProfile64` / `.np64` host profiles) covering GPU/NPU adapter truth, memory/DMA routes, and tiered hardware identifier slots so QualiaDB can enforce Sanctuary vault policies and Etalon can bind optimal shader execution paths.
- **Repository:** [github.com/mediaprophet/anvil](https://github.com/mediaprophet/anvil)

### Aether (`Aether`)
A QualiaDB-native reactive GUI toolkit (forked and overhauled from Dioxus) with `rsx!` declarative components, copyable signals, and `refract` zero-heap lens reactivity.
- **Targets:** Prioritizes production native GPU applications (`packages/native` and `packages/native-dom` via Blitz + AnyRender + Etalon), while supporting Web (WASM), Desktop compatibility (WebView2/Tao), and Mobile targets.
- **Role:** Provides the GUI toolkit consumed by host applications such as `webizen-os-shell`, the Webizen AI Synth operator UI, and Poet.
- **Repository:** [github.com/mediaprophet/Aether](https://github.com/mediaprophet/Aether)

---

## 3. Language & Developer Tooling

### VibeScript Tooling (`vibe-script`)
The developer ecosystem and tooling repository for **VibeScript** (`vibe-0.1` / `v0.02`), the human-centric application and asset scripting language used across Webizen in place of JavaScript/V8 (whose core evaluation engine resides in `qualiaDB/crates/vibe`).
- **Components:** Language Server Protocol (`vibe-lsp`), VS Code extension, Tree-sitter & TextMate grammars, browser playground (`vibe-wasm`), language contracts, and vocabulary documentation across 100+ host capability families.
- **Design North Star:** Deterministic pure vs. capability-leased effect functions (`pure fn` / `effect fn`), hot-editable `.vibe` scripts without forcing host Rust rebuilds, and native CBOR-LD integration.
- **Repository:** [github.com/mediaprophet/vibe-script](https://github.com/mediaprophet/vibe-script)

### Rust Audit (`rust-audit`)
Resumable codebase-to-RDF static analysis and semantic inventory toolchain (`audit` CLI).
- **Pipeline:** Walks Rust, Python, and WGSL workspaces using Tree-sitter (`audit inventory`, `audit scan`, `audit status`), extracting file inventories, doc comments, function signatures, call graphs (`audit:calls`, `audit:callTarget`), and domain classifications into Turtle (`.ttl`) graphs compiled into queryable QualiaDB `.q42` volumes (`audit q42`, `audit query`, `audit compare`, `audit site`).
- **Repository:** [github.com/mediaprophet/rust-audit](https://github.com/mediaprophet/rust-audit)

### Bot Fix (`botfix`)
A planned Windows system tray application for managing the files, hidden state, and conversation/work history left by AI applications and coding agents in a person's home folder, backed by **QualiaDB**.
- **Purpose:** Recovers local storage, preserves useful knowledge and provenance after leaving an AI application or subscription, restores archived files when needed, and makes selected work available across machines on the owner's terms.
- **Accountability & Ontology:** Defines an RDF/SHACL semantic model for sources, conversations, agent handoffs, longitudinal accountability across project history, evaluation profiles, and resource/economic impact assessment on human-rights infrastructure work.
- **Repository:** [github.com/mediaprophet/botfix](https://github.com/mediaprophet/botfix)

### Agentic Testing & Colab Tooling (`agentic-testing-dev` & `colab`)
- **[agentic-testing-dev](https://github.com/mediaprophet/agentic-testing-dev):** Methodologies and harnesses for evaluating and testing AI agent behaviour, compliance, and reliability.
- **[colab](https://github.com/mediaprophet/colab):** High-RAM / GPU burst scripts and Colab execution workflows supporting ecosystem asset generation and large `.q42` compilation tasks.

---

## 4. Hypermedia Production, Authoring & Asset Engines

### Webizen AI Synth (`synth`)
General-purpose VibeScript asset-production library, CLI, MCP server (`synth-mcp`), and Aether desktop operator/studio application.
- **Role:** The development tool for producing, validating, previewing, and compiling 10D v2 holographic assets (`.10d`), material strata (`.m64`), electromagnetic/bio-field bricks (`.emf`), spatial acoustics (`.qac`), semantic knowledge vaults (`.q42`), and sealed Hypermedia Containers (`.hmc`).
- **Capabilities:** Exposes the 150-morphism production catalog (`synth find` / `synth_produce_present` / `synth_compile_q42` / `synth_validate_model` / `synth_convert_3d`), enforcing Holographic 10D v2 primacy (`HOLO` `0x0306`), scale-space harmonic LODs, two-tier constituency (`AREF`/`IOVR`/`INST`), and source-asset licensing verification.
- **Repository:** [github.com/mediaprophet/synth](https://github.com/mediaprophet/synth)

### Hypermedia Production Libraries (`hypermedia-production`)
Shared native Rust domain-engine and authoring libraries consumed by Webizen AI Synth, Poet, and other QualiaDB applications.
- **Scope:** Houses the 150-morphism Vibe operation catalog (`asset-production-vibe`), `.10d` / `.hmc` compilers (`asset-production`), drafting geometry, profile authoring, terrain brushes, raster blend and selection morphology operators, timeline editing, kinetics, acoustics, and radiance modules (indexed via `rust-audit` across `audit-docs/FUNCTIONS.md`).
- **Repository:** [github.com/mediaprophet/hypermedia-production](https://github.com/mediaprophet/hypermedia-production)

### Poet (`poet`)
Unified hypermedia content creation and neuro-symbolic document authoring environment for QualiaDB and Webizen.
- **Functionality:** Converges rich word-processing, spreadsheet/grid computation, presentation slides, 2D/3D media composition, and Context Markup Language (CML) semantic annotations with deterministic Rust/WASM Natural Language Processing (tokenisation, morphological analysis, dependency parsing, and personalised/project ontology enrichment over RDF/`.q42` graphs).
- **Repository:** [github.com/mediaprophet/poet](https://github.com/mediaprophet/poet)

---

## 5. Operating Environment, Host Infrastructure & Web Engines

### Webizen OS-Shell (`webizenai/webizen-os-shell`)
The native spatial desktop and appliance shell built on the **Aether native** toolkit (Blitz + Etalon Vulkan).
- **Features:** Paints the Spatial Halo rail (Humans-first Talk / Mail / Directory, Library, Settings), Etalon Vulkan GPU stage with floating volume cards, and Constellation QApp launcher. Integrates with `webizen-ua-os` to manage Device OS session binding, enumerated cryptographic identifiers, and the local QualiaDB loopback sidecar (`127.0.0.1:4242`).
- **Repository:** [github.com/WebizenAI/webizen-os-shell](https://github.com/WebizenAI/webizen-os-shell)

### Webizen Desktop (`webizenai/webizen-desktop`)
The Tauri v2 desktop harness, window manager, QApp `.qpkg` runtime (`poet`, `webizen-wallet`, `webizen-comms`, `webizen-health`), and local REST/WebSocket companion gateway serving as the read-only behavioural reference for `webizen-os-shell`.
- **Repository:** [github.com/WebizenAI/webizen-desktop](https://github.com/WebizenAI/webizen-desktop)

### Webizen Host (`webizen-host`)
Human-centric Linux VPS hosting platform and decentralized network infrastructure for QualiaDB projects, semantic publishing, and multi-host cooperative operations (`WP-01` – `WP-08`).
- **Architecture:**
  - `webizen-host-core` & `webizen-host-ingest`: 48-byte `NQuin` ABI and bounded streaming compiler for large ontologies (`>100 MB` `WebCivics/ns`) into `.q42` and `.hmc` bundles.
  - `webizen-host-namespace` & `webizen-host-dns`: Zero-heap content-negotiated virtual namespace server (`ns.webcivics.net` v2) with egress circuit breakers, $O(1)$ `NQuin` DNS zone ring, deontic split-horizon firewall, and Dual-Stack QDNF.
  - `webizen-host-sandbox` & `webizen-host-stewardship`: Three-tier multi-tenant sandbox (VibeScript, Portable QApps/WASM, Solid LDP Pod bridge) and Who-Plane (`NaturalAgent`) vs. Handle-Plane separation with Sanctuary Keep / Permissive Commons stewardship modes.
  - `webizen-host-qcdn`, `webizen-host-economics` & `webizen-host-workbench`: Three-layer user-powered `Q-CDN` swarm, Two-Loop Permissive Commons settlement router (`QualiaPQ-Ledger`), and Poet Host Admin Workbench organized around Webizen's Six Life Domains.
- **Repository:** [github.com/mediaprophet/webizen-host](https://github.com/mediaprophet/webizen-host)

### Webizen WWW Engine (`chora`)
The Servo-derived (`MPL-2.0`) traditional web (HTML/CSS/JS) browser engine repository used as an isolated sibling worker process for the **Webizen Web Browser** QApp.
- **Boundary Note:** Kept strictly separate in workspace and licensing from QualiaDB's native **Chora** spatio-temporal commons canvas (`qualia://chora/universe`). Interfaces with Aether/Webizen exclusively through generic IPC/copied-frame embedding boundaries while migrating its WebGPU backend to Etalon.
- **Repository:** [github.com/WebCivics/chora](https://github.com/WebCivics/chora)

---

## 6. Semantic Namespaces, Solid Off-Ramp, Civics Platforms & Biomedical Ontologies

### Web Civics Ontology Namespace (`ns`)
The foundational semantic registry and content-negotiated ontology directory (`ns.webcivics.net`) for human-centric systems.
- **Scope:** Codifies international human rights instruments (UN, UNESCO, ILO), fundamental freedoms, modalities of human agency, Context Markup Language (CML) schemas, and `NQuin` structures—distinguishing grassroots **Civics** (the generative activity of natural persons establishing mutual agreements) from institutional **Civic** artifacts.
- **Repository:** [github.com/WebCivics/ns](https://github.com/WebCivics/ns)

### Solid Interoperability, Databox & Off-Ramp (`web.civics.au` & Solid Suite)
W3C Solid / Linked Data Platform (LDP) Pod infrastructure and interoperability baseline providing a standards-compliant **off-ramp** and portability bridge for QualiaDB users into generic Solid-based ecosystems.
- **Role:** Ensures users are never locked into QualiaDB's native `.q42` binary runtime. Through `qualia-solid-bridge` and `webizen-host-sandbox` (Tier 3 Solid LDP Pod bridge), personal, family, and cooperative data can traverse a strict W3C Turtle / RDF ↔ 48-byte `NQuin` translation boundary, enabling export, migration, or dual operation with generic MIT-licensed W3C Solid pods.
- **Supporting Repositories:**
  - **[Solid-CSS-Databox](https://github.com/mediaprophet/Solid-CSS-Databox):** Web Civics Databox built by refactoring and extending Community Solid Server (CSS) into a decentralised community of personal, family, and organisational data vaults ([Live Demo](https://mediaprophet.github.io/Solid-CSS-Databox/)).
  - **[solid-databox](https://github.com/mediaprophet/solid-databox):** Secure, two-way Solid data exchange point between organisations and the people they serve, with verifiable receipts and provenance (pairing the `Seraphim` consumer agent with organisational `Admin` / `Forge` / `Smithy` consoles).
  - **[solid-ckan](https://github.com/mediaprophet/solid-ckan):** W3C Solid integration and extension for CKAN open-data portals.
  - **[soliddev-agent-helper](https://github.com/mediaprophet/soliddev-agent-helper):** Comprehensive W3C Solid and Semantic Web knowledge base and system prompts for AI coding assistants (Solid Protocol, WebID, WAC/ACP, Auth, and RDF notifications).
- **Endpoint:** [https://web.civics.au](https://web.civics.au)

### Civics Evidence, Community Grounds & Observatory (`dev.civics.au` / `observatory.civics.au` / `www.civics.au`)
Applied Australian civics research, community site-planning tools, evidence graphs, and cooperative systems modeling that also ground the scenarios in Ecopunk and Maslow's Challenge (`game-demo`).
- **Scope & Modules:**
  - **Planning & Outcomes (`/analysis`):** Area-level (LGA) public context covering housing, services, work, education, tourism, business, retirement, and community safety.
  - **Community Site Planner (`/site-planner`) & Modelling Lab (`/model`):** Community Grounds site layouts, load profiles, financial sustainability, solar/battery microgrids, water/thermal balances, and Walkabout mobile rig/fit-out pathways.
  - **Food & Health Evidence (`/food-health`):** Reviewed linked-data graph of normalised foods, ingredients, and meal options with evidence tiers, provenance, and trade-offs.
  - **Databox, Data-Safe & Community Ledger (`/databox`):** Governed disclosure flows, scoped permission receipts, and cooperative project contribution accounting, paired with **`observatory.civics.au`** as the RDF/`.q42` data registry.
- **Repositories & Endpoints:** [https://dev.civics.au](https://dev.civics.au) | [github.com/mediaprophet/observatory.civics.au](https://github.com/mediaprophet/observatory.civics.au) | [github.com/mediaprophet/www.civics.au](https://github.com/mediaprophet/www.civics.au) | [github.com/mediaprophet/civics.au](https://github.com/mediaprophet/civics.au) | [github.com/mediaprophet/au-legislation](https://github.com/mediaprophet/au-legislation)

### Humanitarian Equity Licensing & Rights Fabric (`license`)
Methodology, legal/technical rights model, and prototype document generator for the **Humanitarian Equity Licensing Framework** and **WellFair** human-centric rights fabric.
- **Scope:** Connects copyright with contract and international trade law, human dignity, privacy, and personhood. Recognises contributors' work and applied resources across cooperative and humanitarian ICT projects so agreed obligations can be recorded, compensated, and discharged before transitioning a work's licence. Establishes the individual human as the **principal** over their agency, identifiers, biometrics, and **mindware**.
- **Repository & Site:** [github.com/mediaprophet/license](https://github.com/mediaprophet/license) | [mediaprophet.github.io/license](https://mediaprophet.github.io/license/)

### Anatomy & Medical Atlas (`anatomy` & `ontology/biomedical`)
Anatomical and human-welfare Hypermedia (`.hmc` / `.10d` / `.q42`) modeling and biomedical ontology integration.
- **Scope:** Combines adult male, adult female, and gestational developmental welfare schematics (`human-welfare.hmc`) with a high-resolution signed-distance-field Medical Atlas (starting with Visible Human cervical vertebrae C1/C2, RDFS/SHACL terminology shapes, and N3Logic rules grounded in FMA 5.0.0, Uberon, ICF, COGAT, SNMI, PMO, AISM, and PHAGE).
- **Repository:** [github.com/mediaprophet/anatomy](https://github.com/mediaprophet/anatomy)

### Webizen Public Website (`webizen-website`)
Editorial content, interactive natural-world exhibition design, 150-operation capability inventory, Infosphere Lab demonstration catalog, and observer-relative `.q42`/Vibe path architecture for the public Webizen presence.
- **Repository:** [github.com/mediaprophet/webizen-website](https://github.com/mediaprophet/webizen-website)

---

## 7. Living-World (`intenteco`) & Made-World (`qualia-poiesis`) Asset Organizations

The ecosystem enforces a strict ontological and organizational boundary (`DOM-AX-1`) between living biosphere taxa and human-manufactured artefacts:

### IntentEco — Living Biosphere Taxa (`eco-intent` / `github.com/intenteco`)
One-repository-per-species Hypermedia (`.hmc`) digital twins of flora, fauna, fungi, and ecological communities governed under the **Social Permissive Commons (`SPC`)**.
- **SE Australian Canopy & Fauna Cohort (`ECO-WP-01..13`):**
  - *Flora:* `eucalyptus-camaldulensis` (River Red Gum), `eucalyptus-dalrympleana` (Mountain White Gum), `eucalyptus-regnans` (Mountain Ash), `eucalyptus-melliodora` (Yellow Box), `banksia-integrifolia` (Coast Banksia), `acacia-pycnantha` (Golden Wattle), `dicksonia-antarctica` (Soft Tree Fern), `bursaria-spinosa`, `lomandra-longifolia`, `poa-labillardierei`, `themeda-triandra`, `anigozanthos-manglesii`, `atriplex-nummularia`, `callistemon-sieberi`, `corymbia-aparrerinja`, `xanthorrhoea-australis`.
  - *Fauna & Hominid:* `wallabia-bicolor` (Swamp Wallaby), `phascolarctos-cinereus` (Koala), `vombatus-ursinus` (Bare-Nosed Wombat), `macropus-giganteus` (Eastern Grey Kangaroo), `ornithorhynchus-anatinus` (Platypus), `dacelo-novaeguineae` (Laughing Kookaburra), `corvus-coronoides`, `varanus-varius`, `iridomyrmex-purpureus`, `homo-sapiens`.
- **Groundcover Cohort (`groundcover-pipeline` / `WEB-WP-16G`):** 13 native and naturalised SE Australian grasses, herbs, and flowers (`austrostipa-scabra`, `bulbine-bulbosa`, `chrysocephalum-apiculatum`, `dichondra-repens`, `hypochaeris-radicata`, `lolium-perenne`, `microlaena-stipoides`, `microseris-walteri`, `plantago-lanceolata`, `rytidosperma-caespitosum`, `taraxacum-officinale`, `trifolium-repens`, `wahlenbergia-capillaris`).
- **Organization:** [github.com/intenteco](https://github.com/intenteco)

### Qualia Poiesis — Made-World Artefacts & Works (`poiesis` / `github.com/qualia-poiesis`)
One-repository-per-artefact Hypermedia (`.hmc`) digital twins for human-made vehicles, buildings, off-grid infrastructure, tools, and creative/intellectual works (`made:*` and `soc:*`).
- **Hub & Standards:** [`poiesis/website`](https://github.com/qualia-poiesis/website) — Governing 7-layer (`L0`–`L6`) production specification, SHACL gates, and 193-row dossier templates.
- **Active Made-World Repositories (`C:\github\poiesis\*`):** `commons-rig-workshop`, `community-civic-hall`, `community-grounds-growing-station`, `community-mesh-comms-mast`, `electric-canal-narrowboat`, `farmers-market-harvest-stall`, `foldout-camp-shelter-trailer`, `offgrid-solar-battery-station`, `rover-field-utility-4wd`, `station-wagon-field-car`, `timber-storage-barn`, `timber-truss-footbridge`, `touring-campervan`, `windpump-water-tank-tower`.
- **Organization:** [github.com/qualia-poiesis](https://github.com/qualia-poiesis)

---

## 8. Civic & Civics Scenarios, Simulations & Foundational Modules

### Ecopunk (`ecopunk`)
Specification, production backlog, semantic agreement architecture, and master dossier governing high-grade biosphere and civics-experience embodiments, cooperative Permissive Commons contribution accounting, and Poet/Craft authoring consolidation.
- **Repository:** [github.com/mediaprophet/ecopunk](https://github.com/mediaprophet/ecopunk)

### Maslow's Challenge / Game Demo (`poiesis/game-demo`) & Talbingo Continuum (`talbingo`)
- **[game-demo](https://github.com/mediaprophet/game-demo) (Maslow's Challenge):** Browser-first WASM interactive SDG simulation and epistemic spatial systems runtime built alongside `dev.civics.au` and QualiaDB (`QualiaPortal` volumetric 3D rendering). Unifies narrative exploration, empirical ecological datasets, engineering digital twins, modal/deontic counterfactual modeling, and bilateral micro-commons stewardship (Kestrel Flats / Saltwind Reach campaign and Talbingo campground drive prototype).
- **[talbingo](https://github.com/mediaprophet/talbingo) (Talbingo Regional Continuum & Biological Education Architecture):** High-fidelity scientific digital twin of the 17.5+ km Snowy Mountains Highway (B72) corridor within Kosciuszko National Park (Blowering Reservoir at 385 m AHD to Kiandra plateau at 1,410 m AHD), pairing continuous 64 Hz 4WD rover and bushwalker exploration with a 5-scale botanical (`PO:`) and zoological (`UBERON:`) educational dissection pipeline.

### Foundational & Earlier Modules (from [`20250723_STATUS.md`](20250723_STATUS.md))
Earlier research, specification, and prototype repositories whose concepts now feed into QualiaDB, Poet, and Webizen Host:
- **[humanitarian-equity-framework](https://github.com/mediaprophet/humanitarian-equity-framework):** Standards, methodologies, and semantic instruments for promoting equity and fairness in humanitarian and cooperative commons initiatives.
- **[semantic-tokens-xec](https://github.com/mediaprophet/semantic-tokens-xec)** & **[xec-slp-rdf](https://github.com/mediaprophet/xec-slp-rdf):** Semantic token and RDF ledger representations informing native semantic instruments and multi-rail settlement.
- **[markdown-ld-star](https://github.com/mediaprophet/markdown-ld-star)** & **[obsidian-semantic-weaver](https://github.com/mediaprophet/obsidian-semantic-weaver):** Linked Data (RDF-Star) Markdown annotations and knowledge-graph weaving informing Poet's Context Markup Language (CML).
- **[gitmark-xec-vscode](https://github.com/mediaprophet/gitmark-xec-vscode):** Verifiable commit and contribution tracking concepts informing Permissive Commons provenance.
- **[init-draft-standards-wip](https://github.com/mediaprophet/init-draft-standards-wip)**, **[socialweb planningdocs](https://github.com/mediaprophet/socialweb/tree/main/planningdocs)**, **[SocialWeb-XEC](https://github.com/mediaprophet/SocialWeb-XEC)**, **[Webcard](https://github.com/webcivics/Webcard)**, **[webizen-dev](https://github.com/WebizenAI/webizen-dev)** & **[webizen-app-docs](https://github.com/WebizenAI/webizen-app-docs):** Early draft standards, social web architecture notes, digital profile cards, and first-generation Webizen prototypes.

---

## Licensing & Human-Rights Governance

QualiaDB, Webizen, Aether, Webizen AI Synth, Hypermedia-Production, Poet, and all Qualia-specific architectures, ontologies, and extensions are governed by:

**Copyright (c) 2026 Timothy Charles Holborn**  
**https://www.linkedin.com/in/ubiquitous/ | timothy.holborn@gmail.com**  
**License:** Attribution-NonCommercial-NoDerivatives 4.0 International (`CC BY-NC-ND 4.0`) unless explicitly covered by a separate component license (such as `MPL-2.0` on the isolated `chora` web engine or preserved upstream `MIT`/`Apache-2.0` notices).
