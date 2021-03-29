---
description: Beschrijft de vereiste gebieden, de syntaxis, en de noemende overeenkomsten die voor op dossier-gebaseerde synchronisatie van identiteitskaart worden gebruikt. Geef de bestandsinhoud een naam en ordent deze volgens deze specificaties.
seo-description: Beschrijft de vereiste gebieden, de syntaxis, en de noemende overeenkomsten die voor op dossier-gebaseerde synchronisatie van identiteitskaart worden gebruikt. Geef de bestandsinhoud een naam en ordent deze volgens deze specificaties.
seo-title: Naam- en contentvereisten voor id-synchronisatiebestanden
solution: Audience Manager
title: Naam- en contentvereisten voor id-synchronisatiebestanden
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Binnenkomende gegevensoverdrachten
translation-type: tm+mt
source-git-commit: de1483763998027c4fc7694223c39dd7a37e87ab
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 6%

---


# Naam- en contentvereisten voor id-synchronisatiebestanden {#name-and-content-requirements-for-id-synchronization-files}

Beschrijft de vereiste gebieden, de syntaxis, en de noemende overeenkomsten die voor op dossier-gebaseerde synchronisatie van identiteitskaart worden gebruikt. Geef de bestandsinhoud een naam en ordent deze volgens deze specificaties.

>[!NOTE]
>
>De tekststijlen (`monospaced text`, *cursief*, haakjes `[ ]` `( )`, enz.) in dit document de elementen en opties van de code aangeven. Zie [Stijlconventies voor code- en tekstelementen](../../../reference/code-style-elements.md) voor meer informatie.

## Syntaxis bestandsnaam en voorbeelden {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

Namen van id-bestanden bevatten de volgende vereiste en optionele elementen:

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>Een statisch voorvoegsel dat het bestand identificeert als een ID-synchronisatiebestand. Gebruik dit voorvoegsel wanneer apparaat-id's overeenkomen met andere apparaat-id's of klant-id's (DPUUID's).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Een statisch voorvoegsel dat het bestand identificeert als een ID-synchronisatiebestand voor op mensen gebaseerde doelen. Gebruik dit voorvoegsel wanneer u id's van klanten (DPUUID's) afstemt op gehashte e-mailadressen voor op mensen gebaseerde doelen.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>De master gegevensleverancier ID is ouderidentiteitskaart van DPIDs in het dossier - naam. De eerste gebruiker-id in het gegevensbestand komt ook overeen met de master id. Verdere DPIDs is andere herkenningstekens die tot master behoren. Door synchronisatie worden DPID's in de bestandsnaam toegewezen aan UUID's in het bestand.</p> <p>Deze DPID mag alleen apparaat-id's bevatten, zoals AAM UUID, GAID, IDFA enzovoort. Het kan geen DPUUIDs bevatten. Dit kan resulteren in een onjuiste synchronisatie.</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>ID's van gegevensaanbieder. Deze id's vertegenwoordigen entiteiten of gegevensbronnen die zijn gekoppeld aan de master DPID. Door synchronisatie worden DPID's in de bestandsnaam toegewezen aan UUID's in het bestand. </p> <p>Het aantal DPID's in de bestandsnaam moet overeenkomen met het aantal UUID's in het gegevensbestand. Stel dat uw bestandsnaam een master DPID en 3 DPID's bevat. Uw gegevensbestand moet vier overeenkomstige kolommen van UUIDs omvatten, die zoals die in de hieronder sectie van de dossierinhoud wordt beschreven wordt geformatteerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Een UNIX-tijdstempel van 10 cijfers in seconden. Met de tijdstempel kunt u elke bestandsnaam uniek maken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Geeft een normale, volledige synchronisatie aan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Een geheel getal. Wordt gebruikt wanneer u grote bestanden in meerdere kleinere bestanden splitst. Dit helpt verwerkingstijden te verbeteren. Het nummer geeft aan welk deel van het oorspronkelijke bestand u wilt invoeren. Zie de voorbeelden van de bestandsnaam hieronder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Geeft aan dat het bestand wordt gecomprimeerd met optionele gzip-compressie. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Voorbeelden van bestandsnamen

