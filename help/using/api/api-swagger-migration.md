---
description: Hier in Audience Manager zijn we ingenieurs, ontwikkelaars en code-negatieven, net als jij. Net als u willen we werken met betrouwbare, nauwkeurige API-documentatie. Hierdoor schrijven we onze API-inhoud opnieuw in Swagger en verplaatsen we deze naar een nieuwe locatie. Deze wijzigingen zijn ontworpen om uw ervaring met de Audience Manager API-code te verbeteren.
seo-description: Here at Audience Manager, we're engineers, developers, and code ninjas just like you. And, like you, we want to work with reliable, accurate API documentation. As a result, we're re-writing our API content in Swagger and moving it to a new location. These changes are designed to help improve your experience with the Audience Manager API code.
seo-title: Audience Manager API Code Migration
solution: Audience Manager
title: Migratie van Audience Manager API-code
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
feature: API
exl-id: 081be8a7-5029-45b1-8fb1-0531d5090fe0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 1%

---

# Migratie van Audience Manager API-code {#audience-manager-api-code-migration}

Hier in Audience Manager zijn we ingenieurs, ontwikkelaars en code-negatieven, net als jij. Net als u willen we werken met betrouwbare, nauwkeurige [!DNL API] documentatie. Hierdoor schrijven we onze [!DNL API] -inhoud opnieuw in [!DNL Swagger] en verplaatsen we deze naar een nieuwe locatie. Deze wijzigingen zijn ontworpen om uw ervaring met de Audience Manager [!DNL API] -code te verbeteren.

## Omhoog verplaatsen {#code-migration-details}

<!-- api-swagger-migration.xml -->

De [&#x200B; Adobe Audience Manager API DOS &#x200B;](https://bank.demdex.com/portal/swagger/index.html) plaats is het nieuwe huis voor onze herziene [!DNL API] inhoud. We proberen bij elke release een aantal sets [!DNL API] -methoden opnieuw te schrijven en te verplaatsen. Dit betekent u zowel de nieuwe plaats als de [&#x200B; REST API &#x200B;](../api/rest-api-main/rest-api-main.md) documentatie zult moeten inchecken om alle beschikbare methodes te vinden. Uiteindelijk bevinden alle openbare [!DNL API] s zich op de documentsite [!DNL Audience Manager] [!DNL API] . De volgende lijst maakt een lijst van gereviseerde en gemigreerde [!DNL API] s.

<!--

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API Type </th> 
   <th colname="col2" class="entry"> API Methods </th> 
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
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Data Feeds</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Data Feed Request</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Data Feed Finance</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Data Feed Plans</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Data Feed Subscriptions</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Data Source</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Data Sources</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Derived Signals</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Derived Signals</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Folders</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Segment Folders</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Trait Folders</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Reporting</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Reporting</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segments</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segments</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Segment Test Groups</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> Segment Test Group Draft API</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Traits</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Traits</a> </p> </td> 
  </tr>
 </tbody>
</table>

-->


| API-type | API-methoden |
|---------|----------|
| **[!UICONTROL Algorithmic Models**] | [Algorithmic Models](https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API) |
| **[!UICONTROL Audience Marketplace]** | <ul><li>[&#x200B; De Eigen Gegevens &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/get_available_data_feeds_)</li><li>[&#x200B; Verzoek van het Doorvoer van Gegevens &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/post_available_data_feeds__dataSourceId__requests)</li><li>[&#x200B; de Financiën van het voer van Gegevens &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Finance%20API/get_data_feeds_billing_report)</li><li>[&#x200B; de Plannen van het voer van Gegevens &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__plans_)</li><li>[&#x200B; het Gegeven Abonnementen van Gegevens &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__subscriptions)</li></ul> |
| **[!UICONTROL Data Sources]** | [&#x200B; Gegevensbronnen &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Data_Source_API) |
| **[!UICONTROL Folders]** | <ul><li>[&#x200B; Omslagen van het Segment &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Segment_Folder_API)</li><li>[&#x200B; de Omslagen van het Spoor &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Trait%20Folder%20API)</li></ul> |
| **[!UICONTROL Reporting]** | [Rapportage](https://bank.demdex.com/portal/swagger/index.html#/Reporting%20API) |
| **[!UICONTROL Segments]** | <ul><li>[&#x200B; Segmenten &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Segments%20API)</li><li>[&#x200B; Groepen van de Test van het Segment &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API)</li><li>[&#x200B; Concept API van de Groep van de Test van het Segment &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API/post_segment_test_groups_drafts)</li></ul> |
| **[!UICONTROL Traits]** | [&#x200B; Tanden &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Traits%20API) |
