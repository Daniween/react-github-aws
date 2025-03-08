# 🚀 Déploiement d'une Application React sur EC2 avec Docker & GitHub Actions

Ceci est une application **React** déployée automatiquement sur **Amazon EC2** en utilisant **Docker** et **GitHub Actions**.

---

## 📌 Prérequis  

Avant de commencer, assurez-vous d'avoir installé :  

- [Node.js](https://nodejs.org/) (version 18 ou supérieure)  
- [Docker](https://www.docker.com/)  
- [Docker Compose](https://docs.docker.com/compose/)  
- Un serveur **EC2** configuré avec **Docker** et **GitHub Actions** (SSH)  

---

## 🔑 Configuration des Secrets GitHub

Pour que **GitHub Actions** puisse se connecter à votre serveur **EC2**, ajoutez ces **secrets** dans votre dépôt :

| Secret            | Description                                      |
|------------------|--------------------------------------------------|
| `SSH_PRIVATE_KEY` | Clé privée SSH pour se connecter au serveur EC2 |
| `SSH_HOST`       | Adresse IP/Domaine du serveur EC2               |
| `SSH_USER`       | Nom d'utilisateur SSH (ex: `ubuntu`)            |
| `WORK_DIR`       | Répertoire de travail sur le serveur            |
| `MAIN_BRANCH`    | Branche principale (`main`)                     |

Vous pouvez configurer ces **secrets** dans **GitHub** :
1. Allez dans **Settings** → **Secrets and variables** → **Actions**.
2. Cliquez sur **New repository secret** et ajoutez chaque secret ci-dessus.

---

## 📂 Arborescence du projet

L'arborescence du projet est la suivante :

| Fichier          | Description |
|------------------|--------------------------------------------------|
| .github/workflows/ | Contient les fichiers GitHub Actions |
| public/ | Fichiers statiques publics |
| src/ | Code source de l'application React |
| .gitignore | Fichier pour ignorer certains fichiers dans Git |
| Dockerfile | Conteneurisation avec Docker |
| README.md | Documentation du projet |
| docker-compose.yml | Configuration pour Docker Compose |

---

## 🛠 Installation et exécution locale  

### 1️⃣ Cloner le dépôt  
```bash
git clone https://github.com/daniween/react-github-aws.git
cd react-github-aws
npm start
