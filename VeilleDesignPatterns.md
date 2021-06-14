# Design Patterns

## Creational Design Patterns

Instancier une classe ! C'est divisé en 2 schémas : un schéma pour créer les classes, et un schéma pour créer des objets

L'héritage est utilisé dans les schémas de création de classe.

- Abstract Factory

Créer une "interface" générale, puis expliciter en plusieurs interfaces/objets/produits cette "interface" générale. Ces interfaces/objets/produits héritent de certaines propriétés de l'interface parent.

Souvent utilisé pour les créations cross-platform UI. 

- Prototype

Copier un objet déjà existant pour créer un nouvel objet, le nouvel objet n'est pas dépendant de la classe de l'objet copié


Inconvénient : certains objets ont des propriétés privées, qui ne seront donc pas copiés. 

Solution : Proposer une interface commun à tous les objets qui peuvent être clonés. 

## Structural design patterns

Class and Object Composition. La notion d'héritage (parent-enfant) est utilisée pour la création de classe. Les objets eux sont définis à partir de méthodes définies, et peuvent avoir de nouvelles propriétés. 

- Proxy

Représentation d'un objet par un autre objet (Par exemple, payer avec un chèque mais derrière ca c'est payé par les fonds dans le compte).

On ne souhaite pas instancier l'objet tant qu'on a pas besoin. 

Apparemment, ca bouffe beaucoup de ressources les objets

## Behavioral design patterns 

- Strategy

C'est + pour la communication entre classes d'objet

Créer pleins d'algorithmes, chaque interface pourra utiliser ses algorithmes.





