# Greedy algorithm
## Chracteristics
- Make optimal choice at each iteration, not considering the future and the past interations
- Greedy solution not always make optimal solution

## Examples

### 1 (Machine Learning) Clustering from worksheet
#### 1.1 Brute force
##### 1.1.1 Making instances
```python
# Each Instance[i] represent which category that node belongs to.
instance26 = [1, 2, 1, 2, 1]
# Total instances = 2^nodes
```
##### 1.1.2 Checking each instances if it is optimal
```python
def costChecker(instance, similarityMatrix):
    cost = 0  # initially, set it to 0
    for i in range(len(instance)):
        for j in range(len(instance)):
            # Finding maximum similarity, which is the cost of clustering
            if (instance[i] != instance[j] and cost < similarityMatrix[i][j]):
                cost = similarityMatrix[i][j]
    return cost
```
#### 1.2 Greedy clustering
- Strategy
  - 1. put each edges into its own category
  - 2. pick edges that have highest similarity and combine the category
  - 3. do 1 and 2 until it reaches intended category numbers
```python
def greedyClustering(edges):
    # sort edges in decreasing order based on similarity
    edges = sorted(edges, key=lambda x: x[2], reverse=True)
    print(edges)

    # put each node in each categories
    # number represent which category node is belongs to.
    category = [0, 1, 2, 3]
    goalCategories = 2

    i = 0

    # len(Counter(edges).keys()) represents number of unique elements in the list
    while len(Counter(category).keys()) > goalCategories:
        # if node1 and node2 belong to different category
        if (category[edges[i][0]] != category[edges[i][1]]):
            category[edges[i][1]] = 0
            category[edges[i][0]] = 0
        i += 1
    return category
```

### 2. MST
definition: subset of edges from the graph that connect all vertices without cycle and with minimum total edge cost.
#### 1.1 Kruskal(Russian)'s algorithm
- Strategy
  - 1. sort the edges in ascending order of weight
  - 2. pick smallest weighted edge and check if it forms cycle
  - 3. If it doesn't form the cycle, include it in the MST
  - 4. iterate 2 and 3 until 
```pseudocode
def kruskal(graph, weight list):
    A = []
    for each vertex in graph:
        put it into single list like [[0],[1],[2],[3]]
    edges = list of edges
    sort edges in ascending order of weight

    for e of edges:
        if adding e does not create cycle:
            A.append(e)
    return A
```
#### 1.2 Prim(French)'s algorithm
- Strategy
  - 1. pick a random node in the beginning
  - 2. check edges that connects from visited nodes to not yet reached nodes
  - 3. pick the smallest weight edge among them
  - 4. iterate 2 and 4 until it includes all nodes in the graph
```python
def prim(graph: List[List[int]]) -> int:
    included = [0] * len(graph[0])
    totalCost = 0

    currentNode = 0
    while included.count(1) < len(thegraph[0]):
        minCost = 999
        for i in range(len(thegraph[0])):
            if graph[currentNode][i] < minCost and included[i] != 1:
                totalCost += graph[currentNode][i]
                included[i] = 1
                currentNode = i
    return totalCost
```
### 3. Knapsack problem
```python
weight1 = [(1/2, 3), (1/2, 1), (1/2, 7), (1/2, 4)]
weight2 = [(1/4, 1), (1/4, 6), (1/4, 7), (1/4, 5)]
weight3 = [(1/8, 9), (1/8, 4), (1/8, 3), (1/8, 7)]
weight4 = [(1/16, 4), (1/16, 4), (1/16, 8), (1/16, 2)]

# Sort weight4 based on value
weight4 = sorted(weight4, key=lambda x: x[1], reverse=True)
tuple1 = (1/8, weight4[0][1]+weight4[1][1])
tuple2 = (1/8, weight4[2][1]+weight4[3][1])
weight3.append(tuple1)
weight3.append(tuple2)

weight3 = sorted(weight3, key=lambda x: x[1], reverse=True)
tuple1 = (1/4, weight3[0][1]+weight3[1][1])
tuple2 = (1/4, weight3[2][1]+weight3[3][1])
tuple3 = (1/4, weight3[4][1]+weight3[5][1])
weight2.append(tuple1)
weight2.append(tuple2)
weight2.append(tuple3)

weight2 = sorted(weight2, key=lambda x: x[1], reverse=True)
tuple1 = (1/2, weight2[0][1]+weight2[1][1])
tuple2 = (1/2, weight2[2][1]+weight2[3][1])
tuple3 = (1/2, weight2[4][1]+weight2[5][1])

weight1.append(tuple1)
weight1.append(tuple2)
weight1.append(tuple3)

weight1 = sorted(weight1, key=lambda x: x[1], reverse=True)

greedyResult = weight1[0][1]+weight1[1][1]
```
### 4. Interval scheduling
```python

```

## Proof technique
### 1. Stays Ahead


### 2. An Exchange Argument
asg 22w1 4.1번
asg 22w2 5.1번

