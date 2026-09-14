# NLP Lab 2 - Emotion Classification

This project was developed for the Natural Language Processing course.

## Objective

The objective is to classify English text messages into six emotion categories:

- Sadness
- Joy
- Love
- Anger
- Fear
- Surprise

The project uses the DAIR.AI Emotion dataset from Hugging Face.

## NLP Pipeline

The project includes:

- Dataset exploration and cleaning
- Duplicate and data leakage detection
- Text preprocessing
- Tokenization
- TF-IDF vectorization
- Linear SVM classification
- DistilBERT fine-tuning
- Model evaluation and comparison

## Models

Two main approaches are compared:

### TF-IDF + Linear SVM

Test Accuracy: approximately 88.3%  
Macro F1-score: approximately 0.824

### DistilBERT

Test Accuracy: approximately 93.2%  
Macro F1-score: approximately 0.898

A tuned version of DistilBERT is also explored using additional epochs, learning-rate warmup and early stopping.

## Installation

A pre-configured Python virtual environment is included in this repository for the project environment used during development.

### Option 1 - Use the included virtual environment

On Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks script execution, you can temporarily allow it for the current terminal session:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy RemoteSigned
```

Then activate the environment again.

### Option 2 - Recreate the environment

If the included virtual environment does not work on your machine, create a new one:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Then open:

```text
LAB2_Emotion_Classification.ipynb
```

and run the notebook cells in order.

### GPU acceleration

The notebook automatically checks whether CUDA is available.

- If a compatible NVIDIA GPU and CUDA-enabled PyTorch installation are available, DistilBERT training uses the GPU.
- Otherwise, the notebook runs on CPU, although DistilBERT training will be slower.

The `requirements.txt` file can be used to recreate the Python environment if necessary.