---
description: Hiermee geeft u een overzicht en beschrijving van de syntaxis en ondersteunde kenmerken (of sleutelwaardeparen) die u kunt doorgeven aan de gegevensverzamelingsservers (DCS). Deze informatie kan u helpen uw DCS- verzoeken formatteren en de parameters begrijpen die door dit systeem zijn teruggekeerd.
seo-description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-title: Supported Attributes for DCS API Calls
solution: Audience Manager
title: Ondersteunde kenmerken voor DCS API-aanroepen
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_d ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: e10211057a87622340fd2c61737c7c7a45c0e99c
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 1%

---

# Ondersteunde kenmerken voor aanroepen [!DNL DCS] [!DNL API] {#supported-attributes-for-dcs-api-calls}

Hiermee geeft u een overzicht en beschrijving van de syntaxis en ondersteunde kenmerken (of sleutelwaardeparen) die u kunt doorgeven aan [!UICONTROL Data Collection Servers] ([!DNL DCS]). Met deze informatie kunt u uw [!DNL DCS] -aanvragen opmaken en de parameters begrijpen die door dit systeem worden geretourneerd.

## Kenmerkvoorvoegsels {#attribute-prefixes}

[!DNL DCS] baseert zich op specifieke prefixen die aan de sleutels in zeer belangrijke-waardeparen worden toegevoegd om het type van gegevens te classificeren u binnen overgaat.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Hoofdvoorvoegsel </th> 
   <th colname="col2" class="entry"> Gereserveerd voor </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>Door de klant gedefinieerde kenmerken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager </span> -kenmerken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP-headergegevens. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Persoonlijke, door de klant gedefinieerde kenmerken. </p> <p> De DCS accepteert uw eigen, persoonlijke gegevens wanneer de toets een voorvoegsel <code> p_</code> heeft. De privé gegevens worden gebruikt voor karakterevaluatie, maar het zal niet in ons systeem worden geregistreerd of worden opgeslagen. Hier kunt u bijvoorbeeld zeggen dat een eigenschap is gedefinieerd als <code> customers = p_age&lt;25</code> en dat u <code> p_age=23</code> doorgeeft in een gebeurtenisaanroep. Gezien deze voorwaarden, kwalificeert de gebruiker die aan de op leeftijd-gebaseerde kwalificatiecriteria voldoet voor het bezit, maar het sleutel-waarde paar wordt gelaten vallen nadat <span class="keyword"> Audience Manager </span> het verzoek ontvangt en niet het programma wordt geopend. </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] Kenmerken {#d-attributes}

Al deze opties zijn optioneel, tenzij u een reactie van de [!DNL DCS] wilt. Als u wilt dat de [!DNL DCS] een reactie retourneert, is `d_rtbd=json` vereist.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kenmerk </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p>Gebruikt om de bezoeker te identificeren die de vraag aan <span class="wintitle"> DCS </span> API maakt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Geeft een JavaScript-functie op die u wilt uitvoeren met de <span class="wintitle"> DCS </span> -reactie als een functieparameter van de callback-functie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Bevat één of meerdere paren van gegevensleverancier IDs (<code> DPID</code>) en gegevensleverancier gebruiker IDs (<code> DPUUID</code>) die door <span class="keyword"> Audience Manager </span> wordt toegewezen. Als u veelvoudige paren van <code> DPID</code> s en <code> DPUUID</code> s gebruikt, scheidt elk paar met het niet-druk karakter <code> %01</code>. Bijvoorbeeld: <code><i>DPID</i>%01<i>DPUUUID</i></code> . </p> <p><code> d_cid</code> vervangt <code> d_dpid</code> en <code> d_dpuuid</code> , die zijn afgekeurd maar nog steeds worden ondersteund. Zie <a href="../../../reference/cid.md"> CID vervangt DPID en DPUUID </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Bevat een integratiecode en een bijbehorende unieke gebruiker - identiteitskaart in één enkel zeer belangrijk-waardepaar. </p> <p><code> d_cid_ic</code> vervangt <code> d_dpid</code> en <code> d_dpuuid</code> , die zijn afgekeurd maar nog steeds worden ondersteund. Zie <a href="../../../reference/cid.md"> CID vervangt DPID en DPUUID </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Schakel het gebruik van cookies van derden uit om te voldoen aan de voorschriften voor kinderbescherming. Deze parameter wordt dynamisch ingesteld door de Adobe Adobe Experience Platform Identity Service en is afhankelijk van de <code> idSyncDisable3rdPartySyncing</code> -configuratie. Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/coppa.html?lang=nl-NL" format="https" scope="external"> Steun COPPA in de Dienst van de Identiteit van Adobe Experience Platform </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Optioneel. Ingeschakeld op verzoek van klant. Neem contact op met uw Adobe Audience Manager-consultant of klantenservice. </p> <p>Geeft aan dat kenmerken en segmenten moeten worden geretourneerd binnen het antwoord <code> JSON</code> . </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> keert <a href="../../../reference/ids-in-aam.md"> verouderde segment IDs </a> voor de segmenten terug. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> keert segment IDs voor de segmenten terug. </p> </li>
     </ul> </p> <p>Een voorbeeldreactie kan er als volgt uitzien: </p> <p>
     <code class="syntax javascript">
      &lbrace;
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      &rbrace;
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>Vervangen. Zie <code> d_cid</code> en <code> d_cid_ic</code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Vervangen. Zie <code> d_cid</code> en <code> d_cid_ic</code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>Retourneert URL-doelgegevens in het <code> JSON</code> -antwoord. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> is een gereserveerd kenmerk dat wordt gebruikt bij de integratie tussen Adobe Analytics en Audience Manager. </p> <p>We raden u af om kenmerken te maken die gereserveerde kenmerken gebruiken. Adobe kan gereserveerde kenmerken te allen tijde wijzigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Geeft de <code> JSON</code> -versie aan die in het antwoord moet worden gebruikt. Normaal gesproken moet u dit instellen op <code> d_jsonv=1</code> . Door <code> d_jsonv=0</code> in te stellen, worden id-syncs uitgeschakeld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Geeft de Experience Cloud-id op die wordt ingesteld en gebruikt door de <span class="keyword"> Experience Cloud </span> -id-service. Voor meer informatie over ECID, zie <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=nl-NL" format="https" scope="external"> Cookies en de Dienst van de Identiteit van Experience Cloud </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>Naam ruimte-id. Geeft aan welke JavaScript-container wordt gebruikt. Wordt gebruikt door <span class="wintitle"> DIL </span> voor id-synchroniseren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Hiermee kan Audience Manager mobiele aanvragen onderscheiden van desktopaanvragen. Tot de ondersteunde waarden behoren: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Vervangen. <code> d_rs</code> is een gereserveerd attribuut, dat in de erfenisintegratie tussen <span class="keyword"> Adobe Analytics </span> en <span class="keyword"> Audience Manager </span> wordt gebruikt. </p> <p>We raden u af om kenmerken te maken die gereserveerde kenmerken gebruiken. Adobe kan gereserveerde kenmerken te allen tijde wijzigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Vereist als u een <code> JSON</code> reactie van <span class="wintitle"> DCS </span> wilt. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Als u dit weglaat, keert <span class="wintitle"> DCS </span> een pixel in de kopbal terug. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Als u dit opneemt, retourneert de <span class="wintitle"> DCS </span> een <code> JSON</code> -object in de hoofdtekst van de reactie. Zie het onderstaande voorbeeld. Uw reactie kan complexer zijn. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      &lbrace;
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      &rbrace;
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> staat voor <span class="term"> score ID </span>. Dit is een unieke id voor een kenmerk of segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Hiermee geeft u een gegevensbron door voor de evaluatie van het kenmerk. Alleen de eigenschappen van deze gegevensbron worden geëvalueerd. </p> <p>Stel dat u het volgende hebt: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b> Spoor T1 </b> met: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Trait rule: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Data Source (<a href="../../../reference/ids-in-aam.md"> DPID </a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID-integratiecode: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b> Spoor T2 </b> met: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Trait rule: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Data Source (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID-integratiecode: ic2 </li> 
     </ul> </p> <p>In een steekproefvraag, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, slechts wordt de eigenschap T1 teruggegeven. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>Het doel is gelijk aan de parameter <code> d_tdpid</code> die hierboven wordt beschreven. In dit geval wordt de gegevensbron echter doorgegeven met behulp van de integratiecode. </p> <p>Houd de hierboven beschreven kenmerken in acht en bekijk de voorbeeldvraag: </p> <p>Voor <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code> wordt alleen de eigenschap T2 geretourneerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>Unieke gebruikersnaam. Hiermee wordt een bezoeker aangegeven wanneer deze waarde niet beschikbaar is in een cookie. </p> </td> 
  </tr>
 </tbody>
</table>

## h_ Attributen

Deze kopballen bevatten informatie zoals verzoeken om gegevens en reacties in een vraag van HTTP.

| Kenmerk | Beschrijving |
| --- | --- | 
| `h_host` | Deze wordt ingesteld op de specifieke hostnaam van de gegevensverzameling van de client. De naam wordt weergegeven als `host name .demdex.net` . Zie [Inzicht in calls naar het Demdex-domein](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=nl-NL). |
| `h_user-agent` | Instellen op de headerwaarde `User-Agent` . |
| `h_accept-language` | Instellen op de headerwaarde `Accept-Language` . |
| `h_referer` | Instellen op de headerwaarde `Referer` . |
| `h_referrer` | Instellen op de headerwaarde `Referrer` . |
| `h_date` | Instellen op de headerwaarde `Date` . |