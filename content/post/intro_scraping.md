---
categories:
  - Offre
title: "Methodo Scraping"
slug: "methodo scraping"
date: 2017-10-20T05:58:27+01:00
draft: false
---


_Ce billet a pour vocation de présenter notre expertise et comment nous pouvons contribuer aux projets et vous aider à mieux identifier les situations ._

---
## Scraping; what you need to know!

Le Scraping est une technique d’extraction automatique d’informations sur un ou plusieurs sites web. Le plus généralement il faut développer un script qui charge des page web une à une et récupère le contenu souhaité.

## Usecase

>Un exemple de usecase classique est la comparaison de catalogues de produits.

En utilisant le site d’asos on peut récupérer un catalogue de lunettes de soleil pour faire un benchmark de ce type de produits.

Notre page de référence est http://www.asos.fr/homme/lunettes-de-soleil/cat/?cid=6519 

On souhaite récupérer :

- Le nom
- La marque
- La catégorie (Aviateur, Barre plate, verres transparents …)
- Une référence produit ou ID produit
- Le prix
- La couleur
- Si il y a un motif écaille de tortue

La première étape va être de récupérer la liste des produits par catégorie. Il faut donc faire un premier script qui va charger les pages de chaques catégories.

![categories de lunettes](/images/intro_scraping/lunettes_categ.png)

Ensuite, il se trouve que certaines informations ne sont pas toujours disponibles dans la liste (la couleur par exemple). Mais ces informations sont disponibles sur la page du produit.

>Il peut y avoir des cas particuliers où le motif écaille se trouve dan le nom et d’autre où il correspond à une couleur.

![product page](/images/intro_scraping/lunettes_single_page_3.png)

Un deuxième script consiste donc à parcourir page par page les produit pour récupérer les informations manquantes.

Une fois la data récoltée il suffit de la formater dans un fichier .csv (ou autre).

[Dowload CSV](/static_files/asos_lunettes.csv) (400+ ref)

| id      | nom                                                               | marque            | categorie | prix     | couleur       | motif_ecaille |
|---------|-------------------------------------------------------------------|-------------------|-----------|----------|---------------|---------------|
| 8260236 | Lunettes de soleil aviateur avec emblème Medusa sur le côté       | Versace           | aviateur  | 267,99 € | Noir          | FALSE         |
| 8260234 | Lunettes de soleil aviateur                                       | Versace           | aviateur  | 279,99 € | Noir          | FALSE         |
| 8166034 | Lunettes de soleil aviateur                                       | Reclaimed Vintage | aviateur  | 27,99 €  | Doré          | FALSE         |
| 8576633 | Lunettes aviateur à verres transparents de forme angulaire        | ASOS              | aviateur  | 16,99 €  | Réinitialiser | FALSE         |
| 8126231 | Lunettes de soleil rétro aspect bois                              | ASOS              | clubmaster_et_retro | 13,99 €          | Argenté | FALSE |
| 8126248 | Lunettes de soleil rétro motif écaille de tortue avec détail sur les branches | ASOS | clubmaster_et_retro | 13,99 €           | Écaille | TRUE  |
| 8064062 | Lunettes de soleil rétro contrastées noires et écaille de tortue              | ASOS | clubmaster_et_retro | 13,99 €           | Noir    | TRUE  |
| 8424238 | Lunettes de soleil aviateur                                       | Pull&Bear         | aviateur  | 14,99 €  | Doré          | FALSE         |
| 8275328 | 0RB3561                                                           | Ray-Ban           | aviateur  | 177,99 € | Doré          | FALSE         |


## Bottlenecks

- **Scraper peut créer une surcharge de trafic** nuisible pour le site. On évite donc de bombarder le serveur. C’est plus courtois et ça évite de se faire bannir. Donc comptez en moyenne entre 1 et 3 secondes par page.
- **Certains sites sont moins bien organisés**. J’ai choisi un exemple simple avec un site bien construit. Mais certains sites sont beaucoup plus difficiles à scraper que d’autres et c’est presque impossible de prévoir cette difficulté avant d’essayer.

## En résumé

- **N’importe quel texte sur un site peut être scrapé.** Certains sites seront trop durs (voir impossibles) à scrapper mais c’est très rare.
- Il faut comptez en moyenne entre **1h et 3h par script** de scraping en fonction de la difficulté.
- Ensuite comptez entre **1 et 3 secondes d'exécution du script par page**.