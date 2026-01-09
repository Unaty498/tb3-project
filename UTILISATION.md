# Projet TB3 - Instructions d'Utilisation
Ce document fournit des instructions détaillées pour utiliser le projet TB3 après l'installation.

## Accéder à l'Application Mobile
1. **Lancer l'Application Mobile** :
   - Ouvrez Android Studio.
   - Connectez votre téléphone Android via USB ou utilisez un émulateur.
   - Exécutez l'application mobile depuis Android Studio.
2. **Se Connecter** :
   - Utilisez les identifiants créés lors de la configuration initiale de Keycloak pour vous connecter à l'application mobile.
3. **Utiliser les Fonctionnalités** :
   - Explorez les différentes fonctionnalités de l'application mobile, telles que la gestion des badges et l'accès aux services.
## Accéder au Frontend Web (interface d'administration)
1. **Ouvrir le Navigateur** :
   - Lancez votre navigateur web préféré.
2. **Accéder à l'URL du Frontend** :
   - Entrez l'adresse suivante dans la barre d'adresse : `http://localhost:80` (ou `http://[IP_DU_SERVEUR]:80` si vous utilisez un serveur distant).
3. **Se Connecter** :
   - Utilisez les mêmes identifiants que pour l'application mobile pour vous connecter au frontend web.
   - Attention : la connexion au frontend nécessite d'avoir le rôle `ADMIN` attribué à l'utilisateur dans Keycloak.
4. **Utiliser les Fonctionnalités** :
   - Explorez les différentes fonctionnalités du frontend web, telles que la gestion des utilisateurs, des badges et des rapports.
## Créer un nouvel Utilisateur dans Keycloak
1. **Accéder à l'Interface d'Administration de Keycloak** :
   - Ouvrez votre navigateur web et allez à l'adresse `http://localhost/keycloak` (ou `http://[IP_DU_SERVEUR]/keycloak`).
2. **Se Connecter** :
   - Utilisez les identifiants administrateur globaux (par défaut : admin/admin).
3. **Créer un Nouvel Utilisateur** :
    - Cliquez sur Realms, puis sélectionnez `connected_lock`.
    - Allez dans l'onglet "Users" et créez un nouvel utilisateur avec les informations suivantes :
      - **Username**: Comme vous le souhaitez mais notez-le pour une utilisation ultérieure.
      - **Email**: Peu importe, par exemple user@example.com.
      - **First Name**: Votre prénom (évitez les accents)
      - **Last Name**: Votre nom de famille
4. **Définir le Mot de Passe** :
   - Dans l'onglet "Credentials", définissez un mot de passe pour l'utilisateur et désactivez l'option "Temporary".
5. **Attribuer des Rôles** :
   - Allez dans l'onglet "Role Mappings" et attribuez les rôles nécessaires à l'utilisateur (par exemple, `ADMIN` pour l'accès au frontend).
6. **Enregistrer les Modifications** :
   - Cliquez sur "Save" pour enregistrer les modifications.
## Créer et Gérer des Badges
1. **Accéder au Frontend Web** :
   - Suivez les instructions dans la section "Accéder au Frontend Web" pour vous connecter.
2. **Créer un Nouveau Badge** :
   - Dans le menu du frontend, naviguez vers la section "Badges".
   - Cliquez sur "Create New Badge" et remplissez les informations requises (par exemple, nom du badge, description).
   - Cliquez sur "Save" pour enregistrer le nouveau badge.
3. **Après la Création** :
   - Le nouveau badge sera attribué à l'utilisateur renseigné, et s'il est physique marqué comme `NON_CHARGE`.
   - Sur l'application mobile, l'utilisateur pourra voir le badge dans sa liste de badges, et s'il clique dessus, l'appli lui proposera de le charger sur un badge physique via NFC.
   - Une fois le badge chargé sur le badge physique, son statut passera à `CHARGE` dans l'application mobile et le frontend web.