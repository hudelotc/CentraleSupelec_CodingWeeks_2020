# Solution 1: désactiver SSL


A la place d'utiliser la commande `git clone`, utilisez ces commandes :

```
mkdir nom_de_votre_projet 
cd nom_de_votre_projet
git init
git remote add origin "ladresse_du_depot_qui_commence_par_https"
git config http.sslVerify false
git pull origin master # cela peut prendre un peu de temps
```