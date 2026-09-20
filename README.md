# AutoLoc

Plateforme de gestion de location de véhicules multi-agences.

Projet réalisé dans le cadre du module **UP ASI — Architecture des Systèmes d'Information** (ESPRIT).

> **Statut : README v0** — acteurs et cas d'utilisation à affiner au fil des séances.

## Objectifs du projet

- Centraliser la gestion des véhicules, des réservations et des contrats de location de plusieurs agences.
- Permettre aux clients de consulter les véhicules disponibles et de réserver en ligne.
- Donner aux agences un outil pour suivre les départs, les retours et l'état du parc.
- Offrir à la direction une vue d'ensemble (parc, activité, utilisateurs).
- Appliquer les bonnes pratiques d'architecture d'un SI : couches (contrôleur, service, persistance), API REST, tests et documentation.

## Acteurs identifiés

| Acteur | Rôle |
|---|---|
| **Client** | Consulte les véhicules, réserve, suit ses locations |
| **Agent d'agence** | Gère le quotidien d'une agence : contrats, départs et retours de véhicules |
| **Responsable d'agence** | Supervise son agence : parc, tarifs, suivi de l'activité |
| **Administrateur** | Gère la plateforme : agences, comptes utilisateurs, paramétrage |

## Cas d'utilisation (première liste, à valider)

**Client**
- Consulter les véhicules disponibles (par agence, dates, catégorie)
- Réserver un véhicule
- Modifier ou annuler une réservation
- Consulter l'historique de ses locations

**Agent d'agence**
- Enregistrer le départ d'un véhicule (création du contrat)
- Enregistrer le retour d'un véhicule (état, kilométrage)
- Mettre à jour l'état d'un véhicule (disponible, loué, en maintenance)

**Responsable d'agence**
- Gérer le parc de véhicules de son agence
- Définir et modifier les tarifs
- Consulter les statistiques d'activité de l'agence

**Administrateur**
- Gérer les agences
- Gérer les comptes utilisateurs et leurs rôles

## Stack technique

| Catégorie | Outils |
|---|---|
| Langage / build | Java 17, Maven |
| Framework | Spring Boot 4.1.1 (Spring Web MVC, Spring Data JPA) |
| Base de données | MySQL 8.4 (développement), H2 (tests) |
| Productivité | Lombok, Validation |
| Outillage | IntelliJ IDEA, Git / GitHub, Postman |

Prévu dans les prochains ateliers : Spring AOP, Spring Scheduler, springdoc-openapi (Swagger UI), JUnit 5, Mockito, MockMvc, Jacoco, SonarLint.

## Prérequis

- JDK 17 (Temurin recommandé)
- MySQL 8.x, avec un service démarré sur le port 3306
- Git
- IntelliJ IDEA (ou tout IDE compatible Maven)

## Installation et lancement

1. Cloner le dépôt :
   ```bash
   git clone https://github.com/Mohamedsakhri08/AutoLoc.git
   cd AutoLoc
   ```
2. Créer la base de données :
   ```sql
   CREATE DATABASE autoloc_db CHARACTER SET utf8mb4;
   ```
3. Définir la variable d'environnement contenant le mot de passe MySQL (il n'est jamais écrit dans le dépôt) :
   - Windows (PowerShell) : `$env:DB_PASSWORD = "votre_mot_de_passe"`
   - IntelliJ : Run → Edit Configurations → *Environment variables* → `DB_PASSWORD=votre_mot_de_passe`
4. Lancer l'application :
   ```bash
   ./mvnw spring-boot:run
   ```
   ou exécuter la classe `tn.esprit.autoloc.AutolocApplication` depuis l'IDE.

L'application démarre sur http://localhost:8080.

## Structure du projet

```
AutoLoc
├── src/main/java/tn/esprit/autoloc   # code source
├── src/main/resources                # configuration (application.properties)
├── src/test                          # tests
└── pom.xml                           # dépendances Maven
```

## Preuve de l'environnement fonctionnel

Capture d'écran du démarrage de l'application : `docs/env-ok.png` *(à ajouter)*.

## Équipe

- Mohamed Sakhri — ESPRIT, 3A11
- *(autres membres à compléter)*
