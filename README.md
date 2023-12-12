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

Sur la base de mes recommandations, Gala Groceries souhaite se concentrer sur l'énoncé du problème suivant :

"Pouvons-nous estimer avec précision les niveaux de stock des produits sur la base des données de vente et des données des capteurs sur une période  afin de nous approvisionner de manière plus intelligente auprès de nos fournisseurs ?"  

<a name="les-donnees"></a>
## 📊 Les Données

Gala Groceries a mis à disposition:

<img src="/img/data_model.PNG"  /> 


- Les données de ventes 
- Les données de capteurs : Les capteurs  mesure la température des locaux de stockage où les produits sont conservés dans l'entrepôt.
- Les données sur le niveau de stockage  dans les réfrigérateurs et les congélateurs du magasin. Ces niveaux de stockage sont estimés par ces capteurs IoT.

<a name="plan-du-projet-data"></a>
## 🗺️ Plan du Projet Data

- Préparation des données : Il est question pour nous de nettoyer, fusionner et gérer les données manquantes.
- Feature engineering : Créer les nouvelles variables et transformer certaines variables pour  préparer la phase de modélisation ([Feature engineering.ipynb](/feature_Ingineering.ipynb) ).
- Construire les modèles de machine learning : Nous allons prédire les niveaux de stock des produits  en fonction des données de vente et des données de température de stockages et horaires ([Modelisation.ipynb](/Modelisation.ipynb)). 
- Evaluation du modèles et interprétations : Métriques de mesure de performance
- Préparation du powerpoint et présentation des résultats au client



<a name="resultats"></a>
## 📈 Résultats

-  **Échantillon de données faibles**

Une précision d'environ 50% a été obtenue avec notre modèle de Random Forest. Pour tester ce modèle en production, nous avons besoin d'échantillons plus importants.

- **Le prix est important**

Le prix était une caractéristique importante dans le modèle de prédiction du stock.
Existe-t-il d'autres caractéristiques sur les produits que nous pouvons utiliser pour les inclure dans le modèle? 

- **S'appuyer sur l'IoT**
  
La température était également significative dans le modèle de prédiction du stock. Avec plus de données IoT sur une période plus longue, nous pensons que la précision de ce modèle augmentera. Cela ouvre également des sources de données, telles que la météo.



