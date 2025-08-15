Dataset: https://gitlab.com/stemcellbioengineering/iqcell/-/tree/master/Mouse%20T-cell%20Supplementary%20dataset?ref_type=heads



Title of the Talk: **** Machine Learning Optimization Methods and Their Application to Predicting T-Cell Differentiation Using GNNs and Reinforcement Learning.****

#adata = sc.datasets.paul15()


#adata = sc.datasets.moignard15()


#adata = sc.datasets.visium_sge()

****(cell, gene)****


The goal of this project is to transform the gene regulatory system into GNN and reinforcement  for predicting the effect of gene perturbations on developmental trajectories using single-cell RNA-seq data

Variational Graph Autoencoder (VGAE) – a graph autoencoder variant that uses variational inference to learn a probabilistic latent representation of graph-structured data.

Graph Convolutional Neural Network (GCN) – a neural network architecture that generalizes convolution to graph domains. 

Graph attention Neural Network (GAT)- replaces uniform neighbor aggregation with a learned, per-edge attention weight. For each node, neighbors are weighted by learned attention scores before aggregation — so the model learns which neighbors matter for each node and task.

Any of these variant of graph neural network can be used for the cell embedding



Model free reinforcement learning-sample inefficient



Model based reinforcement learning- Sample efficient with CRISPER Knockout of certain genes

Mean square error to meaure the difference between the target perturbation trajectory and predicted.



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


***CITATION**


Heydari, Tiam, et al. "IQCELL: A platform for predicting the effect of gene perturbations on developmental trajectories using single-cell RNA-seq data." PLoS Computational Biology 18.2 (2022): e1009907.


Fu, Zeyu, et al. "scRL: Utilizing Reinforcement Learning to Evaluate Fate Decisions in Single-Cell Data." Biology 14.6 (2025): 679.
