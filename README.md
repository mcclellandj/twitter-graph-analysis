## Retweeting analysis

<table>
  <tr>
    <th>Bard Chatbot Launch 2023</th>
    <th>China Spy Balloon 2023</th>
    <th>Eurovision Song Contest 2023</th>
    <th>Nurses Strike 2023</th>
    <th>Six Nations Rugby Tournament 2023</th>
  </tr>
  <tr>
    <td><img src="images/bard.png" width="200"></td>
    <td><img src="images/ChinaSpyBalloon.png" width="200"></td>
    <td><img src="images/Eurovision.png" width="200"></td>
    <td><img src="images/NursesStrike.png" width="200"></td>
    <td><img src="images/SixNations.png" width="200"></td>
  </tr>
</table>

### Project objectives

Compare the graphs of 5 different Twitter hash tags in terms of:

- Ability to diffuse information
- Node and link structure
- Presence of nefarious bot/misinformation behaviour

The social networks analysed are Twitter retweet networks.

A hashtag relating to a significant current event was selected from each of the domains of: sports; music; international affairs; politics; and science. It is expected that the resulting social networks for these conversations will involve different types of users engaging in the conversations and hence have different structures. For instance, hashtags for sports and music may have larger networks due to being popular cultural domains with mass media exposure and users may include influential stars of sports and music. Hashtags for international affairs, politics and science are expected to have narrower audiences and involve niche interest groups and government agencies involved in the conversations and may be more likely to involve echo chambers with some users dominating conversations.

The analysis undertaken by this project follows the Social Media Analytics Process approach (Ganis & Kohirkar, 2015).
  
### Analysis approach

Using PySpark, PySpark SQL and Python where appropriate in a Jupyter Notebook to:
1. Create a Spark session on an available Cluster and upload the data onto Hadoop Distributed File System
2. Convert the data into a dataframe ahead of analysis and undertake a data audit and exploratory data analysis to gain insights on the main features
3. Clean and transform the data as required and build new features
4. Use Spark ML to create transformers and estimators to build predictive models
5. Create pipelines to find the best predictive model using different algorithms, different number of input features and hyperparameter tuning
6. Contemplate what extra steps could make the final model better

cf. code 'stem-jobs-salary-prediction.ipynb'

### Results/findings

- The best model was a Gradient Boosted Trees (GBT) regressor model which explained 64% of the variance and had a high RMSE
- To improve the model tried re-training the GBT regressor over various numbers of features (10, 20, 30,...) using feature importance rankings and tuning the hyperparameters of each using grid search and Spark ML CrossValidator. This increased the explained variance by 0.5 percentage points
- The top features in terms of feature importance were generally intuitive. For example 'years of experience', 'years at company', job titles involving 'software engineering', place of work being 'Google', tag of 'AI/ML', holding a 'PhD' are all significant drivers of higher remuneration. However, a counter intuitive finding was the work 'location' outside of California having a higher feature ranking than 'location' of California. The features of 'race' and 'gender' are quite low in the feature importance rankings.
