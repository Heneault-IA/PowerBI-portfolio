# Dashboard 3 : Commerce

**Description brève** :  
Ce troisième tableau de bord se concentre sur des données commerciales plus globales (Commerce.pbix). Le dossier inclut également les données sources (Data) nécessaires au rapport.

**Contenu** :

- `Commerce.pbix` : Le fichier Power BI.
- `Data/` : Dossier contenant les sources de données brutes.
- `Captures/` : Captures d'écran du rapport.

**Aperçus** :

![page1.png](Formation%20ORSYS/Dashboard%203/Captures/page%201.png)
![page2.png](Formation%20ORSYS/Dashboard%203/Captures/page%202.png)
![page3.png](Formation%20ORSYS/Dashboard%203/Captures/page%203.png)
![page4.png](Formation%20ORSYS/Dashboard%203/Captures/page%204.png)

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
