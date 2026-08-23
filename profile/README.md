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
| **MoleCare-ML** | The TensorFlow melanoma classification service and the training notebooks behind it — Apache-2.0 |

Contributions are welcome. Each repository carries a contributing guide, and anything touching
model behaviour is held to the clinical-safety rules described there.

## Research

The classifiers here are trained on openly licensed dermoscopic imagery from the
[ISIC Archive](https://www.isic-archive.com/). We publish the training notebooks so the
comparisons behind our architecture choices can be inspected and challenged.

The most valuable open problem in this space is **performance across Fitzpatrick skin types** —
dermoscopic datasets are not evenly representative, and models trained on them inherit that.
Contributions on bias evaluation are especially welcome.

## Get in touch

**info@molecare.co.uk**
