# Analysez vos tests #Python avec pytest-monitor

_Pytest-monitor_ est une toute nouvelle extension pour _Pytest_, le framework de test du langage Python, qui vous permet d’analyser l’utilisation des ressources de la machine exécutant les tests. 



![Logo Pytest-monitor](https://raw.githubusercontent.com/CFMTech/pytest-monitor/master/docs/sources/_static/pytestmonitor_readme.png)



Pour le moment, trois ressources sont surveillées et historisés par cette extension :



- le temps d’exécution
- la consommation mémoire
- l’utilisation du processeur



Chaque résultat étant attaché à environnement d’exécution, il est facile de comparer l’impact du matériel utilisé pour faire tourner vos tests.

> _Fin du chapeau_
----

_Pytest-monitor_ est particulièrement utile lors de mises à jour par exemple, qu’elles soient matérielles ou logicielles. Vous pourrez apprécier quel a été l’impact d’une montée de version d’une dépendance externe sur laquelle vous n’avez pas le contrôle ou encore le changement d’interpréteur ou de la machine faisant tourner les tests.



C’est aussi appréciable en intégration continue de pouvoir voir l’impact des modifications du code sur les tests et d’avoir une idée de l’incidence sur les performances.



## Utilisation et mode de fonctionnement



À partir du moment où vous avez au minimum un Python 3.5 et Pytest 4.4, l’installation se fait en une ligne de commande via les classiques canaux :



- *Anaconda* : `conda install pytest-monitor -c https://conda.anaconda.org/conda-forge`
- *pip* : `pip install pytest-monitor`



Ensuite, _pytest-monitor_ est actif par défaut dès que vous lancez vos (py)tests, pas besoin d’ajouter du code ou des commentaires. L’extension va faire une « photo » des ressources utilisées avant l’exécution des tests puis va se baser sur les routines systèmes pour récupérer les informations et minimiser son propre impact sur les mesures :



- `psutil` pour l’utilisation processeur ;
- `memory_profiler` pour la consommmation mémoire.



Au premier lancement, une base sqlite est créée dans le répertoire d’exécution. Celle-ci contient deux tables : une pour stocker la définition de l’environnement (Processeur, mémoire disponible, nom de la machine, OS, version de Python, etc.) et la seconde les résultats proprement dit pour chaque exécution (horodatés et reliés à un environnement). Dans une future version, il sera possible de pousser les résultats directement sur un serveur qui pourra les centraliser. La portée des résultats peut se faire au niveau fonction, module, classe ou encore session. De plus, il est possible d’influer sur la manière dont sont surveillés les tests :


- Ajout d’une description
- Désactivation locale (via un commentaire) ou global de la mesure de la performance des tests
- Paramétrage de certains tests, afin de pouvoir rejouer certaines fonctions avec des jeux de paramètres différents


## Contributions
Le code source, sous licence MIT, est disponible sur un [dépôt GitHub](https://github.com/CFMTech/pytest-monitor) et son auteur, Jean-Sébastien Dieu, est ouvert aux [contributions externes](https://pytest-monitor.readthedocs.io/en/latest/contributing.html).


_Happy testing !_

----
> _Fin de l’article et liste de liens qui seront publiés en bas de l’article_

- [Projet pytest-mmonitor (dépôt git)](https://github.com/CFMTech/pytest-monitor)
- [pytest-monitor version 1.1.1](https://github.com/CFMTech/pytest-monitor/releases)
- [Documentation de pytest-monitor](https://pytest-monitor.readthedocs.io/en/latest/index.html)
- [Pytest (site web)](https://docs.pytest.org/)

