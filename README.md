# Cross-lingual Detection of Vaccine Misinformation in Mongolian

Can an English-trained multilingual model (XLM-RoBERTa) detect Mongolian vaccine misinformation?

MSc dissertation project, Northumbria University London, 2026. Includes the first labelled dataset of Mongolian vaccine-related claims.

## What this does

Trains XLM-RoBERTa on English fact-checking data (CONSTRAINT@AAAI2021, PUBHEALTH), then tests transfer to a purpose-built Mongolian dataset of 495 claims collected from MFCC, FactCheck.mn and iToim.mn. Measures zero-shot performance, how much Mongolian data is needed to close the gap, and whether a COVID-trained model generalises to non-COVID vaccine claims.

## Results

| | macro-F1 |
|---|---|
| English test set (ceiling) | 0.865 |
| Mongolian, zero-shot | 0.425 |
| Mongolian, +100 fine-tuning examples | 0.869 |

Zero-shot transfer fails — below random. Around 100 Mongolian examples recovers English-level performance, though results at smaller sizes are unstable across seeds.

**Caveat.** Mongolian reliable claims came largely from formally worded official sources, so the model can separate classes on register alone. Scores on Mongolian non-COVID claims are inflated as a result. Detailed in the dissertation.

## Setup

`notebooks/fine_tuning_final.ipynb` runs the full pipeline. Open in Colab with a T4 GPU; roughly 1–2 hours end to end. Seeds 42, 123, 2024.

The Mongolian dataset is not committed pending a decision on redistribution terms with the source outlets — contact me for research access.

## Licence

Code under MIT. Source claims remain the property of the originating fact-checking organisations.
