# Lundi 18 Mars 2024

Premier call de mise au point des O’PME :
Fayis → P.O.
Laure → Scrum
Théophile → Lead Front
Laurent → Lead Back
Eva → Git Master

Après une présentation des objectifs du projet par Fayis, chacun des autres participants va mettre ci-dessous ce qu’il a cru comprendre des attentes du projet  en esquissant un morceau de cahier des charges. On laisse le soin à Fayis de nous apporter les informations complémentaires et rectifier nos dires:) 
On se regroupe lundi prochain pour rassembler nos idées sur les MCD/MLD/MPD, user stories, arborescence de pages et wireframes.

------------------------------------------------------------------------------------------
CAHIER DES CHARGES  d’après LAURE

Objectifs : 
- créer une application web de gestion des devis pour une PME de broderie.
- Permettre la visualisation / création/ modification/  suppression des devis, commandes ,produits, options et factures
- On part de l’expression d’un besoin d’un client qui va être matérialisé dans un devis puis ensuite envoyé en commande pour finalement être édité dans une facture au format pdf.

Acteurs :
L’utilisateur est le gérant de la boîte. Il va rentrer le devis dans son logiciel et le mettre en commande jusqu’à sa livraison. Une fois la livraison effectuée, il éditera une facture au format pdf.
Il attribuera le devis à un client s’il existe déjà ou en créera un nouveau sinon.
Le client n’interagit pas avec le logiciel.

MVP :
- CRUD des différentes entités
- que l’utilisateur puisse faire le parcours de la création du devis à la création de la facture

Fonctionnalités avancées : 
- pouvoir accéder à la page de création d’un client à partir de la page de création du devis
- autocomplétion du champ de recherche lors de la recherche du nom d’un client
- pouvoir filtrer /rechercher les clients en fonction de critères géographiques etc..
- permettre de personnaliser l’app pour usage par d’autres PME 

Difficultés et questionnements actuels : 
- a-t-on besoin d’une authentification ? Et si oui, comment la mettre en place ?
- autocomplétion du champ de recherche??
- les filtres sont-ils du ressort du back ou du front ? Des deux:)
- comment faire une facture en pdf ?

------------------------------------------------------------------------------------------------------

Cahier des charges d’après Laurent : 

Objectifs du projet : 

Fournir un outil de gestion de commande pour un public de pme , il doit pouvoir éditer , un devis lié à un client soit existant soit en créant un nouveau client , une fois le devis validé il passe en commande et une fois la commande terminé une facture sera éditée au format pdf.

MVP:

    • Une page d’accueil  incluant un lien vers l’édition d’un devis et l'édition d’un nouveau client mais également un lien pour afficher la liste des produits .

    • Une page d’édition du devis doit obligatoirement être lié à un client existant et le cas échéant on doit pouvoir créer le nouveau client via un formulaire pop up sans perdre les données du devis. On doit également pouvoir choisir un produit et lui associer d'éventuelles options . une fois le devis édité nous devons pouvoir l’envoyer par mail. (crud complet )

    • Une page d’édition de commande en lien avec les données préalablement validées via le devis . Cette commande doit être lié avec le profil du client ainsi que le devis lié . (crud complet)

    • Une interface d’admin afin d’avoir la main pour ajouter , supprimer , modifier des produits ou des options 

Fonctions avancées:
    • Pouvoir générer des statistiques par client sur leur nombre de commandes .
    • Un menu supplémentaires pour gérer les factures

Difficultés identifiées : 

    • Doit on gérer les authentifications avec des rôles définis et des accès limités
    

Technologies : 

    • Symfony, React , Mysql , API 



# Lundi 25 Mars 2024

Call de groupe : 
Echanges sur le cahier des charges, user stories, MCD, wireframes, qqs scénarios utilisateur
Demain : 
    • Eva, Théophile -> wireframes
    • Laurent et Laure ->  MCD
    • Fayis -> helper et peaufinage CDC + arborescence des pages
 Point avec Clara à 11h

# Mardi 26 Mars 2024

## Entretien avec Clara 

