---
description: Domeinbeheermethoden waarmee u domeinen kunt maken en beheren waarnaar u gegevens wilt verzenden (alleen voor cookie-doelen).
seo-description: Domeinbeheermethoden waarmee u domeinen kunt maken en beheren waarnaar u gegevens wilt verzenden (alleen voor cookie-doelen).
seo-title: API-methoden voor domeinbeheer
solution: Audience Manager
title: API-methoden voor domeinbeheer
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API-methoden voor domeinbeheer {#domain-management-api-methods}

Domeinbeheermethoden waarmee u domeinen kunt maken en beheren waarnaar u gegevens wilt verzenden (alleen voor cookie-doelen).

<!-- c_partner_site.xml -->

## Een nieuw domein maken {#create-new-domain}

Een `POST` methode waarmee u een nieuw domein kunt maken voor (alleen cookie-doelen).

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

Een succesvolle reactie keert `201 created` en de partnerplaats, met inbegrip van zijn unieke identiteitskaart terug.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Een domein verwijderen {#delete-domain}

Een `DELETE` methode waarmee u een domein kunt verwijderen (alleen voor cookie-doelen).

<!-- r_delete_partner_site.xml -->

### Verzoek

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Antwoord

Een geslaagde reactie wordt geretourneerd `204 no content`. Keert terug `404 not found` als de partnerplaats niet kan worden gevonden.

## Eigenschappen voor een domein retourneren {#return-props-domain}

Een `GET` methode die details over het gespecificeerde domein (voor koekjesbestemmingen slechts) terugkeert.

<!-- r_get_partner_site.xml -->

### Verzoek

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Antwoord

Een succesvolle reactie keert `200 OK` en gegevens terug zoals aangetoond in de steekproef hieronder. Retourneert `404 Not found` of de site-id of partner niet is gevonden.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Eigenschappen retourneren voor alle domeinen {#return-props-all-domains}

Een `GET` methode die informatie over al uw domeinen (voor koekjesbestemmingen slechts) terugkeert.

<!-- r_get_partner_sites.xml -->

### Verzoek

`GET https://api.demdex.com/v1/partner-sites/`

### Optionele queryparameters

U kunt deze optionele parameters gebruiken met [!DNL API] methoden die *alle* eigenschappen van een object retourneren. Plaats deze opties in het verzoekkoord wanneer het overgaan van die vraag in aan het [!DNL API]. Zie [Optionele parameters](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2">Retourneert resultaten op basis van de opgegeven tekenreeks die u als zoekparameter wilt gebruiken. Stel dat u resultaten wilt zoeken voor alle modellen die het woord "Testen" hebben in een van de waardevelden voor dat item. Uw voorbeeldverzoek kan er als volgt uitzien: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>U kunt zoeken op elke waarde die door de methode "get all" wordt geretourneerd. </p> </td>
  </tr> 
 </tbody> 
</table>

### Antwoord

Een geslaagde reactie retourneert `200 OK` en gegevens in een array, zoals in het onderstaande voorbeeld wordt getoond. Retourneert `404 Not found` of de site-id of partner niet is gevonden.

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
