
# A study on formation of echo chambers on social media based on political ideologies

Political ideologies of individuals are often a major driving force in discussions and discourse
on social media. This might even hold for conversations outside of the realm of politics itself
and might lead to creation of echo chambers of discussion online. In this project, I want to
understand if people (agents) tend to prefer being part of networks of people with similar
ideologies as theirs, whilst segregating themselves from other groups. In other words, does the
desire to follow and be surrounded by people of similar ideologies lead to disparate networks,
and more so how do these structures look like internally?

## Introduction
The advent of internet and social media has given rise to avenues for conversation and
discourse online about issues of all kinds. Moreover, the heightened dissemination and access
that social media platforms offer make them ideal for discussions on matters that concern large
populations. Unlike the real world, this widespread access also allows for creation of networks,
and consequentially interactions with a large number of people of diverse backgrounds, beliefs,
and ideologies. It is not uncommon to see these differences create friction and pave their way
to heated arguments online. While there could be several other factors, in this project I
specifically look at how political ideology can be instrumental in shaping conversations online.
I choose to distinguish people based on political ideology since political beliefs and opinions
often translate into other avenues of life and can be strong aggregated indicators of
individualistic traits. Moreover, they are more amplified and visible in online forums. As
people move towards extremes of the liberal and conservative spectrum, conversations online
can mirror the disparities in ideologies and lead to disagreements. It is also a common
phenomenon to see these disparities to eventually lead to creation of subnetworks or echo
chambers within the larger network where people interact with a subset of the population that
validates and agrees with their ideas and opinions. Subreddits on Reddit, and groups on
Facebook are examples of this.

The growing relevance of discourse along political ideologies has led several researchers to
undertake meaningful work in this area. A recent study that conducted comparative analysis
across platforms regarding information spreading and formation of echo chambers found that
homophilic clusters of users is a major component in social media dynamics (Cinelli et al.,
2021). Another research project that uses a network-based approach, finds that confirmation
bias amongst users leads to informational cascades within identifiable communities online,
which is further reiterated by reinforcement seeking of information (Brugnoli et al., 2019). A
study conducted in 2018, leverages a model of Bayesian agents to show that the structure of a
network itself contributes to the formation of echo chambers. In fact, larger networks increase
the chances of this formation (Madsen et al., 2018). Interestingly, a recent study published in
the journal of artificial societies suggests that a user’s ability to rapidly share information with
other users is itself enough to form echo chambers (Fränken & Pilditch, 2021).
The domain of understanding echo chambers and segregation caused by political ideologies
online is a fairly recent field of research. Even though a few studies have adopted agent models
and network analysis methods to study this, I believe there still lies a potential to use simple
models with greater explanatory power as opposed to complex methods. This project aims to
use a simple agent-based model (ABM) — the Schelling model (Schelling, 1971) — that
confirms the underlying principle of all the results presented thus far. It uses the concept of
homophily to establish segregation between people of different political ideologies. Moreover,
this study is a steppingstone towards understanding not just the formation of echo chambers,
but also how networks can be combined with ABMs to see how echo chambers that resonate
with the same sentiment might themselves be disconnected on social media. The foundational
model used in the study to answer these questions is extremely rudimentary yet significant to
the field of agent-based modelling, and hence makes it easy to change parameters and adapt
this to other, perhaps more nuanced problems of social science.

## Simulation
In this project, I attempt to understand creation of echo chambers of users on social media
based on political ideology. To do this, I build an agent-based model, which aims to simulate
how people react as they interact with people of different ideologies online, and accordingly
form subgroups with like minded people. I use the Schelling model to study my question, and
I do so by using the following process.

1. Akin to the Schelling model, I create a model with two types of agents — liberals and
conservatives. I keep their proportions equal i.e. .5 since I wanted to see how echo
chambers are formed when the size of the disparate groups itself is not different.
However, for future work, these numbers can be experimented with to see how results
change.

