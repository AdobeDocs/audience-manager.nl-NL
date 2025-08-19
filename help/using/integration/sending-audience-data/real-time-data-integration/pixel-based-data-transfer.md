---
description: Eenvoudige pixels (die kunnen worden gebruikt om gebruikers voor kenmerken in aanmerking te laten komen) voeren realtime gegevensoverdracht uit. De interface van Audience Manager laat cliënten om het even welk aantal pixel op een zelfbediening basis tot stand brengen. Pixeltekenreeksen bestaan uit eenvoudige id's of sleutelwaardeparen.
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: Op pixels gebaseerde gegevensoverdracht
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Op pixels gebaseerde gegevensoverdracht {#pixel-based-data-transfers}

Eenvoudige pixels (die kunnen worden gebruikt om gebruikers voor kenmerken in aanmerking te laten komen) voeren realtime gegevensoverdracht uit. De interface van Audience Manager laat cliënten om het even welk aantal pixel op een zelfbediening basis tot stand brengen. Pixeltekenreeksen bestaan uit eenvoudige id&#39;s of sleutelwaardeparen.

<!-- c_rt_inbound_pixel_transfers.xml -->

Om binnenkomende gegevensoverdrachten toe te laten, zouden de verkoper en de cliënt:

1. Bepaal welke kenmerken u door de leverancier of partner wilt laten activeren.
1. De pixel voor de eigenschap ophalen. Houd de cursor boven de kolom **[!UICONTROL Actions]** in het scherm met de lijst met kenmerken en klik op het symbool **[!UICONTROL Get trait URL]** voor de gewenste richting.
1. Geef [!DNL URL] door aan de leverancier of partner.

## Voorbeelden

Met deze eenvoudige gebeurtenisaanroep wordt de standaard-id 1234 naar [!DNL Audience Manager] verzonden.

```
https://something.demdex.net/event?d_sid=1234
```

In een gebeurtenisaanroep kunt u teken-id&#39;s serialiseren om het `HTTP` -verkeer van de pagina te verminderen. Voeg extra eigenschap IDs aan het koord URL zoals aangetoond in het volgende voorbeeld toe:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
