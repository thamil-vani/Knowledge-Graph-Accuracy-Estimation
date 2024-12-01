**This is a reproduction of the experiment : Efficient and Reliable Estimation of Knowledge Graph Accuracy by Stefano Marchesin and Gianmaria Silvello.**

**Experimental Results:**

**Interval Comparison Experiment:**
This experiment evaluates the efficiency and reliability of binomial confidence intervals—Wald, Wilson, continuity-corrected Wilson, and Agresti-Coull—using datasets from YAGO, NELL, and DisGeNET under simple random sampling. Efficiency was measured through annotation costs, while reliability was assessed via empirical coverage probabilities compared to the nominal coverage of 0.95.
The reproduced results aligned with the original findings:

Efficiency: Annotation costs increased as accuracy moved toward the midpoint (e.g., μ=0.5 for DisGeNET TEM). The Wald interval was most efficient for boundary accuracies (YAGO, NELL), outperforming Wilson, corrected Wilson, and Agresti-Coull. However, Wilson and Agresti-Coull were more efficient as accuracy deviated from boundaries.
Reliability: The Wald interval failed to meet nominal coverage on boundary datasets (e.g., 0.20 for YAGO), while Wilson, corrected Wilson, and Agresti-Coull consistently achieved or exceeded nominal coverage across all datasets.
The study confirmed that Wilson and Agresti-Coull intervals provide a better balance between efficiency and reliability, especially as KG accuracy moves away from the boundaries.

**Wald Limitations Experiment:**
In reproducing the experiment on the limitations of the Wald interval, the results closely matched the original findings, with only minor variations. For example, DisGeNET CEM with the STWCS sampling strategy exhibited 10 iterations with zero-width intervals in our reproduction, compared to 9 in the original study. This slight difference likely stems from the inherent randomness in sampling strategies like TWCS and STWCS. Despite these minimal variations, the overall trends and conclusions regarding the Wald interval's limitations were consistent with the original experiment.

**Method Comparison:**
The reproduced experiment compared Wilson and Wald confidence intervals under TWCS (Two-Way Cluster Sampling) and STWCS (Stratified Two-Way Cluster Sampling) across diverse Knowledge Graphs, focusing on coverage probabilities and annotation costs. For DisGeNET TEM with TWCS using Wilson (εₜ = 0.5), the original experiment reported a coverage of 0.95±0.01, while the reproduced results showed 0.93±0.02. Similarly, for STWCS, the original coverage was 0.93±0.02, and the reproduced experiment yielded 0.92±0.02. These minor differences are likely due to the randomness inherent in sampling and clustering methods. Despite these variations, the overall trends and findings closely aligned with the original study.

**Scalability:**


![image](https://github.com/user-attachments/assets/c7102c6e-e4c1-4a2f-b2cb-2845a2de4130)



![image](https://github.com/user-attachments/assets/98081bd1-6d78-4dca-b60d-3d57d9cd5c64)


The original experiment tested scalability using SYN 100M, but due to memory constraints, we reproduced the experiment using a smaller synthetic dataset of 1M triples. Results from the reproduced experiment (Table 1) and the original experiment (Table 2) show similar trends. Across all sampling techniques (SRS, TWCS, and STWCS), Wilson intervals consistently provided better coverage than Wald intervals. These findings confirm that the proposed algorithm is scalable, even when applied to smaller datasets, demonstrating its robustness across different scales.
