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
  
----
### CodeBase : 
### Guide de Création et Installation d'une Application de Chat Vidéo avec JavaFX

#### 1. Prérequis

- Java Development Kit (JDK) 11 ou supérieur
- Maven ou Gradle (pour la gestion des dépendances)
- MySQL ou PostgreSQL (pour la base de données)
- Un IDE comme IntelliJ IDEA ou Eclipse

#### 2. Structure du Projet

La structure du projet suivra l'architecture MVC avec des couches supplémentaires pour les services et les répertoires. Voici un exemple de structure de répertoires :

```
video-chat-app/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── com/
│   │   │   │   ├── app/
│   │   │   │   │   ├── controller/
│   │   │   │   │   ├── model/
│   │   │   │   │   ├── repository/
│   │   │   │   │   ├── service/
│   │   │   │   │   ├── view/
│   │   │   │   │   └── App.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── views/
│   │           ├── LoginView.fxml
│   │           ├── MainView.fxml
│   │           └── CallView.fxml
├── pom.xml (ou build.gradle)
└── README.md
```

#### 3. Configuration de Maven/Gradle

##### Maven

Créez un fichier `pom.xml` à la racine du projet et ajoutez les dépendances nécessaires :

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.app</groupId>
    <artifactId>video-chat-app</artifactId>
    <version>1.0-SNAPSHOT</version>
    <properties>
        <maven.compiler.source>11</maven.compiler.source>
        <maven.compiler.target>11</maven.compiler.target>
    </properties>
    <dependencies>
        <dependency>
            <groupId>org.openjfx</groupId>
            <artifactId>javafx-controls</artifactId>
            <version>17.0.1</version>
        </dependency>
        <dependency>
            <groupId>org.openjfx</groupId>
            <artifactId>javafx-fxml</artifactId>
            <version>17.0.1</version>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-data-jpa</artifactId>
            <version>2.7.0</version>
        </dependency>
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.30</version>
        </dependency>
        <dependency>
            <groupId>javax.xml.bind</groupId>
            <artifactId>jaxb-api</artifactId>
            <version>2.3.1</version>
        </dependency>
    </dependencies>
</project>
```

##### Gradle

Créez un fichier `build.gradle` à la racine du projet et ajoutez les dépendances nécessaires :

```groovy
plugins {
    id 'java'
    id 'application'
}

group 'com.app'
version '1.0-SNAPSHOT'

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.openjfx:javafx-controls:17.0.1'
    implementation 'org.openjfx:javafx-fxml:17.0.1'
    implementation 'org.springframework.boot:spring-boot-starter-data-jpa:2.7.0'
    implementation 'mysql:mysql-connector-java:8.0.30'
    implementation 'javax.xml.bind:jaxb-api:2.3.1'
}

application {
    mainClassName = 'com.app.App'
}

java {
    toolchain {
        languageVersion = JavaLanguageVersion.of(11)
    }
}
```

#### 4. Configuration de la Base de Données

Créez une base de données MySQL ou PostgreSQL et configurez le fichier `application.properties` pour la connexion :

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/video_chat_db
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL5Dialect
```

#### 5. Code de Base pour le Serveur

##### Entity: User.java

```java
package com.app.model;

import javax.persistence.*;

@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String username;
    private String password;
    // Getters and Setters
}
```

##### Repository: UserRepository.java

```java
package com.app.repository;

import com.app.model.User;
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.stereotype.Repository;

@Repository
public interface UserRepository extends JpaRepository<User, Long> {
    User findByUsername(String username);
}
```

##### Service: UserService.java

```java
package com.app.service;

import com.app.model.User;
import com.app.repository.UserRepository;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder;
import org.springframework.stereotype.Service;

@Service
public class UserService {
    @Autowired
    private UserRepository userRepository;

    private BCryptPasswordEncoder passwordEncoder = new BCryptPasswordEncoder();

    public User registerUser(String username, String password) {
        User user = new User();
        user.setUsername(username);
        user.setPassword(passwordEncoder.encode(password));
        return userRepository.save(user);
    }

    public User findByUsername(String username) {
        return userRepository.findByUsername(username);
    }
}
```

##### Controller: UserController.java

```java
package com.app.controller;

import com.app.model.User;
import com.app.service.UserService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/users")
public class UserController {
    @Autowired
    private UserService userService;

    @PostMapping("/register")
    public User register(@RequestParam String username, @RequestParam String password) {
        return userService.registerUser(username, password);
    }

    @GetMapping("/{username}")
    public User getUser(@PathVariable String username) {
        return userService.findByUsername(username);
    }
}
```

