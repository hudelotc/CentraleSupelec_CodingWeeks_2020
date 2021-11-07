# Gitlab avec une clé SSH

**Pourquoi ?**

Pour éviter de devoir mettre ses identifiants à chaque `push / pull` comme c'est le cas avec https.

**Comment ?**

 En utilisant le terminal (voir [Cheatsheet Bash](./bash.md)) et en suivant ce [tutoriel](https://docs.gitlab.com/ee/ssh/).

Les principales étapes sont données ci-dessous.

## Générer une clé SSH

 Dans un terminal :

*  Toujours faire entrée sur les choix proposés et laisser une passphrase vide.
*  Vous avez le choix entre clé RSA ou clé ed25519. Si vous connaissez pas la différence, faites	la ed25519. Si vous voulez faire la RSA, les commandes sont similaires (voir par exemple [ici](https://docs.gitlab.com/ee/ssh/))
*  Si vous modifiez les choix par défaut, la commande suivante pour récupérer votre clé
	* Si par miracle vous arrivez à récupérer votre clé quand même à l'aide du terminal, il y
		*  Si vous choisissez une passphrase non vide, il faudra s'en rappeler, et la renseigner à chaque fois que vous faites un push ou pull avec git. C'est plus sur mais non nécessaire pour les coding weeks.

## Copier sa clé ssh

Dans un terminal:

*  Mac : `pbcopy < ~/.ssh/id_ed25519.pub`
*  Windows : `cat ~/.ssh/id_ed25519.pub | clip` 
*  Si vous choisissez une autre méthode, faites attention à bien copier la totalité du fichier, sans oublier le début en `ed25519` ni la fin avec votre adresse mail si elle y est.


## Ajouter votre clé ssh


*  Si vous utilisez un autre domaine, ou GitHub, il suffit de copier la clé que vous avez généré
domaine
* Pour faire plus avancé, il est possible de créer plusieurs clés avec des permissions différentes
* Si vous avez mis une date d'expiration, elle finira par expirer toute seule. Pour les Coding Weeks,c'est pas grave de laisser traîner des clés sur le GitLab de l'école. Si vous codez plus sérieusement, avec un compte perso et des projets à vous, il vaut mieux faire attention à ne pas laissertraîner des clés, c'est potentiellement une faille de sécurité. C'est une bonne pratique de les renouveler régulièrement.


<span style="color: #26B260">**A ce stade, tous les membres du groupe devraient avoir un compte sur Gitlab et une clé SSH** </span> 