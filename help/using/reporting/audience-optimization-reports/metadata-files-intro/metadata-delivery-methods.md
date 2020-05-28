---
description: Verzend of werk meta-gegevensdossiers bij door hen naar een speciale folder van Amazon S3 voor uw rekening van de Manager van de Publiek te verzenden. Raadpleeg deze sectie voor informatie over levering/directorypaden, verwerkingstijden en updates.
seo-description: Verzend of werk meta-gegevensdossiers bij door hen naar een speciale folder van Amazon S3 voor uw rekening van de Manager van de Publiek te verzenden. Raadpleeg deze sectie voor informatie over levering/directorypaden, verwerkingstijden en updates.
seo-title: Leveringsmethoden voor metagegevensbestanden
solution: Audience Manager
title: Leveringsmethoden voor metagegevensbestanden
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 62147fc719a59d2b2c7b444bce853334b03816c6
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---


# Leveringsmethoden voor metagegevensbestanden{#delivery-methods-for-metadata-files}

Verzend of werk meta-gegevensdossiers bij door hen naar een speciale [!DNL Amazon S3] folder voor uw rekening van de Manager van de Publiek te verzenden. Raadpleeg deze sectie voor informatie over levering/directorypaden, verwerkingstijden en updates.

>[!IMPORTANT]
>
> Neem contact op met de consultant van de Audience Manager of de klantenservice om aan de slag te gaan en stel een [!DNL Amazon S3] map in voor uw metagegevensbestanden.

## Syntaxis en voorbeeld van pad voor levering {#syntax}

Gegevens worden opgeslagen in aparte naamruimte voor elke klant in een [!DNL Amazon S3] map. Het bestandspad volgt de onderstaande syntaxis. Nota, de punthaakjes `<>` wijzen op veranderlijke placeholder. De andere elementen zijn constanten en veranderen niet.

**Syntaxis:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Voorbeeld:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

In de volgende tabel worden deze elementen gedefinieerd in een pad voor het leveren van bestanden.


| Bestandsparameter | Beschrijving |
---------|----------|
| `.../log_ingestion/` | Dit is het begin van de weg van de folderopslag. U ontvangt het volledige pad wanneer alles is ingesteld. |
| `pid=<AAM ID>` | Dit zeer belangrijk-waardepaar bevat uw de klantenidentiteitskaart van de Manager van de Publiek. |
| `dpid=<d_src>` | Dit zeer belangrijk-waardepaar bevat gegevensbronidentiteitskaart die op een gebeurtenisvraag wordt overgegaan. De gegevensbron-id is de waarde die alle inhoud van het bestand koppelt aan de werkelijke gegevens waartoe het behoort. </br> Stel dat u een creatieve account hebt met de id 123 en de naam Advertiser Creative A. Als een gebeurtenisaanroep wordt alleen doorgegeven aan de id die u nodig hebt om &#39;Advertiser Creative A&#39; op te nemen in het metagegevensbestand. De campagne en de creatieve projecten horen bij een gegevensbron. De gegevensbron-id is wat deze aan elkaar koppelt en ons de inhoud van het bestand nauwkeurig laat koppelen aan een id die wordt verzonden op een gebeurtenisaanroep. Zie [hoe IDs van de Vraag van de Gebeurtenis de Namen van het Dossier, de Inhoud, en de Wegen](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)van de Levering bepalen. |
| `<yyyymmdd_0_child ID>` | Dit is de bestandsnaam. Zie [Naamgevingsconventies voor metagegevensbestanden](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Verwerkingstijden en updates van bestanden {#processing-times}

Metagegevensbestanden worden viermaal per dag verwerkt, met regelmatige tussenpozen.

Als u uw metagegevensrecords wilt bijwerken, verzendt u gewoon een bestand dat nieuwe gegevens bevat. U hoeft niet elke keer volledige updates te verzenden.
