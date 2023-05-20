---
description: Optionele methoden waarmee u eigenschappen kunt toewijzen aan een door de gebruiker gedefinieerd type of categorie, meestal op basis van de functie of voor uw eigen interne rapportageprocessen.
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: Methoden voor eigenschaptypen
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 3%

---

# Methoden voor eigenschaptypen {#trait-type-methods}

Optionele methoden waarmee u eigenschappen kunt toewijzen aan een door de gebruiker gedefinieerd type of categorie, meestal op basis van de functie of voor uw eigen interne rapportageprocessen.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Trainingstypemethoden wijzen geen kenmerken toe aan categorieën die door de [gemeenschappelijke taxonomie](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Beschouw deze als labels die los staan van de algemene taxonomie.

Voor visuele referentie: [!UICONTROL Trait Types] is een dropdown-besturingselement in het dialoogvenster [!DNL UI] krachtens **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Een nieuw type overtrek maken {#create-trait-type}

A `POST` een methode waarmee u een nieuw type eigenschap kunt maken.

<!-- r_rest_api_create_trait_type.xml -->

### Verzoek

`POST https://api.demdex.com/v1/customer-trait-types`

### Voorbeeldverzoek

```
{
"name":"Custom trait type"
}
```

### Antwoord

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## Eigenschappen retourneren voor een type overtrek {#return-props}

A `GET` methode die details over het gespecificeerde type van eigenschap terugkeert.

<!-- r_rest_api_get_trait_type.xml -->

### Verzoek

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### Antwoord

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## Eigenschappen retourneren voor alle travetypen {#return-props-all}

A `GET` methode die details over al uw types van eigenschap in een serie terugkeert.

<!-- r_rest_api_get_trait_types.xml -->

### Verzoek

`GET https://api.demdex.com/v1/customer-trait-types/`

### Antwoord

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
