---
description: Audience Manager en de Adobe Experience Platform Identity Service maken aanroepen naar en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk domein van derden, maar dit is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-description: Audience Manager en de Adobe Experience Platform Identity Service maken aanroepen naar en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk domein van derden, maar dit is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-title: Inzicht krijgen in oproepen van het demdex-domein
solution: Audience Manager
title: Inzicht krijgen in oproepen van het demdex-domein
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Inzicht krijgen in oproepen van het demdex-domein{#understanding-calls-to-the-demdex-domain}

Audience Manager en de Adobe Experience Platform Identity Service maken aanroepen naar en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk domein van derden, maar dit is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elementen aanroepen </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Dit is een verouderd domein dat door <span class="keyword"> Adobe</span>wordt beheerd. Deze geeft de oorspronkelijke naam van <span class="keyword"> Audience Manager</span>vóór de overname weer (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> heeft <span class="keyword"> Demdex</span> in 2011 overgenomen en het bedrijf opnieuw gebrandt als <span class="keyword"> Audience Manager</span>. Het is moeilijk om dit domein te veranderen omdat het diep met de Manager <span class="keyword"> van het</span>Publiek, de dienst <span class="wintitle"> van</span>identiteitskaart, en onze geïnstalleerde gebruikersbasis wordt verweven. Zie <a href="../overview/aam-overview.md#history-and-background"> Geschiedenis en Achtergrond</a>. </p> <p>U kunt andere prefixen zien verbonden aan erfenisvraag (b.v., <code> demdex.net</code> , <code> dcs.demdex.net</code><code> fast.demdex.net</code>, enz.). Een aanroep naar <code><i>something</i>.demdex.net</code> is altijd een aanroep naar <span class="keyword"> Adobe</span> en niet naar een onbekend of verdacht domein van derden, ongeacht het voorvoegsel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> is een afkorting voor de Gelijke van de <span class="wintitle"> Gegevensleverancier</span>. Het vertelt interne, <span class="keyword"> systemen van Adobe</span> dat een vraag van de Manager <span class="keyword"> van het</span> Publiek of de dienst <span class="wintitle"></span> van identiteitskaart in klantengegevens voor synchronisatie of het vragen van een identiteitskaart overgaat. Dit is de gemeenschappelijkste <code> demdex.net</code> vraag u van de Manager <span class="keyword"> van het</span> Publiek of de dienst <span class="wintitle"> van</span>identiteitskaart zult zien. </p> <p><span class="wintitle"> Beginselen van DPM</span> -aanroepen: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Poortbeheer</span> </b>: Een <span class="wintitle"> DPM</span> vraag van de Manager <span class="keyword"> van de Auditie verzendt gegevens naar de Servers</span> van de <span class="wintitle"> Gegevensverzameling en de Servers</span> van het Geheime voorgeheugen van het <span class="wintitle"></span>Profiel. Zie <a href="../reference/system-components/components-data-collection.md"> Componenten</a>voor gegevensverzameling. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> ID-service</span> </b>: Een vraag <span class="wintitle"> DPM</span> van de dienst <span class="wintitle"></span> van identiteitskaart is een verzoek om bezoekersidentiteitskaart Zie <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies en de Adobe Experience Platform Identity Service</a> en <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="https" scope="external"> How the Adobe Experience Platform Identity Service Requests and Sets IDs</a>. </li> 
     </ul> </p> <p> <p>Opmerking:  <span class="wintitle"> De de dienstklanten van identiteitskaart</span> kunnen de prefix <span class="wintitle"> DPM</span> in de domeinnaam veranderen. Zie <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html" format="https" scope="external"> publieksbeheerserver en publiekManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Auditiebeheer cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

