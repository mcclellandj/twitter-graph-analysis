<table>
  <tr>
    <td><strong>Bard chatbot launch 2023</strong><br><img src="images/bard.png" width="200"></td>
    <td><strong>China Spy Balloon 2023</strong><br><img src="images/ChinaSpyBalloon.png" width="200"></td>
    <td><strong>Eurovision Song Contest 2023</strong><br><img src="images/Eurovision.png" width="200"></td>
    <td><strong>Nurses Strike of 2023</strong><br><img src="images/NursesStrike.png" width="200"></td>
    <td><strong>Six Nations Rugby Tournament 2023</strong><br><img src="images/SixNations.png" width="200"></td>
  </tr>
  <tr>
    <td colspan="5" style="padding: 20px; text-align: left; vertical-align: top;">
      <h2>Predicting Annual Remuneration for STEM Professionals</h2>

      <h3>Project Objectives</h3>
      <ol>
        <li>Build a model to predict a person's expected remuneration for any role in the STEM sector based on attribute profiles of the role and the person.</li>
        <li>Use big data tools to build the model to enable efficient processing of data features comprising extreme cardinality.</li>
      </ol>

      <h3>Analysis Approach</h3>
      <p>Using PySpark, PySpark SQL, and Python where appropriate in a Jupyter Notebook:</p>
      <ol>
        <li>Create a Spark session on an available cluster and upload the data onto Hadoop Distributed File System.</li>
        <li>Convert the data into a dataframe ahead of analysis and undertake a data audit and exploratory data analysis to gain insights on the main features.</li>
        <li>Clean and transform the data as required and build new features.</li>
        <li>Use Spark ML to create transformers and estimators to build predictive models.</li>
        <li>Create pipelines to find the best predictive model using different algorithms, different numbers of input features, and hyperparameter tuning.</li>
        <li>Contemplate what extra steps could make the final model better.</li>
      </ol>

      <h3>Results/Findings</h3>
      <ul>
        <li><strong>The best model</strong> was a Gradient Boosted Trees (GBT) regressor model, which explained 64% of the variance but had a high RMSE.</li>
        <li>To improve the model, we re-trained the GBT regressor over various numbers of features (10, 20, 30, etc.) using feature importance rankings and tuning hyperparameters via grid search and Spark ML CrossValidator. This increased the explained variance by 0.5 percentage points.</li>
        <li>Top features in terms of feature importance were generally intuitive:
          <ul>
            <li>'Years of experience', 'years at company', and job titles involving 'software engineering' were strong predictors.</li>
            <li>Working at 'Google', having an 'AI/ML' tag, and holding a 'PhD' correlated with higher remuneration.</li>
            <li>Unexpectedly, 'location' outside of California had a higher feature ranking than 'location' in California.</li>
            <li>'Race' and 'gender' had low importance rankings.</li>
          </ul>
        </li>
      </ul>

      <p>cf. code <code>stem-jobs-salary-prediction.ipynb</code></p>
    </td>
  </tr>
</table>
