\documentclass[12pt,a4paper]{article}

% Packages
\usepackage[utf8]{inputenc}
\usepackage{graphicx}
\usepackage{geometry}
\usepackage{amsmath}
\usepackage{booktabs}
\usepackage{setspace}
\usepackage{hyperref}
\usepackage{float}

\geometry{margin=2.5cm}

\title{\textbf{Analyse de la Santé Mentale des Étudiants \\ \large Rapport Scientifique – Data Science \& Machine Learning}}
\author{Projet Académique}
\date{\today}

\begin{document}

\maketitle

\onehalfspacing

\begin{abstract}
Ce rapport présente une étude complète basée sur un dataset Kaggle portant sur la santé 
mentale des étudiants. L’objectif est d’analyser les facteurs associés à la dépression 
chez les étudiants et de développer un modèle de Machine Learning permettant de prédire 
le risque de dépression. La méthodologie suit les étapes standards d’un pipeline 
scientifique : nettoyage, analyse exploratoire, modélisation, validation et discussion.
\end{abstract}

\section{Introduction}

La santé mentale des étudiants constitue aujourd’hui un enjeu majeur. Entre la pression 
académique, le stress lié à l’avenir professionnel et les contraintes sociales, les 
étudiants présentent des risques élevés de troubles psychologiques, notamment de 
dépression.  

Dans ce projet, nous analysons un dataset Kaggle intitulé \textit{Student Depression Dataset}.  
La problématique étudiée est la suivante :

\begin{quote}
\textbf{Quels facteurs académiques, sociaux et comportementaux influencent la dépression 
des étudiants, et peut-on prédire l'état dépressif à partir de ces informations ?}
\end{quote}

Les objectifs du projet sont :
\begin{itemize}
    \item Réaliser une analyse exploratoire pour comprendre les relations entre variables ;
    \item Construire un modèle de classification binaire : Dépressif / Non Dépressif ;
    \item Évaluer les performances du modèle et interpréter ses erreurs ;
    \item Proposer des pistes d'amélioration pour une prédiction plus fiable.
\end{itemize}

\section{Méthodologie}

\subsection{Nettoyage et Pré-traitement}

Plusieurs étapes de préparation des données ont été nécessaires :

\begin{itemize}
    \item \textbf{Gestion des valeurs manquantes :} Les lignes contenant des valeurs nulles ont été retirées (faible impact).
    \item \textbf{Conversion des données textuelles :} La variable \textit{Sleep Duration} étant de type texte (ex. ``7 hours''), nous avons extrait la composante numérique (7).
    \item \textbf{Sélection des variables numériques :} Cela a permis de construire une heatmap de corrélation.
    \item \textbf{Encodage de la variable cible :} La variable \textit{Depression} était déjà binaire, donc directement exploitable.
\end{itemize}

Ces choix techniques sont justifiés par la simplicité du dataset et la nécessité d'assurer 
la cohérence des variables avant la modélisation.

\subsection{Analyse Exploratoire des Données (EDA)}

L’EDA a permis de dégager des tendances importantes :

\begin{itemize}
    \item L’histogramme des âges montre une population majoritairement située entre 18 et 24 ans.
    \item Le \textit{countplot} de la dépression indique un léger déséquilibre entre classes.
    \item Le \textbf{boxplot Academic Pressure vs Depression} montre une pression académique plus élevée chez les étudiants dépressifs.
    \item La heatmap de corrélation révèle des relations faibles mais structurées entre satisfaction, pression et CGPA.
    \item Plusieurs barplots catégoriels mettent en évidence des variations selon le genre et la satisfaction académique.
\end{itemize}

Chaque visualisation a été interprétée afin d'éviter une EDA purement descriptive.

\subsection{Modélisation}

Nous avons choisi d’entraîner un modèle de \textbf{régression logistique}, car :
\begin{itemize}
    \item il est adapté aux problèmes de classification binaire ;
    \item il offre une interprétabilité importante ;
    \item il constitue une baseline solide à comparer à d’autres modèles.
\end{itemize}

Les variables utilisées comme prédicteurs sont :
\begin{itemize}
    \item Age ;
    \item Academic Pressure ;
    \item Work Pressure ;
    \item CGPA ;
    \item Study Satisfaction ;
    \item Job Satisfaction ;
    \item Work/Study Hours ;
    \item Sleep Duration Numeric.
\end{itemize}

Les données sont séparées en \textbf{train-test} avec un ratio de 80/20, en fixant un 
random state pour assurer la reproductibilité.

\section{Résultats et Discussion}

\subsection{Métriques}

Le modèle de régression logistique obtient une \textbf{Accuracy d'environ 0.xx}.  
(à remplacer par la valeur exacte obtenue dans ton Notebook)

Une matrice de confusion a été générée pour analyser les erreurs :

\begin{itemize}
    \item Les \textbf{vrais positifs} représentent les étudiants correctement identifiés comme dépressifs.
    \item Les \textbf{faux négatifs} constituent l’erreur la plus critique (un étudiant dépressif non détecté).
    \item Les \textbf{faux positifs} sont moins graves, mais peuvent conduire à de fausses alertes.
\end{itemize}

\subsection{Discussion}

Les performances sont correctes pour un premier modèle, mais limitées :

\begin{itemize}
    \item Les corrélations observées dans la heatmap sont faibles, suggérant un phénomène multifactoriel.
    \item Le dataset repose sur des déclarations subjectives (biais possibles).
    \item Des modèles plus complexes pourraient capturer des relations non linéaires.
\end{itemize}

Le modèle reste cependant interprétable et donne une bonne première estimation.

\section{Conclusion}

Ce projet a permis de mettre en œuvre l'ensemble du pipeline Machine Learning :  
pré-traitement, analyse exploratoire, modélisation et évaluation.

Les résultats montrent que la dépression est influencée par plusieurs variables, 
notamment :
\begin{itemize}
    \item la pression académique ;
    \item la satisfaction d'étude ;
    \item la durée du sommeil.
\end{itemize}

\subsection*{Limites}

\begin{itemize}
    \item Dataset auto-déclaratif, donc biais possible ;
    \item Modèle simple (linéaire) ;
    \item Absence de variables psychologiques essentielles.
\end{itemize}

\subsection*{Pistes d'amélioration}

\begin{itemize}
    \item Tester des modèles plus robustes tels que Random Forest, XGBoost ou SVM ;
    \item Ajouter une sélection automatique de features ;
    \item Normaliser les variables pour les modèles sensibles à l’échelle ;
    \item Utiliser des techniques de rééchantillonnage en cas de déséquilibre ;
    \item Implémenter SHAP ou LIME pour interpréter les modèles plus complexes.
\end{itemize}

\end{document}
