AutoML

## 1- Identify the steps of the machine learning workflow completed by AutoML.


    AutoML (Automated Machine Learning) is designed to automate and streamline various steps in the machine learning workflow. Here are the typical steps completed by AutoML:

    1- Data Preprocessing: AutoML often includes data preprocessing functionalities such as handling missing values, outlier detection, feature scaling, and transformation. It automates these tasks to ensure the data is properly prepared for training models.

    2- Feature Engineering: AutoML can automatically generate and select relevant features from the raw data. It explores different feature combinations, performs feature extraction, and applies techniques like one-hot encoding, feature hashing, or embedding to enhance the representation of the data.

    3- Model Selection: AutoML assists in selecting the appropriate machine learning algorithm or model for the given task. It automatically tests multiple algorithms, compares their performance, and recommends the best models based on metrics like accuracy, precision, recall, or F1 score.

    4- Hyperparameter Tuning: AutoML optimizes model performance by fine-tuning hyperparameters. It performs an automated search over a range of hyperparameter values, such as learning rate, regularization rate, or number of layers, to identify the optimal combination that maximizes model performance.

    5- Model Evaluation: AutoML evaluates the trained models using appropriate evaluation metrics. It may employ techniques like cross-validation or train/validation/test splits to assess model performance and generalize well to unseen data.

    6- Model Deployment: Once the best model is selected, AutoML facilitates the deployment of the model into production or operational systems. It may generate deployment-ready code, provide APIs or model endpoints, and generate documentation to support the integration of the model into production workflows.

    7- Monitoring and Maintenance: AutoML may include capabilities to monitor model performance and detect model drift. It helps to ensure that the deployed model continues to perform effectively and alerts users when retraining or updates are required.

    AutoML aims to accelerate the machine learning workflow, reduce manual effort, and leverage automation to improve the efficiency and productivity of the data science process.
    
## 2- Identify how to locate the source code for the best model produced by AutoML.
    To locate the source code for the best model produced by AutoML, you can follow these steps:

    1- Identify the best model: First, you need to identify the best model produced by AutoML. This can be done by reviewing the results of the AutoML run. Look for the model with the highest performance metric (e.g., highest accuracy, lowest error).

    2- Access the best model details: Once you have identified the best model, you can access its details. In Databricks, you can do this by navigating to the AutoML UI and selecting the best model from the list of models generated.

    3- Review the model details: In the best model's details page, you can find information such as the model type, hyperparameters, and performance metrics.

    4- Locate the source code: To locate the source code for the best model, you can look for the "Training Script" or "Source Code" section in the model details. This section usually contains the code that was used to train and build the model.

    Note: The availability of the source code depends on how the model was trained. If the model training process used a specific training script or code, then the source code will be available. However, if the model was trained using an algorithm or library that doesn't expose the source code, then the source code may not be directly accessible. In such cases, you may only see the hyperparameters or configuration used for training.


```python
from mlflow.tracking import MlflowClient

# Set the experiment ID
experiment_id = "<experiment_id>"

# Instantiate an MLflow client
client = MlflowClient()

# Get the best run from the experiment
best_run = client.search_runs(experiment_ids=experiment_id, order_by=["metrics.<metric> DESC"], max_results=1)[0]

# Get the run ID of the best run
best_run_id = best_run.run_id

# Get the source code for the best run
source_code = client.get_run(best_run_id).data.params["artifact_uri"]

# Print the source code URI
print("Source code URI: ", source_code)
```

## 3- Identify which evaluation metrics AutoML can use for regression problems.

    primary_metric - Primary metric to select the best model. Each trial will compute several metrics, but this one determines which model is selected from all the trials. One of r2 (default, R squared), mse (mean
    
    Databricks AutoML supports several evaluation metrics for regression problems. Some of the commonly used evaluation metrics for regression models in AutoML are:

    Mean Squared Error (MSE): MSE measures the average of the squared differences between the predicted values and the true values. It penalizes larger errors more heavily.

    Root Mean Squared Error (RMSE): RMSE is the square root of the MSE. It provides a more interpretable error metric in the same unit as the target variable.

    Mean Absolute Error (MAE): MAE computes the mean of the absolute differences between the predicted values and the true values. It provides a more robust measure of error that is not sensitive to outliers.

    R-squared (R2): R-squared is a statistical measure that represents the proportion of the variance in the target variable that can be explained by the model. It indicates the goodness of fit of the model, with 1 being a perfect fit and 0 indicating that the model does not explain any variance.

    Explained Variance Score (EV): EV measures the proportion of the variance in the target variable that is explained by the model. It provides a similar interpretation to R-squared.

    These evaluation metrics help assess the performance and accuracy of regression models generated by AutoML. Depending on the specific requirements and context of your regression problem, you can choose the most appropriate evaluation metric to evaluate and compare the performance of different models.


## 4- Identify the key attributes of the data set using the AutoML data exploration notebook.

    To identify the key attributes of the dataset using the AutoML data exploration notebook, you can follow these steps:

    1- Load the dataset: Make sure you have the dataset imported or loaded in your notebook. If not, use the appropriate method to load the dataset into a DataFrame.

    2- Run AutoML data exploration: Execute the AutoML data exploration function on the dataset. This function can automatically analyze the data and provide key insights about its attributes.

```python
from databricks import automl

exploration_summary = automl.run_data_exploration(data_df)
```
    3- Access the exploration summary: The exploration_summary object will contain the results of the data exploration analysis. You can access the summary to retrieve the key attributes of the dataset.
    
    key_attributes = exploration_summary.attributes

```python
for attribute in key_attributes:
    print(attribute)
```
    The key_attributes variable will contain a list of the important attributes identified by the AutoML data exploration. You can loop over this list and print each attribute to see the details such as attribute name, data type, number of distinct values, and other relevant information.

    Make sure to replace data_df with the name of your DataFrame containing the dataset. By following these steps, you can identify the key attributes of the dataset using the AutoML data exploration notebook.