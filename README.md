# Comparative Emotion Classification in Short User-Generated Text

CM3060 Natural Language Processing mid-term coursework project.

## Project

This project compares traditional statistical text classification with an embedding-based neural model for emotion classification in short user-generated text.

Dataset: Google Research GoEmotions.

Simplified target classes:

- joy
- anger
- fear
- sadness
- surprise
- neutral

The original GoEmotions labels are already annotated. The project filters to comments with exactly one of the six selected labels and does not manually relabel comments.

## Files

- `emotion_classification_goemotions.ipynb`: main Jupyter notebook.
- `requirements.txt`: Python packages used by the notebook.
- `report_outline.md`: concise report-writing scaffold.
- `AGENTS.md`: project notes and agreed direction.

## Suggested Run Order

1. Open `emotion_classification_goemotions.ipynb`.
2. Run the optional install cell if required.
3. Run all cells from top to bottom.
4. Use the metrics, plots, confusion matrices, and error examples in the written report.
