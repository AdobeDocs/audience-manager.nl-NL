---
description: In dit artikel worden de voorvoegsels beschreven die u aan belangrijke variabelen moet koppelen bij het maken van regels voor kenmerken.
seo-description: In dit artikel worden de voorvoegsels beschreven die u aan belangrijke variabelen moet koppelen bij het maken van regels voor kenmerken.
seo-title: Voorvoegselvereisten voor belangrijkste variabelen
solution: Audience Manager
title: Voorvoegselvereisten voor belangrijkste variabelen
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---


# Voorvoegselvereisten voor belangrijkste variabelen {#prefix-requirements-for-key-variables}

In dit artikel worden de voorvoegsels beschreven die u aan belangrijke variabelen moet koppelen bij het maken van regels voor kenmerken.

<!-- r_tb_variable_prefixes.xml -->

## Doel van voorvoegsels van hoofdvariabelen

Wanneer u [!UICONTROL Trait Builder] regels maakt, is het belangrijk dat u een voorvoegsel aan de hoofdvariabele toevoegt. Deze voorvoegsels identificeren het type gegevens dat wordt doorgegeven en helpen naamruimteconflicten binnen te voorkomen [!DNL Audience Manager]. Over het algemeen, kunt u een variabele om het even welke naam geven, maar de gegevens voor een regel zullen niet verwerken als de zeer belangrijke veranderlijke naam niet de veranderlijke naam in een gebeurtenisvraag aanpast.

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
   <td colname="col2"> <p>Op het niveau van de <span class="keyword"> Audience Manager</span> . Deze gegevens zijn uniform in het ecosysteem van de <span class="keyword"> Audience Manager</span> . Zie <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Gesteunde Attributen voor Vraag</a> DCS API voor een volledigere lijst. <p>Signalen die dit voorvoegsel gebruiken, worden niet weergegeven in <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signaal zoeken</a>.</p></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Dat bevat <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP-headerinformatie</a> . Omvat kopbalparameters zoals <code> referer</code>,<code> IP</code>, <code> accept-language</code>enz. </p> <p> <p>Opmerking: Voor klanten die DIL-versies ouder dan 9.0 gebruiken, werkt gegevensverzameling met behulp van het <code> h_referer</code> signaal niet in Safari-browsers. Met de introductie van <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, kunnen de browsers Safari het domein demdex.net als trekker classificeren en zullen de verwijzer op het verzoek van de gegevensinzameling bekorten om slechts de oorsprong in plaats van volledige URL te bevatten. Zie <a href="../../dil/dil-overview.md#get-implement-dil-code">De DIL-code</a> ophalen en implementeren voor de nieuwste DIL-versie.<p>Signalen die dit voorvoegsel gebruiken, worden niet weergegeven in <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signaal zoeken</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Onze servers <span class="wintitle"> van de</span> Gegevensverzameling staan het overgaan van privé parameters toe. In feite, zal om het even welke parameter die met begint <code> p_</code> worden gebruikt voor keurmerking, maar het zal niet stroomafwaarts worden geregistreerd, noch worden opgeslagen. </p> <p>Voorbeeld: gegeven <code> /event?p_age=23</code> en een eigenschap als <code> YoungPeople = p_age &lt; 25</code>, zal het bezit worden gerealiseerd, maar het <code> p_age=23</code> zeer belangrijk-waardepaar zal na het verzoek worden gelaten vallen en zal niet worden geregistreerd. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Basisinformatie - overzicht](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Trait-regels beheren](../../features/traits/manage-trait-rules.md#managing-trait-rules)

