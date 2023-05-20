---
description: Rust API-methoden om groepen te beheren, zoals het maken, bijwerken, weergeven en verwijderen van groepen.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: API-methoden voor groepsbeheer
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 3%

---

# API-methoden voor groepsbeheer {#group-management-api-methods}

Rust [!DNL API] methoden om groepen te beheren, zoals het maken, bijwerken, weergeven of verwijderen van groepen.

<!-- c_rest_api_user_man_group.xml -->

## Een groep maken {#create-group}

A `POST` methode om een nieuwe gebruikersgroep te maken.

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

A `PUT` methode om een gebruikersgroep bij te werken.

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

A `GET` om gebruikersgroepen weer te geven.

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

A `DELETE` methode om een gebruikersgroep te verwijderen en alle leden uit die groep te verwijderen.

<!-- r_rest_api_group_delete.xml -->

### Verzoek

`DELETE /api/v1/groups/`*`<groupId>`*

Retourneert `204 No Content` indien succesvol. In geval van conflictopmerkingen `409 Conflict`.

## Groepen in bulk verwijderen {#delete-groups-bulk}

A `DELETE` methode om veelvoudige groepen in massa te schrappen en alle leden uit die groep te verwijderen.

<!-- r_rest_api_group_delete_bulk.xml -->

### Verzoek

`DELETE /api/v1/groups/bulk-delete`

Retourneert `204 No Content` indien succesvol. In geval van conflictopmerkingen `409 Conflict`.

## Alle machtigingen voor een groep weergeven {#list-permissions-group}

A `GET` methode om de machtigingsobjecten op een groep weer te geven.

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

Retourneert `400 Bad Request` als de groep ontoegankelijk is.

## Machtigingen instellen voor een groep {#set-permissions-group}

A `PUT` methode om groepsmachtigingen bij te werken. Deze methode beschrijft de oude toestemmingen met de nieuwe toestemmingen.

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

Retourneert `200 OK` indien succesvol. Retourneert `400` als een bepaalde machtiging ongeldig is. Kan ook terugkeren `403` als het object niet toegankelijk is voor de aangemelde gebruiker.
