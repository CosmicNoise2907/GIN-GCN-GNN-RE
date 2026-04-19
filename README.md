content = """# Reverse Engineering of Gate-Level Netlists: Subcircuit Sampling and Graph Isomorphism Networks

This repository contains the codebase for advanced graph learning methodologies applied to the functional reverse engineering of optimized gate-level netlists. It explores localized subcircuit classification and introduces highly expressive, pure PyTorch architectures (GIN and GCN) to resolve structural ambiguities and scalability bottlenecks in hardware security.

## Acknowledgment
This project builds upon the foundational framework provided by the **GNN-RE** project. We extend our sincere gratitude to the original authors. 
* **Original Repository:** [DfX-NYUAD/GNN-RE](https://github.com/DfX-NYUAD/GNN-RE/tree/main)

---

## Repository Structure

The repository is divided into two primary exploratory phases:

### Part 1: Subcircuit Sampling (GraphSAINT)
Located in the `GNN-RE Subcircuits/GraphSAINT/` directory.

This section explores a localized, bottom-up classification approach. It utilizes a Double-BFS subcircuit sampling methodology integrated with the existing GraphSAINT model from the original GNN-RE framework. The goal is to extract and classify bounded graph neighborhoods from massive netlists without loading the entire global topology into GPU memory.

**To run the Subcircuit Sampler and GraphSAINT training:**
Navigate to the `GraphSAINT` directory and execute the automated experiment pipeline:
```bash
python run_exp_bfs_cache.py
