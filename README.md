#  Analyse predictive du niveaux de stock des produits de vente dans des magasins d’épiceries ( simulation projet ) <!-- omit from toc -->

- [:mag\_right: Contexte](#mag_right-contexte)
- [🤝 Besoin Client](#besoin-client)
- [📑 Analyse du besoin client et recommandations](#analyse-besoin-client)
- [🎯 Énoncé du Problème spécifique ( SMART ) avec le client](#enonce-du-probleme)
- [📊 Les Données](#les-donnees)
- [🗺️ Plan du Projet Data](#plan-du-projet-data)
- [📈 Résultats](#resultats)

## :mag_right: Contexte
<a name="mag_right-contexte"></a>
Gala Groceries est une société de distribution de produits alimentaires basée aux États-Unis et axée sur la technologie. Elle s'appuie fortement sur les nouvelles technologies, telles que l'IoT, pour se donner un avantage concurrentiel sur les autres épiceries. 
Elle fournit à ses clients des produits frais de la meilleure qualité, provenant de fournisseurs locaux. 

Cependant, cela s'accompagne de nombreux défis pour atteindre cet objectif.  Elle a besoin d’aide pour gérer sa chaîne d’approvisionnement. En effet, les produits d'épicerie sont des articles hautement périssables. En cas de surstockage, il gaspille de l'argent en raison d'un stockage excessif et de déchets, mais en cas de sous-stockage, il risque de perdre des clients.


<a name="besoin-client"></a>
## 🤝 Besoin Client
Gala Groceries  veut savoir comment mieux stocker les articles qu'ils vendent?
Il s’agit d’un problème commercial auquel nous avons été soumis et nous devons nous plonger dans les données afin de formuler des questions et des recommandations à Gala Groceries sur les autres éléments dont nous avons besoin pour répondre à cette question.
L’équipe data engineering a mis à ma disposition un échantillon de données de ventes. 

<a name="analyse-besoin-client"></a>
## 📑 Analyse du besoin client et recommandations

J'ai recu un echantillon de données de ventes comportant 7829 lignes et 8 colonnes.

- transaction_id = il s'agit d'un identifiant unique attribué à chaque transaction
- timestamp = il s'agit de la date à laquelle la transaction a été effectuée
- product_id = il s'agit d'un identifiant attribué au produit vendu. Chaque produit a un identifiant unique
- category = il s'agit de la catégorie dans laquelle le produit est contenu
- customer_type = il s'agit du type de client qui a effectué la transaction
- unit_price = le prix de vente d'une unité de ce produit
- quantity = le nombre d'unités vendues pour ce produit dans le cadre de cette transaction
- total = le montant total à payer par le client
- payment_type = le mode de paiement utilisé par le client

J’ai analysé les données de ventes reçues ([Analyse Exploratoires des données.ipynb](/Analyse_exploratoire_données.ipynb) ). Cette analyse m’a permis d’obtenir les informations suivantes :

<img src="/img/besoin_client.jpg"  height =400 /> 

- Les fruits et légumes sont les deux catégories de produits les plus fréquemment achetées
- Les non-membres sont les acheteurs les plus fréquents dans le magasin
- Les espèces sont le mode de paiement le plus utilisé 
- 11 heures du matin est l'heure la plus chargée en ce qui concerne le nombre de transactions. 


En ce qui concerne la question du client :  "Comment mieux stocker les articles qu'il vend ?" 

mes recommandations sont les suivantes : 

⇒ Il s'agit d'une question très générale et pour l'aborder avec plus de précision, nous devons identifier un problème spécifique que l'entreprise souhaite résoudre. Par exemple, pouvons-nous prévoir la demande de produits sur une base horaire afin d'approvisionner les produits de manière plus intelligente ? 

⇒ Nous avons besoin de plus de données. L'échantillon actuel ne couvre qu’un seul magasin. 

⇒ En fonction de l'énoncé du problème, nous aurons besoin d'autres ensembles de données pour décrire le résultat que nous essayons de modéliser. Par exemple, si nous modélisons la demande de produits, nous pourrions vouloir inclure des informations sur les niveaux de stock ou les conditions météorologiques. 


<a name="enonce-du-probleme"></a>
## 🎯 Énoncé du Problème spécifique ( SMART ) avec le client

Description détaillée du problème SMART avec le client.

<a name="les-donnees"></a>
## 📊 Les Données

Explication sur les données utilisées pour le projet.

<a name="plan-du-projet-data"></a>
## 🗺️ Plan du Projet Data

Présentation du plan et de la méthodologie du projet.

<a name="resultats"></a>
## 📈 Résultats

Affichage des résultats obtenus avec des graphiques et analyses.

