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

- `emotion_classification_goemotions.ipynb`: the single submission document. It now contains the full written report interleaved with the code, structured to the marking rubric (I. Introduction sections 1-4, II. Implementation sections 5-8, III. Conclusions sections 9-10, then References).
- `README.md`: project overview and run instructions.
- `requirements.txt`: Python dependencies.
- `AGENTS.md`: agent-facing project notes.
- `CM2060-NLP-Coursework.md`: original coursework brief.
- `*.BACKUP.ipynb` / `*.PREEXEC.ipynb`: local safety snapshots of the notebook (not committed).

Note: the standalone `report.md` was removed. Its prose lives inside the notebook now, so edit the notebook markdown cells, not a separate report file.

## Submission Format

- Submit as a **single PDF** that contains both the written sections and the code with outputs.
- Produce it from the notebook, not a separate document. The environment has no LaTeX or pandoc, so the reliable path is: `nbconvert --to html --embed-images`, open the HTML in a browser, then Print to PDF with **Background graphics** enabled (so the confusion-matrix heatmaps and charts keep their fills).
- The notebook must be re-run top to bottom (using the project `.venv` kernel) before exporting so every output is fresh.
- Only the subtitle header block identifies this as coursework: title, then `### CM3060 Natural Language Processing mid-terms`, `Name: Jaslyn Chan Yu Xin`, `Student ID: 240662387`. Keep coursework/course/rubric/submission wording out of the body prose.

## Modelling Approach

Use this model structure unless there is a strong reason to change it:

- Baseline: majority-class classifier.
- Statistical models: bag-of-words with Multinomial Naive Bayes, and TF-IDF with Logistic Regression (both implemented for comparison).
- Embedding model: Keras/TensorFlow Embedding layer with a simple neural network, plus a class-weighted ablation variant (Section 8b) that mirrors the TF-IDF + Logistic Regression model's `class_weight="balanced"` to test whether it closes the macro F1 gap.
- Analysis: classification report, macro F1, weighted F1, confusion matrices, class distribution chart, misclassified examples, and the class-weighting ablation comparison.

## Writing Style and Tone (important)

The user (Jaslyn) has specific, firmly-held writing preferences. Follow them in every markdown cell and any prose written for this project.

- **No em dashes anywhere.** Never use `—`. Rewrite with commas, full stops, or parentheses. (En dashes `–` are fine in number/page ranges only, e.g. `pp. 169–200`.)
- **No semicolons in prose.** Split into two sentences or join with "and". This also applies to citation groups (write "(Pedregosa et al., 2011, and Abadi et al., 2016)", not a semicolon-separated list).
- **No "label: explanation" colon patterns**, and avoid bold mini-header lead-ins on explanatory paragraphs (e.g. do NOT open a note with "**How TF-IDF works.**" or "**Reading this chart.**"). The user actively edits these out. Let explanations flow as plain sentences. Short bold sub-labels are only tolerated in genuinely list-like structured passages (e.g. the dataset-description sub-points), not on ordinary explanatory paragraphs.
- **Balance plain language with academic professionalism.** This is the core preference. Cut bloat: empty qualifiers ("genuinely", "clearly"), self-important framing ("the most instructive result of the project", "surfaced honestly"), nominalisations, and doubled words. Keep precise technical vocabulary (macro F1, class imbalance, generative model, oneDNN), keep citations, keep a formal register. Plain does NOT mean dumbed-down. Calibration example: prefer "The emotion categories come from psychology" over "The set of target categories is itself a modelling choice grounded in psychological theory"; but do NOT go as far as "We just picked the emotions from psychology".
- **Citations: Harvard (Cite Them Right).** In-text uses "and" not "&", and "et al." for three or more authors, in the form `(Author, Year)` or narrative `Author (Year)`. Reference list: `Surname, Initials. (Year) 'Article title in sentence case', *Journal in italics*, Volume(Issue), pp. start–end. Available at: [url](url) (Accessed: D Month YYYY).` Books use `*Title*. Place: Publisher.`
- **Every reference must be cited in-text** (no orphan references) and every reference must be real and verifiable, with a working link (DOI or official page). Verify before adding.
- Keep the coursework framing out of the body (see Submission Format above).

## Working Rules

- Keep the project student-level and explainable.
- Prefer clear notebook cells over complex abstractions.
- Do not commit downloaded datasets, cache folders, virtual environments, model binaries, or notebook checkpoints.
- Preserve the coursework framing and the six-class GoEmotions simplification.
- If adding improvements, prioritise report clarity, reproducibility, and evaluation quality.
- Note: the class-weighted embedding model (Section 8b) is not fully run-to-run deterministic despite fixed seeds (TensorFlow's oneDNN CPU ops reorder floating-point operations between runs). This is documented as an honest limitation in the notebook rather than hidden or "fixed" — don't overwrite that caveat with a single cherry-picked run.

## Git Workflow

This repository is intended for work across laptop and PC.

- Pull before starting work on a different machine.
- Commit meaningful notebook/report changes.
- Push after each useful work session.
- Keep generated data and local environments out of Git.
