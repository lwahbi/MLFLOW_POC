# MLflow: A Machine Learning Lifecycle Platform
Ce Poc a pour objective de prendre en main l'utilisation de Mlflow.
Il s’agit de manipuler un modèle de régression linaire. Cet exemple est repris depuis le site officiel https://mlflow.org/docs/latest/tutorials-and-examples/tutorial.html

Installation
------------
MLflow nécessite l'installation de conda https://docs.conda.io/projects/conda/en/latest/#


Documentation
-------------
La documentation officielle de MLflow peut être trouvée ici https://mlflow.org/docs/latest/index.html.


Création d'environnement conda pour Notre projet
-----------------------------------------------


Pour créer un environnement conda il faut exécuter la commande::

    conda env create mlflow_conda

Entrainement du modèle
-----------------------
Se positionner dans l'environnement conda::

    conda activate mlflow_conda

Entrainer le modèle en lui fournissant les paramètre::

    python train.py 0.7 0.2

Packaging du modèle
-------------------
Après la phase d'entrainement et le choix des meilleurs paramètre on fait le packaging via la commande::

    mlflow run . -P alpha=0.7

Démarrage du serveur
---------------------
Pour lancer le serveur, on identifie l'id du modèle choisie par exemple 48cce6955f9e43dcbb2497718a104e9d puis on exécute la commande suivante::

    Mlflow models serve -m runs:/48cce6955f9e43dcbb2497718a104e9d/model -p 1234


