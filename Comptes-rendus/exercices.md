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

## 4.admin.py : `from django.contrib import admin

from .models import Question, Choice

class QuestionAdmin(admin.ModelAdmin):
    list_display = ['question_text', 'pub_date']
    list_filter = ['question_text', 'pub_date']
    ordering = ['pub_date', 'question_text']
    search_fields = ['question_text', 'pub_date']


class ChoiceAdmin(admin.ModelAdmin):
    list_display = ['question', 'choice_text', 'votes']
    list_filter = ['question', 'choice_text', 'votes']
    ordering = ['question', 'choice_text', 'votes']
    search_fields = ['choice_text']

admin.site.register(Question, QuestionAdmin)
admin.site.register(Choice, ChoiceAdmin)`

## 5. Administration
Avec ce réglage, l'utilisateur ne peut pas se connecter. 

## 6. Contrôle d'accès
Avec le statut d'équipier et en ne lui ajoutant aucun droit supplémentaire, il peut se 
connecter mais la console d'admin lui indique qu'il ne peut rien consulter et rien modifier.

## 7. Administration
En faisant passer le compte d'actif à non actif, l'utilisateur ne peut pas se connecter