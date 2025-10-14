---
description: Verzend of werk meta-gegevensdossiers bij door hen naar een speciale folder van Amazon S3 voor uw Audience Manager rekening te verzenden. Raadpleeg deze sectie voor informatie over levering/directorypaden, verwerkingstijden van bestanden en updates.
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: Leveringsmethoden voor metagegevensbestanden
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Leveringsmethoden voor metagegevensbestanden{#delivery-methods-for-metadata-files}

Verzend of werk metagegevensbestanden bij door deze naar een speciale [!DNL Amazon S3] -map voor uw Audience Manager-account te verzenden. Raadpleeg deze sectie voor informatie over levering/directorypaden, verwerkingstijden van bestanden en updates.

>[!IMPORTANT]
>
> Neem contact op met uw Audience Manager-consultant of de klantenservice om aan de slag te gaan en stel een map [!DNL Amazon S3] in voor uw metagegevensbestanden.

## Syntaxis en voorbeeld van pad voor levering {#syntax}

Gegevens worden opgeslagen in een aparte naamruimte voor elke klant in een map [!DNL Amazon S3] . Het bestandspad volgt de onderstaande syntaxis. Hoekhaken `<>` geven een variabele plaatsaanduiding aan. De andere elementen zijn constanten en veranderen niet.

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
|---------|----------|
| `.../log_ingestion/` | Dit is het begin van de weg van de folderopslag. U ontvangt het volledige pad wanneer alles is ingesteld. |
| `pid=<AAM ID>` | Dit sleutelwaardepaar bevat uw Audience Manager-klant-id. |
| `dpid=<d_src>` | Dit zeer belangrijk-waardepaar bevat gegevensbronidentiteitskaart die op een gebeurtenisvraag wordt overgegaan. De gegevensbron-id is de waarde die alle inhoud van het bestand koppelt aan de werkelijke gegevens waartoe het behoort. </br> Stel dat u een creatieve account hebt met de id 123 en de naam Advertiser Creative A. Als een gebeurtenisaanroep alleen de id doorgeeft die u &quot;Advertiser Creative A&quot; in het metagegevensbestand moet opnemen. De campagne en de creatieve activiteiten horen bij een gegevensbron. De gegevensbron-id is wat deze aan elkaar koppelt en ons de inhoud van het bestand nauwkeurig laat koppelen aan een id die wordt verzonden op een gebeurtenisaanroep. Zie [&#x200B; hoe de Vraag IDs van de Gebeurtenis de Namen van het Dossier, de Inhoud, en de Paden van de Levering &#x200B;](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names) bepaalt. |
| `<yyyymmdd_0_child ID>` | Dit is de bestandsnaam. Zie [&#x200B; Noemende Conventies voor de Dossiers van Meta-gegevens &#x200B;](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Verwerkingstijden en updates van bestanden {#processing-times}

Metagegevensbestanden worden viermaal per dag verwerkt, met regelmatige tussenpozen.

Als u uw metagegevensrecords wilt bijwerken, verzendt u gewoon een bestand dat nieuwe gegevens bevat. U hoeft niet elke keer volledige updates te verzenden.
