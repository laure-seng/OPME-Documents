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

-------------------------


----------------------------

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

-------------------------
