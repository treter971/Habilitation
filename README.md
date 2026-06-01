# Application Habilitations

## 1. Présentation de l'application

L'application **Habilitations** est un outil interne développé pour répondre aux besoins d'une entreprise spécialisée dans la génération de sites web.

Cette entreprise dispose d’une application principale permettant de configurer et générer des sites internet pour ses clients (choix des pages, charte graphique, fonctionnalités, etc.). Cette application évolue régulièrement avec l’ajout et la mise à jour de modules techniques (CSS, HTML, JavaScript, PHP).

Dans ce contexte, il est nécessaire de sécuriser l’accès au back-end en fonction des profils des utilisateurs. L'application Habilitations a pour objectif de gérer ces accès.

---

## 2. Objectif de l'application

L'application permet de :

Gérer les développeurs (utilisateurs)
Associer un profil à chaque utilisateur
Définir des niveaux d’habilitation selon les profils
Contrôler l’accès aux fonctionnalités de l’application principale

Les profils existants sont :

Stagiaire
Designer
Développeur Front-End
Développeur Back-End
Administrateur

Les fonctionnalités concernées sont :

CSS
HTML
JavaScript
PHP

Les opérations possibles sont :

Consulter
Modifier
Administrer

---

## 3. Structure de la base de données

La base de données est implémentée sous MySQL.

Elle est composée des tables suivantes :

developpeur
profil
fonctionnalite
operation
habilitation

Le modèle conceptuel de données (MCD) est fourni dans le projet (fichier : *0-MCD_habilitations*).

---

## 4. Interfaces et fonctionnalités

L’application propose une interface permettant la gestion complète des développeurs.

### 4.1 Gestion des développeurs

L’utilisateur peut :

Consulter la liste des développeurs (nom, prénom, téléphone, email, profil)
Ajouter un développeur
  (le mot de passe est initialisé par défaut avec le nom du développeur, puis stocké sous forme hashée)
Modifier les informations d’un développeur
Supprimer un développeur
Modifier le mot de passe d’un développeur

---

## 5. Architecture de l'application

L’application est conçue selon le pattern **MVC (Model – View – Controller)**.

Le diagramme de paquetages est disponible dans le fichier :
*2-diagramme_de_paquetages_S2*

---

## 6. Couches supplémentaires

### 6.1 BddManager

Gère la connexion à la base de données
Exécute les requêtes SQL
Implémenté sous forme de singleton
Indépendant et réutilisable dans d’autres projets

### 6.2 DAL (Data Access Layer)

Sert d’intermédiaire entre les contrôleurs et la base de données
Contient les requêtes SQL
Utilise la classe BddManager

Cette architecture permet une séparation claire des responsabilités et facilite la maintenance et l’évolution de l’application.

---

## 7. Fonctionnement global

Le fonctionnement de l’application est le suivant :

1. L’application démarre sur une vue
2. La vue instancie son contrôleur
3. Le contrôleur traite les demandes et interagit avec la couche DAL
4. La DAL exécute les requêtes via BddManager
5. Les données sont manipulées via les classes du modèle

Cette organisation permet une bonne modularité et facilite les évolutions techniques (changement de SGBD, par exemple).

---

## 8. Étapes de construction (commits)

### Phase 1 : Structure de l’application

Création des paquetages et des classes
Début de l’implémentation de BddManager

### Phase 2 : Application fonctionnelle

Implémentation des fonctionnalités principales
Mise en place du CRUD des développeurs

### Phase 3 : Authentification

Ajout d’une fenêtre de connexion
Restriction de l’accès aux utilisateurs ayant le profil administrateur

### Phase 4 : Installeur

Création d’un installeur pour déployer l’application sur un autre poste

### Phase 5 : Sécurisation des mots de passe
Mise en place de règles de validation :

Longueur entre 8 et 30 caractères
Présence d’au moins une majuscule, une minuscule, un chiffre et un caractère spécial
Absence d’espaces

---

## 9. Installation

### 9.1 Prérequis

Système de gestion de base de données MySQL (WAMP recommandé)
Visual Studio 2022

### 9.2 Étapes d’installation

1. Importer la base de données :

   Exécuter le script `habilitations.sql`

2. Lancer l’application :

   Ouvrir le projet dans Visual Studio
   Compiler et exécuter

Ou

3. Installer via l’installeur :

   Lancer le fichier `setup.exe`
   Suivre les instructions d’installation

---

## 10. Authentification

L’accès à l’application est restreint aux utilisateurs disposant du profil administrateur.

---

## 11. Documentation utilisateur

Une vidéo de démonstration est fournie.
Elle présente l’ensemble des fonctionnalités de l’application ainsi que son utilisation.

---

## 12. Conclusion

L’application Habilitations permet de gérer efficacement les accès et les droits des utilisateurs au sein de l’entreprise.

Grâce à une architecture claire et modulaire, elle est facilement maintenable et évolutive, tout en garantissant la sécurité des accès au système.
