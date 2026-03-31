# Métadonnées - Relevé GNSS Place Louis Pasteur

## 1. Informations générales

-   **Auteurs** : Apolline De Prins, Esteban Dandoy, Nicolas Jamar Rodriguez
-   **Institution** : UCLouvain
-   **Cours** : LGEO2250, Mesures de terrain en géographie
-   **Contact** : [apolline.deprins\@student.uclouvain.be](mailto:apolline.deprins@student.uclouvain.be){.email} ; [esteban.dandoy\@student.uclouvain.be](mailto:esteban.dandoy@student.uclouvain.be){.email} ; [nicolas.jamar\@student.uclouvain.be](mailto:nicolas.jamar@student.uclouvain.be){.email}
-   **Date de collecte** : 11/03/2026
-   **Lieu** : Place Louis Pasteur, Louvain-La-Neuve, Belgique

------------------------------------------------------------------------

## 2. Matériel

| Équipement       | Modèle           | Rôle      |
|------------------|------------------|-----------|
| Récepteur GNSS 1 | Emlid Reach RS2+ | Base fixe |
| Récepteur GNSS 2 | Emlid Reach RS2+ | Rover     |
| Application      | Emlid Flow       | Collecte  |
| Logiciel         | Emlid Studio     | PPK       |

------------------------------------------------------------------------

## 3. Paramètres de collecte

-   **Nombre de points collectés** : 139 points
-   **Durée d'averaging par point** : 5 secondes
-   **Hauteur du rover** : 2.074 m
-   **Hauteur de la base** : 1.89 m
-   **Système de coordonnées** : ETRS 1989

------------------------------------------------------------------------

## 4. Structure des fichiers

```         
LGEO2250_Groupe3_metadata/
│
├── Arpentage/
│   ├── 1_Brut/          → tableau points bruts (*_.csv)
│   └── 2_Corrige/       → tableau points corrigés (*_corrected.csv)
│
├── Base/
│   ├── 1_Brut/          → fichiers bruts base (*_.ubx, *_.LLH)
│   └── 2_Converti/      → fichiers RINEX (*_.25O, *_.25P, *_.25B)
│
├── Rover/
│   ├── 1_Brut/          → fichiers bruts rover (*_.ubx, *_.LLH)
│   ├── 2_Converti/      → fichiers RINEX (*_.25O, *_.25P, *_.25B)
│   └── 3_Corrige/       → solution PPK (*_.pos, *_events.pos)
│
README.md            → ce fichier
```

------------------------------------------------------------------------

## 6. Description des fichiers

| Fichier | Description |
|-----------------------|-------------------------------------------------|
| `*_.ubx` | Données brutes GNSS (format u-blox binaire) |
| `*_.LLH` | Position brute (latitude, longitude, hauteur) |
| `*_.25O / .25P / .25B` | Données converties au format RINEX 3.03 |
| `*_.pos` | Solution PPK calculée par Emlid Studio |
| `*_.csv` | Points d'arpentage bruts exportés depuis Emlid Flow |
| `*_corrected.csv` | Points d'arpentage avec corrections PPK appliquées |

### Colonnes du fichier CSV corrigé

| Colonne             | Description                              | Unité     |
|---------------------|------------------------------------------|-----------|
| Name                | Identifiant du point                     | /         |
| Longitude           | Longitude ETRS89                         | degrés dd |
| Latitude            | Latitude ETRS89                          | degrés dd |
| Ellipsoidal height. | Altitude ellipsoïdale                    | m         |
| Easting RMS         | Incertitude horizontale Est              | m         |
| Northing RMS        | Incertitude horizontale Nord             | m         |
| Elevation RMS       | Incertitude verticale                    | m         |
| Lateral RMS         | Incertitude latérale                     | m         |
| Antenna height      | Hauteur de l'antenne                     | m         |
| Solution status     | Qualité de correction (FIX/FLOAT/SINGLE) | /         |
| Averaging start     | Début de la fenêtre d'averaging          | UTC + 1   |
| Averaging end       | Fin de la fenêtre d'averaging            | UTC + 1   |
| Device type         | Matériel utilisé                         | /         |

------------------------------------------------------------------------

## 7. Qualité des données

-   **Points retenus pour l'analyse** : 136 points FIX sur 139 points collectés

Les données brutes étant volumineuses, elles sont stockées dans les "Releases" disponible sur :<https://github.com/ApollineDePrins/LGEO2250_GNSS_3/releases/tag/metadata>
