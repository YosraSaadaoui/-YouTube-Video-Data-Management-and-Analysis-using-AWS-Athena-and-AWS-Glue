# -YouTube-Video-Data-Management-and-Analysis-using-AWS-Athena-and-AWS-Glue

# Table des matières

- [Objectif](#Objectif)
- [source de données](#source de donneés)
- [Architecture](#architecture)
- [Design](#design)
  - [Mockup](#mockup)
  - [Tools](#tools)
- [Development](#development)
  - [Pseudocode](#pseudocode)
  - [Data Exploration](#data-exploration)
  - [Data Cleaning](#data-cleaning)
  - [Transform the Data](#transform-the-data)
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

 — Ingestion des données : Mettre en place un mécanisme pour ingérer les données provenant de différentes sources.
 — Processus ETL :   Recevoir les données au format brut et les transformer en un format approprié.
 — Lac de données : Centraliser les données provenant de multiples sources dans un dépôt centralisé.
 — Scalabilité : Assurer que le système évolue avec l'augmentation du volume de données.
 — Cloud : Utiliser le cloud pour traiter de grandes quantités de données, en l'occurrence AWS.
 — Reporting : Créer un tableau de bord pour répondre aux questions posées précédemment.


 # source de données

 - Where is the data coming from? 
The data is sourced from Kaggle, [see here to find it.](https://www.kaggle.com/datasets/datasnaek/youtube-new)

 This Kaggle dataset contains statistics (CSV files) on daily popular YouTube videos over the course of many months. There are up to 200 trending videos published every day for many locations. The data for each region is in its own file. The video title, channel title, publication time, tags, views, likes and dislikes, description, and comment count are among the items included in the data. A category_id field, which differs by area, is also included in the JSON file linked to the region.
