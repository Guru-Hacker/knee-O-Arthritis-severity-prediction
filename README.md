Knee Osteoarthritis Severity Classification using VGG16:

Used a pretrained VGG16 deep-learning model to classify knee X-ray images into three osteoarthritis severity levels:

Healthy (combines KL-grades 0–2: Healthy, Doubtful, Minimal)

Moderate (KL-grade 3)

Severe (KL-grade 4)

The goal is to assist doctors in early-stage osteoarthritis diagnosis so that timely preventive measures can be recommended.

Key Features:

Uses VGG16 pretrained on ImageNet as the feature extractor

Custom classification head with:

Dual pooling (GAP + GMP)

Four dense layers

Five dropout layers (40–60%)

L2 regularization + BatchNorm

Four-phase progressive fine-tuning:

Train top layers

Unfreeze Block5

Unfreeze Block4 & Block5

Fine-tune full model with ultra-low LR

Extensive data augmentation and class balancing

Automatic:

Model checkpointing

Early stopping

Learning rate scheduling

Full evaluation pipeline with:

Precision, Recall, AUC

Confusion matrices

ROC curves

PR curves

Per-class metrics

Real-time autotest evaluation

Dataset:

We used the KL-based knee osteoarthritis severity dataset (KL grades 0–4).
These labels made it easier to map the original 5 severity levels into the required 3 classes:

KL Grade	Severity Used in This Project
0, 1, 2	Healthy
3	Moderate
4	Severe
Outcome:

The final model achieves high accuracy and balanced performance across all three classes, providing a reliable tool for assisting early arthritis diagnosis.
