---
description: Beschrijft opstellingsstappen en eigenschappen specifiek voor het op regel-gebaseerde en ongebogen proces van de de eigenaarverwezenlijking.
keywords: create trait;create traits
seo-description: Beschrijft opstellingsstappen en eigenschappen specifiek voor het op regel-gebaseerde en ongebogen proces van de de eigenaarverwezenlijking.
seo-title: Op regels gebaseerde of niet-gecodeerde traits maken
solution: Audience Manager
title: Op regels gebaseerde of niet-gecodeerde traits maken
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Op regels gebaseerde of niet-gecodeerde traits maken {#create-rules-based-or-onboarded-traits}

Beschrijft opstellingsstappen en eigenschappen specifiek voor het proces van de [!UICONTROL rules-based] en [!UICONTROL onboarded] eigenschap verwezenlijking.

<!-- c_tb_rules_traits.xml -->

## Basisinformatie over sporen {#basics}

Met [!UICONTROL Trait Builder]de [!UICONTROL Basic Information] instellingen kunt u nieuwe kenmerken maken of bestaande kenmerken bewerken. De [!UICONTROL Basic Information] instellingen zijn gelijk voor op regels gebaseerde, niet-geregistreerde en algoritmische kenmerken. Als u een nieuwe eigenschap wilt maken, geeft u een naam (geen speciale tekens), een gegevensbron en selecteert u een opslagmap. Andere [!UICONTROL Basic Information] velden zijn optioneel.

<!-- c_tb_basics.xml -->

![creëren-eigenschap](assets/create-trait.png)

### Standaardinformatievelden gedefinieerd

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Interface-element </th> 
   <th colname="col2" class="entry"> Toelichting </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Naam</span></b> </td> 
   <td colname="col2"> <p>De naam van de eigenschap. Vereist. </p> <p>Maximumlengte: 255 tekens. </p> <p> <p>Opmerking: Vermijd deze speciale tekens bij het benoemen van kenmerken: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Kommels </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Streepjes </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Afbreekstreepjes </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Tabs </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Verticale balk of buissymbool </li> 
      </ul> </p> </p> <p>Hierdoor worden verwerkingsfouten verminderd wanneer u een <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> binnenkomende gegevensbestandsoverdracht</a>instelt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Beschrijving</span></b> </td> 
   <td colname="col2"> Een paar woorden om het doel of de functie van de eigenschap te beschrijven. Optioneel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Gegevensbron</span></b> </td> 
   <td colname="col2"> Koppelt de eigenschap aan een specifieke gegevensaanbieder. Vereist. <p>Gebruik het eerste vervolgkeuzemenu om te filteren tussen de gegevensbronnen van Audience Manager, Adobe Analytics-rapportreeksen of beide. Kies vervolgens de gegevensbron in het tweede keuzemenu.</p><p> Als u geen Adobe Analytics-rapportreeksen gebruikt, is de gegevensbrontypekiezer uitgeschakeld en standaard alleen ingesteld op Audience Manager-gegevensbronnen.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Type gebeurtenis</span></b> </td> 
   <td colname="col2"> Wijst de eigenschap aan een type of een categorie toe, gewoonlijk volgens functie (b.v. omzetting, plaatsbezoeker, partner, paginamening, enz.). Optioneel. <p> Meer informatie over het maken van conversiekenmerken vindt u in de video <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Conversietaken</a>maken in Audience Manager. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Integratiecode</span></b> </td> 
   <td colname="col2"> Een gebied voor identiteitskaart, SKU, of andere waarde die door uw interne bedrijfsprocessen wordt gebruikt. Optioneel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Opmerkingen</span></b> </td> 
   <td colname="col2"> Algemene opmerkingen over een eigenschap. Optioneel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Opslaan in</span></b> </td> 
   <td colname="col2"> Hiermee bepaalt u tot welke opslagmap de eigenschap behoort. Vereist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Gegevenscategorie</span></b> </td> 
   <td colname="col2"> Classificeert kenmerken volgens algemeen begrepen categorieën. <p>Opmerking:  Treinen behoren slechts tot één categorie. Optioneel. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Een interval voor verlopen van sporen instellen {#set-expiration-interval}

In [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] laat u een tijd-aan-levende ([!DNL TTL]) interval voor een eigenschap plaatsen. [!DNL TTL] bepaalt hoeveel dagen een gekwalificeerde bezoeker in een eigenschap blijft (120 dagen is standaard). Wanneer ingesteld op 0, verloopt het standaardlidmaatschap nooit.

<!-- t_tb_ttl.xml -->

### TTL instellen voor een kenmerk

1. Vouw de [!UICONTROL Advanced Options] sectie uit en voer een getal in om een [!DNL TTL] waarde voor de eigenschap in te stellen.
1. Klik op **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Tijd van segment voor live uitleg](../../features/traits/segment-ttl-explained.md)

