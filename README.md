# DSC212: Modularity on the Karate Club Graph

Name: Sobhan Terang
Roll Number: IMS25201

## Project Overview

This assignment divides the Zachary Karate Club graph into communities
using recursive spectral partitioning. It also studies the roles of
individual nodes using four network metrics.

The project uses: - **NumPy** for matrix calculations and eigenvectors -
**Pandas** for organizing result tables - **Matplotlib** for plots and
graph visualizations - **NetworkX** for the Karate Club graph, network
metrics, and modularity checks

## Dataset

The Karate Club graph contains 34 vertices (club members) and 78 edges
(friendships). The graph is treated as unweighted, as required by the
assignment. The historical club labels are used only to evaluate the
first split, not to construct the communities.

## Method

The community-detection procedure uses recursive spectral partitioning:

1.  Construct the modularity matrix from the graph's binary adjacency
    matrix.
2.  For each candidate community, form the corrected subgroup matrix.
3.  Use the leading eigenvector to propose a two-way split.
4.  Accept a split only when both groups are nonempty and the modularity
    gain is positive.
5.  Repeat the procedure recursively on the accepted groups.

The original graph remains unchanged during the splitting process.

## Node Metrics

The assignment examines four network measures:

-   Degree centrality
-   Betweenness centrality
-   Closeness centrality
-   Clustering coefficient

Metrics are considered both on the complete graph and on each node's
current induced community subgraph.

## Main Results

The recursive procedure accepts three splits and produces four
communities with sizes **7, 9, 12, and 6**.

The modularity increases as follows:

-   Initial partition: 0
-   After the first accepted split: 0.371466
-   After the second accepted split: 0.372699
-   After the third accepted split: 0.393409

The first split agrees with the historical club labels for 33 of the 34
nodes.

## Requirements

The notebook uses Python and the following packages:

-   `numpy`
-   `pandas`
-   `matplotlib`
-   `networkx`
-   `ipython`

The notebook's setup cell checks for missing packages and attempts to
install them.

## How to Run

1.  Open `DSC212_Karate_Modularity (2).ipynb` in Jupyter Notebook,
    JupyterLab, or Google Colab.
2.  Run the notebook cells in order, starting from the setup cell.
3.  Review the generated tables, plots, and community-detection results.
4.  The notebook saves figures and tables in a folder named `results/`.

## References

1.  Newman, M. E. J. (2006). "Modularity and community structure in
    networks." *Proceedings of the National Academy of Sciences*,
    103(23), 8577--8582. https://doi.org/10.1073/pnas.0601602103
2.  Zachary, W. W. (1977). "An Information Flow Model for Conflict and
    Fission in Small Groups." *Journal of Anthropological Research*, 33,
    452--473.
3.  NetworkX documentation: https://networkx.org/documentation/stable/