2. Since I want to study how subgroups emerge between people of the same type, I also
create an attribute happy in the agent class. The purpose of this attribute is to ensure
that every agent that becomes a part of the network is happy with the existing agents in
their neighbourhood at the time, and so are the other agents in the neighbourhood.
Essentially, not only must every agent be of the same type to be a part of the network,
but each of them should also be happy based on their homophily in the current
neighbourhood. In a real-world situation, one of the major reasons why certain
polarized groups have intense discussions is because most participants of the group feel
strongly about the issue at hand with the same intensity. Of course, it might be more
realistic to consider a certain majority of agents in the existing neighbourhood to be
happy, instead of all of them, and this is an aspect that can be explored in future works.

3. Using the condition mentioned in the above point, along with the condition for
homophily in a Schelling model, I create two separate networkx graph objects of
liberals and conservatives and create a connection between an agent and his/her
neighbours of a certain type if all of them are happy.

4. Lastly, I experiment with the levels of homophily to check how segregation occurs at
various levels and create certain visuals to better understand the process.
The Schelling model provides a foundational and simple way of understanding segregation. Its
abstract nature allows for adapting it to settings of various kinds. Moreover, I believe an agentbased
model of such kind is apt for studying online phenomena such as formation of echo
chambers since the random movements of agents mirror entropy of social media platforms and
the ability of users to move and interact with individuals randomly. Yet, no specific conditions
have been induced to make the setting particular to social media i.e. one could argue that this
might very well hold for offline social interactions too. However, those often do not tend to
mimic encounters on a large scale such as the one in this model. Hence, owing to random
movements of agents over several simulations, the implicit nature of the model itself makes it
better suitable for studying interactions on social media.

## Discussion
## Findings
1. As expected, because I create two separate graph objects using the networkx library, I
get two separate networks of liberal and conservative agents. However, across
simulations, there seem to appear disconnected subnetworks within the network.
For instance, this graph representing the group of liberals, has two visibly separate sub
networks. This could be caused because of the nature of the movements of agents
themselves. There is a chance that as agents move across the space, they do not end up
being part of neighborhoods where every other agent of their type is happy, and as a
result there are certain disconnected groups formed. This I believe is synonymous with
what happens in the real world where different echo chambers that inherently speak of
the same issue, might actually have disjoint sets of users that are a part of them. This
result not only explains the formation of disjoint networks of users of different
ideologies, but also their internal network structure to some extent, even if it might be
simplified.
Moreover, these graph objects are formed at the end of the entire simulation, and thus,
the sum total of the nodes in the two individual objects (liberal and conservative) is the
same as that of the total number of happy agents at the end of the simulation.

2. I also create a dynamic visual similar to that in the Schelling model to observe the
formation of these echo chambers with time, and this is the final state of the agents at
the end of the simulation.
The minority and majority are liberals and conservatives respectively, and are equally
spread out, and rightly so because their proportions are equal. However, as one would
expect in a Schelling model, there are visible segregated neighborhoods, or in this case,
online echo chambers that seem to emerge. Moreover, this visual and the empty spaces
in it also explain how two users can be parts of networks of the same type (agent type),
and still not be connected since they are parts of different sub networks. This reiterates
the message conveyed by the graph object in the previous figure.

3. Lastly, I vary the homophily to see how various levels of homophily lead to different
levels of segregated agents in echo chambers.
Akin to the Schelling Model, agents are segregated into echo chambers even at a
homophily level of 1. However, the percentage of agents in segregated neighborhoods
is significantly lesser for homophily 1 when both agent types are present in the same
proportions, as opposed to one of them being in a minority (such as the one we did in
class). In fact, this I believe also speaks for how social media works. Users want larger
numbers of people to agree with their views, and in the process end up forming larger
groups which echo their sentiments. This is represented in the figure as with increase
in homophily, the proportion of agents in segregated echo chambers also seems to
increase. As a matter of fact, a study in 2016 found that more extreme and conservative
users tend to be more homophilous than more liberal and moderate users on social
media networks (Boutyline & Willer, 2016). To delve further into broader questions of
this kind, it could be an interesting topic of study in the future to use ABMs of this kind
and tweak the number of conservatives or liberals in the network and see how they
individually react to different levels in homophily.

