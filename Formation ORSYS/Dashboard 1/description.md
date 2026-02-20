# Dashboard 1 : E-commerce Analysis

**Description brève** :  
Ce tableau de bord (Rapport ecom-analysis.pbix) présente une analyse des données d'un site de e-commerce, en explorant les revenus, les volumes de ventes et le comportement des clients.

**Contenu** :

- `Rapport ecom-analysis.pbix` : Le fichier Power BI principal.
- `Captures/` : Captures d'écran du tableau de bord.

**Aperçus** :

![overview1.png](Formation%20ORSYS/Dashboard%201/Captures/overview.png)

**DAX** :

```dax
Chiffre d'affaire = SUMX(
    Sales,
    Sales[Products.price] * Sales[Sales]
    )
```
