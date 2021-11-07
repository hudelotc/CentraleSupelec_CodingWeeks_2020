# Gitlab avec une clé SSH

**Pourquoi ?**

Pour éviter de devoir mettre ses identifiants à chaque `push / pull` comme c'est le cas avec https.

**Comment ?**

 En utilisant le terminal (voir [Cheatsheet Bash](./bash.md)) et en suivant ce [tutoriel](https://docs.gitlab.com/ee/ssh/).

Les principales étapes sont données ci-dessous.

## Générer une clé SSH

 Dans un terminal :`ssh-keygen -t ed25519 -C "<adresse mail>" `, cela génère une clé ssh chiffrée avec ed25519,remplacez <adresse mail> par votre adresse cs - c'est juste pour se rappeler de la clé ssh

*  Toujours faire entrée sur les choix proposés et laisser une passphrase vide.
*  Vous avez le choix entre clé RSA ou clé ed25519. Si vous connaissez pas la différence, faites	la ed25519. Si vous voulez faire la RSA, les commandes sont similaires (voir par exemple [ici](https://docs.gitlab.com/ee/ssh/))
*  Si vous modifiez les choix par défaut, la commande suivante pour récupérer votre clépublique ne marchera pas. 
	* Si par miracle vous arrivez à récupérer votre clé quand même à l'aide du terminal, il ya de grandes chances que vous vous preniez une erreur de permission denied(publickey) ( voir cette [erreur](https://forum.gitlab.com/t/permission-denied-publickey/29670/3) ) plus tard quand vous tentez de push ou pull. Si c'est lecas, le plus simple est de générer une nouvelle clé sans changer les choix par défaut.
		*  Si vous choisissez une passphrase non vide, il faudra s'en rappeler, et la renseigner à chaque fois que vous faites un push ou pull avec git. C'est plus sur mais non nécessaire pour les coding weeks.

## Copier sa clé ssh

Dans un terminal:

*  Mac : `pbcopy < ~/.ssh/id_ed25519.pub`
*  Windows : `cat ~/.ssh/id_ed25519.pub | clip` 
*  Si vous choisissez une autre méthode, faites attention à bien copier la totalité du fichier, sans oublier le début en `ed25519` ni la fin avec votre adresse mail si elle y est.


## Ajouter votre clé ssh
Ajoutez votre clé ssh toute fraîchement copiée à votre compte gitlab. Cliquez sur votre petite icône en haut à droite, puis Settings, puis SSH Keys à gauche. Coller votre clé, donnez lui un petit nom pour vous en souvenir (pas besoin de date d'expiration). Cliquez sur Add key.Pour vos projets suivants, inutile de refaire une nouvelle clé !
* Si vous utilisez le même domaine GitLab, la clé ssh est déjà enregistrée dans votre profil (sous Settings > SSH Keys)
*  Si vous utilisez un autre domaine, ou GitHub, il suffit de copier la clé que vous avez généréprécédemment (reprendre l'étape "Copier sa clé ssh) et l'ajouter aux clés du nouveau
domaine
* Pour faire plus avancé, il est possible de créer plusieurs clés avec des permissions différentes(pour contrôler notamment la sécurité), mais ce n'est pas utile pour les codingweeks.
* Si vous avez mis une date d'expiration, elle finira par expirer toute seule. Pour les Coding Weeks,c'est pas grave de laisser traîner des clés sur le GitLab de l'école. Si vous codez plus sérieusement, avec un compte perso et des projets à vous, il vaut mieux faire attention à ne pas laissertraîner des clés, c'est potentiellement une faille de sécurité. C'est une bonne pratique de les renouveler régulièrement.


<span style="color: #26B260">**A ce stade, tous les membres du groupe devraient avoir un compte sur Gitlab et une clé SSH** </span> 
