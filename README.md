####LES ROUTES À UTILISER :

FAIT - * #### Requête d'ajout user :  /user/add (POST) (Ajoute un nouvel utilisateur à l’application)
FAIT - * #### Requête d'authentification :  /login (POST) (Demande une authentification en tant que session d’administration)
FAIT - * #### Requête de supression user :  /user/delete/{id} (DELETE) (Supprime l’utilisateur avec l’id {id}. Supression en cascaade)
FAIT - * #### Requête de déconnexion :   /logout (GET) (Demande la révocation d’une clé d’API)
* #### Requête pour consulter les post-its :  /stickys (GET) Renvoie la liste des post-its existants
FAIT - * #### Requête d'ajout de post-it :  /sticky/add (ajout d'un nouveau pense-bête)
* #### Requête de supression de post-it :  /sticky/delete/{id} (supression d'un pense-bête)



### LES ROUTES À UTILISER :

---
#### I. INSCRIPTION - CONNEXION - DECONNEXION

* #### Requête d'inscription :  /user/add (POST) (inscription, soit l'ajout d'un nouvel utilisateur)
    >*  **Paramètres envoyés**
    ```
    {
            "login" : "nomUser",
            "mail" : "mailUser",
            "password" : passwordUser
            // password => 8 caractères
    }
    ```

    >* **Réponses retournées**    
    ```
    {
            "status" : OK,
            "id" : idIdentifiantSession
    } or
    {
            "status": KO,
            "error" : "Retour message"
            // cas n°1 : nomUser déjà dans la BD
            // cas n°2 : mailUser déjà dans la BD
            // cas n°3 : passwordUser < 8 caractères
            // cas n°4 : Error lors de l'ajout dans BD
    }
    ```


* #### Requête d'authentification :  /login (POST) (Demande une authentification en tant que session d’administration)
    >*  **Paramètres envoyés**
    ```
    {
            "mail" : "mailUser",
            "password" : passwordUser
    }
    ```

    >* **Réponses retournées**    
    ```
    {
            "status" : OK
            "id": idIdentifiantSession
    } or

    {
            "status" : KO,
            "error" : "Retour message"
            // cas : Erreur lors de l'authentification de session
    }
    ```


* #### Requête de déconnexion :   /logout (GET) (Demande la révocation d’une clé d’API)
    >*  **Paramètres envoyés**
    ```
    {
            "id" : idD'identifiantSession
    }
    ```

    >* **Réponses retournées**    
    ```
    {
            "status" : OK
    } or

    {
            "status" : KO,
            "error" : "Retour message"
            // cas : Erreur lors de la déconnexion de session
    }
    ```



---
#### II. SUPRESSION

* #### Requête de supression de compte :  /user/delete/{id} (DELETE) (Supprime l’utilisateur avec l’id {id}. Supression en cascade)
    >*  **Paramètres envoyés**
    ```
    {
             "id" : idD'identifiantSession
    }
    ```

    >* **Réponses retournées**    
    ```
    {
            "status" : OK,
    } or
    {
            "status" : KO,
            "error" : "Retour message"
            // cas : Erreur lors de la supression du compte
    }
    ```



---
#### III.  POST-ITS

* #### Requête d'ajout de post-it :  /sticky/add (ajout d'un nouveau pense-bête)
    >*  **Paramètres envoyés**
    ```
    {
        "title" : "nomPost", (obligatoire)
        "contenu" : "contenuPost", (obligatoire)
        "color" : nomColorPost (obligatoire)
    }
    ```

    >* **Réponses retournées**    
    ```
    {
            "status" : OK,
            "id" : idPost (obligatoire)
            "title" : "titrePost", (obligatoire)
            "contenu" : "contenuPost", (obligatoire)
            "color" : nomColorPost
            // si il y a ajout d'une couleur d'importance
    } or
    {
            "status": KO,
            "error" : "Retour message"
            // cas n°1 : il manque un champ obligatoire
            // cas n°2 : Error d'ajout de post-it
    }
    ```


* #### Requête pour afficher les post-its :  /stickys (GET) Renvoie la liste des post-its existants
    >*  **Paramètres envoyés**
    ```
    {
        none
    }
    ```

    >* **Réponses retournées**    
    ```
    "sticky": [
        {
             "id": idPost,
             "titre": "titrePost",
             "date": "05/08/2017",
             "contenu": "contenuPost",
             "color": nomColorPost
        },
        {
            "id": idPost,
            "titre": "titrePost",
            "date": "05/08/2017",
            "contenu": "contenuPost",
            "color": "orangeRed"
        },
        {
            "id": idPost,
            "titre": "titrePost",
            "date": "05/08/2017",
            "contenu": "contenuPost",
            "color": "oliveDrab"
        },
        {
            "id": idPost,
            "titre": "titrePost",
            "date": "05/08/2017",
            "contenu": "contenuPost",
            "color": "gold"
        },
        {
            "etc"
        }     
    ]
    ```






