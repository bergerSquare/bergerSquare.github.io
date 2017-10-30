---
categories:
  - Offre
title: "Methodo Machine Learning"
slug: "methodo ML"
date: 2017-09-05T05:58:27+01:00
draft: false
---


_Ce billet a pour vocation de présenter notre expertise et comment nous pouvons contribuer aux projets et vous aider à mieux identifier les situations ._

---
## Machine Learning; what you need to know!

Le **Machine Learning** (aka. **ML**) s'apparente à de **l'apprentissage par l'exemple** a partir de data et appliqué par des algorithmes résultant à une **prédiction**.

>**Myth Buster:**

>_Le ML permet de détecter des **corrélations** et non des **causalités**. En d'autres termes, il est impossible de dire **POURQUOI** des faits sont corrélés ou non!_

Comprendre les causalités est possible par de l'**analyses descriptive ciblées** grâce aux pistes offertes par le ML.

Concrêtement, le ML chez RB peut permettre d'obtenir des **analyses prédictives sur projet**, ouvrant la voie à des interprétations et résultats impossible à obtenir de manière humaine.


## Uses cases

Le ML peut ce définir dans 3 contextes:

- La **Classification**: A partir de données déjà catégorisé et de catégorie définies, on assigne prédit pour une nouvelle entrée de donnée ca catégorie.
- Le **Clustering**: Similaire à la classification sauf que les catégories ne sont pas connues à l'avance et nous essayons de les définir.
- **Regression**: A partir de données numériques corrélée, on prédit une nouvelle valeur (prédition de prix futur, stocks,...).

Quelques exemples pour vous projeter sur vos projets:

- A a partir de réponse de sondage, catégoriser les répondants selon des personae pré défini, ou trouver ces catégories data driven pour confirmer les intuitions
- Prévoir des évolutions de marchés; évolution de traffic Web chez des retailers
- Détection de fraudes et pattern à partir de donnée fraude où des fraudes ont déjà été avéré.


Pour vous inspirer et jetter un oeil aux type de donnée nécessaire pour la mise en application, n'hésitez pas a jetter un oeil sur les [compétitions Kaggle](https://www.kaggle.com/competitions?sortBy=deadline&group=all&page=1&pageSize=20) qui répertorie des **real world problems** d'entreprises (ou particulier) à résoudre par du ML.



## Demonstration in real word exemple:

Une entreprise missione RB sur un problème RH. De plus en plus de leur plus anciens et talentueux employées quitte le navire.

- **Pourquoi?** _(le ML ne peut pas répondre directement)_
- **Comment endiguer le phénomène et prévoir le turn over?** _(le ML peut nous donner des pistes)_
- **Peut on anticiper quels autres employées sont susceptible de partir?** _(le ML est fait pour cette question!)_

Le client nous fournit un dataset [(récupérable ici)](https://www.kaggle.com/ludobenistant/hr-analytics/data) concernant des informations sur ces employés.



### Before started

Il est interessant de connaître les **grandes lignes du process** de mise en application du Machine Learning.  
Cela vous permet **d'identifier les situations** qui se prête a l'exercice.

Cet exemple, vous l'aurez peut-être deviné, implique de la classification et de la détermination d'importance de critère.


### Step 1: Nettoyer la donnée

Le ML fonctionne uniquement sur de la donnée **"propre"**.
De la donnée trouée, fausse ou mal formaté peut biaiser le résultat, voir rendre le processus de ML impossible.

![dirty data](/images/intro_ml/dirty_data.png)

Notre dataset n'est pas parfait mais les valeurs valeurs manquante. Il y a plusieurs moyen de gérer ce problème et ne pas perdre d'information en supprimant cette ligne. Par exemple, remlacons la par la moyenne des donnée.

![clean data](/images/intro_ml/clean_data.png)

### Bonus Stage: Enrichissement

A partir **d'autres source de donnée en relation** avec notre dataset, il est possible de rajouter des critères et ainsi être plus précis.

On peux imaginé que le client dispose de donnée sur le nombre de jours congé maladie, RTT et vacances pris par chaque employé. 

En **fusionnant** ces datasets, il est alors possible de prendre en compte de nouveau facteurs!

### Step 2: Créer un modèle

> Let's do it!

Je passe les détails du travail sur le choix des algorithmes à utiliser et tester sur les données pour avoir le résultat le plus fiable possible.

J'utilise maintenant **80%** du jeu de donnée pour **apprendre a notre machine** à étiquetter les futurs démissionaires.

Les **20%** restants servirons de **test**, que nous donnerons a la machine SANS le résultat, pour constater un niveau de précision de la prédiction.

> **94,4%**; Not too bad!

On peut maintenant continuer d'itérer pour obtenir une meilleur précision.

Dans notre cas, j'estime que 5% de marge d'erreur et acceptable.

Il n'y a plus qu'a utiliser la base de donnée du client concernant ces employée actuellement en poste; nourrir de data notre algo, et savoir qui sont les prochains à partir!

Par exemple, voici le résultat brut d'une prédiction (pas vraiment lisible! télécharger le csv de l'étape 3 pour plus de détails):

![prediction](/images/intro_ml/predictions.png)
En rouge, les prédictions (1 = va démissioner, 0 = va rester).
En vert, les critères.


### Step 3: Formatter le résultat

Ne reste qu'a générer un résultat utilisable pour le livrable, comme un fichier csv concernant les employées concidéré sur le départ:

[Dowload Predictions](/static_files/predictions_RH.csv)

Et un chart sur l'importance de critères jouant sur la démission d'employés:

![features importances](/images/intro_ml/features_importance.png)

### Step 4: Aller plus loin

On peux maintenant consolider les résultats du ML par des analyses descriptive plus ciblé pour appuyer nos recommandations (je n'en ferais pour notre exemple pour des raisons de conscisions).

Le niveau de satifaction, le nombre de projets, le nombre d'années dans l'entreprise, le nombre d'heure de travail et le nombre d'année depuis la dernière évaluation semble être des critères très déterminant.

Si les critères comme le nombre de projets et le nombre d'années dans l'entreprise ne peuvent être changés; d'autres leviers peuvent être actionnés:

- Faire une enquête interne pour savoir ce qu'il faut améliorer dans l'entreprise pour augmenter le niveau de satisfaction des employés?
- Leurs laisser plus de flexibilité en authorisant plus de télétravail?
- Faut t-il faire plus d'évaluation du travail des seniors?
- ...

## Bottlenecks

### Qualité

La **qualification** et la **"propreté"** des données sont des facteurs très impactant sur l'analyse. 
Si les données sont peu pertinentes et/ou manque de critères, aucun résultat solide ne peut émerger.
Porter un regard critique sur ce qu'il est possible de trouver au vu des donnée disponibles est indispensable.

### Quantité

Le ML à besoin d'une quantité suffisante pour fonctionner correctement. **Plus il y a de données** plus les résultats sont **probant** et **précis**. 
Il est possible de faire un learning à partir de 50 lignes Excel, mais le résultats sera alors a prendre avec des pincettes!

A l'inverse passé un certain volume, les implications techniques ce complexifient (changement de technologies et infrastructure cloud obligatoire).

## Le mot de la fin

Il n'en tient plu qu'à vous pour passer a la vitesse supérieur sur projet avec nous. Ce qui à été présenté ici n'est qu'une partie de notre expertise. Nous vous présenterons dans d'autres post d'autres partie de ce que nous pouvons faire en analyse, charting interactif, scraping,...
