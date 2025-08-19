---
description: Stel API-methoden in om machtigingen voor objecten en groepen te beheren.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: API-methoden voor machtigingenbeheer
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 0%

---

# API-methoden voor machtigingenbeheer {#permissions-management-api-methods}

Stel [!DNL API] -methoden in om machtigingen voor objecten en groepen te beheren.

<!-- c_rest_api_perm_man.xml -->

## Beschikbare objecttypen weergeven {#list-object-types}

Een `GET` -methode om beschikbare objecttypen weer te geven waarop op rollen gebaseerde toegangsbesturingselementen kunnen worden ingesteld.

<!-- r_rest_api_perm_list.xml -->

### Verzoek

`GET /api/v1/permissionable-object-types/`

### Antwoord

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Beschikbare machtigingen weergeven voor een objecttype {#list-permissions-object-type}

Een methode `GET` om de beschikbare machtigingen voor een objecttype weer te geven.

<!-- r_rest_api_perm_list_perms.xml -->

### Verzoek

`GET /api/v1/permissionable-object-types/SEGMENT/`

### Antwoord

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>De objecttypen TAGS en AFGELEIDE SIGNALS hebben geen reguliere rechten om te gebruiken. De controles op deze objecten types worden veranderd door allen of niets de Toestemmingen van de Kaart slechts.
