---
title: "MLX Benchmarking"
date: 2024-04-01T21:36:56-04:00
draft: true
---

## Intro

[Andrej Karpathy tutorial](https://www.youtube.com/watch?v=kCc8FmEb1nY)

[MLX Repo](https://github.com/ml-explore/mlx)

## Required Code Changes

## System Specs

| | Macbook | Desktop |
|:---: | :---: | :---:|
|**CPU**| M3 Pro (12 Core) | Intel Core i5-12400f |
|**GPU**| M3 Pro (18 Core) | NVIDIA 2060 12 GB |

## Results
|||||
|:--- | :---: | :---: | :---: |
|**Hyperparameters**||||
|`batch_size` | 16 | 32 | 64 |
|`block_size` | 32 | 128 | 256 |
|`n_embd` | 64 | 256 | 384 |
|`n_head` | 4 | 8 | 6 |
|`n_layer` | 4 | 8 | 6 |
|**Training Times**||||
| Memory Used (MLX) | 300 MB | 1.7 GB | 5.5 GB |
| MLX Training Time (1000 iters) | 37.2s | 4:50.0 | 24:38.4 |
| CUDA Training Time (1000 iters) | 13.4s | 2:29.2 | 12:09.3 |
|**Power Draw**||||
| Macbook SOC Power Consumption | 18W | 18W | 18W |
| Desktop GPU Power Consumption | 180W | 170W* | 170W* |
|**Efficiency (Iterations per Second per Watt)**||||
| Macbook | 1.49 | 0.19 | 0.04 |
| Desktop | 0.44 | 0.04 | 0.01 |
 
*_in longer training sessions, the desktop GPU throttles down to ~170W_
