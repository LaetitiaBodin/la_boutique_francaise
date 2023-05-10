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
  ![Création de l'entity User](/ReadMe/01_creation-de-l-entity-User.png)  
  &nbsp;
- Création de la base de données
    - Modification du fichier `.env` : `DATABASE_URL="mysql://root:@127.0.0.1:3306/la_boutique_francaise?serverVersion=8&charset=utf8mb4"`
    - `symfony console doctrine:database:create`  
  &nbsp;
- Création de la migration de l'entity User  
    `symfony console make:migration`  
  &nbsp;
- Exécution de la migration de l'entity User  
    `symfony console doctrine:migrations:migrate`