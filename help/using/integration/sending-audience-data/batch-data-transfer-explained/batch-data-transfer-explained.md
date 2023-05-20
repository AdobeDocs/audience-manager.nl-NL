---
description: Een algemeen overzicht van hoe de Audience Manager een asynchrone uitwisseling van partijgegevens met een derdeverkoper uitvoert.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Beschrijving van batchdataoverdracht
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 5%

---

# Beschrijving van batchdataoverdracht {#batch-data-transfer-process-described}

Een algemeen overzicht van hoe [!DNL Audience Manager] voert een asynchrone uitwisseling van partijgegevens met een derdeverkoper uit.

## Batchgegevensintegratie

<!-- c_async.xml -->

Bij het integratieproces van batchgegevens worden bezoekersgegevens op onze servers opgeslagen en gesynchroniseerd met gegevens die regelmatig door een provider worden verzonden. Het asynchrone proces voor gegevensoverdracht is handig wanneer:

* Directe gegevensoverdracht is niet vereist.
* Gegevens verzamelen om een grote groep gesegmenteerde gebruikers samen te stellen.
* U wilt gegevensdiscrepanties verminderen en `HTTP` roept van browser.

![](assets/s2s_70.png)

## Stappen voor gegevensintegratie

1. Een gebruiker bezoekt een klantsite.
1. [!DNL Audience Manager] en de externe gegevensaanbieder wijst de bezoeker een unieke id toe (meestal met een cookie).
1. [!DNL Audience Manager] roept de gegevensleverancier van de derde om bezoeker IDs aan te passen.
1. Een gepland verzoek, gewoonlijk op een dagelijks interval, ruilt de gegevens van het bezoekerssegment tussen [!DNL Audience Manager] en uw externe gegevensaanbieder.
1. Wanneer een binnenkomend [!UICONTROL Server-to-Server] het dossier wordt verwerkt, wordt een ontvangstbewijs verzonden via e-mail naar partneroplossingen en, indien gevormd, naar de partner. Zie voor meer informatie [Het Bericht van de steekproef aan Partners na Binnenkomende Verwerking](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
