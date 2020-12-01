---
description: Hoe gedeclareerde id's werken, instellingsprocedures, codevoorbeelden en variabelen.
keywords: id sync
seo-description: Hoe gedeclareerde id's werken, instellingsprocedures, codevoorbeelden en variabelen.
seo-title: Gedeclareerde id’s
solution: Audience Manager
title: Gedeclareerde id’s
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
translation-type: tm+mt
source-git-commit: 29708d5fc528ac9da08f4c5a7f2bcaa11b240d8b
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 9%

---


# [!UICONTROL Declared IDs] {#declared-ids}

Hoe [!UICONTROL declared IDs] werkt, opstellingsprocedures, codevoorbeelden, en variabelen.

## [!UICONTROL Declared ID] Doelstelling  {#declared-id-targeting}

U kunt gebruikers-id&#39;s uitwisselen en synchroniseren met [!DNL Audience Manager] van apparaten of browsers die geen permanente opslagmechanismen gebruiken of accepteren, zoals [!DNL cookies] van derden.

## Doel van [!UICONTROL Declared ID] gericht {#declared-id-targeting-purpose}

Sommige browsers en de meeste mobiele apparaten accepteren [!DNL cookies] van derden niet. Hierdoor is het moeilijk om informatie over sitebezoekers te behouden of permanente id&#39;s toe te wijzen. [!DNL Audience Manager] gebruikt [!UICONTROL DIL] om dit probleem op te lossen om u toe te laten binnen [!UICONTROL declared IDs] op een gebeurtenisvraag overgaan. Een [!UICONTROL declared ID] kan ook fungeren als een universele id die van toepassing is op dezelfde gebruiker voor alle oplossingen in [!DNL Experience Cloud]. In de volgende tabel wordt het proces beschreven voor het zoeken naar en zoeken naar id&#39;s.

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
   <td colname="col2"> <p>Als u wilt werken, hebt u <span class="wintitle"> DIL </span> en de code <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a> op de pagina nodig. <span class="wintitle"> DIL  </span> krijgt  <span class="wintitle"> verklaarde identiteitskaarts  </span> van de  <code> setVisitorID </code> functie die door de Dienst van de Identiteit van  <span class="keyword"> Adobe Experience Platform wordt verstrekt  </span> en gaat dat op  <span class="keyword"> Audience Manager over  </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identiteitskaart afstemmen</b> </td> 
   <td colname="col2"> <p>Audience Manager probeert de client- en bezoekersidentiteitskaart te koppelen aan een bijbehorende id in ons systeem. Als er geen overeenkomende id bestaat, maakt Audience Manager een nieuwe id en koppelt deze aan de client- en bezoeker-id. </p> <p> <p>Opmerking:  De meest recente toewijzing wordt gebruikt als uw identiteitskaart aan meer dan één Audience Manager ID toewijst. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Return-id</b> </td> 
   <td colname="col2"> <p>Audience Manager schrijft zijn gesynchroniseerde identiteitskaart aan een eerderangs koekje (of andere adresseerbare opslagruimte) in het cliëntdomein of de toepassing. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Volgende gebeurtenisaanroepen</b> </td>
   <td colname="col2"> <p>De extra gebeurtenisvraag leest identiteitskaart van de Audience Manager van het domein van de cliënt en verzendt dat naar Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Om te beginnen, moet u de [!DNL Experience Cloud] dienst van identiteitskaart en [!UICONTROL DIL] over de pagina&#39;s op uw plaats vormen die u voor gegevensinzameling wilt gebruiken. Zie [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) en [Opgegeven ID-variabelen](../features/declared-ids.md#declared-id-variables).

## Uitgaande oproepen {#opt-out-calls}

Bij het proces [!UICONTROL declared ID] worden de voorkeuren van de sitebezoeker gerespecteerd voor het uitschakelen van [!DNL Audience Manager]-doelen door uw website. Wanneer [!DNL Audience Manager] een &quot;opt-out&quot;-verzoek ontvangt, bevat [!DNL JSON] die door [!DNL DCS] is geretourneerd, de foutcode 171 met het bericht `Encountered opt out tag` in plaats van de [!DNL Audience Manager]-gebruikersnaam.

