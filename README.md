# AI-Generated vs. Human-Created Art Classifier with Explainability
### Deep Learning (CSCI3370) Group Project — Boston College, Fall 2025  
**Professor:** [Dr. Yuan Yuan](https://yyuanad.github.io/) 

**Student Team:** Xiaoyin Liu, Josiah Kondo, Tim Hays, and Julie Hohenberg

This repository contains our group project for *Deep Learning*, taught by Professor Yuan.  
Our goal is to build a robust classifier that distinguishes AI-generated artwork from human-created artwork using a multimodal feature-extraction pipeline combining [**OpenAI CLIP**](https://arxiv.org/abs/2103.00020) and the **Stable Diffusion Turbo VAE**. We also apply class-specific [img2img](https://github.com/GaParmar/img2img-turbo) augmentations to strengthen stylistic robustness and improve generalization. In addition to benchmark classification performance, the project emphasizes interpretability. We provide visual explanations using Grad-CAM and occlusion-based saliency, and generate natural-language explanations grounded in latent feature activations using large language models.

Our work was partially inspired by [Castellano et al.’s](https://arxiv.org/abs/2103.00020) exploration of AI-generated art classification and their emphasis on improving model explainability using Grad-CAM and multimodal LLMs. Their study highlights the difficulty in distinguishing synthetic from human-made artwork and the importance of visual cues. We build on this motivation and focus on developing a more robust feature-extraction pipeline that leverages additional preprocessing from CLIP and Stable Diffusion VAE representations.

---

## Datasets

### Benchmark Dataset
Our primary dataset is the [Kaggle AI vs. Human Art Classification dataset](https://www.kaggle.com/datasets/doctorstrange420/real-and-fake-ai-generated-art-images-dataset). It contains two balanced classes: AI-generated artwork produced by diffusion models or other generative systems, and non-AI-generated (human-created) photographs, paintings, and traditional artwork scraped from WikiArt. Each class contains 10,821 images, spanning a wide range of subjects, textures, and artistic styles. The dataset is used for supervised training, validation, and benchmark evaluation. Raw images are downloaded directly via the Kaggle API and stored locally.

### Out-of-Distribution Dataset (Childhood Artwork)
In addition to the benchmark dataset, we evaluate the strongest-performing classifier on a small, out-of-distribution dataset consisting of childhood artwork created by one author (Tim Hays) and AI-generated images produced using Gemini’s Nano Banana model. This dataset is **not used during training** and is intended to probe model generalization and explainability under asymmetric distribution shift. While the AI-generated images may partially overlap with the distribution of generative models seen during training, the human-created childhood artwork is substantially out-of-distribution relative to the Kaggle benchmark. This dataset is used exclusively for robustness analysis, explainability experiments, and qualitative comparison against general-purpose multimodal and language models. The dataset can be viewed [here](https://drive.google.com/drive/folders/1eNAi9rbSuIrqLiqtpi0qWF9vcLhLmttZ?usp=drive_link).

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

- **Full LLM Text Explainability Results**  
  Google Sheets containing all model-generated explanations and annotations:  
  https://docs.google.com/spreadsheets/d/1ndK6W_tVSY7-Q02GdzTKe0UyhRFGvhrS2AC3KjYYV_E/edit?usp=sharing
  
---

