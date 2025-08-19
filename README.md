Dataset: https://gitlab.com/stemcellbioengineering/iqcell/-/tree/master/Mouse%20T-cell%20Supplementary%20dataset?ref_type=heads



Title of the Talk: **** Machine Learning Optimization Methods and Their Application to Predicting T-Cell Differentiation Using GNNs and Reinforcement Learning****

#adata = sc.datasets.paul15()


#adata = sc.datasets.moignard15()


#adata = sc.datasets.visium_sge()

****(cell, gene)****


The goal of this project is to transform the gene regulatory system into GNN and reinforcement  for predicting the effect of gene perturbations on developmental trajectories using single-cell RNA-seq data

GNN and its variants:



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


train_steps = {


    "A2C": 1000000,

    
    "PPO": 1000000,

    
    "SAC": 1000000,

    
    "TRPO": 1000000,

    
    "TRPO_to_PPO": 500000, ***First stage of the Proposed method ***

    
    "TRPO_from_PPO": 500000 ***Second  stage of the Proposed method***

    
}



Algorithm2 

algorithms = {


    #"StandardPPO": {"class": StandardPPO, "kwargs": common_kwargs},

    
    "ProposedFocalPPO": {"class": ProposedFocalPPO, "kwargs": common_kwargs},
    
    
    #"FixedGammaFocalPPO": {"class": FixedGammaFocalPPO, "kwargs": common_kwargs},
   
   
   #"ScopePPO": {"class": ScopePPO, "kwargs": common_kwargs},


}

train_steps = {name: 100_000 for name in algorithms}



***CITATION**


Heydari, Tiam, et al. "IQCELL: A platform for predicting the effect of gene perturbations on developmental trajectories using single-cell RNA-seq data." PLoS Computational Biology 18.2 (2022): e1009907.


Fu, Zeyu, et al. "scRL: Utilizing Reinforcement Learning to Evaluate Fate Decisions in Single-Cell Data." Biology 14.6 (2025): 679.
