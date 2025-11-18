# AI-Generated vs. Human-Created Art Classifier with Explainability
### Deep Learning (CSCI3370) Group Project — Boston College  
**Professor:** [Dr. Yuan Yuan]([https://cs.brown.edu/people/yyuan/](https://yyuanad.github.io/))  

This repository contains our group project for *Deep Learning*, taught by Professor Yuan.  
Our goal is to build a robust classifier that distinguishes AI-generated artwork from human-created artwork using a multimodal feature-extraction pipeline combining **OpenAI CLIP** and the **Stable Diffusion Turbo VAE**. We also apply class-specific [img2img](https://github.com/GaParmar/img2img-turbo) augmentations to strengthen stylistic robustness and improve generalization.

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

### **How to Run**
1. Install dependencies  
2. Prepare dataset (original + augmented)  
3. Extract CLIP + VAE embeddings  
4. Train classifier  

---

### **Team**
Xiaoyin Liu, Josiah Kondo, Tim Hays, and Julie Hohenberg

---

