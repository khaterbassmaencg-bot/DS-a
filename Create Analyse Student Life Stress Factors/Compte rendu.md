# BASSMA KHATER

<img src="https://github.com/khaterbassmaencg-bot/DS-a/blob/main/Create%20Analyse%20Student%20Life%20Stress%20Factors/Bassma%20khater%20image.jpg" style="height:464px;margin-right:432px"/>

# CAC2

# 22007239

# Student Life and Stress Factors — Rapport d’Analyse

## SOMMAIRE

1. Introduction  
2. Contexte de l’étude  
3. Objectifs du projet  
4. Description du dataset  
5. Méthodologie d’analyse  
6. Chargement et préparation des données  
7. Analyse statistique et visualisations  
8. Interprétation des résultats  
9. Facteurs les plus déterminants  
10. Limites de l’étude  
11. Conclusion et recommandations  
12. Annexe — Code Python complet

---

## 1. Introduction

Ce rapport présente l’analyse d’un ensemble de données portant sur les habitudes de vie des étudiants et les facteurs associés au stress.

L’objectif principal est d’identifier les variables ayant le plus d’influence sur le niveau de stress déclaré par les étudiants.

Les données analysées proviennent du fichier :

**Student Stress Factors.csv**

---

## 2. Contexte de l’Étude

Le stress étudiant constitue un enjeu majeur pour :

- la santé mentale,
- la réussite académique,
- le bien-être psychologique.

Le jeu de données étudie plusieurs aspects de la vie étudiante :

- qualité du sommeil  
- fréquence des maux de tête  
- performance académique perçue  
- activité physique  
- consommation de caféine  
- niveau de stress ressenti  

L’objectif est d’analyser les relations entre ces facteurs.

---

## 3. Objectifs du Projet

Les objectifs de l’étude sont :

- Décrire statistiquement les variables du dataset
- Visualiser la distribution du stress
- Étudier la relation entre sommeil et stress
- Identifier les facteurs les plus corrélés au stress
- Interpréter les résultats obtenus

---

## 4. Description du Dataset

**Nom du fichier :** `Student Stress Factors.csv`

Le dataset contient des réponses d’étudiants sur :

- leurs habitudes de vie
- leur état de santé perçu
- leur niveau de stress

Il s’agit de données auto-rapportées.

---

## 5. Méthodologie d’Analyse

L’analyse a été réalisée en Python en utilisant :

- `pandas` → manipulation et analyse statistique
- `matplotlib` → visualisation graphique

### Étapes suivies

1. Importation des données
2. Exploration et statistiques descriptives
3. Vérification des valeurs manquantes
4. Visualisation de la distribution du stress
5. Analyse corrélationnelle
6. Interprétation des tendances observées

---

## 6. Chargement et Préparation des Données

### 6.1 Importation du dataset

```python
import pandas as pd

df = pd.read_csv("Student Stress Factors.csv")
df.head()
df.describe(include='all')
df.isnull().sum()
import matplotlib.pyplot as plt

plt.hist(df["How would you rate your stress levels?"])
plt.title("Distribution des niveaux de stress")
plt.xlabel("Stress level")
plt.ylabel("Fréquence")
plt.show()
df[
    ["Kindly Rate your Sleep Quality",
     "How would you rate your stress levels?"]
].corr()
plt.scatter(
    df["Kindly Rate your Sleep Quality"],
    df["How would you rate your stress levels?"]
)

plt.xlabel("Qualité du sommeil")
plt.ylabel("Niveau de stress")
plt.title("Relation entre sommeil et stress")
plt.show()
8. Interprétation des Résultats
🔹 Qualité du sommeil

Un sommeil de mauvaise qualité est fortement associé à un stress élevé.

🔹 Maux de tête

Les étudiants ayant des maux de tête fréquents présentent un niveau de stress supérieur.

🔹 Performance académique perçue

Les étudiants estimant avoir une faible performance subissent davantage de stress.

🔹 Activité physique

Elle semble jouer un rôle protecteur vis-à-vis du stress.

9. Facteurs les Plus Déterminants

Les trois facteurs principaux associés au stress sont :

Qualité du sommeil

Fréquence des maux de tête

Performance académique perçue

Ces résultats confirment l’impact :

des habitudes de vie

de la santé physique

du vécu académique

sur l’état de stress.
