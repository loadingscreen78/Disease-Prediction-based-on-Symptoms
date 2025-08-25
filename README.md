# Disease-Prediction-based-on-Symptoms


This project implements a disease prediction system using a neural network classifier (MLPClassifier) based on symptom input. The system is trained on a dataset of symptoms and associated diseases, utilizing a one-hot encoding scheme for symptom representation.

## Dataset

The project utilizes the `ddxplus_loaded_data.csv` dataset. This dataset contains information on patient age, differential diagnoses, sex, pathology (the predicted disease), evidences (symptoms), and initial evidence.

The 'EVIDENCES' column, which contains lists of symptoms for each record, is the primary feature source for the model. The 'PATHOLOGY' column serves as the target variable (the disease to be predicted).

## Methodology

1.  **Data Loading and Inspection**: The `ddxplus_loaded_data.csv` dataset is loaded into a pandas DataFrame. Initial inspection is performed to understand the data structure, column types, and sample values.

2.  **Symptom Extraction and Encoding**:
    *   Symptoms are extracted from the 'EVIDENCES' column. Since the symptoms are stored as string representations of lists, they are parsed using `ast.literal_eval`.
    *   A unique list of all symptoms present in the dataset is created.
    *   Symptoms are one-hot encoded, creating a binary feature vector for each record where each element corresponds to a unique symptom, with a value of 1 indicating the presence of the symptom and 0 indicating absence. The 'INITIAL_EVIDENCE' is also included in this encoding.

3.  **Model Training**:
    *   The data is split into training and testing sets.
    *   An MLPClassifier from scikit-learn is initialized and trained on the one-hot encoded symptom data (features) and the corresponding diseases (target variable).

4.  **Prediction**:
    *   The trained model can be used to predict diseases based on user-provided symptoms.
    *   User-input symptoms are also converted into a one-hot encoded vector using the same unique symptom list used during training.
    *   This one-hot encoded vector is then fed into the trained MLPClassifier to get the disease prediction.

## How to Use

1.  **Load and Run the Notebook**: Ensure you have the `ddxplus_loaded_data.csv` file available and run the notebook cells sequentially.
2.  **Data Inspection**: Review the data loading and inspection steps to understand the dataset being used.
3.  **Model Training**: The model will be trained automatically.
4.  **User Input Prediction**: The notebook includes a section for user input prediction. You will be prompted to enter the numbers corresponding to the symptoms you are experiencing from the provided list.
5.  **View Prediction**: The system will output the predicted disease based on your input symptoms.

## Dependencies

*   pandas
*   numpy
*   scikit-learn
*   ast

This project demonstrates a practical application of machine learning for disease prediction, highlighting the steps from data processing to model deployment for making predictions based on symptomatic information.
