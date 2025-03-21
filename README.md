# 🚨 Twitter Disaster Classification

This project focuses on classifying whether a tweet is about a **disaster** or **not** using Natural Language Processing (NLP) techniques. The workflow involves **data exploration, feature extraction, text cleaning, and various machine learning & deep learning models**, including **pretrained embeddings (GloVe), Universal Auto Encoder, and BERT**.

---

## 📌 Problem Statement
Given a dataset of tweets, the goal is to **predict whether a tweet describes a real disaster or not**. This classification helps in filtering relevant information during crisis situations.

---

## 🔍 1️⃣ Data Understanding
The dataset contains tweets labeled as:
- **Disaster (1)**: Tweets reporting real-world disasters.
- **Non-Disaster (0)**: Tweets unrelated to actual disasters.

Each tweet may include **mentions (@), hashtags (#), URLs, typos, slang, abbreviations, and special characters**, which influence classification accuracy.

---

## 📊 2️⃣ Exploratory Data Analysis (EDA)
- **Most frequent words in disaster vs. non-disaster tweets** were visualized.
- Disaster tweets are generally more **formal** and contain **longer words**, as they often originate from news sources.
- Non-disaster tweets are more **informal** with higher occurrences of **slang, typos, and abbreviations**.

---

## 📌 3️⃣ Feature Extraction
Meta-features were extracted to improve model performance:

| Feature | Description |
|---------|-------------|
| **word_count** | Number of words in a tweet |
| **unique_word_count** | Number of unique words in a tweet |
| **stop_word_count** | Number of stop words |
| **punctuation_count** | Number of punctuations |
| **char_count** | Number of characters in text |
| **mean_word_length** | Average word length |
| **url_count** | Number of URLs |
| **mention_count** | Number of mentions (@) |
| **hashtag_count** | Number of hashtags (#) |

---

## 🛠 4️⃣ Preprocessing (Text Cleaning)
Text cleaning was performed to improve **embedding coverage** and model performance.

**📉 Before Cleaning:**
- **GloVe Embeddings Coverage:**
  - **Training Set:** 52.06% vocabulary, 82.68% text
  - **Test Set:** 57.21% vocabulary, 81.85% text

**⚡ Cleaning Steps:**
- Removed **punctuations**, special characters, and symbols.
- Expanded **contractions** (e.g., *can't → cannot*).
- Removed **URLs, mentions, hashtags** (or expanded them when informative).
- Corrected **typos, slang, and informal abbreviations**.

**📈 After Cleaning:**
- **GloVe Embeddings Coverage:**
  - **Training Set:** 82.89% vocabulary, 97.14% text
  - **Test Set:** 88.09% vocabulary, 97.32% text

---

## 🏗 5️⃣ Modeling
A range of models were implemented to classify tweets:

| Model | Validation Accuracy (Before Fine-Tuning) | Validation Accuracy (After Fine-Tuning) |
|--------|----------------------------|----------------------------|
| **My Embedding** | 77.03% (Overfitting) | - |
| **Pretrained GloVe** | 80.31% | 79.27% |
| **Universal Auto Encoder** | 82.15% | 84.38% |
| **BERT** | 79.00% | 81.10% |

**🏆 Best Model:** Universal Auto Encoder (**84.38% validation accuracy**) after fine-tuning.

---

## 📊 6️⃣ Model Comparison
The results indicate that **fine-tuned models outperform their raw versions**, with **Universal Auto Encoder achieving the highest accuracy**.

- **GloVe performed well but required significant cleaning**.
- **BERT improved after fine-tuning** but was computationally expensive.
- **Universal Auto Encoder achieved the best balance between accuracy and efficiency**.

**Final Ranking:** **186th out of 804** on Kaggle! 🚀🎯

---
