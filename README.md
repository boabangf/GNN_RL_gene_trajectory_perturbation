**Our mission**  is to accelerate recovery from cancer and combat autoimmune diseases through advanced cellular reprogramming and the development of a digital twin of wet-lab stem cell differentiation experiments. This digital twin will empower bioinformaticians to simulate, optimize, and refine cellular models within the context of wet-lab differentiation, driving faster discoveries, enhancing predictive accuracy, and enabling more personalized and effective therapeutic interventions.


UBC Seminar: 5th September 2025, Title of  Talk: **** Machine Learning Optimization Methods and Their Application to Predicting Stem Cell Differentiation Using GNNs and Reinforcement Learning-UBC 5th September 2025****


***Escaping Local Optima in the Waddington Landscape: A Multi-Stage TRPO–PPO  Approach for Single-Cell Perturbation Analysis - To be Submitted to   IEEE Transactions on Computational Biology and Bioinformatics***

(https://arxiv.org/html/2510.13018v1)

****Initial Paper Draft(To be submitted) - Enhanced Adaptive Stochastic Gradient Descent: Convergence Analysis and Its Application in Single-Cell Perturbation Analysis (To be submitted to IEEE Transactions on Neural Networks and Learning Systems)****


https://github.com/boabangf/GNN_RL_gene_trajectory_perturbation/blob/main/Multi-Step%20Differentiation%20Experiment/Enhanced_Adaptive_Stochastic_Gradient_Descent__Convergence_Analysis_and_Its_Application_in_Single_Cell_Perturbation_Analysis.pdf

Link to github for double bind submission: https://github.com/TNNLS-PeerReview/ASGD-ADAM/tree/main


*** New Research Direction from Epitopea*** ****Class II antigen immune system recognition and response using machine learning(Modeling Antigentic Landscape)1st October 2025****

TCR-CD8-MHC I - cytokines- Immune Response


TCR-CD4-MHC- II - cytokines - Immune Response

peptide–TCR–MHC interactions is learned by IMMUNENET(graph attention model)

This script will compare three activation modes with model distillation:


  1) convex:     Pure ReLU  + nonconvex antigentic Landscape with model distillation
     
  2) nonconvex:  Pure Swish-like + nonconvex antigentic Landscapew ith model distillation
     
  3) multistage: Transition convex→nonconvex after switch_epoch + nonconvex  cytokines- antigentic Landscape with model distillation (To overcome local optima in  the antigentic Landscape Modeling)

It trains the model (supervised), runs a PPO cytokine policy for the immune response, evaluates
MSE, RMSE, MAE, R², Pearson, and saves a CSV "relu_comparison.csv



The model simulates peptide-MHC binding and T-cell recognition with a GAT-style encoder, followed by cytokine-RL (PPO)modulated immune response. ****(Under Construction)****


<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/0183722f-82eb-4978-821f-7df361971b77" />


****Link to sample dataset: https://www.iedb.org/****











***CITATION***

Nilsson, J. B., et al. "Accurate prediction of HLA class II antigen presentation across all loci using tailored data acquisition and refined machine learning 9, eadj6367." Publisher: American Association for the Advancement of Science.

Memczak S, Izpisua Belmonte JC, Graepel T. Escaping ageing through Cell Annealing-a phenomenological model. Cell Res. 2025 
