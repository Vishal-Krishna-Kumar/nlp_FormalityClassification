# NLP Final Project - Formality Classification

## Overview
This project aims to classify the formality of given sentences using various machine learning models. We explore character-based preprocessing techniques and implement multiple models including BiLSTM, DeBerta, BERT, and a simple CNN.

## Dataset
We utilize the GYAFC Corpus, specifically focusing on the `Entertainment_Music` domain. The dataset is split into training and test sets containing formal and informal sentences.

## Project Structure
The project is structured into the following sections:
1. **Loading the Dataset**
2. **Preprocessing the Data**
3. **Training the Models**
4. **Evaluating the Models**
5. **Formality Score Calculations**

## How to Run
1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/Formality-Classification.git
    cd Formality-Classification
    ```

2. **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3. **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook NLP_Final_Project_Formality_Classification.ipynb
    ```

## Results
- **BiLSTM Model:** Achieved a high F1 score but required significant computational resources.
- **DeBerta Model:** Outperformed the BiLSTM model in terms of accuracy and F1 score, proving to be the most effective model.
- **BERT Model:** Provided competitive results but was slightly less accurate than DeBerta.
- **CNN Model:** Offered a simpler alternative with decent performance but did not match the accuracy of DeBerta and BERT.

## Conclusion
The project successfully implements multiple models to classify the formality of sentences. DeBerta emerges as the most effective model, offering high accuracy and efficiency. Further improvements can be made by experimenting with other architectures and fine-tuning techniques.
