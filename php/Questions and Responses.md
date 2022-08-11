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

