# AI Travel Agent — Agentic RAG + MCP

Projet NLP 2026 — Assistant de planification de voyage intelligent  
**Auteurs :** Francesco ORSI

## Description

Agent de voyage intelligent qui génère des itinéraires complets à partir d'un budget, 
une ville de départ, des dates et des centres d'intérêt.

**Pipeline complet :**
1. Recherche de destinations avec prix de vols réels
2. Itinéraire détaillé jour par jour (vols, hôtels, activités, météo)
3. Carte interactive des lieux à visiter
4. Chatbot pour affiner le voyage

## Architecture

- **LangGraph + Llama 3.3-70b (Groq)** — Agent ReAct pour l'orchestration
- **RAG automatisé** — Scraping Wikipedia + base vectorielle FAISS
- **Serveur MCP** — Exposition des outils à l'agent
- **APIs externes** — Amadeus (vols), SerpApi (hôtels), OpenWeather (météo)
- **Interface** — Gradio + Folium (carte interactive)

## Prérequis

Les clés API suivantes sont nécessaires :
- **Amadeus API** — Client ID & Client Secret
- **Groq API** — clé API
- **OpenWeather API** — clé API
- **SerpApi** — clé API

## Utilisation (Google Colab)

1. Ouvrir `projet_ai_travel_agent.ipynb` dans Google Colab
2. **Exécuter la cellule 1** (installation des dépendances), puis **redémarrer le kernel**
3. Reprendre depuis la cellule 2 et renseigner les clés API
4. Exécuter les cellules suivantes pour initialiser RAG, MCP et l'agent
5. Lancer la dernière cellule pour démarrer l'interface Gradio

### Interface

- **Phase 1** — Renseigner budget, départ, dates, intérêts → 3 destinations proposées
- **Phase 2** — Sélectionner une destination → planning détaillé généré
- **Chatbot** — Affiner l'itinéraire par questions

## Technologies

Python · LangGraph · LangChain · FAISS · Gradio · Folium  
Groq · Amadeus API · SerpApi · OpenWeather API
