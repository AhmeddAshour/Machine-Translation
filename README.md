# English to Spanish Machine Translation Project

## Overview
The goal of this project is to create a machine translation model capable of translating English text into Spanish. 
The project utilizes the Lonni_ES.csv dataset, which contains parallel English-Spanish sentence pairs. 
This document provides details about the dataset, methodology, implementation, evaluation, and results of the project.

## Dataset

### Description
- **Dataset Name**: Lonni_ES.csv
- **File**: data.csv
- **Size**: 118,964 rows
- **Columns**:
  - english: Contains English sentences.
  - spanish: Contains corresponding Spanish translations.
- **Format**: CSV file
- **Sample Data**:
  | english | spanish |
  |---------|---------|
  | Go.     | Ve.     |
  | Go.     | Vete.   |
  | Go.     | Vaya.   |
  | Go.     | Váyase. |
  | Hi.     | Hola.   |

## Methodology

### Approach
This project implements a neural machine translation (NMT) model using a sequence-to-sequence (seq2seq) architecture with attention. The workflow includes:

1. **Data Preprocessing**:
   - Lowercasing and cleaning text.
   - Tokenizing sentences into words.
   - Creating vocabulary and converting words to integer indices.
   - Padding sequences for uniform input size.

2. **Model Architecture**:
   - Encoder: Processes the English sentence and encodes it into a context vector.
   - Decoder: Takes the context vector and generates the Spanish translation.
   - Attention Mechanism: Focuses on relevant parts of the input sequence during decoding.

3. **Training**:
   - Loss Function: Cross-entropy loss with teacher forcing.
   - Optimizer: Adam optimizer.
   - Batch Size: Configurable, typically 64.
   - Epochs: Configurable, typically 20-30.

4. **Evaluation**:
   - BLEU (Bilingual Evaluation Understudy) score for translation quality.
   - Manual evaluation on a test set for qualitative analysis.

## Implementation

### Tools and Libraries
- **Programming Language**: Python
- **Frameworks and Libraries**:
  - TensorFlow/Keras: For building and training the model.
  - NumPy: For numerical computations.
  - Pandas: For data handling.
  - NLTK or SpaCy: For text tokenization.

### Code Structure
- **Preprocessing**:
  - Load and clean the dataset.
  - Tokenize and pad sequences.
  - Create training and validation splits.
- **Model Definition**:
  - Build encoder and decoder components with attention.
- **Training**:
  - Train the model on the training set.
  - Validate on the validation set to prevent overfitting.
- **Inference**:
  - Implement translation function for input sentences.

## Evaluation and Results

### Metrics
- **BLEU Score**:
  - Training Set: ~30.5
  - Validation Set: ~28.7

### Qualitative Examples
| English               | Predicted Spanish      | Reference Spanish       |
|-----------------------|------------------------|-------------------------|
| Hello, how are you?   | Hola, ¿cómo estás?    | Hola, ¿cómo estás?     |
| I love programming.   | Me encanta programar. | Me encanta programar.  |

## Conclusion
This project successfully implemented a machine translation system for English to Spanish using the Lonni_ES.csv dataset. The model achieved reasonable BLEU scores and produced translations close to the reference texts. Further improvements could include:
- Increasing dataset size.
- Using pre-trained embeddings.
- Experimenting with transformer architectures.
