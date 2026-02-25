# Spectral Clustering

**Computational Linear Algebra – Academic Year 2024–2025**  
**Authors:** Ismail Aljosevic (s337769), Daniele Amato (s334211)

## 📌 Project Overview

This project implements **Spectral Clustering** for detecting non-linearly separable cluster structures.

The method was applied to:

- Circle dataset (900 points)
- Spiral dataset (312 points)
- Custom 3D Circles dataset (450 points)

The complete theoretical explanation and results are available in:

- `report.pdf` – full lab report (readable independently of the code)
- `software.ipynb` – contains the complete implementation of the spectral clustering pipeline

## ⚙ Methodology

1. Construct k-nearest neighbors similarity graph  
2. Build adjacency matrix \( W \)  
3. Compute Degree matrix \( D \)  
4. Construct Laplacian matrix:

Unnormalized:
$$
L = D - W
$$

Normalized symmetric:
$$
L_{sym} = I - D^{-1/2} W D^{-1/2}
$$

5. Compute smallest eigenvalues  
6. Select number of clusters using **Eigengap heuristic**  
7. Perform K-means on spectral embedding  

Smallest eigenvalues were computed using:

- Shifted Inverse Power Method  
- Householder Deflation  

## 📊 Results Summary

### Circle Dataset
- Best result: **k = 10**
- Selected clusters: M = 3
- Spectral clustering correctly separates non-linear structure

### Spiral Dataset
- Consistent result: M = 3
- Spectral clustering outperforms classical K-means

### 3D Circles Dataset
- Best result: k = 10 → M = 3
- Larger k values reduce cluster separability

