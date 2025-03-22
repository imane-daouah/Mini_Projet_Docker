📦 Mini-Projet Docker : Conteneurisation d'une Application Flask + PHP

**Description du Projet**
Ce projet consiste à conteneuriser une application composée de :  
-  **Un backend** en Python utilisant **Flask** (API REST).  
-  **Un frontend** en PHP affichant la liste des étudiants récupérée depuis l’API.  

L'objectif est de **déployer l'application avec Docker**, en utilisant **Docker Compose** pour orchestrer les conteneurs.  


⚙️ **Technologies utilisées**  
- **Python 3.8** (Flask, HTTPAuth)  
- **PHP + Apache**  
- **Docker & Docker Compose**  
- **Linux / Windows PowerShell**  

---

## 🔨 **1. Création et test de l'API Flask**  
### 📌 **Étapes réalisées :**  
- Création du `Dockerfile` pour conteneuriser l'API.  
- Construction de l’image et lancement du conteneur.  

![image](https://github.com/user-attachments/assets/90f4cc1e-e8e1-4639-a70e-f5116d15d400)

### 🛠️ **Commandes utilisées :**  
```sh
# Construction de l'image API
docker build -t student_api ./simple_api

# Exécution du conteneur Flask
docker run -d -p 5000:5000 -v $(pwd)/simple_api/student_age.json:/data/student_age.json --name api student_api

# Vérification des logs
docker logs api
```
📸 **Capture d'écran :** Lancement et test du conteneur API avec `curl`.  

---

## 🏗️ **2. Mise en place du site web PHP**  
### 📌 **Étapes réalisées :**  
- Création du fichier `index.php` contenant l’interface utilisateur.  
- Connexion du site web à l'API Flask pour récupérer les données.  
- Ajout des variables d’environnement pour sécuriser la connexion.  

📸 **Capture d'écran :** Interface web avant intégration Docker.  

---

## 🐳 **3. Orchestration avec Docker Compose**  
### 📌 **Objectif :**  
Utiliser `docker-compose.yml` pour **démarrer et connecter les conteneurs** automatiquement.  

### 🛠️ **Commandes utilisées :**  
```sh
# Lancer l'application avec Docker Compose
docker-compose up --build -d

# Vérifier les conteneurs en cours d'exécution
docker ps
```
📸 **Capture d'écran :** Exécution de `docker-compose up` et vérification des conteneurs actifs.  

---

## 📦 **4. Déploiement du Docker Registry (Bonus)**  
### 📌 **Objectif :**  
Créer un **registre privé** pour stocker les images Docker localement.  

### 🛠️ **Commandes utilisées :**  
```sh
# Lancer le registre privé Docker
docker run -d -p 5001:5000 --name registry registry:2

# Tagger l'image et l'envoyer au registre privé
docker tag student_api localhost:5001/student_api
docker push localhost:5001/student_api

# Vérifier les images dans le registre
curl http://localhost:5001/v2/_catalog
```
📸 **Capture d'écran :** Affichage du registre Docker avec les images stockées.  

---

## ✅ **5. Tests finaux et validation**  
- 📌 **Tester l'API dans le navigateur :** `http://localhost:5000/supmit/api/v1.0/get_student_ages`  
- 📌 **Accéder au site web :** `http://localhost:8080`  
📸 **Capture d'écran :** Liste des étudiants affichée sur le site web.  

---

## 🚀 **6. Conclusion et améliorations possibles**  
📌 **Améliorations possibles :**  
- 🔐 **Sécuriser l’API avec JWT** plutôt qu’une authentification basique.  
- 🗄️ **Utiliser une base de données (MySQL/PostgreSQL)** au lieu du fichier JSON.  
- 🌍 **Déployer sur un serveur Cloud (AWS, GCP, Azure).**  

---

## 🔗 **7. Lien du Dépôt GitHub/GitLab**  
📌 **Lien vers le projet :** [Ajoute ici ton lien GitHub/GitLab]  

---

## 🎯 **8. Fichiers fournis dans ce dépôt**  
✅ `Dockerfile` (API Flask)  
✅ `docker-compose.yml`  
✅ `student_age.py` (API Python)  
✅ `index.php` (Frontend PHP)  
✅ `README.md` (Documentation complète)  

---

**👨‍💻 Réalisé par :**  
🔹 **Nom :** Imane Daouah, Isamil Damouh, Imane Bouhabba  
🔹 **Email :** imane.daouah@gmail.com  
🔹 **Date :** [Ajoute la date]

