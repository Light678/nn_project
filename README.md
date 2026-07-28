## Sparse Attention in BERT: Improving Efficiency without Sacrificing Quality
This project was developed in the context of the Hauptseminar “Neural Networks and Sequence-to-Sequence Learning”.
The goal was to evaluate how different sparse attention mechanisms can improve the computational efficiency of BERT while maintaining comparable model quality on masked language modeling tasks.

## Project Summary

1. I implemented and compared several BERT variants trained on a 5 M token subset of WikiText-103:

2. Baseline (Dense Attention) – the standard BERT model with full self-attention, serving as the performance reference.

3. Local Window Attention – each token attends only to a fixed-size neighborhood, reducing quadratic complexity to linear with respect to the window size.

4. Longform Attention – extends Local Window with sparse global connections (CLS token + strided anchors) to enable long-range information flow.

The models were compared in terms of perplexity, runtime, tokens per second, and GPU memory consumption.
Results showed that sparse variants significantly improved runtime and memory efficiency while retaining strong model quality:
- Local Window reduced memory use by over 60 % but suffered higher perplexity due to limited context.
- Longform maintained near-baseline perplexity ( ≈ +3.8 % ) while achieving faster inference and lower memory load.

Note: ChatGPT was used as support for debugging and commenting the scripts.

## Repository Structure
```
NN-Project/
├── Baseline                   ← BERT Baseline
├── Report                     ← Final report
├── Variant_1_local_window     ← BERT with Local Window Variant 
├── Variant_2_longform         ← BERT with Longform Variant
├── README.md                  ← This file
├── requirements.txt           ← libraries requirements

```

## Author:
```
Name: Jonas Alexander Lütticken
Matriculation: 4218670
University: Heidelberg University
Course: Neural Networks and Sequence-to-Sequence Learning
Semester: SS25
Supervisor: Prof. Michael Staniek
```
