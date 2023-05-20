---
description: Eenvoudige pixels (die kunnen worden gebruikt om gebruikers voor kenmerken in aanmerking te laten komen) voeren realtime gegevensoverdracht uit. De interface van de Audience Manager laat cliënten om het even welk aantal pixel op een zelfbediening basis tot stand brengen. Pixeltekenreeksen bestaan uit eenvoudige id's of sleutelwaardeparen.
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: Op pixels gebaseerde dataoverdracht
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 3%

---

# Op pixels gebaseerde dataoverdracht {#pixel-based-data-transfers}

Eenvoudige pixels (die kunnen worden gebruikt om gebruikers voor kenmerken in aanmerking te laten komen) voeren realtime gegevensoverdracht uit. De interface van de Audience Manager laat cliënten om het even welk aantal pixel op een zelfbediening basis tot stand brengen. Pixeltekenreeksen bestaan uit eenvoudige id&#39;s of sleutelwaardeparen.

<!-- c_rt_inbound_pixel_transfers.xml -->

Om binnenkomende gegevensoverdrachten toe te laten, zouden de verkoper en de cliënt:

1. Bepaal welke kenmerken u door de leverancier of partner wilt laten activeren.
1. Hiermee krijgt u de pixel voor de eigenschap. Houd de muisaanwijzer boven het scherm Lijst met kenmerken **[!UICONTROL Actions]** en klik op de knop **[!UICONTROL Get trait URL]** voor de gewenste eigenschap.
1. Geef de [!DNL URL] aan de verkoper of partner.

## Voorbeelden

Deze basisvraag van de gebeurtenis verzendt eigenschap ID 1234 naar [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

U kunt standaard-id&#39;s in een gebeurtenisaanroep serialiseren om te helpen het aantal `HTTP` verkeer van de pagina. Voeg extra eigenschap-id&#39;s toe aan de URL-tekenreeks, zoals in het volgende voorbeeld wordt getoond:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
