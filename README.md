Here's a structured README based on the provided project description and Jupyter Notebook:

* * *

Plant Disease Classification and Explainability Using Deep Learning
===================================================================

Overview
--------

This project explores the use of machine learning and explainable AI techniques to classify plant diseases from images and understand the visual patterns associated with different conditions. Using a **pretrained VGG-16 neural network**, we classify images of **healthy** and **black rot-infected apple leaves** from the **Plant Disease Dataset**. Beyond classification, we apply **sensitivity analysis** and **robust gradient-based methods** to highlight image regions that contribute to model predictions, offering insights into disease markers.

Dataset
-------

**Plant Disease Dataset**:

*   **Source**: [Mendeley Data](https://data.mendeley.com/datasets/tywbtsjrjv/1)
*   **Subset Used**:
    *   **Classes**:
        *   _apple-healthy_
        *   _apple-black-rot_
    *   **Sample Size**: 100 images per class (for computational efficiency).
*   **Metadata**: Each image is labeled with plant type, disease presence, and disease type.

Project Structure
-----------------

1.  **Image Feature Extraction**
    
    *   **Pretrained VGG-16 Network** (without batch normalization) is used for feature extraction.
    *   The top layers of the network are removed to retain general features.
    *   The extracted features are denoted as **Φ(x)**.
2.  **Classification Model**
    
    *   A **difference-of-means discriminant** is used to separate classes in the feature space.
    *   Performance is evaluated using **Area Under the ROC Curve (AUC)**.
3.  **Explainability Techniques**
    
    *   **Sensitivity Analysis**: Highlights image regions contributing to predictions using gradients.
    *   **Robust Gradient-Based Explanations**: Modified gradients reduce noise in explanations, focusing on relevant features.
4.  **Experiments**
    
    *   Evaluate the discriminant’s performance on a disjoint test set.
    *   Compare the effectiveness of standard sensitivity analysis with robustified explanations.
    *   Discuss mismatches between highlighted regions and actual disease-affected areas.

Setup Instructions
------------------

1.  **Clone the repository:**
    
    ```bash
    git clone <repository_url>
    cd <repository_folder>
    ```
    
2.  **Install dependencies:**
    
    ```bash
    pip install -r requirements.txt
    ```
    
3.  **Download the Plant Disease Dataset:**
    
    *   Download from [here](https://data.mendeley.com/datasets/tywbtsjrjv/1) and place the relevant images in the project directory.
4.  **Run the notebook:**
    
    ```bash
    jupyter notebook projectThree.ipynb
    ```
    

Key Results
-----------

*   **Classification**: The difference-of-means model achieved high AUC scores, effectively distinguishing between healthy and diseased leaves.
*   **Explainability**:
    *   Sensitivity analysis identified key visual patterns but was prone to noise.
    *   Robust gradient modifications improved explanation clarity, focusing on disease-relevant regions.

Visualizations
--------------

*   **Class Discriminant Scores**: Visualization of how well the model separates healthy and diseased leaves.
*   **Heatmaps**:
    *   Sensitivity maps show pixel importance for predictions.
    *   Robustified heatmaps provide clearer insights into disease-affected regions.

Challenges & Discussion
-----------------------

*   Some highlighted regions didn’t perfectly align with visible disease areas.
*   Possible issues:
    *   Pretrained model limitations (trained on ImageNet, not plant-specific data).
    *   Sensitivity to data artifacts or imbalanced sample sizes.
    *   Variability in disease presentation in images.

**Future Improvements**:

*   Fine-tune VGG-16 on a larger, plant-specific dataset.
*   Explore alternative explainability techniques like **Grad-CAM** or **Layer-wise Relevance Propagation (LRP)**.
*   Increase dataset size and diversity to improve generalization.

References
----------

*   [Plant Disease Dataset on Mendeley](https://data.mendeley.com/datasets/tywbtsjrjv/1)
*   [VGG\-16 Model Documentation (PyTorch)](https://pytorch.org/vision/stable/models.html)

* * *

Let me know if you'd like any modifications!