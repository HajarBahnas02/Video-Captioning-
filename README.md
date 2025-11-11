# 🎥 Video Captioning – Application de Description Automatique de Vidéos

## 📄 Présentation du projet
Ce projet a pour objectif de développer un système capable de **comprendre et décrire automatiquement une vidéo**, en combinant l’analyse **audio (Whisper)** et **visuelle (LLaVA)**.

L’application extrait la bande sonore pour la transcrire, analyse les images pour identifier le contexte visuel, puis fusionne les deux résultats pour produire un **résumé audio-visuel cohérent**.

---

##  Objectif principal
- Transcrire le contenu audio d’une vidéo à l’aide de **Whisper (OpenAI)**.  
- Analyser les images extraites de la vidéo via **LLaVA (Large Language and Vision Assistant)**.  
- Générer une **description multimodale cohérente et contextuelle** combinant audio et visuel.  
- Fournir une **API REST** utilisable par une application web.

---

##  Évolution des approches utilisées
| Étape | Modèles utilisés | Résultats |
|-------|------------------|------------|
| 1️⃣ | **Whisper + GPT** | Bonne transcription, mais descriptions hors contexte |
| 2️⃣ | **BLIP-2 + Whisper** | Cohérence limitée entre audio et image |
| 3️⃣ | **LLaVA + Whisper** | Résultats précis, descriptions cohérentes et contextualisées |

---

## ⚙️ Technologies utilisées
- **Backend :** FastAPI  
- **Transcription audio :** Whisper (OpenAI)  
- **Analyse visuelle :** LLaVA (LLaMA + Vision Adapter)  
- **Traitement vidéo :** FFmpeg  
- **Bibliothèques Python :** `torch`, `transformers`, `PIL`, `subprocess`  
- **Hébergement / Environnement :** Google Colab + ngrok  

---

## 🧩 Architecture fonctionnelle
1. 📤 L’utilisateur charge une vidéo.  
2. 🎧 L’audio est extrait et transcrit avec **Whisper**.  
3. 🖼️ Des frames sont extraites toutes les 2 secondes avec **FFmpeg**.  
4. 🧩 Les frames sont analysées avec **LLaVA** pour générer des descriptions d’images.  
5. 🧠 Fusion des informations audio et visuelles pour générer une **description globale**.  
6. 🌐 Les résultats sont renvoyés via une **API FastAPI**.

---

## 🧱 Structure du projet
