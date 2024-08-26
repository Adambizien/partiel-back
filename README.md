# Partiel de front pour S2 A2 NWS

### Étape 1 : <br>
  - Initialisation du projet avec les commandes : <br>
      - Si vous n'avez pas Symfony : <br>
      ```
        curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | sudo -E bash
        sudo apt install symfony-cli
        symfony
      ```
    
    - Pour créer le projet : <br>
    ```
      symfony check:requirements
      symfony new my_project_directory --version="7.0.*" --webapp
    ```

    - Pour installer l'ORM : <br>
    ```
      composer require orm
      composer require --dev symfony/maker-bundle
      composer require --dev orm-fixtures
    ```
      Créer le fichier .env.local avec le nom de la base de données souhaitée.<br>
    - Créer la base de donnée :
    ```
      php bin/console doctrine:database:create
    ```
- implémenter boostrap : 
  - header :
  ```
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
  ```
- body :
  ```
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
  ```
- Créer le home : 
```
  php bin/console make:controller
```

### Étape 2 [ici]() : <br>
  - Faire un subscribe pour styliser nos pages d'erreur : <br>
```
    php  bin/console make:subscriber
        -> ExceptionSubscriber
        ->  kernel.exception
```
  - Puis modifier le fichier ExceptionSubscriber.php.<br>
  - Enfin, ajouter le template d'erreur.
  - Si vous modifiez le template d'erreur, supprimez le cache pour que les modifications soient prises en compte (exécutez ``` php bin/console cache:clear ```).
- Appliquer le style avec boostrap [ici]()
    
