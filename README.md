#  Segmentation Client & Stratégie de Rétention 

## Contexte Business
Dans le secteur du e-commerce, traiter tous les clients de la même manière est une stratégie inefficace et coûteuse. Ce projet vise à analyser les données transactionnelles d'une boutique en ligne pour **identifier des profils de clients distincts**.

L'objectif est de passer d'une approche marketing "taille unique" (Mass Marketing) à une **stratégie ciblée** (Targeted Marketing) pour :
1.  **Maximiser la valeur** des meilleurs clients (Rétention).
2.  **Réactiver** les clients dormants (Win-back).
3.  **Optimiser le budget** publicitaire en ne ciblant que les bons segments.

##  Stack Technique
* **Langage :** Python 3.x
* **Bibliothèques :** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn.
* **Algorithme :** K-Means Clustering .
* **Technique d'analyse :** RFM.

## Méthodologie

### 1. Préparation des Données
* Utilisation du dataset **Online Retail** (UCI Machine Learning Repository).
* **Nettoyage critique :** Suppression des transactions annulées (quantités négatives) et des enregistrements sans identifiant client (`CustomerID`).
* Création de la variable `TotalAmount` (Quantité * Prix Unitaire).

### 2. Feature Engineering (Analyse RFM)
Transformation des données transactionnelles en une table unique par client avec trois indicateurs clés :
* **Recency (R) :** Jours écoulés depuis le dernier achat.
* **Frequency (F) :** Nombre total de transactions.
* **Monetary (M) :** Montant total dépensé (Customer Lifetime Value - CLV).

### 3. Prétraitement et Modélisation
* Traitement de l'asymétrie des données (Skewness) via une **transformation logarithmique**.
* Standardisation des échelles avec **StandardScaler**.
* Détermination du nombre optimal de clusters ($k=3$) via la **Méthode du Coude (Elbow Method)**.
* Application de l'algorithme **K-Means**.

## Résultats & Analyse Marketing

L'analyse a permis d'isoler 3 segments de clients distincts ayant des comportements d'achat radicalement différents :

| Segment (Cluster) | Profil | Caractéristiques Observées | Stratégie Marketing Recommandée |
| :--- | :--- | :--- | :--- |
| **Cluster 1** 🥇 | **Champions (VIPs)** | Récence très faible (actifs), Fréquence et Montant très élevés. | **Fidélisation & Exclusivité :** Ne pas offrir de réductions (ils achètent déjà). Proposer un programme VIP, des accès anticipés aux nouveaux produits. |
| **Cluster 0** 🥈 | **Potentiels (Moyens)** | Achètent occasionnellement, panier moyen modéré. | **Développement (Upsell) :** Inciter à augmenter le panier moyen via des bundles ou la livraison offerte à partir d'un certain montant. |
| **Cluster 2** 🥉 | **À Risque (Perdus)** | Récence très élevée (n'ont pas acheté depuis longtemps), faible valeur. | **Réactivation (Win-back) :** Campagne e-mail agressive "Vous nous manquez" avec code promo. Si pas de réponse, arrêter les frais marketing. |


## 🚀 Conclusion
Ce projet démontre comment l'analyse de données permet de segmenter une base client hétérogène. L'application de ces stratégies permettrait à l'entreprise d'augmenter le ROI de ses campagnes marketing en adressant le bon message, au bon moment, au bon client.
