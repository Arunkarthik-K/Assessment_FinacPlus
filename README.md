# *Assessment Report for FinacPlus Project*
## *Introduction*
*This report outlines the various stages and methodologies employed in completing the FinacPlus assessment project. The project focuses on the extraction, preprocessing, and classification of financial document types using advanced machine learning techniques. The primary objective is to identify and categorize financial documents such as Balance Sheets, Cash Flows, Income Statements, Notes, and Others with high accuracy.*

## *Data Extraction and Preprocessing*
### *Keyword Collection*
- *Keywords relevant to different financial documents (Balance Sheets, Cash Flow, Income Statement, Notes, Others) were collected.*
- *These keywords serve as a basis for identifying and categorizing the financial files.*
### *HTML File Processing*
- *HTML files were loaded from a specified file location.*
- *Extracted content included folder names, file names, number of rows and columns, keyword counts, and text.*
- *The extracted information was stored in a dictionary, which was then converted into a dataframe for further processing.*
## *Text Embedding*
### *Embedding Process*
- *Utilized Hugging Face's transformer models to convert text into embeddings.*
- *Specifically, the "distilbert-base-uncased" tokenizer and embedding model were employed.*
- *The process was optimized to use a GPU if available, otherwise defaulting to a CPU.*
### *Storage of Embedded Text*
- *The text was embedded in batches and stored in a new column named "embeddings" within the dataframe.*
## *Handling Data Imbalance*
### *Identifying Imbalance*
- *The dataset exhibited significant imbalance across different document types:*
  - *Balance Sheets: 271 files*
  - *Cash Flow: 37 files*
  - *Income Statement: 306 files*
  - *Notes: 691 files*
  - *Others: 1225 files*
### *SMOTE Technique*
- *Synthetic Minority Over-sampling Technique (SMOTE) was applied to balance the dataset.*
- *Features and targets were passed to the SMOTE class to generate a balanced dataset, which was stored in a new dataframe.*
## *Label Encoding*
### *Target Encoding*
- *The XGBClassifier model requires numerical targets for training.*
- *Label encoding was used to convert categorical targets into numerical values.*
### *Model Storage*
- *The label encoding model was stored using the pickle module, saved in a .pkl format for later use.*
## *Train Test Split*
### *Data Splitting*
- *The dataset was split into training and testing sets using the train_test_split function.*
- *This ensured the model could be trained on one portion of the data (X_train, y_train) and tested on another (X_test, y_test) to evaluate performance.*
## *Model Training*
### *Model Selection*
- *Three different models were defined and evaluated, with a particular focus on the XGBClassifier.*
- *Each model was trained using the training dataset (X_train, y_train).*
### *Model Evaluation*
- *The performance of each model was assessed to determine the best performing one.*
### *Model Storage*
- *All trained models were stored using the pickle module in .pkl format for future predictions.*
## *Model Prediction*
### *Loading and Predicting*
- *Stored models were loaded from files.*
- *Predictions were made on the X_test dataset.*
### *Performance Analysis*
- *Accuracy scores and classification reports were used to analyze and compare model performance.*
## *User Interface*
### *Gradio Application*
- *Gradio was used to build a user-friendly interface for interacting with the model.*
- *The interface allows users to upload a file and receive predictions on the document type.*
### *Implementation Steps*
1. _**Load the Dataset:** Users load the dataset as a zip file._
2. _**Run All Cells:** Users execute all cells in the notebook to perform the complete workflow._
3. _**Build Gradio Interface:** Upon successful execution, the Gradio interface is built._
4. _**File Classification:** Users can upload files through the interface to classify the document type._
## Conclusion
*This project successfully implemented a comprehensive workflow to extract, preprocess, and classify financial documents. By addressing data imbalance and leveraging advanced machine learning models, the system demonstrates robust performance in document categorization. The user interface further enhances usability, allowing seamless interaction and predictions. The methodologies and results from this project can be extended and refined for broader applications in financial document analysis.*
