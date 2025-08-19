---
description: Beschrijft opstellingsstappen en eigenschappen specifiek voor het op regel-gebaseerde en ongebogen proces van de de eigenaarverwezenlijking.
keywords: eigenschap maken;kenmerken maken
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: Op regels gebaseerde of niet-gecodeerde traits maken
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 1%

---

# Maken [!UICONTROL Rules-Based] of [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Beschrijft instellingsstappen en functies die specifiek zijn voor het maken van [!UICONTROL rules-based] - en [!UICONTROL onboarded] -kenmerken.

<!-- c_tb_rules_traits.xml -->

## Basisinformatie over sporen {#basics}

In [!UICONTROL Trait Builder] kunt u met de [!UICONTROL Basic Information] -instellingen een nieuwe versie maken of bestaande [!UICONTROL traits] bewerken. De instellingen voor [!UICONTROL Basic Information] zijn gelijk voor [!UICONTROL rules-based] , [!UICONTROL onboarded] en [!UICONTROL algorithmic traits] . Als u een nieuwe [!UICONTROL trait] wilt maken, geeft u een naam (geen speciale tekens), een [!UICONTROL data source] en selecteert u een [!UICONTROL storage folder] . Andere [!UICONTROL Basic Information] -velden zijn optioneel.

<!-- c_tb_basics.xml -->

![ creeer-spoor ](assets/create-trait.png)

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
   <td colname="col1"> <b><span class="uicontrol"> Naam </span></b> </td> 
   <td colname="col2"> <p>De naam van de eigenschap. Vereist. </p> <p>Maximale lengte: 255 tekens. </p> <p> <p>Opmerking: gebruik deze speciale tekens bij de naamgeving van kenmerken: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Kommels </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Streepjes </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Afbreekstreepjes </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Tabs </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Verticale balk of buissymbool </li> 
      </ul> </p> </p> <p>Dit helpt verwerkingsfouten te verminderen wanneer u opstelling een <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> binnenkomende gegevensdossieroverdracht </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Beschrijving </span></b> </td> 
   <td colname="col2"> Een paar woorden om het doel of de functie van de eigenschap te beschrijven. Optioneel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Data Source </span></b> </td> 
   <td colname="col2"> Koppelt de eigenschap aan een specifieke gegevensaanbieder. Vereist. <p>Gebruik het eerste vervolgkeuzemenu om te filteren tussen Audience Manager-gegevensbronnen, Adobe Analytics-rapportreeksen of beide. Kies vervolgens de gegevensbron in het tweede keuzemenu.</p><p> Als u geen Adobe Analytics-rapportreeksen gebruikt, is de gegevensbrontypekiezer uitgeschakeld en standaard alleen ingesteld op Audience Manager-gegevensbronnen.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Gebeurtenistype </span></b> </td> 
   <td colname="col2"> Wijst de eigenschap aan een type of een categorie toe, gewoonlijk volgens functie (bijvoorbeeld omzetting, plaatsbezoeker, partner, paginamening, enz.). Optioneel. <p> Leren hoe te om omzettingseigenschappen tot stand te brengen, zie <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html"> Creërend de Tanden van de Omzetting in de video van Audience Manager </a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Integratiecode </span></b> </td> 
   <td colname="col2"> Een gebied voor identiteitskaart, SKU, of andere waarde die door uw interne bedrijfsprocessen wordt gebruikt. Optioneel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Opmerkingen </span></b> </td> 
   <td colname="col2"> Algemene opmerkingen over een eigenschap. Optioneel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Opslaan in </span></b> </td> 
   <td colname="col2"> Hiermee bepaalt u tot welke opslagmap de eigenschap behoort. Vereist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Gegevenscategorie </span></b> </td> 
   <td colname="col2"> Classificeert kenmerken volgens algemeen begrepen categorieën. <p>Opmerking: de treinen behoren slechts tot één categorie. Optioneel. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Een [!UICONTROL Trait] vervalinterval instellen {#set-expiration-interval}

In [!UICONTROL Trait Builder], laat [!UICONTROL Advanced Options] u een tijd-aan-levende ([!DNL TTL]) interval voor een [!UICONTROL trait] plaatsen. [!DNL TTL] definieert hoeveel dagen een gekwalificeerde bezoeker in een [!UICONTROL trait] blijft (standaard is dit 120 dagen). Wanneer u dit op 0 instelt, verloopt het [!UICONTROL trait] -lidmaatschap nooit.

<!-- t_tb_ttl.xml -->

### TTL instellen voor een [!UICONTROL trait]

1. Vouw de sectie [!UICONTROL Advanced Options] uit en voer een getal in om een [!DNL TTL] -waarde voor de sectie [!UICONTROL trait] in te stellen.
1. Klik op **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [ Tijd van het Segment aan Levend Verklaard ](../../features/traits/segment-ttl-explained.md)
