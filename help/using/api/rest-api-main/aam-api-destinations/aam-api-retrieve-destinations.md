---
description: Een GET methode die de bestemming voor gespecificeerde destinationId terugkeert.
seo-description: Een GET methode die de bestemming voor gespecificeerde destinationId terugkeert.
seo-title: Een bestemming retourneren op destinatie-id
solution: Audience Manager
title: Een bestemming retourneren op destinatie-id
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 5%

---


# Een bestemming retourneren op destinatie-id {#return-a-destination-by-destination-id}

Een `GET` methode die de bestemming voor gespecificeerde `destinationId`.

<!-- r_get_all_destinations_order_id.xml -->

## Verzoek

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>Als u het `mappings` veld wilt invullen, geeft u dit door `includeMappings=true` in de URL.

## Antwoord

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Alle doelen retourneren {#return-all-destinations}

Een `GET` methode die alle bestemmingen voor de gespecificeerde partner terugkeert.

<!-- r_get_all_destinations.xml -->

### Verzoek

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Optioneel)* Geef aan `containsSegment=<sid>` om een array te retourneren van alle doelen die aan het opgegeven segment zijn toegewezen. Uw query kan er bijvoorbeeld als volgt uitzien: `GET .../destinations/?containsSegment=4321`.
   >
   >
* Retourneert het volledige doelobject niet. Hiermee wordt het doel via de gegevensvolgorde opgehaald als u een volledig gevuld object nodig hebt.


### Optionele queryparameters

U kunt deze optionele parameters gebruiken met API-methoden die *alle* eigenschappen voor een object retourneren. Plaats deze opties in het verzoekkoord wanneer het overgaan van die vraag in aan het [!DNL API]. Zie [Optionele parameters](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th>
   <th colname="col2" class="entry"> Beschrijving </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> Geeft resultaten op paginanummer. De nummering begint bij 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> Stelt het aantal reactieresultaten in dat door de aanvraag wordt geretourneerd (10 is standaard). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">Sorteert en retourneert resultaten volgens de opgegeven <span class="keyword"> JSON</span> -eigenschap. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Sorteert en retourneert resultaten in aflopende volgorde. Oplopend is standaard. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Retourneert resultaten op basis van de opgegeven tekenreeks die u als zoekparameter wilt gebruiken. Stel dat u resultaten wilt zoeken voor alle modellen die het woord "Testen" hebben in een van de waardevelden voor dat item. Uw voorbeeldverzoek kan er als volgt uitzien: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>U kunt zoeken op elke waarde die door de methode "get all" wordt geretourneerd. </p> </td>
  </tr>
 </tbody>
</table>

### Antwoord

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Een doeltoewijzing retourneren met de toewijzingsid {#return-dest-mapping-id}

Een `GET` methode die een individuele bestemmingstoewijzing terugkeert die op `mappingId`wordt gebaseerd.

<!-- r_get_destination_trait_data_order.xml -->

### Verzoek

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### Antwoord

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Toewijzingen retourbestemming {#return-dest-mappings}

Een `GET` methode die de toewijzingen voor een bestemming terugkeert.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>De teruggekeerde afbeelding is specifiek voor het bestemmingstype en de configuratie.

### Verzoek

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>Ondersteunt paginaparameters.

### Antwoord

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Alle beschikbare Platforms van de Bestemming terugkeren {#return-dest-platforms}

Een `GET` methode die alle beschikbare apparatenplatforms voor bestemmingen terugkeert.

<!-- r_get_dest_platforms.xml -->

### Verzoek

`GET /destinations/configurations/available-platforms/`

### Antwoord

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## S2S- en Bulk S2S-taakgeschiedenis retourneren {#return-job-history}

Een `GET` methode die uitgaande [!UICONTROL Server-to-Server] ( [!UICONTROL S2S][!UICONTROL S2S] ) en de geschiedenisinformatie van de bulkdoelbaan terugkeert.

<!-- r_get_job_history.xml -->

### Verzoek

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Vereiste queryparameters: `startDate` = *&lt;`epochtime`>* en `endDate` = *&lt;`epochtime`>*.

### Antwoord

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
