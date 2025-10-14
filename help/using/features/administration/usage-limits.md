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
source-wordcount: '530'
ht-degree: 3%

---

# Gebruiksbeperkingen {#usage-limits}

Audience Manager stelt een maximumlimiet in voor het aantal kenmerken, segmenten, doelen en algoritmische modellen dat u voor een account kunt maken. Limieten gelden voor deze items, ongeacht of deze zijn gemaakt in de gebruikersinterface of via programmacode via [!DNL API] -methoden. Beperkingen van het gebruik helpen Audience Manager te beschermen tegen geautomatiseerde processen die onze [!DNL API] s of gebruikersinterface in gevaar kunnen brengen.

## Limieten voor id-toewijzing {#id-mapping-limits}

De lijst hieronder maakt een lijst van de [&#x200B; afbeelding van identiteitskaart &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) grenzen voor apparaat IDs. Als een id een van de onderstaande limieten heeft bereikt, voegt Audience Manager nieuwe id-toewijzingen toe op basis van een FIFO-logica (eerst in, eerst uit), door de oudste opgeslagen id-toewijzing te verwijderen en de nieuwe id toe te voegen. Verwijs naar [&#x200B; Index van IDs &#x200B;](../../reference/ids-in-aam.md) in Audience Manager voor details op IDs die door Audience Manager wordt gesteund.

| ID-toewijzing | Maximale limiet |
|-----------|-------------- |
| Identiteitskaart van Advertising van het apparaat ([&#x200B; DAID &#x200B;](../../reference/ids-in-aam.md)) aan dwars-apparaat identiteitskaart ([&#x200B; DPUUID &#x200B;](../../reference/ids-in-aam.md)) | 100 Apparaat Advertising IDs ([&#x200B; DAID &#x200B;](../../reference/ids-in-aam.md)) aan 1 dwars-apparaat identiteitskaart ([&#x200B; DPUUID &#x200B;](../../reference/ids-in-aam.md)) |
| Identiteitskaart van het dwars-apparaat ([&#x200B; DPUUID &#x200B;](../../reference/ids-in-aam.md)) aan identiteitskaart van Advertising van het Apparaat ([&#x200B; DAID &#x200B;](../../reference/ids-in-aam.md)) | 10 dwars-apparaat IDs ([&#x200B; DPUUID &#x200B;](../../reference/ids-in-aam.md)) aan 1 identiteitskaart van Advertising van het Apparaat ([&#x200B; DAID &#x200B;](../../reference/ids-in-aam.md)), per elk [&#x200B; DPID &#x200B;](../../reference/ids-in-aam.md) |
| Cookie/browser-id naar cookie/browser-id | 1000 cookie/browser-id&#39;s naar 1 cookie/browser-id |

## Itemlimieten {#item-limits}

In de tabellen worden de huidige limieten per itemtype weergegeven. U kunt geen nieuwe eigenschappen, segmenten, bestemmingen, of [!UICONTROL Algorithmic Models] tot stand brengen als u een specifieke grens voor één van deze punten bereikt. Als u een limiet bereikt, moet u een ouder item verwijderen voordat u een nieuw item kunt maken.

### Trait Limits

| Type overtrek | Maximale limiet |
| -------------------------- | ------------------------------------- |
| Totaal aantal treinen | 100.000 |
| Totale beroepskwalificaties | 150.000. Voor meer informatie over vakkwalificatie, zie de Grens van de Kwalificatie van het Beetje in [&#x200B; Verwijzing van de Kwalificaties van het Beetje &#x200B;](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algorithmic | 50 |
| Op regel gebaseerd | 100.000 |
| Onboard | 100.000 |
| Maptrajecten | 2.000 |

### Segmentlimiet

| Segmenttype | Maximale limiet |
| -------------- | ------------- |
| Totaal aantal segmenten | 20.000 |

### Doelgrenzen

| Doeltype | Maximale limiet |
| ------------------ | ------------- |
| Totaal bestemmingen | 1.000 |
| Cookie | 1.000 |
| URL | 1.000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limieten algoritmisch model

| Item | Maximale limiet |
| -------- | ----- |
| Actief [!UICONTROL Look-Alike Models] | &#x200B;20. Audience Manager telt slechts *actieve* algoritmische modellen tegen de grens. |
| [!UICONTROL Look-Alike Models] maximale doelgrootte | 25 000 000.  Deze limiet kan niet worden verhoogd. U kunt de publieksgrootte verminderen door minder gegevensbronnen voor het model te selecteren of door een korter terugblik venster te selecteren. |
| Maximumaantal uitgesloten kenmerken voor een [!UICONTROL Look-Alike Model] | &#x200B;500. Zie [&#x200B; Uitsluiting van het Spoor in Algorithmic Modeling &#x200B;](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Maximaal [!UICONTROL Predictive Audiences Models] | 10 |
| Maximum aantal basislijnpersona&#39;s voor [!UICONTROL Predictive Audiences Models] | 50 |

### Maplimieten

| Item | Maximale limiet |
| ------------- | ------------------ |
| Mappen overtrekken | 2.000.  Uw mapstructuur kan maximaal vijf niveaus diep zijn. |

### Afgeleide signaallimieten

| Item | Maximale limiet |
| --------------- | ------------- |
| Afgeleide signalen | 50.000. |

### Limiet voor bedrijfsaccounts

| Item | Maximale limiet |
| ----------- | ------------- |
| Maximum aantal gebruikersrekeningen voor een bedrijf | 1.000. |

## Monitorgebruik {#monitor-usage}

Ga naar **[!UICONTROL Administration > Limits]** om het gebruik en de limieten van uw account te bekijken. Voor toegang zijn beheerdersmachtigingen vereist.

![&#x200B; gebruikslimieten beeld &#x200B;](assets/usage-limits.png)

## Itemlimieten verhogen {#increase-item-limits}

De hier vermelde standaardgrenzen zouden genoeg capaciteit voor uw bedrijfsbehoeften moeten verstrekken. Als uw organisatie deze limieten consequent bereikt, neemt u contact op met uw accountvertegenwoordiger om een verhoging te bespreken.
