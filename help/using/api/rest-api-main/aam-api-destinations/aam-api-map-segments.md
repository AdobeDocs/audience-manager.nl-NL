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
ht-degree: 2%

---

# Segmenten toewijzen aan een bestemming {#map-segments-to-a-destination}

De segmenten van de kaart aan bestemmingen met deze [!DNL RESTful API] methoden.

<!-- c_api_map_seg_dest.xml -->

## Ondersteunde doeltypen: Alleen URL en cookie

De beschikbare `POST` methoden waarmee u segmenten kunt toewijzen aan [!UICONTROL URL] en [!UICONTROL cookie destinations] alleen. U kunt momenteel geen segmenten toewijzen aan [!UICONTROL server-to-server destinations] met deze [!DNL REST API] methoden. Gebruik in plaats hiervan de gebruikersinterface. De verwante bestemming `GET` methodes laten u informatie over terugwinnen [!UICONTROL server-to-server destinations] gemaakt in de gebruikersinterface.

## Wijs een Segment aan een Niet in series vervaardigd Doel URL toe {#map-segment-non-serial}

A `POST` methode die u een segment aan een niet periodieke kaart laat toewijzen [!UICONTROL URL] bestemming.

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

A `POST` methode die u een segment aan geserialiseerde een kaart laat maken [!UICONTROL URL] bestemming.

<!-- r_map_serialized_url.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Voorbeeldverzoek

In het verzoek worden de `traitAlias` komt overeen met de sleutel in een sleutelwaardepaar. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

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

## Wijs een Segment aan een Bestemming van het Koekje toe: Single-Key, zonder serienummering {#map-segment-cookie-noserial}

A `POST` methode die u een segment aan enig-zeer belangrijk laat in kaart brengen, niet in series vervaardigd [!UICONTROL cookie] bestemming.

<!-- r_map_cookie_noserial.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Voorbeeldverzoek

In het verzoek worden de `valueAlias` komt overeen met de waarde in een sleutelwaardepaar. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

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

## Wijs een Segment aan een Bestemming van het Koekje toe: Multi-Key, zonder serienummering {#map-segment-cookie-multi-noserial}

A `POST` methode die u een segment aan multi-sleutel laat in kaart brengen, niet-geserialiseerde [!UICONTROL cookie] bestemming.

<!-- r_map_cookie_multikey_noserial.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Voorbeeldverzoek

In het verzoek worden de `traitAlias` en `valueAlias` Stel de sleutel en de waarde respectievelijk in een sleutelwaardepaar in. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

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

## Wijs een Segment aan een Bestemming van het Koekje toe: Multi-Key, serieel {#map-segment-cookie-multi-serial}

A `POST` methode die u een segment aan multi - zeer belangrijk laat in kaart brengen, geserialiseerd [!UICONTROL cookie destination].

<!-- r_map_cookie_multikey_serialized.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Voorbeeldverzoek

In het verzoek worden de `traitAlias` en `valueAlias` Stel de sleutel en de waarde in een sleutelwaardepaar in. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

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

A `POST` methode waarmee u een segment kunt toewijzen aan een bestaand segment [!UICONTROL server-to-server] bestemming. Het is echter niet mogelijk om [!UICONTROL server-to-server] bestemmingen met deze momenteel beschikbare [!DNL API] methoden.

<!-- r_map_segment_s2s.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Voorbeeldverzoek

In het verzoek worden de `traitAlias` komt overeen met de sleutel in een sleutelwaardepaar. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

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

A `POST` methode waarmee u een array van [!UICONTROL cookie] of [!UICONTROL URL] doeltoewijzingen.

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

A `POST` methode waarmee u meerdere segmenten kunt toewijzen aan een doel.

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

A `PUT` methode waarmee u een bestaand doel kunt bijwerken `destinationId`.

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

A `PUT` methode waarmee u een toewijzing aan een doel kunt bijwerken met de opgegeven `mappingId`.

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
>* [Bestemmingen ](../../../features/destinations/destinations.md)
>* [Serienummering bestemming](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Sleutelwaardeparen](../../../reference/key-value-pairs-explained.md)

