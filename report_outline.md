# Report Outline

## 1. Domain-Specific Area

Emotion classification identifies the emotion expressed in short user-generated text. This is useful for social media analysis, user feedback monitoring, wellbeing tools, and emotionally aware conversational systems.

## 2. Objectives

Compare a traditional statistical classifier with an embedding-based neural model for six-class emotion classification. The comparison focuses on performance, class-level behaviour, and practical suitability for short online comments.

## 3. Dataset Description

Use Google Research's GoEmotions dataset, a manually annotated collection of Reddit comments with fine-grained emotion labels. For this project, filter the original labels to six target classes: joy, anger, fear, sadness, surprise, and neutral.

## 4. Evaluation Methodology

Use accuracy, precision, recall, F1-score, macro F1, weighted F1, and confusion matrices. Macro F1 is important because class imbalance can hide poor performance on minority emotions.

## 5. Implementation

Preprocess by filtering labels, checking class distribution, and preparing text representations. Use bag-of-words or TF-IDF for statistical models and tokenized padded sequences for the embedding model.

## 6. Models

Baseline: majority-class classifier.

Statistical models: Multinomial Naive Bayes and TF-IDF Logistic Regression.

Embedding model: Keras Embedding layer with GlobalAveragePooling1D and dense layers.

## 7. Discussion

Compare results across models and emotions. Discuss likely confusions such as sadness/fear, joy/surprise, or neutral/emotional classes. Use misclassified examples to support the analysis.

## 8. Reflection

Discuss strengths and limitations of each model type, reproducibility, transferability to other user-generated text domains, and possible improvements such as pretrained embeddings or transformer models.
