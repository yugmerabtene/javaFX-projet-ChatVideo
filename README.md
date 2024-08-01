### User Story pour un Logiciel de Chat Vidéo avec JavaFX

**Titre : Développer une Application de Chat Vidéo Utilisant JavaFX**

#### En tant qu'utilisateur, je veux :

1. **Installer l'application sur mon PC :**
   - Télécharger et installer facilement le logiciel de chat vidéo.

2. **Créer un compte :**
   - M'inscrire en fournissant un identifiant unique et un mot de passe, avec une confirmation de mot de passe pour éviter les erreurs.
   - Aucune vérification par email n'est requise pour l'inscription.

3. **Se connecter avec d'autres utilisateurs :**
   - Rechercher et se connecter à un autre utilisateur en utilisant son identifiant unique.
   - Initier un appel vidéo ou audio avec l'utilisateur sélectionné.

4. **Recevoir des notifications d'appel :**
   - Recevoir une notification lorsqu'un autre utilisateur m'appelle.
   - Accepter ou refuser les appels entrants.

#### En tant que développeur, je veux :

1. **Implémenter une architecture client-serveur :**
   - Développer des composants serveur et client distincts pour l'application.
   - Assurer que le serveur maintienne une base de données pour stocker les informations des utilisateurs en toute sécurité.
   - Assurer que le serveur gère l'interaction et la mise en relation entre les clients.

2. **Suivre une architecture en couches :**
   - Utiliser JavaFX pour l'interface utilisateur (Vue).
   - Implémenter des contrôleurs pour gérer les interactions utilisateur.
   - Développer des modèles pour représenter les données de l'application.
   - Utiliser des répertoires pour les opérations de base de données.
   - Créer des services pour gérer la logique métier et les flux de travail de l'application.
   - Définir des entités pour représenter les objets de données stockés dans la base de données.

3. **Assurer des fonctionnalités de chat audio et vidéo fonctionnelles :**
   - Fournir un streaming vidéo et audio de haute qualité pendant les appels.
   - Assurer que l'application soit fiable et réactive pendant les appels.

4. **Développer une interface utilisateur conviviale :**
   - Concevoir une interface intuitive utilisant JavaFX.
   - Faciliter la navigation des utilisateurs dans l'application et leur permettre de réaliser toutes les actions nécessaires comme rechercher des utilisateurs, passer des appels et recevoir des notifications.

5. **Implémenter des mesures de sécurité robustes :**
   - **Chiffrement des communications :** Utiliser le chiffrement end-to-end pour toutes les communications audio et vidéo afin de garantir la confidentialité des conversations.
   - **Stockage sécurisé des mots de passe :** Hasher et saler les mots de passe avant de les stocker dans la base de données.
   - **Authentification sécurisée :** Utiliser des jetons de session sécurisés pour l'authentification des utilisateurs.
   - **Protection contre les attaques :** Implémenter des protections contre les attaques de type SQL injection, cross-site scripting (XSS) et autres vulnérabilités courantes.
   - **Journalisation et audit :** Mettre en place des mécanismes de journalisation des activités utilisateur et des tentatives de connexion pour la détection et la réponse aux incidents de sécurité.

#### Critères d'acceptation :

1. **Installation :**
   - L'application peut être installée sur les systèmes Windows et macOS.

2. **Création de compte :**
   - Les utilisateurs peuvent créer un compte avec un identifiant unique et un mot de passe.
   - La fonctionnalité de confirmation de mot de passe est implémentée pour éviter les erreurs.

3. **Connexion des utilisateurs :**
   - Les utilisateurs peuvent rechercher d'autres utilisateurs par leur identifiant unique.
   - Les utilisateurs peuvent initier et accepter/rejeter des appels sans problème.

4. **Notifications d'appel :**
   - Les utilisateurs reçoivent des notifications pour les appels entrants.
   - Les utilisateurs ont la possibilité d'accepter ou de refuser les appels.

5. **Qualité audio et vidéo :**
   - L'application supporte une communication audio et vidéo de haute qualité.

6. **Conformité à l'architecture :**
   - Le projet adhère au modèle MVC (Modèle-Vue-Contrôleur).
   - Les services gèrent la logique métier.
   - Les répertoires gèrent les opérations de base de données.
   - Les entités représentent correctement les objets de la base de données.
   - Le serveur gère l'interaction et la mise en relation entre les clients.

7. **Sécurité :**
   - Les communications audio et vidéo sont chiffrées end-to-end.
   - Les mots de passe sont hashés et salés avant d'être stockés.
   - Des jetons de session sécurisés sont utilisés pour l'authentification des utilisateurs.
   - Des protections contre les attaques courantes sont en place.
   - Des mécanismes de journalisation et d'audit sont implémentés.
