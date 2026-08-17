## Architecture globale du projet

```mermaid
flowchart LR
    subgraph Frontend
        A[React + Vite]
    end

    subgraph Backend
        B[FastAPI]
    end

    subgraph Database
        C[(PostgreSQL)]
    end

    A --> B
    B --> C
```

## 2. Architecture Docker

```mermaid
flowchart TD
    subgraph Docker
        F[Frontend Container]
        B[Backend Container]
        D[(PostgreSQL Container)]
    end

    F --> B
    B --> D
```

## Pipeline CI/CD GitHub Actions
```mermaid
flowchart TD
    A[Push sur GitHub] --> B[GitHub Actions]
    B --> C[Build Backend Dockerfile]
    B --> D[Build Frontend Dockerfile]
    C --> E[Backend Image]
    D --> F[Frontend Image]
    E --> G[Docker Compose]
    F --> G[Docker Compose]
    G --> H[Backend Container]
    G --> I[Frontend Container]
    G --> J[PostgreSQL Container]

```
## 7. Structure du dépôt
h4ckr-devops/
│
├── backend/
│   ├── Dockerfile
│   ├── main.py
│   ├── requirements.txt
│   └── ...
│
├── frontend/
│   ├── Dockerfile
│   ├── package.json
│   ├── src/
│   └── ...
│
├── docker-compose.yml
│
├── .github/
│   └── workflows/
│       └── ci-cd.yml
│
├── screenshots/
│
└── README.md


## Objectif DevOps
Ce dépôt a pour but de :

Centraliser l’architecture complète du projet

Montrer une pipeline CI/CD fonctionnelle

Illustrer une stack full DevOps

Monter en compétences

## À propos de l’auteure

Jenet  

Étudiante Bac+2 Informatique – Réseaux & Cybersécurité
Préparation Bac+3 en alternance (Administrateur LAN / DevOps)
Passionnée par :

les architectures réseau

la cybersécurité

le DevOps

les pipelines CI/CD

Docker & FastAPI

les projets techniques concrets