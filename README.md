https://www.kaggle.com/code/kuangank/ase-fighting

As part of this project, I aim to develop an automated essay scoring model to streamline
the grading process for student essays. The goal is to leverage natural language 
processing and machine learning techniques to provide timely and accurate feedback to 
students while reducing the burden on educators.

Selecting datasets: I used the following datasets:
 • Competition dataset.
 • Kononenko’s Notebook to import pyspellchecker libraries in no-internet mode.
Phase1: 
Dataset preparation: 
First I defined target variable and
encode it using LabelEncoder. Then I tokenize each essay
splitting text into individual words.
I tried to tokenize by a simple way like: split the essay and
scan each word if it is alpha and add it into a list. But the
problem is it can not scan words that contain punctuation,
such as contractions like ”don’t”, words before and after a
dot and words enclosed in quotation marks.
So I decided to use the word tokenize function from the nltk
library. This method took the kernel a long time to execute
but resulted in better accuracy.
Phase2: Extract features: 
I listed some featured that I can extract
from the essay such as: total words, total sentences, total
length, total stopwords, total spelling errors, average word
length, lexical diversity.
After some tests and entries with better score, I decided
to keep: total words, total sentences, total spelling errors,
average word length and lexical diversity as main features.
At this phase, I got problem while counting the total spelling
errors. The rule of the competition is that we need to submit
the code in the no-internet mode. So I can not install the
library to use it for spell checking tasks. So I had to add
Kononenko’s Notebook as a data source to my main notebook.
And as I mentioned above, I used a function word tokenize to
tokenize the essay. Although the complexity of this function
is quite large, it tokenized quite accurately. So in this step,
spell checker checked the number of misspelled words more
accurately.
Phase3: Split data into train and validation sets: 
I split the training dataset into training and validation dataset with adjusted parameters.
Phase4: Train model: 
Experiment with various machine learning
algorithms such as Gradient Boosting, Random Forest, and
Neural Networks to identify the best-performing model.
And finally, I used Gradient Boosting. Train the selected
model on the preprocessed training data to learn patterns and
relationships between essay features and scores.
Phase5: Model Evaluation: 
Evaluate the model’s performance using
metrics like Cohen’s Kappa Score, accuracy, and mean squared
error. Then create visualizations such as scatter plots and
histograms to compare actual vs. predicted scores and gain
insights into the model’s performance
