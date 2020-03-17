---
description: Hier bij Audience Manager zijn wij ingenieurs, ontwikkelaars, en code-negatieven, net als u. Net als u willen we werken met betrouwbare, nauwkeurige API-documentatie. Hierdoor schrijven we onze API-inhoud opnieuw in Swagger en verplaatsen we deze naar een nieuwe locatie. Deze wijzigingen zijn ontworpen om uw ervaring met de API-code van Audience Manager te verbeteren.
seo-description: Hier bij Audience Manager zijn wij ingenieurs, ontwikkelaars, en code-negatieven, net als u. Net als u willen we werken met betrouwbare, nauwkeurige API-documentatie. Hierdoor schrijven we onze API-inhoud opnieuw in Swagger en verplaatsen we deze naar een nieuwe locatie. Deze wijzigingen zijn ontworpen om uw ervaring met de API-code van Audience Manager te verbeteren.
seo-title: Auditiebeheer API-codemigratie
solution: Audience Manager
title: Auditiebeheer API-codemigratie
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# Auditiebeheer API-codemigratie {#audience-manager-api-code-migration}

Hier bij Audience Manager zijn wij ingenieurs, ontwikkelaars, en code-negatieven, net als u. Net als u willen we werken met betrouwbare, nauwkeurige [!DNL API] documentatie. Als gevolg hiervan schrijven we onze [!DNL API] inhoud opnieuw in [!DNL Swagger] en verplaatsen deze naar een nieuwe locatie. Deze wijzigingen zijn ontworpen om uw ervaring met de [!DNL API] code Audience Manager te verbeteren.

## Omhoog verplaatsen {#code-migration-details}

<!-- api-swagger-migration.xml -->

De [Adobe Audience Manager API Docs](https://bank.demdex.com/portal/swagger/index.html) -site is de nieuwe website voor onze herziene [!DNL API] inhoud. We proberen bij elke release een aantal sets [!DNL API] methoden opnieuw te schrijven en te verplaatsen. Dit betekent dat u zowel de nieuwe locatie als de [REST API](../api/rest-api-main/rest-api-main.md) -documentatie moet inchecken om alle beschikbare methoden te vinden. Uiteindelijk, zullen alle openbare [!DNL API]s op de [!DNL Audience Manager] [!DNL API] documentenplaats zijn. In de volgende tabel worden de gereviseerde en gemigreerde [!DNL API]bestanden weergegeven.

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API-type </th> 
   <th colname="col2" class="entry"> API-methoden </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Algorithmic Models</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Algorithmic Models</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Gegevensfeeds</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Verzoek gegevensdoorvoer</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Gegevensfeed-financiering</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Gegevensvoederplannen</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Abonnementen gegevensfeed</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Gegevensbron</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Gegevensbronnen</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Afgeleide signalen</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Afgeleide signalen</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Mappen</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Segmentmappen</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Mappen overtrekken</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Rapportage</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Rapportage</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmenten</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segmenten</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Segmenttestgroepen</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> Concept-API voor segmenttestgroep</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Treinen</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Treinen</a> </p> </td> 
  </tr>
 </tbody>
</table>