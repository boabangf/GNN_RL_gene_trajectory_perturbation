Dataset: https://gitlab.com/stemcellbioengineering/iqcell/-/tree/master/Mouse%20T-cell%20Supplementary%20dataset?ref_type=heads



Title of the Talk: **** Machine Learning Optimization Methods and Their Application to Predicting T-Cell Differentiation Using GNNs and Reinforcement Learning****

#adata = sc.datasets.paul15()


#adata = sc.datasets.moignard15()


#adata = sc.datasets.visium_sge()

****(cell, gene)****


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


    "A2C": 1000000,

    
    "PPO": 1000000,

    
    "SAC": 1000000,

    
    "TRPO": 1000000,

    
    "TRPO_to_PPO": 500000, ***First stage of the Proposed method ***

    
    "TRPO_from_PPO": 500000 ***Second  stage of the Proposed method***

    
}



Algorithm2 

algorithms = {


    "StandardPPO": {"class": StandardPPO, "kwargs": common_kwargs},

    
    "FixedGammaFocalPPO": {"class": FixedGammaFocalPPO, "kwargs": common_kwargs},

    
    "StagedGammaFocalPPO": {"class": StagedGammaFocalPPO, "kwargs": common_kwargs}, # offline Proposed method

    
    "AdaptiveGammaFocalPPO": {"class": AdaptiveGammaFocalPPO, "kwargs": common_kwargs},    # Online update Proposed method
    
    #  Why start high and reduce:
    

Early training: High gamma encourages exploration of long-term strategies, preventing the agent from just chasing immediate rewards.


Later training: Reducing gamma helps stabilize learning by letting the agent focus more on immediate, reliable rewards, reducing variance in value estimates.
}


train_steps = {

    "StandardPPO": 1000000,
    
    "FixedGammaFocalPPO": 1000000,
    
    "StagedGammaFocalPPO": 1000000, # Proposed method
    
    "AdaptiveGammaFocalPPO": 1000000,  # Proposed method
    
}

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