In de volgende voorbeelden worden bestandsnamen met de juiste indeling getoond. De bestandsnamen kunnen er ongeveer hetzelfde uitzien.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Zie [Workflow A - Personalisatie gebaseerd op alle online activiteiten gecombineerd met offlinegegevens](../../../features/destinations/people-based-destinations-workflow-combined.md) of [Workflow B - Personalisatie gebaseerd op gegevens die alleen offline zijn.](../../../features/destinations/people-based-destinations-workflow-offline.md) voor naamgeving van ID-synchronisatiebestanden (c2c-voorvoegsel) voor op mensen gebaseerde doelen.

## Syntaxis bestandsinhoud en voorbeelden {#file-content-syntax}

De inhoud van een id-bestand bevat de volgende elementen:

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

Het bestand bevat gebruikers-id&#39;s ([!DNL UUID]). Plaats in elke rij een tab tussen de id&#39;s. In het volgende voorbeeld wordt een correct opgemaakt id-bestand getoond. De inhoud kan er ongeveer hetzelfde uitzien.

```
abc123 def456 ghi789 xyz987
```

### Overwegingen bij bestandsinhoud {#considerations}

Wanneer u binnenkomende bestanden maakt, moet u ervoor zorgen dat de eerste kolom alleen met apparaat-id&#39;s wordt gevuld, zoals [!DNL AAM UUID], [!DNL GAID], [!DNL IDFA] enzovoort. Zie [Index van id&#39;s in Audience Manager](../../../reference/ids-in-aam.md) voor een gedetailleerde uitleg van id&#39;s die door Audience Manager worden ondersteund.

>[!IMPORTANT]
>
>Gebruik [DPUUIDs](../../../reference/ids-in-aam.md) op de eerste kolom niet. Dit kan resulteren in een onjuiste synchronisatie.

## Synchronisatie stemt overeen met DPUUID&#39;s met UUID&#39;s {#sync-matches-dpuuids-uuids}

Het doel van een bestand voor id-synchronisatie is om de [DPUUID&#39;s](../../../reference/ids-in-aam.md) vanuit uw eigen gegevensbronnen te synchroniseren met [!DNL Audience Manager] UUID&#39;s. De synchronisatie wijst [!DNL DPUUID]s van master [!DNL DPID] en zijn verwante [!DNL DPID]s aan [!DNL Audience Manager] [!DNL UUID]s toe. Wanneer u de id&#39;s in de bestandsnaam en de hoofdtekst plaatst, bepaalt u hoe deze id&#39;s aan elkaar worden toegewezen. Neem bijvoorbeeld de volgende twee voorbeeldbestanden:

* **Bestand 1:** `adobe_id_0_12345_1476312152.sync`

* **Bestand 2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

Op basis van de naam en inhoud van het voorbeeld worden de id&#39;s als volgt toegewezen:

**Bestand 1**  (voorbeeldbestand [ ](assets/adobe_id_0_12345_1476312152.sync)downloaden)

| DPID 0 = Adobe Audience Manager UUIDs | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR.38 |
| 6741268208341199572553870443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 6655275740751744946280581945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLworgJU2M |
| 6618477822667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

{style=&quot;table-layout:auto&quot;}

Stap 1: Bij het synchronisatieproces van de id worden de [!DNL DPUUID]s van [!DNL DPID] 12345 gesynchroniseerd met de [!DNL Audience Manager] [!DNL UUID]s in de linkerkolom. De [!DNL DPID] &quot;0&quot; in de bestandsnaam vertegenwoordigt [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**Bestand 2**  (voorbeeldbestand [ ](assets/adobe_id_12345_67890_1477846458.sync)downloaden)

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR.38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLworgJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

{style=&quot;table-layout:auto&quot;}

Stap 2: de [!DNL DPUUID]s van [!DNL DPID] 12345 zijn gesynchroniseerd in stap 1 met de Audience Manager [!DNL UUID]s. Bij deze ID-synchronisatie worden de [!DNL DPUUID]s van [!DNL DPID] 67890 gesynchroniseerd met de Audience Manager [!DNL UUID]s van stap 1.

<br/>

## Overige indelingsvereisten {#other-format-reqs}

Gebruikersnamen kunnen niet:

* Plaats tabs in de id zelf. Tabs worden alleen gebruikt om afzonderlijke id&#39;s in het gegevensbestand te scheiden.
* Bevat persoonlijk identificeerbare informatie ([!UICONTROL PII]).
* Codering [!DNL URL] gebruiken. Alleen niet-gecodeerde id&#39;s doorgeven.

Rijen die eindigen met tabs of spaties, worden niet verwerkt of uitgevoerd. Zorg er doorgaans voor dat het einde van de rijen ongewijzigd blijft.