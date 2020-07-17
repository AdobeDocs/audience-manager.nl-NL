---
description: Optionele methoden waarmee u eigenschappen kunt toewijzen aan een door de gebruiker gedefinieerd type of categorie, meestal op basis van de functie of voor uw eigen interne rapportageprocessen.
seo-description: Optionele methoden waarmee u eigenschappen kunt toewijzen aan een door de gebruiker gedefinieerd type of categorie, meestal op basis van de functie of voor uw eigen interne rapportageprocessen.
seo-title: Methoden voor eigenschaptypen
solution: Audience Manager
title: Methoden voor eigenschaptypen
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 5%

---


# Methoden voor eigenschaptypen {#trait-type-methods}

Optionele methoden waarmee u eigenschappen kunt toewijzen aan een door de gebruiker gedefinieerd type of categorie, meestal op basis van de functie of voor uw eigen interne rapportageprocessen.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Bij methoden van het type Trait worden geen kenmerken toegewezen aan categorieën die door de [gemeenschappelijke taxonomie](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)worden gebruikt. Beschouw deze als labels die los staan van de algemene taxonomie.

Voor visuele verwijzing, is [!UICONTROL Trait Types] een dropdown controle die in [!DNL UI] onder wordt gevestigd **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Een nieuw type overtrek maken {#create-trait-type}

Een `POST` methode waarmee u een nieuw type eigenschap kunt maken.

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

Een `GET` methode die details over het gespecificeerde type van eigenschap terugkeert.

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

Een `GET` methode die details over al uw eigenschappen in een serie terugkeert.

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
