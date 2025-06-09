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

1. **[MARBERT: Pretraining BERT on Arabic Tweets](https://aclanthology.org/2021.acl-long.551.pdf)**

   * Focused on dialectal Arabic.
2. **[CAMeL Tools](https://aclanthology.org/2020.lrec-1.868v2.pdf)**

   * Toolkit for Arabic NLP, including dialect identification.
3. **[AraBERTv2: Arabic BERT](https://arxiv.org/abs/2003.00104v2)**

   * Standard Arabic and dialect support.
4. **[Fine-grained Arabic Dialect Identification](https://aclanthology.org/W19-4622.pdf)**

   * Dataset and task focused on multi-dialect detection.

---

### 📊 Datasets

These are freely available and used in prior research:

| Dataset                                          | Description                                                 | Link                                                                     |
| ------------------------------------------------ | ----------------------------------------------------------- | ------------------------------------------------------------------------ |
| **ADI / MADAR**                                  | Multilingual Arabic Dialect Identification across 25 cities | [MADAR](https://sites.google.com/nyu.edu/madar/)                              |


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
