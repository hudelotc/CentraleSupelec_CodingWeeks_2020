## Pytest ne marche pas
(FAQ 3A INFONUM)
* As-tu installé Pytest dans le bon interpréteur ? 
* As-tu bien Python dans ton PATH ? (voir [problèmes de path](https://github.com/LoicPoullain/je-code/blob/master/regler-les-problemes-de-path.md))
*  As-tu bien la même distribution (version) de Python sélectionnée lors de l'installation dePytest, et sur VSCode / ton terminal ? Il faut vérifier que Pytest a bien été installée sur ladistribution qu'utilise ton terminal.(voir [python et environnement](https://github.com/hudelotc/CentraleSupelec_CodingWeeks_2020/blob/main/pythonversion.md))
* As-tu une commande de la forme :```
pytest --cov=src --cov-report html tests/test_grid_2048.py
```
* Je veux lancer plusieurs tests :
```pytest --cov=src --cov-report html tests/test_*.py 
```

Si tu es sous autre chose que Windows, utilise une "wildcard" (*) pour exécuter la commande sur tous lesfichiers qui s'appellent "test_quelquechose.py"
* Le wildcard ne marche pas : tu es probablement
	* dans le mauvais dossier : tes fichiers tests sont-ils dans un dossier test ? Es-tutoi-même dans le fichier parent de test ? Utilise `ls` (voir [Cheatsheet Bash](https://github.com/hudelotc/CentraleSupelec_CodingWeeks_2020/blob/main/bash.md))pour vérifier.
	* dans un shell Windows qui ne supporte pas les wildcards. Utilise```pytest --cov=src --cov-report html tests/
```

Et pour un tuto plus détaillé c'est [ici](https://openclassrooms.com/fr/courses/4425126-testez-votre-projet-avec-python/4435144-ajoutez-des-tests-avec-pytest).