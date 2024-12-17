# Bi-LSTM CRF for Named Entity Recognition (NER)

## Project Overview
This repository implements **Named Entity Recognition (NER)** using **BiLSTM** and **BiLSTM-CRF** models.  
NER involves identifying and classifying entities in text, such as **Person**, **Location**, **Organization**, and **Miscellaneous** entities.

The project is inspired by [Huang et al.'s paper](https://paperswithcode.com/paper/bidirectional-lstm-crf-models-for-sequence) and achieves competitive F1 scores on the **CoNLL-2003 dataset**.

---

## Architecture
### Bi-LSTM Model
The BiLSTM model processes input sequences bidirectionally:
1. **Embedding Layer**: Converts tokens to dense vector representations.
2. **Forward and Backward LSTM**: Captures context from both directions.
3. **Fully Connected Layer**: Outputs token-level predictions.

### Bi-LSTM-CRF Model
The CRF layer improves the BiLSTM model by considering **dependencies between output labels**, ensuring coherent predictions.

---

## Experimental Results
### Key Metrics
| Model          | F1 Score  |
|----------------|-----------|
| Bi-LSTM        | 82%       |
| Bi-LSTM-CRF    | 83.8%     |

### Observations:
- The **CRF layer** improves recall and F1 scores by addressing misclassification issues.
- Misclassification between **entities** and the 'O' class (non-entities) is reduced with the BiLSTM-CRF model.

---

## Dataset
- **CoNLL-2003 Dataset**: Available [here](https://huggingface.co/datasets/conll2003).
- Classes: **PER** (Person), **LOC** (Location), **ORG** (Organization), **MISC** (Miscellaneous).

---

## Dependencies
Run the following to install required libraries:
```bash
pip install -r requirements.txt
