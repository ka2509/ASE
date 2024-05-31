https://www.kaggle.com/code/kuangank/ase-fighting

# Automated Essay Scoring Model

This project aims to develop an automated essay scoring model to streamline the grading process for student essays. The goal is to leverage natural language processing and machine learning techniques to provide timely and accurate feedback to students while reducing the burden on educators.

## Datasets

The following datasets were used in this project:
- Competition dataset
- Kononenko’s Notebook to import pyspellchecker libraries in no-internet mode

## Project Phases

### Phase 1: Dataset Preparation
- **Define Target Variable:** The target variable was defined and encoded using LabelEncoder.
- **Tokenization:** 
  - Initial tokenization involved splitting the essay into individual words. However, this method did not handle punctuation well (e.g., contractions like "don’t", words before and after punctuation, and words enclosed in quotation marks).
  - The `word_tokenize` function from the `nltk` library was used for better accuracy, despite its longer execution time.

### Phase 2: Feature Extraction
- Various features were considered, such as:
  - Total words
  - Total sentences
  - Total length
  - Total stopwords
  - Total spelling errors
  - Average word length
  - Lexical diversity
- After testing, the following features were retained:
  - Total words
  - Total sentences
  - Total spelling errors
  - Average word length
  - Lexical diversity
- **Spelling Errors Count:** 
  - Due to the no-internet rule of the competition, the `pyspellchecker` library was included via Kononenko’s Notebook as a data source.
  - The `word_tokenize` function was used for accurate tokenization, aiding the spell checker in counting misspelled words more accurately.

### Phase 3: Data Splitting
- The training dataset was split into training and validation datasets with adjusted parameters.

### Phase 4: Model Training
- Various machine learning algorithms were experimented with, including Gradient Boosting, Random Forest, and Neural Networks.
- Gradient Boosting was selected as the best-performing model.
- The model was trained on the preprocessed training data to learn patterns and relationships between essay features and scores.

### Phase 5: Model Evaluation
- The model’s performance was evaluated using metrics like Cohen’s Kappa Score, accuracy, and mean squared error.
- Visualizations such as scatter plots and histograms were created to compare actual vs. predicted scores and to gain insights into the model’s performance.

## Conclusion
This project demonstrates the development of an automated essay scoring model that effectively leverages natural language processing and machine learning techniques. The model provides accurate feedback to students, aiding in their learning process while reducing the workload for educators.

