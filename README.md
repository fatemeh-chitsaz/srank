# SibRank / SRank Recommendation Framework

An implementation of a graph-based recommendation workflow built around a **Structured Bipartite Network (SiBreNet)** and **SRank** scores.

The project represents user preferences as a structured graph, estimates similarity through positive/negative ranking signals, finds relevant neighbors, infers missing rankings, and produces top-k recommendations.

## Pipeline

```text
preference data
      ↓
SiBreNet construction
      ↓
positive / negative SRank
      ↓
neighbor discovery
      ↓
ranking inference
      ↓
top-k recommendation
```

## Main stages

### 1. SiBreNet construction

Preference data — including rankings and temporal/order information — is converted into a structured bipartite network.

### 2. SRank calculation

For a target user, the method calculates positive and negative ranking signals over the graph.

### 3. Neighbor discovery

Users with related preference structure are identified using the computed SRank information.

### 4. Ranking inference

Neighbor information is used to estimate the target user's missing preferences.

### 5. Top-k recommendation

The inferred ranking is converted into a final recommendation list.

## Dependencies

```bash
pip install pandas numpy scipy networkx
```

## Project status

The repository currently captures the algorithmic implementation and workflow, but it does not yet include a polished benchmark section.

For a research-quality release, the next additions should be:

- dataset description and preprocessing;
- explicit train/test protocol;
- recommendation metrics such as Precision@K, Recall@K, NDCG@K, and MAP;
- baseline comparisons;
- runtime/complexity measurements;
- experiment seeds and reproducible scripts.


