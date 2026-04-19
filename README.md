Advanced Graph Learning for Functional Reverse Engineering of Gate-Level Netlists

This repository implements advanced graph learning methodologies for the functional reverse engineering of optimized gate-level netlists. It focuses on addressing structural ambiguities and scalability challenges using expressive Graph Neural Networks (GNNs).

The project explores both:

Localized subcircuit classification
Global graph learning with pure PyTorch architectures (GIN & GCN)
Acknowledgment

This project builds upon the foundational framework provided by the GNN-RE project.

Original Repository:
https://github.com/DfX-NYUAD/GNN-RE

Repository Structure

The repository is divided into two primary experimental phases:

Part 1: Subcircuit Sampling (GraphSAINT)

Directory:
GNN-RE Subcircuits/GraphSAINT/

Overview

This phase implements a localized, bottom-up classification approach using:

Double-BFS subcircuit sampling
Integration with GraphSAINT
Objective
Extract bounded graph neighborhoods from massive netlists
Avoid loading full graph into GPU memory
Enable scalable training
Features
Efficient Double-BFS sampling
Cached traversal pipeline
GraphSAINT integration
How to Run
cd "GNN-RE Subcircuits/GraphSAINT/"
python run_exp_bfs_cache.py
Part 2: Pure PyTorch GIN & GCN Models

Directory:
GIN and GCN/Netlist_to_graph/Graphs_datasets/Interconnected-Modules/

Overview

This phase introduces custom pure PyTorch models to overcome the contextual limitations of localized sampling.

Graph Isomorphism Network (GIN)

A highly expressive architecture designed for distinguishing structurally complex subgraphs.

Key Features
Weisfeiler-Lehman equivalent aggregation
Differentiates overlapping arithmetic logic structures
Dynamic inverse-frequency class weighting
Run GIN
cd Interconnected-Modules/
python train_gin_multiclass.py
Graph Convolutional Network (GCN)

A scalable baseline model enhanced with custom partitioning.

Key Features
Pure PyTorch implementation
Custom C-level CSR sparse BFS partitioner
VRAM-efficient training on large netlists
Workflow
Generate partitions:
python offline_cluster_bfs.py
Train GCN:
python train_pure_pytorch_gcn.py