TODO
- faire l’arborescence
- compléter les user stories
- rajouter l’entité de USER et la lier au contrat
- mettre le MCD en anglais , rajouter le mot contrat à code dans la propriété code de contrat
- mettre le MLD en anglais aussi, ne pas mettre d’espace
- dans  le mCD retirer création et modification comme c updated at et crated at
- ds le dico de données, préciser les created at et updated à la fin de chaque table
- Pour le MPD : le terme id figure ainsi que les clés étrangères, pour chaque champ, le type
- voir si Adminer peut le faire ou phpMyAdmin
- Wireframes mettre des légendes pour expliquer les éléments( bouton, lien, image etc…)
- Ne pas mettre de couleur sur un wireframe.
- Faire une vue desktop et une vue mobile par étudiant
- pas besoin de faires toutes les wireframes tant qu’on en a 2 chacun

- Quand le sprint 0 sera fini, on pourra rajouter les user sorties dans le Kanban
- Faire un doc de veille pour lister les problèmes et le lien de la solution, pas tout mais quelques trucs intéressants

- Faire une charte graphique avec couleurs , logo, polices,

- RGPD si on collecte des données il faut qu’elles soient indispensables, le justifier
->  laurent va demander à madame :p 

- Mentions légales : infos de l’entreprise SIRET etc…

------------------------------------------------------------------------------------------------------

Laurent et Laure MCD et autres ok , à voir en équipe pour les détails ( ?? user id dans contract pour validated_by ?)

Wireframes en cours, changement de logiciel whimsical->figma

Fayis a fait une arborescence avec LucidChart

------------------------------------------------------------------------------------------------------

# Mercredi 27 Mars 2024

Point matinal : 
    • docs BDD ok Laurent et Laure, en attente review Fayis et reste de l’équipe
    • wireframes à terminer et à légender
3.1 à dupliquer
4.1 textile 
5.1 - broderie
Passer en commande , passer en facture
Eva théo ---> responsive et légendes

Laurent Laure et Fayis s’occupent de revoir les user stories et tous les docs BDD

- Faire un document readme avec les explications pour installer les porjets dans chaque repo front et back
- Faire des conventions de n hommage pour les branches


## Conventions de nommage pour les branches git

Noms de commits d'apres liste ci-dessous:
- git commit -m "feat: add contact page" →gitmoji :rocket:
- git commit -m "fix: login issue when no email" →gitmoji :sparkles:
- git commit -m "refacto: better homepage styling " →gitmoji :art: 
- git commit -m "docs: added documentation for image upload"→gitmoji :memo:
- git commit -m "wip: MailHog configuration not finished"→gitmoji :construction:

| Type du commit | Explication| Emoji à placer au début du commit | Exemple |
| ----------- | ----------- |----------- |----------- |
| feat  |Rajout d'une fonctionnalité|:rocket:|":rocket: add contact page" 
| fix |  Réparation d'un bug|:sparkles:|":sparkles: login issue when no email"
| refacto | Refactorisation|:art:|":art: better homepage styling "
| docs | Documentation|:memo:|":memo: added documentation for image upload"
| wip | En cours |:construction:|":construction: MailHog configuration not finished"

Exemple :- git commit -m ":construction: authentification"


Comptes github: 
-evafontainee
-ApuCalypse
-TheophileLefer
-ridculle

## Conventions de nommage pour les méthodes des controller cf doc de Fayis : 

| Nom de la méthode  | Action | Méthode HTTP |
| ----------- | ----------- |----------- |
| index |Show all listings| GET |
| show |Show one listing | GET |
| create | Show form to create new listing | GET |
| store | Store one listing | POST |
| edit | Show form to create new listing | GET |
| update | Update listing | POST |
| destroy | Delete listing | POST |

### **A soumettre aux backeux :**

Perso je suis pas à l'aise avec ces mots

- je crois qu'on a des méthodes de controller pour lesquelles on va avoir POST et GET en même temps, du coup on utilise le même nom de méthode de controller mais avec la méthode HTTP différente
- les termes add/delete me parlent mieux que create/destroy
- mais bon on choisira en créant le premier controller, il sera encore temps de modifier au début.




