---
description: In dit artikel worden de voorvoegsels beschreven die u aan belangrijke variabelen moet koppelen bij het maken van regels voor kenmerken.
seo-description: In dit artikel worden de voorvoegsels beschreven die u aan belangrijke variabelen moet koppelen bij het maken van regels voor kenmerken.
seo-title: Voorvoegselvereisten voor belangrijke variabelen
solution: Audience Manager
title: Voorvoegselvereisten voor belangrijke variabelen
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
translation-type: tm+mt
source-git-commit: 1c0d40082cd0753a9b4326aae764eb74aefb8be4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 5%

---


# Voorvoegselvereisten voor belangrijke variabelen {#prefix-requirements-for-key-variables}

In dit artikel worden de voorvoegsels beschreven die u aan belangrijke variabelen moet koppelen bij het maken van regels voor kenmerken.

<!-- r_tb_variable_prefixes.xml -->

## Doel van voorvoegsels van hoofdvariabelen

Wanneer u [!UICONTROL Trait Builder] regels creeert, is het belangrijk om de zeer belangrijke variabele met een geadviseerd voorvoegsel voor te bereiden. Deze voorvoegsels identificeren het type gegevens dat wordt doorgegeven en helpen naamruimteconflicten binnen [!DNL Audience Manager] te voorkomen. Over het algemeen, kunt u een variabele om het even welke naam geven, maar de gegevens voor een regel zullen niet verwerken als de zeer belangrijke veranderlijke naam niet de veranderlijke naam in een gebeurtenisvraag aanpast.

## Voorvoegsels voor hoofdvariabelen

In de volgende tabel worden de algemene voorvoegsels gedefinieerd die door [!UICONTROL Trait Builder] worden gebruikt.

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Voorvoegsel van de toetsvariabele </th> 
   <th colname="col2" class="entry"> Identificeert de variabele </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>Als klantspecifiek. Dit zijn sleutelgegevens die vanuit uw eigen eigenschappen worden verzonden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>Op het niveau <span class="keyword"> Audience Manager</span>. Deze gegevens zijn uniform over het <span class="keyword"> ecosysteem </span>. Zie <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Gesteunde Attributen voor Vraag DCS API</a> voor een volledigere lijst.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Dat bevat <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP header</a> informatie. Omvat kopbalparameters zoals <code> referer</code>,<code> IP</code>, <code> accept-language</code>, enz. </p> <p> <p>Opmerking: Voor klanten die DIL-versies ouder dan 9.0 gebruiken, werkt gegevensverzameling met het <code> h_referer</code>-signaal niet in Safari-browsers. Met de introductie van <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, kunnen de browsers Safari het domein demdex.net als trekker classificeren en zullen de verwijzer op het verzoek van de gegevensinzameling bekorten om slechts de oorsprong in plaats van volledige URL te bevatten. Zie <a href="../../dil/dil-overview.md#get-implement-dil-code">DIL Code ophalen en implementeren</a> voor de nieuwste versie van DIL.<p>Signalen die dit voorvoegsel gebruiken, worden niet weergegeven in <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signaal zoeken</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Onze <span class="wintitle"> Servers voor gegevensverzameling</span> staan het doorgeven van persoonlijke parameters toe. In principe wordt elke parameter die begint met <code> p_</code> gebruikt voor de evaluatie van het kenmerk, maar deze wordt niet verderop in het logboek opgenomen en wordt ook niet opgeslagen. </p> <p>Voorbeeld: op basis van <code> /event?p_age=23</code> en een eigenschap als <code> YoungPeople = p_age &lt; 25</code> wordt het kenmerk gerealiseerd, maar het sleutelwaardepaar <code> p_age=23</code> wordt na het verzoek verwijderd en wordt niet vastgelegd. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Basisinformatie - overzicht](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Eigenschapregels beheren](../../features/traits/manage-trait-rules.md#managing-trait-rules)

