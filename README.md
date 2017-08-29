####LES ROUTES À UTILISER :

FAIT - * #### Requête d'ajout user :  /user/add (POST) (Ajoute un nouvel utilisateur à l’application)
FAIT - * #### Requête d'authentification :  /login (POST) (Demande une authentification en tant que session d’administration)
* #### Requête de supression user :  /user/delete/{id} (DELETE) (Supprime l’utilisateur avec l’id {id}. Supression en cascaade)
FAIT - * #### Requête de déconnexion :   /logout (GET) (Demande la révocation d’une clé d’API)
* #### Requête pour consulter les post-its :  /stickys (GET) Renvoie la liste des post-its existants
* #### Requête d'ajout de post-it :  /sticky/add (ajout d'un nouveau pense-bête)
* #### Requête d'ajout de post-it :  /sticky/delete/{id} (supression d'un pense-bête)



### LES ROUTES À UTILISER :

#### I. INSCRIPTION - CONNEXION - DECONNEXION

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
            // cas : Erreur lors de l'authentification de session
    }
    ```




* #### Requête de déconnexion :   /logout (GET) (Demande la révocation d’une clé d’API)

    >*  **Paramètres envoyés**
    ```
    {
            none
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
            // cas : Erreur lors de la déconnexion de session
    }
    ```




#### II. SUPRESSION

* #### Requête de supression de compte :  /user/delete/{id} (DELETE) (Supprime l’utilisateur avec l’id {id}. Supression en cascaade)

    >*  **Paramètres envoyés**
    ```
    {
             "id" : n° d'identifiantSession
    }
    ```

    >* **Réponses retournées**    
    ```
    {
            "status" : OK,
    } or
    {
            "status": KO,
            "error" : Retour message
            // cas : Erreur lors de la supression du compte
    }
    ```

