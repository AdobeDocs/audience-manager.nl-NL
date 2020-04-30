---
description: Hoe gedeclareerde id's werken, instellingsprocedures, codevoorbeelden en variabelen.
keywords: id sync
seo-description: Hoe gedeclareerde id's werken, instellingsprocedures, codevoorbeelden en variabelen.
seo-title: Opgegeven id's
solution: Audience Manager
title: Opgegeven id's
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Opgegeven id&#39;s {#declared-ids}

Hoe gedeclareerde id&#39;s werken, instellingsprocedures, codevoorbeelden en variabelen.

## Waarschuwing voor gedeclareerde id {#declared-id-targeting}

U kunt gebruikers-id&#39;s uitwisselen en synchroniseren met Audience Manager vanaf apparaten of browsers die geen permanente opslagmechanismen, zoals cookies van derden, gebruiken of accepteren.

<!-- declared_id_about.xml -->

## Doel van opgegeven ID-activering {#declared-id-targeting-purpose}

Sommige browsers en de meeste mobiele apparaten accepteren cookies van derden niet. Hierdoor is het moeilijk om informatie over sitebezoekers te behouden of permanente id&#39;s toe te wijzen. Om dit probleem op te lossen, gebruikt de Manager van de Publiek [!UICONTROL DIL] [!UICONTROL declared IDs] om u binnen op een gebeurtenisvraag te laten overgaan. Een id [!UICONTROL declared ID] kan ook fungeren als een universele id die van toepassing is op dezelfde gebruiker voor alle oplossingen in de toepassing [!DNL Experience Cloud]. In de volgende tabel wordt het proces beschreven voor het zoeken naar en zoeken naar id&#39;s.

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Proces </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Gebeurtenisoproep</b> </td> 
   <td colname="col2"> <p>Als u wilt werken, hebt u <span class="wintitle"> DIL </span> en de code voor de identiteitsservice van <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> </a> Adobe Experience Platform op de pagina nodig. <span class="wintitle"> DIL </span> krijgt gedeclareerde id's <span class="wintitle"> van de </span> functie die wordt geleverd door de <code> setVisitorID </code> Adobe Experience Platform Identity Service <span class="keyword"> en geeft deze door aan </span> Audience Manager <span class="keyword"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identiteitskaart afstemmen</b> </td> 
   <td colname="col2"> <p>Audience Manager probeert de client- en bezoekersidentiteitskaart te koppelen aan een bijbehorende id in ons systeem. Als er geen overeenkomende id bestaat, maakt Audience Manager een nieuwe id en koppelt deze aan de client- en bezoekersidentiteitskaart. </p> <p> <p>Opmerking:  De meest recente toewijzing wordt gebruikt als uw identiteitskaart aan meer dan één identiteitskaart van de Manager van de Publiek toewijst. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Return-id</b> </td> 
   <td colname="col2"> <p>Audience Manager schrijft de gesynchroniseerde id naar een cookie van de eerste partij (of een andere opslagruimte voor geadresseerden) in het clientdomein of de toepassing. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Volgende gebeurtenisaanroepen</b> </td>
   <td colname="col2"> <p>De extra gebeurtenisvraag leest identiteitskaart van de Manager van de Publiek van het domein van de cliënt en verzendt dat naar de Manager van de Publiek. </p> </td>
  </tr> 
 </tbody>
</table>

Om te beginnen, moet u de dienst van [!DNL Experience Cloud] [!UICONTROL DIL] identiteitskaart en over de pagina&#39;s op uw plaats vormen die u voor gegevensinzameling wilt gebruiken. Zie [DIL voor het maken](../dil/dil-class-overview/dil-create.md#dil-create) en [declareren van id-variabelen](../features/declared-ids.md#declared-id-variables).

## Uitgaande oproepen {#opt-out-calls}

Bij dit [!UICONTROL declared ID] proces worden de voorkeuren van de sitebezoeker aangehouden om te weigeren dat uw website doelt op Audience Manager. Wanneer de Manager van het Publiek een opt-out verzoek ontvangt, [!DNL JSON] bevat de [!UICONTROL DCS] teruggekeerde fout code 171, met het bericht &quot;Ontvangen opt-out markering&quot;, in plaats van de gebruiker ID van de Manager van de Publiek.

