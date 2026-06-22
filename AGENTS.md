# Project Notes for Agents

## Coursework Brief
- Module: CM3060 Natural Language Processing.
- Task: build a text classifier for a domain-specific problem and compare a traditional statistical model with an embedding-based/deep learning model.
- Required work: dataset description, preprocessing, baseline, comparative modelling, evaluation, discussion, and reflection.
- Expected tools: Python and Jupyter Notebook.
- Evaluation should include metrics such as accuracy, precision, recall, F1-score, and confusion matrix.

## Course Topics Covered Before Midterm
- NLP introduction, applications, Python/Jupyter, and evaluation metrics.
- Text preprocessing: sentence segmentation, tokenization, normalization, regex, stop words, and corpora.
- Language modelling: frequency distributions, statistical language models, topic modelling.
- Lexical semantics: WordNet, semantic similarity, vector semantics, word embeddings, Word2Vec.
- Text categorisation and sentiment analysis: Bayes' theorem, Multinomial Naive Bayes, supervised learning, lexicon methods.
- Syntax and parsing appears later but is not central to the chosen project.

## Chosen Project Direction
- Topic: comparative emotion classification in short user-generated text.
- Proposed title: Comparative Emotion Classification in Short User-Generated Text Using Statistical and Embedding-Based Models.
- Dataset: Google Research GoEmotions dataset, using Reddit comments with existing human emotion labels.
- Simplification: filter the original 27 emotion categories plus neutral to six target classes only: joy, anger, fear, sadness, surprise, and neutral.
- Filtering means selecting rows that already have one of the target labels; do not manually relabel comments.

## Planned Modelling Approach
- Baseline: majority-class classifier.
- Statistical model: TF-IDF or bag-of-words with Multinomial Naive Bayes or Logistic Regression.
- Embedding model: Keras/TensorFlow Embedding layer with a simple neural network.
- Analysis: compare models using overall metrics, per-class F1-scores, confusion matrices, and examples of misclassified comments.

## GitHub / Multi-Device Workflow
- Keep the project in a GitHub repository so work can move between laptop and PC.
- On any machine: clone the repo, open the notebook, run `pip install -r requirements.txt`, then work in Jupyter.
- Commit and push notebook/report changes from whichever machine was used; pull before starting work on the other machine.
- Avoid committing downloaded datasets, virtual environments, notebook checkpoints, or generated cache folders.

## Rationale
- Emotion classification is richer than simple positive/negative sentiment but still aligns with course topics.
- GoEmotions has clearer provenance than the DAIR.AI-hosted six-emotion dataset.
- Filtering to six classes keeps the coursework manageable while preserving a meaningful multi-class classification problem.