##### Application: App.java

```java
package com.app;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class App {
    public static void main(String[] args) {
        SpringApplication.run(App.class, args);
    }
}
```

#### 6. Interface Utilisateur avec JavaFX

##### Vue : LoginView.fxml

```xml
<?xml version="1.0" encoding="UTF-8"?>

<?import javafx.geometry.Insets?>
<?import javafx.scene.control.Button?>
<?import javafx.scene.control.Label?>
<?import javafx.scene.control.PasswordField?>
<?import javafx.scene.control.TextField?>
<?import javafx.scene.layout.GridPane?>

<GridPane fx:id="gridPane" alignment="CENTER" hgap="10" vgap="10" xmlns:fx="http://javafx.com/fxml" fx:controller="com.app.view.LoginController">
    <Label text="Username:" GridPane.columnIndex="0" GridPane.rowIndex="0"/>
    <TextField fx:id="usernameField" GridPane.columnIndex="1" GridPane.rowIndex="0"/>
    <Label text="Password:" GridPane.columnIndex="0" GridPane.rowIndex="1"/>
    <PasswordField fx:id="passwordField" GridPane.columnIndex="1" GridPane.rowIndex="1"/>
    <Label text="Confirm Password:" GridPane.columnIndex="0" GridPane.rowIndex="2"/>
    <PasswordField fx:id="confirmPasswordField" GridPane.columnIndex="1" GridPane.rowIndex="2"/>
    <Button text="Register" onAction="#handleRegister" GridPane.columnIndex="1" GridPane.rowIndex="3"/>
</GridPane>
```

##### Contrôleur : LoginController.java

```java
package com.app.view;

import javafx.fxml.FXML;
import javafx.scene.control.PasswordField;
import javafx.scene.control.TextField;
import javafx.scene.control.Alert;
import org.springframework.web.client.RestTemplate;
import com.app.model.User;

public class LoginController {

    @FXML
    private TextField usernameField;

    @FXML
    private PasswordField passwordField;

    @FXML
    private PasswordField confirmPasswordField;

    private RestTemplate restTemplate = new RestTemplate();

    @FXML
    private void handleRegister() {
        String username = usernameField.getText();
        String password = passwordField.getText();
        String confirmPassword = confirmPasswordField.getText();

        if (!password.equals(confirmPassword)) {
            showAlert("Passwords do not match!");
            return;
        }

        User user = restTemplate.postForObject("http://localhost:8080/users/register", null, User.class, username

, password);

        if (user != null) {
            showAlert("User registered successfully!");
        } else {
            showAlert("Failed to register user.");
        }
    }

    private void showAlert(String message) {
        Alert alert = new Alert(Alert.AlertType.INFORMATION);
        alert.setTitle("Registration");
        alert.setHeaderText(null);
        alert.setContentText(message);
        alert.showAndWait();
    }
}
```

##### Application Principale : App.java

```java
package com.app;

import javafx.application.Application;
import javafx.fxml.FXMLLoader;
import javafx.scene.Scene;
import javafx.stage.Stage;

public class App extends Application {

    @Override
    public void start(Stage primaryStage) throws Exception {
        FXMLLoader loader = new FXMLLoader(getClass().getResource("/views/LoginView.fxml"));
        Scene scene = new Scene(loader.load());
        primaryStage.setScene(scene);
        primaryStage.setTitle("Video Chat App");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

#### 7. Exécution et Test

1. **Démarrer le Serveur** : Exécutez `App.java` (côté serveur) pour démarrer le serveur Spring Boot.
2. **Démarrer le Client** : Exécutez `App.java` (côté client) pour lancer l'application JavaFX.
3. **Tester l'Inscription** : Utilisez l'interface de l'application pour créer un compte.
4. **Vérifier la Base de Données** : Assurez-vous que l'utilisateur est correctement enregistré dans la base de données.

#### 8. Fonctionnalités Avancées

1. **Chiffrement des Communications** : Utiliser des bibliothèques comme WebRTC pour les appels vidéo/voix chiffrés.
2. **Stockage Sécurisé des Mots de Passe** : Les mots de passe sont hashés et salés avec BCrypt.
3. **Authentification Sécurisée** : Utiliser JWT (JSON Web Tokens) pour sécuriser les sessions utilisateurs.
4. **Protection Contre les Attaques** : Implémenter des protections contre les attaques SQL injection et XSS.
5. **Journalisation et Audit** : Mettre en place des logs pour surveiller les activités et les tentatives de connexion.



