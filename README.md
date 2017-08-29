### LES ROUTES À UTILISER :

#### I. CONNEXION - INSCRIPTION

* #### Requête d'inscription :  /user/add (POST) (inscription, soit l'ajout d'un nouvel utilisateur)

    >*  **Paramètres envoyés**
    ```
    {
            "login" : nomUser,
            "mail" : mailUser,
            "password" : passwordUser
            // password => 8 caractères
    }
    ```

    >* **Réponses retournées**    
    ```
    {
            "status" : OK,
            "id" : n° d'identifiantSession
    } or
    {
            "status": KO,
            "error" : Retour message
            // cas n°1 : nomUser déjà dans la BD
            // cas n°2 : mailUser déjà dans la BD
            // cas n°3 : passwordUser < 8 caractères
    }
    ```




* #### Requête d'authentification :  /login (POST) (Demande une authentification en tant que session d’administration)

    >*  **Paramètres envoyés**
    ```
    {
            "mail" : mailUser,
            "password" : passwordUser
    }
    ```

    >* **Réponses retournées**    
    ```
    {
            "status" : OK
            "id": n°identifiantSession
    } or

    {
            "status": KO,
            "error" : Retour message
            // cas : Erreur lors de l'authentification
    }
    ```





