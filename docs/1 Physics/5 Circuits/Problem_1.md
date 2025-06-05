# Problem 1

# Algorithm for Calculating Equivalent Resistance Using Graph Theory

The algorithm to calculate the equivalent resistance in a circuit using graph theory involves representing the circuit as a graph, where nodes correspond to the junctions of the circuit, and edges represent resistors with weights equal to their resistance values. The goal is to iteratively simplify the graph by identifying series and parallel connections and reducing the graph until only one equivalent resistance remains.

## Key Concepts:
1. **Series Connection:** Resistors in series can be replaced by a single resistor with a resistance equal to the sum of the individual resistances:  
   $$
   R_{\text{eq}} = R_1 + R_2 + \cdots + R_n
   $$
   
2. **Parallel Connection:** Resistors in parallel can be replaced by a single resistor with resistance given by:  
   $$
   \frac{1}{R_{\text{eq}}} = \frac{1}{R_1} + \frac{1}{R_2} + \cdots + \frac{1}{R_n}
   $$

## Steps:
1. **Initial Graph Representation:**
   - The circuit is represented as a graph \( G = (V, E) \), where:
     - \( V \) is the set of vertices (representing junctions),
     - \( E \) is the set of edges (representing resistors between junctions).
     - Each edge \( e = (u, v) \) has a resistance \( R_e \) as its weight.
  
2. **Identifying Series and Parallel Connections:**
   - **Series Connection:** If two resistors are connected end-to-end (i.e., they share a node and are not in parallel), the resistances are in series.
   - **Parallel Connection:** If two resistors are connected between the same two nodes, the resistances are in parallel.

3. **Graph Reduction:**
   - **Series Combination:** For resistors in series, reduce the graph by replacing the series resistors with a single equivalent resistor, updating the graph.
   - **Parallel Combination:** For resistors in parallel, reduce the graph by replacing the parallel resistors with a single equivalent resistor, updating the graph.

4. **Repeat:** Continue identifying series and parallel combinations and reducing the graph until only one edge (the equivalent resistance) remains.

## Pseudocode

```python
def find_series_resistors(graph):
    """Identify and return all series resistor pairs in the graph."""
    series_pairs = []
    for node in graph:
        neighbors = graph[node]
        for neighbor in neighbors:
            if is_series_connection(node, neighbor):
                series_pairs.append((node, neighbor))
    return series_pairs

def find_parallel_resistors(graph):
    """Identify and return all parallel resistor pairs in the graph."""
    parallel_pairs = []
    for node in graph:
        neighbors = graph[node]
        for neighbor in neighbors:
            if is_parallel_connection(node, neighbor):
                parallel_pairs.append((node, neighbor))
    return parallel_pairs

def is_series_connection(node1, node2):
    """Check if two nodes are connected in series."""
    # Logic to check if two resistors are in series (e.g., same current path)
    pass

def is_parallel_connection(node1, node2):
    """Check if two nodes are connected in parallel."""
    # Logic to check if two resistors are in parallel (same voltage across them)
    pass

def combine_series_resistors(graph, node1, node2):
    """Combine two series resistors into one equivalent resistor."""
    resistance1 = graph[node1][node2]
    resistance2 = graph[node2][node1]
    equivalent_resistance = resistance1 + resistance2
    # Remove the old resistors and add the equivalent resistor
    graph[node1][node2] = equivalent_resistance
    graph[node2][node1] = equivalent_resistance

def combine_parallel_resistors(graph, node1, node2):
    """Combine two parallel resistors into one equivalent resistor."""
    resistance1 = graph[node1][node2]
    resistance2 = graph[node2][node1]
    equivalent_resistance = 1 / (1 / resistance1 + 1 / resistance2)
    # Remove the old resistors and add the equivalent resistor
    graph[node1][node2] = equivalent_resistance
    graph[node2][node1] = equivalent_resistance

def calculate_equivalent_resistance(graph):
    """Calculate the equivalent resistance of the entire circuit."""
    while len(graph) > 1:  # Continue until the graph is reduced to one node
        # Identify series and parallel combinations
        series_pairs = find_series_resistors(graph)
        parallel_pairs = find_parallel_resistors(graph)

        if series_pairs:
            for pair in series_pairs:
                combine_series_resistors(graph, pair[0], pair[1])
        
        if parallel_pairs:
            for pair in parallel_pairs:
                combine_parallel_resistors(graph, pair[0], pair[1])

    # Return the equivalent resistance of the circuit
```
