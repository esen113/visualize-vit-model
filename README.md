## Overview
This project started as an attempt to **build a Vision Transformer (ViT) from scratch**. However, after realizing the computational limitations of training a ViT from scratch, I decided to leverage a **pretrained ViT model** to perform a simple **flower classification task** and visualize its attention maps.

## Project Goals
- **Train a Vision Transformer on a flower classification dataset**
- **Visualize attention scores from different layers**
- **Analyze how the model attends to different parts of the image**
- **Investigate the effect of dataset background on attention distribution**

## Key Findings
1. **Attention Distribution**  
   - Among the **12 attention layers**, only **layers 1 and 2** showed significant focus on the flower itself.
   - The **higher layers did not strongly attend to the object (flower)**, suggesting that the task is **too simple** for the ViT model.
   - The model might **not require many attention heads** to achieve high classification accuracy.

2. **Dataset Influence**  
   - Some classes of flowers had **very similar backgrounds**, making it harder to distinguish them purely based on object attention.
   - The model might be leveraging **background information** instead of focusing solely on the flower.

3. **Classification Performance**  
   - The **F1 score for all classes exceeded 90%**, indicating that the ViT model performs well on this task.
   - However, the attention visualization suggests that **many layers are not crucial for solving this classification problem**.

## Implementation Details
- Used **pretrained ViT model** from `timm` library.
- Dataset: **Flower classification dataset** (custom dataset with labeled flower images).
- Visualized attention using **attention score heatmaps** from different transformer layers.

## Next Steps
- Experiment with **more complex datasets** where background information is less correlated with class labels.
- Explore **fine-tuning** the pretrained model on a **more diverse dataset** to see if attention distribution changes.

  
