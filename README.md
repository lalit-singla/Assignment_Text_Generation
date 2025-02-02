# Model Comparison using TOPSIS

## Overview
This project evaluates different text-generation models using various performance metrics and applies **TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution)** to rank them objectively.

## Models Compared
- **FINEgpt2** (`Amitesh007/text_generation-finetuned-gpt2`)
- **NYTK-GPT2** (`NYTK/text-generation-news-gpt2-small-hungarian`)
- **rayhanozzy** (`rayhanozzy/text_generation`)
- **RuGPT3-Small** (`ai-forever/rugpt3small_based_on_gpt2`)
- **GPT2-Large** (`openai-community/gpt2-large`)

## Evaluation Metrics
The models are evaluated based on the following metrics:

| Parameter               | Description |
|-------------------------|-------------|
| **Avg F1-score**        | Measures precision and recall of generated text |
| **Avg ROUGE-1**         | Unigram overlap with reference text |
| **Avg ROUGE-2**         | Bigram overlap with reference text |
| **Avg ROUGE-L**         | Longest common subsequence similarity |
| **Diversity Score**     | Measures diversity in generated text (1 - Jaccard Similarity) |
| **Avg Response Length** | Measures verbosity of the generated response |

## TOPSIS Parameters
| Parameter               | Weight | Impact |
|-------------------------|--------|--------|
| **Avg F1-score**        | 0.25   | **+**  |
| **Avg ROUGE-1**         | 0.20   | **+**  |
| **Avg ROUGE-2**         | 0.15   | **+**  |
| **Avg ROUGE-L**         | 0.15   | **+**  |
| **Diversity Score**     | 0.15   | **+**  |
| **Avg Response Length** | 0.10   | **-**  |

## Installation & Setup
### 1. Install Required Dependencies
```sh
pip install transformers rouge-score numpy scikit-learn pandas topsis-python
pip install topsis-LalitSingla-102383006 
```

### 2. Run Model Evaluation
```sh
python Model_comparision_TextGeneration.ipynb
```
This generates `model_comparison_results2.csv` with model performance scores.

### 3. Apply TOPSIS
```sh
python -m topsis-LalitSingla-102383006  "model_comparison_results.csv" "0.25,0.20,0.15,0.15,0.15,0.10" "+,+,+,+,+,-" "model_topsis_results"
```
This generates `model_topsis_results2` with the TOPSIS ranking of the models.

## Output
- **`model_comparison_results.csv`** → Contains raw evaluation results.
- **`model_topsis_results.csv`** → Contains final rankings using TOPSIS.

## Output file
![result_table](https://github.com/user-attachments/assets/39372c02-da0f-4217-b356-09918e9d01be)



## Model comparision for Text Generating Models
![topsis_models_comparison](https://github.com/user-attachments/assets/f5d1978b-e216-47a9-94c2-67ee62265508)


## Authors
- **Lalit Singla** (lsingla_be22@thapar.edu)

## License
This project is licensed under the MIT License.

