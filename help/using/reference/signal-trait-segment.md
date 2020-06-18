---
description: Beschrijft de componenten van een segment van de Audience Manager, de uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe het gegeven in een gebeurtenisvraag wordt overgebracht.
seo-description: Beschrijft de componenten van een segment van de Audience Manager, de uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe het gegeven in een gebeurtenisvraag wordt overgebracht.
seo-title: Signalen, Traits en Segmenten
solution: Audience Manager
title: Signalen, Traits en Segmenten
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---


# Signalen, Traits en Segmenten{#signals-traits-and-segments}

Beschrijft de componenten van een [!DNL Audience Manager] segment, de uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe het gegeven in een gebeurtenisvraag wordt overgebracht.

<!-- 

c_signal_trait_segment.xml

 -->

**Samenstelling en doel**

[!DNL Audience Manager] de gegevens bestaan uit signalen, eigenschappen, segmenten, en verwante kwalificatieregels. De gegevenselementen en de regels combineren om segmenten tot stand te brengen. Segmenten organiseren sitebezoekers in verwante groepen. De volgende lijst bepaalt de drie belangrijkste componenten in een [!DNL Audience Manager] segment.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Bestaat uit </th> 
   <th colname="col3" class="entry"> Voorbeeld </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Signaal</b> </td> 
   <td colname="col2"> <p>Signalen zijn de kleinste gegevenseenheden in <span class="keyword"> Audience Manager</span> en worden uitgedrukt als <a href="../reference/key-value-pairs-explained.md"> sleutelwaardeparen</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">De sleutel is een constante die een gegevensset definieert (bijvoorbeeld geslacht, kleur, prijs). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">De waarde is een variabele die gerelateerd is aan de constante (bijvoorbeeld mannelijk/vrouwelijk, groen, 100). </li> 
    </ul> <p>Vergelijkingsoperatoren voegen zich bij het sleutelwaardepaar en stellen de relatie tussen deze operatoren in. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trait</b> </td> 
   <td colname="col2"> <p>Combinaties van een of meer signalen. </p> <p>Met Booleaanse expressies en vergelijkingsoperatoren kunt u kwalificatieregels voor eigenschappen maken. </p> <p>Maak nauwkeurige kwalificatievereisten met combinaties van kenmerken en groepen eigenschappen. </p> </td> 
   <td colname="col3"> <p>Aan de hand van de beschikbare signalen kunt u een regel maken voor een "High End Camera Browser", uitgedrukt als: </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segment</b> </td> 
   <td colname="col2"> <p>Gebruikers die een set gemeenschappelijke kenmerken delen en in aanmerking komen voor verwante kenmerken. </p> <p>Met Booleaanse expressies kunt u samen met de vereisten voor recentie/frequentie, kwalificatieregels voor segmenten maken. </p> <p>Maak nauwkeurige kwalificatievereisten met combinaties van kenmerk- en segmentregels. </p> </td> 
   <td colname="col3"> <p>Van de beschikbare eigenschappen en de signalen, kon u een segmentregel tot stand brengen die als wordt uitgedrukt: </p> <p><code> (product=camera AND type=digital SLR) OR (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Gebruik het diagram hieronder om een mentale nota van het verband tussen signalen, eigenschappen, en segmenten te houden.

![](assets/signals-traits-segments.png)

**Bouw Lijsten en de Regels van het Segment met Visuele Hulpmiddelen en de Redacteurs van de Code**

Clients beheren traits en segmenten met visuele gereedschappen en code-editors in de [!DNL Audience Manager] gebruikersinterface. Met de visuele gereedschappen kunt u regels maken met behulp van zoekfuncties, pop-upopties, vervolgkeuzemenu&#39;s en functionaliteit voor slepen en neerzetten. De codeeditors verstrekken geavanceerde gebruikers van een manier om publiekssegmenteringscriteria programmatically te ontwikkelen.

**Gebeurtenisaanroepen verzenden gegevens naar Audience Manager**

Een gebeurtenisaanroep verzendt gegevens van uw website naar [!DNL Audience Manager]. De vraag bevat signaal, eigenschap, en segmentgegevens in een [!DNL HTTP] verzoek. De gebeurtenis zelf is alles na het `/event` deel van een [!DNL URL] tekenreeks. Zoals in het onderstaande voorbeeld wordt getoond, is voor dit proces slechts één gebeurtenisaanroep nodig om meerdere variabelen door te geven aan [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenten: Doel, samenstelling en regels](../features/segments/segments-purpose.md)

