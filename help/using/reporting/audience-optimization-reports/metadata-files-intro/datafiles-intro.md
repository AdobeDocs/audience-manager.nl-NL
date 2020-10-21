---
description: Een gegevensbestand bevat indruk, klik, of omzettingsgegevens. Als de indeling correct is, kunt u deze gegevens importeren in de Audience Manager en gebruiken in de Audience Optimization-rapporten en voor uitvoerbare logbestanden. Maak uw gegevensbestanden op volgens de specificaties in deze sectie.
seo-description: Een gegevensbestand bevat indruk, klik, of omzettingsgegevens. Als de indeling correct is, kunt u deze gegevens importeren in de Audience Manager en gebruiken in de Audience Optimization-rapporten en voor uitvoerbare logbestanden. Maak uw gegevensbestanden op volgens de specificaties in deze sectie.
seo-title: Databestanden voor Audience Optimization-rapporten en actiegerichte logboekbestanden
solution: Audience Manager
title: Databestanden voor Audience Optimization-rapporten en actiegerichte logboekbestanden
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: log files
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 3%

---


# Databestanden voor Audience Optimization-rapporten en actiegerichte logboekbestanden {#data-files-for-audience-optimization-reports}

Een gegevensbestand bevat indruk, klik, of omzettingsgegevens. Als de indeling correct is, kunt u deze gegevens importeren in Audience Manager om deze weer te geven in de [Audience Optimization-rapporten](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) en kenmerken maken met behulp van de gegevens via [uitvoerbare logbestanden](/help/using/integration/media-data-integration/actionable-log-files.md). Maak uw gegevensbestanden op volgens deze specificaties in deze sectie.

## Overzicht {#overview}

