# Introduction PHP et MySql

# Description du guide

Ce guide ce veut d'être un aide-mémoire pour les opérations de bases en PHP ainsi que les notions Sql.

## PHP

### Description

PHP: Hypertext Preprocessor, plus connu sous son sigle PHP (sigle auto-référentiel), est un langage de programmation libre, principalement utilisé pour produire des pages Web dynamiques via un serveur HTTP, mais pouvant également fonctionner comme n'importe quel langage interprété de façon locale. PHP est un langage impératif orienté objet.

### Utilisation

PHP a permis de créer un grand nombre de sites web célèbres, comme Facebook, Wikipédia et etc. Il est considéré comme une des bases de la création de sites web dits dynamiques, mais également des applications web.

### Configuration de l'environnement de travail

Se référer au [guide](https://www.dropbox.com/sh/ng3cfib6mkz5vb7/AAAfjjyGkXm6k5YicMksqEOSa?dl=0&preview=Configuration+PHP+et+MySQL.pdf).

### Bonnes pratiques php

Voici un [guide](https://github.com/jupeter/clean-code-php) à lire sur les bonnes pratiques en php.

### Syntaxe

#### Ajouter des commentaires

```php
<?php

    //À noter, les commentaires sont généralement en vert dans le code

    // Une ligne de commentaire simple doit commencer par "//"
    // Exemple, ceci est un commentaire simple

    // Pour faire un bloc de commentaires, il faut utiliser "/**/"
    /*
        Toute cette section est un commentaire,
        Et il n'est pas nécessaire de mettre les "//" en début de ligne
    */
?>
```

Voir le [fichier](https://github.com/alexis35115/IntroductionPHP/blob/master/src/exemples/ecrireCommentaires.php).

#### Création d'une variable

Voir le [fichier](https://github.com/alexis35115/IntroductionPHP/blob/master/src/exemples/creationVariables.php) et pour connaître les types possibles voici une [référence](https://www.php.net/manual/fr/function.gettype.php#refsect1-function.gettype-returnvalues).

#### Intruction echo

```php
<?php
    // Affiche une chaîne de caractères

    echo("Ceci est un message qui sera affiché.");

    $message = "Ceci est un message à afficher";
    echo($message);
?>
```

#### Affichier les éléments d'une liste

```php
<?php

    // Description : Affiche des informations lisibles pour une variable.

    //Liste à afficher
    $fruits = ["banane", "pomme", "fraise"];

    print_r($fruits);
    // Affiche ceci à l'écran : Array ( [0] => banane [1] => pomme [2] => fraise )
?>
```

#### Opérateur (if, while, for, foeach, égalité)

Voir le [fichier](https://github.com/alexis35115/IntroductionPHP/blob/master/src/exemples/exempleOperateurs.php).

#### Utilisation de la "->"

Voir le [fichier](https://github.com/alexis35115/IntroductionPHP/blob/master/src/exemples/flecheSyntaxe.php).

#### Concaténation

Voir le [fichier](https://github.com/alexis35115/IntroductionPHP/blob/master/src/exemples/concatenation.php).

#### Utilisation du HTML et php

Pour inclure du HTML dans un fichier avec l'extension ".php", voir la [documentation](https://www.php.net/manual/fr/faq.html.php).

#### Connexion avec une base de données MySql

```php
<?php
    error_reporting(E_ALL);
    ini_set('display_errors', 1);

    $identifiant = 'root';
    $motDePasse = 'admin123';
    $nomServeur = 'localhost';
    $nomBaseDeDonnees = 'demowow';

    $chaineConnection = 'mysql:dbname='.$nomBaseDeDonnees.';host=' . $nomServeur;
    $basededonnees = new PDO($chaineConnection, $identifiant, $motDePasse);

    // l'objet $basededonnees sera avec lequel que nous allons pouvoir travailler avec la base de données
?>
```

##### Obtenir des données à partir de la base de données

```php

    include "database.php"; // Correspond au code de la section précédente

    $requeteAExecuter = "SELECT colone1 FROM nomTable";
    $objetQuiContientLaRequeteAExecuter = $basededonnees->prepare($requeteAExecuter);
    $objetQuiContientLaRequeteAExecuter->execute();
    $elementsRecuperes = $objetQuiContientLaRequeteAExecuter->fetchAll();

    print_r($elementsRecuperes);
    // Le print_r() permet l'affichage de tous les données
```

## MySql

### Qu'est-ce que phpMyAdmin

phpMyAdmin est un logiciel gratuit écrit en PHP, destiné à gérer l'administration de MySQL sur le Web. phpMyAdmin prend en charge un large éventail d'opérations sur MySQL et MariaDB. Les opérations fréquemment utilisées (gestion des bases de données, des tables, des colonnes, des relations, des index, des utilisateurs, des autorisations, etc.) peuvent être effectuées via l'interface utilisateur, tout en vous permettant d'exécuter directement toute instruction SQL. Voir le [guide d'utilisation](https://docs.phpmyadmin.net/fr/latest/user.html).

### Configurations de bases de phpMyAdmin

Se référer au [guide](https://www.dropbox.com/sh/ng3cfib6mkz5vb7/AAAfjjyGkXm6k5YicMksqEOSa?dl=0&preview=Configuration+PHP+et+MySQL.pdf).

### Création d'une base de données

#### Via phpMyAdmin

#### Via Sql

### Création d'une table

#### À quoi une table dans une base de données

#### Via phpMyAdmin

#### Via Sql

### Comment procéder à la suppression d'une table

phpMyAdmin n'offre pas l'option de supprimer une table via son interface, il faut donc procéder à la suppression via une commande SQL.

### Cas d'utilisations

#### Manipulations des données dans une table

##### Importance d'avoir une clé unique

##### Effectuer une recherche

##### Effectuer une mise à jour

##### Effectuer une suppression

##### Faire une mise à jour

#### Caractères d'échapement

### Astuces

