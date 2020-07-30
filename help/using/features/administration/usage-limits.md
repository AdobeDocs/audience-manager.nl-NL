---
description: Audience Manager stelt een maximumlimiet in voor het aantal kenmerken, segmenten, doelen en algoritmische modellen dat u voor een account kunt maken. De beperkingen zijn op deze punten van toepassing ongeacht of gecreeerd in het gebruikersinterface of programmatically door API methodes. Beperkingen van het gebruik helpen Audience Manager te beschermen tegen geautomatiseerde processen die onze API's of gebruikersinterface in gevaar kunnen brengen.
seo-description: Audience Manager stelt een maximumlimiet in voor het aantal kenmerken, segmenten, doelen en algoritmische modellen dat u voor een account kunt maken. De beperkingen zijn op deze punten van toepassing ongeacht of gecreeerd in het gebruikersinterface of programmatically door API methodes. Beperkingen van het gebruik helpen Audience Manager te beschermen tegen geautomatiseerde processen die onze API's of gebruikersinterface in gevaar kunnen brengen.
seo-title: Gebruiksbeperkingen
solution: Audience Manager
title: Gebruiksbeperkingen
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: aa583c0f2f8883249d7e8038b7bf2fb4c8951962
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 5%

---


# Gebruiksbeperkingen {#usage-limits}

Audience Manager stelt een maximumlimiet in voor het aantal kenmerken, segmenten, doelen en algoritmische modellen dat u voor een account kunt maken. De grenzen zijn op deze punten van toepassing ongeacht of gecreeerd in het gebruikersinterface of programmatically door [!DNL API] methodes. Beperkingen van het gebruik helpen Audience Manager tegen geautomatiseerde processen te beschermen die onze [!DNL API]s of gebruikersinterface in gevaar kunnen brengen.

## Limieten voor id-toewijzing {#id-mapping-limits}

In de onderstaande tabel staan de limieten voor [id-toewijzing](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) voor apparaat-id&#39;s. Zodra een identiteitskaart om het even welke hieronder grenzen bereikt, voegt de Audience Manager nieuwe die in kaart gebrachte identiteitskaart toe op een [!DNL FIFO] (eerste binnen, eerst uit) logica wordt gebaseerd, door de oudste opgeslagen afbeelding van identiteitskaart te verwijderen, en nieuwe toe te voegen. Raadpleeg [Index van id&#39;s](../../reference/ids-in-aam.md) in Audience Manager voor meer informatie over de id&#39;s die door Audience Manager worden ondersteund.

| ID-toewijzing | Maximale limiet |
|-----------|-------------- |
| Advertising-id ([DAID](../../reference/ids-in-aam.md)) voor apparaten ([DPUUID](../../reference/ids-in-aam.md)) | 100 Device Advertising IDs ([DAID](../../reference/ids-in-aam.md)) naar 1 Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) |
| Id van[DPUUID](../../reference/ids-in-aam.md)(cross-device) naar advertentie-id voor apparaat ([DAID](../../reference/ids-in-aam.md)) | 10 apparaat-id&#39;s ([DPUUID](../../reference/ids-in-aam.md)) naar 1 apparaat-advertentie-id ([DAID](../../reference/ids-in-aam.md)) per [DPID](../../reference/ids-in-aam.md) |
| Cookie/browser-id naar cookie/browser-id | 1000 cookie/browser-id&#39;s naar 1 cookie/browser-id |

## Itemlimieten {#item-limits}

In de tabellen worden de huidige limieten per itemtype weergegeven. U kunt geen nieuwe eigenschappen, segmenten, bestemmingen tot stand brengen, of [!UICONTROL Algorithmic Models] als u een specifieke grens voor één van deze punten bereikt. Als u een limiet bereikt, moet u een ouder item verwijderen voordat u een nieuw item kunt maken.

### Trait Limits

| Type overtrek | Maximale limiet |
| -------------------------- | ------------------------------------- |
| Totaal aantal sporen | 100,000 |
| Totale beroepskwalificaties | 150,000. Zie Trait Qualification Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)voor meer informatie over vakkwalificatie. |
| Algorithmic | 50 |
| Op regel gebaseerd | 100,000 |
| Onboard | 100,000 |
| Maptrajecten | 2,000 |

### Segmentlimiet

| Segmenttype | Maximale limiet |
| -------------- | ------------- |
| Totaal segmenten | 20,000 |

### Doelgrenzen

| Doeltype | Maximale limiet |
| ------------------ | ------------- |
| Totaal bestemmingen | 1,000 |
| Cookie | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limieten algoritmisch model

| Item | Maximale limiet |
| -------- | ----- |
| Actief [!UICONTROL Look-Alike Models] | 20. Audience Manager telt alleen *actieve* algoritmische modellen tegen de limiet. |
| [!UICONTROL Look-Alike Models] maximale doelgrootte | 25,000,000.  Deze limiet kan niet worden verhoogd. U kunt de publieksgrootte verminderen door minder gegevensbronnen voor het model te selecteren of door een korter terugblik venster te selecteren. |
| Maximumaantal uitgesloten kenmerken voor een [!UICONTROL Look-Alike Model] | 500 Zie [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Naximum [!UICONTROL Predictive Audiences Models] | 10 |
| Maximaal aantal basislijnpersona&#39;s voor [!UICONTROL Predictive Audiences] modellen | 50 |

### Maplimieten

| Item | Maximale limiet |
| ------------- | ------------------ |
| Mappen overtrekken | 2,000.  Uw mapstructuur kan maximaal vijf niveaus diep zijn. |

### Afgeleide signaallimieten

| Item | Maximale limiet |
| --------------- | ------------- |
| Afgeleide signalen | 50,000. |

### Limiet voor bedrijfsaccounts

| Item | Maximale limiet |
| ----------- | ------------- |
| Maximum aantal gebruikersrekeningen voor een bedrijf | 1,000. |

## Monitorgebruik {#monitor-usage}

Je kunt het gebruik en de limieten van je account bekijken door naar te gaan **[!UICONTROL Administration > Limits]**. Voor toegang zijn beheerdersmachtigingen vereist.

![gebruikslimieten afbeelding](assets/usage-limits.png)

## Itemlimieten verhogen {#increase-item-limits}

De hier vermelde standaardgrenzen zouden genoeg capaciteit voor uw bedrijfsbehoeften moeten verstrekken. Als uw organisatie deze limieten consequent bereikt, neemt u contact op met uw accountvertegenwoordiger om een verhoging te bespreken.