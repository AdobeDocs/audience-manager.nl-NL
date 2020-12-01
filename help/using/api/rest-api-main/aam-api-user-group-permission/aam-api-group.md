---
description: Rust API-methoden om groepen te beheren, zoals het maken, bijwerken, weergeven en verwijderen van groepen.
seo-description: Rust API-methoden om groepen te beheren, zoals het maken, bijwerken, weergeven en verwijderen van groepen.
seo-title: API-methoden voor groepsbeheer
solution: Audience Manager
title: API-methoden voor groepsbeheer
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 5%

---


# API-methoden voor groepsbeheer {#group-management-api-methods}

Stel [!DNL API] methoden in om groepen te beheren, zoals het maken, bijwerken, weergeven of verwijderen van groepen.

<!-- c_rest_api_user_man_group.xml -->

## Een groep maken {#create-group}

Een `POST` methode om een nieuwe gebruikersgroep tot stand te brengen.

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

## Een groep {#update-group} bijwerken

Een methode `PUT` om een gebruikersgroep bij te werken.

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

Een methode `GET` om gebruikersgroepen weer te geven.

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

## Een groep {#delete-groups} verwijderen

Een methode `DELETE` om een gebruikersgroep te schrappen en alle leden uit die groep te verwijderen.

<!-- r_rest_api_group_delete.xml -->

### Verzoek

`DELETE /api/v1/groups/`*`<groupId>`*

Retourneert `204 No Content` indien gelukt. In geval van conflict retourneert `409 Conflict`.

## Groepen in bulk verwijderen {#delete-groups-bulk}

Een `DELETE` methode om veelvoudige groepen in massa te schrappen en alle leden uit die groep te verwijderen.

<!-- r_rest_api_group_delete_bulk.xml -->

### Verzoek

`DELETE /api/v1/groups/bulk-delete`

Retourneert `204 No Content` indien gelukt. In geval van conflict retourneert `409 Conflict`.

## Alle machtigingen voor een groep {#list-permissions-group} weergeven

A `GET` methode om van de toestemmingsvoorwerpen op een groep een lijst te maken.

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

Retourneert `400 Bad Request` als de groep niet toegankelijk is.

## Machtigingen instellen voor een groep {#set-permissions-group}

Een methode `PUT` om groepsmachtigingen bij te werken. Deze methode beschrijft de oude toestemmingen met de nieuwe toestemmingen.

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

Retourneert `200 OK` indien gelukt. Retourneert `400` als een gegeven machtiging ongeldig is. Kan ook `403` retourneren als het object niet toegankelijk is voor de aangemelde gebruiker.