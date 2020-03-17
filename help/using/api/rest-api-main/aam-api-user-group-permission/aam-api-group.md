---
description: Rust API-methoden om groepen te beheren, zoals het maken, bijwerken, weergeven en verwijderen van groepen.
seo-description: Rust API-methoden om groepen te beheren, zoals het maken, bijwerken, weergeven en verwijderen van groepen.
seo-title: API-methoden voor groepsbeheer
solution: Audience Manager
title: API-methoden voor groepsbeheer
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# API-methoden voor groepsbeheer {#group-management-api-methods}

Stel methoden in [!DNL API] voor het beheer van groepen, zoals het maken, bijwerken, weergeven en verwijderen van groepen.

<!-- c_rest_api_user_man_group.xml -->

## Een groep maken {#create-group}

Een `POST` methode om een nieuwe gebruikersgroep te maken.

<!-- r_rest_api_group_create.xml -->

### Verzoek

`POST /api/v1/groups/`

### Voorbeeld van aanvraaginstantie

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Antwoord

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Een groep bijwerken {#update-group}

Een `PUT` methode om een gebruikersgroep bij te werken.

<!--
r_rest_api_group_update.xml
-->

### Verzoek

`PUT /api/v1/groups/`*`<groupId>`*

### Voorbeeld van aanvraaginstantie

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Antwoord

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Groepen weergeven {#list-groups}

Een `GET` methode om gebruikersgroepen weer te geven.

<!--
r_rest_api_group_list.xml
-->

### Verzoek

`GET /api/v1/groups/`

### Antwoord

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## Een groep verwijderen {#delete-groups}

Een `DELETE` methode om een gebruikersgroep te verwijderen en alle leden uit die groep te verwijderen.

<!-- r_rest_api_group_delete.xml -->

### Verzoek

`DELETE /api/v1/groups/`*`<groupId>`*

Retourneert `204 No Content` indien gelukt. In geval van conflictoplossing `409 Conflict`.

## Groepen in bulk verwijderen {#delete-groups-bulk}

Een `DELETE` methode om veelvoudige groepen in massa te schrappen en alle leden uit die groep te verwijderen.

<!-- r_rest_api_group_delete_bulk.xml -->

### Verzoek

`DELETE /api/v1/groups/bulk-delete`

Retourneert `204 No Content` indien gelukt. In geval van conflictoplossing `409 Conflict`.

## Alle machtigingen voor een groep weergeven {#list-permissions-group}

Een `GET` methode om de machtigingsobjecten in een groep weer te geven.

<!-- r_rest_api_perm_list_group.xml -->

### Verzoek

`GET /api/v1/groups/{groupId}/permissions`

### Antwoord

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

Retourneert `400 Bad Request` of de groep ontoegankelijk is.

## Machtigingen instellen voor een groep {#set-permissions-group}

Een `PUT` methode om groepsmachtigingen bij te werken. Deze methode beschrijft de oude toestemmingen met de nieuwe toestemmingen.

<!-- r_rest_api_perm_set.xml -->

### Verzoek

`PUT /api/v1/groups/{groupId}/permissions/`

### Antwoord

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

De voorbeeldreactie vertegenwoordigt de bijgewerkte lijst met machtigingsobjecten.

Retourneert `200 OK` indien gelukt. Retourneert `400` of een bepaalde machtiging ongeldig is. Kan ook retourneren `403` als het object niet toegankelijk is voor de aangemelde gebruiker.