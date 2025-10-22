**Project Vision:** Digital Twin for Stem Cell Differentiation and Therapeutic Reprogramming


 **Goal:** AI for understanding developmental pathways

**Our mission** is to accelerate recovery from cancer, enable next-generation vaccine creation, and combat autoimmune diseases through advanced cellular reprogramming integrated with a digital twin of wet-lab stem cell differentiation experiments. This digital twin will replicate the complex molecular and epigenetic dynamics of stem cell differentiation in silico, allowing bioinformaticians and experimental biologists to simulate, optimize, and refine cellular behavior in real time. 


UBC Seminar: 5th September 2025, Title of  Talk: **** Machine Learning Optimization Methods and Their Application to Predicting Stem Cell Differentiation Using GNNs and Reinforcement Learning-UBC 5th September 2025****


***Escaping Local Optima in the Waddington Landscape: A Multi-Stage TRPO–PPO  Approach for Single-Cell Perturbation Analysis - To be Submitted to   IEEE Transactions on Computational Biology and Bioinformatics***

(https://arxiv.org/html/2510.13018v1)

****(To be submitted) - Enhanced Adaptive Stochastic Gradient Descent: Convergence Analysis and Its Application in Single-Cell Perturbation Analysis (To be submitted to IEEE Transactions on Neural Networks and Learning Systems)****


https://github.com/boabangf/GNN_RL_gene_trajectory_perturbation/blob/main/Multi-Step%20Differentiation%20Experiment/Enhanced_Adaptive_Stochastic_Gradient_Descent__Convergence_Analysis_and_Its_Application_in_Single_Cell_Perturbation_Analysis.pdf

Link to github for double bind submission: https://github.com/TNNLS-PeerReview/ASGD-ADAM/tree/main


*** New Research Direction from Epitopea*** ****Class II antigen immune system recognition and response using machine learning(Modeling Antigentic Landscape)1st October 2025(Under Construction)****

TCR-CD8-MHC I - cytokines- Immune Response


TCR-CD4-MHC- II - cytokines - Immune Response

peptide–TCR–MHC interactions is learned by IMMUNENET(graph attention model)

ImmuneNet for binding and recognition (antigen II + CD4)

PPO = cytokine behavior(in similar spirit as perturbation or knockout) -trigger immune response

Create a nonconvex Waddington Landscape (loss function) before proceeding to the following steps

This script will compare three activation modes with model distillation:


  1) convex:     softplus(x)   + nonconvex antigentic Landscape with model distillation
     
  2) nonconvex:  Pure sigmoid + nonconvex antigentic Landscape with model distillation
     
  3) convex(nonconvex(x)) + cytokines- antigentic Landscape with model distillation (Reprogramming)

It trains the model (supervised), runs a PPO cytokine policy for the immune response, evaluates
MSE, RMSE, MAE, R², Pearson, and saves a CSV "relu_comparison.csv



The model simulates peptide-MHC binding and T-cell recognition with a GAT-style encoder, followed by cytokine-RL (PPO)modulated immune response. ****(Under Construction)****


<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/0183722f-82eb-4978-821f-7df361971b77" />


****Link to sample dataset: https://www.iedb.org/****





***CITATION***

Nilsson, J. B., et al. "Accurate prediction of HLA class II antigen presentation across all loci using tailored data acquisition and refined machine learning 9, eadj6367." Publisher: American Association for the Advancement of Science.
