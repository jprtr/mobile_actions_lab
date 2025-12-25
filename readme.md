# Mobile Actions Lab

## FunctionGemma Fine-tuning for Mobile Actions

This repository contains a Jupyter notebook for fine-tuning FunctionGemma 270M on mobile action tasks.

### Overview

The notebook demonstrates how to:
- Fine-tune FunctionGemma 270M for mobile function calling using the Hugging Face TRL library
- Train the model to handle 7 mobile functions: flashlight control, contact creation, email sending, map navigation, WiFi settings, and calendar events
- Evaluate model performance on mobile action tasks
- Convert the model to `.litertlm` format for on-device deployment

### Requirements

- Google Colab with A100 GPU (Colab Pro subscription or Pay as You Go)
- Hugging Face account with access token
- Python packages: transformers 4.57.1, trl 0.25.1, datasets 4.4.1

### Key Features

**Dataset**: Uses the [Mobile Actions dataset](https://huggingface.co/datasets/google/mobile-actions) with examples for 7 mobile functions

**Training**: 
- Fine-tunes FunctionGemma 270M instruction-tuned model
- 4 epochs with batch size 8 and gradient accumulation
- Completion-only loss for efficient training
- Takes ~8 minutes per epoch on A100 GPU

**Evaluation**: 
- Includes comprehensive evaluation framework
- Compares base vs fine-tuned model performance
- Analyzes function calling accuracy and argument correctness

**Deployment**:
- Converts trained model to `.litertlm` format
- Optimized for on-device deployment
- Compatible with Google AI Edge Gallery

### Usage

1. Open the notebook in Google Colab
2. Accept the FunctionGemma license on Hugging Face
3. Create a Hugging Face access token with write permissions
4. Add the token as a Colab secret named `HF_TOKEN`
5. Run all cells to train and evaluate the model
6. (Optional) Save the converted `.litertlm` model to Google Drive

### Model Performance

The fine-tuned model shows significant improvement over the base model in:
- Correct function selection
- Accurate argument parsing
- Handling relative dates and multi-tool scenarios
- Edge cases like WiFi settings and flashlight operations

### Files

- `FunctionGemma/[FunctionGemma]Finetune_FunctionGemma_270M_for_Mobile_Actions_with_Hugging_Face.ipynb` - Main training notebook

### License

Copyright 2025 Google LLC. Licensed under Apache License 2.0.
