**Our mission:** We want to help people recover from cancer and treats autoimmune diseases by cell reprogramming and developing a digital twin of wet-lab stem cell differentiation experiments. This digital twin will enable bioinformaticians to simulate and fine-tune their models more efficiently, accelerating discoveries and improving personalized treatment strategies.



UBC 5th September 2025, Title of  Talk: **** Machine Learning Optimization Methods and Their Application to Predicting Stem Cell Differentiation Using GNNs and Reinforcement Learning-UBC 5th September 2025****


***Escaping Local Optima in the Waddington Landscape: A Multi-Stage TRPO–PPO  Approach for Single-Cell Perturbation Analysis - Under Review in IEEE Transactions on Computational Biology and Bioinformatics***

https://github.com/boabangf/GNN_RL_gene_trajectory_perturbation/blob/main/Multi-Step%20Differentiation%20Experiment/Escaping_Local_Optima_in_the_Waddington_Landscape__A_Multi_Stage_TRPO_PPO_Approach_for_Single_Cell_Perturbation_Analysis.pdf


****Paper Draft - Enhanced Adaptive Stochastic Gradient Descent: Convergence Analysis and Its Application in Single-Cell Perturbation Analysis (possible venue-JMLR)****



*** New Research Direction from Epitopea*** ****Class II antigen immune system recognition and response using machine learning(Modeling Antigentic Landscape)**** 

****Major Histocompatibility Complex (MHC) class II molecules are essential for immune recognition by presenting antigenic peptides to CD4⁺ T cells, a process critical for vaccine design and immunotherapy. However, accurately predicting peptide–MHC class II interactions remains challenging due to molecular diversity and complex binding mechanisms. This study proposes an advanced machine learning framework integrating bidirectional encoding, transformer-based architectures, and reinforcement learning optimization to enhance class II antigen recognition and response modeling. Peptide and MHC sequences will be encoded using contextual representations derived from bidirectional neural networks and transformer attention mechanisms, enabling the model to capture both local and global dependencies. A reinforcement learning loop will iteratively refine predictions based on biological relevance, improving the interpretability and accuracy of antigen binding landscapes. The model will be trained and evaluated using benchmark datasets such as IEDB, with performance measured through accuracy, F1-score, and AUC metrics. Expected outcomes include improved predictive performance, deeper insight into peptide MHC binding mechanisms, and a scalable framework for applications in immunotherapy and vaccine discovery.-1st October 2025****

****Link to sample dataset: https://www.iedb.org/****


Videos lectures on Computational Biology: https://www.youtube.com/playlist?list=PLypiXJdtIca4gtioEPLIExlAKvu64z7rc

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/3e8f3437-b3fb-4b92-8f7a-e20ad7eafa3d" />


 
 Gene regulatory network or protein or metabolic network can be included as prior knowledge into the GNN embedding or we can consider fully data-driven case.
 
I hold the view point that  creating completely data-driven model can outperform methods that include prior knowledge from regulatory networks.




Dataset: https://gitlab.com/stemcellbioengineering/iqcell/-/tree/master/Mouse%20T-cell%20Supplementary%20dataset?ref_type=heads  




**build a multimodal framework that integrates  - RNA, CITE, ATAC dataset with in-silico perturbation (i.e., crisper, cytokine simulation, drug perturbation)- select mode: RNA, ATAC or ALL(JOINT)**


****Joint modeling of proteomics, genomics and trancriptomics(Multi-omic integration)   ****

<img width="1100" height="700" alt="image" src="https://github.com/user-attachments/assets/dd79fdfc-2835-4987-b2d6-dfb3aeadbfaa" />



****Algorithm  1  (METRICS-RMSE, MSE, MAE, R^2 )****



 
****Timeseries Prediction: NonConvex  and Strongly Convex cases: Focusing on multistep prediction(multistep differentiation)  to reach a particular lineage****

****MAX_STEPS > 200 to reach a particular lineage with single or double perturbation****


<img width="863" height="362" alt="Screenshot 2025-10-03 at 9 47 02 PM" src="https://github.com/user-attachments/assets/3d83af32-3128-4113-af17-d46d7cd53ef9" />



The proposed ASGDAdam/ASGDAmsgrad optimizers (nonconvex case) are particularly well-suited for step-ahead prediction of cell fate and lineage using single-cell gene expression data. These datasets are inherently sparse, with a large fraction of entries consisting of zeros due to gene perturbations, and they exhibit strong variability across temporal or pseudotime trajectories. In the context of multistep-ahead prediction, this variability is amplified: early prediction errors can propagate forward, making stability in optimization crucial.

Traditional optimizers with a fixed base learning rate often struggle in this setting. A static learning rate may be too conservative, slowing convergence across many zero-gradient steps, or too aggressive, leading to instability when the model encounters rare but highly informative non-zero updates. By contrast, the proposed ASGD-based optimizers dynamically alternate between a cautious learning rate (lr_max) and a more aggressive one (lr_max), enabling them to adjust effectively to the shifting gradient landscape.

