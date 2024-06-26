---
description: Domeinbeheermethoden waarmee u domeinen kunt maken en beheren waarnaar u gegevens wilt verzenden (alleen voor cookie-doelen).
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: API-methoden voor domeinbeheer
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# API-methoden voor domeinbeheer {#domain-management-api-methods}

Domeinbeheermethoden waarmee u domeinen kunt maken en beheren waarnaar u gegevens wilt verzenden (alleen voor cookie-doelen).

<!-- c_partner_site.xml -->

## Een nieuw domein maken {#create-new-domain}

A `POST` methode die u een nieuw domein voor (koekjesbestemmingen slechts) laat creëren.

<!-- r_post_new_partner_site.xml -->

### Verzoek

`POST` `https://api.demdex.com/v1/partner-sites/`

### Voorbeeldverzoek

```
{
   "url":"example1.com"
}
```

### Antwoord

Resultaten van een succesvolle reactie `201 created` en de partnerplaats, met inbegrip van zijn unieke identiteitskaart

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Een domein verwijderen {#delete-domain}

A `DELETE` methode waarmee u een domein kunt verwijderen (alleen voor cookie-doelen).

<!-- r_delete_partner_site.xml -->

### Verzoek

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Antwoord

Resultaten van een succesvolle reactie `204 no content`. Retourneert `404 not found` als de partnerplaats niet kan worden gevonden.

## Eigenschappen voor een domein retourneren {#return-props-domain}

A `GET` methode die details over het gespecificeerde domein (voor koekjesbestemmingen slechts) terugkeert.

<!-- r_get_partner_site.xml -->

### Verzoek

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Antwoord

Resultaten van een succesvolle reactie `200 OK` en gegevens zoals weergegeven in onderstaande steekproef. Retourneert `404 Not found` als de site-id of partner niet wordt gevonden.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Eigenschappen retourneren voor alle domeinen {#return-props-all-domains}

A `GET` methode die informatie over al uw domeinen (voor koekjesbestemmingen slechts) terugkeert.

<!-- r_get_partner_sites.xml -->

### Verzoek

`GET https://api.demdex.com/v1/partner-sites/`

### Optionele queryparameters

U kunt deze optionele parameters gebruiken met [!DNL API] methoden die worden geretourneerd *alles* eigenschappen voor een object. Stel deze opties in de tekenreeks request wanneer u die query doorgeeft aan de [!DNL API]. Zie [Optionele parameters](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> Geeft resultaten op paginanummer. De nummering begint bij 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Stelt het aantal reactieresultaten in dat door de aanvraag wordt geretourneerd (10 is standaard). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Sorteert en retourneert resultaten volgens de opgegeven JSON-eigenschap. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Sorteert en retourneert resultaten in aflopende volgorde. Oplopend is standaard. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Retourneert resultaten op basis van de opgegeven tekenreeks die u als zoekparameter wilt gebruiken. Bijvoorbeeld, laten wij zeggen u resultaten voor alle modellen wilt vinden die het woord "Test"in om het even welke waardegebieden voor dat punt hebben. Uw voorbeeldverzoek kan er als volgt uitzien: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>U kunt zoeken op elke waarde die door de methode "get all" wordt geretourneerd. </p> </td>
  </tr> 
 </tbody> 
</table>

### Antwoord

Resultaten van een succesvolle reactie `200 OK` en gegevens in een array zoals in het onderstaande voorbeeld wordt getoond. Retourneert `404 Not found` als de site-id of partner niet wordt gevonden.

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
