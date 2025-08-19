---
description: De segmenten van de kaart aan bestemmingen met deze RESTful API methodes.
seo-description: Map segments to destinations with these RESTful API methods.
seo-title: Map Segments to a Destination
solution: Audience Manager
title: Segmenten toewijzen aan een bestemming
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
exl-id: 906df6c5-f878-48e6-a804-eb5b4407f304
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 0%

---

# Segmenten toewijzen aan een bestemming {#map-segments-to-a-destination}

Wijs segmenten toe aan doelen met deze [!DNL RESTful API] -methoden.

<!-- c_api_map_seg_dest.xml -->

## Ondersteunde doeltypen: alleen URL en cookie

Met de beschikbare `POST` -methoden kunt u segmenten alleen toewijzen aan [!UICONTROL URL] en [!UICONTROL cookie destinations] . U kunt momenteel geen segmenten toewijzen aan [!UICONTROL server-to-server destinations] met deze [!DNL REST API] -methoden. Gebruik in plaats hiervan de gebruikersinterface. Met de verwante doelmethoden `GET` kunt u echter wel informatie ophalen over [!UICONTROL server-to-server destinations] die in de gebruikersinterface is gemaakt.

## Wijs een Segment aan een Niet in series vervaardigd Doel URL toe {#map-segment-non-serial}

Een methode `POST` waarmee u een segment kunt toewijzen aan een niet-seriële [!UICONTROL URL] -bestemming.

<!-- r_map_noserial_url.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Voorbeeldverzoek

Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### Antwoord

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## Een segment toewijzen aan een geserialiseerde URL-bestemming {#map-segment-serial}

Een methode `POST` waarmee u een segment kunt toewijzen aan een geserialiseerde [!UICONTROL URL] -bestemming.

<!-- r_map_serialized_url.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Voorbeeldverzoek

In het verzoek komt `traitAlias` overeen met de sleutel in een sleutelwaardepaar. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Antwoord

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Wijs een Segment aan een Bestemming van het Koekje toe: Enig-Sleutel, niet-in series vervaardigd {#map-segment-cookie-noserial}

Een methode `POST` waarmee u een segment kunt toewijzen aan een [!UICONTROL cookie] -doel zonder serienummering met één toets.

<!-- r_map_cookie_noserial.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Voorbeeldverzoek

In het verzoek komt `valueAlias` overeen met de waarde in een sleutelwaardepaar. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### Antwoord

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Wijs een Segment aan een Bestemming van het Koekje toe: Multi-Zeer belangrijk, niet in series vervaardigd {#map-segment-cookie-multi-noserial}

Een `POST` -methode waarmee u een segment kunt toewijzen aan een [!UICONTROL cookie] -doel met meerdere sleutels zonder serienummering.

<!-- r_map_cookie_multikey_noserial.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Voorbeeldverzoek

In de aanvraag stellen de `traitAlias` en `valueAlias` respectievelijk de sleutel en de waarde in een sleutelwaardepaar in. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Antwoord

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Wijs een Segment aan een Bestemming van het Koekje toe: Van meerdere sleutels, in series vervaardigd {#map-segment-cookie-multi-serial}

Een methode `POST` waarmee u een segment kunt toewijzen aan een met meerdere sleutels geserialiseerde [!UICONTROL cookie destination] .

<!-- r_map_cookie_multikey_serialized.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Voorbeeldverzoek

In de aanvraag stellen de `traitAlias` en `valueAlias` de sleutel en de waarde in een sleutelwaardepaar in. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Antwoord

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Wijs een Segment aan een Server-aan-Server Bestemming toe {#map-segment-s2s}

Een methode `POST` waarmee u een segment kunt toewijzen aan een bestaand [!UICONTROL server-to-server] -doel. U kunt echter geen [!UICONTROL server-to-server] -doelen maken met deze momenteel beschikbare [!DNL API] -methoden.

<!-- r_map_segment_s2s.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Voorbeeldverzoek

In het verzoek komt `traitAlias` overeen met de sleutel in een sleutelwaardepaar. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Antwoord

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## Toewijzingen bestemming bulksgewijs maken {#bulk-create}

Een methode `POST` waarmee u een array van [!UICONTROL cookie] - of [!UICONTROL URL] doeltoewijzingen kunt doorgeven.

<!-- r_bulk_create.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### Voorbeeldverzoek

Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Antwoord

Een geslaagde reactie retourneert de array met gemaakte toewijzingen.

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Meerdere segmenten toevoegen aan een doel {#add-segments-dest}

Een methode `POST` waarmee u meerdere segmenten aan een doel kunt toewijzen.

<!-- r_add_segments_to_destination.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### Voorbeeldverzoek

Maak meerdere doeltoewijzingen in een array. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Antwoord

Retourneert een array met gemaakte toewijzingen.

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Een doel bijwerken op doel-id {#update-dest-data-order}

Een methode `PUT` waarmee u een bestaand doel kunt bijwerken door `destinationId` .

<!-- r_update_destination_data_order_id.xml -->

### Verzoek

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### Voorbeeldverzoek

Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Antwoord

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## Een toewijzing aan een Doel bijwerken door Id toe te wijzen {#update-mapping-dest-id}

Een `PUT` -methode waarmee u een toewijzing aan een doel kunt bijwerken met de opgegeven `mappingId` .

<!-- r_update_destination_trait_data_order_id.xml -->

### Verzoek

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### Voorbeeldverzoek

Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### Antwoord

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```

>[!MORELIKETHIS]
>
>* [Doelen](../../../features/destinations/destinations.md)
>* [ Serienummering van de Bestemming ](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Sleutelwaardeparen](../../../reference/key-value-pairs-explained.md)
