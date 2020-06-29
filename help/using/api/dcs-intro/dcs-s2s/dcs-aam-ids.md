---
description: In deze sectie wordt beschreven hoe u een DCS-reactie kunt parseren om de id's van de bezoeker en regio op te halen die nodig zijn om real-time aanroepen naar de DCS uit te voeren.
seo-description: In deze sectie wordt beschreven hoe u een DCS-reactie kunt parseren om de id's van de bezoeker en regio op te halen die nodig zijn om real-time aanroepen naar de DCS uit te voeren.
seo-title: Gebruikersnaam en regio's ophalen uit een DCS-reactie
solution: Audience Manager
title: Gebruikersnaam en regio's ophalen uit een DCS-reactie
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---


# Gebruikersnaam en regio&#39;s ophalen uit een DCS-reactie {#get-user-ids-and-regions-from-a-dcs-response}

Deze sectie beschrijft hoe te om een [!DNL DCS] reactie te ontleden om bezoeker en gebied IDs terug te winnen die wordt vereist om vraag in real time aan [!DNL DCS]te maken.

## Gebruiker- en regio-id&#39;s {#user-region-ids}

Een [!DNL DCS] reactie bevat gegevens over uw sitebezoekers. U hebt de bezoeker- en regio-id nodig voordat u server-naar-server aanroepen kunt uitvoeren naar de [!DNL DCS]server.

* De gebruikers-id is vereist om gegevens te identificeren en aan een bepaalde bezoeker te koppelen.
* De regio-id is vereist omdat deze is gekoppeld aan een regionale servernaam, die u gegevens naar de [!DNL DCS]server moet verzenden. De [!DNL DCS] opslaginformatie in gegevenscentra die geografisch het dichtst bij plaatsbezoekers zijn. Zie [DCS-regio-id&#39;s, -locaties en -hostnamen](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Deze parameters worden hieronder beschreven. De code in *cursief* staat voor een variabele plaatsaanduiding.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Gegevenstype </th> 
   <th colname="col3" class="entry"> Voorbeeld </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Samplereactie {#sample-response}

Deze eenvoudige reactie laat de `UUID` regio zien `ID`. Dit zijn alleen voorbeeldgegevens. Uw logbestanden kunnen langer en complexer zijn.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Volgende stappen {#next-steps}

Zodra u de gebruikers-id en de regionale servernaam hebt, kunt u beginnen met het verzenden en ontvangen van [!DNL DCS] gegevens. Zie [DCS API-aanroepen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)maken.
