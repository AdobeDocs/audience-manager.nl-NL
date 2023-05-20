---
description: In dit artikel worden de voorvoegsels beschreven die u aan belangrijke variabelen moet koppelen bij het maken van regels voor kenmerken.
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: Voorvoegselvereisten voor belangrijke variabelen
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 4%

---

# Voorvoegselvereisten voor belangrijke variabelen {#prefix-requirements-for-key-variables}

In dit artikel worden de voorvoegsels beschreven die u aan belangrijke variabelen moet koppelen bij het maken van regels voor kenmerken.

<!-- r_tb_variable_prefixes.xml -->

## Doel van voorvoegsels van hoofdvariabelen

Wanneer u [!UICONTROL Trait Builder] regels, is het belangrijk om de zeer belangrijke variabele met een geadviseerd voorvoegsel voor te bereiden. Deze voorvoegsels identificeren het type gegevens dat wordt doorgegeven en voorkomen naamruimteconflicten binnen [!DNL Audience Manager]. Over het algemeen, kunt u een variabele om het even welke naam geven, maar de gegevens voor een regel zullen niet verwerken als de zeer belangrijke veranderlijke naam niet de veranderlijke naam in een gebeurtenisvraag aanpast.

## Voorvoegsels voor hoofdvariabelen

In de volgende tabel worden de algemene voorvoegsels gedefinieerd die worden gebruikt door [!UICONTROL Trait Builder].

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
   <td colname="col2"> <p>Bij de <span class="keyword"> Audience Manager</span> niveau. Deze gegevens zijn overal gelijk <span class="keyword"> Audience Manager</span> ecosysteem. Zie <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Ondersteunde kenmerken voor DCS API-aanroepen</a> voor een vollediger lijst.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Dat bevat <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP-header</a> informatie. Omvat kopbalparameters zoals <code> referer</code>,<code> IP</code>, <code> accept-language</code>, enz. </p> <p> <p>Opmerking: Voor klanten die versies van DIL ouder dan 9.0 gebruiken, gegevensinzameling gebruikend <code> h_referer</code> Het signaal werkt niet in Safari-browsers. Met de invoering van <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>In Safari kunnen browsers het domein demdex.net als een tracker classificeren en wordt de referentie op het verzoek om gegevensverzameling afgebroken, zodat alleen de oorsprong in plaats van de volledige URL wordt opgenomen. Zie <a href="../../dil/dil-overview.md#get-implement-dil-code">DIL-code ophalen en implementeren</a> voor de nieuwste versie van DIL.<p>Signalen met dit voorvoegsel worden niet weergegeven in <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signaalzoekopdracht</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Ons <span class="wintitle"> Gegevensverzamelingsservers</span> doorgeven van parameters van het type private toestaan. Elke parameter die begint met <code> p_</code> wordt gebruikt voor keurmerken, maar het zal niet stroomafwaarts worden geregistreerd, noch worden opgeslagen. </p> <p>Voorbeeld: gegeven <code> /event?p_age=23</code> en een soort eigenschap <code> YoungPeople = p_age &lt; 25</code>, zal de eigenschap worden gerealiseerd, maar <code> p_age=23</code> key-value paar zal na het verzoek worden gelaten vallen en zal niet worden geregistreerd. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Basisinformatie - overzicht](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Eigenschapregels beheren](../../features/traits/manage-trait-rules.md#managing-trait-rules)

