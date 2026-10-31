🇪🇸 [Leer en español](README.es.md)

# Lucas F. Meneses — Engineering Portfolio & Architecture Case Studies

> Software Engineer · Applied AI · Full-stack · Argentina

Welcome to my public architecture and engineering portfolio. This repository documents technical case studies, design patterns, and engineering practices developed across real-world systems, written as a clean-room technical showcase for engineering teams and recruiters.

---

## Portfolio Index

### Architecture Case Studies

| System | Domain & Scope | Highlights | Case Study |
| :--- | :--- | :--- | :--- |
| **Quiddit** | Multi-Provider AI Orchestration & Long-Term Memory | PostgreSQL + pgvector, multi-provider failover (Gemini, Together AI, Ollama), strict JSON-schema outputs, prompt injection defense (XML delimiter isolation + recursive JSON sanitization), local DETR image scrubbing, Docker + Nginx (~60k LOC) | [Read Case Study](case-studies/quiddit.md) |
| **Qvision** | Real-Time Edge Video & Sensor Capture Platform | React Native app with Kotlin native modules capturing video + IMU (100 ms), on-device privacy (TFLite face detection, ML Kit document detection → discard segment & pause), React/Vite/Supabase admin for dataset validation, Roboflow for annotation and YOLO semantic segmentation training (~55k LOC) | [Read Case Study](case-studies/qvision.md) |
| **umi** | On-Device Vision & Document Processing | Flutter MVP, on-device QR + OCR with Google ML Kit, Supabase with Row-Level Security | [Read Case Study](case-studies/umi.md) |

### Engineering Workflows

- **[Agentic Human-in-the-Loop Development](workflow/agentic-development.md)**: A documented methodology for combining AI agents (Claude, Jules/Antigravity, Codex) with engineering discipline, security audits, automated testing gates, and human oversight.

---

## Core Technical Competencies

- **Applied AI & ML Systems**: Multi-provider LLM failover, strict JSON schema output validation, pgvector semantic search, edge vision models (DETR, YOLO semantic segmentation, TFLite, ML Kit).
- **Security & Privacy Engineering**: Multi-stage prompt injection isolation, recursive schema validation, edge redaction and privacy tripwires (local person scrubbing and document/face detection before data leaves devices), Row-Level Security (RLS).
- **Full-Stack & Mobile Architecture**: Node.js/TypeScript services, Flutter, React Native with native Kotlin modules, React/Vite frontends, containerized Docker deployments with reverse proxies.
- **Modern Development Methodologies**: Human-in-the-loop agentic workflows, test-driven merge gates, automated continuous integration, and clean architectural separation.

---

## Design Decisions

1. **Clean-Room Documentation**: All case studies describe architectures, interface boundaries, and operational tradeoffs at the box level. No proprietary business logic, schemas, tokens, or customer data are included.
2. **Edge-First Privacy**: In computer vision and generative systems, sensitive elements are processed locally on the capture edge or local network boundary.
3. **Resilience Through Multi-Provider Redundancy**: Rather than binding flows to a single model vendor, orchestrators are designed with ordered fallback across cloud and local providers.
4. **Strict Schema Constraints**: Model outputs are treated as untrusted input, gated by recursive sanitization and strict JSON schema validators prior to downstream usage.

---

## Quick Start & Navigation

To navigate the repository and inspect the architecture diagrams:

```bash
# Clone the repository
git clone https://github.com/lucasfmeneses/qproject-showcase.git
cd qproject-showcase

# Run markdown validation locally
npm install
npm run lint
```

- Review architectural diagrams in `/case-studies/` (rendered natively on GitHub via Mermaid).
- Review the agentic engineering pipeline in `/workflow/agentic-development.md`.

---

## Limitations

- **Documentation Scope**: This repository serves as a technical architecture portfolio and does not contain proprietary source code, internal dataset weights, or operational credentials.
- **Diagram Abstraction**: Diagrams present box-level subsystem relationships and data flows rather than low-level internal class implementations.

---

## License

This repository is licensed under the [MIT License](LICENSE).
