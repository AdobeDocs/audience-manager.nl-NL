---
description: Hoe gedeclareerde id's werken, instellingsprocedures, codevoorbeelden en variabelen.
keywords: id sync
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: Opgegeven id's
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 6%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Hoe [!UICONTROL declared IDs] werkt, procedures instellen, codevoorbeelden en variabelen.

## [!UICONTROL Declared ID] Doel {#declared-id-targeting}

U kunt gebruikers-id&#39;s uitwisselen en synchroniseren met [!DNL Audience Manager] van apparaten of browsers die geen permanente opslagmechanismen, zoals derden, gebruiken of accepteren [!DNL cookies] .

## Doel van [!UICONTROL Declared ID] gericht {#declared-id-targeting-purpose}

Sommige browsers en de meeste mobiele apparaten accepteren [!DNL cookies] niet van derden. Hierdoor is het moeilijk om informatie over sitebezoekers te behouden of permanente id&#39;s toe te wijzen. Om dit probleem op te lossen, gebruikt [!DNL Audience Manager] [!UICONTROL DIL] om u [!UICONTROL declared IDs] toe te staan bij een gebeurtenisaanroep. Een [!UICONTROL declared ID] kan ook fungeren als een universele id die van toepassing is op dezelfde gebruiker voor alle oplossingen in de [!DNL Experience Cloud] . In de volgende tabel wordt het proces beschreven voor het zoeken naar en zoeken naar id&#39;s.

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Proces </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> Vraag van de Gebeurtenis </b> </td> 
   <td colname="col2"> <p>Als u wilt werken, hebt u <span class="wintitle"> DIL </span> en de code <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL" format="https" scope="external"> Adobe Experience Platform Identity Service </a> op de pagina nodig. <span class="wintitle"> DIL </span> haalt <span class="wintitle"> gedeclareerde id's </span> op van de <code> setVisitorID </code> -functie die wordt geleverd door de <span class="keyword"> Adobe Experience Platform Identity Service </span> en geeft die door aan <span class="keyword"> Audience Manager </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> identiteitskaart van de Gelijke </b> </td> 
   <td colname="col2"> <p>Audience Manager probeert de client- en bezoekersidentiteitskaart te koppelen aan een overeenkomstige id in ons systeem. Als er geen overeenkomende id bestaat, maakt Audience Manager een nieuwe id en koppelt deze aan de client- en bezoeker-id. </p> <p> <p>Opmerking: de meest recente toewijzing wordt gebruikt als uw id is toegewezen aan meerdere Audience Manager-id's. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> identiteitskaart van de Terugkeer </b> </td> 
   <td colname="col2"> <p>Audience Manager schrijft de gesynchroniseerde id naar een cookie van de eerste partij (of een andere opslagruimte voor geadresseerden) in het clientdomein of de toepassing. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b> de Volgende Vraag van de Gebeurtenis </b> </td>
   <td colname="col2"> <p>Aanvullende gebeurtenisaanroepen lezen de Audience Manager-id uit het domein van de client en sturen die naar Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Om te beginnen moet u de [!DNL Experience Cloud] id-service en [!UICONTROL DIL] configureren voor alle pagina&#39;s op uw site die u wilt gebruiken voor gegevensverzameling. Zie [ DIL creeert ](../dil/dil-class-overview/dil-create.md#dil-create) en [ Verklaarde Variabelen van identiteitskaart ](../features/declared-ids.md#declared-id-variables).

## Uitgaande oproepen {#opt-out-calls}

Het [!UICONTROL declared ID] -proces houdt rekening met de voorkeuren van de sitebezoeker om [!DNL Audience Manager] -doelen niet te kiezen voor uw website. Wanneer [!DNL Audience Manager] een aanvraag om te weigeren ontvangt, bevat de [!DNL JSON] die door [!DNL DCS] wordt geretourneerd, de foutcode 171 met het bericht `Encountered opt out tag` in plaats van de gebruikers-id van [!DNL Audience Manager] .

