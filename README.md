# VALDOM_surfacewater
Ce repository contient des éléments relatifs à la mise en œuvre du projet qualité des eaux de surfaces dans le cadre du min-projet mastère VALDOM

Projet Sopra<a name="TOP"></a>
===================

- - - - 
	
# Bassin adour-garonne #
* Données Hydrobiologie (Science qui étudie la faune aquatique)
		-> https://drive.google.com/file/d/1GQtdWMoVsghquLNrVzF8PkPe31TNLRDq/view?usp=sharing
* Données Physicoshimie (propriétés physiques et chimiques de la matière)
		-> https://drive.google.com/file/d/1pB8BZGVFXFXqJ09palVIImZn_Ao1wQZs/view?usp=sharing
		
# Objectifs #
- [ ] Compréhension des données : quelle valeur métiers sont-elles susceptibles de porter ?
- [ ] Quels usages peuvent en être fait avec les données telles que disponibles actuellement ?
- [ ] Comment pourrait on donner de la valeur à l’utilisation de ces données ?
- [ ] Identifier les « manques », ou ce qui permettraient d’aller plus loin par rapport à l’état
- [ ] Formaliser le problème sous un angle data-science / Machine Learning : type de problème
- [ ] Autant que faire se peut, ébaucher cet analyse data :
- [ ] Se projeter : cette approche, si elle devait être industrialisée, quelles en seraient les contraintes (rafraichissement des données, pérennité des données…)

# Data #	
## hydrobio ##
* **Stations_hydrobio_garonne**

| Colonne   |      Description      |
|-----------|:---------------------:|
| CdStationMesureEauxSurface, LbStationMesureEauxSurface |  code & label de la station |
| ~~DurStationMesureEauxSurface~~ |    indicateur de la minéralisation de l’eau(N/A)   |
| CoordXStationMesureEauxSurface, CoordYStationMesureEauxSurface, CdProjStationMesureEauxSurface, LibelleProjection, CodeCommune, LbCommune, CodeDepartement, LbDepartement, CodeRegion, LbRegion, LocPreciseStationMesureEauxSurf
ace | Localisation |
| CdMasseDEau, CdEuMasseDEau, NomMasseDEau, CdEuSsBassinDCEAdmin, NomSsBassinDCEAdmin, CdBassinDCE, CdEuBassinDCE, NomEuBassinDCE,  | identification de la masse d'eau en frence et en europe |
| CdTronconHydrographique, CdCoursdEau, ~~NomCoursdEau~~, CodeTypEthStationMesureEauxSurface, LibelleTypEthStationMesureEauxSurface | info hydrographique |
| DateCreationStationMesureEauxSurface, ~~DateArretActiviteStationMesureEauxSurface~~, DateMAJInfosStationMesureEauxSurface  | date de création, arret, maj de la sation |
| FinaliteStationMesureEauxSurface | finalité de la station |
| ~~ComStationMesureEauxSurface~~ | commentaire |
| CodeNatureStationMesureEauxSurface, LibelleNatureStationMesureEauxSurface | manuelle, automatique |
| AltitudePointCaracteristique | altitude |
| ~~PkPointTronconEntiteHydroPrincipale~~, ~~PremierMoisAnneeEtiage~~, ~~SuperficieBassinVersantReel~~, ~~SuperficieBassinVersantTopo~~ | irrelevent |

* **Operations_hydrobio_garonne**

| Colonne   |      Description      |
|-----------|:---------------------:|
| CdStationMesureEauxSurface, LbStationMesureEauxSurface, CdPointEauxSurf | id station |
| CdSupport, LbSupport | jointure avec les fichiersResultatsBiologiques |
| CdMethode, NomLongMethodePrel | Methode de prélèvement |
| DateDebutOperationPrelBio, HeureDebutOperationPrelBio, DateFinOperationPrelbio, HeureFinOperationPrelBio | date et heaure, DateDebutOperationPrelBio permet une jointure avec ResultatsBiologiques |
| CdProducteur, NomProducteur,  | Le producteur représente le maître d’ouvrage, ou le commanditaire de la donnée et prend la responsabilité d’accepter la donnée |
| CdPreleveur, NomPreleveur | ’intervenant ayant effectué l’opération de prélèvement biologique |
| CdDeterminateur, NomDeterminateur | l’intervenant ayant réalisé la détermination taxonomique de l’opération de prélèvement biologique |
| CodeSandreRdd, NomRdd | réseau de mesure de rattachement de l’opération de prélèvemen |
| CdStatutResBioOperationPrelBio, MnemoStatutResBioOperationPrelBio | statut des résultats de l’opération de prélèvement biologique |
| CdQualResBioOperationPrelBio, LbQualResBioOperationPrelBio | résultats de l’opération de prélèvement biologique (correcte/ pas correcte) |
| RefOperationPrelBio,  | Référence de l’opération de prélèvemen |
| ObjOperationPrelBio | Objectif de l’opération de prélèvement biologique |
| LongProspecOperationPrelBio | Longueur prospectée de l’opération de prélèvement biologique en mètres |
| LargeurMoyLameEauOperationPrelBio, HMoyLamOperationPrelBio | Largeur/ hauteur a lame d’eau de l’opération de prélèvement biologique |
| SurfTotProspecteeOperationPrelBio | Surface totale prospectée de l’opération de prélèvement biologique |

