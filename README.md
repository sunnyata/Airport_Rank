#Markov Chain Analysis of the US Airport Network

One way to view the airline transportation infrastructure is in the form of a directed network or graph, in which vertices are airports and edges are the direct-flight segments that connect them. For instance, if there is a direct flight from Atlanta's Hartsfield-Jackson International Airport ("ATL") to Los Angeles International Airport ("LAX"), then the airport network would have a directed edge from ATL to LAX.

Given the airport network, it may be useful to understand which airports are most critical to disruption of the overall network? That is, if an airport is shut down, thereby leading to all inbound and outbound flights being cancelled, will that catastrophic event have a big impact or a small impact on the overall network?

One would expect this importance to be related to an airport's total number of inbound or outgoing connections. In graph lingo, the number of such connections is called the degree of a vertex or node. The indegree is the number of incoming edges to a node, and the outdegree is the number of outgoing edges.

But if there are multiple routes between two airports, then even if one of the routes includes a high-degree airport in its path, a traveler that can work around a closure by going on an alternate route. So having a high-degree is not the only factor contributing to how important an airport is. Here, I will try to use a PageRank-like scheme to rank airports and compare that to looking at degree.

This was adapted from: 

https://www.mongodb.com/blog/post/pagerank-on-flights-dataset. The dataset is available here: https://www.transtats.bts.gov/Fields.asp?gnoyr_VQ=FIM

