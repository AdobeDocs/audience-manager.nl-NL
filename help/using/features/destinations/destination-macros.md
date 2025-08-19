---
description: Beschrijft de macro's u aan een bestemmingsURL kunt toevoegen.
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: Gedefinieerde doelmacro's
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 0%

---

# Gedefinieerde doelmacro&#39;s {#destination-macros-defined}

Beschrijft de macro&#39;s u aan een bestemming [!DNL URL] kunt toevoegen.

<!-- destination-macros.xml -->

Wanneer u een [!DNL URL] -doel maakt, kunt u de volgende macro&#39;s in de [!DNL URL] -tekenreeks invoegen. Raadpleeg uw gegevens/bestemmingspartner voor een juiste macroplaatsing binnen het doel [!DNL URL] .

>[!NOTE]
>
>Macro&#39;s zijn optioneel, tenzij anders aangegeven. *Cursief* wijst op veranderlijke placeholder.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Toelichting </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>Vereist. </p> <p>Bepaalt de plaats van de in kaart gebrachte segmentwaarde in een bestemmingsURL. Gewoonlijk is dit identiteitskaart van het 1} Segment <i>, maar kon ook de integratiecode zijn.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Voegt <span class="keyword"> Audience Manager </span> identiteitskaart van de gebruiker in bestemmingsURL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>De <i> gegevensbron identiteitskaart </i> beantwoordt aan het herkenningsteken voor een gegevensbron die binnen tot de macro wordt overgegaan. </p> <p>Laten we eens kijken hoe dit werkt in een eenvoudig voorbeeld. In dit geval, hebben wij een <span class="keyword"> Audience Manager </span> partner met volgende IDs en voorwaarden: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Gegevensbron-id: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Een interne klant-id: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Gedeclareerde id: de partner wil deze waarden doorgeven als de gedeclareerde id <code> 1:CustomerABC</code> . </li> 
    </ul> <p>Om dit met <code>%dpid_<i>data source id</i>%</code> te doen, zou de <span class="keyword"> Audience Manager </span> partner de macro als dit formatteren: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>De macro vervangt <code> 1</code> door <code> CustomerABC</code> . </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Geeft aan of de GDPR-regels al dan niet van toepassing zijn op de bezoeker. Gebruik deze macro om toestemming in segmenten te omvatten die naar bestemmingen URL worden verzonden die met IAB worden geïntegreerd. Zie <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md"> Plug-in Audience Manager voor IAB TCF </a> voor details.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>De toestemmingstekenreeks (met inbegrip van IAB verkopersidentiteitskaart) die wordt verzameld wanneer de bezoekers verlenen of toestemming op uw plaats ontkennen. Gebruik deze macro om het toestemmingskoord in segmenten te omvatten die naar bestemmingen URL worden verzonden die met IAB worden geïntegreerd. Vervang <code>XXXX</code> door de id van de doelpartner. Zie <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md"> Plug-in Audience Manager voor IAB TCF </a> voor details. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Detecteert het protocol dat in de bovenliggende webpagina wordt gebruikt en voegt dit in de doel-URL in. Bijvoorbeeld:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">als webpage <b> https </b> is://aam_client.com, zal deze macro met <b> https </b> worden vervangen://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">als webpage <b> http </b> is://aam_client.com, zal deze macro met <b> worden vervangen http </b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Voegt <span class="keyword"> identiteitskaart van Experience Cloud </span> in bestemmingsURL in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Neemt het <span class="wintitle"> gebied van de Server van de Inzameling van Gegevens (DCS) </span> in bestemmingsURL op. Om latentie te minimaliseren, wanneer de bezoeker een vraag van HTTP aan <span class="keyword"> Audience Manager </span> maakt, worden zij opnieuw gericht aan het dichtstbijzijnde <span class="wintitle"> DCS </span> datacenter. Dit wordt bereikt door DNS, die de plaats van de bezoeker kan ontdekken en hen aan aangewezen datacenter leiden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Voert een functie voor het buigen van cache uit door een willekeurig getal in te voegen in de doel-URL. Zo voorkomt u dat browsers inhoud in de cache verzenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Voegt een UNIX-tijdstempel in de doel-URL in om te voorkomen dat browsers inhoud in de cache verzenden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Het Bewaren van het geheime voorgeheugen met de Macro&#39;s van de Doel {#destination-cache-busting}

Met de macro&#39;s `%rnd%` en `%timestamp%` voegt u unieke waarden in een [!DNL URL] -tekenreeks in om te voorkomen dat de browser in cache wordt geplaatst.

## Cache Busting with `%rnd%` en `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Browsers bewaren (sparen) vaak gevraagde inhoud in geheugen. Wanneer een pagina wordt geladen, dient opgeslagen inhoud niet van een externe server, maar van de cache te worden opgeslagen. Dit proces helpt efficiënte downloadtijden te handhaven omdat gegevens lokaal dienen in plaats van van van een andere plaats. Omdat caching echter geen serveraanroep vereist, kan de rapportage scheeftrekken door het aantal unieke aanvragen kunstmatig te verlagen.

Door de cache op te slaan kunnen browsers geen inhoud opslaan en opnieuw gebruiken. Deze techniek gebruikt code die een willekeurig getal of tijdstempel in een URL-tekenreeks invoegt, waardoor deze er uniek uitziet voor de browser. Dientengevolge, wordt elke `HTTP` vraag geteld als afzonderlijk verzoek aan de server. Dwingend een nieuwe servervraag voor elk verzoek helpt rapporteringsnauwkeurigheid te handhaven en discrepanties te verminderen. [!DNL Audience Manager] biedt twee macro&#39;s voor het busten van cache:

* `%rnd%`: voegt een willekeurig getal in een URL in.
* `%timestamp%`: voegt de Unix-datum/tijd in een URL in.

## `%rnd%` en `%timestamp%` vergelijken {#compare-rnd-timestamp}

Beide macro&#39;s voorkomen caching, maar `%rnd%` kan efficiënter zijn. Met `%timestamp%` krijgen meerdere gebruikers bijvoorbeeld dezelfde datum-/tijdwaarde wanneer ze een pagina tegelijk bekijken. Als gevolg hiervan is [!DNL URL] niet uniek en worden meerdere aanroepen slechts één keer geteld. `%rnd%` genereert echter een unieke numerieke waarde voor elke aanroep (zelfs als gebruikers dezelfde pagina tegelijk zien). Dit betekent dat de [!DNL URL] -tekenreeks andere waarden bevat en als uniek wordt geteld.

>[!MORELIKETHIS]
>
>* [Definities van bestemmingsmacro’s](../../features/destinations/destination-macros.md#destination-macros-defined)