* **Resultats_hydrobio_garonne**

| Colonne   |      Description      |
|-----------|:---------------------:|
| CdStationMesureEauxSurface, LbStationMesureEauxSurface, CdPointEauxSurf | id station |
| DateDebutOperationPrelBio | Date début, jointure avec les fichiers Operations |
| CdSupport, LbSupport | jointure avec les fichiers Operations |
| DtProdResultatBiologique, HeureResultat | date, heure production du résultat  |
| CdParametreResultatBiologique, LbLongParametre | résultat ou indice calculé |
| ResIndiceResultatBiologique | Résultat biologique |
| CdUniteMesure, SymUniteMesure | Unité de Mesure |
| CdRqIndiceResultatBiologique, MnemoRqAna | remarque sur le résultat |
| CdMethEval | méthode d’évaluation du résultat biologique |
| RefOperationPrelBio | réf prélèvement: jointure avec le fichier Opérations |
| CdProducteur, NomProducteur | Producteur du prélèvement |
| CdAccredRsIndiceResultatBiologique, MnAccredRsIndiceResultatBiologique | Information permettant d’indiquer si une analyse a été réalisée dans les conditions d’accréditation (inconnu) |

* **ListesFauneFlore_hydrobio_garonne**

| Colonne   |      Description      |
|-----------|:---------------------:|
| CdStationMesureEauxSurface, LbStationMesureEauxSurface, CdPointEauxSurf | id station | 
| CdSupport, LbSupport | permet de faire une jointure avec le fichier Operations et resultats |
| DateDebutOperationPrelBio | date début prelevment jointure avec le fichier Operations et resultats |
| CdListeFauFlor, LbListeFauFlor | la liste faunistique ou floristique |
| ~~CdTypListeFauFlor~~, ~~MnTypListeFauFlor~~ | Code Sandre du type de la liste faunistique ou floristique |
| CdTypTaxRep, MnTypTaxRep, CdAppelTaxon, NomLatinAppelTaxon, RsTaxRep, CdRqNbrTaxRep, MnemoRqNbrTaxRep | Taxonomie |
| CdUniteMesure, SymUniteMesure | UniteMesure |
| RefOperationPrelBio | Référence de l’opération de prélèvement, jointure avec le fichier Operations et resultats |
| CdProducteur, NomProducteur | producteur |

* **ConditionsEnvironnementales_physico_garonne**
* 
| Colonne   |      Description      |
|-----------|:---------------------:|
CdStationMesureEauxSurface, LbStationMesureEauxSurface, CdPointEauxSurf | id station |
| CdSupport, LbSupport | jointure avec Operations, ResultatsBiologiques et ListesFauneFlore. |
| DateDebutOperationPrelBio,  | date prélevement jointure avec Operations ResultatsBiologiques et ListesFauneFlore |
| CdParametreEnv, LbLongParametre | paramètre environnemental |
| RsParEnvOpPrelBio | Mesure de la condition environnementale | 
| CdUniteMesure, SymUniteMesure | Unite de mesure |
| CdRqParEnvPrelBio, MnemoRqParEnvPrelBio | remarque de la mesure de la condition environnementale |
| CdMethodeParEnvPrelBio, NomMethodeParEnvPrelBio | méthode de la condition environnementale |
| RefOperationPrelBio | Référence de l’opération de prélèvement, jointure avec les fichiers Operations ResultatsBiologiques et ListesFauneFlore. |
| CdStatutParEnvPrelBio, MnStatutParEnvPrelBio | statut de la condition environnementale de l’opération de prélèvement biologique |
| CdQualParEnvPrelBio, LbQualParEnvPrelBio | la qualification de l’acquisition de la condition environnementale |
| DateParEnvPrelBio | Date de la mesure de la condition environnementale |
| CdProducteur, NomProducteur | l’intervenant producteur du prélèvement |
