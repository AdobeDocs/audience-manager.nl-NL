---
description: Maak doelen met deze RESTful API-methoden.
seo-description: Maak doelen met deze RESTful API-methoden.
seo-title: Bestemmingen maken
solution: Audience Manager
title: Bestemmingen maken
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 2%

---


# Bestemmingen maken {#create-destinations}

Maak doelen met deze [!UICONTROL RESTful API] methoden.

<!-- c_create_destinations.xml -->

## Ondersteunde doeltypen: Alleen URL en cookie

Met de beschikbare `POST` methoden kunt u [!UICONTROL URL] alleen en [!UICONTROL cookie destinations] alleen maken. U kunt momenteel niet maken [!UICONTROL server-to-server destinations] met deze [!DNL REST API] methoden. Nochtans, laten de verwante `GET` bestemmingsmethodes u informatie over terugwinnen [!UICONTROL server-to-server destinations] die in het gebruikersinterface wordt gecreeerd.

## Een niet-seriële URL-bestemming maken {#create-nonserial-dest}

Een `POST` methode waarmee u een doel kunt maken dat segmenten accepteert die bestaan uit enkele sleutelwaardeparen (bijvoorbeeld `gender=male` of `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`

### Voorbeeldverzoek

Met deze aanvraag wordt één doel gemaakt. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Antwoord

Een succesvol verzoek keert `201 created` en de bestemming terug.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## Een seriële URL-bestemming maken {#create-serial-url-dest}

Een `POST` methode waarmee u een doel kunt maken dat meerdere waarden accepteert die aan één toets zijn gekoppeld (bijvoorbeeld `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`

### Voorbeeldverzoek

Specificeer veilig [!DNL URL] en afbakening voor het zeer belangrijk-waardepaar dat binnen tot de bestemming wordt overgegaan. Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### Antwoord

Een geslaagde update retourneert de antwoordcode `201 created` en de bestemming.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## Een cookiebestemming maken: Single-Key, zonder serienummering {#create-cookie-dest-single}

Een `POST` methode waarmee u een segment kunt maken [!UICONTROL cookie destination] dat segmenten accepteert die bestaan uit paren met één toets (bijvoorbeeld `gender=male` of `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`

### Voorbeeldverzoek

Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### Antwoord

Een geslaagde update retourneert de antwoordcode `201 created` en de bestemming.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## Een cookiebestemming maken: Single Key, serieel {#create-cookie-dest-single-serial}

Een `POST` methode waarmee u een doel kunt maken dat meerdere waarden accepteert die aan één toets zijn gekoppeld (bijvoorbeeld `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`

### Voorbeeldverzoek

Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Antwoord

Een geslaagde update retourneert de antwoordcode `201 created` en de bestemming.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## Een cookiebestemming maken: Multi-Key, zonder serienummering {#create-cookie-dest-multi}

Een `POST` methode waarmee u een doel kunt maken dat segmenten accepteert die meerdere toetsen met verschillende waarden bevatten (bijvoorbeeld `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`

### Voorbeeldverzoek

Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### Antwoord

Een geslaagde update retourneert de antwoordcode `201 created` en de bestemming.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Een cookiebestemming maken: Multi-Key, serieel {#create-cookie-dest-multi-serial}

Een `POST` methode waarmee u een doel kunt maken dat segmenten accepteert die meerdere sleutels en waarden bevatten (bijvoorbeeld `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### Verzoek

`POST https://api.demdex.com/v1/destinations/`

### Voorbeeldverzoek

Alle aanvraagwaarden zijn vereist, tenzij anders aangegeven.

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Antwoord

Een geslaagde update retourneert de antwoordcode `201 created` en de bestemming.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [Bestemmingen ](../../../features/destinations/destinations.md)
>* [Serienummering bestemming](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Sleutelwaardeparen](../../../reference/key-value-pairs-explained.md)

