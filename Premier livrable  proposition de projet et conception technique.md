# 🏠 Home Staging Virtuel par Deep Learning
### Projet – Computer Vision & Modèles Génératifs

## 📌 Présentation du projet
Dans le secteur de l’immobilier, la qualité visuelle des annonces joue un rôle déterminant dans
l’attraction des acheteurs et des locataires. Cependant, de nombreux biens sont présentés avec
des pièces vides ou mal aménagées, ce qui rend difficile la projection des clients.

Ce projet vise à concevoir un **système de Home Staging Virtuel basé sur le Deep Learning**,
capable de transformer des images d’intérieurs vides ou peu meublés en **images réalistes et
esthétiques**, tout en conservant la structure originale de la pièce.

---

## ❓ Problématique
- Les photos de biens vides diminuent l’engagement des clients.
- Le home staging traditionnel est coûteux, lent et peu scalable.

**Problème central :**  
Comment générer automatiquement des images d’intérieurs réalistes et attractives à partir
d’images réelles, tout en respectant la structure de la pièce et le style décoratif souhaité ?

---

## 💡 Solution proposée
Nous proposons une **plateforme de Home Staging Virtuel basée sur l’IA** qui :
- Prend en entrée une image d’une pièce (chambre, salon, etc.).
- Analyse automatiquement les objets et la structure de la pièce.
- Préserve la disposition spatiale (murs, sol, fenêtres, portes).
- Génère du mobilier et une décoration réalistes à l’aide de **modèles génératifs**.
- Permet le conditionnement par **style de décoration** (moderne, classique, rustique…).
- Produit des images finales adaptées aux annonces immobilières.

---

## 🧠 Approche technique

### 1. Computer Vision – Détection et Segmentation
- **Détection d’objets par YOLO (You Only Look Once) exmple** :
  - Fine-tuning d’un modèle YOLO pré-entraîné (YOLOv8/YOLOv5) pour détecter :
    - lits, canapés, tables, chaises, fenêtres, portes, etc.
  - Analyse de l’occupation de l’espace et des zones libres.
- **Segmentation sémantique** des éléments structurels à l’aide de **U-Net / DeepLab**.
- Objectif : garantir la cohérence spatiale entre l’image originale et l’image générée.

### 2. Modèles génératifs
- Utilisation de **GANs conditionnels** ou de **modèles de diffusion**.
- Génération d’images réalistes conditionnées par :
  - le type de pièce,
  - la structure détectée,
  - le style de décoration souhaité.
- Intégration des informations issues de YOLO et de la segmentation pour guider la génération.

### 3. Évaluation
Les performances du système seront évaluées de manière quantitative et qualitative à l’aide de :
- **FID (Fréchet Inception Distance)** : réalisme et qualité globale des images générées.
- **SSIM (Structural Similarity Index)** : préservation de la structure spatiale.
- **LPIPS (Learned Perceptual Image Patch Similarity)** : similarité perceptuelle entre images.

---

## 📊 Jeux de données utilisés
Le projet s’appuie sur plusieurs datasets open-source complémentaires :

- **LSUN Bedroom Dataset**  
  Images réalistes de chambres pour l’entraînement des modèles génératifs.  
  https://www.kaggle.com/datasets/jhoward/lsun_bedroom

- **ADE20K Dataset**  
  Images et masques de segmentation pour les scènes intérieures.  
  https://www.kaggle.com/datasets/soumikrakshit/ade20k

- **Interior Design Styles Dataset**  
  Images d’intérieurs classées par style de décoration.  
  https://www.kaggle.com/datasets/stepanyarullin/interior-design-styles

- **House Rooms Dataset**  
  Classification des types de pièces (chambre, salon, cuisine…).  
  https://www.kaggle.com/datasets/annielu21/house-rooms

---

## 🧪 Suivi expérimental et déploiement
- **MLflow** pour le suivi des expériences et la traçabilité des modèles.
- **Docker** pour la conteneurisation et la reproductibilité.
- **FastAPI** pour exposer les modèles sous forme d’API.
- **Interface web (NestJS)** pour la démonstration et l’interaction utilisateur.

---

## ⚙️ Stack technologique
- **Langage** : Python  
- **Deep Learning** : PyTorch  
- **Computer Vision** : OpenCV, Albumentations  
- **Détection d’objets** : YOLO (fine-tuning)  
- **Modèles génératifs** : GANs / Modèles de diffusion  
- **Suivi expérimental** : MLflow  
- **API backend** : FastAPI  
- **Frontend** : NestJS  
- **Conteneurisation** : Docker  
- **Environnement d’entraînement** : Kaggle / Google Colab (version gratuite)