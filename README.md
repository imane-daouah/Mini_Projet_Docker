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