* [!DNL Audience Manager] een  [!UICONTROL declared ID] opt-out kan doorgeven naast een  [!DNL Audience Manager] [!UICONTROL UUID] in de  [!DNL URL].
* De [!UICONTROL declared ID] opt-out wordt opgeslagen in [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) op een per-partnerbasis. Er is geen opt-out op platformniveau met [!UICONTROL declared IDs]. Bovendien [!DNL Audience Manager] kiest de gebruiker uit dat bepaalde gebied op de rand (de opt-out overschrijdt [!DNL DCS] gebieden niet).

Zie [Gegevensprivacy](../overview/data-security-and-privacy/data-privacy.md) voor meer informatie over het opting-out van gegevensinzameling.

## [!UICONTROL Declared ID] Voorbeelden voor uitschakelen  {#opt-out-examples}

U kunt een [!UICONTROL declared ID] opt-out verzoeken met `d_cid` en `d_cid_ic` sleutel-waardeparen. De oude parameters zoals `d_dpid` en `d_dpuuid` werken nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

### Opt-out met [!UICONTROL CID] en [!UICONTROL CID_IC]

Zie [URL-variabelen en syntaxis voor gedeclareerde id’s](../features/declared-ids.md#variables-and-syntax) voor een beschrijving en syntaxis.

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-out met </th> 
   <th colname="col2" class="entry"> Codevoorbeeld </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Een dataprovider-id en een gebruikers-id. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Een integratiecode en een gebruikers-id. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Meerdere <code> d_cid </code>- en <code> d_cid_ic </code>-sleutelwaardeparen. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-out met [!UICONTROL DPID], [!UICONTROL DPUUID], en [!UICONTROL UUID] (afgekeurd)

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Een opt-out van het partnerniveau wordt opgeslagen voor de recentste afbeelding van dit <code> dpid </code> + <code> dpuuid </code> paar aan AAM UUID. Als er nog geen bestaande toewijzing is, controleert de Audience Manager of de aanvraag een AAM UUID in het cookie bevat en, als dit het geval is, gebruikt deze om de opt-out op te slaan. Anders genereert Audience Manager een nieuwe AAM UUID en slaat de opt-out onder deze UID op. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> +  <code> d_dpid </code> en expliciet  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> heeft altijd voorrang. Als de <code> dpid </code> + <code> dpuuid </code> combinatie aan een andere AAM UUID in kaart brengt, wordt opt-out opgeslagen onder AAM UUID die in het verzoek ( <code> d_uuid </code>) wordt overgegaan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabelen en syntaxis voor [!UICONTROL Declared IDs] {#variables-and-syntax}

De volgende lijst maakt een lijst van de zeer belangrijk-waardeparen die in uw [!DNL Audience Manager] gegevensleverancier ID en gebruiker IDs of integratiecodes overgaan, indien gebruikt. Opmerking: *cursief* geeft een variabele plaatsaanduiding aan. Er zijn spaties toegevoegd om deze beter leesbaar te maken.

In elk zeer belangrijk-waardepaar:

* Het symbool `=` scheidt de sleutel van zijn verwante waarden.
* Het [!DNL ASCII]-teken `%01` scheidt de waarden.

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
   <td colname="col2"> <p>Bevat een gegevensleverancier-id en een bijbehorende unieke gebruikers-id in één sleutel-waardepaar. <code> d_cid </code> vervangt  <code> d_dpid </code> en  <code> d_dpuuid </code>, die als afgekeurd worden beschouwd, maar nog gesteund. Zie <a href="../reference/cid.md">CID vervangt DPID en DPUUID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Bevat een integratiecode en een bijbehorende unieke gebruiker - identiteitskaart in één enkel zeer belangrijk-waardepaar. <code> d_cid_ic </code> vervangt  <code> d_dpid </code> en  <code> d_dpuuid </code>, die afgekeurd zijn, maar nog gesteund. Zie <a href="../reference/cid.md">CID vervangt DPID en DPUUID</a>. </p> </td> 
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
   <td colname="col1"> <p>Een dataprovider-id en een gebruikers-id. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Een integratiecode en een gebruikers-id. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Meerdere <code> d_cid </code>- en <code> d_cid_ic </code>-sleutelwaardeparen. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variabelen  {#declared-id-variables}

Beschrijft de configuratievariabelen die worden gebruikt om [!UICONTROL declared IDs] tot [!UICONTROL DIL] tot [!DNL Audience Manager.] over te gaan

## [!UICONTROL DIL] gebruikt  [!DNL Adobe Experience Platform Identity Service] om te slagen  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Bij gebruik met [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/nl-NL/id-service/using/home.html) hoeft u [!UICONTROL declared IDs] niet meer door te geven met de afgekeurde variabelen `dpid` en `dpuuid`. In plaats daarvan, baseren de huidige versies van [!UICONTROL DIL] op de `visitorService` functie om [!UICONTROL declared IDs] van de `setCustomerIDs` functie in [!UICONTROL Adobe Experience Platform Identity Service] te krijgen. Voor meer informatie, zie [Klantidentiteitskaart en Authentificatiestatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). U zou `visitorService` in `DIL.create` zoals hieronder getoond roepen.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In `namespace` sleutel-waarde paar, `MCORG` is uw [!DNL Experience Cloud] identiteitskaart van de Organisatie Als u deze id niet hebt, vindt u deze in de sectie [!UICONTROL Administration] van het [!DNL Experience Cloud] dashboard. U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie [Beheer: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Vervangen functies {#deprecated-functions}

Met de recentste versies van [!UICONTROL DIL] (6.2+), te hoeven u niet deze zeer belangrijk-waardeparen te gebruiken om binnen [!UICONTROL declared IDs] over te gaan. Dat komt doordat [!UICONTROL DIL] nu afhankelijk is van de functie `visitorService` die in het bovenstaande codevoorbeeld wordt getoond. Deze functie krijgt [!UICONTROL declared IDs] van [!UICONTROL Adobe Experience Platform Identity Service]. Maar we verwijzen hier naar deze variabelen voor historische en oudere doeleinden. Zie de code hieronder voor een voorbeeld van hoe te om `DIL.create` te vormen om [!UICONTROL declared ID] van [!UICONTROL Visitor ID Service] te krijgen.
In de volgende tabel worden de oudere variabelen beschreven die door het object `declaredId` worden gebruikt:

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
   <td colname="col3"> <p>Identiteitskaart van de partner van gegevens die door Audience Manager wordt toegewezen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>De unieke id van de gegevensaanbieder voor de gebruiker. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] en  [!UICONTROL DPUUID]

[!DNL Audience Manager] vergelijkt en past gecombineerde  `DPID` en  `DPUUID` aan een overeenkomstige gebruiker - identiteitskaart in ons systeem aan. Als een id niet bestaat, maakt [!DNL Audience Manager] een nieuwe gebruiker-id en synchroniseert deze met de `DPID/DPUUID`-combinatie. Als [!DNL Audience Manager] eenmaal een gebruikers-id (de `UUID`) aanpast of maakt, wordt die id geretourneerd in het [!DNL JSON]-antwoord op de [!DNL cookie] in het domein van de client (first-party [!DNL cookie]) of andere lokale opslag.

Roep deze functie aan wanneer u [!UICONTROL DIL] v6.1 of vroeger gebruikt. Deze functie is echter vervangen door de nieuwe versie die [!UICONTROL declared IDs] krijgt van [!DNL Adobe Experience Platform Identity Service].

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
>U moet programmatically de code ontwikkelen die de waarden van identiteitskaart voor `d_dpuuid` en `d_dpid` sleutels levert.

### ID&#39;s doorgeven nadat [!UICONTROL DIL] is geïnstantieerd

>[!NOTE]
>
>Als u [!DNL API] vraag met een verschillende `declaredID` combinatie maakt, zal de nieuwe combinatie voor die vraag slechts worden gebruikt. Verdere regelmatige gebeurtenisvraag zal de originele `DIL.create` `declaredID` combinatie gebruiken.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Voorbeelden van aanvragen/antwoorden {#request-response-examples}

De aanvraag verzendt een gegevensaanbieder en een gebruikers-id naar [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

De reactie keert identiteitskaart van de Audience Manager (b.v., `UUID`) terug die aan een eerstepartijkoekje in het paginadomein wordt geschreven.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Niet richten en uit Vraag {#do-not-target}

Bij het proces [!UICONTROL declared ID] worden de voorkeuren van de sitebezoeker gerespecteerd voor het uitschakelen van [!DNL Audience Manager]-doelen door uw website. Wanneer [!DNL Audience Manager] een &quot;opt-out&quot;-verzoek ontvangt, retourneert [!DNL DCS] een leeg [!DNL JSON]-object in plaats van de [!DNL Audience Manager]-gebruikersnaam.

>[!MORELIKETHIS]
>
>* [CID vervangt DPID en DPUUID](../reference/cid.md)

