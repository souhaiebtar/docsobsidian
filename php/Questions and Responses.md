1. on considere le code suivant:

```
$entityManager = $this->getDoctrine()->getManager();

$product = new Product();
$product->setName('Laptop');
$product->setPrice(2499);
$product->setDescription('Polished and bitten');
```

quel code doit on ajouter pour sauver le produit dans la base de données ?

```
$entityManager->persist($product);
$entityManager->flush();
```

2. comment obtenir tous les bundles ?
`$this->container->getParameter('kernel.bundles');`

3. quelle annotation de validation de contrainte disponible dans Symfony 4.1+ peut-on utiliser pour valider un email en utilisant la validation html5 ?
`@Assert\Email(mode = "html5")`

4. On Considère le code suivant:
```
/**
* @Route("/products/{productId}/edit", name = "edit_product")
*
* /
public function editProductAction(Request $request, Product $product)
{
	//
}
```
comment configure-t-on `ParamConverter` pour que le paramètre `productId` soit affecté à la propriété `id` de `Product` ? 

`@ParamConvert("product", options={"mapping": {"prductId": "id"}})`

5. quel types de messages FlashBag sont-ils supportés par Symfony ?
le tye de messages est une chaine de caractère et peut donc adopter n'importe quelle valeur souhaitée

6. quelles méthodes doivent etre définies lors de l'implémentation de `Symfony\Component\Security\Core\User\UserProviderInterface` ?
* `refreshUser(UserInterface $user)`
* `loadUserByUsername($username)`

7. quelle option de la ligne de commande permet de spécifier un commentaire de commit à l'exécution de `git commit` ?
`-m`

8. quel fichier mis à la racine de votre dépot est utilisé par **Github** pour afficher un résumé ou de la documentation relative à votre page ?
`README.md`

9. un dépot distant a pour URL: `https://github.com/hellogit/hello.git` , Ecriverz la commande utilisée pour créer une copie locale de ce dépot dans le repertoire courant
`git clone https://github.com/hellogit/hello.git`

10. on vous demande de corriger le bug n 33. vous créez donc une nouvelle branche `bugfix33` et commitez les changements requis sur cette branche, Ecrivez la prochaine commande git qui merge ces changements sur la branche `master` (la branche courant),
`git merge bugfix33`

11. qu'est-ce qui  est **vrai** à propos de l'option `--amend` de la commande `git commit` ?
* elle ne peut modifier que le dernier commit
* elle peut a la fois modifier le message de commit et ajouter des nouveaux fichiers au meme commit

12. Pour Investiguer un probleme, vous avez besoin de lancer un **shell interactif**  (bash) dans un container en cours d'exécution  nommé `mycontainer` , votre but est de pouvoir exécuter des commandes  depuis l'interieur du container. quelle commande utiliseriez-vous pour lancer ce shell ?
* `docker exec -it mycontainer  /bin/bash`

13. quel est le role de l'instruction `EXPOSE` dans un Dockerfile ?
elle indique au demon docke que le container sera a a l'ecoute d'un port donne

14. `COPY` et `ADD` sont des instructions du dockerfile utilisées pour copier un fichier dans le container durant la phase de build. mais il y a une difference entre ces instructions ?
* `COPY` n'a pas la possibilité d'extraire les archives tar  ou d'aller recuperer un fichier depuis un url alors que `ADD` le peut

15. pour garantir la pérennité de votre serveur, vous avez besoin d'afficher des informations relatives à la quantité d'espace disque utilisé par le démon docker. quelle commande est appropriée pour ce cas de figure ?
`docker system df`

16. vous gérez le cluster Docker Swarm ci-dessus. Comme le nombre d'utilisateurs croit vous avez besoin de redimensionner la taille de votre cluster. (constitue de 1 master et 2 esclave)
* Ajouter 1 maitre et 2 esclaves (generalement lors de l'ajout on ajoute plus d'esclave que de maitre)

17. les abstractions ne doivent pas dependre de details. les details doivent dependre d'abstractions.
* vrai

