<table>
  <tr>
    <td>
      Bard chatbot launch 2023
      <img src="images/bard.png" width="500"><br>
      China Spy Balloon 2023
      <img src="images/ChinaSpyBalloon.png" width="500"><br>
      Eurovison song contest 2023
      <img src="images/Eurovision.png" width="500"><br>
      Nurses strike of 2023
      <img src="images/NursesStrike.png"" width="500"><br>
      Six Nations Rugby tournament 2023
      <img src="images/SixNations.png" width="500">
    </td>
    <td style="vertical-align: top; padding-left: 20px; border: none;">
      <p>
        Predicting annual remuneration for STEM professionals
        
        Project objectives
        
        1. Build a model to predict a person's expected remuneration for any role in the STEM sector based on attribute profiles of the role and the person
        2. Use big data tools to build the model to enable efficient processing of data features comprising extreme cardinality
          
        Analysis approach
        
        Using PySpark, PySpark SQL and Python where appropriate in a Jupyter Notebook to:
        1. Create a Spark session on an available Cluster and upload the data onto Hadoop Distributed File System
        2. Convert the data into a dataframe ahead of analysis and undertake a data audit and exploratory data analysis to gain insights on the main features
        3. Clean and transform the data as required and build new features
        4. Use Spark ML to create transformers and estimators to build predictive models
        5. Create pipelines to find the best predictive model using different algorithms, different number of input features and hyperparameter tuning
        6. Contemplate what extra steps could make the final model better
        
        cf. code 'stem-jobs-salary-prediction.ipynb'
        
        Results/findings
        
        a. The best model was a Gradient Boosted Trees (GBT) regressor model which explained 64% of the variance and had a high RMSE
        b. To improve the model tried re-training the GBT regressor over various numbers of features (10, 20, 30,...) using feature importance rankings and tuning the hyperparameters of each using grid search and Spark ML CrossValidator. This increased the explained variance by 0.5 percentage points
        c. The top features in terms of feature importance were generally intuitive. For example 'years of experience', 'years at company', job titles involving 'software engineering', place of work being 'Google', tag of 'AI/ML', holding a 'PhD' are all significant drivers of higher remuneration. However, a counter intuitive finding was the work 'location' outside of California having a higher feature ranking than 'location' of California. The features of 'race' and 'gender' are quite low in the feature importance rankings.
     </p>
    </td>
  </tr>
</table>
