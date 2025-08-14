Dataset: https://gitlab.com/stemcellbioengineering/iqcell/-/tree/master/Mouse%20T-cell%20Supplementary%20dataset?ref_type=heads


#adata = sc.datasets.paul15()


#adata = sc.datasets.moignard15()


#adata = sc.datasets.visium_sge()

****(cell, gene)****


The goal of this project is to transform the gene regulatory system into GNN and reinforcement  for predicting the effect of gene perturbations on developmental trajectories using single-cell RNA-seq data

Variational Graph Autoencoder (VGAE) – a graph autoencoder variant that uses variational inference to learn a probabilistic latent representation of graph-structured data.

Graph Convolutional Neural Network (GCN) – a neural network architecture that generalizes convolution to graph domains. 

Model free reinforcement learning-sample inefficient



Model based reinforcement learning- Sample efficient

Mean square error to meaure the difference between the target perturbation trajectory and predicted.



algorithms = {


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

    
    "TRPO_to_PPO": {"class": PPO, "kwargs": {}},

    
    "TRPO_from_PPO": {"class": TRPO, "kwargs": {}}

    
}


train_steps = {


    "A2C": 1000000,

    
    "PPO": 1000000,

    
    "SAC": 1000000,

    
    "TRPO": 1000000,

    
    "TRPO_to_PPO": 500000,

    
    "TRPO_from_PPO": 500000

    
}


***CITATION**




Heydari, Tiam, et al. "IQCELL: A platform for predicting the effect of gene perturbations on developmental trajectories using single-cell RNA-seq data." PLoS Computational Biology 18.2 (2022): e1009907.
