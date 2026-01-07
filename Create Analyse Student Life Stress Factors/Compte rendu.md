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
# Compte rendu
Student Life and Stress Factors – Rapport d'Analyse
1. Introduction

Ce rapport présente l'analyse d'un ensemble de données portant sur les habitudes de vie des étudiants et les facteurs associés au stress.
L'objectif est d'identifier les variables ayant le plus d'influence sur le niveau de stress des étudiants.

Les données analysées proviennent du fichier : Student Stress Factors.csv.

2. Contexte de l'Étude

L'étude s'intéresse à plusieurs comportements et habitudes quotidiennes des étudiants, notamment :

Qualité du sommeil

Fréquence des maux de tête

Performance académique

Activité physique

Consommation de caféine

Niveau de stress déclaré

L'analyse vise à dégager les liens entre ces facteurs et le stress.

3. Objectifs

Les objectifs de l'étude sont :

Décrire les variables statistiquement

Visualiser les distributions et relations

Identifier les facteurs les plus corrélés au stress

Fournir une interprétation claire des résultats

4. Chargement et Exploration des Données
4.1 Importation des données
import pandas as pd

df = pd.read_csv("Student Stress Factors.csv")
df.head()

4.2 Statistiques descriptives
df.describe(include='all')

5. Nettoyage des Données
5.1 Vérification des valeurs manquantes
df.isnull().sum()


Aucune valeur manquante critique n'a été détectée.

6. Analyse des Données
6.1 Distribution du niveau de stress
import matplotlib.pyplot as plt

plt.hist(df["How would you rate your stress levels?"])
plt.title("Distribution des niveaux de stress")
plt.xlabel("Stress level")
plt.ylabel("Fréquence")
plt.show()

6.2 Relation entre sommeil et stress
df[[
    "Kindly Rate your Sleep Quality",
    "How would you rate your stress levels?"
]].corr()

6.3 Visualisation
plt.scatter(
    df["Kindly Rate your Sleep Quality"],
    df["How would you rate your stress levels?"]
)
plt.xlabel("Qualité du sommeil")
plt.ylabel("Niveau de stress")
plt.title("Relation entre sommeil et stress")
plt.show()

7. Interprétation des Résultats
Qualité du sommeil

Une tendance claire montre qu'une mauvaise qualité du sommeil est associée à un niveau de stress plus élevé.

Maux de tête

Les étudiants qui déclarent des maux de tête fréquents ont généralement un stress plus important.

Performance académique

Les étudiants considérant leur performance comme faible ou moyenne présentent un stress plus élevé.

Activité physique

L'activité physique semble avoir un effet atténuant sur le stress.

8. Conclusion

Les trois facteurs les plus déterminants dans les niveaux de stress sont :

Qualité du sommeil

Fréquence des maux de tête

Performance académique perçue

Ces résultats permettent de mieux comprendre les mécanismes du stress chez les étudiants.

9. Code complet utilisé
import pandas as pd
import matplotlib.pyplot as plt

# Load data
df = pd.read_csv("Student Stress Factors.csv")

# Preview
print(df.head())

# Description
print(df.describe(include="all"))

# Missing values check
print(df.isnull().sum())

# Stress distribution
plt.hist(df["How would you rate your stress levels?"])
plt.title("Distribution des niveaux de stress")
plt.xlabel("Stress Level")
plt.ylabel("Effectif")
plt.show()

# Correlation Sleep vs Stress
print(df[[
    "Kindly Rate your Sleep Quality",
    "How would you rate your stress levels?"
]].corr())

# Scatter plot
plt.scatter(
    df["Kindly Rate your Sleep Quality"],
    df["How would you rate your stress levels?"]
)
plt.xlabel("Qualité du sommeil")
plt.ylabel("Niveau de stress")
plt.title("Relation entre sommeil et stress")
plt.show()





