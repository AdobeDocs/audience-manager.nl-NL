---
description: Rest API-methoden om gebruikers te beheren, zoals het maken, bijwerken, aanbieden, verwijderen en retourneren van gebruikersobjecten.
seo-description: Rest API-methoden om gebruikers te beheren, zoals het maken, bijwerken, aanbieden, verwijderen en retourneren van gebruikersobjecten.
seo-title: API-methoden voor gebruikersbeheer
solution: Audience Manager
title: API-methoden voor gebruikersbeheer
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 3%

---


# API-methoden voor gebruikersbeheer {#user-management-api-methods}

Stel methoden in om gebruikers te beheren, zoals het maken, bijwerken, aanbieden, verwijderen en retourneren van gebruikersobjecten. [!DNL API]

<!-- c_rest_api_user_man_user.xml -->

## Een gebruiker maken {#create-user}

Een `POST` methode om een nieuwe gebruiker te maken.

<!-- r_rest_api_user_create.xml -->

### Verzoek

`POST /api/v1/users/`

### Voorbeeld van aanvraaginstantie

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### Antwoord

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

Als `isAdmin` aan waar wordt geplaatst, wordt de gebruiker gecreeerd als partner admin. Dit bezit laat u ook weten of een gebruiker een partner admin is.

Retourneert `409 Conflict` of de gebruikersnaam al in gebruik is.

## Een gebruiker bijwerken {#update-user}

Een `PUT` methode om een gebruiker bij te werken.

<!-- r_rest_api_user_update.xml -->

### Verzoek

`PUT /api/v1/users/`*`<userId>`*

### Voorbeeld van aanvraaginstantie

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### Antwoord

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

Retourneert `409 Conflict` of de gebruikersnaam al in gebruik is.

## Gebruiker met aanmelding bijwerken {#update-logged-in-user}

Een `PUT` methode om de momenteel aangemelde gebruiker bij te werken.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Terwijl de meeste [!DNL API] methodes slechts callable door partnerbeheerders zijn, is deze methode aanroepbaar door niet-admin gebruikers.

### Verzoek

`PUT /self/update`

### Voorbeeld van aanvraaginstantie

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### Antwoord

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

Retourneert `409 Conflict` of de gebruikersnaam al in gebruik is.

## Aangemeld gebruikerswachtwoord bijwerken {#update-logged-in-user-pw}

Een `PUT` methode om de momenteel aangemelde gebruiker bij te werken.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Terwijl de meeste [!DNL API] methodes slechts callable door partnerbeheerders zijn, is deze methode aanroepbaar door niet-admin gebruikers.

### Verzoek

`POST /users/self/update-password`

### Voorbeeld van aanvraaginstantie

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Retourneert `200 OK` indien gelukt. Retourneert `400 Bad Request` of er iets mis is met een van beide wachtwoorden.

## Wachtwoord aangemelde gebruiker opnieuw instellen {#reset-logged-in-user-pw}

Een `PUT` methode om de momenteel aangemelde gebruiker opnieuw in te stellen. [!UICONTROL Audience Management] stuurt de gebruiker een door het systeem gegenereerd wachtwoord.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Terwijl de meeste [!DNL API] methodes slechts callable door partnerbeheerders zijn, is deze methode aanroepbaar door niet-admin gebruikers.

### Verzoek

`POST /self/reset-password`

Retourneert `200 OK` indien gelukt.

## Gebruikersobject retourneren voor een gebruikersnaam {#return-user-object-for-id}

Een `Get` methode om het gebruikersobject voor een gebruikersnaam te retourneren.

<!-- r_rest_api_user_get_user_obj.xml -->

### Verzoek

`GET /api/v1/users/`*`<userId>`*

### Antwoord

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Gebruikersobject retourneren voor aangemelde gebruiker {#return-user-object-for-logged-in-user}

Een `Get` methode om het gebruikersvoorwerp voor de momenteel het programma geopende gebruiker terug te keren.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Terwijl de meeste [!DNL API] methodes slechts callable door partnerbeheerders zijn, is deze methode aanroepbaar door niet-admin gebruikers.

### Verzoek

`GET /api/v1/users/self`

### Antwoord

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Lijstgebruikers {#list-users}

Een `GET` methode om gebruikers weer te geven.

<!-- r_rest_api_user_list.xml -->

### Verzoek

`GET /api/v1/users/`

U kunt veelvoudige groep IDs in de vraagparameters specificeren:

`GET /api/v1/users/?groupId=343&groupdId=12`

Deze query retourneert een lijst met alle gebruikers in de opgegeven groepen.

### Antwoord

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## Een gebruiker verwijderen {#delete-users}

Een `DELETE` methode om een gebruiker te verwijderen.

<!-- r_rest_api_user_delete.xml -->

### Verzoek

`DELETE /api/v1/users/`*`<user_id>`*

Retourneert `204 No Content` indien gelukt. In geval van conflictoplossing `409 Conflict`.

## Gebruikers in bulk verwijderen {#delete-users-bulk}

Een `POST` methode om meerdere gebruikers in bulk te verwijderen.

<!-- r_rest_api_user_delete_bulk.xml -->

### Verzoek

`POST /api/v1/users/bulk-delete`

### Voorbeeld van aanvraaginstantie

```
{[<user_id_1>, <user_id_2>, ...]}
```
