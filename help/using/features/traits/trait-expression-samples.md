---
description: De voorbeelden u kunt naar voor het creëren van uitdrukkingen in de de coderedacteur van de Bouwer van de Uitdrukking verwijzen.
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: Voorbeeldexpressies met booleaanse en vergelijkingsoperatoren
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 7%

---

# Voorbeeldexpressies met booleaanse en vergelijkingsoperatoren {#sample-expressions-with-boolean-and-comparison-operators}

Voorbeelden waarnaar u kunt verwijzen voor het maken van expressies in het dialoogvenster [!UICONTROL Expression Builder] code-editor.

## Overzicht van codevoorbeelden {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Maak uw eigen regels voor kenmerken met de [!UICONTROL Expression Builder] code-editor. De volgende voorbeelden kunnen u helpen om aan de slag te gaan. Sommige voorbeelden geven de voorkeur aan *`key`* variabele met `c_` om het als user-defined variabele te identificeren. Inclusief de `c_` voorvoegsel (of een andere naamgevingsconventie) voor *`key`* variabele als uw gebeurtenisaanroepen gegevens verzenden naar [!DNL Audience Manager] die syntaxis gebruiken.

## Booleaanse expressies {#boolean-expressions}

### AND-voorbeeld

De regel stelt kwalificatievereisten vast met behulp van Boolean [!UICONTROL AND] operatoren.

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

Deze regel stelt vereisten inzake beroepskwalificaties vast met behulp van [!DNL Boolean] [!UICONTROL OR] en [!UICONTROL AND] operatoren.

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
   <td colname="col2"> Voldoen aan de voorwaarden die zijn ingesteld door variabelen <code><i>a </i></code> of <code><i>b </i></code> en <code><i>c </i></code>. </td> 
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
