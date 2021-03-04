# Table of Contents
 <p><div class="lev1 toc-item"><a href="#VERSIONS-et-paths" data-toc-modified-id="VERSIONS-et-paths-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>VERSIONS et paths</a></div><div class="lev1 toc-item"><a href="#Syntaxe-et-convention-d'écriture" data-toc-modified-id="Syntaxe-et-convention-d'écriture-2"><span class="toc-item-num">2&nbsp;&nbsp;</span>Syntaxe et convention d'écriture</a></div><div class="lev2 toc-item"><a href="#Commentaire" data-toc-modified-id="Commentaire-21"><span class="toc-item-num">2.1&nbsp;&nbsp;</span>Commentaire</a></div><div class="lev2 toc-item"><a href="#Encodage" data-toc-modified-id="Encodage-22"><span class="toc-item-num">2.2&nbsp;&nbsp;</span>Encodage</a></div><div class="lev1 toc-item"><a href="#Variables-Python" data-toc-modified-id="Variables-Python-3"><span class="toc-item-num">3&nbsp;&nbsp;</span>Variables Python</a></div><div class="lev2 toc-item"><a href="#Booléen-True-et-False" data-toc-modified-id="Booléen-True-et-False-31"><span class="toc-item-num">3.1&nbsp;&nbsp;</span>Booléen <code>True</code> et <code>False</code></a></div><div class="lev2 toc-item"><a href="#Chaines-de-caractères-str" data-toc-modified-id="Chaines-de-caractères-str-32"><span class="toc-item-num">3.2&nbsp;&nbsp;</span>Chaines de caractères <code>str</code></a></div><div class="lev2 toc-item"><a href="#Entiers-et-Réels-avec-int-et-float" data-toc-modified-id="Entiers-et-Réels-avec-int-et-float-33"><span class="toc-item-num">3.3&nbsp;&nbsp;</span>Entiers et Réels avec <code>int</code> et <code>float</code></a></div><div class="lev2 toc-item"><a href="#Tuples" data-toc-modified-id="Tuples-34"><span class="toc-item-num">3.4&nbsp;&nbsp;</span>Tuples</a></div><div class="lev2 toc-item"><a href="#Liste-list" data-toc-modified-id="Liste-list-35"><span class="toc-item-num">3.5&nbsp;&nbsp;</span>Liste <code>list</code></a></div><div class="lev2 toc-item"><a href="#Dictionnaires-dict" data-toc-modified-id="Dictionnaires-dict-36"><span class="toc-item-num">3.6&nbsp;&nbsp;</span>Dictionnaires <code>dict</code></a></div><div class="lev2 toc-item"><a href="#Ensemble-avec-set" data-toc-modified-id="Ensemble-avec-set-37"><span class="toc-item-num">3.7&nbsp;&nbsp;</span>Ensemble avec <code>set</code></a></div><div class="lev1 toc-item"><a href="#Opérateurs,-boucles-et-conditions" data-toc-modified-id="Opérateurs,-boucles-et-conditions-4"><span class="toc-item-num">4&nbsp;&nbsp;</span>Opérateurs, boucles et conditions</a></div><div class="lev2 toc-item"><a href="#Structures-conditionelles" data-toc-modified-id="Structures-conditionelles-41"><span class="toc-item-num">4.1&nbsp;&nbsp;</span>Structures conditionelles</a></div><div class="lev3 toc-item"><a href="#Structures-de-if" data-toc-modified-id="Structures-de-if-411"><span class="toc-item-num">4.1.1&nbsp;&nbsp;</span>Structures de <code>if</code></a></div><div class="lev2 toc-item"><a href="#Opérateurs" data-toc-modified-id="Opérateurs-42"><span class="toc-item-num">4.2&nbsp;&nbsp;</span>Opérateurs</a></div><div class="lev3 toc-item"><a href="#Opérateurs-classiques" data-toc-modified-id="Opérateurs-classiques-421"><span class="toc-item-num">4.2.1&nbsp;&nbsp;</span>Opérateurs classiques</a></div><div class="lev3 toc-item"><a href="#Opérateurs-booléens--or,-and,-not" data-toc-modified-id="Opérateurs-booléens--or,-and,-not-422"><span class="toc-item-num">4.2.2&nbsp;&nbsp;</span>Opérateurs booléens  <code>or</code>, <code>and</code>, <code>not</code></a></div><div class="lev3 toc-item"><a href="#Opérateurs-bitwise" data-toc-modified-id="Opérateurs-bitwise-423"><span class="toc-item-num">4.2.3&nbsp;&nbsp;</span>Opérateurs bitwise</a></div><div class="lev3 toc-item"><a href="#Opérateurs-de-comparaison" data-toc-modified-id="Opérateurs-de-comparaison-424"><span class="toc-item-num">4.2.4&nbsp;&nbsp;</span>Opérateurs de comparaison</a></div><div class="lev1 toc-item"><a href="#Boucles" data-toc-modified-id="Boucles-5"><span class="toc-item-num">5&nbsp;&nbsp;</span>Boucles</a></div><div class="lev2 toc-item"><a href="#Boucle-while" data-toc-modified-id="Boucle-while-51"><span class="toc-item-num">5.1&nbsp;&nbsp;</span>Boucle <code>while</code></a></div><div class="lev2 toc-item"><a href="#Boucle-for" data-toc-modified-id="Boucle-for-52"><span class="toc-item-num">5.2&nbsp;&nbsp;</span>Boucle <code>for</code></a></div><div class="lev2 toc-item"><a href="#Interompre-et-continuer-une-boucle-break-et-continue" data-toc-modified-id="Interompre-et-continuer-une-boucle-break-et-continue-53"><span class="toc-item-num">5.3&nbsp;&nbsp;</span>Interompre et continuer une boucle <code>break</code> et <code>continue</code></a></div><div class="lev3 toc-item"><a href="#break" data-toc-modified-id="break-531"><span class="toc-item-num">5.3.1&nbsp;&nbsp;</span><code>break</code></a></div><div class="lev3 toc-item"><a href="#continue" data-toc-modified-id="continue-532"><span class="toc-item-num">5.3.2&nbsp;&nbsp;</span><code>continue</code></a></div><div class="lev1 toc-item"><a href="#Exceptions" data-toc-modified-id="Exceptions-6"><span class="toc-item-num">6&nbsp;&nbsp;</span>Exceptions</a></div><div class="lev2 toc-item"><a href="#Bloc-try-et-except" data-toc-modified-id="Bloc-try-et-except-61"><span class="toc-item-num">6.1&nbsp;&nbsp;</span>Bloc <code>try</code> et <code>except</code></a></div><div class="lev2 toc-item"><a href="#Assertion-avec-assert" data-toc-modified-id="Assertion-avec-assert-62"><span class="toc-item-num">6.2&nbsp;&nbsp;</span>Assertion avec <code>assert</code></a></div><div class="lev2 toc-item"><a href="#Lever-une-exception-avec-raise" data-toc-modified-id="Lever-une-exception-avec-raise-63"><span class="toc-item-num">6.3&nbsp;&nbsp;</span>Lever une exception avec <code>raise</code></a></div><div class="lev1 toc-item"><a href="#Itérateurs-et-générateurs" data-toc-modified-id="Itérateurs-et-générateurs-7"><span class="toc-item-num">7&nbsp;&nbsp;</span>Itérateurs et générateurs</a></div><div class="lev2 toc-item"><a href="#Itérateur-avec-iter-et-next" data-toc-modified-id="Itérateur-avec-iter-et-next-71"><span class="toc-item-num">7.1&nbsp;&nbsp;</span>Itérateur avec <code>iter</code> et <code>next</code></a></div><div class="lev3 toc-item"><a href="#Principe-des-itérateurs" data-toc-modified-id="Principe-des-itérateurs-711"><span class="toc-item-num">7.1.1&nbsp;&nbsp;</span>Principe des itérateurs</a></div><div class="lev4 toc-item"><a href="#Fonctions-et-méthodes-utiles" data-toc-modified-id="Fonctions-et-méthodes-utiles-7111"><span class="toc-item-num">7.1.1.1&nbsp;&nbsp;</span>Fonctions et méthodes utiles</a></div><div class="lev2 toc-item"><a href="#Générateur-avec-yield" data-toc-modified-id="Générateur-avec-yield-72"><span class="toc-item-num">7.2&nbsp;&nbsp;</span>Générateur avec <code>yield</code></a></div><div class="lev1 toc-item"><a href="#Contexte-manager-:-with" data-toc-modified-id="Contexte-manager-:-with-8"><span class="toc-item-num">8&nbsp;&nbsp;</span>Contexte manager : <code>with</code></a></div><div class="lev2 toc-item"><a href="#Méthodes-enter()-et-exit()" data-toc-modified-id="Méthodes-enter()-et-exit()-81"><span class="toc-item-num">8.1&nbsp;&nbsp;</span>Méthodes <strong>enter</strong>() et <strong>exit</strong>()</a></div><div class="lev2 toc-item"><a href="#Mot-clé-as" data-toc-modified-id="Mot-clé-as-82"><span class="toc-item-num">8.2&nbsp;&nbsp;</span>Mot clé <code>as</code></a></div><div class="lev2 toc-item"><a href="#Context-manager-en-fonction-:-module-contextlib" data-toc-modified-id="Context-manager-en-fonction-:-module-contextlib-83"><span class="toc-item-num">8.3&nbsp;&nbsp;</span>Context manager en fonction : module <code>contextlib</code></a></div><div class="lev1 toc-item"><a href="#Fonctions" data-toc-modified-id="Fonctions-9"><span class="toc-item-num">9&nbsp;&nbsp;</span>Fonctions</a></div><div class="lev2 toc-item"><a href="#Définir-une-fonction" data-toc-modified-id="Définir-une-fonction-91"><span class="toc-item-num">9.1&nbsp;&nbsp;</span>Définir une fonction</a></div><div class="lev2 toc-item"><a href="#Fonctions-lambda" data-toc-modified-id="Fonctions-lambda-92"><span class="toc-item-num">9.2&nbsp;&nbsp;</span>Fonctions <code>lambda</code></a></div><div class="lev1 toc-item"><a href="#Modules-et-packages" data-toc-modified-id="Modules-et-packages-10"><span class="toc-item-num">10&nbsp;&nbsp;</span>Modules et packages</a></div><div class="lev2 toc-item"><a href="#Modules" data-toc-modified-id="Modules-101"><span class="toc-item-num">10.1&nbsp;&nbsp;</span>Modules</a></div><div class="lev3 toc-item"><a href="#Mot-clé-import,-from-et-as" data-toc-modified-id="Mot-clé-import,-from-et-as-1011"><span class="toc-item-num">10.1.1&nbsp;&nbsp;</span>Mot-clé <code>import</code>, <code>from</code> et <code>as</code></a></div><div class="lev3 toc-item"><a href="#Créer-ses-propres-modules" data-toc-modified-id="Créer-ses-propres-modules-1012"><span class="toc-item-num">10.1.2&nbsp;&nbsp;</span>Créer ses propres modules</a></div><div class="lev2 toc-item"><a href="#Packages" data-toc-modified-id="Packages-102"><span class="toc-item-num">10.2&nbsp;&nbsp;</span>Packages</a></div><div class="lev1 toc-item"><a href="#Fichiers" data-toc-modified-id="Fichiers-11"><span class="toc-item-num">11&nbsp;&nbsp;</span>Fichiers</a></div><div class="lev2 toc-item"><a href="#Fichiers-et-dossiers" data-toc-modified-id="Fichiers-et-dossiers-111"><span class="toc-item-num">11.1&nbsp;&nbsp;</span>Fichiers et dossiers</a></div><div class="lev1 toc-item"><a href="#Classes-et-méthodes" data-toc-modified-id="Classes-et-méthodes-12"><span class="toc-item-num">12&nbsp;&nbsp;</span>Classes et méthodes</a></div><div class="lev2 toc-item"><a href="#Classes" data-toc-modified-id="Classes-121"><span class="toc-item-num">12.1&nbsp;&nbsp;</span>Classes</a></div><div class="lev2 toc-item"><a href="#Attribut-de-classe" data-toc-modified-id="Attribut-de-classe-122"><span class="toc-item-num">12.2&nbsp;&nbsp;</span>Attribut de classe</a></div><div class="lev2 toc-item"><a href="#Méthode-de-classe" data-toc-modified-id="Méthode-de-classe-123"><span class="toc-item-num">12.3&nbsp;&nbsp;</span>Méthode de classe</a></div><div class="lev2 toc-item"><a href="#Méthode-statique" data-toc-modified-id="Méthode-statique-124"><span class="toc-item-num">12.4&nbsp;&nbsp;</span>Méthode statique</a></div><div class="lev2 toc-item"><a href="#Méthodes-spéciales" data-toc-modified-id="Méthodes-spéciales-125"><span class="toc-item-num">12.5&nbsp;&nbsp;</span>Méthodes spéciales</a></div><div class="lev3 toc-item"><a href="#Initialiser-un-objet-avec-__init__" data-toc-modified-id="Initialiser-un-objet-avec-__init__-1251"><span class="toc-item-num">12.5.1&nbsp;&nbsp;</span>Initialiser un objet avec <code>__init__</code></a></div><div class="lev3 toc-item"><a href="#Supprimer-un-objet-avec-__del__" data-toc-modified-id="Supprimer-un-objet-avec-__del__-1252"><span class="toc-item-num">12.5.2&nbsp;&nbsp;</span>Supprimer un objet avec <code>__del__</code></a></div><div class="lev3 toc-item"><a href="#Représentation-avec-__repr__" data-toc-modified-id="Représentation-avec-__repr__-1253"><span class="toc-item-num">12.5.3&nbsp;&nbsp;</span>Représentation avec <code>__repr__</code></a></div><div class="lev3 toc-item"><a href="#Conversion-en-chaine-de-caractère-avec-__str__" data-toc-modified-id="Conversion-en-chaine-de-caractère-avec-__str__-1254"><span class="toc-item-num">12.5.4&nbsp;&nbsp;</span>Conversion en chaine de caractère avec <code>__str__</code></a></div><div class="lev3 toc-item"><a href="#Accès-aux-attributs-avec-__getattr__" data-toc-modified-id="Accès-aux-attributs-avec-__getattr__-1255"><span class="toc-item-num">12.5.5&nbsp;&nbsp;</span>Accès aux attributs avec <code>__getattr__</code></a></div><div class="lev3 toc-item"><a href="#Modification-des-attributs-avec-__setattr__" data-toc-modified-id="Modification-des-attributs-avec-__setattr__-1256"><span class="toc-item-num">12.5.6&nbsp;&nbsp;</span>Modification des attributs avec <code>__setattr__</code></a></div><div class="lev3 toc-item"><a href="#Suppression-des-attributs-avec-__delattr__" data-toc-modified-id="Suppression-des-attributs-avec-__delattr__-1257"><span class="toc-item-num">12.5.7&nbsp;&nbsp;</span>Suppression des attributs avec <code>__delattr__</code></a></div><div class="lev3 toc-item"><a href="#__hasattr__" data-toc-modified-id="__hasattr__-1258"><span class="toc-item-num">12.5.8&nbsp;&nbsp;</span><code>__hasattr__</code></a></div><div class="lev3 toc-item"><a href="#Méthode-d'indexing-__getitem__,-__setitem__-et-__delattr__" data-toc-modified-id="Méthode-d'indexing-__getitem__,-__setitem__-et-__delattr__-1259"><span class="toc-item-num">12.5.9&nbsp;&nbsp;</span>Méthode d'indexing <code>__getitem__</code>, <code>__setitem__</code> et <code>__delattr__</code></a></div><div class="lev3 toc-item"><a href="#Méthode-__contains__-pour-le-mot-clé-in" data-toc-modified-id="Méthode-__contains__-pour-le-mot-clé-in-12510"><span class="toc-item-num">12.5.10&nbsp;&nbsp;</span>Méthode <code>__contains__</code> pour le mot clé <code>in</code></a></div><div class="lev3 toc-item"><a href="#Méthode-__len__" data-toc-modified-id="Méthode-__len__-12511"><span class="toc-item-num">12.5.11&nbsp;&nbsp;</span>Méthode <code>__len__</code></a></div><div class="lev3 toc-item"><a href="#Objets-callable-__call__" data-toc-modified-id="Objets-callable-__call__-12512"><span class="toc-item-num">12.5.12&nbsp;&nbsp;</span>Objets callable <code>__call__</code></a></div><div class="lev3 toc-item"><a href="#Méthodes-mathématiques-__add__,-__sub,-__mul__,-__div__" data-toc-modified-id="Méthodes-mathématiques-__add__,-__sub,-__mul__,-__div__-12513"><span class="toc-item-num">12.5.13&nbsp;&nbsp;</span>Méthodes mathématiques <code>__add__</code>, <code>__sub</code>, <code>__mul__</code>, <code>__div__</code></a></div><div class="lev3 toc-item"><a href="#Méthodes-de-comparaison-__lt__,-__gt__,-__eq__" data-toc-modified-id="Méthodes-de-comparaison-__lt__,-__gt__,-__eq__-12514"><span class="toc-item-num">12.5.14&nbsp;&nbsp;</span>Méthodes de comparaison <code>__lt__</code>, <code>__gt__</code>, <code>__eq__</code></a></div><div class="lev2 toc-item"><a href="#Classe-de-base-abstraites-:-Abstract-Base-Class" data-toc-modified-id="Classe-de-base-abstraites-:-Abstract-Base-Class-126"><span class="toc-item-num">12.6&nbsp;&nbsp;</span>Classe de base abstraites : Abstract Base Class</a></div><div class="lev2 toc-item"><a href="#Attributs-spéciales" data-toc-modified-id="Attributs-spéciales-127"><span class="toc-item-num">12.7&nbsp;&nbsp;</span>Attributs spéciales</a></div><div class="lev3 toc-item"><a href="#__dict__" data-toc-modified-id="__dict__-1271"><span class="toc-item-num">12.7.1&nbsp;&nbsp;</span><code>__dict__</code></a></div><div class="lev2 toc-item"><a href="#Métaclasse" data-toc-modified-id="Métaclasse-128"><span class="toc-item-num">12.8&nbsp;&nbsp;</span>Métaclasse</a></div><div class="lev3 toc-item"><a href="#Méthodes-et-attributs-utiles-des-métaclasse" data-toc-modified-id="Méthodes-et-attributs-utiles-des-métaclasse-1281"><span class="toc-item-num">12.8.1&nbsp;&nbsp;</span>Méthodes et attributs utiles des métaclasse</a></div><div class="lev1 toc-item"><a href="#Héritage" data-toc-modified-id="Héritage-13"><span class="toc-item-num">13&nbsp;&nbsp;</span>Héritage</a></div><div class="lev2 toc-item"><a href="#Héritage" data-toc-modified-id="Héritage-131"><span class="toc-item-num">13.1&nbsp;&nbsp;</span>Héritage</a></div><div class="lev3 toc-item"><a href="#Fonctions-utiles" data-toc-modified-id="Fonctions-utiles-1311"><span class="toc-item-num">13.1.1&nbsp;&nbsp;</span>Fonctions utiles</a></div><div class="lev4 toc-item"><a href="#Appartenance-à-une-classe-issubclass()et-isinstance" data-toc-modified-id="Appartenance-à-une-classe-issubclass()et-isinstance-13111"><span class="toc-item-num">13.1.1.1&nbsp;&nbsp;</span>Appartenance à une classe <code>issubclass()</code>et <code>isinstance</code></a></div><div class="lev2 toc-item"><a href="#MRO-:-Method-Resolution-Order" data-toc-modified-id="MRO-:-Method-Resolution-Order-132"><span class="toc-item-num">13.2&nbsp;&nbsp;</span>MRO : Method Resolution Order</a></div><div class="lev1 toc-item"><a href="#Portée-des-variables-et-espaces-de-noms" data-toc-modified-id="Portée-des-variables-et-espaces-de-noms-14"><span class="toc-item-num">14&nbsp;&nbsp;</span>Portée des variables et espaces de noms</a></div><div class="lev3 toc-item"><a href="#Variables-globales-avec-global" data-toc-modified-id="Variables-globales-avec-global-1401"><span class="toc-item-num">14.0.1&nbsp;&nbsp;</span>Variables globales avec <code>global</code></a></div><div class="lev1 toc-item"><a href="#Objets-Python-de-base" data-toc-modified-id="Objets-Python-de-base-15"><span class="toc-item-num">15&nbsp;&nbsp;</span>Objets Python de base</a></div><div class="lev2 toc-item"><a href="#Mots-clés-python" data-toc-modified-id="Mots-clés-python-151"><span class="toc-item-num">15.1&nbsp;&nbsp;</span>Mots-clés python</a></div><div class="lev3 toc-item"><a href="#Liste-des-mots-clé-python" data-toc-modified-id="Liste-des-mots-clé-python-1511"><span class="toc-item-num">15.1.1&nbsp;&nbsp;</span>Liste des mots-clé python</a></div><div class="lev3 toc-item"><a href="#Détails-sur-les-mots-clés-python" data-toc-modified-id="Détails-sur-les-mots-clés-python-1512"><span class="toc-item-num">15.1.2&nbsp;&nbsp;</span>Détails sur les mots-clés python</a></div><div class="lev4 toc-item"><a href="#Fonction-lambda" data-toc-modified-id="Fonction-lambda-15121"><span class="toc-item-num">15.1.2.1&nbsp;&nbsp;</span>Fonction <code>lambda</code></a></div><div class="lev2 toc-item"><a href="#Variables-python" data-toc-modified-id="Variables-python-152"><span class="toc-item-num">15.2&nbsp;&nbsp;</span>Variables python</a></div><div class="lev3 toc-item"><a href="#Variables--__name__-et-__main__" data-toc-modified-id="Variables--__name__-et-__main__-1521"><span class="toc-item-num">15.2.1&nbsp;&nbsp;</span>Variables  <code>__name__</code> et <code>__main__</code></a></div><div class="lev2 toc-item"><a href="#Fonctions-spéciales-python" data-toc-modified-id="Fonctions-spéciales-python-153"><span class="toc-item-num">15.3&nbsp;&nbsp;</span>Fonctions spéciales python</a></div><div class="lev3 toc-item"><a href="#Liste-des-fonctions-spéciales-python" data-toc-modified-id="Liste-des-fonctions-spéciales-python-1531"><span class="toc-item-num">15.3.1&nbsp;&nbsp;</span>Liste des fonctions spéciales python</a></div><div class="lev3 toc-item"><a href="#Détails-sur-les-fonctions-spéciales" data-toc-modified-id="Détails-sur-les-fonctions-spéciales-1532"><span class="toc-item-num">15.3.2&nbsp;&nbsp;</span>Détails sur les fonctions spéciales</a></div><div class="lev4 toc-item"><a href="#Fonctions-globals()-et-locals()" data-toc-modified-id="Fonctions-globals()-et-locals()-15321"><span class="toc-item-num">15.3.2.1&nbsp;&nbsp;</span>Fonctions <code>globals()</code> et <code>locals()</code></a></div><div class="lev4 toc-item"><a href="#Référence-et-identifiants-id()-et-is()" data-toc-modified-id="Référence-et-identifiants-id()-et-is()-15322"><span class="toc-item-num">15.3.2.2&nbsp;&nbsp;</span>Référence et identifiants <code>id()</code> et <code>is()</code></a></div><div class="lev4 toc-item"><a href="#Fonction-dir()" data-toc-modified-id="Fonction-dir()-15323"><span class="toc-item-num">15.3.2.3&nbsp;&nbsp;</span>Fonction <code>dir()</code></a></div><div class="lev4 toc-item"><a href="#Informations-sur-un-objet-help()" data-toc-modified-id="Informations-sur-un-objet-help()-15324"><span class="toc-item-num">15.3.2.4&nbsp;&nbsp;</span>Informations sur un objet <code>help()</code></a></div><div class="lev1 toc-item"><a href="#Decorators" data-toc-modified-id="Decorators-16"><span class="toc-item-num">16&nbsp;&nbsp;</span>Decorators</a></div><div class="lev2 toc-item"><a href="#Décorateur-simple" data-toc-modified-id="Décorateur-simple-161"><span class="toc-item-num">16.1&nbsp;&nbsp;</span>Décorateur simple</a></div><div class="lev2 toc-item"><a href="#Décorateur-sur-fonction-avec-paramètres" data-toc-modified-id="Décorateur-sur-fonction-avec-paramètres-162"><span class="toc-item-num">16.2&nbsp;&nbsp;</span>Décorateur sur fonction avec paramètres</a></div><div class="lev2 toc-item"><a href="#Décorateur-avec-paramètre" data-toc-modified-id="Décorateur-avec-paramètre-163"><span class="toc-item-num">16.3&nbsp;&nbsp;</span>Décorateur avec paramètre</a></div><div class="lev2 toc-item"><a href="#Décorateur-de-classe" data-toc-modified-id="Décorateur-de-classe-164"><span class="toc-item-num">16.4&nbsp;&nbsp;</span>Décorateur de classe</a></div><div class="lev2 toc-item"><a href="#Décorateurs-utiles" data-toc-modified-id="Décorateurs-utiles-165"><span class="toc-item-num">16.5&nbsp;&nbsp;</span>Décorateurs utiles</a></div><div class="lev3 toc-item"><a href="#Singleton" data-toc-modified-id="Singleton-1651"><span class="toc-item-num">16.5.1&nbsp;&nbsp;</span>Singleton</a></div><div class="lev3 toc-item"><a href="#Controleur-de-type" data-toc-modified-id="Controleur-de-type-1652"><span class="toc-item-num">16.5.2&nbsp;&nbsp;</span>Controleur de type</a></div><div class="lev2 toc-item"><a href="#Décorateurs-prédéfinis" data-toc-modified-id="Décorateurs-prédéfinis-166"><span class="toc-item-num">16.6&nbsp;&nbsp;</span>Décorateurs prédéfinis</a></div><div class="lev1 toc-item"><a href="#Propriétés-avec-property" data-toc-modified-id="Propriétés-avec-property-17"><span class="toc-item-num">17&nbsp;&nbsp;</span>Propriétés avec <code>property</code></a></div><div class="lev1 toc-item"><a href="#Paramétrage-dynamique-:-Packing-et-Unpacking,-et-*args-et-**kwargs" data-toc-modified-id="Paramétrage-dynamique-:-Packing-et-Unpacking,-et-*args-et-**kwargs-18"><span class="toc-item-num">18&nbsp;&nbsp;</span>Paramétrage dynamique : Packing et Unpacking, et <code>*args</code> et <code>**kwargs</code></a></div><div class="lev2 toc-item"><a href="#Principe-de-l'unpacking-:-appel-d'une-fonction-ou-affectation" data-toc-modified-id="Principe-de-l'unpacking-:-appel-d'une-fonction-ou-affectation-181"><span class="toc-item-num">18.1&nbsp;&nbsp;</span>Principe de l'unpacking : appel d'une fonction ou affectation</a></div><div class="lev2 toc-item"><a href="#Principe-du-packing-:-définition-d'une-fonction" data-toc-modified-id="Principe-du-packing-:-définition-d'une-fonction-182"><span class="toc-item-num">18.2&nbsp;&nbsp;</span>Principe du packing : définition d'une fonction</a></div><div class="lev2 toc-item"><a href="#Packing-et-Unpacking-implicite" data-toc-modified-id="Packing-et-Unpacking-implicite-183"><span class="toc-item-num">18.3&nbsp;&nbsp;</span>Packing et Unpacking implicite</a></div><div class="lev3 toc-item"><a href="#Unpacking-implicite" data-toc-modified-id="Unpacking-implicite-1831"><span class="toc-item-num">18.3.1&nbsp;&nbsp;</span>Unpacking implicite</a></div><div class="lev3 toc-item"><a href="#Packing-implicite" data-toc-modified-id="Packing-implicite-1832"><span class="toc-item-num">18.3.2&nbsp;&nbsp;</span>Packing implicite</a></div><div class="lev2 toc-item"><a href="#Packing-et-Unpacking-explicite" data-toc-modified-id="Packing-et-Unpacking-explicite-184"><span class="toc-item-num">18.4&nbsp;&nbsp;</span>Packing et Unpacking explicite</a></div><div class="lev3 toc-item"><a href="#Unpacking-explicite" data-toc-modified-id="Unpacking-explicite-1841"><span class="toc-item-num">18.4.1&nbsp;&nbsp;</span>Unpacking explicite</a></div><div class="lev3 toc-item"><a href="#Packing-explicite" data-toc-modified-id="Packing-explicite-1842"><span class="toc-item-num">18.4.2&nbsp;&nbsp;</span>Packing explicite</a></div><div class="lev1 toc-item"><a href="#Docstring-et-doctest" data-toc-modified-id="Docstring-et-doctest-19"><span class="toc-item-num">19&nbsp;&nbsp;</span>Docstring et doctest</a></div><div class="lev1 toc-item"><a href="#Bonnes-pratiques" data-toc-modified-id="Bonnes-pratiques-20"><span class="toc-item-num">20&nbsp;&nbsp;</span>Bonnes pratiques</a></div><div class="lev2 toc-item"><a href="#Règles-de-programmation" data-toc-modified-id="Règles-de-programmation-201"><span class="toc-item-num">20.1&nbsp;&nbsp;</span>Règles de programmation</a></div><div class="lev3 toc-item"><a href="#Objets-protégés-et-objets-privés" data-toc-modified-id="Objets-protégés-et-objets-privés-2011"><span class="toc-item-num">20.1.1&nbsp;&nbsp;</span>Objets protégés et objets privés</a></div><div class="lev2 toc-item"><a href="#List-comprehension" data-toc-modified-id="List-comprehension-202"><span class="toc-item-num">20.2&nbsp;&nbsp;</span>List comprehension</a></div><div class="lev2 toc-item"><a href="#Classes-concrètes-et-classes-abstraites" data-toc-modified-id="Classes-concrètes-et-classes-abstraites-203"><span class="toc-item-num">20.3&nbsp;&nbsp;</span>Classes concrètes et classes abstraites</a></div><div class="lev2 toc-item"><a href="#Conventions-d'écritures" data-toc-modified-id="Conventions-d'écritures-204"><span class="toc-item-num">20.4&nbsp;&nbsp;</span>Conventions d'écritures</a></div><div class="lev1 toc-item"><a href="#Import-et-python-path" data-toc-modified-id="Import-et-python-path-21"><span class="toc-item-num">21&nbsp;&nbsp;</span>Import et python path</a></div><div class="lev2 toc-item"><a href="#Help" data-toc-modified-id="Help-211"><span class="toc-item-num">21.1&nbsp;&nbsp;</span>Help</a></div><div class="lev2 toc-item"><a href="#Divers" data-toc-modified-id="Divers-212"><span class="toc-item-num">21.2&nbsp;&nbsp;</span>Divers</a></div><div class="lev1 toc-item"><a href="#Tkinter" data-toc-modified-id="Tkinter-22"><span class="toc-item-num">22&nbsp;&nbsp;</span>Tkinter</a></div>

