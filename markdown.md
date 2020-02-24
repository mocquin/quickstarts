# Quickstart
```markdown
# Titre
- liste 1
- liste 2
*important* _important_
**tres important** __tres important__
~~rayé~~
```


# Titres
Un titre commence par un dièze, il existe 6 niveaux de titres, donné par le nombre de dièze:
```markdown
# Titre de niveau 1
## Titre de niveau 2
### Titre de niveau 3
#### Titre de niveau 4
##### Titre de niveau 5
###### Titre de niveau 6
```

# Listes
On peut créer plusieurs types de listes ; les listes non-ordonnées, les listes ordonnées. Et faire des sous-listes:

Liste non-ordonnée : (une liste ordonnée peut être déclarée à l'aide d'un "+", d'un "-" ou d'un "*" :
- element 1
- element 2
- element 3
* element 4
+ element 5

Liste ordonée : les listes ordonnées sont déclarées à l'aide d'un chiffre puis d'un point "1.": 
1. element 1
2. element 2
3. element 3
5. element 4

Sous liste : pour créer une sous-liste, il suffit d'indenter les élements qui deviennent des sous listes :
1. Niveau 1 element 1
 1. Niveau 2 element 1
    1. Niveau 3 element 1
      1. Niveau 3 element 2  
      a. test  
      b. test
   1. Niveau 2 element 2


# Code
Code inline  
Pour insérer du code dans une ligne, entourer le code par 3 apostrophes inverse (alt Gr + 7). Par exemple, une déclaration en code python pêut etre afficher dans un paragraphe ```ma_variable = 5``` simplement.

Code block
Pour insérer un bloc de code, il suffit de l'entourer par les 3 apostrophes inverses, sur plusieurs lignes. On peut indiquer le nom du language pour avoir de la coloration. Cela dépend de l'afficheur markdown utilisé, mais le notebook supporte le Github Flavored Markdown, on peut donc utiliser cette fonction :

```python
# Ceci est un bloc de code python
ma_variable = 5
ma_variable = ma_variable + 10
```

On peut également créer un bloc de code en indentant de 4 espaces:
    # Ceci est du code, identé avec 4 espaces

# Mise en forme du texte

Pour mettre du texte en italique, l'entourer par une astérisque ou un underscore :  
*texte entre une astérisque*  
_texte entre un underscore_  
<font color=blue>Coucou bleu</font>  
Pour mettre du texte en gras, l'entourer par un double astérisque ou un double underscore :  
**texte entre 2 astérisques**  
__texte entre 2 underscore__

Pour rayer un texte, l'entourer par un double tilde :  
~~Texte rayé~~  

# Liens 
Un lien commence par un texte entre crochet qui représente ce qui sera écrit sur le lien. Ensuite vient l'adresse effective du lien : (on peut ajouter un titre au lien, qui s'affiche lorsqu'on survole le lien, en ajoutant le texte après l'adresse entre guillemets)  

