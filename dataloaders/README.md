README.md 

Le but de ce répertoire est de regrouper les fonctions et les classes permettant de faire
le chargement de données du dataset CIRCA et cela dans le but de faire de la reconstruction
de données Sentinel-S2 sans nuages. 

TODO:
-----
- refaire rapidement des liens vers jzay sur Nautilus (revoir comment faire la connection ssh via Nautilus)
- regarder les données de SEN12MSCRTSDataset sur jzay

- faire un script permettant de calculer les métriques de reconstruction en prenant en entrée une donnée sans nuage, son mask et la vérité terrain correspondante. 
    => (réfléchir à faire des métriques pour les pixels masqués et ceux non masqués)

- commencer à faire une doc sur le masquage des nuages possibles et intéressant à couvrir (s'inspirer de U-TILISE)

- faire des fonctoins de timeout pour savoir que prends le temps du dataloader et voir quels sont les améliorations que l'on peut y faire pour l'accélérer.

- enrichier le README

python tif2hdf5.py /lustre/fsn1/projects/rech/tel/uug84ql/cloud_reconstruction/africa all africa /lustre/fsn1/projects/rech/tel/uug84ql/DATA-SEN12MS-CR-TS