---
description: Een metagegevensbestand koppelt numerieke id's met namen die u kunt lezen en begrijpen. De Audience Optimization rapporten tonen leesbare namen in de diverse menu's van rapportopties.
seo-description: Een metagegevensbestand koppelt numerieke id's met namen die u kunt lezen en begrijpen. De Audience Optimization rapporten tonen leesbare namen in de diverse menu's van rapportopties.
seo-title: Overzicht en toewijzingen voor metadatabestanden
solution: Audience Manager
title: Overzicht en toewijzingen voor metadatabestanden
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Log Files
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 3%

---

# Overzicht en toewijzingen voor metadatabestanden{#overview-and-mappings-for-metadata-files}

Een metagegevensbestand koppelt numerieke id&#39;s met namen die u kunt lezen en begrijpen. De Audience Optimization rapporten tonen leesbare namen in de diverse menu&#39;s van rapportopties.

## Overzicht {#overview}

Een overzicht van metagegevens en hoe deze worden gebruikt. Een metagegevensbestand moet vergezeld gaan van een gegevensbestand. De inhoud van het meta-gegevensdossier past de informatie van het gegevensdossier aan verwante, mens-leesbare etiketten in de rapportmenu&#39;s aan. Voor meer informatie, zie [Gegevensdossiers voor de Rapporten van de Audience Optimization en Acteerbare Logdossiers](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Metagegevensbestanden bevatten gegevens over andere gegevens

Een metagegevensbestand bevat informatie over andere typen gegevens. Om u te helpen begrijpen hoe dit werkt, herzien hoe [!DNL Audience Manager] gegevens ontvangt.

Tijdens een indruk of klikgebeurtenis, [!DNL Audience Manager] ontvangt gegevens in een koord URL dat als *gebeurtenisvraag* wordt bekend.

De gebeurtenisvraag organiseert informatie in reeksen bepaalde zeer belangrijk-waardeparen. De waarden in een sleutelwaardepaar bevatten numerieke gegevens. Het metagegevensbestand bevat namen en andere leesbare gegevens die overeenkomen met de id in elk sleutelwaardepaar.

### Metagegevenskoppelingen-id&#39;s naar leesbare namen

Het metagegevensbestand is vereist om een numerieke id aan een leesbare naam te koppelen. Stel dat een gebeurtenisaanroep een creatieve id bevat in een sleutelwaardepaar als deze: `d_creative:1234`. Zonder een metagegevensbestand zou dit creatieve bestand worden weergegeven als 1234 in een optiemenu.

Een metagegevensbestand met de juiste indeling kan dit creatieve bestand echter binden aan een echte naam zoals &quot;Advertiser Creative A&quot;, een naam die u in een rapport kunt lezen en herkennen.

### Wanneer hebt u een metagegevensbestand nodig

Eerst, worden een meta-gegevensdossier, en alle hieronder vermelde parameters, vereist in een gebeurtenisvraag wanneer u [Audience Optimization Rapporten](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) wilt gebruiken.

Ten tweede hebt u een metagegevensbestand nodig als u uw eigen gegevens naar [!DNL Audience Manager] verzendt of als u gegevens wilt bekijken in de rapporten van andere providers waarmee u niet bent geïntegreerd. [!DNL Audience Manager] heeft bijvoorbeeld een integratie met [Dubbelklik op Campagne Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM) van Google. Wegens deze verhouding, [!DNL Audience Manager] kan IDs met namen en beschrijvingen associëren die door de rapportopties worden gebruikt. Zonder integratie, kunnen wij nog gegevens opnemen, maar de rapportopties zullen numerieke IDs in plaats van beschrijvende naam tonen.

