---
description: De de actiecomponenten van gegevens omvatten de Diefstal van de Gegevens van de Klant, de Server van de Inzameling van Gegevens, SFTP/S3/HTTP uitgevers, IRIS, en de Server van het Geheime voorgeheugen van het Profiel.
seo-description: De de actiecomponenten van gegevens omvatten de Diefstal van de Gegevens van de Klant, de Server van de Inzameling van Gegevens, SFTP/S3/HTTP uitgevers, IRIS, en de Server van het Geheime voorgeheugen van het Profiel.
seo-title: Componenten van gegevenshandeling
solution: Audience Manager
title: Componenten van gegevenshandeling
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 0%

---


# Componenten van gegevenshandeling{#data-action-components}

De de actiecomponenten van gegevens omvatten de Diefstal van de Gegevens van de Klant, de Server van de Inzameling van Gegevens, SFTP/S3/HTTP uitgevers, IRIS, en de Server van het Geheime voorgeheugen van het Profiel.

<!-- 

c_compact.xml

 -->

Actiecomponenten zijn systemen en processen waarmee u gegevens in en uit kunt verplaatsen [!DNL Audience Manager] en er (bij gebrek aan een betere uitdrukking) dingen mee kunt doen. Deze [!DNL Audience Manager] onderdelen zijn:

## CDF (Customer Data Feeds) {#cdf}

[!UICONTROL CDF] Dit zijn bestanden die per uur naar klanten worden verzonden. Deze bevatten gebruikers-id&#39;s samen met de bijbehorende segment-id&#39;s, teken-id&#39;s en andere gegevens. Voor meer informatie, zie het Overzicht [van de Invoer van de Gegevens van de](../../features/cdf-files.md)Klant.

## Data Collection Server (DCS) {#dcs}

Zie [Componenten](../../reference/system-components/components-data-collection.md)voor gegevensverzameling.

## SFTP/S3 {#sftp-s3}

De [!UICONTROL SFTP/S3] uitgevers ontvangen gesynchroniseerde-id-gegevens van de [!UICONTROL Outbound Feed Converter]uitgever. Wanneer deze bestanden klaar zijn, [!UICONTROL SFTP/S3 publishers] verzendt de ontvanger deze gegevens naar een door de client opgegeven bestemming. Deze bestanden bevatten gesynchroniseerde id-gegevens met een één-op-veel toewijzing van [!DNL Audience Manager] gebruikers-id&#39;s (UUID) aan:

* Apparaat-id/gegevensaanbieder-id&#39;s (DPUUID)
* Gekwalificeerde segment-id&#39;s
* Trait-id&#39;s

[!DNL Audience Manager] klanten hebben geen toegang tot eigenschappen die rechtstreeks het [!UICONTROL SFPT/S3 publishers]. De klanten gebruiken deze dienst onrechtstreeks wanneer zij creëren en gegevens verzenden naar bestemmingen. Het [!UICONTROL SFTP/S3] systeem is in wezen een geautomatiseerd taakproces dat met geplande intervallen wordt uitgevoerd.

## IRIS {#iris}

In de Griekse mythologie [!UICONTROL Iris] is een figuur die snel boodschappen afgeeft. Het [!UICONTROL IRIS] systeem is een naamplaatje dat de kenmerken van dit cijfer uit de oude wereld weerspiegelt. In moderne termen [!UICONTROL IRIS] is dit een low-latency, high-frequency cookie synchronisatie en gegevensoverdrachtservice.

[!UICONTROL IRIS] werkt met hetzelfde type gegevens als het [!UICONTROL SFTP/S3] systeem. Nochtans, [!UICONTROL IRIS] is verschillend omdat het gegevens naar bestemmingen in real time eerder dan met vastgestelde intervallen verzendt. Dit is een afzonderlijk systeem omdat de [!UICONTROL SFTP/S3] uitgevers geen gegevens naar een bestemming van HTTP kunnen verzenden en zij niet voor gegevensoverdrachten in real time worden ontworpen.

