# Translation Assignment - English into Hinglish

## 1. Project Overview
##### Hinglish Translation Model
### Introduction

  This project aims to develop a Python-based Hinglish translation model that can convert English text into a simplified form of Hindi and English mixed language, known as Hinglish. The goal is to make the translated text     sound natural and easy to understand for both native Hindi speakers and non-native Hindi speakers.

### Purpose

  The primary purpose of this project is to bridge the language gap between English and Hindi, particularly for users who are more comfortable with a blend of both languages. Hinglish is commonly spoken and used in various   informal and online communication channels, making it essential to provide accurate and fluent translations.

### Features
  1. Translation Accuracy: The model will accurately convert complex English words and phrases into their Hinglish equivalents while preserving simplicity.
  2. Fluency: The translated text will sound natural and colloquial, resembling how a casual Hinglish speaker would express themselves.
  3. Understandability: The Hinglish translations will be easy to comprehend for non-native Hindi speakers and those familiar with the Hinglish dialect.

## 2. Setup

  To get started with the Hinglish Translation Model project, you'll need to set up a Python environment and install the necessary libraries. We'll cover the installation of libraries like numpy, pandas, matplotlib,           TensorFlow, and Keras, which are commonly used for data processing and machine learning tasks.
  Prerequisites
  
    Python 3.x installed on your system.
    Pip, the Python package manager, should also be available.

### Installation Steps

    Python Environment: If you haven't already, install Python 3.x on your system. You can download it from the official Python website: python.org.

    Virtual Environment (Optional but Recommended): It's a good practice to create a virtual environment for your project to manage dependencies cleanly.
        
#### Install virtualenv using pip
    pip install virtualenv
    
#### Create a new virtual environment
    virtualenv hinglish_translation_env
    
#### Activate the virtual environment (on Windows)
    hinglish_translation_env\Scripts\activate
    
#### Activate the virtual environment (on macOS and Linux)
    source hinglish_translation_env/bin/activate
#### Navigate to your project directory
    cd your_project_directory
    
    # Create a requirements.txt file (if not already created)
    touch requirements.txt
    Add the following lines to your requirements.txt file:

#### Add the following lines to your requirements.txt file:
  
    numpy==1.21.2
    pandas==1.3.3
    matplotlib==3.4.3
    tensorflow==2.6.0
    keras==2.6.0

#### Install the libraries by running:
    pip install -r requirements.txt

#### Verifying the Setup
  To verify that your setup is successful, you can create a Python script and import the required libraries and you can check the versions. For example:
    
    import numpy as np
    import pandas as pd
    import matplotlib.pyplot as plt
    import tensorflow as tf
    from tensorflow import keras

    print("NumPy version:", np.__version__)
    print("Pandas version:", pd.__version__)
    print("Matplotlib version:", plt.__version__)
    print("TensorFlow version:", tf.__version__)
    print("Keras version:", keras.__version__)


## 4. Usage
  
  Using the Hinglish Translation Model is straightforward. You can incorporate it into your Python script or application to translate English text into Hinglish. Below are the steps to utilize the model effectively:
    
  1. Import the Required Libraries
  Ensure you have imported the necessary libraries, as mentioned in the "Setup" section of this README.
  2. Define the Translation Logic

  Write a function that takes an English text as input and returns the corresponding Hinglish translation. This function should tokenize the English text, identify words or phrases that require translation, and replace       them with Hinglish equivalents.

      def decode_sequence(input_seq):
        # Encode the input as state vectors.
        states_value = encoder_model.predict(input_seq)
    
        # Generate empty target sequence of length 1.
        target_seq = np.zeros((1, 1, num_decoder_tokens))
        # Populate the first character of target sequence with the start character.
        target_seq[0, 0, target_token_index["\t"]] = 1.0
    
        # Sampling loop for a batch of sequences
        # (to simplify, here we assume a batch of size 1).
        stop_condition = False
        decoded_sentence = ""
        while not stop_condition:
            output_tokens, h, c = decoder_model.predict([target_seq] + states_value)
    
            # Sample a token
            sampled_token_index = np.argmax(output_tokens[0, -1, :])
            sampled_char = reverse_target_char_index[sampled_token_index]
            decoded_sentence += sampled_char
    
            # Exit condition: either hit max length
            # or find stop character.
            if sampled_char == "\n" or len(decoded_sentence) > max_decoder_seq_length:
                stop_condition = True
    
            # Update the target sequence (of length 1).
            target_seq = np.zeros((1, 1, num_decoder_tokens))
            target_seq[0, 0, sampled_token_index] = 1.0
    
            # Update states
            states_value = [h, c]
        return decoded_sentence


  You can now generate decoded sentences as such:

    for seq_index in range(20):
        # Take one sequence (part of the training set)
        # for trying out decoding.
        input_seq = encoder_input_data[seq_index : seq_index + 1]
        decoded_sentence = decode_sequence(input_seq)
        print("-")
        print("Input sentence:", input_texts[seq_index])
        print("Decoded sentence:", decoded_sentence)


    
## 5. Evaluation

  Evaluating the performance of the Hinglish Translation Model is essential to ensure the accuracy, fluency, and understandability of the generated Hinglish text. This section provides guidelines on how to evaluate the       model effectively.

  ![image](https://github.com/rkgupta7463/Openinapp-Company-Assignment/assets/96177171/7a33e035-5dd9-4d58-b210-5580b2b8750e)
  ![image](https://github.com/rkgupta7463/Openinapp-Company-Assignment/assets/96177171/3c921e09-d611-4de5-8d0c-a6647f4f3e42)

  
## 6. Results
  ![image](https://github.com/rkgupta7463/Openinapp-Company-Assignment/assets/96177171/54fb0689-1892-4926-ab10-f9b06659a730)
  ![image](https://github.com/rkgupta7463/Openinapp-Company-Assignment/assets/96177171/c9710d9d-6b66-4b98-a939-e1408a2ddd44)

