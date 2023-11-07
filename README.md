Markov chain analysis of the US airport network

One way to view the airline transportation infrastructure is in the form of a directed network or graph, in which vertices are airports and edges are the direct-flight segments that connect them. For instance, if there is a direct flight from Atlanta's Hartsfield-Jackson International Airport ("ATL") to Los Angeles International Airport ("LAX"), then the airport network would have a directed edge from ATL to LAX.

Given the airport network, one question we might ask is, which airports are most critical to disruption of the overall network? That is, if an airport is shut down, thereby leading to all inbound and outbound flights being cancelled, will that catastrophic event have a big impact or a small impact on the overall network?

You would expect "importance" to be related to whether an airport has lots of inbound or outgoing connections. In graph lingo, the number of such connections is called the degree of a vertex or node. The indegree is the number of incoming edges to a node, and the outdegree is the number of outgoing edges.

But if there are multiple routes between two airports, then even if one of the routes includes a high-degree airport in its path, a traveler that can work around a closure by going on an alternate route. So having a high-degree is not the only contributor to how important an airport is. Therefore, in this notebook, let's try to use a PageRank-like scheme to rank airports and compare that to looking at degree.

As it happens, the US Bureau of Transportation Statistics collects data on all flights originating or arriving in the United States. Let's use this data to build an airport network and then use Markov chain analysis to rank the networks by some measure of "criticality."

This was adapted from: https://www.mongodb.com/blog/post/pagerank-on-flights-dataset. The dataset is available here: https://www.transtats.bts.gov/Fields.asp?gnoyr_VQ=FIM

