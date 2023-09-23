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

  In this section, we will guide you through the process of setting up the machine translation model for English to Hinglish translation using the Hugging Face Transformers library.
  #### 1. Prerequisites
  
  Before you get started, ensure that you have the following prerequisites installed:

    Python 3.x
    Hugging Face Transformers library
    An internet connection (for downloading pre-trained models)


  #### 2. Installation

  First, clone the repository containing your project or create a new one: 
    
    # Clone your project repository
    git clone https://github.com/rkgupta7463/Openinapp-Company-Assignment.git
        
    # Navigate to the project directory
    cd your-repo
  
  Install the required Python packages, including the Hugging Face Transformers library:
  
  # Install the Hugging Face Transformers library
    pip install transformers torch
    pip install sentencepiece
    pip install sacremoses

## 3. Usage

  Now that you have the project and dependencies set up, you can use the machine translation model to translate English text to Hinglish.
  Modify the input_statement variable in your Python script with the text you want to translate.

  #### python

    from transformers import MarianTokenizer, MarianMTModel

    # Define the input statement in English
    input_statement = "I had about a 30-minute demo just using this new headset"
    
    # Define the model and tokenizer for English to Hindi translation
    model_name = "Helsinki-NLP/opus-mt-en-hi"
    tokenizer = MarianTokenizer.from_pretrained(model_name)
    model = MarianMTModel.from_pretrained(model_name)
    
    # Translate the input statement to Hindi
    translated_statement = model.generate(**tokenizer(input_statement, return_tensors="pt", padding=True))
    translated_statement = tokenizer.decode(translated_statement[0], skip_special_tokens=True)
    
    # Print the translated statement
    print(translated_statement)

  Now you can run your Python script to perform English to Hindi translation. Make sure to customize the input_statement variable with the text you want to translate.

## 4. Additional Information

  If you encounter any issues during setup or usage, refer to the Hugging Face Transformers documentation for troubleshooting and further information: Hugging Face Transformers Documentation.

## 5. Results

  In this section, we present the results of using the machine translation model for English to Hindi translation. Below, you can find translated examples and any additional   insights gained from the model's performance.
  Translated Examples
  
  Here are some examples of English text translated to Hindi using the model:
  
  #### input_statement 
    
    "I had about a 30 minute demo just using this new headset"  
  #### Sample Output
  
    मैं 30 मिनट डेमो था सिर्फ इस नए सिरसेट का इस्तेमाल
