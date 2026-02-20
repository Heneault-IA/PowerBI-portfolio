# Portfolio Power BI – Thomas Heneault

Deux dashboards créés après une formation intensive de 4 jours sur Power BI (février 2026), et un troisième dashboard sur le commerce en général.

Objectif : Transformer des données brutes en visualisations interactives et insights business.

## Dashboard 1 : E-commerce Analysis

**Description** : Dashboard sur les ventes d'un e-commerce, top produits, évolution CA, comportement clients.
_(Voir [Formation ORSYS/Dashboard 1/description.md](Formation%20ORSYS/Dashboard%201/description.md) pour plus de détails)_

- Outils : Power Query (nettoyage), DAX (mesures YoY, % marge), slicers, cartes, graphs bar/line.
- Apprentissages : Modélisation star schema, bookmarks, tooltips custom.

**Aperçus** :

<img src="Formation%20ORSYS/Dashboard%201/Captures/overview.png" alt="overview1" width="600">

**DAX** :

```dax
Chiffre d'affaire = SUMX(Sales, Sales[Products.price] * Sales[Sales])
```

**Télécharger** : [Rapport ecom-analysis.pbix](https://raw.githubusercontent.com/Heneault-IA/PowerBI-portfolio/blob/main/Formation%20ORSYS/Dashboard%201/Rapport%20ecom-analysis.pbix)

## Dashboard 2 : E-commerce Analysis V2

**Description** : Seconde itération de l'analyse e-commerce avec un design et des indicateurs potentiellement différents.
_(Voir [Formation ORSYS/Dashboard 2/description.md](Formation%20ORSYS/Dashboard%202/description.md) pour plus de détails)_

- Focus : Mesures calculées, conditional formatting, drill-through.

**Aperçus** :

<img src="Formation%20ORSYS/Dashboard%202/Captures/overview.png" alt="overview2" width="600">

**DAX** :

```dax
total gross margin = SUMX(
    sales,
    Sales[Sales]*Sales[Products.gross margin]
    )
```

```dax
Titre Sales Revenue per Month = "Sales Revenue for Periode " & MIN(Sales[Month]) & " to " & MAX(Sales[Month])
```

**Télécharger** : [Rapport ecom-analysis.pbix](https://raw.githubusercontent.com/Heneault-IA/PowerBI-portfolio/blob/main/Formation%20ORSYS/Dashboard%202/Rapport%20ecom-analysis.pbix)

## Dashboard 3 : Commerce

**Description** : Analyse des activités commerciales et suivi de données globales. Inclut un dossier de données sources.
_(Voir [Formation ORSYS/Dashboard 3/description.md](Formation%20ORSYS/Dashboard%203/description.md) pour plus de détails)_

**DAX** :

```dax
Chiffre d'affaire = SUMX(
    'Commandes_complètes',
    'Commandes_complètes'[prix_vente] * 'Commandes_complètes'[Quantite]
    )
```

```dax
Cumul clients livrés trimestre = CALCULATE(
    [Nb Clients livrés],
    USERELATIONSHIP(
        Calendrier_final[Date],
        Calendrier_commandes[Date de livraison]
    )
)
```

```dax
Nb Commandes Jours Feries = CALCULATE(
    [Nb Commandes],
    FILTER(Calendrier_final, Calendrier_final[Jours fériés] == TRUE())
    )
```

**Aperçus** :

<img src="Formation%20ORSYS/Dashboard%203/Captures/page%201.png" alt="page1" width="600">
<img src="Formation%20ORSYS/Dashboard%203/Captures/page%202.png" alt="page2" width="600">
<img src="Formation%20ORSYS/Dashboard%203/Captures/page%203.png" alt="page3" width="600">
<img src="Formation%20ORSYS/Dashboard%203/Captures/page%204.png" alt="page4" width="600">

**Télécharger** : [Commerce.pbix](https://raw.githubusercontent.com/Heneault-IA/PowerBI-portfolio/blob/main/Formation%20ORSYS/Dashboard%203/Commerce.pbix)

## Comment tester les dashboards

1. Télécharge le fichier `.pbix` concerné.
2. Ouvre avec Power BI Desktop (gratuit).
3. Actualise les données si besoin (ou utilise les données embarquées).

## Compétences mises en avant

- Power BI Desktop & Service
- Power Query (ETL)
- DAX basique
- Visualisations interactives
- Design dashboards (thèmes, mise en page)

LinkedIn : https://www.linkedin.com/in/thomas-heneault-b955b2173/
