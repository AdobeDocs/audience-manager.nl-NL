---
description: Wanneer het doen van een vraag, keurt DCS zeer belangrijke-waardegegevens in standaard of geserialiseerde formaat goed. Herzie deze sectie voor informatie over hoe te om standaard en geserialiseerde sleutel-waarde gegevens te formatteren.
seo-description: Wanneer het doen van een vraag, keurt DCS zeer belangrijke-waardegegevens in standaard of geserialiseerde formaat goed. Herzie deze sectie voor informatie over hoe te om standaard en geserialiseerde sleutel-waarde gegevens te formatteren.
seo-title: Het opmaken van zeer belangrijke-waardeparen in Vraag DCS
solution: Audience Manager
title: Het opmaken van zeer belangrijke-waardeparen in Vraag DCS
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---


# Het opmaken van zeer belangrijke-waardeparen in Vraag DCS {#formatting-key-value-pairs-in-dcs-calls}

Wanneer het doen van een vraag, [!DNL DCS] keurt zeer belangrijk-waardegegevens in standaard of in series vervaardigd formaat goed. Herzie deze sectie voor informatie over hoe te om standaard en geserialiseerde sleutel-waarde gegevens te formatteren.

## Standaard en seriële sleutelwaardeparen {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type sleutelwaarde </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
   <th colname="col3" class="entry"> Voorbeeld </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standaard</b> </td> 
   <td colname="col2"> <p>Een standaard sleutel-waarde paar bestaat uit één enkele sleutel en waarde. Deze structuur ordent gegevens in afzonderlijke sleutel-waarde paren. Elke toets wordt expliciet vermeld, zelfs wanneer deze opnieuw wordt gebruikt om een andere waarde te definiëren. Dit is de gemeenschappelijkste manier om gegevens naar DCS te verzenden. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Gesserveerd</b> </td> 
   <td colname="col2"> <p>Een geserialiseerd sleutel-waardepaar bestaat uit één enkele sleutel en veelvoudige waarden. Dit kan een efficiënte manier zijn om gegevens te organiseren, maar de geserialiseerde sleutel-waarde paren vereisen specifieke symbolen om elke sleutel en elke sleutel-waarde reeks te scheiden. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Scheidingstekens en scheidingstekens voor seriële sleutelwaardeparen {#delimiters-separators}

Met geserialiseerde sleutel-waarde paren, moet u de tellers specificeren die waarden binnen en tussen deze variabelen scheiden. Voor Audience Manager zijn de volgende scheidingstekens en scheidingstekens vereist:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Voorschriften voor </th> 
   <th colname="col2" class="entry"> Symbool </th> 
   <th colname="col3" class="entry"> Afzonderlijk </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Scheidingstekens</b> </td> 
   <td colname="col2"> Ampersand &amp; </td> 
   <td colname="col3"> <p>Sleutelwaardeparen: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Scheidingstekens</b> </td> 
   <td colname="col2"> Komma </td> 
   <td colname="col3"> <p>Waarden binnen sleutelwaardeparen: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Gegevens verzenden naar de DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Belangrijke voorvoegsels en variabelen die door DCS worden ondersteund](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Belangrijke paar uitgelegd](../../../reference/key-value-pairs-explained.md)

