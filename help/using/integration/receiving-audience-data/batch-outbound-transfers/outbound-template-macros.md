---
description: Hiermee geeft u de macro's weer die u kunt gebruiken om uitgaande sjablonen te maken. Dit zijn onder andere bestandsnaammacro's, koptekstmacro's en inhoudmacro's.
seo-description: Hiermee geeft u de macro's weer die u kunt gebruiken om uitgaande sjablonen te maken. Dit zijn onder andere bestandsnaammacro's, koptekstmacro's en inhoudmacro's.
seo-title: Uitgaande sjabloonmacro’s
solution: Audience Manager
title: Uitgaande sjabloonmacro’s
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 2%

---


# Uitgaande sjabloonmacro’s {#outbound-template-macros}

Hiermee geeft u de macro&#39;s weer die u kunt gebruiken om uitgaande sjablonen te maken. Dit zijn onder andere bestandsnaammacro&#39;s, koptekstmacro&#39;s en inhoudmacro&#39;s.

## Bestandsnaam en Koptekstmacro&#39;s {#file-name-header-macros}

De tabel bevat een overzicht en beschrijving van de macro&#39;s die u kunt gebruiken in de bestandsnaam en om koptekstvelden te definiëren. Voor codesteekproeven, zie [Uitgaande MacroVoorbeelden](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>Een niet-afdrukbaar ASCII-teken. Hiermee wordt het begin van een rij of een sectie met inhoud aangegeven. Deze kan ook worden gebruikt om gegevenskolommen in een bestand te scheiden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID gegevensaanbieder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>ID belangrijkste gegevensaanbieder van gebruikersnaam. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> Staat de verwezenlijking van multi-lijnkopballen voor uitgaande orden toe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Volgorde/doel-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>An alias for an order/destination ID. </p> <p>De alias wordt ingesteld in de interface voor beheerders. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Geeft de splitsing van uitgaande bestanden in meerdere onderdelen aan. Vervang de sectie SPLITNUM in de bestandsnaam door het onderdeelnummer, voorafgegaan door nullen, zodat minimaal drie tekens beschikbaar zijn voor de sectie SPLITNUM.</p>
   <p>De SPLITNUM-macro hoeft niet te worden omringd door &lt;&gt;-tekens.</p><p>Voorbeeld: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>De laatste drie cijfers (001.002.003) in de bovenstaande voorbeelden zijn de SPLITNUM-id's.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Geeft het synchronisatietype aan en omvat: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Volledige synchronisatie. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Incrementele synchronisatie. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Geeft de methode voor gegevensoverdracht aan en omvat: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Deze macro wordt gebruikt als scheidingsteken en voegt een tab in tussen velden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Een tijdstempel van 10 cijfers, UTC en Unix. </p> <p>De notatie kan ook worden ingesteld op de volgende indelingsregels voor datum- en tijdstempels van Java. <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> </p> </td> 
  </tr>

</tbody> 
</table>

## Inhoudsmacro&#39;s {#content-macros}

Macro&#39;s die worden gebruikt om de inhoud van een gegevensbestand te formatteren. Voor codesteekproeven, zie [Uitgaande MacroVoorbeelden](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Voegt een haakje sluiten }-teken in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Unieke gebruikersnaam van gegevensaanbieder </span>. </p> <p>Dit is identiteitskaart voor de gegevenspartner u gegevens naar in een uitgaand dossier verzendt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Keert een lijst terug die veelvoudige IDs voor een gegevenspartner bevat. Dit is nuttig als u een grote organisatie met veelvoudige onderverdelingen of andere organisatorische groepen hebt u gegevens met mag delen. Deze macro keert een lijst van identiteitskaarts voor die ondergeschikte groepen terug. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID gegevensaanbieder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>De uitvoer van deze macro wijst de gegevensleverancier-id (DPID) toe aan gerelateerde unieke gebruikers-id's (DPUUID). Deze macro moet een opmaaktekenreeks hebben om de uitvoer ervan te bepalen. De voorbeelduitvoer ziet er ongeveer als volgt uit: </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>De <code> maxMappings </code> instelling bepaalt hoeveel toewijzingen de macro moet retourneren. Wanneer <code> maxMappings=0 </code>, keert deze macro alle afbeeldingen voor elke gespecificeerde DPID terug. Gegevens worden gesorteerd op tijdstempel (meest recente eerst) en retourneert eerst resultaten met de grootste tijdstempel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>Deze combinatie van macro's leidt tot een voorwaardelijke verklaring die van de segmenten een lijst maakt de gebruikers tot behoren en zijn verwijderd uit. Er wordt een lege tekenreeks geretourneerd als niet aan beide voorwaarden is voldaan of als er geen gegevens zijn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud ID.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Hiermee voegt u een open accolade {-teken in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>Vervangen. Niet gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Volgorde- of doel-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Vervangen. Niet gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>Retourneert <code> 1 </code> als een statische, gecodeerde waarde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>Partner-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>An alias for an order/destination ID. </p> <p>De alias wordt ingesteld in de interface voor beheerders. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Retourneert een lijst met eventueel verwijderde segmenten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Retourneert een lijst met segmenten in een lijst. Accepteert de volgende optionele argumenten: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>: Segment-id. Vervangen. Gebruik <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: Klantsegment-id. Vervangen. Gebruik <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: Segment-id </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Retourneert <code> 5 </code>een statische, gecodeerde waarde die gegevens identificeert als segmentgegevens. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Vervangen. Niet gebruiken. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>: Een Unix-tijdstempel waarmee de laatste keer wordt aangegeven dat een segment werd gerealiseerd. </li> 
    </ul> <p>Plaats deze variabelen tussen accolades na de macro. Deze code scheidt bijvoorbeeld de resultaten met een verticale streep (|): <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Retourneert <code> 1 </code>als een statische, gecodeerde waarde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Geeft het synchronisatietype aan en omvat: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Volledige synchronisatie. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Incrementele synchronisatie. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Geeft de methode voor gegevensoverdracht aan en omvat: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Deze macro wordt gebruikt als scheidingsteken en voegt een tab in tussen velden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Retourneert een lijst met kenmerken. Accepteert de volgende optionele argumenten: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Geeft de typen eigenschap aan op basis van een numerieke id. Retourneert: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> die een spoor DPM (off-line, die door een binnenkomende baan wordt ingezien) identificeert. </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> die een op regels gebaseerde eigenschap (realtime, aan boord genomen via de DCS) identificeert. </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>: traditie-id. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>: De laatste keer dat de eigenschap werd gerealiseerd. Unix-tijdstempel. </li> 
    </ul> <p>Plaats deze variabelen tussen accolades na de macro. In deze code worden de resultaten bijvoorbeeld gescheiden met het teken "|" van de pipe: <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager- </span> gebruikersnaam. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Uitgaande macrovoorbeelden](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

