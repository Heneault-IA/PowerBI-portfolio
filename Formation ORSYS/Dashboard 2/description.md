# Dashboard 2 : E-commerce Analysis V2

**Description brève** :  
Une seconde vue ou itération du rapport e-commerce (Rapport ecom-analysis.pbix), potentiellement avec un design alternatif (wallpaper inclus) ou de nouvelles mesures.

**Contenu** :

- `Rapport ecom-analysis.pbix` : Le fichier Power BI.
- `wallpaper.jpg` : Arrière-plan utilisé dans le rapport.
- `Captures/` : Aperçus visuels du dashboard.

**Aperçus** :

![overview2.png](Formation%20ORSYS/Dashboard%202/Captures/overview.png)

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
