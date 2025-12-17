# AI-Generated vs. Human-Created Art Classifier with Explainability
### Deep Learning (CSCI3370) Group Project — Boston College  
**Professor:** [Dr. Yuan Yuan](https://yyuanad.github.io/) 

> **Project Status: In Progress**  
> This repository is actively being developed and updated.

This repository contains our group project for *Deep Learning*, taught by Professor Yuan.  
Our goal is to build a robust classifier that distinguishes AI-generated artwork from human-created artwork using a multimodal feature-extraction pipeline combining [**OpenAI CLIP**](https://arxiv.org/abs/2103.00020) and the **Stable Diffusion Turbo VAE**. We also apply class-specific [img2img](https://github.com/GaParmar/img2img-turbo) augmentations to strengthen stylistic robustness and improve generalization.

Our work was partially inspired by [Castellano et al.’s](https://arxiv.org/abs/2103.00020) exploration of AI-generated art classification and their emphasis on improving model explainability using Grad-CAM and multimodal LLMs. Their study highlights the difficulty in distinguishing synthetic from human-made artwork and the importance of visual cues. We build on this motivation and focus on developing a more robust feature-extraction pipeline that leverages additional preprocessing from CLIP and Stable Diffusion VAE representations.

---

### **Dataset**
Our dataset comes from the [Kaggle AI vs. Human Art Classification dataset](https://www.kaggle.com/datasets/doctorstrange420/real-and-fake-ai-generated-art-images-dataset). The dataset contains two labeled categories: AI-generated artwork produced by diffusion models or other AI systems, and non-AI-generated (human-generated) photographs, paintings, and traditional art scraped from WikiArt. Each category contains 10,821 images. The dataset provides a diverse set of subjects, textures, and artistic styles. The raw dataset is downloaded directly via the Kaggle API and stored locally.

---

### **Project Highlights**
- CLIP ViT-B/32 semantic embeddings  
- Stable Diffusion Turbo VAE latent texture embeddings  
- Fused 768-dimensional feature representations  
- Class-specific img2img augmentations using SD-Turbo  
- MLP classifier with strong performance on held-out test data   

---
## **Repository Structure**

### `notebooks/`
All experimental, training, inference, and explainability work is contained in the `notebooks/` directory:

- **`ResNet_finetuned.ipynb`**  
  Fine-tuned ResNet benchmark model for AI vs. human art classification.

- **`Tim_LLM_final.ipynb`**  
  LLM-based textual explainability pipeline for classifier predictions.

- **`classifier_inference_final.ipynb`**  
  Final inference notebook used to evaluate the classifier on the Beatles images and Tim’s childhood artwork.

- **`img2img_clip_mlp_final.ipynb`**  
  End-to-end pipeline including img2img augmentation, CLIP feature extraction, feature fusion, and MLP classification.

---

## **Repository Structure**

### `notebooks/`
All experimental, training, inference, and explainability work is contained in the `notebooks/` directory:

- **`ResNet_finetuned.ipynb`**  
  Fine-tuned ResNet benchmark model for AI vs. human art classification.

- **`img2img_clip_mlp_final.ipynb`**  
  End-to-end pipeline including img2img augmentation, CLIP feature extraction, feature fusion, MLP classification, and visual explainability.

- **`Tim_LLM_final.ipynb`**  
  LLM-based textual explainability pipeline for classifier predictions.

- **`classifier_inference_final.ipynb`**  
  Final inference notebook used to evaluate the classifier on the Beatles images and Tim’s childhood artwork.

---

## **External Results & Artifacts**

- **img2img Augmentation Results (AI & Non-AI)**  
  Visual outputs from class-specific Stable Diffusion Turbo img2img augmentations:  
  https://drive.google.com/drive/folders/1RHqQRoOv3Y_Z4iaCfkKvcec6Q1RKO1ty?usp=sharing

- **Saved Classifier Models**  
  Trained MLP and benchmark model checkpoints:  
  https://drive.google.com/drive/folders/14ZK3vldCWk_nLoaTcjqub5owA-ZNqgtz?usp=sharing

- **Childhood Artwork Evaluation Dataset (Tim Hays)**  
  Independent evaluation set consisting of real childhood artwork created by **Tim Hays (author)** and AI-generated images produced using **Gemini Nano Banana**:  
  https://drive.google.com/drive/folders/1eNAi9rbSuIrqLiqtpi0qWF9vcLhLmttZ?usp=drive_link

- **Full LLM Text Explainability Results**  
  Google Sheets containing all model-generated explanations and annotations:  
  https://docs.google.com/spreadsheets/d/1ndK6W_tVSY7-Q02GdzTKe0UyhRFGvhrS2AC3KjYYV_E/edit?usp=sharing
  
---

### **Team**
Xiaoyin Liu, Josiah Kondo, Tim Hays, and Julie Hohenberg

---

