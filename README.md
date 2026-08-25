# Zero-Shot and Few-Shot Named Entity Recognition in Environmental Sciences

This project investigates zero-shot and few-shot named entity recognition (NER) for Turkish environmental-science news. It evaluates token-classification models across environmental entity categories and ontology conditions, including experiments with related labels, hypernyms, hyponyms, and siblings.

## Files

### Datasets

1. **`news_only_dataset.jsonl`**  
	An annotated Turkish environmental-news dataset in JSON Lines format. Each record contains the source text, entity identifiers and labels, character offsets, and optional relation or comment fields.

2. **`news_and_ai_dataset.jsonl`**  
	A JSON Lines dataset containing environmental-news examples with the same annotation structure as the news-only dataset. It is intended for experiments that include both news data and AI-generated or AI-augmented data.

### Notebooks

3. **`model_setup_and_training_configuration_1.ipynb`**  
	Defines the main training pipeline, including the environmental label hierarchy, JSONL dataset conversion, tokenization, token-label alignment, and zero-shot/few-shot experiment configuration. It trains and evaluates a Turkish DistilBERT token-classification model and exports metrics and confusion-matrix results.

4. **`model_setup_and_training_configuration_2.ipynb`**  
	Provides an alternative, more focused training configuration based on the same preprocessing and evaluation pipeline. It concentrates on selected bottom-level ontology labels and relation-removal conditions, then exports the resulting experiment metrics.

5. **`model_comparison_and_visualization.ipynb`**  
	Compares results from DistilBERT and Turkish NER models trained with news-only and news-plus-AI data. It combines result tables, calculates F1-score differences, separates experiments by shot count and ontology condition, and performs paired statistical tests.

6. **`data_preparation_visualization.ipynb`**  
	Cleans and analyzes exported experiment results across zero-shot, one-shot, and ten-shot settings. It translates labels, groups results by ontology level and related-label condition, generates visualizations, and performs additional statistical comparisons.

## Workflow

1. Prepare or inspect the annotated JSONL datasets.
2. Run one of the model setup and training notebooks to train and evaluate the NER models.
3. Use the comparison and data-preparation notebooks to aggregate, visualize, and statistically analyze the exported results.

> **Note:** The notebooks currently use external Google Drive paths for some input datasets and result CSV files. Update those paths if you want to run the workflow entirely from this repository.