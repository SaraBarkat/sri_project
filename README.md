# SRI Project – Agent IA avec LangChain, Groq et Django

## Présentation du Projet

Ce projet est une application web développée avec **Django** intégrant un **agent d’intelligence artificielle** basé sur **LangChain** et le modèle **Groq (LLaMA 3)**.  
Il permet d’analyser un profil client et de fournir une **recommandation intelligente, structurée et fiable**, avec une logique **Human-In-The-Loop (HITL)** basée sur un score de confiance.

Le projet met en œuvre une architecture **modulaire et moderne**, adaptée aux systèmes LLM en production.

---

## Fonctionnalités

- Agent IA basé sur **LangChain (LCEL)**
- Modèle **Groq – LLaMA 3**
- Sorties structurées et validées avec **Pydantic**
- API REST via **Django Rest Framework**
- Interface Web simple
- Gestion sécurisée des clés API avec `.env`
- Logique **Human-In-The-Loop (HITL)**

---

## Architecture

Utilisateur
↓
Interface Web / API REST
↓
Agent LangChain (Prompt | LLM | Parser)
↓
Groq LLM (LLaMA 3)
↓
Réponse JSON Structurée

---

## Structure du Projet
```
sri_project/
├── manage.py
├── .env
├── requirements.txt
├── db.sqlite3
├── sri_project/
│ ├── settings.py
│ ├── urls.py
│ └── wsgi.py
├── agent_service/
│ ├── groq_agent.py
│ ├── views.py
│ ├── urls.py
│ ├── serializers.py
│ └── templates/
│ └── agent_service/
│ ├── form.html
│ └── result.html
└── venv/
```

---


## Prérequis

- Python 3.8 ou plus
- pip
- Clé API Groq

---

## Lancer le projet

```bash
git clone https://github.com/SaraBarkat/sri_project.git
cd sri_project
python -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt
GROQ_API_KEY=gsk_votre_cle_api_ici
python manage.py migrate
python manage.py runserver
```

Accéder à l’application

Interface Web :
http://127.0.0.1:8000/api/

Via postman : 
http://127.0.0.1:8000/api/analyze/
