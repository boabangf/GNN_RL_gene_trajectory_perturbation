Projected Name: **StemTwin Analytics**

Sponsors

<img width="1771" height="427" alt="image" src="https://github.com/user-attachments/assets/c0a64fac-a685-42e6-8b15-f341fee5bdfd" />

**Project Vision:** Digital Twin for Stem Cell Differentiation and Therapeutic Reprogramming

I will be attending the Omics Codeathon April  2026: https://docs.google.com/forms/d/e/1FAIpQLSfmWvIxuE7JR4T7kwfWA_HIt0GUQ_czqVlK2zeeio5tzBmmvw/viewform?pli=1

 Unified CTRL + PTPN2 RL (Model-based + Model-free)

 Omics Codeathon, Boabang Francis

 Encoder:
 
    - Align genes (CTRL, PTPN2)

   - True 80/20 split on PTPN2 BEFORE preprocessing

   - HVG on PTPN2-TRAIN only → applied to PTPN2-TEST + CTRL

   - Gene Autoencoder (PTPN2-TRAIN only)

   - PCA (PTPN2-TRAIN only, applied to all)

   - Simple inference-only GAT on joint PCA space

 RL:

 PTPN2: model-based RL with world model f_θ, perturb once at t=0

 CTRL: model-free RL, multi-step perturbation (additive updates)

Our framework goes beyond IQCELL-style paper by:

 Heydari, Tiam, et al. "IQCELL: A platform for predicting the effect of gene perturbations 

on developmental trajectories using single-cell RNA-seq data." PLoS Computational Biology 18.2 (2022): e1009907.

Performing direct quantitative matching (MSE, DTW, Wasserstein, Pearson)

Comparing simulated continuous trajectories vs scRNA-seq perturbation


Using model-based + model-free RL, not Boolean rules

 Evaluation:

   - Single-dim metrics ( MSE, RMSE, MAE, R2, Pearson, AUPRC
   - 
   - Distance to REAL PTPN2 TRAIN mean

   - Pseudotime alignment (mapped to PTPN2 pseudotime)

   - IQCELL-style:

       * Full H-step trajectories (mean simulated vs experimental)

       * DTW per latent dimension

       * 1D Wasserstein (OT) per dimension

       * DTW heatmap (CTRL vs PTPN2)

       * Combined similarity table (CSV)



**Unperturb data (Control Sample) and Perturb data with CRISPRKO (Single Perturbation)**

Code: https://colab.research.google.com/drive/1pJJpmq2cz5iY0ctqEYmCx7U8p4kUNRa-?usp=sharing

Data: https://drive.google.com/drive/folders/1AAI4KU9G-UHoKo72Ne6iGAaCgFPADIW3?usp=drive_link

**https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE134139**


**https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE156478**

**https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE126310**


**Drug treatment in Mouse(Double Perturbation)**

Anti–PD-1 → blocks PD-1/PD-L1 suppressive axis

Anti–CTLA-4 → blocks regulatory checkpoints & enhances T cell priming

Link to Code: https://colab.research.google.com/drive/1UoPEKODPjZeQ2BuGoC5iFKkUqwlj3bkm?usp=sharing


**https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE119352**





http://www.perturbase.cn/


Heydari, Tiam, et al. "IQCELL: A platform for predicting the effect of gene perturbations on developmental trajectories using single-cell RNA-seq data." PLoS Computational Biology 18.2 (2022): e1009907. (In-silico Perturbation)



 **Goal:** AI for understanding developmental pathways

**Our mission** is to accelerate recovery from cancer, enable next-generation vaccine creation, and combat autoimmune diseases through advanced cellular reprogramming integrated with a digital twin of wet-lab stem cell differentiation experiments. This digital twin will replicate the complex molecular and epigenetic dynamics of stem cell differentiation in silico, allowing bioinformaticians and experimental biologists to simulate, optimize, and refine cellular behavior in real time. 


UBC Seminar: 5th September 2025, Title of  Talk: **** Machine Learning Optimization Methods and Their Application to Predicting Stem Cell Differentiation Using GNNs and Reinforcement Learning-UBC 5th September 2025****


***Escaping Local Optima in the Waddington Landscape: A Multi-Stage TRPO–PPO  Approach for Single-Cell Perturbation Analysis - To be Submitted to   IEEE Transactions on Computational Biology and Bioinformatics***


(https://arxiv.org/html/2510.13018v1)

****(To be submitted) - Enhanced Adaptive Stochastic Gradient Descent: Convergence Analysis and Its Application in Single-Cell Perturbation Analysis (To be submitted to IEEE Transactions on Neural Networks and Learning Systems)****


https://github.com/boabangf/GNN_RL_gene_trajectory_perturbation/blob/main/Multi-Step%20Differentiation%20Experiment/Enhanced_Adaptive_Stochastic_Gradient_Descent__Convergence_Analysis_and_Its_Application_in_Single_Cell_Perturbation_Analysis.pdf

Link to github for double bind submission: https://github.com/TNNLS-PeerReview/ASGD-ADAM/tree/main

Reference

https://www.ncbi.nlm.nih.gov/search/all/?term=scRNA-seq

http://www.perturbase.cn/

Xing, Hanwen, and Christopher Yau. "GPerturb: Gaussian process modelling of single-cell perturbation data." Nature Communications 16.1 (2025): 5423.

Zhiting Wei, Duanmiao Si, Bin Duan, Yicheng Gao, Qian Yu, Zhenbo Zhang, Ling Guo, Qi Liu, PerturBase: a comprehensive database for single-cell perturbation data analysis and visualization, Nucleic Acids Research, Volume 53, Issue D1, 6 January 2025,

Kamimoto, Kenji, et al. "Dissecting cell identity via network inference and in silico gene perturbation." Nature 614.7949 (2023): 742-751.

