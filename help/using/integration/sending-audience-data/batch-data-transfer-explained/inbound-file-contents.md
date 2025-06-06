---
description: De vereiste gebieden, syntaxis, en regels u zouden moeten volgen wanneer het formatteren van een binnenkomend dossier van eigenschapsgegevens.
solution: Audience Manager
title: Ingaande inhoud gegevensbestand - Syntaxis, Ongeldige tekens, variabelen en voorbeelden
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 1%

---

# Content van binnenkomende databestanden: syntaxis, ongeldige tekens, variabelen en voorbeelden {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

De vereiste gebieden, syntaxis, en regels u zouden moeten volgen wanneer het formatteren van een binnenkomend dossier van eigenschapsgegevens.

## Syntaxis bestandsinhoud {#file-content-syntax}

De velden in het binnenkomende gegevensbestand moeten in de hieronder getoonde orde verschijnen. In dit voorbeeld wordt `<` `>` er zijn symbolen toegevoegd om elk element visueel te kunnen scheiden. U hoeft deze niet op te nemen in het gegevensbestand.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Voor andere geaccepteerde bestandsindelingen raadpleegt u [Aangepaste partnerintegratie](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>We hebben een limiet van 200 regels die we kunnen verwerken voor elke gebruikersnaam die in het binnenkomende gegevensbestand wordt verzonden. Als u bijvoorbeeld 300 regels verzendt voor een gebruikers-id, worden de eerste 200 regels bewaard en worden de extra 100 regels verwijderd. In het onderstaande voorbeeld kun je het beste drie regels verzenden voor gebruikers-id 1 en gebruikersnaam 2. Wij dwingen geen grens op het aantal eigenschappen of zeer belangrijke paren af u in een lijn omvat.
>
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Bestandsvariabelen gedefinieerd {#file-variables-defined}

De tabel bevat een lijst met en definieert de variabelen die worden gebruikt in een bestand met correct opgemaakte binnenkomende gegevens. *Cursief* Hiermee wordt een tijdelijke aanduiding voor een variabele aangegeven.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabele </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Een gebruikersnaam kan: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Een unieke gebruikersnaam toegewezen door <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> UUID Audience Manager </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Een unieke gebruikersnaam die is toegewezen in uw CRM-systeem ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Een mobiele Android- of iOS-apparaat-id in de oorspronkelijke, ongewijzigde vorm zoals deze wordt weergegeven door het mobiele besturingssysteem. </li> 
     </ul> </p> <p>Voor mobiele id's: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA-indeling: Id's moeten hoofdletters/kleine letters zijn en geen hashes. Bijvoorbeeld, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android-indeling: Id's moeten kleine letters zijn en geen hashes. Bijvoorbeeld, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Scheid de gebruikers-id en de gebruikers-id met één tabscheidingsteken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> Audience Manager </span> traditie-id. Wij vragen u ook <i>alleen ongebogen eigenschappen</i> in binnenkomende gegevensbestanden. We verwerken geen andere typen eigenschappen in de binnenkomende gegevensoverdracht. </p> <p> <p>Opmerking: De Trait-id kunt u vinden met de methode GET die details over al uw kenmerken retourneert. Zie voor meer informatie <a href="../../../api/rest-api-main/api-traits.md"> Trait API-methoden </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Opmaak [!UICONTROL Trait IDs] {#formatting-trait-ids}

In de volgende tabel worden de voorvoegsels beschreven die [!UICONTROL trait] namen of id&#39;s in een binnenkomend gegevensbestand. Zie de [voorbeeldbestanden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) voor voorbeelden.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Voorvoegsel </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>De <code> d_sid </code> voorvoegsel vertelt ons systeem dat de id een <span class="keyword"> Audience Manager </span> traditie-id. Dit is dezelfde id die in de gebruikersinterface wordt weergegeven. U kunt ook standaard-id's retourneren met de API <code> GET </code> methode. Zie <a href="../../../api/rest-api-main/api-traits.md"> Trait API-methoden </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Gegevens voorafgegaan door <code> d_unsid </code> Hiermee verwijdert u gebruikers van die eigenschap. De <code> d_unsid </code> voorvoegsel wordt genegeerd in een <code> overwrite </code> bestand. </p> <p>De <code> d_unsid= </code> voorvoegsel vertelt ons systeem dat de id een <span class="keyword"> Audience Manager </span> traditie-id. Dit is dezelfde id die in de gebruikersinterface wordt weergegeven. U kunt ook standaard-id's retourneren met de API <code> GET </code> methode. Zie <a href="../../../api/rest-api-main/api-traits.md"> Trait API-methoden </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Handelsvoorschriften </a> laat u criteria voor vakkwalificatie plaatsen. Als u een gedragslijn opmaakt als <code> ic == trait ID </code>, kunt u in kenmerken verzenden in een eenvoudige lijst met komma's. </p> <p>Stel bijvoorbeeld dat u deze drie regels voor de eigenschap maakt: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Deze kenmerken zijn gekoppeld aan de <code> ic </code> toets. Zo kunt u een eenvoudigere lijst met eigenschappen maken in het gegevensbestand. En u hoeft de <code> ic </code> voorvoegsel. Hierdoor kan de inhoud van het gegevensbestand er als volgt uitzien: </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sleutelwaardeparen </p> </td> 
   <td colname="col2"> <p>De gegevens van het spoor kunnen als sleutel-waardeparen worden geformatteerd gebruikend alfanumerieke koorden. Er zijn verschillende manieren om sleutelwaardeparen op te maken, zoals hieronder wordt getoond: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> , <code> "gender"=m </code> , <code> model = "pickup truck" </code> , <code> product = tablet </code> Dit zijn allemaal voorbeelden van correct opgemaakte sleutelwaardeparen. </p> </td> 
  </tr>
 </tbody>
</table>

## Ongeldige tekens in [!UICONTROL Trait IDs], [!UICONTROL User IDs] en sleutelwaardeparen {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] bestaan alleen uit numerieke tekens. Wij vragen u ook *alleen[!UICONTROL onboarded traits]* in binnenkomende gegevensbestanden. We verwerken geen andere [!UICONTROL trait] typen in de binnenkomende gegevensoverdracht.

### [!UICONTROL User IDs]

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type id </th> 
   <th colname="col2" class="entry"> Vereiste </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>Niet gebruiken</i> een gecodeerde dubbele punt gebruiken ( <code> %3A </code>) of niet-gecodeerde dubbele punt ( : ) in DPUUIDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile iOS (IDFA) of Android-apparaat-id </p> </td> 
   <td colname="col2"> <p>Mobiele apparaat-id's moeten strikt zijn opgemaakt zoals hieronder wordt weergegeven: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA-indeling: Id's moeten hoofdletters/kleine letters zijn en geen hashes. Bijvoorbeeld, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android-indeling: Id's moeten kleine letters zijn en geen hashes. Bijvoorbeeld, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Belangrijke paren

Onjuist opgemaakte waardennamen in een sleutelwaardepaar veroorzaken ook problemen. Volg deze regels wanneer het creëren van of het noemen van de waarde in een zeer belangrijk-waardepaar:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Teken </th> 
   <th colname="col2" class="entry"> Vereiste </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Aanhalingsteken (") </p> </td> 
   <td colname="col2"> <p>U kunt het aanhalingsteken in de sleutel en in het waardegedeelte van sleutel-waardepaar als volgt gebruiken: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Streepje (-) </p> </td> 
   <td colname="col2"> <p>We negeren streepjesborden aan het begin van toetsen. Bijvoorbeeld: <code> -product = camera </code> wordt geïnterpreteerd als <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Niet gebruiken</i> gebruiken <code> TAB </code> in plaats van lege waarden in sleutelwaardeparen. Alleen gebruiken <code> TAB </code> om variabelen in het binnenkomende gegevensbestand te scheiden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>De nieuwe regel of tabtekens ( <code> \n, \t </code>) in toetsen of in waarden. </p> </td> 
  </tr>
 </tbody>
</table>

## Voorbeelden van gegevensbestanden {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gegevensbestandsindeling </th> 
   <th colname="col2" class="entry"> Beschrijving en voorbeeld </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Met <code> d_sid </code> of <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>In dit gegevensbestand wordt een gebruiker weergegeven die is gekwalificeerd voor de kenmerken 24, 26, 27 en die is verwijderd uit kenmerk 28 en 29. </p> <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;&nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Opmerking:  <p>In plaats van d_unsid te gebruiken, kunt u eigenschappen uit gebruikersprofielen ook verwijderen door de volgende syntaxis te gebruiken: </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:0,&nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:-1,&nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Met <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Deze kenmerken zijn toegevoegd aan een regel met eigenschappen <code> ic </code> voorvoegsel. Als zodanig kunt u ze toevoegen aan het gegevensbestand, gescheiden door komma's, zoals getoond. Een tabblad scheidt de UUID en de eigenschap-id's. De <code> ic </code> voorvoegsel is niet vereist in het bestand. </p> <p><b>Numerieke id's</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>Tekenreeks-id's</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Met sleutelwaardeparen </p> </td> 
   <td colname="col2"> In dit bestand worden sleutelwaardeparen gebruikt om gegevens door te geven aan <span class="keyword"> Audience Manager </span>. <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Downloaden](assets/ftp_dpm_1234_1445374061.overwrite) het bestand met voorbeeldgegevens als u meer voorbeelden nodig hebt. Het downloadbestand bevat een `.overwrite` bestandsextensie. U kunt het openen met een eenvoudige tekstverwerker.

## Voorbeeldmatrix {#examples-matrix}

In de onderstaande tabel ziet u voorbeelden van de juiste manier om uw binnenkomende bestanden op te maken, afhankelijk van de [type id&#39;s](../../../reference/ids-in-aam.md) en de methode waarmee u wilt toevoegen [!UICONTROL traits] naar profielen.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type id/bewerking </th> 
   <th colname="col2" class="entry"> D_ijd gebruiken om kenmerken toe te voegen aan een gebruikersprofiel </th> 
   <th colname="col3" class="entry"> G_unsid gebruiken om kenmerken uit een gebruikersprofiel te verwijderen </th> 
   <th colname="col4" class="entry"> Verzenden in sleutelwaardeparen om eigenschappen aan een gebruikersprofiel toe te voegen </th> 
   <th colname="col5" class="entry"> Gebruik het voorvoegsel ic om kenmerken aan een gebruikersprofiel toe te voegen </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID Audience Manager </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Voorbeeld 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Voorbeeld 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Voorbeeld 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Voorbeeld 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google-advertentie-id voor Android-apparaten </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Voorbeeld 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Voorbeeld 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Voorbeeld 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Voorbeeld 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA voor iOS-apparaten </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Voorbeeld 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Voorbeeld 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Voorbeeld 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Voorbeeld 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Je eigen CRM-id (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Voorbeeld 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Voorbeeld 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Voorbeeld 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Voorbeeld 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Voorbeeld 1 {#example-1}

Gebruiken [!UICONTROL trait IDs] om te verzenden [!UICONTROL trait] kwalificatiegegevens voor [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Voorbeeld 2 {#example-2}

Gebruiken [!UICONTROL trait IDs] om te verzenden [!UICONTROL trait] informatie over ontzetting voor [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

of

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

of

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Voorbeeld 3 {#example-3}

Verzenden in sleutelwaardeparen om toe te voegen [!UICONTROL trait] kwalificatiegegevens voor [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

of

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Voorbeeld 4 {#example-4}

Gebruik de `ic` voorvoegsel dat moet worden verzonden [!UICONTROL trait] kwalificatiegegevens voor [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

of

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Voorbeeld 5 {#example-5}

Gebruiken [!UICONTROL trait IDs] om te verzenden [!UICONTROL trait] kwalificatiegegevens voor [!DNL Android] apparaten.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Voorbeeld 6 {#example-6}

Gebruiken [!UICONTROL trait IDs] om te verzenden [!UICONTROL trait] informatie over ontzetting voor [!DNL Android] apparaten.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

of

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

of

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Voorbeeld 7 {#example-7}

Verzenden in sleutelwaardeparen om toe te voegen [!UICONTROL trait] kwalificatiegegevens voor [!DNL Android] apparaten.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

of

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Voorbeeld 8 {#example-8}

Gebruik de `ic` voorvoegsel dat moet worden verzonden [!UICONTROL trait] kwalificatiegegevens voor [!DNL Android] apparaten.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

of

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Voorbeeld 9 {#example-9}

Gebruiken [!UICONTROL trait IDs] om te verzenden [!UICONTROL trait] kwalificatiegegevens voor [!DNL iOS] apparaten.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Voorbeeld 10 {#example-10}

Gebruiken [!UICONTROL trait IDs] om te verzenden [!UICONTROL trait] informatie over ontzetting voor [!DNL iOS] apparaten.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

of

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

of

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Voorbeeld 11 {#example-11}

Verzenden in sleutelwaardeparen om toe te voegen [!UICONTROL trait] kwalificatiegegevens voor [!DNL iOS] apparaten.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

of

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Voorbeeld 12 {#example-12}

Gebruik de `ic` voorvoegsel dat moet worden verzonden [!UICONTROL trait] kwalificatiegegevens voor [!DNL iOS] apparaten.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

of

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Voorbeeld 13 {#example-13}

Gebruiken [!UICONTROL trait IDs] om te verzenden [!UICONTROL trait] kwalificatiegegevens voor [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Voorbeeld 14 {#example-14}

Gebruiken [!UICONTROL trait IDs] om te verzenden [!UICONTROL trait] informatie over ontzetting voor [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

of

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

of

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Voorbeeld 15 {#example-15}

Verzenden in sleutelwaardeparen om toe te voegen [!UICONTROL trait] kwalificatiegegevens voor [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

of

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Voorbeeld 16 {#example-16}

Gebruik de `ic` voorvoegsel dat moet worden verzonden [!UICONTROL trait] kwalificatiegegevens voor [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

of

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Eigenschapbuilder ](../../../features/traits/about-trait-builder.md)

