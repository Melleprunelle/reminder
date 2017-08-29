#### LES ROUTES À UTILISER :

##### Pour l'admin

* #### Requête d'authentification :  /login (POST) (Demande une authentification en tant que session d’administration)

    >*  **Paramètres envoyés**

    ```
    {
            "login" : nomAdmin,
            "password" : passwordAdmin
    }
    ```

    >* **Réponses retournées**    

    ```
    {
            "status" : OK
    } or

    {
            "status": KO,
            "error" : Retour message
            // cas : Erreur lors de la connexion
    }
    ```
