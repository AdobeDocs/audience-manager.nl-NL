---
description: Foutcodes en berichten die worden gegenereerd door de gegevensverzamelingsservers (DCS) in numerieke volgorde op basis van code-id.
title: DCS-foutcodes, berichten en voorbeelden
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '1517'
ht-degree: 2%

---

# DCS-foutcodes, berichten en voorbeelden {#dcs-error-codes-messages-and-examples}

Foutcodes en berichten die worden gegenereerd door de [!UICONTROL Data Collection Servers] ([!DNL DCS] ) in numerieke volgorde op basis van code-id.

In de lijsten hieronder, *cursief* vertegenwoordigt veranderlijke placeholder.

## Systeemfoutcodes {#system-error-codes}

| Foutcode | Foutbericht | Beschrijving |
|---|---|---|
| 0 | Onbekende fout | Dit is een catch-all fout die gebeurtenissen behandelt die niet door de andere foutenmanagers worden behandeld. Problemen met deze fout zijn moeilijk op te lossen. Het kan worden veroorzaakt door een verscheidenheid van onbekende acties of gebeurtenissen. Als deze fout optreedt, probeert u het [!DNL DCS] -verzoek nogmaals uit. Neem contact op met uw [!DNL Adobe] -vertegenwoordiger als het probleem zich blijft voordoen. |
| 1 | Kan configuratie voor hostnaam niet vinden: `hostname` | De gastheernaam die in het verzoek wordt verzonden is niet opstelling door ons team van de partnerlevering. Neem contact op met uw [!DNL Adobe] -vertegenwoordiger als dit foutbericht wordt weergegeven. |
| 2 | Ongeldige `d_orgid` waarde (kan geen config voor deze org-id vinden): `ID` | De organisatie-id is onjuist. Controleer uw id en probeer het verzoek opnieuw. Als u niet kent of uw identiteitskaart van de Organisatie hebt, zie de &quot;pagina van het Beleid&quot;sectie [ Organisaties en rekening die ](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) verbinden voor informatie over hoe te om het te vinden. |
| 10 | Kan kenmerken niet evalueren | De kenmerken van het verzoek zijn gedeeltelijk of helemaal niet beoordeeld. Neem contact op met uw [!DNL Adobe] -vertegenwoordiger als het probleem zich blijft voordoen. |

## Integratiefoutcodes {#integration-error-codes}

| Foutcode | Foutbericht | Beschrijving |
|---|---|---|
| 100 | Kan de hostnaam voor de aanvraag niet ophalen | Een [!DNL API] -aanroep heeft de host [!DNL HTTP] -header in de aanvraag niet verzonden. Voeg de gastheerkopbal aan de vraag toe en probeer opnieuw. De meeste browsers en [!DNL API] clients doen dit automatisch. |
| 101 | Ongeldige [!DNL Experience Cloud] id doorgegeven in `ID` | De aanroep van [!DNL DCS] bevat een ongeldige [!DNL Experience Cloud] ID. Controleer het sleutelwaardepaar `d_mid=` in de koptekstreeks. Geef de juiste [!DNL Experience Cloud] id door en probeer het verzoek opnieuw. |
| 102 | Ongeldige [!DNL AAM ID] doorgegeven in aanvraag `ID` | De aanroep van [!DNL DCS] bevat een ongeldige [!DNL Audience Manager] ID. Controleer het sleutelwaardepaar `d_uuid=` in de koptekstreeks. Geef de juiste [!DNL Audience Manager] id door en probeer het verzoek opnieuw. |
| 104 | Alle klant-id&#39;s zijn ongeldig | Alle klant IDs in uw vraag is ongeldig. Controleer uw id&#39;s en probeer het opnieuw. |
| 109 | Verwijzing `HTTP referer` is niet toegestaan voor partner `Partner ID` | De `HTTP referer` kopbal op de vraag wordt niet toegestaan voor partneridentiteitskaart op de vraag. Controleer of de koptekst van `HTTP referer` juist is. |
| 111 | Ongeldige token `IMS` ontvangen | Geretourneerd voor [!DNL Audience Manager] - [!DNL Adobe Target] integratie. De fout wordt gegenereerd wanneer een aanroep wordt gemaakt naar de [!DNL DCS] , die een ongeldig [!DNL IMS] -token bevat. Het token kan onjuist zijn geformuleerd, verlopen of de gebruiker is mogelijk niet gemachtigd om toegang te krijgen tot de vereiste resource. |

