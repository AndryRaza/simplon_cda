# Design Patterns

## Abstract Class

C'est une classe qui n'est ni complète, ni instanciable. Elle sert de base à d'autres classes dérivées. (wikipedia)

Ex :
<pre>
//Abstract class 
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}


// Subclass (inherit from Animal)
class Pig extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
}

class Main {
  public static void main(String[] args) {
    Pig myPig = new Pig(); // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}

</pre>

## Static method / method 

Static method : On n'instancie pas un objet pour pouvoir utiliser la "method" de cette classe

Ex :

<pre>

Static Method: $item = Item::getDetail(15);

Instance Method: $item = getDetail(15);

</pre>

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

- Singleton Design Pattern

Les classes ne peuvent avoir qu'une instance. L'objet créé par ces classes est global.

Par exemple : Il est défini comme quoi il n'y a qu'un président de la République, et le titre de "Président de la République" est accessible à tous pour identifier le président (son nom, etc).

Exemple code :

On va implémenter une classe "livre empruntable" qui renvoie son titre et son auteur à celui qui l'a emprunté. Lorsque quelqu'un emprunte le livre, une variable "estEmprunté" se mettra à vrai, il pourra alors lire le titre et l'auteur du livre. Une 2ème qui souhaiterai faire de même ne pourra donc pas. 

<pre>
class BookSingleton {
    private $author = 'Gamma, Helm, Johnson, and Vlissides';
    private $title  = 'Design Patterns';
    private static $book = NULL;
    private static $isLoanedOut = FALSE;

    private function __construct() {
    }

    static function borrowBook() {
      if (FALSE == self::$isLoanedOut) {
        if (NULL == self::$book) {
           self::$book = new BookSingleton();
        }
        self::$isLoanedOut = TRUE;
        return self::$book;
      } else {
        return NULL;
      }
    }

    function returnBook(BookSingleton $bookReturned) {
        self::$isLoanedOut = FALSE;
    }

    function getAuthor() {return $this->author;}

    function getTitle() {return $this->title;}

    function getAuthorAndTitle() {
      return $this->getTitle() . ' by ' . $this->getAuthor();
    }
  }
 
class BookBorrower {
    private $borrowedBook;
    private $haveBook = FALSE;

    function __construct() {
    }

    function getAuthorAndTitle() {
      if (TRUE == $this->haveBook) {
        return $this->borrowedBook->getAuthorAndTitle();
      } else {
        return "I don't have the book";
      }
    }

    function borrowBook() {
      $this->borrowedBook = BookSingleton::borrowBook();
      if ($this->borrowedBook == NULL) {
        $this->haveBook = FALSE;
      } else {
        $this->haveBook = TRUE;
      }
    }

    function returnBook() {
      $this->borrowedBook->returnBook($this->borrowedBook);
    }
  }
 
/**
 * Initialization
 */

  writeln('BEGIN TESTING SINGLETON PATTERN');
  writeln('');

  $bookBorrower1 = new BookBorrower();
  $bookBorrower2 = new BookBorrower();

  $bookBorrower1->borrowBook();
  writeln('BookBorrower1 asked to borrow the book');
  writeln('BookBorrower1 Author and Title: ');
  writeln($bookBorrower1->getAuthorAndTitle());
  writeln('');

  $bookBorrower2->borrowBook();
  writeln('BookBorrower2 asked to borrow the book');
  writeln('BookBorrower2 Author and Title: ');
  writeln($bookBorrower2->getAuthorAndTitle());
  writeln('');

  $bookBorrower1->returnBook();
  writeln('BookBorrower1 returned the book');
  writeln('');

  $bookBorrower2->borrowBook();
  writeln('BookBorrower2 Author and Title: ');
  writeln($bookBorrower1->getAuthorAndTitle());
  writeln('');

  writeln('END TESTING SINGLETON PATTERN');

  function writeln($line_in) {
    echo $line_in.'<br/>';
  }
?>
</pre>

## Structural design patterns

Class and Object Composition. La notion d'héritage (parent-enfant) est utilisée pour la création de classe. Les objets eux sont définis à partir de méthodes définies, et peuvent avoir de nouvelles propriétés. 

- Proxy

Représentation d'un objet par un autre objet (Par exemple, payer avec un chèque mais derrière ca c'est payé par les fonds dans le compte).

On ne souhaite pas instancier l'objet tant qu'on a pas besoin. 

Apparemment, ca bouffe beaucoup de ressources les objets

- Decorator

Pouvoir rajouter des propriétés dynamiquement à des objets sans pour autant modifier la propriété de la classe (c-a-d pouvoir modifier un objet en particulier sans que ca touche aux autres même objet)

## Behavioral design patterns 

C'est + pour la communication entre classes d'objet

- Strategy

Créer pleins d'algorithmes, chaque interface pourra utiliser ses algorithmes.

- Template method

On va définir un algorithme général pour une classe entière. Les fonctions/méthodes définies ne seront pas tous obligatoirement requises/utilisées. Les fonctions doivent alors ne rien retourner (return NULL)


- Visitor 

Pouvoir définir de nouvelles opérations/fonctions/méthodes sur un autre objet sans en modifier sa classe

Exemple : Une personne appelle un taxi. Le taxi c'est le "visitor", lorsque la personne va rentrer dans le taxi, le taxi fera le changement personne => client. 