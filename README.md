# Poincaré Embeddings – Experiments and Extensions
This project explores the performance and robustness of Poincaré embeddings, a type of hyperbolic embedding used to capture hierarchical structures in data. The work is divided into two main phases:

🔬 Phase 1: Reproducing and Stress-Testing Poincaré Embeddings
I replicated the core experiments from the original Poincaré paper and applied various "stress tests" to assess embedding performance across different datasets and conditions. The evaluation focused on link prediction and reconstruction, using Mean Rank (MR) and Mean Average Precision (MAP) as metrics.

Experiment 1: Mammals WordNet with edge flipping noise

Experiment 2: Facebook Social Circles with subset size variation

Experiment 3: HebrewNet (custom dataset) with probabilistic edge removal

Across all experiments, I varied embedding dimensions (5 to 200) and evaluated how noise, data size, and dimensionality affected embedding quality.

🧪 Phase 2: Trainable Curvature Extension
In this phase, I modified the original Poincaré embedding algorithm to allow trainable curvature, replacing the fixed 
𝑘
=
−
1
k=−1 assumption with a learnable parameter 
𝑘
=
−
exp
⁡
(
𝛼
)
k=−exp(α). This aimed to make the embedding space more adaptable to different dataset geometries.

Implemented curvature reparameterization with gradient descent

Evaluated performance against original Poincaré model

Found that the original fixed-curvature model consistently outperformed the flexible version across most settings

📦 What's Included
Full experiment results and metrics across all settings

Code for embedding training and curvature modification

Custom dataset (HebrewNet) and data processing scripts

Jupyter notebooks comparing original vs. modified models

📉 Key Insights
The original Poincaré model with 
𝑘
=
−
1
k=−1 is surprisingly robust—even for non-hierarchical data

Introducing trainable curvature adds complexity and didn’t yield consistent improvements

Dimensionality matters more under noisy or data-scarce conditions

Link prediction is more sensitive to noise than reconstruction

💡 Future Work
Improving the trainable curvature version may require:

Smarter optimization schedules

Better initialization of curvature

Regularization or clamping strategies

