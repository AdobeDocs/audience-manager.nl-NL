---
description: In dit artikel wordt uitgelegd hoe de kenmerken en segmentgereedschappen van Audience Manager de Booleaanse expressies AND, OR en NOT gebruiken.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: Booleaanse expressies in Trait and Segment Builder
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Booleaanse expressies in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

In dit artikel wordt uitgelegd hoe de kenmerken en segmentgereedschappen van Audience Manager de Booleaanse expressies AND, OR en NOT gebruiken.

<!-- 

c_tb_boolean.xml

 -->

**Uitdrukkingen Van Boole**

Booleaanse logica is een vertakking van algebra die enkele basisexpressies (of operatoren) gebruikt om te bepalen of een instructie waar of onwaar is. De meest gebruikte operatoren zijn [!UICONTROL AND] , [!UICONTROL OR] en [!UICONTROL NOT] . Met combinaties van deze expressies kunt u speciale kenmerken of segmentkwalificatieregels maken die uniek zijn voor uw gegevensvereisten. In de volgende afbeelding ziet u hoe basis-Booleaanse expressies werken.

<br>

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>De operator [!UICONTROL NOT] gebruikt een geïmpliceerde voorwaarde &quot;en&quot; en wordt soms geschreven als [!UICONTROL AND NOT] .

**hoe te om de Uitdrukkingen Van Boole in de Bouwer van het Spoor en van het Segment te gebruiken**

U bouwt eigenschap en segmentkwalificatieregels met uitdrukkingen Van Boole. In de onderstaande tabel worden algemene aanbevolen procedures beschreven voor het maken van kwalificatiecriteria met [!UICONTROL AND] , [!UICONTROL OR] en [!UICONTROL NOT] .

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Uitdrukking </th> 
   <th colname="col2" class="entry"> Het gebruiken om te creëren </th> 
   <th colname="col3" class="entry"> In aanmerking komen </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> AND </span></b> </p> </td> 
   <td colname="col2"> <p>Smalle, gerichte vereisten voor publiekskwalificatie. </p> </td> 
   <td colname="col3"> <p>De gebruikers <i> moeten </i> tot alle gespecificeerde eigenschappen of segmenten behoren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR </span></b> </p> </td> 
   <td colname="col2"> <p>Brede, minder gerichte vereisten voor publiekskwalificatie. </p> </td> 
   <td colname="col3"> <p>De gebruikers <i> kunnen </i> tot om het even welke gespecificeerde eigenschappen of segmenten behoren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT </span></b> </p> </td> 
   <td colname="col2"> <p>Smalle, gerichte vereisten voor publiekskwalificatie. </p> <p>Nuttig wanneer er meerdere voorwaarden zijn die het definiëren van kwalificatievereisten voor het publiek moeilijk of inefficiënt maken. Soms is het gemakkelijker om te valideren aan de hand van vereisten die u wilt uitsluiten in plaats van opnemen. </p> </td> 
   <td colname="col3"> <p>De gebruikers <i> moeten niet </i> tot een uitgesloten spoor of een segment behoren. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Voorbeeld van hoofdletters/kleine letters gebruiken**

De operator [!UICONTROL AND] is handig wanneer u eenvoudig vereisten voor standaardlidmaatschap hebt opgesomd. Stel dat u een publiek moet maken van &#39;dure camerakoppen&#39;. Met een pixelmodel moet u pixels voor camera&#39;s en een numerieke prijswaarde op de pagina maken en plaatsen. Met de juiste kenmerken kunt u daarentegen Booleaanse operatoren toepassen om beide voorwaarden (prijs camera&#39;s [!UICONTROL AND] ) af te handelen. Het resultaat is efficiënte gegevensinzameling met minder vraag van HTTP, die, beurtelings, de gebruikerservaring op uw plaats helpt bewaren.

**[!UICONTROL OR]Voorbeeld van hoofdletters/kleine letters gebruiken**

De operator [!UICONTROL OR] is handig wanneer u signalen wilt maken met uitgebreide kwalificatievereisten voor het publiek. Als u verscheidene eigenschap of segmentkwalificatievereisten hebt, zal de [!UICONTROL OR] exploitant aan waar evalueren wanneer uw plaatsbezoekers *om het even welk* van die kenmerken tentoonstellen. [!UICONTROL OR] kan handig zijn als u snel een breed publiek wilt maken met gekwalificeerde sitebezoekers.

**[!UICONTROL AND NOT]Voorbeeld van hoofdletters/kleine letters gebruiken**

De [!UICONTROL AND NOT] exploitant is nuttig wanneer het gemakkelijker is om een publiek door *uitsluiting* eerder dan *opneming* te bepalen. Bijvoorbeeld, zeg u een verkoop hebt en bezoekers in klanten willen segmenteren die volledige prijspunten slechts bekijken. In plaats van een lijst van signalen voor alle kwalificerende volledige of verkoop-prijs punten tot stand te brengen, kan het gemakkelijker zijn om bezoekers te kwalificeren als zij ** geen punt van de verkoopprijs hebben gezien. Dit is administratief efficiënt, omdat je doorgaans minder objecten tegen de verkoopprijs hebt dan die voor de volledige prijs. Met een Booleaanse waarde [!UICONTROL NOT], moeten bezoekers *niet* het verkoopsignaal tonen om voor volwaardig prijslidmaatschap van het publiek in aanmerking te komen. Daarentegen is [!UICONTROL AND NOT] het tegenovergestelde van de [!UICONTROL AND] -use-case, die laat zien hoe het lidmaatschap van het publiek door inclusie wordt bepaald (de bezoeker heeft dus de kwalificatie gebaseerd op twee expliciet vermelde signalen).

>[!MORELIKETHIS]
>
>* [ Werkend met de Exploitanten van de Vergelijking in TraitBuilder ](../features/traits/trait-comparison-operators.md)
>* [ Orde van Verrichtingen in Uitdrukkingen TraitBuilder ](../features/traits/trait-operator-precedence.md)
