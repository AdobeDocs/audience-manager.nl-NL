---
description: Eenvoudige pixels (die kunnen worden gebruikt om gebruikers voor kenmerken in aanmerking te laten komen) voeren realtime gegevensoverdracht uit. De interface van de Audience Manager laat cliënten om het even welk aantal pixel op een zelfbediening basis tot stand brengen. Pixeltekenreeksen bestaan uit eenvoudige id's of sleutelwaardeparen.
seo-description: Eenvoudige pixels (die kunnen worden gebruikt om gebruikers voor kenmerken in aanmerking te laten komen) voeren realtime gegevensoverdracht uit. De interface van de Audience Manager laat cliënten om het even welk aantal pixel op een zelfbediening basis tot stand brengen. Pixeltekenreeksen bestaan uit eenvoudige id's of sleutelwaardeparen.
seo-title: Op pixels gebaseerde gegevensoverdracht
solution: Audience Manager
title: Op pixels gebaseerde gegevensoverdracht
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---


# Op pixels gebaseerde gegevensoverdracht {#pixel-based-data-transfers}

Eenvoudige pixels (die kunnen worden gebruikt om gebruikers voor kenmerken in aanmerking te laten komen) voeren realtime gegevensoverdracht uit. De interface van de Audience Manager laat cliënten om het even welk aantal pixel op een zelfbediening basis tot stand brengen. Pixeltekenreeksen bestaan uit eenvoudige id&#39;s of sleutelwaardeparen.

<!-- c_rt_inbound_pixel_transfers.xml -->

Om binnenkomende gegevensoverdrachten toe te laten, zouden de verkoper en de cliënt:

1. Bepaal welke kenmerken u door de leverancier of partner wilt laten activeren.
1. Hiermee krijgt u de pixel voor de eigenschap. Houd de muisaanwijzer boven de **[!UICONTROL Actions]** kolom in de lijst met kenmerken en klik op het **[!UICONTROL Get trait URL]** symbool voor de gewenste eigenschap.
1. De leverancier of partner de [!DNL URL] informatie geven.

## Voorbeelden

Deze basisvraag van de gebeurtenisvraag verzendt eigenschap ID 1234 naar [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

U kunt eigenschap IDs in een gebeurtenisvraag in series vervaardigen helpen `HTTP` verkeer van de pagina verminderen. Voeg extra eigenschap-id&#39;s toe aan de URL-tekenreeks, zoals in het volgende voorbeeld wordt getoond:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
