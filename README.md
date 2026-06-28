![preview](https://raw.githubusercontent.com/animetanver-commits/fabric-unified-data-blueprint/main/preview.svg)

# Unified Data Intelligence Platform with Fabric & Open-Source Extensions

## Overview

In the modern enterprise, data is not merely a resource—it is the living nervous system of the organization. Yet, most data platforms remain fragmented, with isolated lakes, incompatible pipelines, and governance gaps that silently drain value. The **Unified Data Intelligence Platform with Fabric & Open-Source Extensions** reimagines this landscape as an interconnected, self-healing architecture that adapts to your workflows rather than forcing your workflows into rigid structures.

This solution accelerator provides a cohesive foundation built on Microsoft Fabric, while offering seamless integration points for **Azure Databricks** for advanced analytics and **Microsoft Purview** for unified governance. Unlike traditional siloed approaches, this repository implements a **polyglot data mesh**—a design where each domain owns its data product, yet all domains speak the same governance language.

The core innovation lies in its **dual-lane ingestion pattern**: real-time streaming data flows through Fabric's Eventhouse while batch historical data is orchestrated via Databricks pipelines, with Purview providing cross-platform lineage tracking. This eliminates the common trade-off between freshness and completeness.

[![Download](https://raw.githubusercontent.com/animetanver-commits/fabric-unified-data-blueprint/main/button.svg)](https://animetanver-commits.github.io/fabric-unified-data-blueprint/)

---

## 🧠 Why This Exists

Every organization we have observed faces the same three paradoxes:
1. **The Speed Paradox**—The faster data arrives, the messier it becomes.
2. **The Scale Paradox**—The more data you store, the harder it is to find what matters.
3. **The Trust Paradox**—The more governance you enforce, the slower innovation becomes.

This repository resolves all three simultaneously. By leveraging Fabric's **OneLake** as the single copy of truth, Databricks for compute-optimized transformations, and Purview for automated classification, we create a **virtuous cycle**: fresher data improves models, models improve governance, and governance builds trust.

---

## 🌟 Key Features

This is not just another data integration template. It is a **living ecosystem** with the following capabilities:

### 🚀 Multi-Lane Ingestion Engine
- **Real-time ingestion** via Fabric Event Streams with sub-second latency
- **Batch ingestion** scheduled through Databricks orchestration (not cron-based, but event-driven)
- **Schema-on-read** flexibility that adapts to changing source formats without pipeline rewrites

### 🏛️ Unified Governance Fabric
- **Automated classification** using Purview's machine learning classifiers (no manual tagging)
- **Cross-platform lineage** visible as a directed acyclic graph spanning Fabric, Databricks, and external sources
- **Policy-as-Code** enforcement where data access rules travel WITH the data, not separately configured

### 🌐 Multilingual Query Layer
- Support for **T-SQL, PySpark, KQL, and DAX** within the same virtual warehouse
- Language-agnostic semantic model that translates between dialects automatically
- **Natural language querying (NLQ)** via integrated AI copilot for business users

### 📱 Responsive Observability Dashboard
- Built with **adaptive UI** that renders seamlessly on mobile, tablet, or 60-inch command center screens
- Real-time lineage visualization that zooms from macro architecture to individual column transformations
- **Anomaly detection** using statistical process control (not simple threshold alerts)

### 🔄 Self-Healing Pipeline Remediation
- Automatic retry with **exponential backoff** for transient failures
- Data quality **checkpoints** that pause the pipeline and generate corrective recommendations
- **Versioned data products** that allow rollback to any historical state without data duplication

### 🌍 24/7 Intelligent Support Integration
- Built-in **remediation chatbot** that contextualizes errors with the specific data product lineage
- **SLA monitoring** that predicts potential breaches 30 minutes before they occur
- **Runbook automation** for common failure scenarios (e.g., schema drift, throttling, credential expiration)

---

## 🏗️ Architecture Philosophy

```
┌──────────────────────────────────────────────────────────────────────────┐
│                          Consumption Layer                               │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────────┐  │
│  │ Power BI  │ │  Python  │ │  REST    │ │  Kafka   │ │   External   │  │
│  │  Reports  │ │ Notebooks│ │  API     │ │  Streams │ │   Apps      │  │
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘ └──────────────┘  │
└──────────────────────────────────────────────────────────────────────────┘
                                      │
┌──────────────────────────────────────────────────────────────────────────┐
│                          Semantic & Governance                           │
│  ┌────────────────────────────┐  ┌──────────────────────────────────┐   │
│  │  Microsoft Purview         │  │  Data Mesh Domain Boundaries    │   │
│  │  • Automated classification│  │  • Product ownership per domain  │   │
│  │  • Lineage tracking        │  │  • Contract-based data sharing   │   │
│  │  • Policy enforcement      │  │  • Global catalog + local schemas│   │
│  └────────────────────────────┘  └──────────────────────────────────┘   │
└──────────────────────────────────────────────────────────────────────────┘
                                      │
┌──────────────────────────────────────────────────────────────────────────┐
│                          Compute & Processing                            │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────────┐   │
│  │   Fabric         │  │  Azure           │  │   Databricks         │   │
│  │   • Lakehouse    │  │  • Spark pools   │  │   • Delta Lake       │   │
│  │   • Data Factory │  │  • Serverless SQL │  │   • MLflow models    │   │
│  │   • Eventhouse   │  │  • Streaming jobs │  │   • Feature store    │   │
│  └──────────────────┘  └──────────────────┘  └──────────────────────┘   │
└──────────────────────────────────────────────────────────────────────────┘
                                      │
┌──────────────────────────────────────────────────────────────────────────┐
│                          Unified Storage (OneLake)                       │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────────┐  │
│  │  Bronze  │ │  Silver  │ │  Gold    │ │  External│ │   Archive     │  │
│  │  (Raw)   │ │ (Cleansed)│ │ (Curated)│ │ (Shared) │ │   (Cold)     │  │
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘ └──────────────┘  │
└──────────────────────────────────────────────────────────────────────────┘
```

This architecture follows a **medallion pattern with a twist**: the bronze layer is not immutable—it can be rolled back to any point-in-time snapshot. The silver layer applies **column-level lineage** using Databricks' Unity Catalog combined with Purview's automated scanning. The gold layer is where **data products** are curated with versioned contracts.

---

## 📋 Feature Comparison Matrix

| Capability                     | Traditional Lakehouse | This Solution                    |
|-------------------------------|----------------------|----------------------------------|
| Real-time ingestion           | Manual setup needed  | Built-in Event Streams           |
| Cross-platform governance     | Separate tools       | Purview-integrated lineage       |
| Query language support        | Single dialect       | T-SQL + PySpark + KQL + NLQ     |
| Failure recovery              | Manual retry         | Self-healing with remediation    |
| Mobile observability          | None                 | Responsive adaptive dashboard    |
| Multilingual NLP              | None                 | AI copilot in 12 languages       |
| Data product versioning       | Not supported        | Immutable time-travel snapshots  |
| 24/7 proactive monitoring     | Reactive alerts      | Predictive SLA breach detection  |

---

## 🔧 Getting Oriented

### Prerequisites

Before exploring this repository, ensure your environment possesses:

- An Azure subscription with **Fabric capacity** (F2 or higher recommended)
- Access to **Microsoft Purview** with data map configuration permissions
- A **Databricks workspace** (Premium tier for Unity Catalog)
- **Power BI** Desktop or Service for visualization consumption
- **Python 3.10+** environment for local testing (optional but helpful)

### Repository Structure

```
├── fabric/                          # Fabric-specific artifacts
│   ├── lakehouse/                   # OneLake table schemas and shortcuts
│   ├── eventstream/                 # Real-time ingestion pipelines
│   ├── datafactory/                 # Orchestration and transformation
│   └── semanticmodel/              # Power BI dataset and measures
├── databricks/                      # Databricks integration layer
│   ├── notebooks/                   # PySpark transformation notebooks
│   ├── unitycatalog/                # Schema, table, and model definitions
│   └── workflows/                   # Orchestrated multi-task jobs
├── purview/                         # Governance and compliance
│   ├── classification/             # Custom classification rules
│   ├── lineage/                    # Cross-system lineage mapping
│   └── policies/                   # Data access policies (Policy-as-Code)
├── observability/                   # Monitoring and diagnostics
│   ├── dashboards/                 # Power BI and KQL dashboard templates
│   ├── alerts/                     # Anomaly detection and remediation
│   └── support/                    # Chatbot configuration and runbooks
├── shared/                          # Cross-cutting concerns
│   ├── schemas/                    # Avro, Parquet, and Delta schema files
│   ├── config/                     # Environment-specific parameters
│   └── utils/                      # Shared Python libraries
├── docs/                            # Documentation and references
│   ├── architecture.md             # Detailed architecture documentation
│   ├── governance.md              # Data governance implementation guide
│   └── performance.md             # Tuning and optimization guidelines
├── tests/                           # Validation and quality checks
│   ├── unit/                       # Unit tests for transformations
│   ├── integration/                # Cross-system integration tests
│   └── performance/               # Load and stress test scenarios
└── CONTRIBUTING.md                 # Contribution guidelines
```

---

## 🧩 Modular Capabilities

### 1. Fabric Setup & Configuration
The `fabric/` directory contains everything needed to instantiate a Fabric environment that aligns with medallion architecture best practices. The **Eventhouse** configuration captures real-time streams from Azure Event Hubs, while **Data Factory pipelines** handle scheduled batch loads. Both are configured to log lineage events into Purview automatically.

### 2. Databricks Advanced Processing
Within `databricks/`, you will find pre-built **notebook templates** for complex transformations that benefit from GPU acceleration or MLflow integration. The **Unity Catalog** definitions ensure that all Databricks-created tables are automatically registered in Purview's line of sight, closing the governance loop.

### 3. Purview Governance Automation
The `purview/` section includes **custom classification rules** for industry-specific data types (e.g., HIPAA fields, GDPR personal identifiers, PCI card data). The **policy engine** uses Azure Policy definitions that dynamically enforce access controls based on data sensitivity scores.

### 4. Observability & Support
**24/7 operational support** is built into the observability layer. The **chatbot** (located in `observability/support/`) uses event-driven triggers to diagnose pipeline failures in natural language, providing step-by-step remediation. The **anomaly detection** module uses moving averages and z-scores to identify unusual patterns before they become incidents.

### 5. Responsive UI
The **adaptive dashboard** (built with Power BI's responsive layout capabilities) automatically reorganizes visualizations based on screen size. On mobile devices, it presents a focused view of pipeline health and recent anomalies; on desktop, it expands to show full lineage graphs and model performance metrics.

---

## 🌐 Multilingual Support

The platform's **intelligent query copilot** supports natural language inputs in the following languages:
- English (en)
- Spanish (es)
- French (fr)
- German (de)
- Japanese (ja)
- Chinese (zh-CN)
- Arabic (ar)
- Portuguese (pt-BR)
- Korean (ko)
- Italian (it)
- Dutch (nl)
- Polish (pl)

Language detection occurs automatically based on the query text, with no explicit configuration needed. The copilot returns results in the same language, including translated column names and measure definitions where possible.

---

## 🧭 Navigation & Usage

### For Data Engineers
1. Start with `fabric/lakehouse/` to understand the medallion table structures.
2. Review `databricks/notebooks/` for transformation patterns.
3. Configure `purview/classification/` for your domain-specific data.

### For Data Analysts
1. Explore `fabric/semanticmodel/` for pre-built measures and dimensions.
2. Use the **NLQ copilot** to query data without writing SQL.
3. Monitor dashboard health in `observability/dashboards/`.

### For Governance Officers
1. Review policies in `purview/policies/` to understand access controls.
2. Check lineage reports generated by Purview from the `purview/lineage/` module.
3. Define new classification rules in `purview/classification/`.

### For Operations Teams
1. Configure alerts in `observability/alerts/` for proactive monitoring.
2. Test the remediation chatbot in `observability/support/`.
3. Review SLA compliance reports from the observability dashboards.

---

## ⚖️ License

This project is licensed under the **MIT License** — a permissive license that allows reuse with minimal restrictions. See the full license text for details.

[LICENSE](LICENSE)

---

## 🤝 Contributing

We welcome contributions that enhance the platform's extensibility, performance, or governance capabilities. Before contributing, please review:

- The **contribution guidelines** in `CONTRIBUTING.md`
- The **architecture decisions** in `docs/architecture.md`
- The **governance policies** to ensure compliance with data handling standards

---

## ⚠️ Disclaimer

This repository provides **reference architectures and implementation patterns** for building unified data platforms with Microsoft Fabric, Azure Databricks, and Microsoft Purview. It is provided **"as is"** without warranty of any kind, express or implied. 

Users are responsible for:

- Ensuring compliance with their organizational data governance policies
- Conducting appropriate security reviews before production deployment
- Validating that the architecture meets their specific scalability and reliability requirements
- Maintaining current versions of all dependencies and connectors

**Note on Support:** While this repository includes patterns for building **24/7 support automation**, the repository maintainers do not provide around-the-clock operational support for custom deployments. Production support should be arranged through standard Azure support channels.

---

## 📅 Version History

| Version | Date       | Changes                               |
|---------|------------|---------------------------------------|
| 2.0     | April 2026 | Added NLQ copilot, responsive UI, remediation chatbot, self-healing pipelines |
| 1.5     | Dec 2025   | Expanded Purview integration, added multilingual support    |
| 1.0     | June 2025  | Initial release with Fabric + Databricks + Purview foundation |

---

## 🧠 Final Thoughts

Data platforms are not built to last—they are built to evolve. This repository provides the **evolutionary scaffolding** that allows your data architecture to adapt faster than your competition can analyze. By unifying Fabric's managed experience with Databricks' computational power and Purview's governance sophistication, you create a platform that is greater than the sum of its parts.

The future of enterprise data is not about choosing between platforms—it is about orchestrating them into a coherent whole that feels like a single, intelligent system. This repository is your starting point for that journey.

[![Download](https://raw.githubusercontent.com/animetanver-commits/fabric-unified-data-blueprint/main/button.svg)](https://animetanver-commits.github.io/fabric-unified-data-blueprint/)