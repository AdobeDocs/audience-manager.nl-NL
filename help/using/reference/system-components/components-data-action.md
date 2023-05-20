---
description: De de actiecomponenten van gegevens omvatten de Diefstal van de Gegevens van de Klant, de Server van de Inzameling van Gegevens, SFTP/S3/HTTP uitgevers, IRIS, en de Server van het Geheime voorgeheugen van het Profiel.
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: Onderdelen voor actie op data
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# Onderdelen voor actie op data{#data-action-components}

De de actiecomponenten van gegevens omvatten de Diefstal van de Gegevens van de Klant, de Server van de Inzameling van Gegevens, SFTP/S3/HTTP uitgevers, IRIS, en de Server van het Geheime voorgeheugen van het Profiel.

<!-- 

c_compact.xml

 -->

De componenten van de actie zijn systemen en processen die u gegevens binnen en uit laten bewegen [!DNL Audience Manager] en (bij gebrek aan een betere uitdrukking) hiermee te doen. Deze [!DNL Audience Manager] tot de componenten behoren :

## CDF (Customer Data Feeds, klantdatafeeds) {#cdf}

[!UICONTROL CDF] Dit zijn bestanden die per uur naar klanten worden verzonden. Deze bevatten gebruikers-id&#39;s samen met de bijbehorende segment-id&#39;s, teken-id&#39;s en andere gegevens. Zie voor meer informatie [Overzicht van de doorvoergegevens voor klantgegevens](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

Zie [Onderdelen voor dataverzameling](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

De [!UICONTROL SFTP/S3] uitgevers ontvangen gesynchroniseerde id-gegevens van de [!UICONTROL Outbound Feed Converter]. Wanneer deze bestanden gereed zijn, worden de [!UICONTROL SFTP/S3 publishers] Verzend deze gegevens naar een doel dat door de client is opgegeven. Deze bestanden bevatten gesynchroniseerde id-gegevens met een één-op-veel-toewijzing van [!DNL Audience Manager] gebruikers-id&#39;s (UUID) naar:

* Apparaat-id/gegevensaanbieder-id&#39;s (DPUUID)
* Gekwalificeerde segment-id&#39;s
* Trait-id&#39;s

[!DNL Audience Manager] klanten hebben geen toegang tot eigenschappen die direct controleren [!UICONTROL SFPT/S3 publishers]. De klanten gebruiken deze dienst onrechtstreeks wanneer zij creëren en gegevens verzenden naar bestemmingen. De [!UICONTROL SFTP/S3] het systeem is in wezen een geautomatiseerd taakproces dat op geregelde tijdstippen wordt uitgevoerd.

## IRIS {#iris}

in de Griekse mythologie, [!UICONTROL Iris] is een figuur die snel reist en berichten levert. De [!UICONTROL IRIS] het systeem is een naamplaatje dat de kenmerken van dit cijfer uit de oude wereld weerspiegelt . In moderne termen [!UICONTROL IRIS] is een low-latency, high-frequency cookiesynchronisatie en de dienst van de gegevensoverdracht.

[!UICONTROL IRIS] werkt met hetzelfde type gegevens als de [!UICONTROL SFTP/S3] systeem. Maar [!UICONTROL IRIS] is verschillend omdat het gegevens naar bestemmingen in real time eerder dan bij vastgestelde intervallen verzendt. Dit is een apart systeem omdat het [!UICONTROL SFTP/S3] uitgevers kunnen geen gegevens naar een bestemming van HTTP verzenden en zij zijn niet ontworpen voor gegevensoverdracht in real time.

Er zijn geen controles UI die klanten laten werken direct met [!UICONTROL IRIS]. Klanten werken met [!UICONTROL IRIS] indirect wanneer zij tot stand brengen en gegevens verzenden naar bestemmingen, en voor andere processen die snelle gegevensoverdrachten vereisen.

Voorbeelden van [!UICONTROL IRIS] de diensten en kenmerken omvatten :

* Snelle synchronisatie (binnen 30 seconden) voor cookies en segmenten. Het kan de [!DNL Audience Manager] cookie, partnercookies of beide.
* Gegevensoverdracht in realtime. [!UICONTROL IRIS] is verantwoordelijk voor het verzenden van de in real time gebeurtenissen van de segmentkwalificatie naar een partner of een andere bestemming. Deze gegevens zijn in JSON-indeling en worden verzonden via een HTTP-verbinding `POST` verzoek.

* Bulk server-aan-server gegevensoverdrachten: Als u grote hoeveelheden gegevens met [!DNL Audience Manager], [!UICONTROL IRIS] Dit is het systeem waarmee uw servers gegevens overdragen.

* Betrouwbare infrastructuur die op schaal werkt en fouttolerantie heeft. Systemen die [!UICONTROL IRIS] omvat Amazon SQS, Amazon EC2 en Cassandra.

**Regels voor segmenttoewijzing**

Om verkeer tussen te optimaliseren [!UICONTROL IRIS] en segmentbestemmingen, [!UICONTROL IRIS] verzendt segmenten naar bestemmingen die op een reeks regels worden gebaseerd.

1. **Nieuwe segmentkwalificatie**: wanneer een apparaat in aanmerking komt voor een nieuw segment, [!UICONTROL IRIS] verzendt alle segmenten verbonden aan dat apparaat naar alle bestemmingen in kaart gebracht aan deze segmenten.

1. **Nieuwe segmentdeskwalificatie**: wanneer een apparaat niet langer voor een segment in aanmerking komt, [!UICONTROL IRIS] verzendt alle segmentkwalificaties en ontzettingen verbonden aan dat apparaat naar alle bestemmingen in kaart gebracht aan deze segmenten.

1. **Updates voor doeltoewijzing**: wanneer een bestemmingstoewijzing wordt bijgewerkt, [!UICONTROL IRIS] verzendt alle segmenten verbonden aan een apparaat naar alle bestemmingen in kaart gebracht aan deze segmenten, de volgende tijd ziet de Audience Manager het apparaat.

1. **Updates van apparaatgrafieken**: wanneer een apparaat-id wordt toegevoegd aan of verwijderd uit de apparaatgrafiek die wordt gebruikt om een segment te evalueren, [!UICONTROL IRIS] verzendt alle segmenten verbonden aan dat apparaat naar alle bestemmingen in kaart gebracht aan deze segmenten, de volgende tijd ziet de Audience Manager het apparaat.

>[!IMPORTANT]
>
>Als Audience Manager geen van de bovenstaande updates detecteert gedurende 3 opeenvolgende dagen, [!UICONTROL IRIS] verzendt alle segmenten verbonden aan een apparaat naar alle bestemmingen in kaart gebracht aan deze segmenten, de volgende tijd ziet de Audience Manager het apparaat.

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

Zie [Onderdelen voor dataverzameling](../../reference/system-components/components-data-collection.md).