* De Manager van het publiek kan in een [!UICONTROL declared ID] opt-out naast een Manager van het Publiek [!UICONTROL UUID] in [!DNL URL]. overgaan
* De [!UICONTROL declared ID] opt-out wordt opgeslagen in [!UICONTROL de Server van het Geheime voorgeheugen van het Profiel ([!UICONTROL PCS]) op een per-partnerbasis. Er is geen opt-out op platformniveau [!UICONTROL declared IDs]. Bovendien kiest Audience Manager de gebruiker uit dat bepaalde gebied aan de rand (de opt-out overschrijdt niet de [!UICONTROL DCS] regio&#39;s).

Zie [Gegevensprivacy](../overview/data-security-and-privacy/data-privacy.md) voor meer informatie over het opting-out van gegevensinzameling.

## Voorbeelden van gedeclareerde id-optie {#opt-out-examples}

U kunt een [!UICONTROL declared ID] opt-out-aanvraag indienen met de `d_cid` combinatie sleutel- `d_cid_ic` waardeparen. De oudere parameters werken `d_dpid` `d_dpuuid` nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

### Opt-out met CID en CID_IC

Zie [URL-variabelen en syntaxis voor gedeclareerde id&#39;s voor een beschrijving en syntaxis](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Weigeren met </th> 
   <th colname="col2" class="entry"> Codevoorbeeld </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A data provider ID and user ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Een integratiecode en een gebruikers-id. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Meerdere <code> d_cid </code> en <code> d_cid_ic </code> sleutelwaardeparen. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Uitschakelen met DPID, DPUUID en UUID (afgekeurd)

Deze methoden werken nog wel, maar worden als afgekeurd beschouwd. Deze informatie wordt verstrekt voor erfenisdoeleinden en verwijzing. Oudere opt-outs zijn:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Uitschakelen (afgekeurd) </th> 
   <th colname="col2" class="entry"> Codevoorbeeld </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> alleen </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Optie op partnerniveau </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Een opt-out van het partnerniveau wordt opgeslagen voor de recentste afbeelding van dit <code> dpid </code> + <code> dpuuid </code> paar aan AAM UUID. Als er geen eerder bestaande afbeelding is, controleert Audience Manager of de aanvraag een AAM UUID in het cookie bevat, en als dit het geval is, gebruikt deze om de opt-out op te slaan. Anders genereert Audience Manager een nieuwe AAM UUID en slaat deze de opt-out onder deze UID op. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> en expliciet <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> heeft altijd voorrang. Als de combinatie <code> dpid </code> + <code> dpuuid </code> aan een andere UUID AAM toewijst, wordt opt-out opgeslagen onder AAM UUID die in het verzoek ( <code> d_uuid </code>) wordt overgegaan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabelen en syntaxis voor opgegeven id&#39;s {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

In de volgende tabel worden de sleutel-waardeparen weergegeven die uw [!DNL Audience Manager] gegevensaanbieder-id en gebruikers-id&#39;s of integratiecodes doorgeven, indien gebruikt. Opmerking: *cursief* geeft een variabele plaatsaanduiding aan. Er zijn spaties toegevoegd om deze beter leesbaar te maken.

In elk zeer belangrijk-waardepaar:

* Het `=` symbool scheidt de sleutel van zijn verwante waarden.
* De waarden worden [!DNL ASCII] gescheiden door het niet-afdrukbare `%01` teken.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabele </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Bevat een gegevensleverancier-id en een bijbehorende unieke gebruikers-id in één sleutel-waardepaar. <code> d_cid </code> vervangt <code> d_dpid </code> en <code> d_dpuuid </code>, die als afgekeurd worden beschouwd, maar nog gesteund. Zie <a href="../reference/cid.md"> CID vervangt DPID en DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Bevat een integratiecode en een bijbehorende unieke gebruiker - identiteitskaart in één enkel zeer belangrijk-waardepaar. <code> d_cid_ic </code> vervangt <code> d_dpid </code> en <code> d_dpuuid </code>, die verouderd, maar nog gesteund zijn. Zie <a href="../reference/cid.md"> CID vervangt DPID en DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeeld van gebeurtenisaanroepen {#sample-event-calls}

Op basis van deze sleutelwaardeparen en hun vereiste syntaxis kunt u gebeurtenisaanroepen uitvoeren zoals hieronder wordt weergegeven.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gebeurtenisoproep omvat </th> 
   <th colname="col2" class="entry"> Codevoorbeeld </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A data provider ID and user ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Een integratiecode en een gebruikers-id. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Meerdere <code> d_cid </code> en <code> d_cid_ic </code> sleutelwaardeparen. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Opgegeven id-variabelen {#declared-id-variables}

Beschrijft de configuratievariabelen die worden gebruikt om gedeclareerde id&#39;s door [!UICONTROL DIL] te geven aan [!DNL Audience Manager.]

## DIL gebruikt de Adobe Experience Platform Identity Service om aangegeven id&#39;s door te geven {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Wanneer u het gebruikt met de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), hoeft u niet langer [!UICONTROL declared IDs] de afgekeurde `dpid` en `dpuuid` variabelen door te geven. In plaats daarvan, baseren de huidige versies van [!UICONTROL DIL] zich op de `visitorService` functie om van de [!UICONTROL declared IDs] functie in de `setCustomerIDs` functie te krijgen [!UICONTROL Adobe Experience Platform Identity Service]. Zie [Klantnamen en verificatiestatussen](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)voor meer informatie. Je belt `visitorService` in `DIL.create` zoals hieronder weergegeven.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In het `namespace` zeer belangrijk-waardepaar, `MCORG` is uw identiteitskaart van de [!DNL Experience Cloud] Organisatie. Als u deze id niet hebt, vindt u deze in het [!UICONTROL Administration] gedeelte van het [!DNL Experience Cloud] dashboard. U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie [Toediening: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Verouderde functies {#deprecated-functions}

Met de recentste versies van [!UICONTROL DIL] (6.2+), te hoeven u niet deze zeer belangrijk-waardeparen te gebruiken om binnen over te gaan [!UICONTROL declared IDs]. Dat komt omdat [!UICONTROL DIL] nu afhankelijk is van de `visitorService` functie die in het bovenstaande codevoorbeeld wordt getoond. Deze functie krijgt [!UICONTROL declared IDs] van [!UICONTROL Adobe Experience Platform Identity Service]. Maar we verwijzen hier naar deze variabelen voor historische en oudere doeleinden. Zie de code hieronder voor een voorbeeld van hoe te vormen om een `DIL.create` van te krijgen [!UICONTROL declared ID] [!UICONTROL Visitor ID Service].
In de volgende tabel worden de oudere variabelen beschreven die door het `declaredId` object worden gebruikt:

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Naam </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Identiteitskaart van de partner van gegevens die door de Manager van het Publiek wordt toegewezen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>De unieke id van de gegevensaanbieder voor de gebruiker. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` en `DPUUID`

Audience Manager vergelijkt en past de gecombineerde `DPID` en `DPUUID` de bijbehorende gebruikers-id in ons systeem aan. Als een id niet bestaat, maakt Audience Manager een nieuwe gebruiker-id en synchroniseert deze met de `DPID/DPUUID` combinatie. Zodra de Manager van de Publiek een gebruiker - identiteitskaart ( `UUID`) aanpast of creeert keert het die identiteitskaart in de [!DNL JSON] reactie op het koekje in het domein van de cliënt (eerstepartijkoekje) of andere lokale opslag terug.

Roep deze functie aan wanneer u [!UICONTROL DIL] v6.1 of eerder gebruikt. Deze functie is echter vervangen door de nieuwe versie die [!UICONTROL declared IDs] van het [!UICONTROL Adobe Experience Platform Identity Service]bestand afkomstig is.

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>Nota, moet u programmatically de code ontwikkelen die de waarden van identiteitskaart voor de `d_dpuuid` en `d_dpid` sleutels levert.

### ID&#39;s doorgeven na DIL-instantiesegment

>[!NOTE]
>
>Als u een [!DNL API] vraag met een verschillende `declaredID` combinatie maakt, zal de nieuwe combinatie slechts voor die vraag worden gebruikt. Verdere regelmatige gebeurtenisvraag zal de originele `DIL.create` `declaredID` combinatie gebruiken.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Voorbeelden van aanvragen/antwoorden {#request-response-examples}

De aanvraag verzendt een gegevensaanbieder en een gebruikers-id naar Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

De reactie keert identiteitskaart van de Manager van de Publiek (b.v., `UUID`) terug die aan een eerstepartijkoekje in het paginadomein wordt geschreven.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Niet de Vraag van het Doel en van de Weigering {#do-not-target}

Bij dit [!UICONTROL declared ID] proces worden de voorkeuren van de sitebezoeker aangehouden om te weigeren dat uw website doelt op Audience Manager. Wanneer de Manager van de Publiek een opt-out verzoek ontvangt, [!UICONTROL DCS] keert een leeg [!DNL JSON] voorwerp in plaats van de gebruiker identiteitskaart van de Manager van de Publiek terug.

>[!MORELIKETHIS]
>
>* [CID vervangt DPID en DPUUID](../reference/cid.md)

