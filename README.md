# sms_spam_detector

## Module 21 Challenge
The module has code to build an SMS text classification solution into a function that constructs a linear Support Vector Classification (SVC) model. The model is created and trained using data from a source Resources/SMSSpamCollection.csv that contains 5572 rows × 2 columns:
1) text_message- containing text from text messages
2) lable- with the classificatin lebel of 'ham' for good messages and 'spam' for spam messages

## Model
SMS text classification is done via A linear Support Vector Classification (SVC) model.The above data is split into training and testing  dataframes based on a sampe split of 33%. 
2 functions were created:

### **sms_classification -**

function performs SMS classification using a pipeline with TF-IDF vectorization and Linear Support Vector Classification.
Parameters: sms_text_df (pd.DataFrame): DataFrame containing 'text_message' and 'label' columns for SMS classification. the function  returns 'text_clf' a Fitted pipeline model for SMS classification. This function takes a DataFrame with 'text_message' and 'label' columns, splits the data into training and testing sets, builds a pipeline with TF-IDF vectorization and Linear Support Vector Classification, and fits the model to the training data. The fitted pipeline is returned to make future predictions.

### **sms_prediction -**

Function built to predict the classification of a new text by Creating a variable that will hold the prediction of a new text.
Uses a conditional statement that determines if the text message is "ham" or “spam”.
1) If the message is “ham”, the function should return the following message: f'The text message: "{text}", is not spam.'
2) If the message is spam, the function should return the following message: f'The text message: "{text}", is spam.'


## App creation:
In the final section Gradio app is used to host the application, enabling users to test text messages. The application will provide feedback to users, indicating whether the text is classified as spam or not, based on the model's performance.

## Obervations:
Data used to train the model shows using stop_words ='english', to filter out connection words, is actually performing less effectively on test sampes of text messages. Setitng it to 'None' has a better effect.