## Strengths
As mentioned earlier, the model is based on a model which was built in an abstract setting and
can be adapted to various questions of the social science. Hence, it allows for answering deeper
questions such as how agents even within conservative and liberal networks behave online. For
instance, one could study moderate and extreme conservative users as agent types in a separate
model building off this project. Moreover, as I previously explained, random movements of
agents simulate user behavior on social media, and hence are suitable for studying questions in
such contexts. Additionally, the use of graph objects, even though preliminary, sheds light on
the structure of how agent types are connected internally. This part of the study can be made
more elaborate in the future by removing certain users from the network as they become
unhappy and looking at how dynamically the number of nodes and degrees of freedom of the
network changes at every step.

## Limitations
1. One of the strengths of this model is also its limitations that I address before. One could
easily argue that this model could be descriptive of interactions offline, perhaps at a
setting like a conference where people do interact more randomly. However, I believe
the effects of such interactions might be more short term and actually not lead to
formation of echo chambers. That being said, the model can definitely have more
parameters to be more representative of an online setting.

2. Even though the model briefly explains internal structure of agent networks, the way
the simulation is set up, one would naturally expect two separate networks of similar
agent types to emerge. However, it is important to note that it is only the formation of
the graph object that is set up this way, and not the actual random interaction of agents
itself. Thus, problem could be dealt with to some extent by looking at interactions and
nodes at every step to take into account steps where agents of a certain type do not get
added to a network because either they are not happy, or their neighbors are not.

3. Lastly, this specific model assumes an equal representation of liberal and conservative
populations online which might not be the case. However, owing to the abstract nature
of Schelling’s model, this could easily be resolved by varying the levels of each agent
type to see how that affects the formation of echo chambers.

## Conclusion
It is needless to say that as rudimentary as this model is, it comes with obvious limitations.
Perhaps several more than those covered in this write up. However, this project is a step
towards critically thinking about how extremely simple ABMs can be used to describe and
study more complex and relevant questions of social science. Moreover, if combined with other
suitable computational methods such as network analysis, simple ABMs can have significant
explanatory power, and could be applied to interesting contexts in the future.

## References
Boutyline, A., & Willer, R. (2016). The Social Structure of Political Echo Chambers:
Variation in Ideological Homophily in Online Networks. Political Psychology, xx, No.
xx. https://doi.org/10.1111/pops.12337

Brugnoli, E., Cinelli, M., Quattrociocchi, W., & Scala, A. (2019). Recursive patterns in
online echo chambers. Scientific Reports 2019 9:1, 9(1), 1–18.
https://doi.org/10.1038/s41598-019-56191-7

Cinelli, M., de Francisci Morales, G., Galeazzi, A., Quattrociocchi, W., & Starnini, M.
(2021). The echo chamber effect on social media. Proceedings of the National Academy
of Sciences of the United States of America, 118(9).
https://doi.org/10.1073/PNAS.2023301118/-/DCSUPPLEMENTAL

Fränken, J. P., & Pilditch, T. D. (2021). Cascades Across Networks Are Sufficient for the
Formation of Echo Chambers: An Agent-Based Model. 2021:4:2, 24(3).
https://doi.org/10.18564/JASSS.4566

Madsen, J. K., Bailey, R. M., & Pilditch, T. D. (2018). Large networks of rational agents
form persistent echo chambers. Scientific Reports 2018 8:1, 8(1), 1–8.
https://doi.org/10.1038/s41598-018-25558-7

Schelling, T. C. (1971). Dynamic models of segregation. The Journal of Mathematical
Sociology, 1(2), 143–186. https://doi.org/10.1080/0022250X.1971.9989794
