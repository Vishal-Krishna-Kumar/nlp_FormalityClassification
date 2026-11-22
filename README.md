# Formality classification on GYAFC

Course team project (NLP): classify English sentences as **formal** or **informal** and compare four model
families on the [GYAFC corpus](https://github.com/raosudha89/GYAFC-corpus) (Entertainment & Music domain).

Everything is in one notebook: `GYAFC_Corpus_Fomality_Classification.ipynb` (run on Google Colab with a GPU).

## Approach

1. **Data:** GYAFC Entertainment & Music train and test splits (formal and informal sentences, labels 1 and 0).
2. **Preprocessing:** character-level encoding for the BiLSTM and CNN models (lower-casing, character
   tokenization, padding); WordPiece / SentencePiece tokenizers for the transformer models.
3. **Models:**
   - BiLSTM baseline (Keras)
   - 1D CNN over character embeddings (Keras)
   - `bert-base-uncased`, fine-tuned for 3 epochs (Hugging Face `Trainer`)
   - `microsoft/deberta-v3-base`, fine-tuned for 3 epochs (Hugging Face `Trainer`)
4. **Formality score:** the softmax probability of the "formal" class from the fine-tuned BERT model,
   shown for 50 test sentences at the end of the notebook.

## Results on the test set (from the notebook outputs)

| Model | Precision | Recall | F1 |
|---|---|---|---|
| BiLSTM (character-level) | 0.682 | 0.951 | 0.794 |
| 1D CNN (character-level) | 0.713 | 0.962 | 0.819 |

The BERT and DeBERTa models were fine-tuned (final training loss 0.551 and 0.175), but the notebook does not
print their test-set precision, recall or F1, so they are not reported here. Both character-level models
have high recall and lower precision: they label many informal sentences as formal.

## Running it

```bash
git clone https://github.com/Vishal-Krishna-Kumar/nlp_FormalityClassification.git
cd nlp_FormalityClassification
pip install numpy pandas scikit-learn tensorflow torch transformers sentencepiece accelerate
jupyter notebook GYAFC_Corpus_Fomality_Classification.ipynb
```

The notebook reads GYAFC from Google Drive; the corpus is distributed by its authors on request, so point the
loading cell at your own copy.

## Possible next steps

- Report test-set metrics for the fine-tuned BERT and DeBERTa models.
- Tune the classification threshold to balance precision and recall.
- Evaluate on the Family & Relationships domain as well.
