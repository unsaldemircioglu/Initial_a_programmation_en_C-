# Initial_a_programmation_en_C-
Initial_a_programmation_en_C++ Lesson Notes


Exercice 1 : âge du capitaine
Cet exercice correspond à l'exercice n°1 (pages 13 et 195) de
l'ouvrage C++ par la pratique (3e édition, PPUR).
Voici une solution :
#include <iostream>
using namespace std;
int main()
{
cout << "Entrez votre âge :" << endl; // Affichage de la question
int age; // Déclaration de variable pour s
cin >> age; // Lecture de la réponse
// Déclaration et initialisation de la variable pour stocker l'année de
int annee(2015 - age);
// Affichage de l'année de naissance (stockée en mémoire)
cout << "Vous êtes né(e) vers l'année " << annee
<< endl;
return 0;
}
Il y a cependant de multiples manières de manipuler ces variables. Elles peuvent par exemple
être déclarées plus tôt (mais je vous conseille plutôt de toujours déclarer vos variables au plus
près de leur utilisation et aussi de toujours les initialiser, ce qui n'est pas le cas ci-dessous) :
#include <iostream>
using namespace std;
int main()
{
// Déclarations
int age;
int annee;
cout << "Entrez votre âge :" << endl; // Affichage de la question
cin >> age; // Lecture de la réponse
annee = 2015 - age; // Calcul
// Affichage de l'année
cout << "Vous êtes né(e) vers l'année " << annee << endl;
return 0;
}
Si ce n'était pas imposé par la donnée, on pourrait aussi ne pas utiliser de variable intermédiaire
et effectuer le calcul directement au moment de l'affichage :
#include <iostream>
using namespace std;
int main()
{
cout << "Entrez votre âge :" << endl; // Affichage de la question
int age; // Déclaration
cin >> age; // Lecture de la réponse
// Affichage de l'année
cout << "Vous êtes né(e) vers l'année " << 2015-age << endl;
return 0;
}
Exercice 2 : fondue
#include <iostream>
using namespace std;
int main()
{
const int BASE(4); // nombre de personnes pour la recette de base
// Pour faire une fondue fribourgeoise pour 4 personnes il faut :
double fromage(800.0); // 800gr de Vacherin fribourgeois
double eau(2.0); // 2dl d'eau
double ail(2.0); // 2 gousses d'ail
double pain(400.0); // 400 gr de pain
/* On supposera pour cet exercice que l'utilisateur ne saisit que
* des valeurs strictement positives mais nous pourrons faire mieux
* dès la semaine prochaine
*/
cout << "Entrez le nombre de personnes conviées à la fondue : ";
int nb_convives;
cin >> nb_convives;
// Mise à jour des quantités en fonction du nombre de convives :
double ratio = nb_convives; // Notez le 'double' ici...
ratio /= BASE; // ... pour éviter une division entière.
fromage *= ratio;
eau *= ratio;
ail *= ratio;
pain *= ratio;
cout << "Pour faire une fondue fribourgeoise pour " << nb_convives
cout << ("il vous faut : ") << endl;
cout << " - " << fromage << " gr de Vacherin fribourgeois" << endl
cout << " - " << eau << " dl d'eau" << endl;
cout << " - " << ail << " gousse(s) d'ail" << endl;
cout << " - " << pain << " gr de pain" << endl;
cout << " - du poivre à volonté" << endl;
return 0;
}
Exercice 3 : variables
Cet exercice correspond à l'exercice n°2 (pages 13 et 196) de
l'ouvrage C++ par la pratique (3e édition, PPUR).
Programme :
#include <iostream>
using namespace std;
int main()
{
int x, y; // Déclarations
double a, b, c, d;
x=2; y=4; // Affectations
a=x+y; b=x-y; c=x*y; d=x/y; // Opérations
// Affichage des résultats
cout << x << "+" << y << "=" << a << " ; "
<< x << "-" << y << "=" << b << endl
<< x << "*" << y << "=" << c << " ; "
<< x << "/" << y << "=" << d << endl
;
return 0;
}
Puis même chose en remplaçant «int x, y;» par «double x, y;», puis par «int x;
double y;».
Explications :
Lorsque les deux opérandes (x et y) sont de type entier, l'expression x/y la division qui
s'effectue est la division entière (ou division «euclidienne») ! C'est-à-dire que le résultat est le
quotient. Dans le cas précis (x=2 et y=4), on obtient bien 0 :
x = 0 * y + 2
Par contre, dès qu'une opérande est de type double, c'est une division réelle qui est effectuée.
C'est-à-dire que le résultat est la valeur (approchée à la précision des double) du nombre réel
correspondant.
