# Grammar Scoring Engine for Spoken English 
📘 Overview

📄 **[Read Full Project Report](https://github.com/Vishal9028/Grammar-Scoring-Engine-for-Spoken-English — Contains detailed explanations on the pipeline architecture, preprocessing, feature extraction, and evaluation metrics.

📘 ### Project Summary

This project implements an automated Grammar Evaluation System designed to assess spoken English responses. The input consists of short speech recordings (approximately 45–60 seconds each), and the system assigns a grammar proficiency score ranging from 0 to 5, aligned with MOS-style human ratings.

To closely approximate expert judgment, the solution adopts a hybrid modeling strategy that blends deep learning techniques with traditional machine learning. The system evaluates two core aspects of grammar:

Correctness – identification of grammatical errors and inconsistencies

Complexity – analysis of sentence structure, syntax, and linguistic variety

By combining these perspectives, the model delivers reliable and human-aligned grammar scores.

📄 Detailed Documentation:
A comprehensive project report explaining the system architecture, data processing steps, feature extraction methods, and evaluation strategy is available here:
Project Report

🛠️ System Architecture & Workflow

The end-to-end pipeline consists of the following stages:

🎧 Audio Processing & Speech-to-Text

Audio normalization and silence removal applied to .wav files

Speech transcription performed using OpenAI Whisper (base model)

✂️ Transcript Refinement

Elimination of filler words such as “uh”, “um”, and “you know”

Consistent punctuation and formatting applied to improve NLP accuracy

🧩 Linguistic Feature Extraction

Grammar mistake detection using language_tool_python

Syntactic and structural features extracted via spaCy

Part-of-speech variation

Sentence length and construction patterns

Grammar correction–based edit distance calculated using a GEC model

🤖 Scoring Model (Hybrid Approach)

DistilBERT regression model fine-tuned on processed transcripts

Ensemble of classical ML models (Random Forest, LightGBM, Ridge Regression) using handcrafted linguistic features

A meta-level regressor fuses predictions from both approaches to produce the final grammar score

📊 Validation Results

Performance was evaluated on a held-out validation set:

Metric	Score
Mean Absolute Error	0.763
Root Mean Squared Error	0.911
Pearson Correlation	0.625

Despite a relatively limited dataset (444 speech samples), the model demonstrates strong correlation with human scores and effective ranking capability, making it suitable for scalable assessment scenarios.

📁 Generated Outputs

Final predictions are exported to 'submission.csv'

Grammar scores are rounded to whole numbers to match Likert-scale grading requirements

The challenge is tackled by combining the *best of deep learning and classical ML*, creating a *hybrid ensemble model* that mimics expert human scoring by evaluating both:
- *Grammatical Accuracy** (via error detection and correction)
- *Grammatical Sophistication** (via sentence structure and syntactic complexity)

🏁 Conclusion

This project showcases how the integration of speech recognition, natural language processing, and machine learning can effectively automate grammar assessment for spoken English. The design is modular, explainable, and adaptable, making it well-suited for deployment in educational platforms, language testing systems, and AI-based interview evaluation tools.