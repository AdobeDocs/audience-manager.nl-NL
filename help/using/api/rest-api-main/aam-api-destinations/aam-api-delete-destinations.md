---
description: DELETE- en POST-methoden waarmee u doelen en segmenttoewijzingen kunt verwijderen.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Doelen verwijderen
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---

# Doelen verwijderen {#delete-destinations}

`DELETE` en `POST` methoden waarmee u doelen en segmenttoewijzingen kunt verwijderen.

<!-- r_delete_destinations_all.xml -->

## Een doel verwijderen

Een methode `DELETE` die een doel verwijdert.

>[!NOTE]
>
>U moet alle segmenttoewijzingen verwijderen voordat u een doel kunt verwijderen.

* Verzoek: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Reactie: retourneert code `204 No Content` als dit gelukt is.

## Bestemmingen voor bulkverwijderen

Verwijder meerdere doelen met deze `POST` -methode. Geef doel-id&#39;s ( `destinationId`) door met een array in de hoofdtekst van de aanvraag.

* Verzoek: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Reactie: retourneert code `204 No Content` als dit gelukt is.

## Doeltoewijzingen verwijderen op basis van segmenttoewijzing-id

A `POST` methode die bestemmingstoewijzingen volgens gespecificeerde segment ID verwijdert.

* Verzoek: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Reactie: retourneert code `204 No Content` als dit gelukt is.
