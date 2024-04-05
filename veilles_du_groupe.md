# VEILLES DU GROUPES

Je propose ce document pour lister notre veille de groupe, peut-être peut-on utiliser la trame suivante :

-----------------------

# TITRE DU PROBLEME

1. Description du problème rencontré
2. Solutions envisagées
3. Recherches effectuées / Outils trouvés / Confrontation des solutions / Cheminement ...
4. Solution appliquée
5. Commentaires

----------------------------

# MPD

1. Description du problème rencontré

Comme Adminer ne met pas les types de variables dans son schéma de BDD, on devait trouver autre chose.

2. Solutions envisagées

Apparemment il existe mySQLworkbench mais nous on a opté pour PHPmyAdmin

3. Recherches effectuées / Outils trouvés / Confrontation des solutions / Cheminement ...

Il suffit de copier le dossier de PhpMyAdmin dans son localhost pour avoir accès à ses BDD comme sur Adminer.
On a commencé à faire la structure de la BDD d'après le MLD.
On n'a pas réussi à créer nos clés étrangères du coup on est revenu sur Adminer pour le faire.
Puis on est revenu sur PHPmyAdmin pour faire le MPD.

4. Solution appliquée

- Utiliser PHPMyAdmin, cliquer sur sa BDD puis ->Concepteur.
- Déplacer les tables correctement.
- Exporter (menu de gauche)
- On peut même avoir le dico de données et le MLD dans le pdf
- Le schéma est riquiqui -> faire une capture d'écran éventuellement.

5. Commentaires
aa

---



# Problèmes avec les validations de contraintes  : DateTime

1. Description du problème rencontré

Lors du Create, la date mise en string empêche l'enregistrement car elle n'est pas valide par rapport à la contrainte `#[Assert\DateTime]`  

2. Solutions envisagées

Trouver une autre syntaxe

3. Recherches effectuées / Outils trouvés / Confrontation des solutions / Cheminement ...

On a essayé     
Eva : `#[ORM\Column(type: "datetime", nullable: true)]`
Mais en fait on s'est rendu compte que ça faisait doublon avec celui mis avant
Et du coup la migration renvoyait une erreur.
On a copié collé cent foisw pour effacer cent fois...

4. Solution appliquée  

Laurent a trouvé cette syntaxe qui semble fonctionner.
    #[Assert\type(Types::DATE_IMMUTABLE)]
On va l'éprouver avant de faire les rectis dans toutes les entités hein.

5. Commentaires  

Ne pas appliquer un changement trop vite. Noter le problème pour ne pas oublier ce qu'on recherchait.
Finalement, on a compris qu'il y avait deux types de validation à mettre en place : via Symfo et via Doctrine.

---


# Problèmes avec les validations de contraintes  : Enum

1. Description du problème rencontré

Le type Enum n'est pas implémenté dans Doctrine contrairement à dans Eloquent.

2. Solutions envisagées

On a essayé des annotations différentes sans succès.

3. Recherches effectuées / Outils trouvés / Confrontation des solutions / Cheminement ...

### On a essayé d'adapter /comprendre

a. le tuto de symfonyCasts

b. https://knplabs.com/en/blog/how-to-map-a-php-enum-with-doctrine-in-a-symfony-project/ 

c. https://debest.fr/en/blog/php-8-1-enums-doctrine-and-symfony-enumtype    

d. https://smaine-milianni.medium.com/use-php-enums-as-doctrine-type-in-symfony-85909aa0a19a 

Il existe un bundle sympa pour avoir tous les types SQL dans Doctrine (mais pas ENUM ;) )**https://github.com/beberlei/DoctrineExtensions**


La solution la plus appropriée semblerait de créer un type custom en suivant la doc de Doctrine mais j'ai trouvé une solution "rustine" moins chronophage : mettre un champ texte avec des valeurs imposées.

4. Solution appliquée  

``` composer require symfony/expression-language ```

```
    #[Assert\ExpressionSyntax(
        allowedVariables: ['user', 'shipping_centers'],
    )]
    protected string $shippingOptions;

```
On peut personnaliser le message

5. Commentaires  

Il y avait aussi la possibilité d'utiliser un assert de type choices ?

---

