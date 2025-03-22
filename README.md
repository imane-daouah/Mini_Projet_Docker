📦 Mini-Projet Docker : Conteneurisation d'une Application Flask + PHP

📌 Étape : Construire (build) et tester l'API 
Dans cette partie, nous allons construire et tester l’API Flask en suivant plusieurs étapes.
 1. Choix de l’image de base
🎯 Objectif :
Nous avons utilisé l’image python:3.8-buster comme base pour notre conteneur.
 2. Ajout des informations du mainteneur
🎯 Objectif :
Nous avons ajouté notre nom et email dans le Dockerfile avec LABEL maintainer.
![image](https://github.com/user-attachments/assets/4ba07cee-5e44-4af9-9e11-721ebe9cb969)


3. Exposition du port 5000
🎯 Objectif :
Nous avons configuré le conteneur pour exposer le port 5000 afin d’accéder à l’API Flask.
✅ 8. Construction et lancement de l’image Docker 
🎯 Objectif :
Nous avons construit l’image avec la commande :
docker build -t student_api .

![Capture d'écran 2025-03-21 112826](https://github.com/user-attachments/assets/52e33dca-809c-4e20-be69-97d81463ddf1)
Puis, nous avons lancé un conteneur avec :
docker run -d -p 5000:5000 -v $(pwd)/student_age.json:/data/student_age.json --name api student_api

Commande docker build avec les logs de création de l’image.
Commande docker ps montrant que le conteneur est en cours d’exécution.
![Capture d'écran 2025-03-21 113448](https://github.com/user-attachments/assets/b0824b76-d22b-425e-8704-30673f9f67a6)
![Capture d'écran 2025-03-21 113833](https://github.com/user-attachments/assets/c92c3a03-5922-4da6-8575-c6253cb06e0f)


10. Test final avec curl
🎯 Objectif :
Nous avons testé l’API en appelant :
curl -u root:root -X GET http://localhost:5000/supmit/api/v1.0/get_student_ages
![Capture d'écran 2025-03-21 114613](https://github.com/user-attachments/assets/8cbe828c-3184-4421-93e6-f6c292309c1c)


📌 Étape II : Infrastructure as Code (5 points)
Dans cette étape, nous allons automatiser le déploiement de l’API et du site web PHP en utilisant Docker Compose. 🚀

✅ 1. Création du fichier docker-compose.yml
🎯 Objectif :
Nous avons créé le fichier docker-compose.yml qui définit les services API et Website.
![image](https://github.com/user-attachments/assets/216c54b1-c9fb-4cdf-91bc-53aeb06be968)


Affichage du code docker-compose.yml montrant la configuration du service api.
✅ 5. Lancer Docker Compose
🎯 Objectif :
Nous avons lancé l’application en une seule commande :
docker-compose up --build -d
![Capture d'écran 2025-03-21 120816](https://github.com/user-attachments/assets/07629c4b-7802-4903-81af-edd2b1de2f58)
![Capture d'écran 2025-03-21 120835](https://github.com/user-attachments/assets/de4bfb06-8edf-43ea-95aa-6c77ec072b23)
![Capture d'écran 2025-03-21 120846](https://github.com/user-attachments/assets/707ec1c4-aac4-4d3a-9201-38e29667efec)
![Capture d'écran 2025-03-21 121055](https://github.com/user-attachments/assets/5dd86317-a202-41fb-a401-e7ebfc2f308f)
![Capture d'écran 2025-03-21 121122](https://github.com/user-attachments/assets/4b93db8d-bace-4df7-8a5e-4eb24d0dd737)
![Capture d'écran 2025-03-21 121122](https://github.com/user-attachments/assets/3b17be75-e36c-4528-b6d9-f3c4e0acd4e4)


✅ 6. Tester l’application
🎯 Objectif :
Nous avons accédé au site web via http://localhost:8080 et cliqué sur "List Student" pour vérifier que l’API fonctionne.
![Capture d'écran 2025-03-21 122255](https://github.com/user-attachments/assets/77860423-9e82-40d0-a54e-e962394b0cc3)
![Capture d'écran 2025-03-21 122304](https://github.com/user-attachments/assets/4116a872-aa27-466a-bb2a-4c6dde2b937e)


Affichage du site web avec la liste des étudiants.



