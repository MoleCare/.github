<h1 align="center">MoleCare</h1>

<p align="center">
  <strong>Skin health self-management — monitor moles and skin lesions over time.</strong>
</p>

<p align="center">
  <a href="https://www.molecare.co.uk">molecare.co.uk</a> ·
  <a href="https://apps.apple.com/us/app/molecare/id1448635328">App Store</a> ·
  <a href="https://play.google.com/store/apps/details?id=com.mymolecare">Google Play</a>
</p>

---

## What MoleCare does

Changes in a mole are easier to spot when you can compare it against a photo from six months ago
than from memory. MoleCare gives people secure, private storage for photos of skin lesions they
want to keep an eye on, and helps them track how those lesions change over time — so a
conversation with a clinician can start from evidence rather than recollection.

> **MoleCare is not a diagnostic tool and not a medical device.** It supports self-monitoring.
> Anyone concerned about a skin change should see a qualified clinician.

## How it is built

| Layer | Technology |
|---|---|
| **Backend** | Java, Spring Boot, REST API on AWS |
| **Machine learning** | TensorFlow / Keras CNN classifiers, served over Flask |
| **Model training** | Transfer learning on public dermoscopic data — Xception, InceptionV3, DenseNet201, EfficientNet |
| **Data & messaging** | PostgreSQL, Apache Kafka |
| **Mobile** | React Native — iOS and Android |
| **Web** | React |
| **Infrastructure** | AWS, Google Cloud (Vertex AI), Docker, Terraform |

## Open source

We are opening up parts of the platform that are useful on their own.

| Repository | What it is |
|---|---|
| [**molecare-mcp**](https://github.com/MoleCare/molecare-mcp) | MCP server giving Claude and other clients educational dermatology knowledge — lesion terminology, ABCDE criteria, SNOMED CT to ICD-10 mapping. Runs with no credentials. Ships `molecare-ops-mcp` alongside it for infrastructure tooling — Apache-2.0 |
| [**molecare-ml**](https://github.com/MoleCare/molecare-ml) | The TensorFlow melanoma classification service and the training notebooks behind it — Apache-2.0 |
| [**molecare-webapp**](https://github.com/MoleCare/molecare-webapp) | The React web app — where people record and compare their own photographs over time — Apache-2.0 |
| [**molecare-desktop**](https://github.com/MoleCare/molecare-desktop) | The Electron desktop app for macOS, Windows and Linux — Apache-2.0 |
| [**skincare-qa**](https://github.com/MoleCare/skincare-qa) | A small LoRA model for educational skin-health Q&A, behind a harness that decides whether a draft answer ships — Apache-2.0 |

Contributions are welcome. Each repository carries a contributing guide, and anything touching
model behaviour is held to the clinical-safety rules described there.

**New here?** `molecare-mcp` is the easiest place to start — it runs locally with no
credentials, no database, and no AWS account. Issues tagged
[`good first issue`](https://github.com/MoleCare/molecare-mcp/labels/good%20first%20issue)
are scoped so you do not need context on the wider platform.

## Research

The classifiers here are trained on openly licensed dermoscopic imagery from the
[ISIC Archive](https://www.isic-archive.com/). We publish the training notebooks so the
comparisons behind our architecture choices can be inspected and challenged.

The most valuable open problem in this space is **performance across Fitzpatrick skin types** —
dermoscopic datasets are not evenly representative, and models trained on them inherit that. Our
model card says so plainly: that performance is currently **unmeasured**. It is tracked as
[an open issue](https://github.com/MoleCare/molecare-ml/issues/10), and contributions there are
especially welcome — including ones that show the model performing badly.

## Get in touch

**info@molecare.co.uk**
