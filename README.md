# ZINB-GNN-for-sparse-OD-flow-generation
Data and code for the paper: Liang, Y., Zhao, Z., Webster, C. J., 2024. Generating sparse origin-destination flows on shared mobility networks using probabilistic graph neural networks. Sustainable Cities and Society (revision), originally submitted in April 2024.

## Introduction
Shared mobility services, such as bike sharing, have gained immense popularity and emerged as an integral part of sustainable urban mobility solutions. The planning of such systems requires forecasting the potential origin-destination (OD) flows between mobility sites (e.g., bike sharing stations) within the proposed network. Existing methods primarily focus on mobility flows between large regions, and do not generalize well to detailed planning applications due to the high spatial resolution required, with increased uncertainty and data sparsity. This study proposes a zero-inflated negative binomial graph neural network (ZINB-GNN) to generate sparse OD flows while capturing complex spatial dependencies. To reflect sparsity, OD flows are modeled as following ZINB distributions parameterized via feed-forward networks. To capture spatial dependencies, localized graphs are constructed to represent proximity between OD pairs, with spatial features encoded using GNNs. ZINB-GNN is validated through a case study of the bike sharing system in New York City. The results verify its prowess in both prediction accuracy and uncertainty quantification under real-world network expansion scenarios. We also demonstrate its interpretability by revealing important factors affecting OD flows. These findings can directly inform the planning of bike sharing systems, and the methodology may be adapted for other shared mobility systems.

## Data
The efficacy of the proposed model is assessed using data from NYC's Citi Bike System (https://ride.citibikenyc.com/system-data). The system was launched in July 2013, and has made trip details available to the public from its onset, including start and end stations and related timestamps. This study is confined to the period between July 2013 and December 2019 to minimize the impact of the COVID-19 pandemic on biking behavior. 

In this project, all the processed data used in our project are available at: https://drive.google.com/drive/folders/1YFUEtA9BpStGqSL9Qv6eCjJvmexzABfY?usp=sharing, including:
(1) OD flows between BSS stations in each month
(2) processed urban context features around BSS stations and spatial interaction features between station pairs
(3) processed adjacency matrices between BSS stations in each month

## Requirement
python
torch
numpy
scipy
pandas

## How to run:
The code for training and testing the model is available at: src/zinb-gnn.ipynb
