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
* *
