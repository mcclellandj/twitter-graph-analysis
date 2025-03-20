## Retweet analysis

<table>
  <tr>
    <!-- Left Cell: Images -->
    <td style="width: 420px; vertical-align: top;">
      <strong>Bard chatbot launch 2023</strong><br>
      <img src="images/bard.png" width="400"><br><br>

      <strong>China Spy Balloon 2023</strong><br>
      <img src="images/ChinaSpyBalloon.png" width="400"><br><br>

      <strong>Eurovision Song Contest 2023</strong><br>
      <img src="images/Eurovision.png" width="400"><br><br>

      <strong>Nurses Strike of 2023</strong><br>
      <img src="images/NursesStrike.png" width="400"><br><br>

      <strong>Six Nations Rugby Tournament 2023</strong><br>
      <img src="images/SixNations.png" width="400">
    </td>

    <!-- Right Cell: Text -->
    <td style="width: 600px; vertical-align: top; padding-left: 20px;">
      <p><strong>Predicting annual remuneration for STEM professionals</strong></p>

      <p><strong>Project objectives:</strong></p>
      <ol>
        <li>Build a model to predict a person's expected remuneration for any role in the STEM sector based on role and person attributes.</li>
        <li>Use big data tools to enable efficient processing of high-cardinality data features.</li>
      </ol>

      <p><strong>Analysis approach:</strong></p>
      <p>Using PySpark, PySpark SQL, and Python in a Jupyter Notebook to:</p>
      <ol>
        <li>Create a Spark session on a cluster and upload data to HDFS.</li>
        <li>Convert data into a dataframe, conduct audits, and perform exploratory data analysis.</li>
        <li>Clean, transform data, and build new features.</li>
        <li>Use Spark ML to create transformers and estimators for predictive models.</li>
        <li>Develop pipelines to test different algorithms, feature selections, and hyperparameter tuning.</li>
        <li>Identify additional steps to further improve the final model.</li>
      </ol>

      <p><strong>cf. Code:</strong> <em>'stem-jobs-salary-prediction.ipynb'</em></p>

      <p><strong>Results/Findings:</strong></p>
      <ul>
        <li>The best model, a Gradient Boosted Trees (GBT) regressor, explained 64% of variance but had a high RMSE.</li>
        <li>Improvement efforts included re-training over various feature sets and hyperparameter tuning, increasing explained variance by 0.5%.</li>
        <li>Key features included 'years of experience', 'years at company', 'software engineering' roles, 'Google' employment, 'AI/ML' tags, and a 'PhD'.</li>
        <li>Unexpectedly, locations outside of California ranked higher in importance than those in California.</li>
        <li>'Race' and 'gender' had low feature importance rankings.</li>
      </ul>
    </td>
  </tr>
</table>

