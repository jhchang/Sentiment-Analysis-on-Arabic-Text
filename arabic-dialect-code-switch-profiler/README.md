### **Arabic Dialect + Code-Switching Detection with Socio-Linguistic Profiling**

**Vision 2030 Alignment**: *Digital Transformation, Cultural Identity, AI in Government & Media*
**Project Description**:

* **Code-switching detection** (English-Arabic mix common on social media).
* Building a **socio-linguistic profiler** to infer speaker’s region, age group, or sentiment.
* Fine-tune Arabic BERT/MarBERT models or use Whisper for speech input.

**Why It Stands Out**:

* Enhances NLP capabilities in a **low-resource language** region.
* Useful for **public sentiment monitoring, e-government tools, and media analysis**.
* Shows understanding of **cultural nuances**, which non-Arab developers often overlook.
* Very few global ML experts specialize in Arabic dialect NLP. Adding code-switching and socio-linguistic profiling (region/age/emotion) is novel.

---



🔬 Projected Research-Driven Goals

Use self-supervised pretraining on dialectal Arabic (e.g., contrastive learning, SimCLR-style), or fine-tune LLMs on Twitter or TikTok comments to detect dialect/emotion/code-switch boundaries.

---

## 🔠 1) Arabic Dialect + Code-Switching Profiler

### 🎯 Objective:

Build a model that:

* Detects Arabic dialects (Gulf, Egyptian, Levantine, etc.)
* Detects **code-switching** between English and Arabic
* Optionally infers speaker metadata (e.g., region, gender, sentiment)

---

### 📚 Research Papers

Will start with these for grounding and architecture inspiration:

1. **[MARBERT: Pretraining BERT on Arabic Tweets](https://arxiv.org/abs/2101.03514)**

   * Focused on dialectal Arabic.
2. **[CAMeL Tools](https://camel-tools.readthedocs.io/en/latest/)**

   * Toolkit for Arabic NLP, including dialect identification.
3. **[AraBERTv2: Arabic BERT](https://arxiv.org/abs/2009.03588)**

   * Standard Arabic and dialect support.
4. **[Fine-grained Arabic Dialect Identification](https://aclanthology.org/2021.wanlp-1.24/)**

   * Dataset and task focused on multi-dialect detection.

---

### 📊 Datasets

These are freely available and used in prior research:

| Dataset                                          | Description                                                 | Link                                                                     |
| ------------------------------------------------ | ----------------------------------------------------------- | ------------------------------------------------------------------------ |
| **ADI / MADAR**                                  | Multilingual Arabic Dialect Identification across 25 cities | [MADAR](https://github.com/CAMeL-Lab/madar)                              |
| **ArSarcasm / Arap-Tweet**                       | Dialectal Arabic tweets with labels                         | [ArSarcasm](https://github.com/UBC-NLP/ArSarcasm)                        |
| **QADI Dataset**                                 | Fine-grained dialect identification                         | [QADI on GitHub](https://github.com/qcri/QADI)                           |
| **CALOYP**                                       | Youth-oriented social media corpus; includes code-switching | [CALOYP Paper](https://aclanthology.org/L18-1554.pdf) (Email to request) |
| **Twitter Dialect Corpus (with code-switching)** | Shared tasks with dialect+code-switch labels                | See [VarDial Workshop](https://vardial.org/2021/)                        |

> 💡 If none have code-switching annotations: build my own from Twitter using regex + langdetect (Arabic vs English tokens) for weak supervision.

---

### 🧠 Baseline Models

* `MARBERT`, `AraBERT`, or `ARBERT` (via Hugging Face)
* `langdetect` or `fastText` for basic code-switch detection
* Token-level classification via BiLSTM or Transformer models

---

### 🛠 Tools

* Hugging Face Transformers (`AutoModelForSequenceClassification`)
* CAMeL Tools for morphological features
* `seqeval` for token classification evaluation
* `pyarabic`, `farasa`, or `stanza` for preprocessing