[Lien vers un site](https://www.google.com "Google's Homepage")  
[Lien vers un fichier/dossier](../)

On peut également indiquer l'adresse du lien avec une table de liens, en indiquant entre crochet le nom du lien dans la table qui est écrite plus bas :  

[Texte du second lien, toujours entre crochet][Nom-référence du lien, entre crochet accolé]  
[Reference direct du lien]  

On ajoute ensuite le tableau de correspondance entre la référence et le lien :  
[Nom-référence du lien, entre crochet accolé]: https://www.google.com  
[Reference direct du lien]: https://www.google.com  

Pour mettre un lien inline, il suffit d'écrire le lien tel quel https://www.google.com ou de l'entourer de <> <https://www.google.com>.

Je reçoit 10 fois plus de trafic de [Google] [1] que de [Yahoo] [2] ou [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"


# Images
Pour insérer une image, il suffit d'utiliser un lien vers cette image précédé d'un point d'exclamation :
![Texte du lien](https://www.google.fr/imgres?imgurl=https%3A%2F%2Fwww.python.org%2Fstatic%2Fopengraph-icon-200x200.png&imgrefurl=https%3A%2F%2Fwww.python.org%2F&docid=Fvb7Gz_c4rwxjM&tbnid=vZKJO2_oBP1evM%3A&vet=10ahUKEwiSpLWv6eDVAhXLVxoKHUisA8wQMwg6KAAwAA..i&w=200&h=200&bih=953&biw=1920&q=python&ved=0ahUKEwiSpLWv6eDVAhXLVxoKHUisA8wQMwg6KAAwAA&iact=mrc&uact=8 "Logo python pris sur google")

On peut également utiliser une référence (comme les liens classiques):
![Texte du lien][Photo1]

[Photo1]: https://www.google.fr/imgres?imgurl=https%3A%2F%2Fwww.python.org%2Fstatic%2Fopengraph-icon-200x200.png&imgrefurl=https%3A%2F%2Fwww.python.org%2F&docid=Fvb7Gz_c4rwxjM&tbnid=vZKJO2_oBP1evM%3A&vet=10ahUKEwiSpLWv6eDVAhXLVxoKHUisA8wQMwg6KAAwAA..i&w=200&h=200&bih=953&biw=1920&q=python&ved=0ahUKEwiSpLWv6eDVAhXLVxoKHUisA8wQMwg6KAAwAA&iact=mrc&uact=8 "Logo python pris sur google"

# Vidéo
On peut ajouter une vidéo à l'aide du HTML :
<a href="http://www.youtube.com/watch?feature=player_embedded&v=bj5ufMLKYhk
" target="_blank"><img src="http://img.youtube.com/vi/bj5ufMLKYhk/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

Ou avec un lien markdown
[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/bj5ufMLKYhk/0.jpg)](http://www.youtube.com/watch?v=bj5ufMLKYhk)

# Quote
Pour mettre un bloc de citation, commencer par un caractère supérieur :
> Ceci est un bloc de citation.
Suite du bloc de citation

Pour terminer un bloc de citation, il faut sauter une ligne dans le code Markdown
> Ceci est un autre bloc de citation plus long

# Retour à la ligne
De base, il n'y a pas de retour à la ligne.
Un retour à la ligne ne s'affichera pas.
Pour avoir un vrai retour à la ligne, il faut laisser 2 espaces "  " à la fin de la ligne. (deux espaces ici -->)  
On a ainsi un retour à la ligne
On peut aussi placer un br entre crochet '<br>' pour aller à a ligne


# Latex 
Pour afficher du latex en inline, entourer le texte par un dollar : $e^{i\pi} + 1 = \cos(\lambda)$  
Pour afficher du latex sur sa propre ligne (et centré), entourer le texte par un double dollar : $$e^x=\sum_{i=0}^\infty \frac{e^{334}}{i+1!}x^i$$


# Lignes
Pour faire une ligne horizontale, mettre 3 astérisques à la suite séparée d'un espace sur une ligne :

Astérisques
***

Tiret
--- 
Underscore
___



# HTML
On peut ajouter du HTML : 
<table>
<tr>
<th>Header 1</th>
<th>Header 2</th>
</tr>
<tr>
<td>row 1, cell 1</td>
<td>row 1, cell 2</td>
</tr>
<tr>
<td>row 2, cell 1</td>
<td>row 2, cell 2</td>
</tr>
</table>



# Tableaux
On créer un tableau à l'aide des caractères | (MAJ+ALT+L)

|Première colone | Deuxieme colone|
|----------------|----------------|
|case 1          |         case 2 |



# Résumé

|Ecriture                 | Signification    |Alternative|
|--------------------------------------------------------|
|`# Tire de niveau 1`     |Titre de niveau 1 |-|
|`## Tire de niveau 2`    |Titre de niveau 2 |-|
|`### Tire de niveau 3`   |Titre de niveau 3 |-|
|`#### Tire de niveau 4`  |Titre de niveau 4 |-|
|`##### Tire de niveau 5` |Titre de niveau 5 |-|
|`###### Tire de niveau 6`|Titre de niveau 6 |-|
|` - Liste non ordonnée`  |Liste non ordonnée|` + ou *`|
|` 1. Liste ordonnée`     |Liste ordonéne    |`A. ou a.`| 
|`Code Inline`            |Code inline       |` ``` `|
|```python print("code sur plusieurs lignes ```|Code block| indentation de 4 espaces|
|`~~Texte rayé~~`| Texte rayé | |
|`*Texte en italique*`| Texte en itallique | avec \_| 
|`**Texte en gras**`| Texte en gras | avec \_\_ |
|`> Citation`| Citation/Indentation | |
|`  `|Retour à a ligne | \<\br> |
|`<font color=blue>Coucou bleu</font>` |Couleur||
|` $Latex inline$` | Latex inline | |
|` $$Latex bloc$$` | Latex block | |  
|`---`| Ligne horizontale | `***`ou `___`| |


# Ressources
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet - DONE  
http://datascience.ibm.com/blog/markdown-for-jupyter-notebooks-cheatsheet/ - DONE
http://nbviewer.jupyter.org/github/ipython/ipython/blob/3.x/examples/Notebook/Working%20With%20Markdown%20Cells.ipynb - DONE  
https://daringfireball.net/projects/markdown/
https://daringfireball.net/projects/markdown/syntax  
https://michelf.ca/projets/php-markdown/syntaxe/  
