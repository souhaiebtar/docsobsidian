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

7