# BAAC - Data Warehouse & Analyse OLAP des Accidents Corporels

## 📌 Contexte du projet

Ce projet a été réalisé dans le cadre d'un TP en **Informatique Décisionnelle** (4ème année Génie Informatique, ENSA). 
L'objectif est de construire un **entrepôt de données (Data Warehouse)** à partir des fichiers BAAC (Bulletins d'Analyse des Accidents Corporels de la circulation) et d'exploiter ces données via un **cube OLAP** pour l'analyse multidimensionnelle.

## 🛠️ Technologies utilisées

| Outil | Rôle |
|-------|------|
| **Pentaho Data Integration (Kettle)** | ETL : Extraction, Transformation, Chargement |
| **MySQL** | Base de données cible (Data Warehouse) |
| **Pentaho Schema Workbench** | Modélisation du cube OLAP (Mondrian) |
| **Pivot4j** | Analyse multidimensionnelle et visualisation |
| **Git / GitHub** | Versionnement du projet |

## 📊 Schéma du Data Warehouse (Schéma en étoile)

**Table de faits :** `fait_accident`
- `NbrDecs` : Nombre de tués
- `NbreBlessee` : Nombre de blessés (hospitalisés + légers)
- `NbreIndemne` : Nombre d'indemnes

**Dimensions :**
- `dim_departement` (lié à Région et Groupe)
- `dim_date` (hiérarchie : Année → Trimestre → Mois)
- `dim_lumiere` (conditions d'éclairage)
- `dim_condition_atmos` (conditions météorologiques)

## 🔄 Processus ETL réalisé

1. **Extraction** : Lecture des 4 fichiers CSV sources (Caractéristiques, Usagers, Véhicules, Lieux)
2. **Transformation** :
   - Nettoyage et remplacement des valeurs NULL
   - Agrégation pour calculer les indicateurs par accident
   - Jointure entre les rubriques Usagers et Caractéristiques
   - Récupération des clés étrangères depuis les dimensions
3. **Chargement** : Alimentation des tables MySQL (`baac_dwh`)

## 📈 Analyse OLAP avec Pivot4j

Requête multidimensionnelle réalisée :
> Nombre de **morts**, **blessés** et **indemnes** pour les années **2010, 2011 et 2012**

Captures d'écran des résultats disponibles dans le rapport.


## 👨‍🎓 Auteur

**Ayoub NIRI** - Étudiant en 4ème année Génie Informatique, ENSA Agadir  

## 📅 Année universitaire

2025/2026
