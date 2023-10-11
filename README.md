# Damage_Detector_Swin

Project Description
-------------------
This project is based on Swin Transformer (Swin-S) model for house damage detection. By training the model, we can predict the extent of damage in the house pictures and use Grad-CAM to visualize the region of attention of the model.

Project Settings and Dependencies
---------------------------------
Make sure your environment meets the following requirements:
Python 3.x
PyTorch (make sure CUDA is supported, if using a GPU)
OpenCV
PIL
Other relevant libraries and dependencies
pip install -r requirements.txt

Model Overview: Swin Transformer
-------------------------------
The Swin Transformer is a novel self-attention neural network designed for computer vision tasks. Distinct from traditional Transformer architectures, the Swin Transformer employs fixed-size windows to perform self-attention computations, significantly reducing computational complexity.
![image](https://github.com/Alen-Xue/Damage_Detector_Swin/assets/126217366/d6abe4b9-143c-4d68-ae88-9ff6f7817e5a)

Window-based Self-Attention
--------------------------
A key innovation of the Swin Transformer is its window-based self-attention mechanism. The input image is divided into multiple fixed-size windows, and self-attention is computed within each window. This approach effectively captures local information instead of global contexts. Furthermore, through cyclically shifting and overlapping these windows, the model can also grasp a broader contextual understanding.
![image](https://github.com/Alen-Xue/Damage_Detector_Swin/assets/126217366/38c8ba67-11ca-4be5-9a5a-4958adc088ff)

Hierarchical Representation
--------------------------
The Swin Transformer adopts a multi-layered structure, with each layer corresponding to a different resolution. This design allows it to capture features at multiple scales.
![image](https://github.com/Alen-Xue/Damage_Detector_Swin/assets/126217366/9c003db4-5505-4f74-9021-abdfb5abff18)


Model Parameters and Settings
----------------------------
Model Variant: Swin-S
Input Size: 224x224
Number of Output Classes: 3 (representing different damage levels)
Cross-Training Mode
In this project, we utilize a cross-training mode to train our Swin Transformer model. This training approach can effectively prevent overfitting while enhancing the model's generalization capabilities.

Method Description
------------------
The entire dataset is divided into k subsets. Each subset takes turns acting as the test set, while the remaining subsets serve as the training set. Through this method, we ensure that every data point gets utilized for both training and testing. Ultimately, we average the results of the k experiments to obtain the final evaluation metrics.

Settings and Parameters
-----------------------
k-value: 5 (i.e., 5-fold cross-validation)
Optimizer: Adam
Learning Rate Strategy: CosineAnnealingLR
Loss Function: CrossEntropyLoss

![Test1](https://github.com/Alen-Xue/Damage_Detector_Swin/assets/126217366/0fd7f7e3-f35c-40ff-8b3a-a6599706e859)
![Test4](https://github.com/Alen-Xue/Damage_Detector_Swin/assets/126217366/a419aa73-5a2e-422a-b257-7c2387bee957)
![Test6](https://github.com/Alen-Xue/Damage_Detector_Swin/assets/126217366/d60ecdc4-04b2-4676-8fc2-ae09031b9cb9)