## Foutcodes voor uitschakelen {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code-id </th> 
   <th colname="col2" class="entry"> Bericht </th> 
   <th colname="col3" class="entry"> Beschrijving </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Label voor uitschakelen aangetroffen voor id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Een klant heeft ervoor gekozen geen op rente gebaseerde reclame te ontvangen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Geblokkeerde cookies </p> </td> 
   <td colname="col3"> <p>Wordt geretourneerd wanneer cookies van derden door de browser van de gebruiker worden geblokkeerd.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Betrokken vertrouwensrelatie via <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI </a> </p> </td> 
   <td colname="col3"> <p>De gebruiker heeft een opt-outproces door NAI in werking gesteld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Verzoeken vanuit dit land worden geblokkeerd door de partner </p> </td> 
   <td colname="col3"> <p>Gebaseerd op het IP adres, <span class="wintitle"> DCS </span> blokkeert verzoeken van landen waar de partner opzettelijk het verkeer heeft beperkt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Verzoeken vanuit dit land zijn niet toegestaan </p> </td> 
   <td colname="col3"> <p>Gebaseerd op het IP adres, <span class="wintitle"> DCS </span> blokkeert verzoeken van de volgende landen: </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">Cuba (CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">Iran (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">Noord-Korea (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">Soedan (SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">Syrië (SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Foutcodes voor het ophalen van profielen {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code-id </th> 
   <th colname="col2" class="entry"> Bericht </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> Kan eigenschappen van profielcache voor id niet lezen: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wordt geretourneerd wanneer een gebruikersprofiel niet kan worden gelezen uit onze interne opslag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Kan geen apparaat-id lezen uit profielcache voor klant-id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Geretourneerd wanneer <a href="../../../reference/ids-in-aam.md"> apparaat identiteitskaart </a> niet voor een de fusieregel van de Verbinding van het Profiel kan worden teruggewonnen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Kan verwante klant voor apparaat-id niet lezen: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Geretourneerd wanneer <a href="../../../reference/ids-in-aam.md"> klant ID (UUID) </a> verbonden aan een apparatenidentiteitskaart niet voor een Laatste Voor authentiek verklaarde fusieregel van onze interne opslag kan worden teruggewonnen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Kan apparaatcluster voor id niet lezen: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>De gekoppelde apparaat-id's van dezelfde apparaatgrafiekcluster kunnen niet worden geretourneerd voor deze apparaat-id. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Kan migratie niet uitvoeren omdat het lezen van het profiel voor het primaire apparaat is mislukt </p> </td> 
   <td colname="col3"> <p>Als u deze fout ontvangt, kunnen wij scalability kwesties met onze gegevensopslag (<span class="wintitle"> PCS </span>) ervaren. Neem contact op met uw Adobe-vertegenwoordiger als het probleem zich blijft voordoen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Kan de migratie van <code><i>ID</i></code> naar <code><i>ID</i></code> niet uitvoeren, omdat het lezen van het profiel is mislukt voor <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Als u deze fout ontvangt, kunnen wij scalability kwesties met onze gegevensopslag (<span class="wintitle"> PCS </span>) ervaren. Neem contact op met uw Adobe-vertegenwoordiger als het probleem zich blijft voordoen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Waarschuwingscodes voor integratie {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code-id </th> 
   <th colname="col2" class="entry"> Bericht </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>Ongeldige klant-id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>De klant-id is ongeldig (ontbrekende waarden voor gegevensbron, ontbrekende integratiecodes, ongeldige indeling voor gegevensbronnen, geblokkeerde klant-id, lege klant-id, poging tot onbevoegde toegang tot een gegevensbron die niet bij de partner hoort). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Maximum aantal klantgegevens is overschreden. Maximaal toegestaan is <code><i>maximum allowed</i></code> . Gevonden is <code><i>maximum found</i></code> .</p> </td> 
   <td colname="col3"> <p>Het aantal klant-id's dat aan een apparaatgegevensbron is gekoppeld, overschrijdt het toegestane aantal apparaat-id's per aanvraag. Deze id's bevatten onder andere id's voor andere apparaten, mobiele apparaten of cookies. De limiet is momenteel ingesteld op 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Niet-geautoriseerde klant-id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wordt geretourneerd wanneer de gegevensbron van de klant-id niet het eigendom is van de huidige organisatie-id. Als u uw organisatie-id niet kent of hebt, raadpleegt u de sectie 'Uw organisatie-id zoeken' in <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisaties en accountkoppeling </a> voor informatie over het zoeken naar deze id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Geblokkeerde klant-id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wordt geretourneerd wanneer de klant-id als kwaadaardig is geïdentificeerd en aan een lijst van gewezen personen is toegevoegd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Id van geblokkeerde gegevensbron <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Geretourneerd wanneer gegevensbron ID als kwaadwillig is geïdentificeerd en aan een lijst van gewezen personen is toegevoegd </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Geblokkeerde gedeclareerde apparaat-id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Apparaatidentiteitskaart is geïdentificeerd als kwaadwillig en toegevoegd aan een lijst van gewezen personen Dit kan gebeuren wanneer wij een extreme hoeveelheid <span class="wintitle"> DCS </span> verzoeken ontvangen die deze apparatenidentiteitskaart in een korte hoeveelheid tijd bevatten. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Geblokkeerde profielbewerking voor <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Een lees-/schrijfactie is geblokkeerd omdat een id is geïdentificeerd als kwaadaardig en is toegevoegd aan een lijst van gewezen personen Zie foutcode 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Klantnummer <code><i>ID</i></code> is verwijderd omdat deze de limiet van opgegeven klantid's per aanvraag overschrijdt </p> </td> 
   <td colname="col3"> <p>Verwant aan fout 301. Deze fout geeft aan welke klant-id is verwijderd omdat de limiet is overschreden. </p> <p>Bijvoorbeeld, als er 12 klant IDs gedeclareerd op de <span class="wintitle"> DCS </span> vraag zijn, zullen twee van hen worden verworpen. Om door te geven welke zijn genegeerd, wordt deze fout twee keer weergegeven in de reactie (één keer voor elke verwijderde klant-id ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Id van klant is verwijderd omdat deze de limiet voor een bepaalde naamruimte overschrijdt. Naamruimte-id is <code><i>ID</i></code> , klant-id is <code><i>ID</i></code> . </p> </td> 
   <td colname="col3"> <p>Deze foutencode is teruggekeerd als er meer dan 3 klant IDs voor zelfde namespace (<code> DPID</code>) op een <span class="wintitle"> DCS </span> vraag wordt verklaard. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one </code> </p> <p>In dit voorbeeld <span class="wintitle"> DCS </span> verzoek, zijn er 4 die identiteitskaart voor zelfde namespace (met de integratiecode wordt verklaard). Een van de id's wordt verwijderd en fout 310 wordt geretourneerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>Verzoek bevat ongeldige parameters </p> </td> 
   <td colname="col3"> <p><span class="wintitle"> DCS </span> keert deze foutencode terug wanneer minstens één parameter URL niet behoorlijk wordt gecodeerd. In dit geval negeert <span class="wintitle"> DCS </span> het volledige verzoek. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>In de voorbeeldaanvraag hierboven is de <code> %</code> -reeks onjuist gecodeerd. Daarom zal <span class="wintitle"> DCS </span> het negeren. </p> <p>Het correct gecodeerde monster zou als dit moeten kijken: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>Aanvraag bevat een ongeldige globale apparaat-id </p> </td> 
   <td colname="col3"> <p><span class="wintitle"> DCS </span> keert deze foutencode terug wanneer het verzoek een ongeldige Globale identiteitskaart van het Apparaat bevat. DCS negeert de ongeldige identiteitskaart en werpt een fout 312 samen met de specifieke fouten van ongeldige identiteitskaart Verwijs naar <a href="../../../features/global-data-sources.md" format="dita" scope="local"> Globale Gegevensbronnen </a> en <a href="../../../reference/ids-in-aam.md" format="dita" scope="local"> Index van IDs in Audience Manager </a> voor gedetailleerde informatie over de correcte formaten van identiteitskaart van de apparatenreclame en overeenkomstige globale gegevensbronnen.</p>
   <p>Voorbeeld van een onjuiste aanroep: <code>"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Uitleg: Een <span class="keyword"> IDFA (DPID 20915) </span> moet een hoofdletteridentiteitskaart zijn. De id in het verzoek is in kleine letters.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>CMP-id is niet aanwezig in GCL</p> </td> 
   <td colname="col3"> <p>Wanneer <code>gdpr=1</code> en de IAB TC-tekenreeks worden gegenereerd door een CMP-id die op het moment van de evaluatie niet aanwezig is in een Audience Manager-versie in de cache van de Global CMP List, verwijdert de Audience Manager-plug-in voor IAB TCF de IAB TC-tekenreeks en verwerkt deze aanvraag op de gebruikelijke manier. De IAB TCF v2.2 $ {GDPR} macro wordt geplaatst aan 0 en $ {GDPR_CONSENT_XXX} macro is leeg.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP-id is gemarkeerd als verwijderd in GCL</p> </td> 
   <td colname="col3"> <p>Wanneer <code>gdpr=1</code> en het koord IAB TC door CMP wordt geproduceerd die zoals geschrapt in onze caching versie van de Globale CMP Lijst wordt duidelijk, verwerpt de stop-binnen van Audience Manager voor IAB TCF de koord TC en verwerkt het verzoek zoals gebruikelijk, als de evaluatietijd voorbij de schrappingstijd van de Globale CMP Lijst is. De IAB TCF v2.2 $ {GDPR} macro wordt geplaatst aan 0 en $ {GDPR_CONSENT_XXX} macro is leeg.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>Constante tekenreeks geeft aan dat er geen toestemming is</p> </td> 
   <td colname="col3"> <p>Wanneer geen toestemming wordt verstrekt, opteert de stop-binnen van Audience Manager voor IAB TCF de gebruiker uit verdere gegevensinzameling, of laat vallen volledig de vraag als er geen partnercontext wordt ontdekt.</p>
   </td>
  </tr>

</tbody>
</table>

## Voorbeeldfoutcode voor berichten {#sample-error-codes}

De [!DNL DCS] retourneert foutcodes en berichten in een [!DNL JSON] -object of in een X-header in de HTTP-antwoordtekenreeks.

### Voorbeeld-DCS-foutcode en -bericht

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-fout

Foutcodes die door de X-header worden vastgelegd, worden als volgt in de URL-tekenreeks weergegeven, `X-Error: 101,102` .

[Voorwaarden van ruimte en foutafhandeling](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