![afbeelding in menu Metagegevens](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## Bestandstoewijzingen {#file-mappings}

De volgende lijst maakt een lijst van de zeer belangrijk-waardeparen die gegevens houden die door [!UICONTROL Audience Optimization] rapporten worden gebruikt. Als u een metagegevensbestand moet gebruiken, bevat het leesbare informatie die overeenkomt met de waarden in deze sleutelwaardeparen. De waarden voor deze toetsen accepteren alleen gehele getallen (gegevenstype INT). Opmerking: *cursief* geeft een variabele plaatsaanduiding aan. Andere elementen zijn constanten of sleutels en veranderen niet.

>[!IMPORTANT]
>
>Als u de [!UICONTROL Audience Optimization] rapporten gebruikt, *al* van deze waarden worden vereist in de gebeurtenisvraag.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rapportoptie </th> 
   <th colname="col2" class="entry"> Sleutelwaardeparen metagegevens </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adverteerder </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Dit is de gegevensbronidentiteitskaart van de adverteerder of integratiecode die wanneer het creëren van een gegevensbron wordt verstrekt. Zie <a href="../../../features/manage-datasources.md#create-data-source"> Een gegevensbron maken</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bedrijfseenheid (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campagne </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creatief </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>Accepteert twee verschillende sleutel-waardeparen: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Invoegvolgorde (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Platform </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Dit is de <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> gegevensbron</a> ID voor het platform dat meta-gegevensinformatie (b.v., DFA, Atlas, GBM, MediaMath, enz.) verstrekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactisch </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verticaal </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Hoe IDs van de Vraag van de Gebeurtenis de Namen van het Dossier, Inhoud, en de Wegen van de Levering {#how-ids-shape-file-names} vormen

Met de id&#39;s die door deze sleutelwaardeparen worden doorgegeven, kunt u de naam en inhoud van het metagegevensbestand maken. De volgende secties en illustraties tonen hoe dit werkt. Deze voorbeelden bouwen een dossier dat de naam van creatief in een campagne bevat, maar andere combinaties zijn mogelijk.

### Gebeurtenisoproep

In dit voorbeeld zullen wij een meta-gegevensdossier creëren dat creatieve namen binnen aan een [!UICONTROL Audience Optimization] rapport brengt. Hiervoor moeten we creatieve id&#39;s, campagne- en gegevensbronid&#39;s ophalen uit een gebeurtenisaanroep.

![gebeurteniscall image](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### Bestandsnaam

De bestandsnaam is gebaseerd op de creatieve id&#39;s, de campagne- en de gegevensbron. In dit geval, vergelijk de verschillen hier tussen de zeer belangrijk-waardegegevens in een gebeurtenisvraag en hoe het in een dossier - naam wordt gebruikt.

In een bestandsnaam:

* De gegevensbronsleutel verandert in `dpid` van `d_src`.

* De creatieve id&#39;s en campagne-id&#39;s vertegenwoordigen een categorie in plaats van een werkelijke id.

![hoe wordt een bestandsnaam samengesteld](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

Zie [Naamgevingsconventies voor metagegevensbestanden](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Bestandsinhoud

In dit voorbeeld weerspiegelt de bestandsinhoud de creatieve id&#39;s en campagne-id&#39;s die zijn doorgegeven aan de gebeurtenisaanroep. Het nieuwe element hier is een leesbare naam. Na verwerking wordt de naam in dit bestand als een optie weergegeven in het menu Creatief van een [!UICONTROL Audience Optimization]-rapport.

![inhoud van een metagegevensbestand](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

Zie [Indeling van inhoud voor metagegevensbestanden](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Bestandslevering

Nadat u de gegevens een naam hebt gegeven en ze aan een bestand hebt toegevoegd, verzendt u deze naar een Amazon S3-opslagmap die wordt geleverd door [!DNL Audience Manager]. Zie [Leveringsmethoden voor metagegevensbestanden](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Gegevensbestanden voor Audience Optimization-rapporten](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Klikdata campagne vastleggen via pixelcalls](../../../integration/media-data-integration/click-data-pixels.md)
>* [Campagne-impressiedata vastleggen via pixelcalls](../../../integration/media-data-integration/impression-data-pixels.md)