18. la fonction
```PHP
function setName( $name = 'John Doe' ){
	return $name;
}
```

quel serait le resultat si la fonction `setName` etait appelee sans fournir d'argument?

*  la fonction retrournerait la valuer 'John Doe'

19. `<?= $a ?>` est un raccourci pour ...
* `<?php echo $a; ?>`

20. le code
```PHP
$a = 4;
$b = 10;

$sentence = "There are ".$a++." cakes for ".++$b." people.";
```

quelle est la valeur de la variable $sentence ?

`There are 4 cakes for 11 people.`

21. quelle fonction n'est pas un fonction PHP par default ?
* print_r
* floatval
* is_real
* getsize (thre correct response)

22. saisissez le nom de la fonction qui convertit tous les caractères éligibles  en entités HTML (par exemple pour  transformer  © en @copy;)
* htmlentities

23. quel est la fonction  qui test la fin d'un fichier sur un pointeur de fichier ?
* feof
24. implementez la fonction `closestToZero`  pour renvoyer  l'entier  du tableau `$ints` le plus proche de zéro.
*  s'il y a deux entiers tout aussi proches de zero, considerez l'entier positif comme etant le plus porche de zero(par exemple si `$ints` contient -5 et 5, retournez 5)
* si `$ints` est vide, retournez 0 (zero)
Donnees: les entiers dans $ints ont des valeurs 

**Solution:**

```PHP
function closestToZero($ints) {

  

if (!count($ints)) {

return 0;

}

  

sort($ints);

  

foreach($ints as $x) {

$intgersAbs[] = abs($x);

}

  
  

$index = array_search(min($intgersAbs), $intgersAbs);

  

if ($ints[$index] === $ints[$index+1] * -1) {

return $ints[$index+1];

} else {

return $ints[$index];

}

}
```

25. probleme:

![[Pasted image 20220814155259.png]]

Solutions:

```PHP
function isLourd($mass) {

if ($mass > 20) {

return true;

}

return false;

}

  

function isEncombrant($width, $height, $length) {

if (

($width * $height * $length >= 1000000) ||

(

$width > 150 || $height > 150 || $length > 150

)

) {

return true;

}

  

return false;

}

  

function solve($width, $height, $length, $mass) {

if (

!isLourd($mass) && !isEncombrant($width,$height,$length)

) {

return 'STANDARD';

}

  

if (

isLourd($mass) && isEncombrant($width, $height, $length)

) {

return 'REJECTED';

}

  

return 'SPECIAL';

}
```

26. ecrivez une fonction calc($array, $n1, $n2) 
$array est un tableau  d'entiers. les parametres $n1 et $n2 sont des entiers definis par la relation `0 <= $n1 <= $n2 < count($array)`

la fonction `calc` doit retourner la somme des entiersde `$array` dont l'index appartient a l'intervalle `[$n1,$n2]`

Solution:
```PHP
function calc($array, $n1, $n2) {

$sum = 0;

for($x = $n1; $x <=$n2; $x++) {

$sum += $array[$x];

}

  

return $sum;

}
```

27. en javascript comment declarer une variable ?
var x = 7;

28. en javascript `isNAN()` est une fonction permettant d'evaluer si une valeur donnee:
* n'est pas un nombre 

29. En javascript, laquelle de ces expressions de declaration de fonction est invalide ?
* `var add(x,y)=return x+y`  // celle est invalide
* `var add = (x,y)=> x+y`
* `function add(x,y){return x+y}`
* `var add = function(x,y) {return x+y}`

30. quel  devez-vous ajouter apres les deux lignes suivantes pour que le tableau A contienne une concatenation du tableau A et B ?
var a = [1,2,3];
var b = [4,5,6];
reponse: a = a.concat(b);

31. Soit un objet `obj` defini par le code:
```PHP
MyClass = function() {
	this.a = 'hello'
	this.b = 'world'
}

MyClass.prototype.a = 'john'
MyClass.prototype.c = 12

obj = new MyClass()
```

`obj.a` s'evalue `hello`
`obj.b` s'evalue `world`
`obj.c` s'evalue `12`
