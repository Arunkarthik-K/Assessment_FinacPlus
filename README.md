# Assessment_FinacPlus

# Data Extraction and Preprocessing:
1. Collect the keywords of the financial files of Balance Sheets, Cash Flow, Income Statement, Notes, Others.
2. Load HTML files from the file location and extract contents.
3. Contents include folder name, file name, no of rows & columns, keywords count and text.
4. Convert the dict to dataframe.

# Embedding:
1. With the use of hugging face text is converted into embeddings.
2. Load tokenizer and embedding model for embeddings with "distilbert-base-uncased".
3. Device: use GPU if available or else CPU
4. Embedded the text with batch.
5. Store the embedded text in a new column "embeddings" in the same dataframe.

# Handle the Imbalance:
1. Here we have an imbalanced data.
2. Balance Sheets with 271 html files, Cash Flow with 37 html files, Income Statement with 306 html files, Notes with 691 html files, Others with 1225 html files.
3. By training the same data with model we get the unexpected results.
4. To overcome this we using SMOTE technique.
5. We passing the features and target to this class to comeup with balanced data.
6. Finally we storing the new balanced data in a new dataframe.

# Label Encoding:
1. We using the XGBClassifier model for our scenario.
2. To use this model we need to have the target in numbers.
3. So for this we using label encoder to convert the traget to numbers.

# Storing the label encoding model:
1. To store the model we use the module called pickle.
2. With the help of pickle we storing the model in a pkl format.

# Train Test Split:
1. To train the model we should have a two dataset train and test.
2. For this using train_test_split function to split the entire dataset as X_train, X_test, y_train, y_test.

# Train Model:
1. Here we using 3 different model but specially XGBClassifier.
2. We defining all 3 models.
3. Fit the X_train and y_train dataset to all 3 model to check which model is performing better.

# Storing the model:
1. To store the model we use the module called pickle.
2. With the help of pickle we storing the all the model in a pkl format to predict the results.

# Predict the model:
1. Load the stored model from the file.
2. once the model the retrived, predict the results with X_test dataset.
3. Use the accuracy score and classification report to analys the performance.

# UserInterface:
Here I using the Gradio application for the user intreaction.


# Steps:
Step 01: Load the dataset as a zip file.
Step 02: Then run the entire cell to perform all the actions.
Step 03: Once the entire cell runned successfully the gradio interface will be build.
Step 04: With the help of interface we can pass the file that we wants to find what kind of file.
