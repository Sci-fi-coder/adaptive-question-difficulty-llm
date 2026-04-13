Adaptive Question Difficulty Adjustment using LLMs
Overview

This project presents an Adaptive Question Difficulty Adjustment System using Large Language Models (LLMs). The system transforms a given question into an easier or harder version while maintaining the same concept.

The objective is to build an intelligent educational assistant capable of dynamically adjusting question difficulty across multiple domains such as Mathematics and History.

The project explores:

Domain-specific fine-tuning
Multi-stage adapter training
Prompt engineering
Hybrid rule-based approaches
Interactive difficulty control
Motivation

Traditional learning systems provide static questions that do not adapt to learner ability. This project introduces a dynamic system that:

Accepts a base question
Adjusts difficulty (Harder / Easier)
Maintains conceptual consistency
Works across multiple domains

This improves learning personalization and user engagement.

Project Architecture

Pipeline:

User Input  
   ↓  
Domain Selection  
   ↓  
Difficulty Selection (Harder / Easier)  
   ↓  
Fine-Tuned LLM  
   ↓  
Difficulty-Adjusted Question  
Project Stages
Stage 1 — Domain Specific Fine-Tuning (Mathematics)

Objective:
Adapt the base LLM to understand mathematical problems.

Details:

Model: Google Gemma-2B
Training: Domain-specific fine-tuning
Dataset: Mathematics textbook-based dataset
Focus Areas:
Linear equations
Algebra
Basic reasoning

Result:

Improved mathematical understanding
Better structured outputs
Stage 2 — Multi-Domain Difficulty Transformation

Objective:
Train the model to transform question difficulty.

Domains Added:

Mathematics (Linear equations)
Counting Problems
History (Conceptual questions)

Dataset:

Custom dataset (~4000 samples)
Harder and Easier transformations

Challenges:

Model hallucination
Inconsistent outputs
Stage 2 (Hybrid Rule-Based Enhancement)

To reduce hallucination:

Rule-based constraints introduced
Prompt engineering applied
Post-processing added

Results:

Algebra performed very well
Counting problems improved
History questions stable
Overall performance improved significantly

This stage achieved strong and reliable outputs.

Stage 3 — Rule-Free LLM Training

Objective:

Remove rule-based system and rely purely on LLM learning.

Method:

Used Stage-1 adapter
Used Stage-2 adapter
Trained Stage-3 adapter

Results:

~70% accuracy
Reduced dependency on rule-based system
Some hallucination remained
Interactive Interface

A Python-based interactive interface was developed that allows:

Input base question
Select domain (Math / History)
Select difficulty (Harder / Easier)

The system then generates the transformed question dynamically.

Dataset

Custom dataset created using:

Mathematics
Linear equations
Algebra
Counting problems
History
Conceptual questions
NCERT Class 7 History

Dataset Size:

~4000 examples

Dataset Format:

{
  "instruction": "Rewrite question difficulty",
  "input": "Base question",
  "output": "Transformed question",
  "subject": "math/history",
  "concept": "topic"
}
Model Used

Primary Model:

Google Gemma-2B

Training Method:

LoRA Fine-tuning
Parameter Efficient Training

Frameworks Used:

Transformers
PEFT
PyTorch
HuggingFace
Evaluation Strategy

Evaluation Methods:

Manual testing
LLM validation (Planned)
Human evaluation (Planned)

Testing Dataset:

38 base questions
Harder and Easier transformations

Evaluation Metrics:

Accuracy
Concept preservation
Difficulty correctness
Project Structure
Stage1/
    stage1_train.ipynb
    dataset.json
    adapter/

Stage2/
    stage2_train.ipynb
    dataset.json
    adapter/

Stage3/
    stage3_train.ipynb
    test.json
    test_results.json

README.md
requirements.txt
Requirements
transformers
peft
torch
accelerate
datasets
bitsandbytes
How to Run
Stage 1

Run:

stage1_train.ipynb
Stage 2

Run:

stage2_train.ipynb
Stage 3

Run:

stage3_train.ipynb
Future Work
Improve accuracy
Reduce hallucination
Add more subjects
Build web interface
Deploy API
Authors

Adaptive Question Difficulty System
Mini Project