Ressources :
http://sametmax.com/le-guide-ultime-et-definitif-sur-la-programmation-orientee-objet-en-python-a-lusage-des-debutants-qui-sont-rassures-par-les-textes-detailles-qui-prennent-le-temps-de-tout-expliquer-partie-1/


https://jeffknupp.com/blog/2014/06/18/improve-your-python-python-classes-and-object-oriented-programming/

https://julien.danjou.info/blog/2013/guide-python-static-class-abstract-methods


# VERSIONS et paths


```python
import sys
import platform

print("\n EXECUTABLE : " + str(sys.executable))
print("\n PATH : " + str(sys.path))
print("\n VERSION_INFO : " + str(sys.version_info))
print("\n Version python: " + str(platform.python_version()))
print("\n MODULES : ")
help('modules')
```

    
     EXECUTABLE : /Applications/anaconda/bin/python
    
     PATH : ['', '/Applications/anaconda/lib/python36.zip', '/Applications/anaconda/lib/python3.6', '/Applications/anaconda/lib/python3.6/lib-dynload', '/Applications/anaconda/lib/python3.6/site-packages', '/Applications/anaconda/lib/python3.6/site-packages/Sphinx-1.5.6-py3.6.egg', '/Applications/anaconda/lib/python3.6/site-packages/aeosa', '/Applications/anaconda/lib/python3.6/site-packages/setuptools-27.2.0-py3.6.egg', '/Applications/anaconda/lib/python3.6/site-packages/IPython/extensions', '/Users/mocquin/.ipython']
    
     VERSION_INFO : sys.version_info(major=3, minor=6, micro=1, releaselevel='final', serial=0)
    
     Version python: 3.6.1
    
     MODULES : 
    
    Please wait a moment while I gather a list of all available modules...
    


    /Applications/anaconda/lib/python3.6/site-packages/IPython/kernel/__init__.py:13: ShimWarning: The `IPython.kernel` package has been deprecated since IPython 4.0.You should import from ipykernel or jupyter_client instead.
      "You should import from ipykernel or jupyter_client instead.", ShimWarning)
    /Applications/anaconda/lib/python3.6/site-packages/odo/backends/pandas.py:94: FutureWarning: pandas.tslib is deprecated and will be removed in a future version.
    You can access NaTType as type(pandas.NaT)
      @convert.register((pd.Timestamp, pd.Timedelta), (pd.tslib.NaTType, type(None)))
    /Applications/anaconda/lib/python3.6/site-packages/blaze/server/server.py:17: ExtDeprecationWarning: Importing flask.ext.cors is deprecated, use flask_cors instead.
      from flask.ext.cors import cross_origin
    /Applications/anaconda/lib/python3.6/site-packages/bokeh/util/deprecation.py:34: BokehDeprecationWarning: MPL compatibility can no longer be successfully maintained, and is now deprecated. All MPL compat functions will be removed completely on the release of Bokeh 1.0. See http://bokeh.pydata.org/en/latest/docs/releases/0.12.5.html for more information
      warn(message)
    /Applications/anaconda/lib/python3.6/site-packages/matplotlib/cbook.py:136: MatplotlibDeprecationWarning: The matplotlib.delaunay module was deprecated in version 1.4. Use matplotlib.tri.Triangulation instead.
      warnings.warn(message, mplDeprecation, stacklevel=1)
    /Applications/anaconda/lib/python3.6/site-packages/nltk/twitter/__init__.py:20: UserWarning: The twython library has not been installed. Some functionality from the twitter package will not be available.
      warnings.warn("The twython library has not been installed. "
    /Applications/anaconda/lib/python3.6/site-packages/skimage/viewer/utils/core.py:10: UserWarning: Recommended matplotlib backend is `Agg` for full skimage.viewer functionality.
      warn("Recommended matplotlib backend is `Agg` for full "
    /Applications/anaconda/lib/python3.6/site-packages/qtawesome/iconic_font.py:268: UserWarning: You need to have a running QApplication to use QtAwesome!
      warnings.warn("You need to have a running "
    /Applications/anaconda/lib/python3.6/site-packages/statsmodels/compat/pandas.py:56: FutureWarning: The pandas.core.datetools module is deprecated and will be removed in a future version. Please use the pandas.tseries module instead.
      from pandas.core import datetools


    xcode-select: note: no developer tools were found at '/Applications/Xcode.app', requesting install. Choose an option in the dialog to download the command line developer tools.
    Crypto              brain_mechanize     jupyter_core        sched
    Cython              brain_nose          jupyter_highlight_selected_word scipy
    IPython             brain_numpy         jupyter_nbextensions_configurator scripts
    OleFileIO_PL        brain_pytest        keyword             seaborn
    OpenSSL             brain_qt            latex_envs          secrets
    PIL                 brain_six           lazy_object_proxy   select
    PyQt5               brain_ssl           lib2to3             selectors
    __future__          brain_stdlib        linecache           setuptools
    _ast                bs4                 llvmlite            shelve
    _asyncio            builtins            locale              shlex
    _bisect             bz2                 locket              shutil
    _blake2             cProfile            logging             signal
    _bootlocale         calendar            lxml                simplegeneric
    _bz2                cffi                lzma                singledispatch
    _cffi_backend       cgi                 macpath             singledispatch_helpers
    _codecs             cgitb               mactypes            sip
    _codecs_cn          chardet             macurl2path         sipconfig
    _codecs_hk          chunk               mailbox             sipdistutils
    _codecs_iso2022     click               mailcap             site
    _codecs_jp          cloudpickle         markupsafe          six
    _codecs_kr          clyent              marshal             skimage
    _codecs_tw          cmath               math                sklearn
    _collections        cmd                 matplotlib          smtpd
    _collections_abc    code                mimetypes           smtplib
    _compat_pickle      codecs              mistune             sndhdr
    _compression        codeop              mkl                 snowballstemmer
    _crypt              collections         mmap                socket
    _csv                colorama            modulefinder        socketserver
    _ctypes             colorsys            mpl_toolkits        sortedcollections
    _ctypes_test        compileall          mpmath              sortedcontainers
    _curses             concurrent          msgpack             sphinx
    _curses_panel       conda               multipledispatch    spyder
    _datetime           conda_env           multiprocessing     spyder_breakpoints
    _dbm                configparser        navigator_updater   spyder_io_dcm
    _decimal            contextlib          nbconvert           spyder_io_hdf5
    _dummy_thread       contextlib2         nbformat            spyder_profiler
    _elementtree        copy                netrc               spyder_pylint
    _functools          copyreg             networkx            sqlalchemy
    _hashlib            crypt               nis                 sqlite3
    _heapq              cryptography        nltk                sre_compile
    _imp                csv                 nntplib             sre_constants
    _io                 ctypes              nose                sre_parse
    _json               curl                notebook            ssl
    _license            curses              ntpath              stat
    _locale             cycler              nturl2path          statistics
    _lsprof             cython              numba               statsmodels
    _lzma               cythonmagic         numbers             storemagic
    _markupbase         cytoolz             numexpr             string
    _md5                dask                numpy               stringprep
    _multibytecodec     datashape           numpydoc            struct
    _multiprocessing    datetime            odo                 subprocess
    _opcode             dateutil            olefile             sunau
    _operator           dbm                 opcode              symbol
    _osx_support        decimal             openpyxl            sympy
    _pickle             decorator           operator            sympyprinting
    _posixsubprocess    difflib             optparse            symtable
    _pydecimal          dis                 os                  sys
    _pyio               distributed         osax                sysconfig
    _pytest             distutils           packaging           syslog
    _random             doctest             pandas              tables
    _scproxy            docutils            pandocfilters       tabnanny
    _sha1               dummy_threading     parser              tarfile
    _sha256             easy_install        partd               tblib
    _sha3               email               path                telnetlib
    _sha512             encodings           pathlib             tempfile
    _signal             entrypoints         pathlib2            terminado
    _sitebuiltins       enum                patsy               termios
    _socket             errno               pdb                 test_path
    _sqlite3            et_xmlfile          pdfkit              test_pycosat
    _sre                fastcache           pep8                testpath
    _ssl                faulthandler        pexpect             tests
    _stat               fcntl               pickle              textwrap
    _string             filecmp             pickleshare         this
    _strptime           fileinput           pickletools         threading
    _struct             flask               pip                 time
    _symtable           flask_cors          pipes               timeit
    _sysconfigdata_m_darwin_darwin fnmatch             pkg_resources       tkinter
    _testbuffer         formatter           pkgutil             tlz
    _testcapi           fractions           platform            token
    _testimportmultiple ftplib              plistlib            tokenize
    _testmultiphase     functools           ply                 toolz
    _thread             gc                  poplib              tornado
    _threading_local    genericpath         posix               trace
    _tkinter            getopt              posixpath           traceback
    _tracemalloc        getpass             pprint              tracemalloc
    _warnings           gettext             profile             traitlets
    _weakref            gevent              prompt_toolkit      tty
    _weakrefset         glob                pstats              turtle
    _yaml               greenlet            psutil              turtledemo
    abc                 grp                 pty                 types
    aem                 gzip                ptyprocess          typing
    aifc                h5py                pwd                 unicodecsv
    alabaster           hashlib             py                  unicodedata
    anaconda_navigator  heapdict            py_compile          unittest
    anaconda_project    heapq               pyclbr              urllib
    antigravity         hide_code           pycosat             uu
    appnope             hmac                pycparser           uuid
    appscript           html                pycurl              venv
    argparse            html5lib            pydoc               warnings
    array               http                pydoc_data          wave
    asn1crypto          idlelib             pyexpat             wcwidth
    ast                 idna                pyflakes            weakref
    astroid             imagesize           pygments            webbrowser
    astropy             imaplib             pylab               werkzeug
    asynchat            imghdr              pylint              wheel
    asyncio             imp                 pyodbc              widgetsnbextension
    asyncore            importlib           pyparsing           wrapt
    atexit              inspect             pytest              wsgiref
    audioop             io                  pytz                xdrlib
    autoreload          ipaddress           pywt                xlrd
    babel               ipykernel           pyximport           xlsxwriter
    backports           ipykernel_launcher  qtawesome           xlwings
    base64              ipython_genutils    qtconsole           xlwt
    bdb                 ipywidgets          qtpy                xml
    binascii            isort               queue               xmlrpc
    binhex              itertools           quopri              xxlimited
    binstar_client      itsdangerous        random              xxsubtype
    bisect              jdcal               re                  yaml
    bitarray            jedi                readline            zict
    blaze               jinja2              reprlib             zipapp
    bleach              json                requests            zipfile
    bokeh               jsonschema          resource            zipimport
    boto                jupyter             rlcompleter         zlib
    bottleneck          jupyter_client      rmagic              zmq
    brain_builtin_inference jupyter_console     rope                
    brain_dateutil      jupyter_contrib_core ruamel_yaml         
    brain_gi            jupyter_contrib_nbextensions runpy               
    
    Enter any module name to get more help.  Or, type "modules spam" to search
    for modules whose name or summary contain the string "spam".
    


---
# Syntaxe et convention d'écriture
Convention d'écriture : 
- classe : MaClasse
- variable : ma_variable
- fonction : ma_fonction
- méthode : ma_methode
- constante : MA_CONSTANTE



## Commentaire
Un commentaire commence par un dièze
```python
# Ceci est un commentaire
```

## Encodage 
En première ligne du fichier, indiquer l'encodage : Utf-8 sur unix, Latin-1 sur windows, à l'aide d'un commentaire:


```python
# -*-coding:Utf-8 -*
```

L'encodage permet de faire la correspondance entre suite de 0 et de 1. Un encodage - ou encoding - est donc un tableau de correspondance entre caractère et code binaire. On peut obtenir la liste d'encoding que Python gère :


```python
import encodings
print(''.join('- ' + e + '\n' for e in sorted(set(encodings.aliases.aliases.values()))))
```

    - ascii
    - base64_codec
    - big5
    - big5hkscs
    - bz2_codec
    - cp037
    - cp1026
    - cp1125
    - cp1140
    - cp1250
    - cp1251
    - cp1252
    - cp1253
    - cp1254
    - cp1255
    - cp1256
    - cp1257
    - cp1258
    - cp273
    - cp424
    - cp437
    - cp500
    - cp775
    - cp850
    - cp852
    - cp855
    - cp857
    - cp858
    - cp860
    - cp861
    - cp862
    - cp863
    - cp864
    - cp865
    - cp866
    - cp869
    - cp932
    - cp949
    - cp950
    - euc_jis_2004
    - euc_jisx0213
    - euc_jp
    - euc_kr
    - gb18030
    - gb2312
    - gbk
    - hex_codec
    - hp_roman8
    - hz
    - iso2022_jp
    - iso2022_jp_1
    - iso2022_jp_2
    - iso2022_jp_2004
    - iso2022_jp_3
    - iso2022_jp_ext
    - iso2022_kr
    - iso8859_10
    - iso8859_11
    - iso8859_13
    - iso8859_14
    - iso8859_15
    - iso8859_16
    - iso8859_2
    - iso8859_3
    - iso8859_4
    - iso8859_5
    - iso8859_6
    - iso8859_7
    - iso8859_8
    - iso8859_9
    - johab
    - koi8_r
    - kz1048
    - latin_1
    - mac_cyrillic
    - mac_greek
    - mac_iceland
    - mac_latin2
    - mac_roman
    - mac_turkish
    - mbcs
    - ptcp154
    - quopri_codec
    - rot_13
    - shift_jis
    - shift_jis_2004
    - shift_jisx0213
    - tactis
    - tis_620
    - utf_16
    - utf_16_be
    - utf_16_le
    - utf_32
    - utf_32_be
    - utf_32_le
    - utf_7
    - utf_8
    - uu_codec
    - zlib_codec
    


Certains encoding ont même plusieurs nom. On compte en tout le nombre d'encoding : 


```python
len(encodings.aliases.aliases.keys())
```




    322



Parmis les encoding, unicode contient presque tous les caractères du monde, permet d'éviter 99.9% des erreurs. C'est un énorme tableau, qui est donc plus lent, mais la puissance aujourd'hui n'est pas un problème. Il existe plusieurs implémentation d'unicode, dont la plus courante est l'utf-8.
Il faut donc toujours privilégier l'utf8. L'encoding du fichier doit être le même que l'encoding du language. Par défaut, l'encoding Python 2.7 est l'ASCII et en Python 3 est l'utf8.
Pour cela il faut configurer l'éditeur de texte pour qu'il enregistre le code en UTF-8, et le déclarer dans le fichier, en première ligne :


```python

```


```python
# coding : utf8
```

En python, il existe 2 types de chaines de caractères :
 - La chaîne de caractères encodée: type ‘str’ en Python 2.7, ‘byte’ en Python 3.
 - La chaîne de caractères décodée: type ‘unicode’ en Python 2.7, et ‘str’ en python 3 (sic).



```python
%load_ext birdseye
```


    ---------------------------------------------------------------------------

    ModuleNotFoundError                       Traceback (most recent call last)

    <ipython-input-5-16d064cdb98e> in <module>()
    ----> 1 get_ipython().run_line_magic('load_ext', 'birdseye')
    

    ~/anaconda3/lib/python3.6/site-packages/IPython/core/interactiveshell.py in run_line_magic(self, magic_name, line, _stack_depth)
       2129                 kwargs['local_ns'] = sys._getframe(stack_depth).f_locals
       2130             with self.builtin_trap:
    -> 2131                 result = fn(*args,**kwargs)
       2132             return result
       2133 


    <decorator-gen-65> in load_ext(self, module_str)


    ~/anaconda3/lib/python3.6/site-packages/IPython/core/magic.py in <lambda>(f, *a, **k)
        185     # but it's overkill for just that one bit of state.
        186     def magic_deco(arg):
    --> 187         call = lambda f, *a, **k: f(*a, **k)
        188 
        189         if callable(arg):


    ~/anaconda3/lib/python3.6/site-packages/IPython/core/magics/extension.py in load_ext(self, module_str)
         31         if not module_str:
         32             raise UsageError('Missing module name.')
    ---> 33         res = self.shell.extension_manager.load_extension(module_str)
         34 
         35         if res == 'already loaded':


    ~/anaconda3/lib/python3.6/site-packages/IPython/core/extensions.py in load_extension(self, module_str)
         83             if module_str not in sys.modules:
         84                 with prepended_to_syspath(self.ipython_extension_dir):
    ---> 85                     mod = import_module(module_str)
         86                     if mod.__file__.startswith(self.ipython_extension_dir):
         87                         print(("Loading extensions from {dir} is deprecated. "


    ~/anaconda3/lib/python3.6/importlib/__init__.py in import_module(name, package)
        124                 break
        125             level += 1
    --> 126     return _bootstrap._gcd_import(name[level:], package, level)
        127 
        128 


    ~/anaconda3/lib/python3.6/importlib/_bootstrap.py in _gcd_import(name, package, level)


    ~/anaconda3/lib/python3.6/importlib/_bootstrap.py in _find_and_load(name, import_)


    ~/anaconda3/lib/python3.6/importlib/_bootstrap.py in _find_and_load_unlocked(name, import_)


    ModuleNotFoundError: No module named 'birdseye'



```python
type("ma chaine") # unicode -> décodé
```




    str




```python
type(b"ma chaine") # bits -> encodé
```




    bytes



En python 3, toutes les chaines sont de type unicode par défaut. Mais en python 2, il faut préfixer les chaines par u pour les déclarer en unicode:


```python
ma_chaine_unicode = u"ma chaine"
type(ma_chaine_unicode)
```




    str



Il est également possible d'utiliser le comportement de Python 3 dans Python 2 en déclarant en début de chaque module:


```python
from __future__ import unicode_literals
```

En résumé, il faut : 
- configurer l'éditeur en utf8
- déclarer l'encoding au début de chaque fichier avec "# coding : utf8"
- déclarer toutes les chaines en unicode, soit en les préfixant de "u", soit en faisant un "from __future__ import unicode_literals" au début de chaque module

Une fois cela fait, il faut gérer les entrées : c'est à dire tout ce qui n'est pas déclaré dans le code, mais qui va être récupéré en dehors, et qui aura un encoding différent voir inconnu. Il faut donc le décoder et le passer en unicode avec la méthode "decode" qui prend en argument le nom de l'encoding:


```python
ma_chaine = b"Chaine"
type(ma_chaine)
```




    bytes



Le type de donnée bytes est une séquence d'octets.


```python
ma_chaine = ma_chaine.decode("utf8")
type(ma_chaine)
```




    str



De même, toute sortie doit être encodée dans le bon encoding. Pour cela, utiliser la méthode encode. Par défaut, utiliser utf8:


```python
ma_chaine = "Chaine"
type(ma_chaine)
```




    str




```python
ma_chaine = ma_chaine.encode("utf8")
type(ma_chaine)
```




    bytes



## Interpréteur

Au début de chaque script python, il est préférable d'indiquer la position de l'interpréteur python:
```python
#! /usr/bin/env python3
```

## __main__ et __name__

Dans chaque script, créer une fonction main, ainsi qu'un bloc d'éxécution if qui vérifie si le script en cours est le script principale ou si il est simplement importé:

```python
def main():
    pass
    
if __name__ == "__main__":
    main()
```

Au début de chaque script, python créé des variables spéciales, dont __name__.
Si le script est le script lancé, cette variable spéciale vaudra __main__, sinon, elle vaudra le nom du module.

## Environnement virtuel
Un environnement virtuel est la combinaison d'une version de python et de bibliothèques.
On peut ainsi travailler avec plusieurs versions de python et/ou bibliothèques en parallèle, sans risque des problèmes de versions (mis à jour).



# Variables Python

Pour supprimer une variable : 
ma_variable = 2
ma_variable
type(ma_variable)
del ma_variable
ma_variable # Renvoi une erreur NameError, puisque la variable n'est pas définie (plus définie)

## Booléen ```True``` et ```False```
Les booléen sont un type de variable qui peut valoir :
- ```True```
- ```False```

## Chaines de caractères ```str```

Pour convertir une chaine de caractère en entier, utiliser la fonction int()  
Pour convertir un entier ou floatant en chaine de caractère, utiliser la fonction : str()  
Pour avoir un caractère spécial comme ", ', dans une chaine de caractère, il faut l'échapper avec un backslash:
    "Il a dit, et je cite : \"OUI!\""
On peut récupérer une information de l'utilisateur avec la fonction input :  
    age = input("Entrez votre age")
Attention, la variable est alors de type chaine de caractère.

Pour afficher des variables dans une chaine de caractères, on utilise la méthode format :
    nom = "Jean"
    age = 24
    ville = "Saint Claude"
    chaineComplete = "Je m'appelle {0}, j'ai {1} ans et j'habite à       {2}".format(nom, age, ville)
On n'est pas obligé d'indiquer les numéros dans les accolades si on donne les variables dans le bon ordre :
    chaineComplete = "Je m'appelle {}, j'ai {} et j'habite à {}".format(nom,age,ville)
nfin, on peut également donner les noms des variables avec leurs valeurs : 
    adresse = "{no_rue}, {nom_rue} {code_postal} {nom_ville} ({pays})".format(no_rue=5, nom_rue="rue des Postes", code_postal=75003, nom_ville="Paris", pays="France")
En concaténant : 
    print("J'ai " + str(age) + "ans")

Pour accéder aux caractères : 
    chaineComplete[0]
    chaineComplete[4]
    chaineComplete[-1] # Dernier carcactère

## Entiers et Réels avec ```int``` et ```float```



## Tuples


## Liste ```list```
Une liste est un type de variable qui se déclare à l'aide de crochet, chaque valeur de la liste séparées par une virugle:  
    maListe = [item1, item2, item3]
Les éléments d'une liste peuvent être de n'importe quel type, même de type liste. On peut donc imbriquer des listes.

On peut récupérer les élements d'une liste, une sous-liste, avec les indices : 
```python
    sousListe = maListe[2:]
```
On peut de même réaffecter la valeur d'un item d'une liste :
```python
    maListe[3] = 5
```

On peut ajouter / concaténer des liste à l'aide du + :
```python
    maListe = maListe + [1,2,3]
    maListe.extent(monAutreListe)
```

On peut supprimer un élément d'une liste : 
```python
    del maListe[3]
    maListe.remove(indexSuppr)
```
On peut récupérer la longueur d'une liste avec la fonction len : 
```python
    len(maListe)
```
Pour copier une liste, utiliser la fonction list() ou les deux points : 
```python
    b = a[:]
    b = list(a)
```
Pour ajouter ou retire un élémen, on peut utiliser une méthode :
```python
    liste = [2,6,8,10]
    liste.append(5)
    liste.remove(5)
```

Pour avoir la position d'un élement: 
```python
    liste.index(6) #renvoi la position de l'ocurrence "6"
```

Pour insérer un élément dans une liste :
```python
    liste.insert(index,valeur)
```
Pour créer une liste vide : 
```python
    maListe = list()
    maListe = []
```

Pour convetir une chaine de caractère en liste, on peut utiliser split : 
```python
    ma_chaine.split(" ") # le paramètre de split est le séparateur à utiliser pour spliter la chaine
```

Pour convertir une liste en chaine de caractère, on peut utiliser join : 
```python
    " ".join(ma_list) 
```

## Dictionnaires ```dict```
La classe d’un dictionnaire est : 
dict
Pour créer un dictionnaire vide : 
```python
Mon_dico = dict()
Mon_dico = {}
```

Au final : 
- les parenthèses délimitent les tuples
- les crochets délimitent les listes
- les accolades délimitent les dictionnaires

Pour ajouter ou modifier un élement d’un dictionnaire : 
```python
Mon_dictionnaire[ma_cle] = valeur_ma_cle
```

SI la clé n’existe pas, une exception KeyError est levée.  
On peut créer un dictionnaire déjà rempli : 
```python
Mon_stock = {"patates" : 5, "courges" : 6}
```
A ne pas confondre avec un set : un ensemble qui ne peut contenir 2 fois le même élement. Un set est comme un dictionnaire sans valeur : il s'agit d'un ensemble de clé, qui peuvent exister plusieurs fois :

```python
mon_set = {"courge", "patate", "courge"}
```

Pour supprimer un élément d'un dico :

```python
del mon_dico[ma_cle_a_supprimer]
mon_dico.pop(ma_cle_a_supprimer)
```

Pour parcourir les clés, on utilise la méthode keys de la structure de donnée dict :  
```python
for cle in mon_dico.keys():
    # ...
```

Pour parcourir les valeurs, on utilise la méthode values de la structure de donnée dict:
```python
for valeur in mon_dico.values():
	# ...
```

La méthode items de la structure dict permet de récuperer les tuples clé/valeur du dictionnaire :
```python
for (cle,valeur) in mon_dico.items():
    # ...
```

## Ensemble avec ```set```
Un tuple est une liste qu'on ne peux pas modifier. On utilise des parenthèses et pas des crochets pour la déclarer:

    monTuple = (1,4,'bonjour)
    monTupleAUnElement = (28,)

Un dictionnaire est une liste qui est indéxée par une chaine de caractère. On utilsie des accolades : 

    monDico = {"Pierre": [10,"Paris"],"Paul": [20,"Lyon"]}
    

Chaque premier élément, appelé "clé", doit être unique dans le dictionnaire (ici, Pierre et Paul), pour permettre une indexation bijective comme avec les nombres. On récupère les informations de Paul avec :

    monDico["Paul"]

Un ensemble est une dictionnaire sans clé, et dont chaque élément est unique. Si on met 2 fois un même élement, il n'est pris en compte qu'une fois. De plus, l'ordre d'apparition n'a pas d'importance.

    monEnsemble = {1,2,5,8,3,2,7} # Cet ensemble est égal à {1,2,3,5,7,8}

On peut ainsi utiliser des opérateur union et intersection : 

- Union : | (Alt+maj+L)
- Intersection : &
- Différence : -
- Différence symétrique : ^

Pour convertir une liste en ensemble, utiliser la fonction set : 
    maListe = [1,2,5,7,4,1]
    monEnsemble = set(maListe) #monEnsemble = {1,2,4,5,7}


# Opérateurs, boucles et conditions

## Structures conditionelles

### Structures de ```if```
3 utilisations possibles : 

- if simple : 
```python
if ma_condition: 
    # ...
```

- if else : 
```python
if ma_condition: 
    #...
else:
    #...
```

- if elif else : 
```python
if ma_condition_1:
    #...
elif ma_condition_2:
    #...
else: 
    #...
```

On appelle *prédicat* les conditions qui sont entre le ```if```et le ```:```.



## Opérateurs 

### Opérateurs classiques 

- ```+``` : Addition
- ```-``` : Soustraction
- ```*``` : Multiplication
- ```/``` : Division entière
- ```%``` : Reste de la division entière
- ```**``` : Puissance

### Opérateurs booléens  ```or```, ```and```, ```not```

On a 3 mots-clés : 
- ```or``` : OU logique
- ```and``` : ET logique
- ```not``` : NON logique  

### Opérateurs bitwise

- ```x << y``` : Returns x with the bits shifted to the left by y places (and new bits on the right-hand-side are zeros). This is the same as multiplying x by 2**y.  
- ```x >> y``` : Returns x with the bits shifted to the right by y places. This is the same as //'ing x by 2**y.   
- ```x & y``` : Does a "bitwise and". Each bit of the output is 1 if the corresponding bit of x AND of y is 1, otherwise it's 0.   
- ```x | y``` : Does a "bitwise or". Each bit of the output is 0 if the corresponding bit of x AND of y is 0, otherwise it's 1.   
- ```~ x``` : Returns the complement of x - the number you get by switching each 1 for a 0 and each 0 for a 1. This is the same as -x - 1.   
- ```x ^ y``` : Does a "bitwise exclusive or". Each bit of the output is the same as the corresponding bit in x if that bit in y is 0, and it's the complement of the bit in x if that bit in y is 1.   

### Opérateurs de comparaison 

- ```<``` : inférieur
- ```>``` : supérieur
- ```<=``` : inférieur ou égal
- ```>=``` : supérieur ou égal
- ```==``` : égal
- ```!=``` : différent



# Boucles

## Boucle ```while```
Pour faire une boucle ``while```:

```python
while ma_condition:
    #....
```
## Boucle ```for```
Pour faire une boucle ```for```:

```python
for mon_compteur in mon_domaine:
    #...
```

        
## Interompre et continuer une boucle ```break``` et ```continue```

### ```break```
Le mot clé ```break``` permet d'interompre une boucle et de poursuirvre le code qui suit la boucle:

```python
while 1:
    print("On sort de la boucle infinie dès le premier tour")
    break
```

### ```continue```
Le mot clé ```continue``` permet de terminer l'occurence courante d'une boucle, puis la boucle passe à l'occurence suivante:

```python
i = 0
while i<20:
    if i%5 ==0: # Si i est un multiple de 5, on lui ajoute 3
        print("i est un multiple de 5, on lui ajoute 3 (et pas 1)")
        i =+ 5
        continue # Ici, on arrête la boucle, et on passe au cas suivant 
                 # (évite de re-ajouter 1 à i et d'afficher sa valeur)
    print("i vaut" + str(i))
    i += 1 # On ajoute 1 à i
```




# Exceptions

## Bloc ```try``` et ```except```
Quand python rencontre une erreur, il lève une exception.
Bloc minimale : 
```python
try: 
    #Code à tester
except: 
    #Code à executer en cas d'erreur
```

On peut exécuter différents codes en fonction du type d'erreur : 
```python 
try: 
    # Code à tester
except NameError: 
    # Code à executer en cas d'erreur de nom
except TypeError: 
    # Code à executer en cas d'erreur de type
except ZeroDivisionError
    # Code à executer en cas d'erreur de division par 0
```

On peut récupérer le texte de l'exception dans une variable pour l'afficher avec ```as``` : 
```python
try: 
    # Code à tester
except nomErreur as textErreur
    print("L'erreur dit : " + textErreur)
```

```python
try: 
    # Code à tester
except Exception as texte_exception
    print("L'erreur dit : " + texte_exception)
```



Pour distinguer les calculs du résultats, on ajoute une instruction else. Il faut distinguer ce qui risque de lever une exception, et qui sera inséré dans le bloc ```try```, de ce qui doit être fait si aucune exception n'est levée, et qui sera placé dans le bloc ```else```.

Pour ajouter du code après le bloc try, quel que soit l'erreur levée ou sans erreur, on ajoute un bloc finally.
```python 
try: 
    # Code à tester
except nomErreur as textErreur:
    # Code à executer en cas d'erreur
except nomErreur2 as textErreur2: 
    # Code à executer en cas d'erreur
else: 
    # Code à executer si aucune exception n'est levée
finally: 
    # Code à executer dans tous les cas (avec ou sans exception)
```

On peut ajouter le mot clé pass dans une exception pour la sauter : 
```python 
except: 
        pass
```

## Assertion avec ```assert```
Permet de faire un test de vérification si une condition est vraie. Si elle est fausse, python lève une exception AssertionError :
```python 
assert a == 5
```

## Lever une exception avec ```raise```
On peut lever à la main une exception avec raise :
```python
raise TypeDeLexception("Texte de l'exception")
```


# Itérateurs et générateurs

## Itérateur avec ```iter``` et ```next```

### Principe des itérateurs
Un itérateur est un objet qui permet de parcourir des objets itérables, c'est-à-dire qui dispose d'un index. On appelle ce type d'objet séquence.
Les itérateurs sont très peu gourmand en ressources.
Quand une liste utilise le mot clé ```for mon_element in mon_objet```, Python fait appel à l'itérateur de ```mon_objet```. Cet itérateur de ```mon_objet``` est lui même un objet créé par la méthode spéciale ```__iter__``` de ```mon_objet```.
A chaque tour de boucle, Python fait appel à la méthode spéciale ```__next__``` de l'itérateur, qui renvoi l'élément suivant ou lève une exception de fin de parcours.

#### Fonctions et méthodes utiles
Python dispose d'une fonction ```iter``` qui permet de créer un itérateur sur un objet itérable.
Certains objet disposent déjà de leur propre itéraeur, accessible par la méthode ```__iter__```.

On peut ainsi récupérer ou définir un iterateur ainsi : 
```python
chaine = 'hello world'
iterateur = iter(chaine)   # iterateur est un objet, de type itérateur
```
ou de manière équivalente :
```python
chaine = 'hello world'
iterateur = chaine.__iter__()
```
Les objets de type itérateur disposent tous d'une fonction ```next()```permettant de parcourir l'objet itérable. Cette méthode permet de déplacer l'indice qui parcourt l'objet. L'appel à la fonction next déplace le curseur d'un indice, et renvoi la valeur lue à cette indice.
La fonction ```next()```fait en fait appel à la méthode spéciale ```__next__```

```python
class MonIterateur(object):
    def __init__(self, obj):
        self.obj = obj
        self.length = len(obj)
        self.count = 0

    def __iter__(self):
        return self

    def next(self):
        if self.count > self.length:
            raise StopIteration

        else:
            result = self.obj[self.count]

        self.count += 2
        return result

if __name__ == "__main__":
    chaine = "hello_world"
    ma_classe_iterateur = MonIterateur(chaine)
    iterateur = ma_classe_iterateur.__iter__()
    try:
        for idx in range(len(chaine)):
            print(iterateur.next())
    except StopIteration:
        print("fin d'iteration")
```

Le bloc \__main\__ est équivalent au suivant : 
```python
if __name__ == "__main__":
    chaine = "hello_world"
    ma_classe_iterateur = MonIterateur(chaine)
    try:
        for lettre in ma_classe_iterateur:
            print(lettre)
    except StopIteration:
        print("fin d'iteration")
```

```python
chaine = 'hello world'
iterateur = iter(chaine) # equivalent à chaine.__iter__()
print(iterateur)
```


## Générateur avec ```yield```



# Contexte manager : ```with```
Le mot clé with permet d'exécuter de manière "lisible" les contextes manager. C'est une simple question de rédaction. 
Les contextes managers peuvent être utilisés sans utiliser le mot clé with.

Pour créer un context manager, deux solutions : 
 - classe
 - fonction avec décorateur


## Méthodes __enter__() et __exit__()
Un contexte manager est une classe qui contient deux méthodes : __enter__ et __exit__().

Exemple : 
```python
import os
 
class Cd(objet):
    def __init__(dirname):
        self.dirname = dirname
    def __enter__(self):
        self.curdir = os.getcwd()
        os.chdir(self.dirname)
    def __exit__(self, exc_type, exc_value, traceback):
        os.chdir(self.curdir)
        
with Cd("/"):
    # ici on fait des trucs dans "/"
# ici on est revenu dans le dossier initial

```

## Mot clé ```as```
On peut retourner un objet via la méthode enter, qui sera renvoyé dans as:
```python
class OpenFile(objet):
    def __init__(filename, mode='r'):
        self.filename = filename
        self.mode = mode
    def __enter__(self):
        self.file = open(self.filename, self.mode)
        # ici on retourne l'objet fichier, il sera accessible avec "as"
        return self.file
    def __exit__(self, type, value, traceback):
        self.file.close()
with OpenFile('/etc/fstab') as f:
    # ici on fait des trucs avec f qui vaut ce qui est retourné par __enter__
```
Les instructions s'éxécutent dans l'ordre suivant : 
- après with : __enter__
- as : récupère la sortie de __enter__
- dans la partie indentée : on fait notre boulot
- à la sortie de l'indentation : __exit__

## Context manager en fonction : module ```contextlib```
On peut rendre une fonction contextuable avec le décorateur @contextmanager du module contextmanager du package contextlib:

```python
from contextlib import contextmanager
 
@contextmanager
def open(filename, mode):
    try:
        f = open(filename, mode)
        yield f
    finally:
        f.close()
```
Le début du bloc try est l'équivalent du __enter__, ce qui est retourné par __enter__ est donné par le yield (et qu'on peut donc récupérer dans as), et l'__exit__ par le finally.
Il faut en gros 3 choses : 
- le set-up avant le yield, équivalent à __enter__
- le retour du yield, équivalent au retour du __enter__
- le tear-down après le yield, équivalent à __exit__


# Fonctions 

## Définir une fonction
Pour définir une fonction:
```python
def nomFonction(in_1, in_2, in_defaut_1 = ma_valeur_defaut_1, in_defaut_2 = ma_valeur_valeur_defaut_2):
    # ...
    return variableRetournéeFonction1, variableRetournéeFonction2 
    #identique à : return (variableRetournéeFonction1, variableRetournéeFonction2)
```

Pour ajouter une doc à une fonction, ajouter une chaine de caractère après la première ligne, appellée *docstring*. C'est ce texte qui sera affiché lorsqu'on appelle la fonction avec ```help(nom_fonction)```:
```python
def nomFonction():
    "Doc de la fonction" # Ce texte est appellé *docstring* de la fonction
    # ...
    return
```

Signature d'une fonction : la signature d'une fonction est ce qui permet de l'identifier entiermeent. En python, c'est son nom. Ainsi si on recréé une fonction avec le même nom mais des paramètres différents, l'ancienne défintiion est écrasée.


## Fonctions ```lambda```
Les fonctions ```lambda``` permettent de définir une fonction rapide sur une ligne :
```python
ma_fonction_lambda = lambda var1, var2, var3: var1 + var2 - v
x = ma_fonction_lambda(1,2,3)
```





# Modules et packages

## Modules

### Mot-clé ```import```, ```from``` et ```as```
Pour importer un module en entier et le déclarer dans son espace de nom:
```python
import nomModule
```

Pour importer seulement certains objets d'un module:
```python
from nomModule import nomFonction, variable
```

Pour importer toutes les fonctions et variables sans les déclarer dans l'espace de noms du module:
```python
from module import *
```

On peut renommer un objet lors de son import avec le mot clé ```as```:
```python
import numpy as np
```

### Créer ses propres modules
Un module est un fichier .py qui contient les déclarations des variables et fonctions.
Pour ajouter une documentation au module, ajouter une chaine de caractère au début du fichier : 
```python
"Ce module permet de faire des calculs trigo"

def ma_fonction1():
 # ...
```

Si je nomme mon module mon_module.py, il suffit de l'importer comme un module normal : 
```python
import mon_module
```
Le module doit être dans le même dossier que le fichier courant.

## Packages
Un package est un dossier contenant un ou plusieurs sous dossiers, appélés sous-packages.  
Dans ces dossiers se trouvent des modules, ou fichiers .py.  

Un package contient un fichier ```__init__.py``` par package (sans quoi un dossier sans ce fichier ne sera pas reconnu comme un sous-package) et plusieurs modules.


Un package s'importe comme un module : 
```python
import mon_package
```

Un package - ou dossier - puis contenir un ou plusieurs sous packages - sous dossiers -:
```python
import mon_package.mon_sous_package.mon_module
```


Pour importer uniquement un module d'un package : 
```python
import mon_package.mon_module
```

Pour accéder à un objet d'un module :
```python
x = mon_package.mon_module.mon_objet
```
La structure ressemble à :

- mon_package
    - mon_sous_package_1
        - module A
        - module B
    - mon_sous_package_2
        - module C
        - module D


Les modules/packages doivent avoir un nom en lowercase, underscore-separated, et unique nom sur pypi.  
https://python-packaging.readthedocs.io/en/latest/everything.html




# Fichiers
Pour lire un fichier, utiliser la fonction open : (par défaut, l'ouverture est faite en mode lecture seule :
    monFichier = open("CheminVersMonFichier")
    contenuDeMonFichier = monFichier.read()
    monFichier.close()
Pour écrire dans un fichier, il faut l'ouvrir en mode write (attention, supprime le contenu existant !)
    monFichierAEcrire = open("Chemin", mode="w")
    monFichier.write("blablabla")
Pour ajouter du texte à la suite, utiliser le mode append :
    file = open("Chemin", mode="a")
    file.write("2ieme blabla") #Ajoute 2ieme blabla à la suite du document
Pour lire seulement les 10 premiers caractères du fichier :
    debutMonFichier = monFichier.read(10) #Le curseur de lecture du fichier se trouve au caractère 10. Si on relis le fichier, la lecture reprend à cet endroit
Pour lire seulement la ligne suivante : 
    ligne = monFichier.readline()
Pour connaitre la position du curseur : 
    monFichier.tell()
Pour replacer le curseur à une certaine position :
    monFichier.seek(28)
   
## Fichiers et dossiers
(a)	Dossiers
Pour changer le dossier courant : 
os.chdir(path_new_dir)
Pour récupérer le dossier courant :
os.getcwd()
Pour avoir la liste des fichiers dans le dossier : 
os.listdir()
(b)	Fichiers
Pour ouvrir un fichier, on précise le mode : 
mon_fichier = open(path_mon_fichier,"r") #'r' ou 'w' ou 'a'
Une fois le fichier ouvert, il faut le lire: 
contenu_str = mon_fichier.read()
Pour écrire dans un fichier, méthode write : 
mon_fichier.write(ma_str_to_write)
Pour fermer un fichier : 
mon_fichier.close()
Pour enregistrer dans un fichiers, utiliser le module pickle la classe Pickler, et sa méthode dump:
import pickle
mon_pickler = pickle.Pickler(mon_fichier)
mon_pickler.dump(variable_a_ecrire)
Pour récupérer un objet enregistré, on utilise le module pickle, la classe Unpickler, et sa méthode loard:
mon_depickler = pickle.Unpickler(mon_fichier)
contenu = mon_depickler.load()

# Classes et méthodes

## Classes
Pour définir une classe :
```python
class NomDeLaClass:
"""definire une personne par son nom age adresse"""
    def __init__(self):
        self.nom = "Dupont" # Valeur par défautt
```


## Attribut de classe 
Attribut déclaré au niveau de la classe, pas de l'instance. N'import quelle instance de la classe aura cet attribut, accessible de la façon normale : self.attribut_de_classe

On peut définir un attribut dans une classe, et le modifier dans une méthode:
```python
class Compteur:
"""Cette classe possède un attribut de classe qui s'incrémente 
à chaque fois que l'on crée un objet de ce type""" 

    objets_crees = 0 # Le compteur vaut 0 au départ 
    
    def __init__(self): 
    """À chaque fois qu'on crée un objet, on incrémente le compteur""" 
    
        Compteur.objets_crees += 1
```

Les méthodes sont associées aux classe des objets, pas dans l'objet.



## Méthode de classe

Méthode de classe :
Une variante de la méthode statique est la méthode de classe, dont le premier paramètre est la classe, et pas une instance de cette classe.
On utilise alors le décorateur @classmethod
Une méthode de classe est "bounded" à sa classe.


On peut créer une méthode de classe, qui agit sur la classe et pas sur l'instance. pour créer une méthode de classe, il faut définir la méthode avec le paramètre ```cls``` et pas ```self```, puis utilise la fonction python ```classmethod``` pour transformer cette méthode en méthode de classe : 
```python
class Compteur:
    objets_crees = 0 # Le compteur vaut 0 au départ

    def __init__(self):
        Compteur.objets_crees += 1

    def combien(cls):
        print("Jusqu'à présent, {} objets ont été     créés.".format(cls.objets_crees))
    combien = classmethod(combien)
```

## Méthode statique
Une méthode statique ne prend en argument ni la classe ni une instance de la classe.
Elle se définit comme une méthode d'instance, mais on utilise la fonction python ```staticmethod``` pour la transformer en méthode statique : 
```python
class Test:
    """Une classe de test tout simplement"""

    def afficher():
        """Fonction chargée d'afficher quelque chose"""
        print("On affiche la même chose.")
        print("peu importe les données de l'objet ou de la classe.")

    afficher = staticmethod(afficher)
```
Méthode de classe - Méthode statique :
Méthode déclarée dans la classe, mais sans self. Elle ne nécessite pas d'instance pour être accessible. Pour bien préciser qu'une méthode de classe ne doit pas avoir d'instance en premier paramètre (comme self classiquement), on la décore avec le décorateur @staticmethod.

Une méthode statique est une méthode qui ne prend pas pas self en paramètre, qui est commune à toutes les instances de la classe. Créer des méthodes statiques évite de créer une méthode pour chaque instance de la classe : on créé une seule méthode pour toutes les instances.
Cela permet également de faciliter la lecture du code : @staticmethod montre que la méthode ne dépend pas de l'instance
Cela permet enfin de surcharger la méthode statique dans une sous classe. 




## Méthodes spéciales 
On appelle méthodes spéciales les méthodes dont le nom est entouré par __ : 
```python
__methode_special__
```

### Initialiser un objet avec ```__init__```
Une classe doit contenir un constructeur, qui est une méthode s'appellant __init__. C'est une méthode spéciale, entourée par __  

Pour définir un constructeur prenant des paramètres: 
```python
def __init__(self, nom, prenom):
    self.nom = nom
    self.prenom = prenom
```

### Supprimer un objet avec ```__del__```
Méthode appellée lors de la suppression d'un objet, à la fin d'une fonction ou d'un module par exemple, lorsque l'espace de nom est détruit.

### Représentation avec ```__repr__```

### Conversion en chaine de caractère avec ```__str__```

### Accès aux attributs avec ```__getattr__```
Syntaxe : 
```python
def __getattr__(self,nom):
        """Si Python ne trouve pas l'attribut nommé nom, il appelle cette méthode. On affiche une alerte"""
```
### Modification des attributs avec ```__setattr__```

### Suppression des attributs avec ```__delattr__```
```python
def __delattr__(self,nom_attr):
```

### ```__hasattr__```


### Méthode d'indexing ```__getitem__```, ```__setitem__``` et ```__delattr__```
Les méthodes d'indexing permettent l'utilisation de la notation a[28].
```python
class MaClasse:
    def __getitem__(self, index):
        """Cette méthode spéciale est appelée quand on fait objet[index]
        Elle redirige vers self._dictionnaire[index]"""
        
        return self._dictionnaire[index]
    def __setitem__(self, index, valeur):
        """Cette méthode est appelée quand on écrit objet[index] = valeur
        On redirige vers self._dictionnaire[index] = valeur"""
        
        self._dictionnaire[index] = valeur
```

### Méthode ```__contains__``` pour le mot clé ```in```
Permet d'utiliser le mot clé ```in```
```python
ma_liste = [1, 2, 3, 4, 5]
8 in ma_liste # Revient au même que ...
ma_liste.__contains__(8)
```

### Méthode ```__len__```
Permet d'utiliser la fonciton python ```len()```.

### Objets callable ```__call__```
Un objet est callable si on peut lui ajouter "```()```".
Pour définir le comportement lorsque l'on appelle ainsi un objet, il faut définir la méthode ```__call__```

### Méthodes mathématiques ```__add__```, ```__sub```, ```__mul__```, ```__div__```
ajouter version radd, rsub, rmul, pow, truediv, floordiv, mod

### Méthodes de comparaison ```__lt__```, ```__gt__```, ```__eq__```
neq, le, ge


## Classe de base abstraites : Abstract Base Class

Abstract Base Class : Classe de base abstraite : 
Il s'agit de classe dont le seul but est de créer des héritages, mais pas d'être utilisée seule. 
Pour déclarer une bastraite de base : définir simplement le nom de la méthode, et lever : raise NotImplementedError dans son corps. Ainsi, on on lui fait appel sans l'avoir rédéfinit, on récupère bien une erreure. 
Le problème de cette méthode est que l'on lève l'erreur seulement lorsqu'on fait appel à la méthode de l'objet instancié (sans la méthode redéfinie). Pour que l'erreur soit levée dès la crétaion de l'instance:
Pour rendre une classe ABC, importer le module "from abc import ABCMeta, abstracmethod".
On set alors la métaclasse de la classe à ABCMeta : "__metaclass__ = ABCMeta". Les méthodes que l'on veut définir dans les sous classes mais pas dans la classe de base abstraite doit être décorée par @abstractmethod, et déclarée à "pass" (sans paramètre).



## Attributs spéciales
### ```__dict__```
Quand on créé une classe, tous les objets de cette classe on un attribut spécial ```__dict__``` qui contient en clé les noms des attributs, et en valeur la valeur des attributs.


## Métaclasse
Une métaclasse est une classe pour définir une classe.
La métaclasse de base est "type".
Pour connaitre la classe d'un objet, on peut uiliser la méthode \_\_class\_\_.
Par exemple, int est une instance de la classe type, ainsi qu'une classe.
Pour créer une métaclasse, on utilise la métaclasse type:
type(name, bases, dct)
avec name le nom de la classe à créer
bases un tuple contenant les classes dont il faut hériter
dct un dictionnaire dont les clés sont les noms de méthodes et attributs de la classe, et les valeurs les valeurs de ces méthodes et attributs.
cls est l'équivalent de self pour les classes.

### Méthodes et attributs utiles des métaclasse
Les méthodes :
- __init__
- __new__
- __del__

Les attributs:
- __name__
- __doc__
- __dict__
- __module__
- __class__
- __metaclass__



# Héritage

## Héritage
Si une classe b hérite de la classe a, les objets créés sur l modèle de la classe b auront accès aux méthodes et attributs de la classe a.
class ma_classe_mere:
    pass
class ma_classe_enfant(ma_classe_mere):
    pass
Pour savoir si une classe est sous classe : 
issubclass(sous_classe_potentielle,classe_mere_potentielle)
	Pour savoir si un objet est une instance d'une classe :
isinstance(objet,classe)
Pour faire de l'héritage multiples :
class MaClassHeritee(MaClassMere1,MaClasseMere2)

### Fonctions utiles
#### Appartenance à une classe ```issubclass()```et ```isinstance```

```python
issubclass(A,B)
```
renvoi True si A est une sous classe de B
```python
isinstance(A,B)
```
renvoi True si A est une instance de B ou d'une classe fille de B

## MRO : Method Resolution Order
La MRO détermine dans quel ordre sont résolus les héritages. En python 2, il faut déclarer une classe à partir de "object" pour utiliser le nouvel algo de MRO, et à partir de rien pour utiliser l'ancien. En python 3, peut importe, c'est le nouvel algo qui est utilisé.
On peut utiliser la méthode __mro__ pour connaitre les héritages de la classe.
.__mro()__ est une méthode de classe
Il faut faire de l'héritage quand on veut pouvoir utiliser un objet de la même façons que la classe mère, mais avec des possibilités supplémentaires.
Il faut faire de la composition quand on veut utiliser une partie des possibilités : par exemple, la classe utilise une liste, mais hérite juste de object; pas de list. Sinon, cela définirai toutes les méthodes de list, dont on ne veux pas forcément.




# Portée des variables et espaces de noms

### Variables globales avec ```global```




# Objets Python de base

## Mots-clés python

### Liste des mots-clé python
Python utilise par défaut des mots-clé qui lui sont réservés : 
```python

from # pour spécifier de quel module on veut importer un objet
as 
import
with # pour utiliser les méthodes de contexte manager

for # boucle for
while # boucle while
break
except

era
del # pour supprimer une variable

None # None

True # Booléen 
False # Booléen

global
local

try
finally
assert
raise
pass
yield
continue

if # si
elif # sinon si
else # sinon

not # NON
or # OU
in # pour parcourir un itérateur
is # compare la référence de deux variables

class # pour créer une classe

def # marque le début de la définition d'une fonction
return # marque la valeur renvoyée par une fonction
lambda # défini une fonction en une ligne


```

### Détails sur les mots-clés python

#### Fonction ```lambda```
Permet de définir une fonction en une seule ligne

## Variables python

### Variables  ```__name__``` et ```__main__```  

La variable ```__name__``` est une variable qui est créée dès le début d'un fichier python, et qui vaut __main__ si on lance le fichier depuis le code principale, pas si c'est un module importé.


## Fonctions spéciales python

### Liste des fonctions spéciales python
Python intègre par défaut des fonctions:
```python
abs()
all()
any()

basestring()
bin()
bool()
bytearray()	

chr()
callable()
cmp()
classmethod()
complex()
compile()

divmod()
delattr()
dir() # liste des attributs d'un objet
dict()

enumerate()
eval()
execfile()

float()	
file() # chemin du fichier python en cours ?
filter()
format()
frozenset()	

globals()
getattr()

hasattr()	
help() # informations sur l'objet passé en argument
hex()
hash()

__import__()
id() # donne la référence d'une variable
is() # compare 2 variables d'après leurs référence
input()
int()
iter()
isinstance()
issubclass()

list()
len()
long()	
locals()

min()	
max()	
memoryview()
map()	

next()	

open()
ord()
object()	
oct()

print()
property()
pow()

raw_input()
range()
reload()	
reduce()
reversed()	
round()	
repr()

super()
sum()	
setattr()	
set()	
slice()
sorted()
staticmethod()
str()

tuple()
type()

unichr()
unicode()

vars()

xrange()

zip()	
```

### Détails sur les fonctions spéciales

#### Fonctions ```globals()``` et ```locals()```

Dans une fonction, les variables déclarées sont uniquement accessible depuis l'intérieur de cette fonction. On appelle cela son espace local.
Les variables déclarées en dehors de la fonction, sont définies en dehors de son espace local, son accessible en lecture mais pas en écriture.
En revanche, on peut passer un objet déclaré en dehors d'une fonction en paramètre d'une fonction, et modifier le contenu de cet objet. Une fois sortie de la fonction, l'objet sera toujours modifié.

Pour utiliser une variable définie en dehors d'une fonction, on utilise le mot clé ```global```:

```python
b = 2

def fonction():
    global b # python va chercher dans les différents espaces de noms pour trouver b
    b = 28
    
>>> b vaut 28
```

#### Référence et identifiants ```id()``` et ```is()```
On peut obtenir la référence d'une variable avec la méthode ```id```.
Pour comparer le contenu de 2 variables, on utilise ==
Pour comparer leurs références, on utilise is.


#### Fonction ```dir()```
La fonction ```dir``` permet de récupérer la liste de tous les attributs et méthodes d'un objet :
```python
ma_chaine = "Coucou"
dir(ma_chaine)
```

#### Informations sur un objet ```help()```
Pour obtenir des informations sur une fonction ou un module :  
```help("nom_fonction```)




# Decorators

Un décorateur est une fonction qui prend en paramètre une fonction.
Pour appliquer un décorateur à une fonction lors de sa définition, il suffirt d'ajouter :
```python
@mondecorateur
def ma_fonction_decoree

```
La fonction est décorée lors de la définition, pas lors du premier appel à la fonction.



## Décorateur simple

Un décorateur est une fonction qui prend en paramètre une fonction et renvoi une fonction. On la définie comme une fonction classique, avec def:
```python
def mon_decorateur(fonction):
    # ...
    return fonction
```

Pour modifier une fonction par un décorateur, il suffit d'ajouter un "@" avec le nom du décorateur devant la définition de la fonction. Le décorateur va s'éxécuter au moment de la définition de la fonction, et pas lors de son appel.
```python
@mon_decorateur
def ma_fonction_a_decorer():
    # ...
```
Ceci est équivalent à 
```python
def ma_fonction_a_decorer():
    # ...
    
ma_fonction_decoree = mon_decorateur(ma_fonction_a_decorer)
```
On comprend ainsi pourquoi la fonction ```mon_decorateur``` finie par ```return fonciton```. L'effet du décorateur étant appliqué à la définition de la focntion.


## Décorateur sur fonction avec paramètres
Si la fonction que l'on décore prend des paramètres, il faut utiliser ces paramètres dans la fonction décorée dans le décorateur. Pour cela, on utilise le paramètrage dynamique :
```python
def mon_decorateur():
    def ma_fonction_decoree(*params,**params_nommes):
        pass
```

## Décorateur avec paramètre
Pour utiliser un décorateur avec paramètre, il faut utiliser la syntaxe :
```python
@mon_decorateur_a_parametre(param_deco)
def ma_fonc
    pass
```
Qui est équivalent à :
```python
ma_fonc_decorateur_a_parametre(param_deco)(ma_fonc)
```

Il faut ainsi déclarer un "générateur" de décorateur, qui prend en paramètre un paramètre de décorateur, et qui renvoi un décorateur, qui lui prend en paramètre une fonction.


## Décorateur de classe
Les décorateurs fonctionnent de la même manière sur des classes.


## Décorateurs utiles

### Singleton
Un singleton est une classe qui ne peut être instanciée qu'une fois
Consiste en un décorateur qui créé un dictionnaire, dont les clés sont les classes, et les valeurs les instances de chaque classe.

### Controleur de type
Décorateur qui prend en paramètre les types des paramètres. Si les paramètre passé à la fonction décorée ne sont pas de ce type, lève une erreur.


## Décorateurs prédéfinis
Permet d'accéder à une méthode comme un attribut :
```python
class Employee:
    @property
    def email(self):
        return' {}.{}@email.com'.format(self.nom,self.prenom)

emp_1.email
```

La propriété setter :


# Propriétés avec ```property```

Il existe une classe "property" qui prend 4 arguments en paramètres : 
```python
def __init__():
    self._mon_attribut = "Coucou"
    
def _getter_mon_attribut():
    return self._mon_attribut
    
def _setter_mon_attribut():
    self._mon_attribut = "Byebye"
    
mon_attribut = property(_getter,_setter,_deleter,_helper)
```
Les méthodes passées dans property doivent être déclarées dans la classe, et commencer par un "\_". L'attribut déclaré dans l'init doit également commencer par "\_".


On utilise l'underscore pour rendre les méthodes "protégée" : elles sont accesibles depuis l'exterieur de l'instance, mais ça n'est pas fait pour ça.

Une propriété est également une méthode que l'on souhaite utiliser comme un attribut:

```python
def __init__():
    self._mon_attribut = "Coucou"
    
@property    
def ma_propriete():
    return self._mon_attribut
```

# Paramétrage dynamique : Packing et Unpacking, et ```*args``` et ```**kwargs```





## Principe de l'unpacking : appel d'une fonction ou affectation
En mettant ```*args``` ou ```**kwargs``` dans l’appel d’une fonction, on va faire de l’unpacking.

L'unpacking permet en une ligne, d'affecter plusieurs variables à partir d'un itérable :
```python
var_1, var_2, var_3 = mon_iterable_3_elements
```

L'opérateur splat * permet de faire de l'unpacking dans les cas où on veut définir moins de variables qu'il n'y a d'éléments dans l'itérable :
```python
var_1, *reste_des_variables = mon_iterable_3_elements

# Pour passer plusieurs paramètres individuellement à une fonction, à partir d'une liste de ces paramètres
ma_fonction(*mon_iterable_3_elements) # equivalent à ma_fonction(var_1,var_2,var_3)
```

On peut également faire de l'unpacking sur des dictionnaires (jusqu'ici on a fait sur itérable), avec \*\*:
```python
def afficher_trois_elements(elem1, elem2=None, elem3=None):
    print(elem1)
    print(elem2)
    print(elem3)

elements = {"elem1": "eau", "elem2": "feu", "elem3": "air"}
afficher_trois_elements(**elements)
```

Ici, on passe en paramètre à la fonction, la valeur du paramètre dont le nom est égal à la clé de l'élément du dictionnaire

On peut aussi utiliser \* sur un dictionnaire, qui va renvoyer la liste des clés, puisque c'est ce que renvoi lorsqu'on fait une itération sur un dictionnaire.



## Principe du packing : définition d'une fonction
En mettant ```*args``` ou ```**kwargs``` dans la définition d’une fonction, on va faire du packing sur les variables envoyées à la fonction.  



On peut utiliser l'opérateur splat pour faire du paramétrage dynamique, c'est à dire définir des fonctions dont le nombre de paramètres n'est pas défini.
Encore une fois, ces paramètres qu'on souhaite passer et dont on ne connais pas le nombre vont être enpaquetés dans une liste, qui va pouvoir être utilisée dans le corps de la fonction:
```python
def multiply(*tous_les_elements): 
    res = 1
    for i in tous_les_elements:
        res = res * i
    return res
multiply(1, 2, 3)
```
Par convention, ce paramètre dont on ne connait pas la taille, doit être déclaré après les paramètres classiques, en dernier, n'apparait qu'une seule fois, et porte le nom par convention de ```*args```:
```python
def afficher(elem1, elem2, *elemx):
   print(elem1)
   print(elem2)
   for e in elemx:
       print("(*) %s" % e)
```

On peut également faire du paramétrage dynamique avec des paramètres nommés en utilisant ```**```, pour récupérer les paramètres dans un dictionnaire:
```python
def afficher_recette(recette, **ingredients): # ingrédients sera un dictionnaire
    print(recette)
    for ingredient in ingredients.items():
        print(" - %s: %s" % ingredient)
 
afficher_recette("moukraines à la glaviouse",
                 creme="trop", # on doit donner le nom de ce paramètre
                 moukraines= "suffisamment",
                 glaviouse="si disponible")
```
Par convention, ce paramètre s'appelle \*\*kwargs pour key-word arguments, et apparait après \*args.

On peut enfin tout utiliser dans une même fonction : 
```python
def affichage_hybride(parametre_normal,
                      parametre_avec_default="valeur par défaut",
                      *args,
                      **kwargs):
    print(parametre_normal)
    print(parametre_avec_default)
    print(args)
    print(kwargs)
```


Enfin, on peut définir des paramètres qui ne peuvent être passés qu’en spécifiant leur nom. On les appelle les « keyword only parameters ». Pour ce faire, il faut mettre au moins un ```*```, et tout ce qu’il y a après sans étoile ne peut plus être passé comme argument positionnel :
```python
>>> def coooool(normal, *args, keyword_only):
...    print(normal, args, keyword_only)
>>> coooool("yeah", "cool", "man")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: coooool() missing 1 required keyword-only argument: 'keyword_only'
>>> coooool("yeah", "cool", keyword_only="man")
yeah ('cool',) man
```

Si vous n’avez pas un \*args à placer, on peut mettre l’étoile toute seule :
```python
>>> def coooool(normal, *, keyword_only):
...    print(normal, keyword_only)
>>> coooool("yeah", "man")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: coooool() takes 1 positional argument but 2 were given
>>> coooool("yeah", keyword_only="man")
yeah man
```


## Packing et Unpacking implicite
Il s’agit d’unpacking et packing implicite puisqu’on a pas utilisé l’opérateur splat « * »

### Unpacking implicite
L’unpacking consiste à distribuer les variables :
a, b = (2, 3)


### Packing implicite
Le packing consiste à les regrouper :
Ma_liste = [a, b]


## Packing et Unpacking explicite


### Unpacking explicite
Unpacking explicite avec une liste, puis un dictionnaire
```python
def aire_rectangle(a, b):
    return a*b

def aire_rectangle(cote1=0, cote2=0):
    return cote1*cote2

if __name__ == '__main__':
    rec1 = [3, 8]
    rec2 = {'cote1':4, 'cote2':8}
    #La liste rec1 va etre depaquetee en arguments unitaires
    print aire_rectangle(*rec1)
    #Le dictionnaire rec2 va etre depaquete en arguments unitaires
    print aire_rectangle(**rec2)
```

Ainsi, si a est un dictionnaire, \*\*a renvoi les valeurs séparées du dictionnaire.
Si a est un tuple, \*a renvoi les valeurs séparées du tuple

### Packing explicite

packing explicite
```python
def aire_rectangle(*args):  # les arguments passes en parametre sont paquetes dans args qui se comporte comme un tuple
    if len(args) == 2:
        return args[0]*args[1]
    else:
        print('Merci de stipuler deux parametres')

def aire_rectangle2(**kwargs):  # les arguments passes en parametre sont paquetes dans kwargs qui se comporte comme un dictionnaire
    if len(kwargs) == 2:
        result = 1
        for key, value in kwargs.items():
            result *=value
        return result
    else:
        print('Merci de stipuler deux parametres')

if __name__ == '__main__':
    # Une liste va etre creee a partir des arguments fournis
    print aire_rectangle(3,8)
    Un dictionnaire va etre cree a partir des arguments nommes
    print aire_rectangle2(cote1=4, cote2=8)
```





# Docstring et doctest
Les docstrings sont les textes sous la définition des classes et des fonctions, définies par des triples guillemets.
On peut inclure des test dans ces docstring : il suffit de commencer une ligne de docstring par ">>>", et de donner le résultat attendu sur la ligne suivante : 
```python
def ma_func(a,b):
""" Somme simple :
      Exemple simple :
      >>> a = 5
      >>> b = 2
      >>> ma_func(a,b)
      7
"""
    return a + b

if __name__ = "__main__":
    import doctest
    doctest.testmod()
```

Il suffit ensuite de lancer le fichier : 
```
python mon_module_avec_docstring.py -v
```
On ajoute le -v pour avoir des infos.

Les docstring sont renvoyées par help(), et sont accessibles par les IDE et générateurs de docs.

Une docstring de module est placée juste après le commentaire d'encodage.  
Une docstring de classe est placée après sa définition  
Une doccstring de méthode est placée après sa définition  
Une docstring doit être rédigée en anglais.  
La docstring d'un objet est accessible par objet.\_\_doc\_\_  
On peut souligner les titres avec des = et les soustitres avec -  


# Bonnes pratiques

## Règles de programmation

Règles de construction de classe:
 - un __init__ doit complètement initialiser une instance. Après un appel à un init, l'utilisateur présume que l'instance est prête à être utilisée.
 

Liskov Substitution Principle : 
une classe enfant doit pouvoir être utilisée partout une classe mère est utilisatble.

Principe : 
DRY : Don't Repeat Yourself.

Dans une classe, les attributs commençants par "\_" ne sont pas fait pour être utilisés en dehors de la classe. Eviter donc de faire un appel var.\_mon\_attr

### Objets protégés et objets privés
Un attribut ou une méthode protégé est accessible depuis l'exterieur de l'instance, mais n'est pas fait pour ça. Pour indiquer qu'un attribut ou qu'une méthode est protégé, on commence par un underscore.

Un attribut ou un méthode privées n'est pas accessible depuis l'exteiru de l'instance. Pour rendre privé, on commence par un double underscore.

## List comprehension 
Pratique consistant à écrire une instruction for sur une seule ligne
```python
for a in b:
    c.append(a*2)
# devient
[c.append(a*2) for a in b]
```


## Classes concrètes et classes abstraites
Les classes abstraites sont des classes dont le seul but est de faire hériter d'autres classes. elles n'ont pas vocation à être utilisée seule. on peut ajouter des méthodes avec "raise NotImplementedError".
Les classes concrètes sont des classes qui ont vocation à être instanciées.

## Conventions d'écritures
- indenter par 4 espaces
- ne pas mélanger espace et tabulation
- lignes de 79 caractères maximum (voir 72 pour les docstring)
- couper les lignes après des virgules si entre parenthèses, crochets, acolades
- couper les lignes après symboles, avec "\" sinon
- 2 sauts de lignes entre classe et fonctino
- 1 saut de ligne entre 2 méthodes
- une seule importation par ligne, en commençant par les bibl standard, puis tierces, puis perso
- pas d'espace avant une virugile, un double point, ou un point virgule
- toujours entourer les opérateurs par des espaces




# Import et python path
PYTHON PATH est une variable système qui contient une liste de dossier, dans lequel python va chercher les modules quand on fait un import
Pour connaître l path utilisé, faire 
Import sys
Sys.path

Pour ajouter un dossier au python path, en ligne de commande
export PYTHONPATH=$PYTHONPATH:/home/olivier/test

Ajouter un fichier https://stackoverflow.com/questions/37006114/anaconda-permanently-include-external-packages-like-in-pythonpath

en .pth dans lib/sites-packages, contenant sur chaque ligne le dossier à ajouter

## Help
Pour obtenir des informations sur une classe, tapez :
    help(str) #Informations sur la classe str  
Aide sur un module :
    help("nom_module")

## Divers
Pour télécharger Python : python.org  
Un fichier python a pour extension ".py"  
IDLE permet d'écrire un programme python  
Si on lance un fichier python, un interpreteur s'ouvre.  



Python :
Sur un script : sont équivalents
Python mon_script.py
Python –m mon_script
Sur un package :
Python mon_package : cherche un fichier __main__.py, et l’execute si en trouve un, sinon renvoi une erreur
 

# Tkinter
Importer tkinter :
import tkinter
from tkinter import *
Code minimal : 
On importe Tkinter
from tkinter import *

On crée une fenêtre, racine de notre interface
fenetre = Tk()

On crée un label (ligne de texte) souhaitant la bienvenue
Note : le premier paramètre passé au constructeur de Label est notre
interface racine
champ_label = Label(fenetre, text="Salut les Zér0s !")

On affiche le label dans la fenêtre
champ_label.pack()

On démarre la boucle Tkinter qui s'interompt quand on ferme la fenêtre
fenetre.mainloop()
Les principaux widgets sont :
-	les labels
champ_label = Label(fenetre, text="contenu de notre champ label")
champ_label.pack()
-	les boutons:
bouton_quitter = Button(fenetre, text="Quitter", command=fenetre.quit)
bouton_quitter.pack()
-	ligne de saisie : 
var_texte = StringVar()
ligne_texte = Entry(fenetre, textvariable=var_texte, width=30)
ligne_texte.pack()
-	case à cocher
var_case = IntVar()
case = Checkbutton(fenetre, text="Ne plus poser cette question", variable=var_case)
case.pack()
-	Radio boutons – liste de choix exclusifs:
var_choix = StringVar()

choix_rouge = Radiobutton(fenetre, text="Rouge", variable=var_choix, value="rouge")
choix_vert = Radiobutton(fenetre, text="Vert", variable=var_choix, value="vert")
choix_bleu = Radiobutton(fenetre, text="Bleu", variable=var_choix, value="bleu")

choix_rouge.pack()
choix_vert.pack()
choix_bleu.pack()var_choix = StringVar()

choix_rouge = Radiobutton(fenetre, text="Rouge", variable=var_choix, value="rouge")
choix_vert = Radiobutton(fenetre, text="Vert", variable=var_choix, value="vert")
choix_bleu = Radiobutton(fenetre, text="Bleu", variable=var_choix, value="bleu")

choix_rouge.pack()
choix_vert.pack()
choix_bleu.pack()
-	liste déroulante
liste = Listbox(fenetre)
liste.pack()
liste.insert(END, "Pierre")
liste.insert(END, "Feuille")
liste.insert(END, "Ciseau")
-	Frame:
cadre = Frame(fenetre, width=768, height=576, borderwidth=1)
cadre.pack(fill=BOTH)

message = Label(cadre, text="Notre fenêtre")
message.pack(side="top", fill=X)


```python

```
