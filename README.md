#### LES ROUTES À UTILISER :



* #### Requête d'ajout user :  /user/add (POST) (Ajouter un nouvel user)

>*  **Paramètres envoyés**
```
{
        "login" : nom user,
        "password" : password user
}
```

>* **Réponses retournées**    
```
{
        "status" : OK,
        "id" : n° d'identifiant
} or

{
        "status": KO,
        "error" : Retour message
        // cas n°1 : User déjà dans BD
        // cas n°2 : Mot de passe inférieur à 8 caractères
}
```



* #### Requête de supression user :  /user/delete/{id} (DELETE) (Supprime l’utilisateur avec l’id {id}. Les dépenses dont cet utilisateur est le payeur ou le seul concerné seront automatiquement supprimées)

>*  **Paramètres envoyés**
```
{
        "id" : n° user
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
        // cas : Erreur lors de la supression
}
```



* #### Requête pour consulter tous les users :  /users (GET) (Renvoie la liste de tous les utilisateurs)

>*  **Paramètres envoyés**
```
{
        "id" : n° session de connexion admin
}
```

>* **Réponses retournées**    

```
{
        "status" : OK
        users : [ 
                    {
                        "id" : n° user1,
                        "nom": nomUser,
                        "prenom": prénomUser
                    },

                    {
                        "id" : n° user2,
                        "nom": nomUser,
                        "prenom": prénomUser
                    },

                    {
                        "id" : n° user3,
                        "nom": nomUser,
                        "prenom": prénomUser
                    },

                    {
                        "id" : n° user4,
                        "nom": nomUser,
                        "prenom": prénomUser
                    }  

                    {
                        etc.
                    }  
                ]
} or

{
        "status": KO,
        "error" : Retour message
        // cas : Erreur lors de l'envois
}
```

* #### Requête d'authentification :  /login (POST) (Demande une authentification en tant que session d’administration)
* #### Requête de déconnexion :   /logout (GET) (Demande la révocation d’une clé d’API)
* #### Requête pour consulter les post-its :  /stickys (GET) Renvoie la liste des post-its existants
* #### Requête d'ajout de post-it :  /sticky/add (ajout d'un nouveau pense-bête)
* #### Requête d'ajout de post-it :  /sticky/delete/{id} (supression d'un pense-bête)
