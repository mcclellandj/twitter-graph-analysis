## Twitter graph analysis

<table>
  <tr>
    <td>
      <figure>
        <img src="images/bard.png" width="200" alt="Bard launch">
      </figure>
    </td>
    <td>
      <figure>
        <img src="images/ChinaSpyBalloon.png" width="200" alt="China spy balloon">
      </figure>
    </td>
    <td>
      <figure>
        <img src="images/Eurovision.png" width="200" alt="Eurovision Song Contest">
      </figure>
    </td>
    <td>
      <figure>
        <img src="images/NursesStrike.png" width="200" alt="Nurses strike">
      </figure>
    </td>
    <td>
      <figure>
        <img src="images/SixNations.png" width="200" alt="Six Nations Rugby">
      </figure>
    </td>
  </tr>
    <tr>
    <th>Bard launch</th>
    <th>China spy balloon</th>
    <th>Eurovision Contest</th>
    <th>Nurses strike</th>
    <th>Six Nations Rugby</th>
  </tr>
</table>

### Project objectives

Compare the ability of different Twitter graphs to transmit information, namely; 

1. Ability to diffuse information
2. Node and link structure
3. Use of bots

The hashtags selected are from different current events from 2023, namely: 

- technology (#bard)
- international affairs (#ChinaSpyBalloon)
- entertainment (#Eurovision2023)
- politics (#NursesStrike)
- sports (#SixNations2023)
  
### Analysis approach

cf. code 'hashtag_graphs.ipynb'

#### 1. Hash tag identification

By conducting keyword searches using the Python Twitter API and comparing the results with the hash tag used by the primary media outlet covering the event, the primary hashtag for each current event could be determined

#### 2. Tweet extraction

Using the python Twitter API, 25,000 tweets per event were extracted including a mix of popular and recent tweets and stored in JSON format

#### 3. Graph visualization

Using the python packages of pyvis and networkx the graphs were constructed. For visualization purposes higher order k-core shell visualizations have been created, whereby for any given k, all nodes with k-1 neighbours and its related edge are removed. The size of k was chosen manually for each hashtag after an iterative process

#### 4. Calculation of metrics

The following metrics were calculated for each graph

##### a. Network size

Comparing the size of each network enables understanding on much engagement each hashtag conversation has attracted. We can measure the size of each network by the numbers of its users (nodes) and relationships (directed links). Also networks may differ in the proportions of users who are retweeters or users who are retweeted. The metrics considered were:

- number of users (nodes)
- number of directed links (relationships)
- percentage of users who are retweeters
- percentage of users who are retweeted

##### b. Network connectivity

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

##### c. Node information diffusion

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

### Results/findings

#### 1. Network size

- There is a significant difference in the size of the networks with the #NursesStrike and #ChinaSpyBalloon conversations having by far the largest number of users - 3.5K users for both compared to 2.4K for both #EuroVision2023 and #bard and 1.8K users for #SixNations2023. This intuitively makes sense given the potential sizes of audience - a pause on NHS services affects most of the UK population while the Six Nations Rugby tournament is a niche sport

- There is an inverse relationship between the numbers of retweeted and retweeter users in each network. Those with the highest proportion of retweeters have the lowest proportion of retweeted users suggesting that in these networks (proportionally) fewer users are generating the retweeted content. In the #NursesStrike conversation 95% of users are retweeters while only 6% of users had their content retweeted whereas for the #bard conversation only 78% of users are retweeters but 25% were retweeted

#### 2. Network connectivity

The k-core decomposition graphs show very different structures when stripped of their periphery shells and these are also reflected in the network metrics for their full compositions. Note that these decompositions strip away a significant proportion of user nodes and links. They are all neither strongly or weakly connected networks. The largest strongly connected component in each comprises between only 1 and 4 users. In terms of weakly connected components, the #NursesStrike and #Eurovision2023 networks comprise the fewest number of weakly connected components and their largest weakly connected component comprise 95% and 82% of all their users respectively meaning the majority of these two networks would be fully connected if the graphs were undirected. In comparison the other three networks are made up of significantly more weakly connected components with their largest comprising between only 30% and 59% of all users

- All the networks are sparse with densities (proportion of all possible links) and average clustering coefficents (how well followers of users are connected to each other) being very low. Interestingly the #SixNations2023 and #bard networks have the highest clustering coefficients which is reflected by them both having the highest average shortest path length.

- There is evidence of ego sub-networks and echo chambers in each network, particularly for #SixNations2023 and #bard where the k-core decomposition graphs show standalone components acting as such with significant numbers of users retweeting the content of very few users while excluding all other users. This is possibly a reflection of all the networks being disassortative (with their degree assortativity coefficients being less than 0) meaning that high degree users are connecting to low degree users and conversely low degree users are connecting to high degree users

#### 3. Node information diffusion

- Users in the #SixNations2023, #ChinaSpyBalloon and #NursesStrike all have significantly higher number of followers with an average of 572, 547 and 515 respectively compared to users in the #Eurovision and #bard conversations with only 375 and 267 respectively

- Looking at the in-degree and out-degree strength percentile distributions, on average users retweet just once and do not get retweeted at all. This is reflected in the distribution functions for each. Only around 5 percent of users retweet or are retweeted more than once for each network. There is heterogeneity in users by number of retweets (in-degree strength), particularly for the #bard conversation which has the heaviest tail (greatest spread in in-degree) while the #ChinaSpyBalloon conversation has the lightest tail (least spread in in-degree). This is reflected by the heterogeneity kappa parameters. In regards to heterogeneity in users by number of tweets retweeted (out-degree strength), #Eurovision has the heaviest tail with heterogeneity kappa parameter of 811 versus #SixNations2023 having the lightest tail and a kappa paremter of 74. These tails also reflect the number of times the top retweeters of each network retweet (up to 101 times for #bard vs. only 9 times for #ChinaSpyBalloon) and similarly the number of times the top retweeted users are retweeted (e.g. 1,696 for #Eurovision vs. 293 for #SixNations2023). The volume of high frequency retweeter users and retweeted users falls away quickly for each network

- In terms of value to diffusion, while the top 10 retweeters (in-degree strength) tend to be private account users the top 10 retweeted users (out-degree strength) tend to be official or associated representatives of the events (e.g. RugbyPass for SixNations2023 and NHSActivistRN for #NursesStrike) or known celebrities (e.g. Scott Mills) which have by far the largest number of followers (~8M to 18M across the networks). This tends to hold across all of the centrality metrics. The #NursesStrike conversation has the top scores for closeness (how close users are to every other user - in terms of path distance - in the network) but #bard has significantly highest scores for page rank (how each node can be arrived at in terms of information flow)

- There are signs of bots in the top 10 lists. It has been summised that usernames followed by 8 digits tend to be bots (Maxwell, 2022) and in this analysis there exists a couple of these in the top 10 for #ChinaSpyBalloon, #Eurovision2023 and #bard conversations across various centrality metrics implying they are acting as important diffusers of either valid information or misinformation. For example, user 'Tsering78393648' is the top retweeter for #ChinaSpyBalloon and 'Directi95865257' is the 5th top retweeter for #Eurovision. Looking at the usernames of retweeted users and retweeter users for the #bard conversation it is quite possible that they are valid information bots which are automatically scheduled by various companies, e.g. 'GoogleAI3', 'SlothGPT' or 'uCloudifyAI'

- In each network there are users that are in both the top 10 users for retweeters and number of followers and can be considered as influencers e.g. 'ScottMills' for #Eurovision2023 or 'DoctorChrisVT' in #NursesStrike. There is some variation in the virality score percentile distributions of each network (for users with at least 1,000 followers) with #SixNations2023 and #ChinaSpyBalloon having by far the highest scores for top 1% of users. Here virality of a user is calculated as the number of times they have been retweeted divided by the number of their followers, it shows us the penetration of their tweets in their following and is not biased towards users with large or small audiences (followers)

### Summary of findings

1. The observations above in terms of density and not being strongly/weakly connected are to be expected for retweet networks which are defined only by one-way relationships (transmission of tweets from retweeted to retweeter) instead of two-way relationships which occur in social media applications like Facebook. All of the networks differ in size and structure, most notably the number of weakly connected components they have, the heterogeneity in the distribution of their in-degree strength and in terms of centrality scores for the top 10 nodes showing that some networks rely more on some nodes for diffusion of information than others. There is clear evidence of influencers in each network in terms of their high out-degree strength (being retweeted) and their large number of followers as well as some high viral users. There is also indications of bots in action particularly for #ChinaSpyBalloon

2. If this analysis was to be repeated, future approaches could include:
   
   - Taking larger data extracts to help ensure data is not biased
   - Consider only tweets from verified (blue tick) users to remove nefarious bots or instead checking metadata of each user for clears signs of fake accounts such as absence of photo, links, or any bio information, etc


