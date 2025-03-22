📦 Mini-Projet Docker : Conteneurisation d'une Application Flask + PHP

📌 Étape I : Construire (build) et tester l'API 
Dans cette partie, nous allons construire et tester l’API Flask en suivant plusieurs étapes.
 _ Choix de l’image de base
 
✅ Objectif :
Nous avons utilisé l’image python:3.8-buster comme base pour notre conteneur.
 _ Ajout des informations du mainteneur
 
✅ Objectif :
Nous avons ajouté notre nom et email dans le Dockerfile avec LABEL maintainer.

![image](https://github.com/user-attachments/assets/4ba07cee-5e44-4af9-9e11-721ebe9cb969)

_ Exposition du port 5000

✅ Objectif :
Nous avons configuré le conteneur pour exposer le port 5000 afin d’accéder à l’API Flask.
_ Construction et lancement de l’image Docker 

✅ Objectif :
Nous avons construit l’image avec la commande :
docker build -t student_api .

![Capture d'écran 2025-03-21 112826](https://github.com/user-attachments/assets/52e33dca-809c-4e20-be69-97d81463ddf1)
Puis, nous avons lancé un conteneur avec :
docker run -d -p 5000:5000 -v $(pwd)/student_age.json:/data/student_age.json --name api student_api
![Capture d'écran 2025-03-21 113448](https://github.com/user-attachments/assets/b0824b76-d22b-425e-8704-30673f9f67a6)
![Capture d'écran 2025-03-21 113833](https://github.com/user-attachments/assets/c92c3a03-5922-4da6-8575-c6253cb06e0f)


✅ Objectif :
Nous avons testé l’API en appelant :
curl -u root:root -X GET http://localhost:5000/supmit/api/v1.0/get_student_ages
![Capture d'écran 2025-03-21 114613](https://github.com/user-attachments/assets/8cbe828c-3184-4421-93e6-f6c292309c1c)


📌 Étape II : Infrastructure as Code (5 points)
Dans cette étape, nous allons automatiser le déploiement de l’API et du site web PHP en utilisant Docker Compose. 🚀

_ Création du fichier docker-compose.yml

✅ Objectif :

Nous avons créé le fichier docker-compose.yml qui définit les services API et Website.

![image](https://github.com/user-attachments/assets/216c54b1-c9fb-4cdf-91bc-53aeb06be968)

Affichage du code docker-compose.yml montrant la configuration du service api.
_ Lancer Docker Compose

✅ Objectif :

Nous avons lancé l’application en une seule commande :
docker-compose up --build -d

![Capture d'écran 2025-03-21 120816](https://github.com/user-attachments/assets/f76195b1-e7b1-4866-98bb-ea6139![Capture d'écran 2025-03-21 120835](https://github.com/user-attachments/assets/9969750b-6196-4b75-b9fe-864819cacdca)
824bf8)
![Capture d'écran 2025-03-21 120846](https://github.com/user-attachments/assets/1a274f91-07ee-4d5d-8a80-9a5e146b4112)
![Capture d'écran 2025-03-21 120930](https://github.com/user-attachments/assets/1bcb483b-71e0-4a28-b63e-656d3852e5a6)
![Capture d'écran 2025-03-21 121055](https://github.com/user-attachments/assets/94fdfcbc-fdd7-4536-a2a4-604ae8905533)

![Capture d'écran 2025-03-21 121122](https://github.com/user-attachments/assets/5e6356a9-16f3-495e-876f-304044a00af8)


_ Tester l’application

✅ Objectif :

Nous avons accédé au site web via http://localhost:8080 et cliqué sur "List Student" pour vérifier que l’API fonctionne.
![Capture d'écran 2025-03-21 122255](https://github.com/user-attachments/assets/77860423-9e82-40d0-a54e-e962394b0cc3)
![Capture d'écran 2025-03-21 122304](https://github.com/user-attachments/assets/4116a872-aa27-466a-bb2a-4c6dde2b937e)

Affichage du site web avec la liste des étudiants.

📌Étape III : Déploiement du Docker Registry 
Dans cette étape, nous allons créer un registre privé Docker pour stocker les images localement et les gérer via une interface web. 🚀

_ Lancer le registre privé Docker

✅ Objectif :

Nous avons démarré un registre privé local pour stocker nos images Docker.
docker run -d -p 5001:5000 --name registry registry:2

![image](https://github.com/user-attachments/assets/a056bce5-f84d-448a-b17c-3b722c4245e6)
![Capture d'écran 2025-03-21 124731](https://github.com/user-attachments/assets/5d60e269-08a5-4fea-a588-3ca755bd3b5b)
![Capture d'écran 2025-03-21 125124](https://github.com/user-attachments/assets/724bd8b7-df6d-46d4-baef-d14105f932d3)


_ Vérifier le registre privé 

✅ Objectif :

Nous avons vérifié si le registre privé fonctionne bien avec :
_ Tagger l’image et l’envoyer au registre privé
docker push localhost:5001/student_api
![Capture d'écran 2025-03-21 125124](https://github.com/user-attachments/assets/21af6588-82f5-4a96-970e-68e987fa0506)

_ Déployer une interface Web pour voir le registre

✅ Objectif :
Nous avons lancé une interface web pour gérer les images Docker avec :

![Capture d'écran 2025-03-21 125255](https://github.com/user-attachments/assets/4369e600-db46-41cf-9096-367b552f4a74)