Met een bestand met een correcte naam en opmaak kunt u indruk-, klik- of conversiegegevens importeren naar [Audience Optimization-rapporten](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Dit is nuttig wanneer het werken met een partner die niet met geïntegreerd is [!DNL Audience Manager] en u met hun gegevens in die rapportreeks wilt werken. Voor dit proces zijn aparte bestanden nodig voor de weergave, klik en conversie van gegevens. Meng deze gebeurtenissen niet in één bestand.

Een gegevensbestand moet vergezeld gaan van een metagegevensbestand. De inhoud van het meta-gegevensdossier past de informatie van het gegevensdossier aan verwante, mens-leesbare etiketten in de rapportmenu&#39;s aan. Voor meer informatie, zie [Overzicht en Toewijzingen voor de Dossiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)van Meta-gegevens.

## Naming Conventions for Data Files {#naming-conventions}

De volgende syntaxis definieert de structuur van een goed gevormde naam van een gegevensbestand. Opmerking: *cursief* geeft een variabele plaatsaanduiding aan die afhankelijk van de bestandsinhoud verandert.

**Syntaxis:** <pre><i>gebeurtenistype</i>_<i>jjjjjjmmdd</i></code></pre>

In een bestandsnaam:

* Het gebeurtenistype geeft aan dat het bestand afbeeldingen bevat, klikt of conversies. Maak een afzonderlijk bestand voor elk gebeurtenistype.
* Een onderstrepingsteken scheidt het gebeurtenistype en een jaar-maand-datum timestamp.
* Voordat u bestanden uploadt, comprimeert u ze met gzip en slaat u ze op met de `.gz` bestandsextensie.

Geef uw gegevensbestanden, op basis van de inhoud van de bestanden, de volgende naam op basis van deze vereisten:

* Impressiegegevens: <pre>impressions_<i>yyyymmdd</i>.gz</code></pre>
* Klik op gegevens: <pre>clicks_<i>yyyymmdd</i>.gz</code></pre>
* Conversiegegevens: <pre>conversions_<i>yyyymmdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

De volgende syntaxis definieert de inhoudsstructuur in een correct samengesteld gegevensbestand. Opmerking: *cursief* geeft een plaatsaanduiding voor variabelen aan en wordt vervangen door een label in een feitelijk gegevensbestand.

**Syntaxis:** <pre><i>koptekstlabel 1</i> | <i>Koptekstlabel 2</i> ... <i>koptekstlabel n</i> | <i>versie</i></code></pre>

In de bestandsinhoud:

* De koptekstlabels moeten in de volgorde staan die in de onderstaande tabel wordt weergegeven. Bij indrukken en klikken worden dezelfde labels gebruikt. Conversiebestanden bevatten extra kopteksten.
* Als u geen gegevens voor een bepaalde kolom hebt, bevolk dat gebied met een `-1`.

* Bestanden *moeten* eindigen op een versienummer. De huidige versie is 1.1.
* Scheid bestandsheaders en inhoud met het niet-afdrukbare ASCII 001-teken. Als u ASCII 001 niet kunt gebruiken, dan scheidt u de kopballen en de gegevens met een lusjescheidingsteken. Aangezien dit niet-afdrukbare tekens zijn, wordt in het bovenstaande syntaxisvoorbeeld alleen een pipe weergegeven `"|"` voor weergavedoeleinden.

**Veldlabels**

In de onderstaande tabel vindt u een overzicht en beschrijving van de kolomkoppen voor het gegevensbestand. De kopballen zijn case-sensitive en moeten verschijnen zoals bevolen in de lijst. Alle gegevenstypen zijn gehele getallen (INT), tenzij anders aangegeven.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tijdstempel </p> </td> 
   <td colname="col2"> <p>Een UTC-datum en -tijd voor de impositie, klik of conversiegebeurtenis. Gebruik de <code> yyyy-MM-dd HH:mm:ss</code> indeling. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gebruikersnaam </p> </td> 
   <td colname="col2"> <p>Uw id voor een sitebezoeker, ook wel de unieke gebruikers-id <span class="term"> of DPUUID van de</span> gegevensaanbieder genoemd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>De gegevensbron-id of integratiecode voor uw adverteerder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>Bedrijfs-eenheid-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campagne-id </p> </td> 
   <td colname="col2"> <p>Campagne-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-id </p> </td> 
   <td colname="col2"> <p>Creative ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-id </p> </td> 
   <td colname="col2"> <p>Site-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plaatsing-id </p> </td> 
   <td colname="col2"> <p> Numerieke plaatsing-id van de advertentieserver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Id van invoegvolgorde </p> </td> 
   <td colname="col2"> <p>Invoegvolgorde-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>Tactische id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verticaal-id </p> </td> 
   <td colname="col2"> <p>ID voor een verticale branche of een categorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aantal </p> </td> 
   <td colname="col2"> <p> Het aantal objecten dat tijdens een conversiegebeurtenis is verkocht. </p> <p> <i>Alleen voor conversiegegevensbestanden.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ontvangsten </p> </td> 
   <td colname="col2"> <p>Aankoop of ander omrekeningsbedrag. Gegevenstype: Zweven. </p> <p> <i>Alleen voor conversiegegevensbestanden.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Andere gegevens </p> </td> 
   <td colname="col2"> <p>URL van de bestemmingspagina van de conversie. Gegevenstype: Tekenreeks. </p> <p> <i>Alleen voor conversiegegevensbestanden.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type gebeurtenis </p> </td> 
   <td colname="col2"> <p>Conversietype. Geeft aan of een conversie overeenkomt of niet. De volgende opties zijn beschikbaar: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impressie </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Klik op </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Onbeheerd of onbekend </li> 
    </ul> <p> <i>Alleen voor conversiegegevensbestanden.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versie </p> </td> 
   <td colname="col2"> <p>Een vereist versienummer dat aan het einde van elke rij in een afbeeldings-, klik- of conversiegegevensbestand wordt weergegeven. De huidige versie is 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload uw afbeeldings-, klik- of conversiegegevensbestanden naar een Amazon S3-directory voor uw [!DNL Audience Manager] account. Raadpleeg deze sectie voor informatie over levering/directorypaden, verwerkingstijden en updates.

>[!IMPORTANT]
>
> Neem contact op met de consultant van de Audience Manager of de klantenservice om aan de slag te gaan en stel een [!DNL Amazon S3] directory voor uw gegevensbestanden in.

**Syntaxis en voorbeelden van leveringspad**

Gegevens worden in een aparte naamruimte voor elke klant in een [!DNL Amazon S3] map opgeslagen. Het bestandspad volgt de onderstaande syntaxis. Opmerking: *cursief* geeft een variabele plaatsaanduiding aan. Andere elementen zijn constanten of sleutels en veranderen niet.

**Syntaxis:** <pre>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ <i>bestandstype</i>_<i>yyyymmdd</i></code></pre>

In de volgende tabel worden deze elementen gedefinieerd in een pad voor het leveren van bestanden.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Bestandsparameter </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Dit is het begin van de weg van de folderopslag. U ontvangt het volledige pad wanneer alles is ingesteld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dit zeer belangrijk-waardepaar bevat uw <span class="keyword"> klant identiteitskaart van de Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Dit zeer belangrijk-waardepaar bevat gegevensbronidentiteitskaart die op een gebeurtenisvraag wordt overgegaan. De instantie waar de gegevens vandaan komen, wordt geïdentificeerd en deze gegevens worden gekoppeld aan een bestand met ondersteunende metagegevens. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Een map op een hoger niveau voor gegevensbestanden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Een bestandstype met de naam die aangeeft welk type gegevens het bevat en een tijdstempel voor de levering. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Voorbeeld van uploadpad en bestandsnaam**

Wanneer u een bestand uploadt, ziet het pad er als volgt uit:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Verwerkingstijden en updates van bestanden**

Gegevensbestanden worden vier keer per dag verwerkt, met regelmatige intervallen.

Om uw gegevens bij te werken, verzend in een dossier dat alle beelden, klikken, of omzettingen voor een bepaalde dag bevat. In dit geval is een dag de periode van 24 uur van middernacht aan volgende. Als beste praktijken, kunt u UTC tijd willen gebruiken om uw daginterval te bepalen.

## Volgende stappen {#next-steps}

Controleer de vereisten voor het benoemen en maken van metagegevensbestanden. Om te beginnen, zie [Overzicht en Toewijzingen voor de Dossiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)van Meta-gegevens.
