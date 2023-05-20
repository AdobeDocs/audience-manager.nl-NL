---
description: Methoden waarmee u DCS-gebieden van Audience Managers programmatisch kunt weergeven.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: API-methoden voor DCS-regio’s
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

---

# API-methoden voor DCS-regio’s {#dcs-region-api-methods}

Methoden waarmee u programmatically van Audience Manager kunt een lijst maken [!DNL DCS] regio&#39;s.

<!-- c_rest_api_regions.xml -->

Voor een lijst met regio&#39;s en de corresponderende gehele getallen raadpleegt u [Id&#39;s, locaties en hostnamen van DCS-regio&#39;s](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Een specifiek DCS-gebied weergeven {#list-specific-dcs-region}

A `GET` methode om een specifieke [!DNL DCS] regio.

<!-- r_rest_api_regions_list_specific.xml -->

### Verzoek

`GET /v1/dcs-regions/`*`<id>`*

### Samplereactie

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

Retourneert `200 OK` indien succesvol.

Voor een lijst met regio&#39;s en de corresponderende gehele getallen raadpleegt u [Id&#39;s, locaties en hostnamen van DCS-regio&#39;s](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## DCS-gebieden weergeven {#list-dcs-regions}

A `GET` methode om [!DNL DCS] regio&#39;s.

<!-- r_rest_api_regions_list.xml -->

### Verzoek

`GET /v1/dcs-regions/`

### Samplereactie

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

Retourneert `200 OK` indien succesvol.

Voor een lijst met regio&#39;s en de corresponderende gehele getallen raadpleegt u [Id&#39;s, locaties en hostnamen van DCS-regio&#39;s](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
