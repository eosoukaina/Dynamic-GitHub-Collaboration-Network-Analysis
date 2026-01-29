# 📊 Dynamic GitHub Collaboration Network Analysis

> **A comprehensive temporal analysis of open-source collaboration networks using GitHub API data**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![NetworkX](https://img.shields.io/badge/NetworkX-3.0+-orange.svg)](https://networkx.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📋 Table of Contents

- [Overview](#overview)
- [Project Objectives](#project-objectives)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Key Findings](#key-findings)
- [Project Structure](#project-structure)
- [Technologies](#technologies)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Contributors](#contributors)

## 🎯 Overview

This project presents a **temporal network analysis** of collaboration patterns in the **pandas** open-source project, one of Python's most popular data analysis libraries. By leveraging the GitHub API, we construct dynamic collaboration networks where nodes represent developers and edges symbolize collaborative relationships through shared file modifications.

The analysis combines:
- **Social Network Analysis** (centrality, communities, structure)
- **Statistical Testing** (hypothesis validation, model comparison)
- **Machine Learning** (future influence prediction)
- **Dynamic Visualizations** (temporal evolution)

### 🏆 Key Features

- ✅ **Automated Data Pipeline**: Complete ETL process from GitHub API to network graphs
- ✅ **Temporal Analysis**: Monthly network snapshots with evolution tracking
- ✅ **Statistical Validation**: Rigorous hypothesis testing and model comparison
- ✅ **Predictive Modeling**: Random Forest regression for influence forecasting
- ✅ **Community Detection**: Louvain algorithm for identifying developer clusters
- ✅ **Reproducible Research**: Comprehensive Jupyter notebook with detailed documentation

## 🎯 Project Objectives

1. **Construct** dynamic collaboration networks from GitHub commit data
2. **Analyze** temporal evolution of structural network metrics
3. **Identify** influential developers and community structures
4. **Predict** future contributor influence using machine learning
5. **Compare** observed networks with theoretical models (Erdős-Rényi, Barabási-Albert)
6. **Validate** findings through rigorous statistical testing

## 📊 Dataset

### Source
- **Platform**: GitHub API v3
- **Repository**: `pandas-dev/pandas`
- **Time Period**: October - December 2025
- **Data Points**: ~2,000 commits analyzed

### Data Collection

```python
# Core data extracted:
- Commit metadata (author, date, SHA, message)
- File modifications per commit
- Developer collaboration patterns
- Temporal activity distributions
```

### Network Construction

**Graph Model**: Undirected weighted graph

- **Nodes**: Developers (commit authors)
- **Edges**: Co-editing relationships (developers modifying the same files)
- **Weights**: Number of co-edited files (collaboration intensity)
- **Temporal Granularity**: Monthly aggregation

## 🔬 Methodology

### 1. Data Engineering Pipeline

<img width="2400" height="800" alt="Image" src="https://github.com/user-attachments/assets/68d1b368-b9f5-4c43-92ac-73abe7b48a50" />

### 2. Network Metrics

#### Global Metrics (Network-level)
- **Size**: Number of nodes and edges
- **Density**: Proportion of existing connections
- **Clustering Coefficient**: Tendency to form triangles
- **Diameter**: Maximum distance between nodes
- **Connected Components**: Isolated subgraphs

#### Local Metrics (Node-level)
- **Degree Centrality**: Number of direct connections
- **Betweenness Centrality**: Bridge role between communities
- **Closeness Centrality**: Average proximity to other nodes
- **PageRank**: Global influence measure

#### Advanced Metrics
- **Assortativity**: Degree correlation between neighbors
- **Transitivity**: Global clustering
- **K-Core**: Dense core cohesion
- **Average Path Length**: Mean distance between nodes

### 3. Statistical Analysis

- Pearson & Spearman correlation tests
- Mann-Whitney U tests for group comparison
- Kolmogorov-Smirnov tests for distribution comparison
- Monte Carlo simulations for theoretical model validation

### 4. Machine Learning Pipeline

```python
# Predictive modeling workflow:
1. Feature extraction: Previous period centrality metrics
2. Target variable: Future PageRank (influence proxy)
3. Algorithm: Random Forest Regressor
4. Validation: Train/test split + 5-fold cross-validation
5. Evaluation: R², RMSE, MAE
```

## 🔑 Key Findings

### Network Structure

The pandas collaboration network exhibits **scale-free properties**:

| Property | Observed Value | Interpretation |
|----------|----------------|----------------|
| **Clustering** | 0.36 - 0.79 | ≫ Random graph (0.37-0.40) |
| **Diameter** | ~2 | Strong "small-world" property |
| **Degree Distribution** | Power-law | Presence of influential hubs (max: 47) |
| **Assortativity** | -0.25 to -0.71 | Hubs connect to periphery |

✅ **Statistical Validation**: Network is NOT random - follows preferential attachment model (Barabási-Albert)

### Temporal Dynamics

Analysis of **3 monthly periods** (Oct-Dec 2025):

| Period | Nodes | Edges | Density | Clustering | Activity Level |
|--------|-------|-------|---------|------------|----------------|
| **2025-10** | 4 | 4 | 0.667 | 0.583 | Calm period |
| **2025-11** | 39 | 254 | 0.343 | 0.794 | Peak activity |
| **2025-12** | 23 | 42 | 0.166 | 0.362 | Moderate activity |

**Key Observations**:
- 📈 **9.75× variability** in active developers (4 → 39)
- 📈 **63.5× variability** in collaborations (4 → 254)
- 🔥 **November 2025**: Major activity spike (sprint period)

### Community Structure

- **Number of communities**: 2-10 per period (Louvain algorithm)
- **Stability (NMI)**: 0.264 (low - high developer mobility)
- **Retention rate**: 25% of developers remain in same community

### Predictive Modeling

**Feature Importance for Influence Prediction**:
1. **Betweenness Centrality** (39%) - Bridge role
2. **Degree Centrality** (35%) - Direct collaborations
3. **Previous PageRank** (26%) - Historical influence

⚠️ **Note**: Limited dataset (3 periods) constrains predictive performance. Extended temporal coverage would improve model accuracy.

## 📁 Project Structure

```
Azure-project/
│
├── src/SNM.ipynb              # Main analysis notebook (comprehensive)
├── README.md   # This file
|── assets/                  # Visualizations and figures

```

### Notebook Organization

The `SNM.ipynb` notebook is structured in **6 main parts**:

1. **Part I**: Introduction and Methodology
2. **Part II**: Data Collection & Preparation
3. **Part III**: Network Construction
4. **Part IV**: Structural Network Analysis
5. **Part V**: Advanced Analysis & Statistical Validation
6. **Part VI**: Synthesis & Conclusions

## 🛠️ Technologies

### Core Stack

| Technology | Purpose | Version |
|------------|---------|---------|
| **Python** | Programming language | 3.8+ |
| **NetworkX** | Graph analysis | 3.0+ |
| **pandas** | Data manipulation | 1.5+ |
| **NumPy** | Numerical computing | 1.24+ |
| **scikit-learn** | Machine learning | 1.2+ |
| **matplotlib** | Visualization | 3.7+ |
| **seaborn** | Statistical visualization | 0.12+ |
| **scipy** | Statistical tests | 1.10+ |

### Additional Libraries

- **requests**: GitHub API interactions
- **python-louvain**: Community detection
- **tqdm**: Progress bars
- **pickle**: Object serialization

## 🚀 Installation

### Prerequisites

- Python 3.8 or higher
- pip package manager
- GitHub API token (optional, for higher rate limits)

### Setup Instructions

1. **Clone the repository**
```bash
git clone https://github.com/eosoukaina/Dynamic-Github-Collaboration-network-Analysis.git
cd Dynamic-Github-Collaboration-network-Analysis
```

2. **Install dependencies**
```bash
pip install pandas numpy networkx matplotlib seaborn scipy scikit-learn requests python-louvain tqdm jupyter
```

## 📖 Usage

### Running the Analysis

1. **Start Jupyter Notebook**
```bash
jupyter notebook
```

2. **Open `SNM.ipynb`**

3. **Run cells sequentially** (or use "Run All")

### Customization Options

#### Analyze Different Repository
```python
# Modify in Part II:
REPO_OWNER = "your-org"
REPO_NAME = "your-project"
```

#### Adjust Time Period
```python
# Modify commit query parameters:
since_date = "2024-01-01"
until_date = "2024-12-31"
```

#### Change Temporal Granularity
```python
# Monthly (default):
df['year_month'] = df['commit_date'].dt.to_period('M')

# Weekly:
df['year_week'] = df['commit_date'].dt.to_period('W')
```

## 📈 Results

### Visualizations Generated

1. **Network Structure Evolution**
   - Node/edge count over time
   - Density and clustering trends
   - Community size distribution

2. **Centrality Analysis**
   - Top influential developers
   - Centrality measure comparisons
   - Temporal centrality evolution

3. **Community Detection**
   - Community structure visualization
   - Stability analysis (NMI)
   - Inter-community connections

4. **Statistical Validation**
   - Degree distribution (log-log plot)
   - Model comparison (ER vs BA vs Observed)
   - Feature importance (ML model)

### Example Outputs

**Network Metrics Summary**:
```
Period: 2025-11 (Peak Activity)
├── Nodes: 39 developers
├── Edges: 254 collaborations
├── Density: 0.343
├── Avg Clustering: 0.794
├── Diameter: 2
└── Communities: 6 detected
```

**Top Influential Developers** (PageRank):
1. Developer A: 0.0521
2. Developer B: 0.0487
3. Developer C: 0.0423

## 👥 Contributors

This project was developed as part of the **Social Network Mining** module:

- **Chakouri Salma** - Data Engineering & Analysis
- **El Guelta Mohamed-Saber** - Network Construction & Modeling
- **Soukaina El Hadifi** - Statistical Validation & Visualization
- **Ibnchakroun Houssam** - Machine Learning & Prediction

**Supervisor**: Pr. O. El Haddadi  
**Academic Year**: 2025-2026


## 🙏 Acknowledgments

- **pandas development team** for maintaining an excellent open-source project
- **GitHub** for providing comprehensive API access
- **NetworkX community** for robust graph analysis tools
- **Academic supervisors** for guidance and feedback

---

### 📧 Contact

For questions or collaboration opportunities, please reach out to the project contributors or open an issue on GitHub.

---