This dual learning rate mechanism enhances the optimizer’s ability to (i) exploit informative non-zero updates to capture critical regulatory signals for predicting future cell states, and (ii) maintain stability across long sequences of  noisy updates where error accumulation is a risk. As a result, the method is better aligned with the demands of multistep-ahead cell fate prediction, where capturing both immediate and downstream transitions in gene expression trajectories requires an optimizer that can flexibly adapt to fluctuations in  variability.

**** The version the algorithm in Francis Boabang's Thesis (Nonconvex and Strongly Convex Cases)****

<img width="651" height="646" alt="image" src="https://github.com/user-attachments/assets/1c657469-294c-4643-8384-0845169f03e1" />

https://spectrum.library.concordia.ca/id/eprint/994877/


In reinforcement learning, you can force local optima by:

Using short horizon episodes, so the policy learns a “shortcut” behavior that is locally optimal but not globally optimum. We proposed three algorithms to achieve a global optimal solution.




RL algorithms = {


    "A2C": {"class": A2C, "kwargs": {}},

    
    "PPO": {"class": PPO, "kwargs": {}},

    
    "SAC": {

    
        "class": SAC,

        
        "kwargs": {

        
            "learning_rate": 3e-4,

            
            "buffer_size": 1000000,

            
            "batch_size": 256,

            
            "tau": 0.005,

            
            "train_freq": (1, "step"),

            
            "gradient_steps": 1,

            
            "ent_coef": "auto"
        }
        
    },
    "TRPO": {"class": TRPO, "kwargs": {}},

    
    "TRPO_to_PPO": {"class": PPO, "kwargs": {}}, ***First stage of the Proposed method ***

    
    "TRPO_from_PPO": {"class": TRPO, "kwargs": {}} ***Second  stage of the Proposed method***


    
}

By starting with a few steps of TRPO before switching to PPO, we help the model avoid local optima and guide it toward a better solution.


train_steps = {


    "A2C": 100000,

    
    "PPO": 100000,

    
    "SAC": 100000,

    
    "TRPO": 100000,

    
    "TRPO_to_PPO": 1000, ***First stage of the Proposed method ***

    
    "TRPO_from_PPO": 99000 ***Second  stage of the Proposed method***

    
}

<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/66dd7938-87b1-4d05-b423-4b24812a8e42" />















   

Algorithm 3

           ┌───────────────────────────┐
           │      Pretrained Policy     │
           └───────────────────────────┘
                       │
                       ▼
             ┌───────────────────┐
             │  Convex LoRA      │
             │ (stable, sample-  │
             │ efficient warm-up)│
             └───────────────────┘
                       │
                       ▼
             ┌───────────────────┐
             │ Non-Convex LoRA   │
             │ (flexible, escape │
             │ local optima)     │
             └───────────────────┘
                       │
                       ▼
             ┌───────────────────┐
             │  Full Fine-Tuning │
             │ or Standard RL    │
             │ (optional, full  │
             │ policy express.) │
             └───────────────────┘


Lora- standard for low rank matrix factoriaztion

We introduce a multistage Low-Rank Adaptation (LoRA) approach for reinforcement learning. The method starts with convex LoRA updates to stabilize training and improve sample efficiency, then transitions to non-convex LoRA to increase expressiveness and allow the policy to escape local optima.






***CITATION**


Heydari, Tiam, et al. "IQCELL: A platform for predicting the effect of gene perturbations on developmental trajectories using single-cell RNA-seq data." PLoS Computational Biology 18.2 (2022): e1009907.


Fu, Zeyu, et al. "scRL: Utilizing Reinforcement Learning to Evaluate Fate Decisions in Single-Cell Data." Biology 14.6 (2025): 679.


Theodorakis, Nikolaos, et al. "Integrating machine learning with multi-omics technologies in geroscience: towards personalized medicine." Journal of Personalized Medicine 14.9 (2024): 931.

Shahzad M, Tahir MA, Alhussein M, Mobin A, Shams Malick RA, Anwar MS. NeuPD-A Neural Network-Based Approach to Predict Antineoplastic Drug Response. Diagnostics (Basel). 2023 Jun 13;13(12):2043. doi: 10.3390/diagnostics13122043. PMID: 37370938; PMCID: PMC10297062.

Tang, Xiangru, et al. "scAgents: A Multi-Agent Framework for Fully Autonomous End-to-End Single-Cell Perturbation Analysis." ICML 2025 Generative AI and Biology (GenBio) Workshop.

Yu, T., Ekbote, C., Morozov, N., Fan, J., Frossard, P., d’Ascoli, S., & Brbić, M. (2025). Tissue reassembly with generative AI. bioRxiv, 2025-02.


H. H. L. Tam, Y. M. Ng, M. A. A. Boolaky and H. F. Ong, "Predicting Drug Resistance in Cancer Cell Lines Using Machine Learning Approaches," 2024 IEEE International Conference on Bioinformatics and Biomedicine (BIBM), Lisbon, Portugal, 2024


Nilsson, J. B., et al. "Accurate prediction of HLA class II antigen presentation across all loci using tailored data acquisition and refined machine learning 9, eadj6367." Publisher: American Association for the Advancement of Science.
