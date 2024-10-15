# Exercice d'administration

## 1. Ajouter l'interface de la classe Choice à la console d'administration

Il s'agissait tout simplement d'ajouter la ligne `admin.site.register(Choice)` 
au fichier polls/admin.py 
pour permettre à django d'ajouter Choice au site 
d'administration. 
Petite remarque en passant, l'update du serveur de flask a 
des ratés, notamment quand on ajoute ou modifie des fichiers, 
de programme, à part les templates, celui de django détecte 
et prend en compte les modifications, y compris les fichiers 
python. Le programme est redémarré silencieusement
Avec flask, il faut redémarrer le serveur, ce qui n'est pas 
le cas avec django.
## 2. Tester l'interface
* J'ai rajouté 5 question, et 3 choix par question, fait des 
modifications. 
C'est bien sûr plus "convivial" qu'avec le shell de 
django, mais ça doit pouvoir être amélioré avec un 
formulaire dédié ou en amendant celui d'admin. Pour la suppression l'interface 
d'admin convient à mon avis, pour une modification à la volée aussi, mais pas pour de multiples 
ajouts àmha..

## 3. Inventaire
* Tous les attributs sont affichable, mais on ne peut pas filtrer suivant les 
attributs, ni trier. On ne peut faire de recherche suivant aucun champ. 