Er zijn geen controles UI die klanten met [!UICONTROL IRIS]laten werken. De klanten werken met [!UICONTROL IRIS] onrechtstreeks wanneer zij creëren en gegevens verzenden naar bestemmingen, en voor andere processen die snelle gegevensoverdrachten vereisen.

Voorbeelden van [!UICONTROL IRIS] services en functies zijn:

* Snelle synchronisatie (binnen 30 seconden) voor cookies en segmenten. Het kan het [!DNL Audience Manager] koekje, partnerkoekjes, of allebei synchroniseren.
* Gegevensoverdracht in realtime. [!UICONTROL IRIS] is verantwoordelijk voor het verzenden van de in real time gebeurtenissen van de segmentkwalificatie naar een partner of een andere bestemming. Deze gegevens zijn in JSON-indeling en worden verzonden via een HTTP- `POST` aanvraag.

* Bulk server-aan-server gegevensoverdrachten: Als u grote hoeveelheden gegevens met elkaar uitwisselen, [!DNL Audience Manager]is [!UICONTROL IRIS] dat het systeem waarmee uw servers werken om gegevens over te dragen.

* Betrouwbare infrastructuur die op schaal werkt en fouttolerantie heeft. Systemen die macht [!UICONTROL IRIS] omvatten Amazon SQS, Amazon EC2, en Cassandra.

**Regels voor segmenttoewijzing**

Om verkeer tussen [!UICONTROL IRIS] en segmentbestemmingen te optimaliseren, [!UICONTROL IRIS] verzendt segmenten naar bestemmingen die op een reeks regels worden gebaseerd.

1. **Nieuwe segmentkwalificatie**: wanneer een apparaat voor een nieuw segment kwalificeert, [!UICONTROL IRIS] verzendt alle segmenten verbonden aan dat apparaat naar alle bestemmingen in kaart gebracht aan deze segmenten.

1. **Nieuwe segmentuitsluiting**: wanneer een hulpmiddel niet meer voor een segment in aanmerking komt, [!UICONTROL IRIS] verzendt alle segmentkwalificaties en ontzettingen verbonden aan dat hulpmiddel naar alle bestemmingen die aan deze segmenten worden toegewezen.

1. **Updates** voor doeltoewijzing: wanneer een bestemmingstoewijzing wordt bijgewerkt, [!UICONTROL IRIS] verzendt alle segmenten verbonden aan een apparaat naar alle bestemmingen in kaart gebracht aan deze segmenten, de volgende tijd ziet de Audience Manager het apparaat.

1. **Apparaatgrafiek wordt bijgewerkt**: wanneer om het even welke apparatenidentiteitskaart wordt toegevoegd of verwijderd uit de apparatengrafiek die wordt gebruikt om een segment te evalueren, [!UICONTROL IRIS] verzendt alle segmenten verbonden aan dat apparaat naar alle bestemmingen in kaart gebracht aan deze segmenten, de volgende tijd Audience Manager het apparaat ziet.

>[!IMPORTANT]
>
>Als de Audience Manager geen updates hierboven 3 opeenvolgende dagen ontdekt, [!UICONTROL IRIS] verzendt alle segmenten verbonden aan een apparaat naar alle bestemmingen in kaart gebracht aan deze segmenten, de volgende tijd ziet de Audience Manager het apparaat.

**Voorbeeldgegevensbestand**

Het volgende voorbeeld bevat real-time segmentgegevens van [!UICONTROL IRIS]. Houd er rekening mee dat dit alleen voorbeeldgegevens zijn. Elke klant kan verschillende opmaakvereisten hebben zodat de inhoud kan variëren.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## Profile Cache Server (PCS) {#pcs}

Zie [Componenten](../../reference/system-components/components-data-collection.md)voor gegevensverzameling.
