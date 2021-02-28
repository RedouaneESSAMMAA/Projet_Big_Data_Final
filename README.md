# *Système de gestion d’emprunt dans une librairie*

L'objectif de ce projet est de faire la gestion d'emprunt dans une librairie via des manipulations des bases de données en utilisant SQL et DSL avec spark.

## Aperçu sur les bases de données :

**book**    : représente une table de livres. Chaque ligne est un livre décrit par son identifiant, son titre et sa catégorie (roman, science-fiction, musique, etc.).


| bid|               title              |   category|
-----|----------------------------------|------------
|0001|L'existentialisme est un humanisme|Philosophie|
|0002|Huis clos. Suivi de Les Mouches   |Philosophie|
|0003|Mignonne allons voir si la rose   |Poeme      |
|0004|Les Amours                        |Poème      |

**Authors** : représente une table d'auteurs. Chaque ligne contient le nom et l'identifiant d'un auteur.

|  aid|             name|
------|------------------
|07890| Jean Paul Sartre|
|05678|Pierre de Ronsard|


**Student** : représente une table d'étudiants. Chaque ligne est un étudiant décrit par son identifiant, son nom et son département (informatique, mécanique...).

|sid|sname|     dept|
----|-----|----------
|S15| toto|     Math|
|S16| popo|      Eco|
|S17| fofo|Mécanique|

**write**   : représente l'association entre les auteurs et les livres. Une ligne de cette table signifie que l'auteur a écrit le livre bid.

|  aid| bid|
------|-----
|07890|0001|
|07890|0002|
|05678|0003|
|05678|0003|

**borrow**  : représente les informations de prêt de livre. Une ligne de cette table signifie que l'étudiant a emprunté le livre bid  , à la date checkout-time et l'a retourné à la date return-time. 

|sid| bid|checkout-time|return-time|
----|----|-------------|------------
|S15|0003|   02-01-2020| 01-02-2020|
|S15|0002|   13-06-2020|       null|
|S15|0001|   13-06-2020| 13-10-2020|
|S16|0002|   24-01-2020| 24-01-2020|
|S17|0001|   12-04-2020| 01-07-2020|

Le fichier output contient les résultat de la question 8.
