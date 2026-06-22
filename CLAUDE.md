# Claude Code Project Guide

## Project Summary

This is a CM3060 Natural Language Processing mid-term coursework project.

The project compares traditional statistical text classification with an embedding-based neural model for emotion classification in short user-generated text.

Working title: **Comparative Emotion Classification in Short User-Generated Text Using Statistical and Embedding-Based Models**

## Coursework Requirements

- Build a text classifier for a domain-specific problem.
- Use Python and Jupyter Notebook.
- Compare a traditional statistical model with an embedding-based or deep learning model.
- Include dataset description, preprocessing, baseline, comparative modelling, evaluation, discussion, and reflection.
- Evaluate with accuracy, precision, recall, F1-score, and confusion matrices.

## Course Alignment

The project should stay visibly connected to topics covered before the midterm:

- Python and Jupyter workflow.
- NLP evaluation metrics: precision, recall, F1-score.
- Text preprocessing: tokenization, normalization, regex, stop words, corpora.
- Frequency-based text representations.
- Vector semantics and word embeddings.
- Text categorisation, Naive Bayes, supervised learning, and sentiment analysis.

Do not introduce advanced concepts unless they are clearly explained as optional future work.

## Dataset Plan

Use Google Research's **GoEmotions** dataset.

The original dataset contains 27 emotion categories plus neutral. For this coursework, filter it to six target classes:

- joy
- anger
- fear
- sadness
- surprise
- neutral

Important: the comments are already labelled. Filtering means selecting rows that already have exactly one of the six target labels. Do not manually relabel comments.

## Existing Files

- `emotion_classification_goemotions.ipynb`: main coursework notebook.
- `README.md`: project overview and run instructions.
- `requirements.txt`: Python dependencies.
- `report_outline.md`: scaffold for the written report.
- `AGENTS.md`: previous agent-facing project notes.
- `CM2060-NLP-Coursework.md`: original coursework brief.

## Modelling Approach

Use this model structure unless there is a strong reason to change it:

- Baseline: majority-class classifier.
- Statistical models: bag-of-words with Multinomial Naive Bayes, and TF-IDF with Logistic Regression (both implemented for comparison).
- Embedding model: Keras/TensorFlow Embedding layer with a simple neural network.
- Analysis: classification report, macro F1, weighted F1, confusion matrices, class distribution chart, and misclassified examples.

## Working Rules

- Keep the project student-level and explainable.
- Prefer clear notebook cells over complex abstractions.
- Do not commit downloaded datasets, cache folders, virtual environments, model binaries, or notebook checkpoints.
- Preserve the coursework framing and the six-class GoEmotions simplification.
- If adding improvements, prioritise report clarity, reproducibility, and evaluation quality.

## Git Workflow

This repository is intended for work across laptop and PC.

- Pull before starting work on a different machine.
- Commit meaningful notebook/report changes.
- Push after each useful work session.
- Keep generated data and local environments out of Git.
