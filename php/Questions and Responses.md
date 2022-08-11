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

4. 