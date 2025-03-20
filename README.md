<style>
  table {
    width: 100%;
    max-width: 100%;
    border-collapse: collapse;
    table-layout: fixed; /* Ensures equal spacing */
  }
  td {
    text-align: center;
    vertical-align: top;
    padding: 10px;
  }
  img {
    max-width: 100%;
    height: auto;
  }
  .full-width {
    text-align: left;
    vertical-align: top;
    padding: 20px;
    word-wrap: break-word;
  }
</style>

<table>
  <tr>
    <td><strong>Bard Chatbot Launch 2023</strong><br><img src="images/bard.png" width="150"></td>
    <td><strong>China Spy Balloon 2023</strong><br><img src="images/ChinaSpyBalloon.png" width="150"></td>
    <td><strong>Eurovision Song Contest 2023</strong><br><img src="images/Eurovision.png" width="150"></td>
    <td><strong>Nurses Strike of 2023</strong><br><img src="images/NursesStrike.png" width="150"></td>
    <td><strong>Six Nations Rugby Tournament 2023</strong><br><img src="images/SixNations.png" width="150"></td>
  </tr>
  <tr>
    <td colspan="5" class="full-width">
      <h2>Predicting Annual Remuneration for STEM Professionals</h2>

      <h3>Project Objectives</h3>
      <ol>
        <li>Build a model to predict a person's expected remuneration based on role attributes.</li>
        <li>Use big data tools to efficiently process high-cardinality data.</li>
      </ol>

      <h3>Analysis Approach</h3>
      <p>Using PySpark, PySpark SQL, and Python in a Jupyter Notebook:</p>
      <ol>
        <li>Upload data onto Hadoop Distributed File System.</li>
        <li>Convert data into a dataframe and conduct exploratory analysis.</li>
        <li>Clean and transform data, creating new features.</li>
        <li>Use Spark ML to build predictive models.</li>
        <li>Optimize models using different algorithms and hyperparameter tuning.</li>
      </ol>

      <h3>Results/Findings</h3>
      <ul>
        <li><strong>Best model:</strong> Gradient Boosted Trees (GBT) regressor (64% variance explained).</li>
        <li>Feature importance highlighted:
          <ul>
            <li>'Years of experience', 'years at company', 'PhD' were significant.</li>
            <li>Working at 'Google' and AI/ML-related roles led to higher salaries.</li>
            <li>Unexpectedly, non-California locations ranked higher than California.</li>
            <li>'Race' and 'gender' had low feature importance rankings.</li>
          </ul>
        </li>
      </ul>

      <p>cf. code <code>stem-jobs-salary-prediction.ipynb</code></p>
    </td>
  </tr>
</table>
