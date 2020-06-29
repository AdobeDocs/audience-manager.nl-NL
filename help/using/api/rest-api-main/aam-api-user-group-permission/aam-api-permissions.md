---
description: Stel API-methoden in om machtigingen voor objecten en groepen te beheren.
seo-description: Stel API-methoden in om machtigingen voor objecten en groepen te beheren.
seo-title: API-methoden voor machtigingenbeheer
solution: Audience Manager
title: API-methoden voor machtigingenbeheer
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---


# API-methoden voor machtigingenbeheer {#permissions-management-api-methods}

Stel methoden in [!DNL API] om machtigingen voor objecten en groepen te beheren.

<!-- c_rest_api_perm_man.xml -->

## Beschikbare objecttypen weergeven {#list-object-types}

Een `GET` methode om van beschikbare objecten types een lijst te maken waarop op rol-gebaseerde toegangscontroles kunnen worden geplaatst.

<!-- r_rest_api_perm_list.xml -->

### Verzoek

`GET /api/v1/permissionable-object-types/`

### Antwoord

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Beschikbare machtigingen weergeven voor een objecttype {#list-permissions-object-type}

Een `GET` methode voor het weergeven van beschikbare machtigingen voor een objecttype.

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