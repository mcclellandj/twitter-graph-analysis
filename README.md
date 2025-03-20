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

- ability to diffuse information
- node and link structure
- use of bots

The hashtags selected are from different current events from 2023, namely: 

- technology (#bard)
- international affairs (#ChinaSpyBalloon)
- entertainment (#Eurovision2023)
- politics (#NursesStrike)
- sports (#SixNations2023)
  
### Analysis approach

#### Hash tag identification

By conducting keyword searches using the Python Twitter API and comparing the results with the hash tag used by the primary media outlet covering the event, the primary hashtag for each current event could be determined

#### Tweet extraction

Using the python Twitter API, 25,000 tweets per event were extracted including a mix of popular and recent tweets and stored in JSON format

#### Graph visualization

Using the python packages of pyvis and networkx the graphs were constructed. For visualization purposes higher order k-core shell visualizations have been created, whereby for any given k, all nodes with k-1 neighbours and its related edge are removed. The size of k was chosen manually for each hashtag after an iterative process

#### Calculation of metrics

Using the graphs created the following metrics were calculated for each graph

##### Network size

Comparing the size of each network enables understanding on much engagement each hashtag conversation has attracted. We can measure the size of each network by the numbers of its users (nodes) and relationships (directed links). Also networks may differ in the proportions of users who are retweeters or users who are retweeted. The metrics considered were:

- number of users (nodes)
- number of directed links (relationships)
- percentage of users who are retweeters
- percentage of users who are retweeted

##### Network connectivity

Understanding how well connected a network is informs us of how well information could be diffused across it. Some networks may be more dense meaning information can travel to more users while other networks may be more disjointed, comprising separate communities such as echo chambers. In the latter a visualization of a suitable k-core decomposition of the network can help to reveal the structure of its main components. The metrics considered were:

- density of network
- average clustering coefficient
- assortativity coefficient
- identification of network being strongly connected 
- number of strongly connected components
- number of nodes in largest strongly connected component
- identification of network being weakly connected 
- number of weakly connected components
- number of nodes in largest weakly connected component
- average shortest path length of largest weakly connected component

#### Node information diffusion

Users can retweet various numbers of other users. This information, along with the number of followers of each user has, enables comparisons of networks in terms of their proportion of influencial users and possible bots. Another comparison can be to compare centrality diffusion scores to see if some networks comprise more key users than others. The metrics considered were:

- percentile distribution of users by number of followers
- percentage of all users with at least 1,000 followers
- percentile distribution of users by number of retweets (in-degree strength)
- percentile distribution of users by number of tweets retweeted (out-degree strength)
- heterogeneity kappa parameters for both CCDF plots
- centrality - in-degree strength - top 10 users
- centrality - out-degree strength - top 10 users
- centrality - closeness - top 10 users
- centrality - betweenness - top 10 users
- centrality - page rank - top 10 users
- top 10 users by number of followers
- top 10 users retweeted by out-degree strength
- top 10 users retweeting by in-degree strength
- percentile distribution of users by virality score (for users with at least 1,000 followers)  

cf. code 'hashtag_graphs.ipynb'

### Results/findings


