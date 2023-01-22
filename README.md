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
```python

```
#### 1.2 Prim(French)'s algorithm
```python

```

### 3. Interval scheduling
```python

```

### 4. Knapsack problem
```python

```

## Proof technique
### 1. Stays Ahead


### 2. An Exchange Argument
asg 22w1 4.1번
asg 22w2 5.1번

