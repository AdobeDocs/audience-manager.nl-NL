---
description: DELETE- en POST-methoden waarmee u doelen en segmenttoewijzingen kunt verwijderen.
seo-description: DELETE- en POST-methoden waarmee u doelen en segmenttoewijzingen kunt verwijderen.
seo-title: Bestemmingen verwijderen
solution: Audience Manager
title: Bestemmingen verwijderen
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

---


# Bestemmingen verwijderen {#delete-destinations}

`DELETE` en `POST` methoden waarmee u doelen en segmenttoewijzingen kunt verwijderen.

<!-- r_delete_destinations_all.xml -->

## Een doel verwijderen

Een `DELETE` methode waarmee een doel wordt verwijderd.

>[!NOTE]
>
>U moet alle segmenttoewijzingen verwijderen voordat u een doel kunt verwijderen.

* Verzoek: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Reactie: Retourneert code `204 No Content` als dit gelukt is.

## Bestemmingen voor bulkverwijderen

Verwijder veelvoudige bestemmingen met deze `POST` methode. Geef doel-id&#39;s ( `destinationId`) door met een array in de aanvraaginstantie.

* Verzoek: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Reactie: Retourneert code `204 No Content` als dit gelukt is.

## Doeltoewijzingen verwijderen op basis van segmenttoewijzing-id

Een `POST` methode die bestemmingstoewijzingen volgens gespecificeerde segmentidentiteitskaart verwijdert

* Verzoek: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Reactie: Retourneert code `204 No Content` als dit gelukt is.