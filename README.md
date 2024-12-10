# Cyber Threat Detection using Deep Learning

## Overview

Cyber threats are a growing concern for organizations worldwide, encompassing malware, phishing, and denial-of-service (DOS) attacks. These threats compromise sensitive information and disrupt operations. Traditional threat detection methods often fall short due to their inability to adapt to evolving threats. This project leverages **deep learning** to proactively detect and mitigate cyber threats, providing organizations with robust defense mechanisms.

This repository contains the implementation of a deep learning model designed to detect cyber threats using the **BETH dataset**, which simulates real-world logs. By successfully developing this model, we aim to enhance cybersecurity measures and contribute to organizational security.

## Features
- **Deep learning model:** Designed to analyze large volumes of log data and identify suspicious patterns.
- **Preprocessed dataset:** The BETH dataset, with a target label (`sus_label`), indicates whether an event is malicious (1) or benign (0).
- **Validation accuracy goal:** Achieve a minimum validation accuracy of 60% within 10 training epochs.

## Dataset

### Description
The BETH dataset simulates real-world logs and includes the following columns:

| Column              | Description                                                  |
|---------------------|--------------------------------------------------------------|
| `processId`         | Unique identifier for the process generating the event (int64)|
| `threadId`          | ID for the thread spawning the log (int64)                   |
| `parentProcessId`   | Label for the process spawning the log (int64)               |
| `userId`            | ID of the user spawning the log (int64)                      |
| `mountNamespace`    | Mounting restrictions the process log works within (int64)   |
| `argsNum`           | Number of arguments passed to the event (int64)              |
| `returnValue`       | Value returned from the event log, usually 0 (int64)         |
| `sus_label`         | Binary label indicating suspicious activity (1: suspicious, 0: benign) |

For more details on the dataset, see the [BETH dataset documentation](accreditation.md).

## Requirements

This project uses **Python** and the following libraries:
- [PyTorch](https://pytorch.org/) for model training and evaluation
- NumPy for numerical operations
- Pandas for dataset manipulation


## How to Use

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Aziz-BenAmira/cyber-threat-detection.git
   cd cyber-threat-detection
   ```

2. **Prepare the dataset:**
   - Ensure the BETH dataset is placed in the `data/` directory.

3. **Train the model:**
   - Run the training script:
     ```bash
     python train.py
     ```
   - The script will train the neural network for 10 epochs and save the validation accuracy as `val_accuracy`.

4. **Evaluate the model:**
   - Use the test dataset to evaluate model performance and calculate precision, recall, and F1-score.

## Model Training Details

- **Architecture:** A basic feedforward neural network is used with fully connected layers.
- **Training:** The model is trained using cross-entropy loss and the Adam optimizer.
- **Validation Accuracy:** Targeted minimum validation accuracy of **60%**.

Feel free to contribute or open issues for discussion.
