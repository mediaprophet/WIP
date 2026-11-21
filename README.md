# WIP — Work in Progress & Ecosystem Directory

This repository tracks the active architecture, core platforms, libraries, toolchains, semantic namespaces, and asset organizations currently under development across the **QualiaDB / Webizen** human-centric computing ecosystem.

- **Previous Historical Snapshot:** [`20250723_STATUS.md`](20250723_STATUS.md) (July 2025 status archive)
- **Last Updated:** November 2026

---

## Table of Contents

1. [Overview](#overview)
2. [Core Platform & Database Foundation](#1-core-platform--database-foundation)
3. [GPU Compute, Inference Engine, Hardware & Native UI Framework](#2-gpu-compute-inference-engine-hardware--native-ui-framework)
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
The core 30+ crate local-first semantic database, multi-modal reasoning engine, decentralized networking stack, post-quantum cryptographic vault, scientific/simulation substrate, and governed personal AI platform that underpins the entire ecosystem.

- **Semantic Graph, Storage & Query Engine (`q42`, `query`, `container_10d`, `qualia-seal-10d`):**
  - **Unified Q42 v3 Storage:** Compact 48-byte `NQuin` records and memory-mapped `.q42` volumes (`Q42\0`, 256-byte header) with embedded `Q42LEX` lexicon, `BIDX` object-range indexes, field-range/postings indexes, and 40 KiB LZ4 `QualiaSuperBlock`s. Enforces Sanctuary vs. Permissive Commons boundary gates at the storage layer.
  - **SPARQL-Star, GeoSPARQL & QISP:** Full SPARQL 1.1 / SPARQL-Star query and governed UPDATE engine, GeoSPARQL WKT topology/distance operations, QISP (`Tensor10D` vector/tensor distance and within predicates), and RDF/Turtle/TriG/N3/JSON-LD/CBOR-LD (`0xD9 0x0501`) codecs.
  - **Hypermedia & Multi-Scale Containers (`L0`–`L6`):** Native 10D v2 holographic phase-space containers (`.10d` with `HOLO` `0x0306`), `.m64` 64-byte material strata, `.emf` Hilbert field bricks, `.qac` spatial PGA acoustic containers, and `.hmc` (`QBDL`) page-aligned hypermedia bundles across Continuum (`L0`), Rigid/Articulated PGA/XPBD (`L1`), Soft-Body/Fluid (`L2`), Molecular/Chemical (`L3`), Cellular/Biological (`L4`), Ecological/Geomorphic (`L5`), and Quantum Physics & Chemistry (`L6`).

- **Networking, Socially Defined Networking (QDNF) & P2P Fabric (`net`, `p2p`, `qualia-peer`):**
  - **Qualia Decentralized Network Fabric (`net/qdnf`):** Socially Defined Networking separating the **Who-Plane** (`did:qi` / `NaturalAgent`) from the **Handle-Plane** (`DNI` / DNS / IP), featuring `QRoute` (Ed25519 → ULA IPv6 `fd00::/8`), `QResolve`, `QPolicy` deontic policy labels, bearer/session contracts, cell replication, and domain vertical profiles (clinical, biometrics, economics).
  - **$O(1)$ `NQuin` DNS & Native Linux eBPF Firewall (`net/dns`, `ebpf_filter`, `ebpf_firewall`):** Zero-heap `NQuin` DNS cache ring, SDN split-horizon resolution, and kernel/socket eBPF packet filtering and per-sandbox egress byte quota enforcement.
  - **Multi-Transport P2P, Mesh & Privacy Routing (`p2p`, `p2p/connectivity`, `net`):** Userspace WireGuard (`wireguard_userspace`, `wg_engine`), CSCP over HTTP/2 capsules (`cscp_h2`, `h2_capsule`) and WebSockets/TLS (`cscp_wss`, `wss_tls`), ICE/STUN/TURN UDP and NAT64 traversal, SocialWebNet (`social_webnet`, `social_qdnf`), **Nym mixnet** privacy routing (`nym_adapter`), and offline **Acoustic/Ultrasonic + BLE Mesh** networking (`acoustic_ble_mesh`, `sonic_token`).

- **Post-Quantum, Fiduciary & Sanctuary Cryptography (`crypto`, `identity`, `did_qi`):**
  - **Post-Quantum & Hybrid Network Crypto (`crypto/network`):** ML-KEM / Kyber key encapsulation (`kem`, `pq_kem_shim`), ML-DSA post-quantum signatures (`mldsa`), dual classical + PQ signing (`dual_sign`: Ed25519 + ML-DSA), X25519, COSE, secret leases, and automated key rotation.
  - **Homomorphic Encryption, Differential Privacy & Zero-Knowledge (`crypto`):** Real BFV homomorphic encryption, caller-buffered calibrated differential privacy with composition accounting, zero-knowledge predicates and proofs (`zk_predicates`, `zk_proofs`), deontic circuits (`deontic_circuit`), Fiduciary Crypto, and Sanctuary Keychain / tamper-evident Audit DAG (`sanctuary_crypto`, `sanctuary_audit_dag`).
  - **Identifier Fabric (`did_qi`, `identity`):** `did:qi` method (Git-object, relationship-scoped mailbox, and UTXO bindings), Verifiable Credentials, Anvil hardware-attuned vault policies (`anvil_policy`), and compartmentalized access modalities.

- **Multi-Modal Logic, Governance & Semantic Instruments (`modalities`, `governance`, `semantic_instruments`, `qualia-cooperative-core`, `work-graph`):**
  - **40+ Formal Logic & Modality Evaluators:** Deterministic zero-heap Prolog/SLG resolution (42 MiB Sentinel), N3Logic, SHACL, Deontic & Meta-Deontic (`deontic_compose`, `meta_deontic`, `n3_deontic_bridge`), Jural & Legal Composition (`jural`, `legal_compose`), Epistemic, Paraconsistent, Temporal LTL/CTL, STIT ("seeing to it that"), Defeasible, Abductive, Argumentation, Dialectical, Causal, Evidential (`evidential_etau`), Type-1/Type-2 Fuzzy, Linear, Description Logic (`dl`), Answer Set Programming (`asp`), Interval Reasoning, and BFT Consensus.
  - **Semantic Instruments:** Canonical Semantic Instruments (`SI-01..10`) for attestations, rights evaluation, RPL, and value flows; Traditional Knowledge & Biocultural (`TK`/`BC`) labels, illocutionary speech-act records, consent contracts, and law packages.

- **Cooperative Projects, Work-Graph & Nine-Stage Contribution Lifecycle (`qualia-cooperative-core`, `work-graph`):**
  - **Transport-Neutral Cooperative Domain (`COP-01..19`):** Manages shared cooperative projects (`Project`, `ProjectRole`: `Steward`, `Contributor`, `Observer`), work items (`work_item`), agency delegation (`agency_delegation`, `authority_type`), contextual assertions/evidence, and append-only contributor author chains (`predecessor_id`). Effort (integer minutes) and money (signed integer minor units, banker's rounding) merge **add-wins by stable entry ID** rather than raw sum so replayed or out-of-order sync frames can never double-count effort or obligations.
  - **Nine-Stage Contribution, Valuation, Obligation & Licence-Transition Lifecycle (`contribution_lifecycle.rs`):** Implements the formal 9-stage pipeline compiling directly to 48-byte `NQuin`s—from **Stage 1 Request & Agreement** (`Commissioned`, `OpenBounty`, `CooperativeMandate`, `StewardAuthorised`, `UnsolicitedNoAgreement`; `ContractedService`, `AcceptedBounty`, `ConditionalPoolShare`, `ReimbursableExpense`, `VoluntaryCommonsGift`) and **Stage 2 Activity & Resources** (logging effort, reimbursable expenses, and capital advanced without prematurely minting debt) through review/acceptance, obligation derivation, pre-funded credit allocation drawdown, periodic reconciliation, **Two-Loop Permissive Commons** accounting, and verified obligation discharge prior to authorizing a licence transition.
  - **Git & Codebase Work-Graph (`crates/work-graph`):** Extracts Git commit histories, authorship, and work graphs into deterministic `.q42` / `NQuin` provenance records connected to cooperative project ledgers.
  - **M-of-N Cooperative Quorum Governance:** Multi-person cooperative stewardship with a 32-slot `SuspendedTransactionQueue` requiring M-of-N Ed25519 / post-quantum `ML-DSA-65` steward signatures for ratification while retaining paraconsistent dissent records.

- **Governed AI, Prompt Precision & Etalon Inference Bridge (`inference`, `wasm_llm`, `qualia-inference-kernel`, `agent_runtime`):**
  - **Prompt Precision & Model Precision Optimizer:** Token-envelope conditioning runtime, automated precision optimization,LoRA adapters (`lora`), and governed-inference intent validation with N3Logic output gating, provenance grounding, and commit-on-permit sequencing.
  - **Split Inference Architecture (with Etalon):** QualiaDB owns semantic context, `.q42` uncertainty, prompt conditioning, and human-centric policy gates, while delegating low-level GPU/CPU tensor kernels, `.p64`/GGUF model execution, and WGSL Forge shader compilation to **Etalon** (`etalon-inference*`, `etalon-model*`, `etalon-wgsl-forge`), plus pure Rust→WASM browser WebGPU LLM execution with OPFS caching.

- **Scientific Domains, Solvers & Specialized Libraries (`domains`, `solvers`, `specialized_libs`, `qualia-sim`, `qualia-geospatial`, `qualia-q-forge`, `qualia-vision`, `qualia-audio`):**
  - **Computational Geometry & Solvers:** Exact predicates/constructions, 2D/3D Delaunay/hulls, mesh generation/repair/boolean operations, BVH, persistent homology (1,517+ tests), computer algebra & symbolic calculus/ODEs, geometric algebra (PGA), category theory, linear algebra, statistics, and optimization.
  - **Quantum Chemistry & QPU Bridge:** Hartree-Fock (RHF/UHF), Density Functional Theory (DFT with native autodiff), GTO basis sets (STO-3G, def2-SVP, ECPs), Obara-Saika/HGP & Rys quadrature ERIs, DIIS/Broyden SCF, quantum biology, and `qualia-q-forge` DQC/VQE QGroup quantum scheduler.
  - **Vision, Audio, Sim & Domain Modeling:** Multi-physics simulation (`qualia-sim`), geospatial strata/Hilbert indexing (`qualia-geospatial`), computer vision (`qualia-vision`: rPPG pulse, respiration, liveness PAD), spatial HRTF audio (`qualia-audio`), bioinformatics, computational economics, financial modeling, engineering analysis, and medical/clinical computing.

- **Applications, WellFair & Runtime Surfaces (`wellfare-core`, `qualia-anatomy-pack`, `webizen-studio`, `webizen-render`, `webizen-runtime`, `qualia-app-contract`, `qualia-mcp`, `qualia-cli`):**
  - **WellFair (`wellfare-core`):** Personal health, anatomy visualization, clinical/medication records, finance, consent, guardianship, and cooperative support vault.
  - **Studio, Renderer & QApp Contract:** N-dimensional renderer (`webizen-render`), fixed-timestep GPU diffusion runtime (`webizen-runtime`), Webizen Studio Semantic Instruments bay, QApp contract (`qualia-app-contract`), MCP server (`qualia-mcp`), and CLI (`qualia-cli`).
- **Repository:** [github.com/mediaprophet/qualiaDB](https://github.com/mediaprophet/qualiaDB)

---

## 2. GPU Compute, Inference Engine, Hardware & Native UI Framework

### Etalon (`etalon`)
A pure-Rust EMF synthesis, physical sensing, AI inference, and GPU compute/graphics stack (originating from an overhauled fork of `wgpu` 30 and `naga`) designed specifically for QualiaDB, Aether, and Hypermedia Production. Substantive GPU compute, `.p64`/GGUF model execution, shader generation, and hardware sensing capabilities were pushed from QualiaDB into Etalon so accelerator execution stays modular and reusable across the stack.

- **Extracted Inference Engine & Model Runtime (`etalon-inference`, `etalon-inference-kernel`, `etalon-inference-contract`, `etalon-inference-lab`, `etalon-model`, `etalon-model-io`):**
  - Houses the core GPU/CPU inference execution engine, `.p64` and GGUF model I/O, role-tagged layer-packed zero-copy weight loading (with CRC-32C integrity), autoregressive Transformer decode kernels, CPU differential oracles (`max_rel` verification), and runtime accuracy guards.
- **WGSL Forge, Tensor Compute & CUDA/Cooperative Matrix (`etalon-wgsl-forge`, `etalon-tensor`, `etalon-cuda`):**
  - Typed kernel and schedule IR, deterministic compute shader generation, Naga validation, bounded autotuning, pipeline caching, Vulkan cooperative-matrix (`vulkanMemoryModelDeviceScope`) and reduced-precision CUDA WMMA tensor-core GEMM execution, and multi-target translation (WGSL, SPIR-V, HLSL, MSL, PTX, CUDA-C).
- **EMF Synthesis, Physical Sensing & Signal Processing (`etalon-sense`, `etalon-sense-core`, `etalon-sense-runtime`, `etalon-signal`):**
  - Zero-heap caller-buffered physical sensing and signal-processing contracts with dedicated hardware crates for **SDR** (`etalon-sense-sdr`), **Wi-Fi** (`etalon-sense-wifi`), **BLE** (`etalon-sense-ble`), **Cellular** (`etalon-sense-cellular`), **NFC** (`etalon-sense-nfc`), **PC/SC smartcards** (`etalon-sense-pcsc`), **Camera** (`etalon-sense-camera`, `etalon-sense-camera-windows`), **WASAPI Audio** (`etalon-sense-wasapi`), **Windows Sensors** (`etalon-sense-windows-sensors`), and **CPU/GPU telemetry** (`etalon-sense-cpu`, `etalon-sense-gpu`).
- **QualiaDB, VibeScript & Spatial Bridges (`etalon-nquin`, `etalon-vibe`, `etalon-render`, `etalon-sim`, `etalon-reconstruct`, `etalon-agent`, `etalon-resources`, `etalon-diagnostics`, `etalon-qualification`):**
  - Direct 48-byte `NQuin` GPU buffer bindings, VibeScript accelerator SDK bindings, N-dimensional `Tensor10D` and `< 32`-step holographic 10D v2 phase-space raymarching, GPU physics simulation, and 3D reconstruction.
- **Hardened Core Graphics & Shader Stack (`etalon`, `etalon-core`, `etalon-hal`, `etalon-types`, `etalon-naga-bridge`, `naga`):**
  - Unified native (Vulkan, Metal, DirectX 12, GLES) and browser (WebGPU/WebGL2) backends with hardened `wasm32` `pop_error_scope` null handling, automatic `requiredLimits` adapter sanitization, and strict safe-boundary shader validation.
- **Repository & Docs:** [github.com/mediaprophet/etalon](https://github.com/mediaprophet/etalon) | [mediaprophet.github.io/etalon](https://mediaprophet.github.io/etalon/)

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

### Webizen WWW Engine — Servo Fork (`chora` / `chora-engine`)
An independent, embeddable Rust browser engine (**`webizen-WWW-engine`**) for the traditional web (HTML, CSS, JavaScript) and the **read-write web** (W3C Solid / LDP / WebID), forked and detached from upstream [Servo](https://github.com/servo/servo) (`main` snapshot [`79ee827b6a5a60a40cab662223f555528571ebcc`](https://github.com/servo/servo/commit/79ee827b6a5a60a40cab662223f555528571ebcc), 19 October 2026) and used by the **Webizen Web Browser** QApp.

- **Strict MPL-2.0 File-Level Ring-Fence & Naming Boundary (`LICENSE-BOUNDARY.md`):**
  - **Chora** in QualiaDB is the native spatio-temporal commons canvas (`qualia://chora/universe`)—not this HTML engine. This engine's product name is **`webizen-WWW-engine`** (Cargo package `servo`, C ABI `ffi/capi`, transitional `Chora*` / `WwwEngine` embedder types; intended GitHub rename: `WebCivics/webizen-www-engine`).
  - Every source file in this tree remains strictly **MPL-2.0**, ring-fenced from `CC BY-NC-ND 4.0` (and future anti-slavery-licensed) QualiaDB/Webizen/Aether code. Zero `qualia-*` or `webizen-*` crates are linked into the engine; host composition occurs exclusively via an isolated **sibling worker process** (`aether-chora-client` / `aether-chora-bridge-protocol`), generic embedder traits (`WebViewDelegate`, `ProtocolHandler`, `SocialWebBackend`), and the C ABI while its WebGPU backend migrates to Etalon.
- **License-Clean Embedded Feature Profile (`embedded_library`):**
  - Provides a non-viral, license-clean library distribution for embedders by omitting LGPL/GPL GStreamer dependencies (`media-gstreamer`) and selecting the BSD-style FreeType License (`FTL`) for `bundled_freetype`.
- **Post-Quantum TLS 1.3 & Custom Root PKI First:**
  - Prioritizes hybrid post-quantum key exchange (`X25519MLKEM768`) in TLS 1.3.
  - Pluggable root trust management (`RootTrustPolicy::EmbedderRootsOnly`, `EmbedderAndWebPki`, `EmbedderAndPlatform`) with live in-flight root CA reload, mutual TLS (`ResolvesClientCert` / WebID-TLS session reuse), and `EmbedderCertVerifier` supporting Australian (AU) and community root CAs alongside post-quantum (`ML-DSA`) X.509 certificates.
- **Hardware-Backed WebCrypto & Fiduciary/Guardianship Protections:**
  - Delegates non-extractable WebCrypto key operations (`ML-DSA`, `ML-KEM`, `X-Wing`, `Ed25519`, `X25519`) to host hardware or Sanctuary keystores via `EmbedderKeystoreProvider`.
  - Enforces human-rights, fiduciary, and guardianship protections (UDHR, CRC, CRPD) across origin isolation, permission gating, and credential handling across 64-bit Windows, Linux, macOS, Android, and OpenHarmony.
- **Repositories:** [github.com/WebCivics/chora](https://github.com/WebCivics/chora) (`C:\github\chora`) | [github.com/mediaprophet/chora-engine](https://github.com/mediaprophet/chora-engine) | [github.com/mediaprophet/chora](https://github.com/mediaprophet/chora)

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

### Humanitarian Equity Licensing Framework & Human-Centric Rights Fabric (`license`)
The normative legal-technical architecture, rights ontology, contribution-to-licence-transition methodology, and prototype profile validator/document generator for the ecosystem.
- **Purpose & Interim Licensing Transition Architecture (`PROJECT-PURPOSE.md`, `LICENSING-FRAMEWORK.md`):**
  - Explains why ecosystem repositories currently use Creative Commons (`CC BY-NC-ND 4.0`) as an interim measure while constituent capabilities in QualiaDB (logic systems, Context Markup Language, Semantic Instruments, `qualia-cooperative-core`, and settlement ledgers) are completed and qualified.
  - Defines the cooperative production model for humanitarian ICT and collaborative software: recognising contributors' work (research, code, documentation, translation, accessibility, review, coordination, care) and applied resources (compute, model/API costs, hosting, equipment), recording agreed compensation and obligations (`CONTRIBUTION-LIFECYCLE.md`), verifying when obligations are fully discharged, and executing an authorised release decision to transition an identified work or derivative to a new licence.
- **Human-Centric Rights Fabric, Biometrics & Mindware (`PROJECT-PURPOSE.md`, `RIGHTS-ONTOLOGY-AND-INSTRUMENTS.md`, `ontology/rights-instrument-model.ttl`):**
  - Establishes the living **human** as the **principal** in relation to their human agency, rights, identifiers, physiological/behavioural **biometrics**, and **mindware** (the objective and subjective foundations and qualia through which a human experiences reality, develops meaning, forms intentions, and exercises agency—keeping system inferences strictly distinct from the human's lived experience).
  - Requires every software or institutional agent's actual principal and authority to be explicit; evaluates whether an agent has permission to act upon, identify, influence, profile, or represent a human; and ensures scoped identifier grants are never silently expanded.
  - Incorporates **Guardianship & Supported Human Agency** grounded in international instruments (UN CRC Articles 3, 5, 12, 16; UN CRPD Articles 12, 22), distinguishing decision support from representative authority without transferring the principal human's inherent rights.
  - Connects creator economic justice and prevention of digital/informational exploitation ("digital slavery") with **WellFair** (welfare and fairness).
- **Contextual Assertions, Fairness Review & Transborder Frameworks:**
  - **[Contextual Assertions (`CONTEXTUAL-ASSERTIONS.md`)](https://github.com/mediaprophet/license/blob/main/CONTEXTUAL-ASSERTIONS.md):** Separates observations, inferences, allegations, attestations, and adjudicated findings with provenance, bounded use, review, and correction routes.
  - **[Fairness & Rights Review (`FAIRNESS-AND-RIGHTS-REVIEW.md`)](https://github.com/mediaprophet/license/blob/main/FAIRNESS-AND-RIGHTS-REVIEW.md) & [Creator Rights (`CREATOR-RIGHTS-AND-ECONOMIC-JUSTICE.md`)](https://github.com/mediaprophet/license/blob/main/CREATOR-RIGHTS-AND-ECONOMIC-JUSTICE.md):** Evaluates human welfare, economic/ecological/resource burdens, AI-assisted production, and practical remedies.
  - **[OECD Transborder-Data Framework (`OECD-TRANSBORDER-DATA-FRAMEWORK.md`)](https://github.com/mediaprophet/license/blob/main/OECD-TRANSBORDER-DATA-FRAMEWORK.md):** Maps privacy, IP, security, localisation, and international trade-law instruments alongside integrity-checked Web Civics linked-data sources (`OECD-SOURCE-MANIFEST.md`, `WEB-CIVICS-SOURCE-MANIFEST.md`).
- **Prototype Profile Validator, Generator & Draft Instruments (`GENERATOR.md`, `QUALIADB-IMPLEMENTATION-ROADMAP.md`):**
  - Dependency-free Python validator and artifact bundle generator (`license-generator.cmd`, `schemas/license-profile.schema.json`) with `public-inspection` and `controlled-deployment` profiles, provisional RDFS/OWL/SHACL rights ontology (`ontology/rights-instrument-model.ttl`), draft instruments (`INCUBATION-LICENCE-DRAFT.md`, `CONTRIBUTOR-TERMS-DRAFT.md`, `ENFORCEMENT-AND-REMEDIES.md`, `RIGHTS-REGISTER.md`), and the roadmap binding these specifications into QualiaDB.
- **Repository & Public Documentation:** [github.com/mediaprophet/license](https://github.com/mediaprophet/license) | [mediaprophet.github.io/license](https://mediaprophet.github.io/license/)

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

QualiaDB, Webizen, Aether, Etalon, Webizen AI Synth, Hypermedia-Production, Poet, and all Qualia-specific architectures, ontologies, and extensions are governed by:

**Copyright (c) 2026 Timothy Charles Holborn**  
**https://www.linkedin.com/in/ubiquitous/ | timothy.holborn@gmail.com**  
**License:** Attribution-NonCommercial-NoDerivatives 4.0 International (`CC BY-NC-ND 4.0`) unless explicitly covered by a separate component license (such as `MPL-2.0` on the isolated `webizen-WWW-engine` / `chora` repository or preserved upstream `MIT`/`Apache-2.0` notices).

>These projects currently use the Creative Commons licence identified in their licence notices as a temporary alternative while the constituent ecosystem work needed to use the intended licensing and rights fabric is completed. The [`license` project](https://github.com/mediaprophet/license) develops that framework for cooperative and collaborative work, humanitarian ICT, contributor compensation, and accountable licence transitions. Its intended operation depends on related semantic and logic tooling, rights safeguards, contribution and settlement systems, and governance processes that remain in development. Once the required capabilities are ready, adoption will require an authorised decision for identified material; any compensation-based licence transition will also require full satisfaction of its defined agreed obligations. See [Project purpose and ecosystem licensing transitions](https://mediaprophet.github.io/license/) for the rationale and development status.

