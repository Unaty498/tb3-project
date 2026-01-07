# Projet TB3 - Instructions d'Installation
Ce document fournit des instructions détaillées pour installer et configurer le projet.

## Prérequis
Avant de commencer l'installation, assurez-vous d'avoir les éléments suivants installés sur votre machine :
- Android Studio (pour le développement mobile)
- Docker et Docker Compose (pour les services backend et base de données) (https://docs.docker.com/get-docker/)
- Un téléphone Android si vous souhaitez tester l'application mobile et correctement configurer les badges physiques.
- La malette TB3 avec les composants nécessaires pour le développement embarqué.
- Le logiciel Thonny pour téléverser le code sur le microcontrôleur (https://thonny.org/).

## Étapes d'Installation
1. **Cloner le dépôt** :
   ```bash
    git clone https://github.com/Unaty498/tb3-project.git
    cd tb3-project
   ```
2. **Configurer le Backend + Keycloak + Frontend avec Docker** :
   - Assurez-vous que Docker et Docker Compose sont installés.
   - Dans le répertoire racine du projet, exécutez la commande suivante pour démarrer les services :
     ```bash
     docker-compose up --build
     ```
   - Cela lancera le backend Spring Boot, Keycloak pour la gestion des utilisateurs, et le frontend Vue.js.

3. **Configurer l'Application Mobile** :
   - Ouvrez Android Studio.
   - Importez le projet mobile situé dans le répertoire `mobile/`.
   - Connectez votre téléphone Android via USB ou utilisez un émulateur. (Assurez-vous que le mode développeur, le débogage USB ainsi que l'installation d'applications via USB sont activés sur votre téléphone.)

    - Exécutez l'application mobile depuis Android Studio.
4. **Configurer le Développement Embarqué** :
    - Suivez le schéma de câblage fourni dans le répertoire `docs/` pour connecter les composants de la malette TB3.
    - Ouvrez Thonny et connectez-vous au microcontrôleur.
    - Téléversez le code Python situé dans le répertoire `embedded/` sur le microcontrôleur.

### Important
- Si vous utilisez votre téléphone Android pour tester l'application mobile, assurez-vous que l'adresse IP du backend dans le code source de l'application mobile (Config.kt) est correctement configurée pour pointer vers votre machine de développement (ou l'adresse IP du serveur si vous utilisez un serveur distant).
- Pour toute modification du code backend ou frontend, n'oubliez pas de reconstruire les images Docker en utilisant la commande `docker-compose up --build`.

## Setup Initial de Keycloak
1. Accédez à l'interface d'administration de Keycloak à l'adresse `http://localhost/keycloak` ou `http://[IP_DU_SERVEUR]/keycloak`.
2. Connectez-vous avec les identifiants par défaut :
   - **Username**: admin
   - **Password**: admin
3. Cliquez sur "Realms", puis sélectionnez `connected_lock`.
4. Allez dans l'onglet "Users" et créez un nouvel utilisateur avec les informations suivantes :
   - **Username**: Comme vous le souhaitez mais notez-le pour une utilisation ultérieure.
   - **Email**: Peu importe, par exemple test@example.com
   - **First Name**: Votre prénom (évitez les accents)
   - **Last Name**: Votre nom de famille
5. Dans l'onglet "Credentials", définissez un mot de passe pour l'utilisateur et désactivez l'option "Temporary".
6. Allez dans l'onglet "Role Mappings" et attribuez le rôle `ADMIN` à l'utilisateur.
7. Enregistrez les modifications.
8. Utilisez ces informations d'identification pour vous connecter à l'application mobile et au frontend.


## Informations Supplémentaires
- Des données de test seront déjà présentes dans la base de données lors du premier démarrage.
- Pour toute question ou problème, veuillez consulter le fichier README.md ou contacter Léon Muselli ici : leon.muselli@etu.emse.fr
- Bonne installation !

