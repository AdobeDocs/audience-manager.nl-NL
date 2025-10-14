---
description: Een gegevensbestand bevat indruk, klik, of omzettingsgegevens. Als de indeling correct is, kunt u deze gegevens importeren naar Audience Manager en gebruiken in de Audience Optimization-rapporten en voor Actionable Log Files. Maak uw gegevensbestanden op volgens de specificaties in deze sectie.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Gegevensbestanden voor Audience Optimization-rapporten en uitvoerbare logbestanden
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 0%

---

# Gegevensbestanden voor Audience Optimization-rapporten en uitvoerbare logbestanden {#data-files-for-audience-optimization-reports}

Een gegevensbestand bevat indruk, klik, of omzettingsgegevens. Wanneer behoorlijk geformatteerd, kunt u deze gegevens in Audience Manager invoeren om het in de [&#x200B; Rapporten van Audience Optimization &#x200B;](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) te bekijken en treinen tot stand te brengen gebruikend de gegevens via [&#x200B; Actiebare Dossiers van het Logboek &#x200B;](/help/using/integration/media-data-integration/actionable-log-files.md). Maak uw gegevensbestanden op volgens deze specificaties in deze sectie.

## Overzicht {#overview}

Een behoorlijk genoemd en geformatteerd gegevensbestand laat u indruk invoeren, klikken, of omzettingsgegevens in de [&#x200B; Rapporten van Audience Optimization &#x200B;](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Dit is handig wanneer u werkt met een partner die niet is geïntegreerd met [!DNL Audience Manager] en u met de gegevens in die rapportsuite wilt werken. Voor dit proces zijn aparte bestanden nodig voor de weergave, klik en conversie van gegevens. Meng deze gebeurtenissen niet in één bestand.

Een gegevensbestand moet vergezeld gaan van een metagegevensbestand. De inhoud van het meta-gegevensdossier past de informatie van het gegevensdossier aan verwante, mens-leesbare etiketten in de rapportmenu&#39;s aan. Voor meer informatie, zie [&#x200B; Overzicht en Toewijzingen voor de Dossiers van Meta-gegevens &#x200B;](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naamgevingsconventies voor gegevensbestanden {#naming-conventions}

De volgende syntaxis definieert de structuur van een goed gevormde naam van een gegevensbestand. Nota, *cursief* wijst op veranderlijke placeholder die afhankelijk van de dossierinhoud verandert.

**Syntaxis:** <pre><code><i> gebeurtenistype </i> _<i> jjjjjjmmdd </i></code></pre>

In een bestandsnaam:

* Het gebeurtenistype geeft aan dat het bestand afbeeldingen bevat, klikt of conversies. Maak een afzonderlijk bestand voor elk gebeurtenistype.
* Een onderstrepingsteken scheidt het gebeurtenistype en een jaar-maand-datum timestamp.
* Voordat u bestanden uploadt, comprimeert u ze met gzip en slaat u ze op met de bestandsextensie `.gz` .

Geef uw gegevensbestanden, op basis van de inhoud van de bestanden, de volgende naam op basis van deze vereisten:

* Impressiegegevens: <pre><code> impressions_<i> jjymmdd </i> .gz</code></pre>
* Klik op gegevens: <pre><code> klikt_<i> jjjjmmdd </i>.gz</code></pre>
* Conversiegegevens: <pre><code> conversions_<i> jjjjmmdd </i>.gz</code></pre>

## Indeling van inhoud voor gegevensbestanden {#content-format}

De volgende syntaxis definieert de inhoudsstructuur in een correct samengesteld gegevensbestand. Nota, *cursief* wijst op veranderlijke placeholder en met een etiket in een werkelijk gegevensdossier vervangen.

**Syntaxis:** <pre><code><i> kopbaletiket 1 </i> | <i> kopbaletiket 2 </i>.. <i> kopbaletiket n </i> | <i> versie </i></code></pre>

In de bestandsinhoud:

* De koptekstlabels moeten in de volgorde staan die in de onderstaande tabel wordt weergegeven. Bij indrukken en klikken worden dezelfde labels gebruikt. Conversiebestanden bevatten extra kopteksten.
* Als u geen gegevens voor een bepaalde kolom hebt, vult u dat veld met een `-1` .

* De dossiers *moeten* met een versieaantal beëindigen. De huidige versie is 1.1.
* Scheid bestandsheaders en inhoud met het niet-afdrukbare ASCII 001-teken. Als u ASCII 001 niet kunt gebruiken, dan scheidt u de kopballen en de gegevens met een lusjescheidingsteken. Aangezien dit niet-afdrukbare tekens zijn, wordt in het bovenstaande syntaxisvoorbeeld een pipe `"|"` weergegeven die alleen voor weergavedoeleinden wordt gebruikt.

**Etiketten van het Gebied**

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
   <td colname="col2"> <p>Een UTC-datum en -tijd voor de impositie, klik of conversiegebeurtenis. Gebruik de <code> yyyy-MM-dd HH:mm:ss</code> -indeling. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gebruikersnaam </p> </td> 
   <td colname="col2"> <p>Uw id voor een sitebezoeker, ook wel de <span class="term"> gegevensaanbieder met unieke gebruikers-id </span> of DPUUID genoemd. </p> </td> 
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
   <td colname="col2"> <p>Creative-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-id </p> </td> 
   <td colname="col2"> <p>Site-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plaatsing-id </p> </td> 
   <td colname="col2"> <p> Numerieke plaatsings-id van de advertentieserver. </p> </td> 
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
   <td colname="col2"> <p> Het aantal objecten dat tijdens een conversiegebeurtenis is verkocht. </p> <p> <i> slechts voor de dossiers van omzettingsgegevens.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ontvangsten </p> </td> 
   <td colname="col2"> <p>Aankoop of ander omrekeningsbedrag. Gegevenstype: Zwevend. </p> <p> <i> slechts voor de dossiers van omzettingsgegevens.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Andere gegevens </p> </td> 
   <td colname="col2"> <p>URL van de bestemmingspagina van de conversie. Gegevenstype: String. </p> <p> <i> slechts voor de dossiers van omzettingsgegevens.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type gebeurtenis </p> </td> 
   <td colname="col2"> <p>Conversietype. Geeft aan of een conversie overeenkomt of niet. U kunt onder andere de volgende opties kiezen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impressie </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: klikken </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Niet toegewezen of onbekend </li> 
    </ul> <p> <i> slechts voor de dossiers van omzettingsgegevens.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versie </p> </td> 
   <td colname="col2"> <p>Een vereist versienummer dat aan het einde van elke rij in een afbeeldings-, klik- of conversiegegevensbestand wordt weergegeven. De huidige versie is 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Leveringsmethoden voor gegevensbestanden {#delivery-methods}

Upload uw afbeeldings-, klik- of conversiegegevensbestanden naar een Amazon S3-directory voor uw [!DNL Audience Manager] -account. Raadpleeg deze sectie voor informatie over levering/directorypaden, verwerkingstijden van bestanden en updates.

>[!IMPORTANT]
>
> Neem contact op met uw Audience Manager-consultant of de klantenservice om aan de slag te gaan en stel een [!DNL Amazon S3] -map in voor uw gegevensbestanden.

**Syntaxis en Voorbeelden van de Weg van de Levering**

Gegevens worden opgeslagen in een aparte naamruimte voor elke klant in een map [!DNL Amazon S3] . Het bestandspad volgt de onderstaande syntaxis. Nota, *cursief* wijst op veranderlijke placeholder. Andere elementen zijn constanten of sleutels en veranderen niet.

**Syntaxis:** <pre><code>../log_ingestion/pid= <i> identiteitskaart van AAM </i>/dpid= <i> d_src </i>/logs/ <i> dossiertype </i> _ <i> jjjjjjjjmmdd </i></code></pre>

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
   <td colname="col2"> <p>Dit sleutelwaardepaar bevat uw <span class="keyword"> Audience Manager </span> klant-id. </p> </td> 
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

**Steekproef uploadt Weg en Dossier - Naam**

Wanneer u een bestand uploadt, ziet het pad er ongeveer als volgt uit:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**de Verwerkingstijden en Updates van het Dossier**

Gegevensbestanden worden vier keer per dag verwerkt, met regelmatige intervallen.

Om uw gegevens bij te werken, verzend in een dossier dat alle beelden, klikken, of omzettingen voor een bepaalde dag bevat. In dit geval is een dag de periode van 24 uur van middernacht aan volgende. Als beste praktijken, kunt u UTC tijd willen gebruiken om uw daginterval te bepalen.

## Volgende stappen {#next-steps}

Controleer de vereisten voor het benoemen en maken van metagegevensbestanden. Om begonnen te worden, zie [&#x200B; Overzicht en Toewijzingen voor de Dossiers van Meta-gegevens &#x200B;](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
