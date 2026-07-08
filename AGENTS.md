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
- Title (current, shortened): Comparative Emotion Classification in Short Text.
- Dataset: Google Research GoEmotions dataset, using Reddit comments with existing human emotion labels.
- Simplification: filter the original 27 emotion categories plus neutral to six target classes only, namely joy, anger, fear, sadness, surprise, and neutral.
- Filtering means selecting rows that already have one of the target labels. Do not manually relabel comments.

## Writing Style and Tone (important)
The user (Jaslyn) has firm writing preferences. Apply them to every markdown cell and any prose for this project.
- No em dashes anywhere. Use commas, full stops, or parentheses instead. En dashes are allowed only in number and page ranges.
- No semicolons in prose, including in citation groups. Split sentences or use "and".
- No "label: explanation" colons, and no bold mini-header lead-ins on explanatory paragraphs (for example, do not open with "**How TF-IDF works.**"). Let explanations flow as plain sentences. The user edits these out by hand.
- Balance plain language with academic professionalism. Cut bloat and self-important framing, but keep technical terms, citations, and a formal register. Plain is not dumbed-down.
- Harvard (Cite Them Right) citations throughout: in-text "and" not "&", "et al." for three or more authors. Reference list with single-quoted sentence-case article titles, italic journal or book titles, "pp." page ranges, and "Available at: url (Accessed: date)." for online sources.
- Every reference must be cited in-text (no orphans) and must be real and verifiable with a working link.
- Keep coursework, course, rubric, and submission wording out of the body prose. Only the subtitle header (module line, name, student ID) identifies the coursework.

## Deliverable Format
- One notebook, submitted as a single PDF containing both the written sections and the code with outputs.
- The written report is now integrated into the notebook itself, structured to the rubric. The old standalone report.md was removed.
- No LaTeX or pandoc in the environment. Export via nbconvert to HTML with embedded images, then print to PDF from the browser with background graphics on.

## Modelling Approach (as implemented)
- Baseline: majority-class classifier.
- Statistical models: bag-of-words with Multinomial Naive Bayes, and TF-IDF with Logistic Regression (class-weighted).
- Embedding model: Keras Embedding layer with a simple neural network, plus a class-weighted ablation (Section 7.3).
- Robustness: multi-seed stability of macro F1 (Section 7.4) and a learning curve versus training-set size (Section 7.7).
- Analysis: overall metrics, per-class F1, confusion matrices, error examples, and a published-baseline comparison against Demszky et al. (2020).

## Lecturer Feedback (Derrick Peh, 8 July 2026)
- Three "Good" marks on the early sections. Two action points, both on Section 10: "Include any limitations that you might have too" and "What other areas for further study / improvements?".
- Next step: strengthen Section 10 with an explicit limitations list and clearer future-study directions (it has word-count room). Full detail in CLAUDE.md.

## GitHub / Multi-Device Workflow
- Keep the project in a GitHub repository so work can move between laptop and PC.
- On any machine: clone the repo, open the notebook, run `pip install -r requirements.txt`, then work in Jupyter.
- Commit and push notebook/report changes from whichever machine was used; pull before starting work on the other machine.
- Avoid committing downloaded datasets, virtual environments, notebook checkpoints, or generated cache folders.

## Rationale
- Emotion classification is richer than simple positive/negative sentiment but still aligns with course topics.
- GoEmotions has clearer provenance than the DAIR.AI-hosted six-emotion dataset.
- Filtering to six classes keeps the coursework manageable while preserving a meaningful multi-class classification problem.
