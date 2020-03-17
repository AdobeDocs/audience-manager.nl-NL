---
description: De vereiste gebieden, syntaxis, en regels u zouden moeten volgen wanneer het formatteren van een binnenkomend dossier van eigenschapsgegevens.
seo-description: De vereiste gebieden, syntaxis, en regels u zouden moeten volgen wanneer het formatteren van een binnenkomend dossier van eigenschapsgegevens.
seo-title: De binnenkomende Syntaxis van de Inhoud van het Dossier van Gegevens, Ongeldige Karakters, Variabelen, en Voorbeelden
solution: Audience Manager
title: De binnenkomende Syntaxis van de Inhoud van het Dossier van Gegevens, Ongeldige Karakters, Variabelen, en Voorbeelden
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Inhoud binnenkomend gegevensbestand: Syntaxis, ongeldige tekens, variabelen en voorbeelden{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

De vereiste gebieden, syntaxis, en regels u zouden moeten volgen wanneer het formatteren van een binnenkomend dossier van eigenschapsgegevens.

## Syntaxis bestandsinhoud {#file-content-syntax}

De velden in het binnenkomende gegevensbestand moeten in de hieronder getoonde orde verschijnen. In dit voorbeeld zijn de `<` `>` symbolen toegevoegd om elk element visueel te kunnen scheiden. U hoeft deze niet op te nemen in het gegevensbestand.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Voor andere toegelaten formaten van de dossierinhoud, zie de Integraties [van de Partner van de](/help/using/integration/sending-audience-data/custom-partner-integrations.md)Douane.

>[!NOTE]
>
>We hebben een limiet van 200 regels die we kunnen verwerken voor elke gebruikersnaam die in het binnenkomende gegevensbestand wordt verzonden. Als u bijvoorbeeld 300 regels verzendt voor een gebruikers-id, blijven de eerste 200 regels behouden en worden de extra 100 regels verwijderd. In het onderstaande voorbeeld kun je het beste drie regels verzenden voor gebruikers-id 1 en gebruikersnaam 2. Wij dwingen geen grens op het aantal eigenschappen of zeer belangrijke paren af u in een lijn omvat.
>
>
```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Bestandsvariabelen gedefinieerd {#file-variables-defined}

De tabel bevat een lijst met en definieert de variabelen die worden gebruikt in een bestand met correct opgemaakte binnenkomende gegevens. *Cursief* verwijst naar een variabele plaatsaanduiding.

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
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Een unieke gebruikers-id die is toegewezen door <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Een unieke gebruikersnaam die is toegewezen in uw CRM-systeem ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Een mobiele Android- of iOS-apparaat-id in het oorspronkelijke, ongewijzigde formulier zoals deze wordt weergegeven door het mobiele besturingssysteem. </li> 
     </ul> </p> <p>Voor mobiele id's: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA-indeling: Id's moeten hoofdletters/kleine letters zijn en geen hashes. Bijvoorbeeld: <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android-indeling: Id's moeten kleine letters zijn en geen hashes. Bijvoorbeeld: <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Scheid de gebruikers-id en de gebruikers-id met één tabscheidingsteken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> </span> statusID van Audience Manager. Wij vragen dat u <i>slechts ongebogen eigenschappen</i> in binnenkomende gegevensdossiers opneemt. We verwerken geen andere typen eigenschappen in de binnenkomende gegevensoverdracht. </p> <p> <p>Opmerking:  De Trait ID kan worden gevonden door de GET methode te gebruiken die details over al uw eigenschappen terugkeert. Zie <a href="../../../api/rest-api-main/api-traits.md"> Trait API-methoden </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait-id&#39;s opmaken {#formatting-trait-ids}

In de volgende tabel worden de voorvoegsels beschreven waarmee de namen van kenmerken of id&#39;s in een binnenkomend gegevensbestand worden geïdentificeerd. Zie de [voorbeeldbestanden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) voor voorbeelden.

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
   <td colname="col2"> <p>Het <code> d_sid </code> voorvoegsel vertelt ons systeem dat identiteitskaart een het dienstitelID van de Manager van de <span class="keyword"> Publiek is </span> . Dit is dezelfde id die in de gebruikersinterface wordt weergegeven. U kunt ook doel-id's retourneren met de API- <code> GET </code> methode. Zie <a href="../../../api/rest-api-main/api-traits.md"> Trait API-methoden </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Gegevens die vooraf met zijn vastgesteld, <code> d_unsid </code> verwijderen gebruikers uit die eigenschap. Het <code> d_unsid </code> voorvoegsel wordt genegeerd in een <code> overwrite </code> bestand. </p> <p>Het <code> d_unsid= </code> voorvoegsel vertelt ons systeem dat identiteitskaart een het dienstitelID van de Manager van de <span class="keyword"> Publiek is </span> . Dit is dezelfde id die in de gebruikersinterface wordt weergegeven. U kunt ook doel-id's retourneren met de API- <code> GET </code> methode. Zie <a href="../../../api/rest-api-main/api-traits.md"> Trait API-methoden </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> De regels van het spoor </a> laten u criteria voor het vakkwalificatie plaatsen. Als u een treklijn als <code> ic == trait ID </code>formatteert, kunt u in eigenschappen in een eenvoudige komma geformatteerde lijst verzenden. </p> <p>Stel bijvoorbeeld dat u deze drie regels voor de eigenschap maakt: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Deze kenmerken zijn gekoppeld aan de <code> ic </code> toets. Zo kunt u een eenvoudigere lijst met eigenschappen maken in het gegevensbestand. U hoeft het <code> ic </code> voorvoegsel niet op te nemen. Hierdoor kan de inhoud van het gegevensbestand er als volgt uitzien: </p> <p>
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
     </ul><code> "age"="32" </code> , <code> "gender"=m </code> , <code> model = "pickup truck" </code> , <code> product = tablet </code> zijn alle voorbeelden van correct opgemaakte sleutel-waardeparen. </p> </td> 
  </tr>
 </tbody>
</table>

## Ongeldige tekens in vak-id&#39;s, gebruikers-id&#39;s en sleutelwaardeparen {#invalid-chars}

### Trait-id&#39;s

Trait-id&#39;s bestaan alleen uit numerieke tekens. Wij vragen dat u *slechts ongebogen eigenschappen* in binnenkomende gegevensdossiers opneemt. We verwerken geen andere typen eigenschappen in de binnenkomende gegevensoverdracht.

### Gebruikersnamen

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
   <td colname="col2"> <p><i>Gebruik geen</i> gecodeerde dubbele punt ( <code> %3A </code>dubbele punt) of niet-gecodeerde dubbele punt ( : ) in DPUUIDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobiele iOS (IDFA) of Android-apparaat-id </p> </td> 
   <td colname="col2"> <p>Mobiele apparaat-id's moeten strikt zijn opgemaakt zoals hieronder wordt weergegeven: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA-indeling: Id's moeten hoofdletters/kleine letters zijn en geen hashes. Bijvoorbeeld: <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android-indeling: Id's moeten kleine letters zijn en geen hashes. Bijvoorbeeld: <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
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
   <td colname="col2"> <p>We negeren streepjesborden aan het begin van toetsen. Bijvoorbeeld, <code> -product = camera </code> wordt geïnterpreteerd als <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Gebruik geen</i> lege waarden <code> TAB </code> in sleutelwaardeparen. Alleen gebruiken <code> TAB </code> om variabelen in het binnenkomende gegevensbestand te scheiden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>Gebruik de nieuwe regel of tabtekens ( <code> \n, \t </code>) niet in toetsen of in waarden. </p> </td> 
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
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Opmerking:  <p>In plaats van d_unsid te gebruiken, kunt u eigenschappen uit gebruikersprofielen ook verwijderen door de volgende syntaxis te gebruiken: </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Met <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Deze kenmerken zijn aan een treklijn met het <code> ic </code> voorvoegsel toegevoegd. Als zodanig kunt u ze toevoegen aan het gegevensbestand, gescheiden door komma's, zoals getoond. Een tabblad scheidt de UUID en de eigenschap-id's. Het <code> ic </code> voorvoegsel is niet vereist in het bestand. </p> <p><b>Numerieke id's</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>Tekenreeks-id's</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Met sleutelwaardeparen </p> </td> 
   <td colname="col2"> In dit bestand worden sleutelwaardeparen gebruikt om gegevens door te geven aan <span class="keyword"> Audience Manager </span>. <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Download](assets/ftp_dpm_1234_1445374061.overwrite) het bestand met voorbeeldgegevens als u meer voorbeelden nodig hebt. Het downloadbestand heeft een `.overwrite` bestandsextensie. U kunt het openen met een eenvoudige tekstverwerker.

## Voorbeeldmatrix {#examples-matrix}

In het onderstaande diagram ziet u voorbeelden van de juiste manier om uw binnenkomende bestanden op te maken, afhankelijk van het [type id](../../../reference/ids-in-aam.md) &#39;s en de methode waarmee u kenmerken aan profielen wilt toevoegen.

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
   <td colname="col1"> <p>UUID van Audience Manager </p> </td> 
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
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Voorbeeld 10 </a> </p> </td> 
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

Gebruik standaard-id&#39;s om de kwalificatiegegevens van het kenmerk te verzenden voor UUID&#39;s van Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Voorbeeld 2 {#example-2}

Gebruik de eigenschap IDs om de informatie van de onvolkomenheden van de Manager UUIDs van de Audience te verzenden.

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

Verzend in sleutel-waardeparen om de informatie van de eigenschapkwalificatie voor de Manager UUIDs van de Publiek toe te voegen.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

of

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Voorbeeld 4 {#example-4}

Gebruik het voorvoegsel van de ic om de informatie van de trekkenkwalificatie voor de Manager UUIDs van de Publiek te verzenden.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

of

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Voorbeeld 5 {#example-5}

Gebruik de kenmerk-id&#39;s om kwalificatiegegevens voor kenmerken van Android-apparaten te verzenden.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Voorbeeld 6 {#example-6}

Gebruik de standaard-id&#39;s om informatie over de onvolledige erkenning van onderdelen naar Android te verzenden.

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

Verzenden in sleutelwaardeparen om kwalificatiegegevens voor eigenschappen voor Android-apparaten toe te voegen.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

of

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Voorbeeld 8 {#example-8}

Gebruik het voorvoegsel ic om kwalificatiegegevens voor eigenschappen voor Android-apparaten te verzenden.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

of

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Voorbeeld 9 {#example-9}

Gebruik standaard-id&#39;s om kwalificatiegegevens voor kenmerken voor iOS-apparaten te verzenden.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Voorbeeld 10 {#example-10}

Gebruik de kenmerk-id&#39;s om informatie over onvolledige erkenning voor iOS-apparaten te verzenden.

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

### Voorbeeld 10 {#example-11}

Verzenden in sleutelwaardeparen om kenmerkgegevens voor iOS-apparaten toe te voegen.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

of

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Voorbeeld 12 {#example-12}

Gebruik het voorvoegsel ic om kwalificatiegegevens over eigenschappen voor iOS-apparaten te verzenden.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

of

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Voorbeeld 13 {#example-13}

Gebruik de standaard-id&#39;s om de kwalificatiegegevens van de eigenschap voor DPUUID&#39;s te verzenden.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Voorbeeld 14 {#example-14}

Gebruik de standaard-id&#39;s om informatie over onvolledige erkenning voor DPUUID&#39;s te verzenden.

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

Verzend in sleutel-waardeparen om de informatie van de eigenschapkwalificatie voor DPUUIDs toe te voegen.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

of

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Voorbeeld 16 {#example-16}

Gebruik het voorvoegsel ic om kwalificatiegegevens voor eigenschappen voor DPUUIDs te verzenden.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

of

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Trait Builder](../../../features/traits/about-trait-builder.md)

