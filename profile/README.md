<h1 align="center">MoleCare</h1>

<p align="center">
  <strong>Skin health self-management — monitor moles and skin lesions over time.</strong>
</p>

<p align="center">
  <a href="https://www.molecare.co.uk">molecare.co.uk</a> ·
  <a href="https://www.youtube.com/@molecare">MoleCare youtube channel</a> ·
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
| [**molecare-desktop**](https://github.com/MoleCare/molecare-desktop) | The Electron desktop app for macOS, Windows and Linux — Apache-2.0 |
| [**molecare-skin-llm**](https://github.com/MoleCare/molecare-skin-llm) | A small LoRA model for educational skin-health Q&A, behind a harness that decides whether a draft answer ships — Apache-2.0 |
| [**privacy-gate-llm**](https://github.com/MoleCare/privacy-gate-llm) | Keeps sensitive prompts local: a tiny classifier on top of bge-m3 that catches health data, credentials and personal details written as plain English, for LLM routers and guardrails. [Try the demo](https://huggingface.co/spaces/YauhenBichel/privacy-gate-llm-demo) — Apache-2.0 |

### Packages for app developers

Small, dependency-light libraries taken out of the MoleCare apps, useful in any app. Each is
stateless, has no MoleCare-specific settings, and keeps the same rule as the product: it shows
or measures photos and data, and never judges what is in them.

| Package | What it is |
|---|---|
| [**react-photo-compare**](https://github.com/MoleCare/react-photo-compare) | Two photos side by side with one shared zoom and pan, for React. Mouse, touch, pen and keyboard; no dependencies. [Live demo](https://molecare.github.io/react-photo-compare/) — Apache-2.0 |
| [**rn-photo-quality**](https://github.com/MoleCare/rn-photo-quality) | On-device photo quality checks for React Native and Expo: exposure, uneven lighting, sharpness, capture details and whether two photos are comparable — Apache-2.0 |
| [**rn-scale-reference**](https://github.com/MoleCare/rn-scale-reference) | Turns pixels into millimetres using a coin or sticker of known size in the same photo, for React Native and Expo. Always an estimate, with the reason when a photo can't be measured — Apache-2.0 |
| [**rn-health-data**](https://github.com/MoleCare/rn-health-data) | Reads steps, sleep, workouts, active energy and water from Apple Health and Health Connect with one API. Read-only; stores and sends nothing — Apache-2.0 |

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

## Contributors

Thank you to everyone who has helped.

<!-- readme: contributors,bots/- -start -->
<p align="center">
  <a href="https://github.com/YauhenBichel" title="Yauhen Bichel" aria-label="Yauhen Bichel"><img src="../.github/faces/YauhenBichel.svg" width="87" height="99" alt="Yauhen Bichel" /></a>
</p>
<!-- readme: contributors,bots/- -end -->

Filled from GitHub commits (bots omitted). [Action](https://github.com/YauhenBichel/readme-contributors)
