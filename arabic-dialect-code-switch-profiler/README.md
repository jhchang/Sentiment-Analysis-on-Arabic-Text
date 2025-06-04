{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": [],
      "authorship_tag": "ABX9TyNl39zMC8/Pt45wfHd4ugyO",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/gist/jhchang/e3295b23c89e688af2787adef32f3cb1/arabic-dialect-code-switching-detection-with-socio-linguistic-profiling.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "### **Arabic Dialect + Code-Switching Detection with Socio-Linguistic Profiling**\n",
        "\n",
        "**Vision 2030 Alignment**: *Digital Transformation, Cultural Identity, AI in Government & Media*\n",
        "**Project Description**:\n",
        "\n",
        "* **Code-switching detection** (English-Arabic mix common on social media).\n",
        "* Building a **socio-linguistic profiler** to infer speaker’s region, age group, or sentiment.\n",
        "* Fine-tune Arabic BERT/MarBERT models or use Whisper for speech input.\n",
        "\n",
        "**Why It Stands Out**:\n",
        "\n",
        "* Enhances NLP capabilities in a **low-resource language** region.\n",
        "* Useful for **public sentiment monitoring, e-government tools, and media analysis**.\n",
        "* Shows understanding of **cultural nuances**, which non-Arab developers often overlook.\n",
        "* Very few global ML experts specialize in Arabic dialect NLP. Adding code-switching and socio-linguistic profiling (region/age/emotion) is novel.\n",
        "\n",
        "---\n",
        "\n",
        "\n",
        "\n",
        "🔬 Projected Research-Driven Goals\n",
        "\n",
        "Use self-supervised pretraining on dialectal Arabic (e.g., contrastive learning, SimCLR-style), or fine-tune LLMs on Twitter or TikTok comments to detect dialect/emotion/code-switch boundaries."
      ],
      "metadata": {
        "id": "qjmN9Cdu-L_X"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "---\n",
        "\n",
        "## 🔠 1) Arabic Dialect + Code-Switching Profiler\n",
        "\n",
        "### 🎯 Objective:\n",
        "\n",
        "Build a model that:\n",
        "\n",
        "* Detects Arabic dialects (Gulf, Egyptian, Levantine, etc.)\n",
        "* Detects **code-switching** between English and Arabic\n",
        "* Optionally infers speaker metadata (e.g., region, gender, sentiment)\n",
        "\n",
        "---\n",
        "\n",
        "### 📚 Research Papers\n",
        "\n",
        "Will start with these for grounding and architecture inspiration:\n",
        "\n",
        "1. **[MARBERT: Pretraining BERT on Arabic Tweets](https://arxiv.org/abs/2101.03514)**\n",
        "\n",
        "   * Focused on dialectal Arabic.\n",
        "2. **[CAMeL Tools](https://camel-tools.readthedocs.io/en/latest/)**\n",
        "\n",
        "   * Toolkit for Arabic NLP, including dialect identification.\n",
        "3. **[AraBERTv2: Arabic BERT](https://arxiv.org/abs/2009.03588)**\n",
        "\n",
        "   * Standard Arabic and dialect support.\n",
        "4. **[Fine-grained Arabic Dialect Identification](https://aclanthology.org/2021.wanlp-1.24/)**\n",
        "\n",
        "   * Dataset and task focused on multi-dialect detection.\n",
        "\n",
        "---\n",
        "\n",
        "### 📊 Datasets\n",
        "\n",
        "These are freely available and used in prior research:\n",
        "\n",
        "| Dataset                                          | Description                                                 | Link                                                                     |\n",
        "| ------------------------------------------------ | ----------------------------------------------------------- | ------------------------------------------------------------------------ |\n",
        "| **ADI / MADAR**                                  | Multilingual Arabic Dialect Identification across 25 cities | [MADAR](https://github.com/CAMeL-Lab/madar)                              |\n",
        "| **ArSarcasm / Arap-Tweet**                       | Dialectal Arabic tweets with labels                         | [ArSarcasm](https://github.com/UBC-NLP/ArSarcasm)                        |\n",
        "| **QADI Dataset**                                 | Fine-grained dialect identification                         | [QADI on GitHub](https://github.com/qcri/QADI)                           |\n",
        "| **CALOYP**                                       | Youth-oriented social media corpus; includes code-switching | [CALOYP Paper](https://aclanthology.org/L18-1554.pdf) (Email to request) |\n",
        "| **Twitter Dialect Corpus (with code-switching)** | Shared tasks with dialect+code-switch labels                | See [VarDial Workshop](https://vardial.org/2021/)                        |\n",
        "\n",
        "> 💡 If none have code-switching annotations: build my own from Twitter using regex + langdetect (Arabic vs English tokens) for weak supervision.\n",
        "\n",
        "---\n",
        "\n",
        "### 🧠 Baseline Models\n",
        "\n",
        "* `MARBERT`, `AraBERT`, or `ARBERT` (via Hugging Face)\n",
        "* `langdetect` or `fastText` for basic code-switch detection\n",
        "* Token-level classification via BiLSTM or Transformer models\n",
        "\n",
        "---\n",
        "\n",
        "### 🛠 Tools\n",
        "\n",
        "* Hugging Face Transformers (`AutoModelForSequenceClassification`)\n",
        "* CAMeL Tools for morphological features\n",
        "* `seqeval` for token classification evaluation\n",
        "* `pyarabic`, `farasa`, or `stanza` for preprocessing"
      ],
      "metadata": {
        "id": "DPszRIAu-Ywa"
      }
    }
  ]
}
