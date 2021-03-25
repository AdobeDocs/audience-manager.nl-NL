---
description: In deze sectie wordt beschreven hoe u een DCS-reactie kunt parseren om de id's van de bezoeker en regio op te halen die nodig zijn om real-time aanroepen naar de DCS uit te voeren.
seo-description: In deze sectie wordt beschreven hoe u een DCS-reactie kunt parseren om de id's van de bezoeker en regio op te halen die nodig zijn om real-time aanroepen naar de DCS uit te voeren.
seo-title: Gebruikers-id’s en -regio’s ontvangen van een DCS-reactie
solution: Audience Manager
title: Gebruikers-id’s en -regio’s ontvangen van een DCS-reactie
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 11%

---


# Gebruikers-id’s en -regio’s ontvangen van een DCS-reactie {#get-user-ids-and-regions-from-a-dcs-response}

In deze sectie wordt beschreven hoe u een [!DNL DCS]-reactie kunt parseren om de id&#39;s van de bezoeker en regio op te halen die nodig zijn om real-time aanroepen uit te voeren naar [!DNL DCS].

## Gebruiker- en regio-id&#39;s {#user-region-ids}

Een [!DNL DCS]-reactie bevat gegevens over uw sitebezoekers. U hebt de bezoeker- en regio-id nodig voordat u server-naar-server aanroepen kunt uitvoeren naar [!DNL DCS].

* De gebruikers-id is vereist om gegevens te identificeren en aan een bepaalde bezoeker te koppelen.
* De regio-id is vereist omdat deze is gekoppeld aan een regionale servernaam, die u gegevens naar [!DNL DCS] moet verzenden. [!DNL DCS] slaat informatie in gegevenscentra op die geografisch dichtst bij bezoekers van de plaats zijn. Zie [DCS-regio-id&#39;s, -locaties en hostnamen](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Deze parameters worden hieronder beschreven. De code in *italics* vertegenwoordigt veranderlijke placeholder.

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

Deze eenvoudige reactie toont `UUID` en gebied `ID`. Dit zijn alleen voorbeeldgegevens. Uw logbestanden kunnen langer en complexer zijn.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Volgende stappen {#next-steps}

Als u de gebruikers-id en de regionale servernaam hebt, kunt u beginnen met het verzenden en ontvangen van [!DNL DCS]-gegevens. Zie [DCS API-aanroepen maken](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
