Download Link: https://assignmentchef.com/product/solved-cs224w-homework-1-network-analysis-and-the-snap-software
<br>
The purpose of these exercises is to get you started with network analysis and the SNAP software. For this homework, you need to install and try out the SNAP network analysis tools. We strongly encourage you to use Snap.py for Python (available from <a href="http://snap.stanford.edu/snappy/">http://snap.stanford.edu/snappy/</a><a href="http://snap.stanford.edu/snappy/">)</a>. However, you can also use SNAP for C++ (available from <a href="http://snap.stanford.edu/snap/download.html">http://snap.stanford.edu/snap/ </a><a href="http://snap.stanford.edu/snap/download.html">download.html</a><a href="http://snap.stanford.edu/snap/download.html">)</a>

<h2>1          Analyzing the Wikipedia voters network</h2>

Download the Wikipedia voting network wiki-Vote.txt.gz: <a href="http://snap.stanford.edu/data/wiki-Vote.html">http://snap.stanford.edu/ </a><a href="http://snap.stanford.edu/data/wiki-Vote.html">data/wiki-Vote.html</a><a href="http://snap.stanford.edu/data/wiki-Vote.html">.</a>

Using one of the network analysis tools above, load the Wikipedia voting network. Note that Wikipedia is a directed network. Formally, we consider the Wikipedia network as a directed graph <em>G </em>= (<em>V,E</em>), with node set <em>V </em>and edge set <em>E </em>⊂ <em>V </em>× <em>V </em>where (edges are ordered pairs of nodes). An edge (<em>a,b</em>) ∈ <em>E </em>means that user <em>a </em>voted on user <em>b</em>.

To make our questions clearer, we will use the following small graph as a running example:

<em>G</em><sub>small </sub>= (<em>V</em><sub>small</sub><em>,E</em><sub>small</sub>), where <em>V</em><sub>small </sub>= {1<em>,</em>2<em>,</em>3} and <em>E</em><sub>small </sub>= {(1<em>,</em>2)<em>,</em>(2<em>,</em>1)<em>,</em>(1<em>,</em>3)<em>,</em>(1<em>,</em>1)}.

Compute and print out the following statistics for the wiki-Vote network:

<ol>

 <li><em>The number of nodes in the network. </em>(<em>G</em><sub>small </sub>has 3 nodes.)</li>

 <li><em>The number of nodes with a self-edge (self-loop), i.e., the number of nodes a </em>∈ <em>V where</em></li>

</ol>

(<em>a,a</em>) ∈ <em>E. </em>(<em>G</em><sub>small </sub>has 1 self-edge.)

CS224W: Analysis of Networks – Problem Set 0                                                                   2

<ol start="3">

 <li><em>The number of directed edges in the network, i.e., the number of ordered pairs </em>(<em>a,b</em>) ∈ <em>E for which a </em>6= (<em>G</em><sub>small </sub>has 3 directed edges.)</li>

 <li><em>The number of undirected edges in the network, i.e., the number of unique </em>unordered <em>pairs </em>(<em>a,b</em>)<em>, a </em>6= <em>b, for which </em>(<em>a,b</em>) ∈ <em>E or </em>(<em>b,a</em>) ∈ <em>E (or both). </em>If both (<em>a,b</em>) and (<em>b,a</em>) are edges, this counts a single undirected edge. (<em>G</em><sub>small </sub>has 2 undirected edges.)</li>

 <li><em>The number of reciprocated edges in the network, i.e., the number of unique unordered pairs of nodes </em>(<em>a,b</em>)<em>, a </em>6= <em>b, for which </em>(<em>a,b</em>) ∈ <em>E and </em>(<em>b,a</em>) ∈ (<em>G</em><sub>small </sub>has 1 reciprocated edge.)</li>

 <li><em>The number of nodes of zero out-degree. </em>(<em>G</em><sub>small </sub>has 1 node with zero out-degree.)</li>

 <li><em>The number of nodes of zero in-degree. </em>(<em>G</em><sub>small </sub>has 0 nodes with zero in-degree.)</li>

 <li><em>The number of nodes with more than 10 outgoing edges (out-degree &gt; </em>10<em>).</em></li>

 <li><em>The number of nodes with fewer than 10 incoming edges (in-degree &lt; </em>10<em>).</em></li>

</ol>

Each sub-question is worth 3 points.

<h2>2           Further Analyzing the Wikipedia voters network</h2>

For this problem, we use the Wikipedia voters network. If you are using Python, you might want to use NumPy, SciPy, and/or Matplotlib libraries.

<ol>

 <li>(18 points) Plot the distribution of out-degrees of nodes in the network on a log-log scale. Each data point is a pair (<em>x,y</em>) where <em>x </em>is a positive integer and <em>y </em>is the number of nodes in the network with out-degree equal to <em>x</em>. Restrict the range of <em>x </em>between the minimum and maximum out-degrees. You may filter out data points with a 0 entry. For the log-log scale, use base 10 for both <em>x </em>and <em>y </em></li>

 <li>(15 points) Compute and plot the least-square regression line for the out-degree distribution in the log-log scale plot. Note we want to find coefficients <em>a </em>and <em>b </em>such that the function log<sub>10 </sub><em>y </em>= <em>a </em> log<sub>10 </sub><em>x </em>+ <em>b</em>, equivalently, <em>y </em>= 10<em><sup>b </sup></em>· <em>x<sup>a</sup></em>, best fits the out-degree distribution. What are the coefficients <em>a </em>and <em>b</em>? For this part, you might want to use the method called polyfit in NumPy with deg parameter equal to 1.</li>

</ol>

<h2>3     Finding Experts on the Java Programming Language on StackOverflow</h2>

Download the StackOverflow network stackoverflow-Java.txt.gz: <a href="http://snap.stanford.edu/class/cs224w-data/hw0/stackoverflow-Java.txt.gz">http://snap.stanford</a>. <a href="http://snap.stanford.edu/class/cs224w-data/hw0/stackoverflow-Java.txt.gz">edu/class/cs224w-data/hw0/stackoverflow-Java.txt.gz</a><a href="http://snap.stanford.edu/class/cs224w-data/hw0/stackoverflow-Java.txt.gz">.</a> An edge (<em>a,b</em>) in the network means that person <em>a </em>endorsed an answer from person <em>b </em>on a Java-related question.

Using one of the network analysis tools above, load the StackOverflow network. Note that StackOverflow is a directed network.

Compute and print out the following statistics for the stackoverflow-Java network:

<ol>

 <li><em>The number of weakly connected components in the network. </em>This value can be calculated in Snap.py via function GetWccs.</li>

</ol>

3

<ol start="2">

 <li><em>The number of edges and the number of nodes in the largest weakly connected component. </em>The largest weakly connected component is calculated in Snap.py with function GetMxWcc.</li>

 <li><em>IDs of the top 3 most central nodes in the network by PagePank scores. </em>PageRank scores are calculated in Snap.py with function GetPageRank.</li>

 <li><em>IDs of the top 3 hubs and top 3 authorities in the network by HITS scores. </em>HITS scores are calculated in Snap.py with function GetHits.</li>

</ol>

Each sub-question is worth 10 points.

You can find more details about this exercise on the Snap.py tutorial page: <a href="http://snap.stanford.edu/proj/snap-icwsm/">http://snap.stanford. </a><a href="http://snap.stanford.edu/proj/snap-icwsm/">edu/proj/snap-icwsm/</a><a href="http://snap.stanford.edu/proj/snap-icwsm/">.</a> As an extra exercise, extend the tutorial to find experts in other programming languages or topics.