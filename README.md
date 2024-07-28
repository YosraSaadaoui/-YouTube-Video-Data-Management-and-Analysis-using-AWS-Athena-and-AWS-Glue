# -YouTube-Video-Data-Management-and-Analysis-using-AWS-Athena-and-AWS-Glue

# Table des matières

- [Objectif](#Objectif)
- [source de données](#source-de-données)
- [Architecture](#architecture)
- [services AWS](#services-AWS)
- [Ètapes du projets](#Ètapes-du-projets)
  - [I. Création d’un utilisateur IAM ](#I.Création-d'un-utilisateur-IAM)  
  - [II. Installation de AWS CLI ](#II.-Installation-de-AWS-CLI) 
  - [III. Extraction des données dans un compartiment S3](#III.extraction-des-donnees-dans-un-compartiment-S3)
  - [IV. Intégration de données avec AWS GLUE](#transform-the-data)
  - [Create the SQL View](#create-the-sql-view)
- [Testing](#testing)
  - [Data Quality Tests](#data-quality-tests)
- [Visualization](#visualization)
  - [Results](#results)
  - [DAX Measures](#dax-measures)
- [Analysis](#analysis)
  - [Findings](#findings)
  - [Validation](#validation)
  - [Discovery](#discovery)
- [Recommendations](#recommendations)
  - [Potential ROI](#potential-roi)
  - [Potential Courses of Actions](#potential-courses-of-actions)
- [Conclusion](#conclusion)

# Objectif
Ce projet vise à gérer de manière sécurisée, rationaliser et analyser les données structurées et semi-structurées des vidéos YouTube en fonction des catégories de vidéos et des métriques de tendance.


Objectifs:

 - Ingestion des données : Mettre en place un mécanisme pour ingérer les données provenant de différentes sources.
- Processus ETL :   Recevoir les données au format brut et les transformer en un format approprié.
 - Lac de données : Centraliser les données provenant de multiples sources dans un dépôt centralisé.
- Scalabilité : Assurer que le système évolue avec l'augmentation du volume de données.
- Cloud : Utiliser le cloud pour traiter de grandes quantités de données, en l'occurrence AWS.
 - Reporting : Créer un tableau de bord pour répondre aux questions posées précédemment.


 # Source de données

 - Les données proviennent de Kaggle. Pour les trouver [cliquer ici.](https://www.kaggle.com/datasets/datasnaek/youtube-new)

Ces données Kaggle contiennent des statistiques (fichiers CSV) sur les vidéos YouTube populaires quotidiennes sur une période de plusieurs mois. Jusqu'à 200 vidéos tendance sont publiées chaque jour pour de nombreux emplacements. Les données pour chaque région sont dans leur propre fichier. Les éléments inclus dans les données sont le titre de la vidéo, le titre de la chaîne, l'heure de publication, les tags, les vues, les likes et dislikes, la description et le nombre de commentaires. Un champ category_id, qui varie selon la région, est également inclus dans le fichier JSON lié à la région.


# Architecture

![Diagramme d'architecture](Assets/images/architecture.png)


# services AWS

 - Amazon S3 : Amazon S3 est un service de stockage d'objets qui offre une évolutivité massive, une disponibilité des données, une sécurité et des performances élevées.
 - AWS IAM : Il s'agit de la gestion des identités et des accès, qui permet de gérer l'accès aux services et ressources AWS de manière sécurisée.
 - Amazon QuickSight : Amazon QuickSight est un service de business intelligence (BI) scalable, sans serveur, intégré et alimenté par l'apprentissage automatique, conçu pour le cloud.
 - AWS Glue : Un service d'intégration de données sans serveur qui facilite la découverte, la préparation et la combinaison des données pour l'analyse, l'apprentissage automatique et le développement d'applications.
 - AWS Lambda : Lambda est un service de calcul qui permet aux programmeurs d'exécuter du code sans créer ni gérer de serveurs.
 - AWS Athena : Athena est un service de requêtes interactives pour S3, permettant de interroger les données directement dans S3 sans avoir besoin de les charger.

# Ètapes du projets

## I. Création d’un utilisateur IAM 

Créer un utilisaeur IAM et lui  accorder la politique « Administrator Acces » puis lui créer une clé d'accès.


## II. Installation de AWS CLI
Téléchargez et exécutez le AWS CLI programme d'installation MSI pour Windows (64 bits) :
[https://awscli.amazonaws.com/AWSCLIV2.msi.](https://awscli.amazonaws.com/AWSCLIV2.msi)

## III. Extraction des données dans un compartiment S3
 - Télécharger les données à partir de Kaggle
 - Créer un compartiment S3
 - Copier les données dans le compartiment S3 en utilisant AWS CLI