* [!DNL Audience Manager] kan een [!UICONTROL declared ID] -optie naast een [!DNL Audience Manager] [!UICONTROL UUID] in de [!DNL URL] doorgeven.
* De [!UICONTROL declared ID] opt-out wordt opgeslagen in [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) op een per-partnerbasis. Er is geen opt-out op platformniveau met [!UICONTROL declared IDs] . Daarnaast wordt de gebruiker door [!DNL Audience Manager] uitgeschakeld in het desbetreffende gebied aan de rand (de optie Weigeren kruist [!DNL DCS] -gebieden niet).

Zie [ Privacy van Gegevens ](../overview/data-security-and-privacy/data-privacy.md) voor meer informatie over het opting-uit van gegevensinzameling.

## [!UICONTROL Declared ID] Voorbeelden voor uitschakelen {#opt-out-examples}

U kunt een [!UICONTROL declared ID] -aanvraag indienen met de sleutelwaardeparen `d_cid` en `d_cid_ic` . De oude parameters zoals `d_dpid` en `d_dpuuid` werken nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

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
   <td colname="col1"> <p>Meerdere <code> d_cid </code> en <code> d_cid_ic </code> sleutelwaardeparen. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-out met [!UICONTROL DPID], [!UICONTROL DPUUID] en [!UICONTROL UUID] (afgekeurd)

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
   <td colname="col1"> <p> alleen <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Optie op partnerniveau </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Een opt-out op partnerniveau wordt opgeslagen voor de laatste toewijzing van dit <code> dpid </code> + <code> dpuuid </code> paar aan AAM UUID. Als er geen bestaande toewijzing bestaat, controleert Audience Manager of de aanvraag een AAM UUID in het cookie bevat en of deze een-UUID bevat. Als dit het geval is, wordt deze gebruikt voor het opslaan van de opt-out. Anders genereert Audience Manager een nieuwe AAM UUID en slaat het de opt-out onder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> en explicit <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> heeft altijd voorrang. Als de <code> dpid </code> + <code> dpuuid </code> -combinatie wordt toegewezen aan een andere AAM UUID, wordt de opt-out opgeslagen onder de AAM UUID die in de aanvraag wordt doorgegeven ( <code> d_uuid </code> ). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabelen en syntaxis voor [!UICONTROL Declared IDs] {#variables-and-syntax}

De volgende tabel bevat een lijst met sleutelwaardeparen die uw [!DNL Audience Manager] -gegevensaanbieder-id en -gebruikers-id&#39;s of integratiecodes doorgeven, indien gebruikt. Nota, *cursief* wijst op veranderlijke placeholder. Er zijn spaties toegevoegd om deze beter leesbaar te maken.

In elk zeer belangrijk-waardepaar:

* Het symbool `=` scheidt de sleutel van zijn verwante waarden.
* Het niet-afdrukbare [!DNL ASCII] teken `%01` scheidt de waarden.

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
   <td colname="col2"> <p>Bevat een gegevensleverancier-id en een bijbehorende unieke gebruikers-id in één sleutel-waardepaar. <code> d_cid </code> vervangt <code> d_dpid </code> en <code> d_dpuuid </code> . Deze worden beschouwd als afgekeurd, maar worden wel ondersteund. Zie <a href="../reference/cid.md"> DPID en DPUUID worden vervangen door CID </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Bevat een integratiecode en een bijbehorende unieke gebruiker - identiteitskaart in één enkel zeer belangrijk-waardepaar. <code> d_cid_ic </code> vervangt <code> d_dpid </code> en <code> d_dpuuid </code> , die zijn afgekeurd, maar nog steeds worden ondersteund. Zie <a href="../reference/cid.md"> DPID en DPUUID worden vervangen door CID </a> . </p> </td> 
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
   <td colname="col1"> <p>Meerdere <code> d_cid </code> en <code> d_cid_ic </code> sleutelwaardeparen. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variabelen {#declared-id-variables}

Beschrijft de configuratievariabelen die worden gebruikt om [!UICONTROL declared IDs] tot en met [!UICONTROL DIL] door te geven aan [!DNL Audience Manager.]

## [!UICONTROL DIL] gebruikt de lus [!DNL Adobe Experience Platform Identity Service] to Pass [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Wanneer gebruikt met de [ Dienst van de Identiteit van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL), te hoeven u niet meer binnen [!UICONTROL declared IDs] met de afgekeurde `dpid` en `dpuuid` variabelen over te gaan. In plaats daarvan vertrouwen de huidige versies van [!UICONTROL DIL] op de `visitorService` functie om [!UICONTROL declared IDs] van de `setCustomerIDs` functie in [!UICONTROL Adobe Experience Platform Identity Service] te krijgen. Voor meer informatie, zie [ Klant IDs en de Staten van de Authentificatie ](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=nl-NL). U roept `visitorService` in `DIL.create` aan, zoals hieronder wordt weergegeven.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In het `namespace` key-value paar is `MCORG` uw [!DNL Experience Cloud] Organisatie-id. Als u deze id niet hebt, vindt u deze in de sectie [!UICONTROL Administration] van het dashboard van [!DNL Experience Cloud] . U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie [ begonnen worden met de diensten van Experience Cloud ](https://experienceleague.adobe.com/nl/docs/core-services/interface/services/getting-started).

## Verouderde functies {#deprecated-functions}

Met de nieuwste versies van [!UICONTROL DIL] (6.2+) hoeft u deze sleutel-waardeparen niet te gebruiken om [!UICONTROL declared IDs] door te geven. Dat komt omdat [!UICONTROL DIL] nu afhankelijk is van de functie `visitorService` die in het bovenstaande codevoorbeeld wordt weergegeven. Deze functie krijgt [!UICONTROL declared IDs] van [!UICONTROL Adobe Experience Platform Identity Service]. Maar we verwijzen hier naar deze variabelen voor historische en oudere doeleinden. Zie de onderstaande code voor een voorbeeld van het configureren van `DIL.create` voor het ophalen van een [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service] .
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

### [!UICONTROL DPID] en [!UICONTROL DPUUID]

[!DNL Audience Manager] vergelijkt en koppelt de gecombineerde `DPID` en `DPUUID` -id met een bijbehorende gebruikers-id in ons systeem. Als een id niet bestaat, maakt [!DNL Audience Manager] een nieuwe gebruiker-id en wordt deze gesynchroniseerd met de combinatie `DPID/DPUUID` . Als [!DNL Audience Manager] eenmaal een gebruikersnaam aanpast of maakt (de `UUID` ), wordt die id geretourneerd in het [!DNL JSON] -antwoord op de [!DNL cookie] in het domein van de client (de eerste partij [!DNL cookie] ) of andere lokale opslag.

Roep deze functie aan wanneer u [!UICONTROL DIL] v6.1 of eerder gebruikt. Deze functie is echter vervangen door de nieuwe versie die [!UICONTROL declared IDs] krijgt van [!DNL Adobe Experience Platform Identity Service] .

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
>U moet programmatisch de code ontwikkelen die de waarden van identiteitskaart voor de `d_dpuuid` en `d_dpid` sleutels levert.

### ID&#39;s doorgeven na [!UICONTROL DIL] Instantiëring

>[!NOTE]
>
>Als u een [!DNL API] vraag met een verschillende `declaredID` combinatie maakt, zal de nieuwe combinatie slechts voor die vraag worden gebruikt. Voor verdere reguliere-gebeurtenisaanroepen wordt de oorspronkelijke `DIL.create` `declaredID` -combinatie gebruikt.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Voorbeelden van aanvragen/antwoorden {#request-response-examples}

De aanvraag verzendt een gegevensaanbieder en een gebruikers-id naar [!DNL Audience Manager] :

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

De reactie retourneert de Audience Manager-id (bijvoorbeeld `UUID` ) die naar een cookie van de eerste partij in het paginadomein is geschreven.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Niet de Vraag van het Doel en van de Weigering {#do-not-target}

Het [!UICONTROL declared ID] -proces houdt rekening met de voorkeuren van de sitebezoeker om [!DNL Audience Manager] -doelen niet te kiezen voor uw website. Wanneer [!DNL Audience Manager] een aanvraag om te weigeren ontvangt, retourneert de [!DNL DCS] een leeg [!DNL JSON] -object in plaats van de [!DNL Audience Manager] gebruikers-id.

>[!MORELIKETHIS]
>
>* [CID vervangt DPID en DPUUID](../reference/cid.md)
