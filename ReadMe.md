# Apprendre Symfony 5 par la création d'un site e-commerce  #

Tuto Symfony 5

## Environnement ##

- server Symfony `symfony serve`
- BDD avec MySQL (voir fichier `.env`)

## Commandes ##

- Création du projet  
    `symfony new . --version="5.4.*" --webapp`  
  &nbsp;
- Mise en route du serveur symfony  
    `symfony serve --port=8081`  
  &nbsp;
- Création du controller Home  
    `symfony console make:controller Home`  
  &nbsp;
- Utilisation d'un thème [Bootstrap](https://getbootstrap.com/docs/5.3/examples/carousel/)  
  &nbsp;
- Création de l'entity User (utilisation du composant **security** de Symfony)  
    `symfony console make:User`  
  &nbsp;
  ![Création de l'entity User](/ReadMe/01_creation_de_l_entity_User.png)
- Création de la base de données
    - Modification du fichier `.env` : `DATABASE_URL="mysql://root:@127.0.0.1:3306/la_boutique_francaise?serverVersion=8&charset=utf8mb4"`
    - `symfony console doctrine:database:create`  
  &nbsp;
- Création de la migration de l'entity User  
    `symfony console make:migration`  
  &nbsp;
- Exécution de la migration de l'entity User  
    `symfony console doctrine:migrations:migrate`  
  &nbsp;
- Création du controller Register  
    `symfony console make:controller Register`  
  &nbsp;
- Création du formulaire d'inscription  
    - `symfony console make:form Register`  
  &nbsp;
  ![Création du formulaire d'inscription](/ReadMe/02_creation_du_formulaire_d_inscription.png)
    - Utilisation d'un [thème](https://symfony.com/doc/5.4/form/form_themes.html) pour le composant **form**.  
    Modification du fichier `config/packages/twig.yaml`
    - Ajout de champs à l'entity User  
    `symfony console make:entity User`  
  &nbsp;
  ![MAJ de l'entity User](/ReadMe/03_maj_de_l_entity_User.png)
  - [Typage](https://symfony.com/doc/5.4/reference/forms/types.html) des inputs du formulaire et personnalisation des labels  
  - Enregistrement des données du formulaire dans la table user  
  - Cryptage du mot de passe  
  Injection de la dépendance `UserPasswordEncoderInterface` dans le `RegisterController`  
  - Ajout de [contraintes](https://symfony.com/doc/5.4/validation.html#constraints) au formulaire  
  &nbsp;
- Changement de la langue locale dans le fichier `config/packages/translation.yaml`  
  &nbsp;
- Création de l'authentificateur de connexion  
  `symfony console make:auth`  
  &nbsp;
  ![Création de l'authentificateur](/ReadMe/04_creation_de_l_authentificateur.png)  
  &nbsp;
- Création du controller Account  
    - `symfony console make:controller Account`  
    - Mise à jour de fichiers liés au controller (vues + redirection)  
  &nbsp;
- Mise à jour de la navbar grâce à la fonction [`path`](https://symfony.com/doc/current/reference/twig_reference.html#path)  
  &nbsp;
- Redirection : modification du fichier `SecurityController`. La page *connexion* n'est plus accessible si l'utilisateur est déjà connecté  
  &nbsp;
- Création du controller AccountPasswordController  
    - `symfony console make:controller AccountPassword`  
    - Réorganisation des fichiers générés  
    - Création d'un formulaire de modification du mot de passe  
    `symfony console make:form ChangePassword`  
  &nbsp;
- Mise à jour du CSS  
  &nbsp;
- Installation du bundle [EasyAdmin](https://symfony.com/bundles/EasyAdminBundle/3.x/index.html)  
  `composer require easycorp/easyadmin-bundle`  
  &nbsp;
- Création du dashboard  
  `symfony console make:admin:dashboard`  
  &nbsp;
  ![Création du dashboard EasyAdmin](/ReadMe/05_creation_du_dashboard_EasyAdmin.png)  
  &nbsp;
- Création du CRUD  
  `symfony console make:admin:crud`  
  &nbsp;
  ![Création du CRUD](/ReadMe/06_creation_du_crud_EasyAdmin.png)  
  &nbsp;  
- Création de l'entity Category  
    `symfony console make:entity Category`  
  &nbsp;
  ![Création de l'entity Category](/ReadMe/07_creation_de_l_entity_Category.png)  
  &nbsp;  
  `symfony console make:migration`  
  `symfony console doctrine:migrations:migrate`  
  &nbsp;  
- Mise à jour du CRUD  
  `symfony console make:admin:crud`  
  &nbsp;  
  ![MAJ du CRUD](/ReadMe/08_maj_du_crud.png)  
  &nbsp;  
- Création de l'entity Product  
    `symfony console make:entity Product`  
  &nbsp;  
  ![Création de l'entity Product-a](/ReadMe/09a_creation_de_l_entity_Product.png)  
  ![Création de l'entity Product-b](/ReadMe/09b_creation_de_l_entity_Product.png)  
  ![Création de l'entity Product-c](/ReadMe/09c_creation_de_l_entity_Product.png)  
  ![Création de l'entity Product-d](/ReadMe/09d_creation_de_l_entity_Product.png)  
  ![Création de l'entity Product-e](/ReadMe/09e_creation_de_l_entity_Product.png)  
  `symfony console make:migration`  
  `symfony console doctrine:migrations:migrate`  
  &nbsp;  
- Mise à jour du CRUD  
  `symfony console make:admin:crud`  
  &nbsp;  
  ![MAJ du CRUD](/ReadMe/10_maj_du_crud.png)  
  &nbsp;
- Insertion des produits via `EasyAdmin`  
  &nbsp;  
- Création du controller Product  
    `symfony console make:controller Product`  
    - Création de la vue avec tous les produits  
    - Création de la vue pour un seul produit  
  &nbsp;  
- Correction du CSS  
  &nbsp;  
- Création du filtre de recherche