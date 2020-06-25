---
description: In dit artikel wordt uitgelegd hoe de kenmerken en segmentgereedschappen van de Audience Manager de Booleaanse expressies AND, OR en NOT gebruiken.
seo-description: In dit artikel wordt uitgelegd hoe de kenmerken en segmentgereedschappen van de Audience Manager de Booleaanse expressies AND, OR en NOT gebruiken.
seo-title: Booleaanse expressies in Trait and Segment Builder
solution: Audience Manager
title: Booleaanse expressies in Trait and Segment Builder
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---


# Booleaanse expressies in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

In dit artikel wordt uitgelegd hoe de kenmerken en segmentgereedschappen van de Audience Manager de Booleaanse expressies AND, OR en NOT gebruiken.

<!-- 

c_tb_boolean.xml

 -->

**Booleaanse expressies**

Booleaanse logica is een vertakking van algebra die enkele basisexpressies (of operatoren) gebruikt om te bepalen of een instructie waar of onwaar is. De meest voorkomende operatoren zijn [!UICONTROL AND], [!UICONTROL OR]en [!UICONTROL NOT]. Met combinaties van deze expressies kunt u speciale kenmerken of segmentkwalificatieregels maken die uniek zijn voor uw gegevensvereisten. In de volgende afbeelding ziet u hoe basis-Booleaanse expressies werken.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>De [!UICONTROL NOT] operator gebruikt een impliciete &quot;en&quot;-voorwaarde en wordt soms geschreven als [!UICONTROL AND NOT].

**Hoe te om Uitdrukkingen Van Boole in Trait en de Bouwer van het Segment te gebruiken**

U bouwt eigenschap en segmentkwalificatieregels met uitdrukkingen Van Boole. In de onderstaande tabel worden algemene aanbevolen procedures beschreven voor het maken van kwalificatiecriteria met [!UICONTROL AND], [!UICONTROL OR]en [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Uitdrukking </th> 
   <th colname="col2" class="entry"> Het gebruiken om te creëren </th> 
   <th colname="col3" class="entry"> Om in aanmerking te komen </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> EN</span></b> </p> </td> 
   <td colname="col2"> <p>Smalle, gerichte vereisten voor publiekskwalificatie. </p> </td> 
   <td colname="col3"> <p>Gebruikers <i>moeten</i> tot alle opgegeven kenmerken of segmenten behoren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OF</span></b> </p> </td> 
   <td colname="col2"> <p>Brede, minder gerichte vereisten voor publiekskwalificatie. </p> </td> 
   <td colname="col3"> <p>De gebruikers <i>kunnen</i> tot om het even welke gespecificeerde eigenschappen of segmenten behoren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>Smalle, gerichte vereisten voor publiekskwalificatie. </p> <p>Nuttig wanneer er meerdere voorwaarden zijn die het definiëren van kwalificatievereisten voor het publiek moeilijk of inefficiënt maken. Soms is het gemakkelijker om te valideren aan de hand van vereisten die u wilt uitsluiten in plaats van opnemen. </p> </td> 
   <td colname="col3"> <p>Gebruikers <i>mogen niet</i> tot een uitgesloten kenmerk of segment behoren. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Voorbeeld van hoofdletters/kleine letters gebruiken **

De [!UICONTROL AND] operator is handig wanneer u eenvoudig hebt aangegeven aan welke vereisten voor standaardlidmaatschap is voldaan. Stel dat u een publiek moet maken van &#39;dure camerakoppen&#39;. Met een pixelmodel moet u pixels voor camera&#39;s en een numerieke prijswaarde op de pagina maken en plaatsen. Met andere kenmerken kunt u daarentegen Booleaanse operatoren toepassen om beide voorwaarden ( [!UICONTROL AND] prijs camera&#39;s) af te handelen. Het resultaat is efficiënte gegevensinzameling met minder vraag van HTTP, die, beurtelings, de gebruikerservaring op uw plaats helpt bewaren.

**[!UICONTROL OR]Voorbeeld van hoofdletters/kleine letters gebruiken **

De [!UICONTROL OR] operator is handig wanneer u signalen wilt maken met uitgebreide kwalificatievereisten voor het publiek. Als u verschillende kwalificatievereisten voor kenmerken of segmenten hebt, evalueert de [!UICONTROL OR] operator true wanneer bezoekers van de site *een* van deze kenmerken vertonen. [!UICONTROL OR] Dit kan handig zijn wanneer u snel een breed publiek van gekwalificeerde bezoekers wilt maken.

**[!UICONTROL AND NOT]Voorbeeld van hoofdletters/kleine letters gebruiken **

De [!UICONTROL AND NOT] operator is handig wanneer u een publiek makkelijker kunt definiëren door *uitsluiting* in plaats van *opname*. Bijvoorbeeld, zeg u een verkoop hebt en bezoekers in klanten willen segmenteren die volledige prijspunten slechts bekijken. In plaats van een lijst met signalen te maken voor alle in aanmerking komende items tegen volledige prijs of verkoopprijs, is het misschien eenvoudiger om bezoekers in aanmerking te nemen als ze *geen* koopprijsobject hebben gezien. Dit is administratief efficiënt, omdat je doorgaans minder objecten tegen de verkoopprijs hebt dan die voor de volledige prijs. Met een Booleaanse waarde [!UICONTROL NOT], *mogen bezoekers het verkoopsignaal niet* weergeven om in aanmerking te komen voor een lidmaatschap voor een publiek met een volledige prijs. Daarentegen [!UICONTROL AND NOT] is dit het tegenovergestelde van het [!UICONTROL AND] gebruiksgeval, waaruit blijkt hoe het lidmaatschap van het publiek wordt bepaald door inclusie (de bezoeker heeft dus een kwalificatie op basis van twee expliciet vermelde signalen).

>[!MORELIKETHIS]
>
>* [Werken met vergelijkingsoperatoren in TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Orde van Verrichtingen in Uitdrukkingen TraitBuilder](../features/traits/trait-operator-precedence.md)

