# Flu forecast

### Description

L’objectif de ce défi est de prévoir le taux de grippe pour 100 000 habitants par région
française au cours de certaines semaines.

Pour atteindre cet objectif, plusieurs jeux de données sont fournis dans la section Données :
mesures météorologiques de plusieurs paramètres (température, vitesse du vent, humidité,
etc.)
Données démographiques : nombre d'individus par région dans différents groupes d'âge,
sexe pour chaque année depuis 2004.
Analyse mensuelle Google : nombre de demandes liées à la grippe depuis 2004.

### Evaluation

Les pages d'évaluation décrivent comment les soumissions seront notées et comment les
étudiants devraient formater leurs soumissions.
La métrique d'évaluation pour cette compétition est l'erreur fondamentale moyenne,
couramment utilisée pour évaluer l'exactitude de la prédiction dans un problème de
régression. Le RMSE est donné par :

<p align="center">
  <img src="https://github.com/user-attachments/assets/e1331ded-bdb3-4fcf-aca8-3c29556a5476" />
</p>

Ou yi et y^i correspond au taux d'influenza réel et prévu (pour 100 000 habitants),
respectivement.

### Format de soumission

Pour chaque ID dans l'ensemble de données, les fichiers de soumission doivent contenir
deux colonnes : Id et TauxGrippe.
Le fichier doit contenir un en-tête et avoir le format suivant :

![image](https://github.com/user-attachments/assets/78505a51-6fb0-4745-a7cd-de2cef469ab7)

### Description de l’ensemble de données

#### Description des fichiers

- **train.csv** : l'ensemble d'entraînement
- **test.csv** : l'ensemble de test
- **example_submission.csv** : un exemple de fichier de soumission dans le bon format
- **ListedesStationsMeteo.csv** : Coordonnées GPS des stations météo
- **meteo.zip** : un fichier zip contenant un fichier .csv pour les mesures météorologiques de chaque semaine de 2004 à 2016 - par exemple le fichier intitulé synop.200504.csv correspondent aux mesures de la 4ème semaine de 2005.
- **doc_data_StationMeteo.pdf** : un document qui explique toutes les entrées dans chaque synop de fichier CSV. YYYYWW.csv dans le DonneesMeteorologiques.zip
- **RequetesGoogleParRegion.zip** : un fichier zip contenant plusieurs fichiers .csv de certains Google analytics, un pour chaque région de France pour la période d’intérêt 2004 à 2016 - Ces analyses représentent l’intérêt de recherche (relatif et normalisé) obtenu de GoogleTrends pour différents mots-clés liés à la grippe en français : a) grippe b) grippe -aviaire -vaccin (- signifie sans) c) grippe -aviaire -vaccin -porcine -H1N1 -AH1N1 -A -mexicaine -Mexique -pandemie
- **estim-pop-areg-sexe-gca-1975-2015.xls** : Ensemble de données de l’Insee (http://www.insee.fr/fr/themes/detail.asp?reg_id=99&ref_id=estim-pop) qui permet d’estimer le nombre d’individus par Région dans différentes tranches d’âge, par sexe pour chaque année de 1975 à 2015.

### Champs de données dans les fichiers train/test

- **Id** : un identifiant unique pour chaque entrée dans les deux fichiers
- **week** : le numéro de semaine d’une année spécifique - format YYYYWW - par exemple 201402 correspondent à la deuxième semaine de 2014 et 201531 à la 31e semaine de 2015,
- **region_code** : le numéro INSEE et celui de la Région française - par exemple 31 est NORD-PAS-DE-CALAIS,
- **region_name** : nom de la région française,
- **TauxGrippe** : Taux de grippe pour 100 000 habitants - Comme cela correspond à la quantité à prévoir, ce champ de données se trouve uniquement dans le fichier train.csv.
