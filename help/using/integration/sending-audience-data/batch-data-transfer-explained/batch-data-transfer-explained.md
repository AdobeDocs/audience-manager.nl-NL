---
description: Een algemeen overzicht van hoe de Audience Manager een asynchrone uitwisseling van partijgegevens met een derdeverkoper uitvoert.
seo-description: Een algemeen overzicht van hoe de Audience Manager een asynchrone uitwisseling van partijgegevens met een derdeverkoper uitvoert.
seo-title: Beschrijving van batchdataoverdracht
solution: Audience Manager
title: Beschrijving van batchdataoverdracht
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 7%

---


# Beschrijving van batchdataoverdracht {#batch-data-transfer-process-described}

Een algemeen overzicht van hoe een asynchrone uitwisseling van partijgegevens met een derdeverkoper [!DNL Audience Manager] uitvoert.

## Batchgegevensintegratie

<!-- c_async.xml -->

Bij het integratieproces van batchgegevens worden bezoekersgegevens op onze servers opgeslagen en gesynchroniseerd met gegevens die regelmatig door een provider worden verzonden. Het asynchrone proces voor gegevensoverdracht is handig wanneer:

* Directe gegevensoverdracht is niet vereist.
* Gegevens verzamelen om een grote groep gesegmenteerde gebruikers samen te stellen.
* U wilt gegevensdiscrepanties en `HTTP` vraag van browser verminderen.

![](assets/s2s_70.png)

## Stappen voor gegevensintegratie

1. Een gebruiker bezoekt een klantsite.
1. [!DNL Audience Manager] en de externe gegevensaanbieder wijst de bezoeker een unieke id toe (meestal met een cookie).
1. [!DNL Audience Manager] roept de gegevensleverancier van de derde om bezoeker IDs aan te passen.
1. Een gepland verzoek, gewoonlijk op een dagelijks interval, ruilt de gegevens van het bezoekerssegment tussen [!DNL Audience Manager] en uw derdegegevensleverancier.
1. Wanneer een binnenkomend [!UICONTROL Server-to-Server] dossier wordt verwerkt, wordt een ontvangstbewijs verzonden via e-mail naar partneroplossingen en, indien gevormd, naar de partner. Voor meer informatie, zie het Bericht van de [Steekproef aan Partners na Binnenkomende Verwerking](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
