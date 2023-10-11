# Damage_Detector_Swin

Project Description
This project is based on Swin Transformer (Swin-S) model for house damage detection. By training the model, we can predict the extent of damage in the house pictures and use Grad-CAM to visualize the region of attention of the model.

Project Settings and Dependencies
Make sure your environment meets the following requirements:
Python 3.x
PyTorch (make sure CUDA is supported, if using a GPU)
OpenCV
PIL
Other relevant libraries and dependencies
pip install -r requirements.txt

Model Overview: Swin Transformer
The Swin Transformer is a novel self-attention neural network designed for computer vision tasks. Distinct from traditional Transformer architectures, the Swin Transformer employs fixed-size windows to perform self-attention computations, significantly reducing computational complexity.

Window-based Self-Attention
A key innovation of the Swin Transformer is its window-based self-attention mechanism. The input image is divided into multiple fixed-size windows, and self-attention is computed within each window. This approach effectively captures local information instead of global contexts. Furthermore, through cyclically shifting and overlapping these windows, the model can also grasp a broader contextual understanding.

Hierarchical Representation
The Swin Transformer adopts a multi-layered structure, with each layer corresponding to a different resolution. This design allows it to capture features at multiple scales.

Model Parameters and Settings
Model Variant: Swin-S
Input Size: 224x224
Number of Output Classes: 3 (representing different damage levels)
Cross-Training Mode
In this project, we utilize a cross-training mode to train our Swin Transformer model. This training approach can effectively prevent overfitting while enhancing the model's generalization capabilities.

Method Description
The entire dataset is divided into k subsets. Each subset takes turns acting as the test set, while the remaining subsets serve as the training set. Through this method, we ensure that every data point gets utilized for both training and testing. Ultimately, we average the results of the k experiments to obtain the final evaluation metrics.

Settings and Parameters
k-value: 5 (i.e., 5-fold cross-validation)
Optimizer: Adam
Learning Rate Strategy: CosineAnnealingLR
Loss Function: CrossEntropyLoss
