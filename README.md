# Projet Tontine - Spring Boot & MongoDB

## Description
Ce projet est une application de gestion de tontine développée avec **Spring Boot** et **MongoDB**. Il permet aux utilisateurs de créer et gérer des tontines, d'effectuer des cotisations et des retraits.

## Technologies utilisées
- **Spring Boot** (Framework backend Java)
- **MongoDB** (Base de données NoSQL)
- **Lombok** (Réduction du code boilerplate)
- **Spring Security** (Authentification et autorisation)
- **JWT (JSON Web Token)** (Gestion des tokens de connexion)

## Installation et configuration

### 1. Prérequis
- **Java 17 ou supérieur**
- **Maven** (pour gérer les dépendances)
- **MongoDB** installé et en cours d'exécution

### 2. Cloner le projet
```sh
git clone https://github.com/votre-repo/tontine.git
cd tontine
```

### 3. Configurer la base de données
Dans `src/main/resources/application.properties`, configurez la connexion à MongoDB :
```properties
spring.data.mongodb.uri=mongodb://localhost:27017/tontine_db
spring.data.mongodb.database=tontine_db
```

### 4. Lancer l'application
```sh
mvn spring-boot:run
```
L'application sera accessible sur **http://localhost:8080/**.

## Endpoints principaux

| Méthode | Endpoint               | Description                          |
|---------|------------------------|--------------------------------------|
| `POST`  | `/auth/signup`         | Inscription d'un utilisateur        |
| `POST`  | `/auth/login`          | Connexion et génération du token JWT |
| `POST`  | `/tontines`            | Créer une tontine                   |
| `GET`   | `/tontines/{id}`       | Récupérer les détails d'une tontine |
| `POST`  | `/cotisations`         | Ajouter une cotisation              |
| `GET`   | `/cotisations/{id}`    | Consulter les cotisations           |
| `POST`  | `/retraits`            | Demander un retrait                 |

## Structure du projet
```
├── src
│   ├── main
│   │   ├── java/com/example/tontine
│   │   │   ├── controller  # Contrôleurs REST
│   │   │   ├── model       # Modèles (classes MongoDB)
│   │   │   ├── repository  # Repositories Spring Data MongoDB
│   │   │   ├── service     # Services métier
│   │   │   ├── security    # Gestion JWT & Spring Security
│   │   │   ├── TontineApplication.java  # Point d'entrée de l'application
│   │   ├── resources
│   │   │   ├── application.properties  # Configuration
│   ├── test  # Tests unitaires et d'intégration
```

## Exécuter les tests
```sh
mvn test
```

## Déploiement
Pour générer le fichier **JAR**, exécutez :
```sh
mvn clean package
```
Puis lancez l'application :
```sh
java -jar target/tontine-0.0.1-SNAPSHOT.jar
```

## Contribuer
Les contributions sont les bienvenues !

1. **Fork** le projet
2. Crée une branche (`git checkout -b feature-nouvelle-fonctionnalité`)
3. Commit tes modifications (`git commit -m 'Ajout d'une nouvelle fonctionnalité'`)
4. Push la branche (`git push origin feature-nouvelle-fonctionnalité`)
5. Ouvre une **Pull Request**

## Auteurs
- **[Votre Nom]** - Développeur principal

## Licence
Ce projet est sous licence **MIT**.

