---
description: De voorbeelden u kunt naar voor het creëren van uitdrukkingen in de de coderedacteur van de Bouwer van de Uitdrukking verwijzen.
seo-description: De voorbeelden u kunt naar voor het creëren van uitdrukkingen in de de coderedacteur van de Bouwer van de Uitdrukking verwijzen.
seo-title: Voorbeeldexpressies met booleaanse en vergelijkingsoperatoren
solution: Audience Manager
title: Voorbeeldexpressies met booleaanse en vergelijkingsoperatoren
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 9%

---


# Voorbeeldexpressies met booleaanse en vergelijkingsoperatoren {#sample-expressions-with-boolean-and-comparison-operators}

Voorbeelden waarnaar u kunt verwijzen voor het maken van expressies in de [!UICONTROL Expression Builder] code-editor.

## Overzicht van codevoorbeelden {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Maak uw eigen regels voor het kenmerk met de [!UICONTROL Expression Builder] code-editor. De volgende voorbeelden kunnen u helpen om aan de slag te gaan. Sommige voorbeelden geven de voorkeur aan de *`key`* variabele `c_` om deze te identificeren als een door de gebruiker gedefinieerde variabele. Neem het `c_` voorvoegsel (of een andere naamgevingsconventie) voor de *`key`* variabele op als uw gebeurtenisaanroepen gegevens naar [!DNL Audience Manager] die syntaxis verzenden.

## Booleaanse expressies {#boolean-expressions}

### AND-voorbeeld

De regel stelt kwalificatievereisten vast met behulp van Booleaanse [!UICONTROL AND] operatoren.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Voorbeeldcode </th> 
   <th colname="col2" class="entry"> Om in aanmerking te komen, moet een bezoeker </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Zoek naar een specifiek merk en model. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Zoek het product op een pagina met zoekresultaten (zoek = "1" of "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### OR-voorbeeld

Deze regel stelt eisen inzake beroepskwalificatie vast die [!DNL Boolean] en [!UICONTROL OR] [!UICONTROL AND] exploitanten gebruiken.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Voorbeeldcode </th> 
   <th colname="col2" class="entry"> Om in aanmerking te komen, moet een bezoeker </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> Voldoet aan de voorwaarden die door variabelen <code><i>a </i></code> of <code><i>b </i></code> en <code><i>c </i></code>worden bepaald. </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeeld van bereik met groter dan, kleiner dan, gelijk aan

Met deze regel worden kwalificatievereisten voor het kenmerk vastgelegd met behulp van een bereik.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Voorbeeldcode </th> 
   <th colname="col2" class="entry"> Om in aanmerking te komen, moet een bezoeker </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> Voldoe aan elke prijsvoorwaarde tussen 1.00 en 100.00 uur. </td> 
  </tr> 
 </tbody> 
</table>