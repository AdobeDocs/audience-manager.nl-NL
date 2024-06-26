---
description: Methoden waarmee u de algemene taxonomie van de Audience Manager kunt weergeven. Dit facultatieve classificatieschema organiseert de eigenschappen in industriestandaard categorieën.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Taxonomische API-methoden
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%

---

# Taxonomische API-methoden {#taxonomic-api-methods}

Methoden waarmee u de algemene taxonomie van de Audience Manager kunt weergeven. Dit facultatieve classificatieschema organiseert de eigenschappen in industriestandaard categorieën.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>U kunt geen nieuwe taxonomische categorieën tot stand brengen of eigenschappen met deze methodes classificeren. Als u een eigenschap wilt classificeren, geeft u de juiste waarde op `categoryId` met een standaard methode maken of bijwerken.

## Een specifieke taxonomie retourneren {#return-specific-taxonomy}

A `GET` methode die details over de gespecificeerde taxonomische categorie terugkeert.

<!-- r_rest_api_taxonomy.xml -->

### Verzoek

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Antwoord

Resultaten van een succesvolle reactie `200 OK` en de categorie voor de opgegeven id. Een mislukte aanvraag wordt geretourneerd `404 No Content` als de id niet bestaat.

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## Alle taxonomische categorieën retourneren {#return-all-taxonomy-categories}

A `GET` methode die een lijst van de top-level categorieën in een serie terugkeert.

<!-- r_rest_api_taxonomies.xml -->

### Verzoek

`GET https://api.demdex.com/v1/taxonomies/0/`

### Antwoord

Afgekort voor bondigheid.

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## Taxonomische subcategorieën retourneren {#return-taxonomy-sub-categories}

A `GET` methode die subcategorieën voor de opgegeven bovenliggende categorie in een array retourneert.

<!-- r_rest_api_taxonomy_sub.xml -->

### Verzoek

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Antwoord

Resultaten van een succesvolle reactie `200 OK` en de categorie voor de opgegeven id. Een mislukte aanvraag wordt geretourneerd `404 No Content` als de id niet bestaat. Afgekort voor bondigheid.

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
