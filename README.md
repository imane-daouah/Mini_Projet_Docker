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
# Construction de l'image API
docker build -t student_api ./simple_api

# Exécution du conteneur Flask
docker run -d -p 5000:5000 -v $(pwd)/simple_api/student_age.json:/data/student_age.json --name api student_api

![Capture d'écran 2025-03-21 112826](https://github.com/user-attachments/assets/ecd8799c-4f00-4a83-966c-2039e4f3a8cf)

![Capture d'écran 2025-03-21 113010](https://github.com/user-attachments/assets/974f8437-f751-4138-97af-5a4b85613a10)

![Capture d'écran 2025-03-21 113448](https://github.com/user-attachments/assets/3744dd16-015b-404a-94c5-6271f7aaea4f)
![Capture d'écran 2025-03-21 114731](https://github.com/user-attachments/assets/295d989e-0606-4d8e-84e4-4fe983230082)




## 🏗️ **2. Mise en place du site web PHP**  
### 📌 **Étapes réalisées :**  
![image](https://github.com/user-attachments/assets/4ef13e30-7b01-4514-8f84-bc98383d5ad9)

![Capture d'écran 2025-03-21 120816](https://github.com/user-attachments/assets/0421c319-6af1-42b7-a068-5b338c6e1184)

![Capture d'écran 2025-03-21 120835](https://github.com/user-attachments/assets/4c7fd7fb-f93b-4197-8676-fac5e1fa7ef1)

![Capture d'écran 2025-03-21 120846](https://github.com/user-attachments/assets/1c8af17b-b56c-4e48-b3ef-5e98022e7fa4)

![Capture d'écran 2025-03-21 120930](https://github.com/user-attachments/assets/2f15d6f0-b68b-45b0-96b5-996390ebed53)
![Capture d'écran 2025-03-21 121017](https://github.com/user-attachments/assets/1383f0a5-fb84-4644-9798-6e07900391e1)
![Capture d'écran 2025-03-21 122159](https://github.com/user-attachments/assets/314c5ca8-ea9d-4550-82d2-033d1d078976)

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





**👨‍💻 Réalisé par :**  
**Nom :** Imane Daouah, Isamil Damouh, Imane Bouhabba  

