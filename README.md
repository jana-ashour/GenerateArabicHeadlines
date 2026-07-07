# Arabic Multi-Style Headline Generation

**Author:** Jana Ashour

## Task

Generate Arabic news headlines in multiple journalistic styles (analytical,
breaking, simple) directly from article text, using fine-tuned seq2seq
transformer models. Given an article, the model is prompted to extract the
core facts and produce three distinct headline styles at once — with the
breaking-news style constrained to start with "عاجل:" ("Breaking:").

## Contents

- `arabic_headline_generation_arabart_arat5_mt5.ipynb` — full notebook: data
  loading, prompt construction, fine-tuning, evaluation, and generation
  comparison across models

## Models Compared

- **AraBART** (`moussaKam/AraBART`)
- **AraT5v2**
- **mT5-small**

## Approach

- Dataset: custom Arabic headline dataset (`HeadlinesStylesDataSet.xlsx`)
  with article text paired with gold analytical, breaking, simple, and
  original headlines
- Each model is fine-tuned as a seq2seq task: article → structured output
  containing extracted facts plus all three headline styles
- Evaluation via ROUGE and BLEU (SacreBLEU) against gold headlines on a held-
  out test set
- Qualitative comparison of generated vs. gold headlines across styles

## Findings

AraBART was the strongest performer among the three models for this task,
producing more fluent and faithful Arabic headlines across all three styles
compared to AraT5v2 and mT5-small.
