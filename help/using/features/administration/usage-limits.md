---
description: Audience Manager stelt een maximumlimiet in voor het aantal kenmerken, segmenten, doelen en algoritmische modellen dat u voor een account kunt maken. De beperkingen zijn op deze punten van toepassing ongeacht of gecreeerd in het gebruikersinterface of programmatically door API methodes. Beperkingen van het gebruik helpen Audience Manager te beschermen tegen geautomatiseerde processen die onze API's of gebruikersinterface in gevaar kunnen brengen.
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: Gebruiksbeperkingen
keywords: ID-toewijzing, id-toewijzingen, cookie-toewijzingen
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 5%

---

# Gebruiksbeperkingen {#usage-limits}

Audience Manager stelt een maximumlimiet in voor het aantal kenmerken, segmenten, doelen en algoritmische modellen dat u voor een account kunt maken. De grenzen zijn op deze punten van toepassing ongeacht of gecreeerd in het gebruikersinterface of programmatically door [!DNL API] methoden. Beperkingen van het gebruik helpen Audience Manager te beschermen tegen geautomatiseerde processen die onze [!DNL API]s of gebruikersinterface.

## Limieten voor id-toewijzing {#id-mapping-limits}

In de onderstaande tabel worden de [ID-toewijzing](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limieten voor apparaat-id&#39;s. Zodra een identiteitskaart om het even welke hieronder grenzen bereikt, voegt de Audience Manager nieuwe die in kaart gebrachte identiteitskaart toe op een FIFO (eerst in, eerst uit) logica wordt gebaseerd, door de oudste opgeslagen afbeelding van identiteitskaart te verwijderen, en nieuwe toe te voegen. Zie [Index van id&#39;s](../../reference/ids-in-aam.md) in Audience Manager voor meer informatie over de id&#39;s die door Audience Manager worden ondersteund.

| ID-toewijzing | Maximale limiet |
|-----------|-------------- |
| Advertentie-id van apparaat ([DAID](../../reference/ids-in-aam.md)) naar apparaat-id ([DPUUID](../../reference/ids-in-aam.md)) | 100 Apparaatadvertentie-id&#39;s ([DAID](../../reference/ids-in-aam.md)) naar 1 apparaat-id ([DPUUID](../../reference/ids-in-aam.md)) |
| Apparaatoverschrijdende id ([DPUUID](../../reference/ids-in-aam.md)) naar advertentie-id van apparaat ([DAID](../../reference/ids-in-aam.md)) | 10 Apparaatoverschrijdende id&#39;s ([DPUUID](../../reference/ids-in-aam.md)) naar 1 advertentie-id van apparaat ([DAID](../../reference/ids-in-aam.md)), per stuk [DPID](../../reference/ids-in-aam.md) |
| Cookie/browser-id naar cookie/browser-id | 1000 cookie/browser-id&#39;s naar 1 cookie/browser-id |

## Itemlimieten {#item-limits}

In de tabellen worden de huidige limieten per itemtype weergegeven. U kunt geen nieuwe eigenschappen, segmenten, bestemmingen tot stand brengen, of [!UICONTROL Algorithmic Models] als u een specifieke limiet voor een van deze objecten hebt bereikt. Als u een limiet bereikt, moet u een ouder item verwijderen voordat u een nieuw item kunt maken.

### Trait Limits

| Type overtrek | Maximale limiet |
| -------------------------- | ------------------------------------- |
| Totaal aantal sporen | 100,000 |
| Totale beroepskwalificaties | 150,000. Zie Trait Qualification Limit voor meer informatie over vakkwalificatie in [Verwijzing naar beroepskwalificaties](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
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
| Actief [!UICONTROL Look-Alike Models] | 20. Alleen aantal Audience Managers *actief* algoritmische modellen tegen de limiet. |
| [!UICONTROL Look-Alike Models] maximale doelgrootte | 25,000,000.  Deze limiet kan niet worden verhoogd. U kunt de publieksgrootte verminderen door minder gegevensbronnen voor het model te selecteren of door een korter terugblik venster te selecteren. |
| Maximumaantal uitgesloten kenmerken voor een [!UICONTROL Look-Alike Model] | 500 Zie [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Maximum [!UICONTROL Predictive Audiences Models] | 10 |
| Maximum aantal basislijnpersona&#39;s voor [!UICONTROL Predictive Audiences Models] | 50 |

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

Je kunt het gebruik en de limieten van je account bekijken door naar **[!UICONTROL Administration > Limits]**. Voor toegang zijn beheerdersmachtigingen vereist.

![gebruikslimieten afbeelding](assets/usage-limits.png)

## Itemlimieten verhogen {#increase-item-limits}

De hier vermelde standaardgrenzen zouden genoeg capaciteit voor uw bedrijfsbehoeften moeten verstrekken. Als uw organisatie deze limieten consequent bereikt, neemt u contact op met uw accountvertegenwoordiger om een verhoging te bespreken.
