## Twitter graph analysis

<table>
  <tr>
    <td>
      <figure>
        <img src="images/bard.png" width="200" alt="Bard Chatbot Launch">
      </figure>
    </td>
    <td>
      <figure>
        <img src="images/ChinaSpyBalloon.png" width="200" alt="China Spy Balloon">
      </figure>
    </td>
    <td>
      <figure>
        <img src="images/Eurovision.png" width="200" alt="Eurovision Song Contest">
      </figure>
    </td>
    <td>
      <figure>
        <img src="images/NursesStrike.png" width="200" alt="Nurses Strike">
      </figure>
    </td>
    <td>
      <figure>
        <img src="images/SixNations.png" width="200" alt="Six Nations Rugby">
      </figure>
    </td>
  </tr>
    <tr>
    <th>Bard Chatbot Launch</th>
    <th>China Spy Balloon</th>
    <th>Eurovision Contest</th>
    <th>Nurses Strike</th>
    <th>Six Nations Rugby</th>
  </tr>
</table>

### Project objectives

Compare the ability of different Twitter graphs to transmit information. Namely, 

- Ability to diffuse information
- Node and link structure
- Use of bots

The hashtags selected are from different current affairs, namely: 

- technology (#bard)
- international affairs (#ChinaSpyBalloon)
- entertainment (#Eurovision2023)
- politics (#NursesStrike)
- sports (#SixNations2023)
  
### Analysis approach

Using the python package pyvis construct the graphs and calculate the following metrics:

#### Network size

- Number of users (nodes)
- Number of directed links (relationships)
- Percentage of users who are retweeters
- Percentage of users who are retweeted

#### Network connectivity

- Density of network
- Average clustering coefficient
- Assortativity coefficient
- Identification of network being strongly connected 
- Number of strongly connected components
- Number of nodes in largest strongly connected component
- Identification of network being weakly connected 
- Number of weakly connected components
- Number of nodes in largest weakly connected component
- Average shortest path length of largest weakly connected component

#### Node information diffusion

- Percentile distribution of users by number of followers
- Percentage of all users with at least 1,000 followers
- Percentile distribution of users by number of retweets (in-degree strength)
- Percentile distribution of users by number of tweets retweeted (out-degree strength)
- Heterogeneity kappa parameters for both CCDF plots
- Centrality - in-degree strength - top 10 users
- Centrality - out-degree strength - top 10 users
- Centrality - closeness - top 10 users
- Centrality - betweenness - top 10 users
- Centrality - page rank - top 10 users
- Top 10 users by number of followers
- Top 10 users retweeted by out-degree strength
- Top 10 users retweeting by in-degree strength
- Percentile distribution of users by virality score (for users with at least 1,000 followers)  

cf. code 'hashtag_graphs.ipynb'

### Results/findings

