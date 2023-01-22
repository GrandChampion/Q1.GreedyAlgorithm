# Greedy algorithm
## Chracteristics
- Make optimal choice at each iteration, not considering the future and the past interations
- Greedy solution not always make optimal solution

## Examples

### 1 (Machine Learning) Clustering from worksheet
#### 1.1 Bruteforce
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

