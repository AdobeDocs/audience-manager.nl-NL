---
description: Hoe gedeclareerde id's werken, instellingsprocedures, codevoorbeelden en variabelen.
keywords: id sync
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: Gedeclareerde id’s
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 8%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Hoe [!UICONTROL declared IDs] werkzaamheden, procedures instellen, codevoorbeelden en variabelen.

## [!UICONTROL Declared ID] Doelstelling {#declared-id-targeting}

Gebruikers-id&#39;s uitwisselen en synchroniseren met [!DNL Audience Manager] van apparaten of browsers die geen permanente opslagmechanismen gebruiken of accepteren, zoals derden [!DNL cookies].

## Doel van [!UICONTROL Declared ID] Doelstelling {#declared-id-targeting-purpose}

Sommige browsers en de meeste mobiele apparaten kunnen niet door derden worden geaccepteerd [!DNL cookies]. Hierdoor is het moeilijk om informatie over sitebezoekers te behouden of permanente id&#39;s toe te wijzen. Om dit probleem op te lossen, [!DNL Audience Manager] gebruik [!UICONTROL DIL] om in te gaan [!UICONTROL declared IDs] op een gebeurtenisvraag. Ook [!UICONTROL declared ID] kan fungeren als een universele id die van toepassing is op dezelfde gebruiker voor alle oplossingen in de [!DNL Experience Cloud]. In de volgende tabel wordt het proces beschreven voor het zoeken naar en zoeken naar id&#39;s.

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
   <td colname="col2"> <p>Als u wilt werken, hebt u <span class="wintitle"> DIL </span> en de <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a> code op de pagina. <span class="wintitle"> DIL </span> get <span class="wintitle"> gedeclareerde id's </span> van de <code> setVisitorID </code> door de <span class="keyword"> Adobe Experience Platform Identity Service </span> en geeft dat door aan <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identiteitskaart afstemmen</b> </td> 
   <td colname="col2"> <p>Audience Manager probeert de client- en bezoekersidentiteitskaart te koppelen aan een bijbehorende id in ons systeem. Als er geen overeenkomende id bestaat, maakt Audience Manager een nieuwe id en koppelt deze aan de client- en bezoeker-id. </p> <p> <p>Opmerking: De meest recente toewijzing wordt gebruikt als uw identiteitskaart aan meer dan één Audience Manager ID toewijst. </p> </p> </td> 
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

Om te beginnen, moet u vormen [!DNL Experience Cloud] ID-service en [!UICONTROL DIL] over de pagina&#39;s op uw plaats die u voor gegevensinzameling wilt gebruiken. Zie [DIL maken](../dil/dil-class-overview/dil-create.md#dil-create) en [Opgegeven id-variabelen](../features/declared-ids.md#declared-id-variables).

## Uitgaande oproepen {#opt-out-calls}

De [!UICONTROL declared ID] proces respecteert voorkeuren sitebezoekers om te weigeren [!DNL Audience Manager] door uw website. Wanneer [!DNL Audience Manager] ontvangt een &quot;opt-out&quot;-verzoek, [!DNL JSON] geretourneerd door de [!DNL DCS] bevat foutcode 171, met het bericht `Encountered opt out tag`in plaats van de [!DNL Audience Manager] gebruikersnaam.

* [!DNL Audience Manager] kan een [!UICONTROL declared ID] opt-out naast een [!DNL Audience Manager] [!UICONTROL UUID] in de [!DNL URL].
* De [!UICONTROL declared ID] opt-out wordt opgeslagen in de [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) per partner. Er is geen opt-out op platformniveau [!UICONTROL declared IDs]. Daarnaast [!DNL Audience Manager] kiest de gebruiker uit dat bepaalde gebied op de rand (de opt-out gaat niet over [!DNL DCS] regio&#39;s).

Zie [Gegevensprivacy](../overview/data-security-and-privacy/data-privacy.md) voor meer informatie over het opting-out van gegevensinzameling.

## [!UICONTROL Declared ID] Voorbeelden voor uitschakelen {#opt-out-examples}

U kunt een [!UICONTROL declared ID] opt-out-verzoeken met de `d_cid` en `d_cid_ic` sleutelwaardeparen. De oude parameters zoals `d_dpid` en `d_dpuuid` werken nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

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

### Opt-out met [!UICONTROL DPID], [!UICONTROL DPUUID], en [!UICONTROL UUID] (Afgekeurd)

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Een partner niveau opt-out wordt opgeslagen voor de recentste afbeelding van dit <code> dpid </code> + <code> dpuuid </code> koppelen aan een AAM UUID. Als er nog geen bestaande toewijzing is, controleert de Audience Manager of de aanvraag een AAM UUID in het cookie bevat en, als dit het geval is, gebruikt deze om de opt-out op te slaan. Anders genereert Audience Manager een nieuwe AAM UUID en slaat de opt-out onder deze UID op. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> en uitdrukkelijk <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> heeft altijd voorrang. Als de <code> dpid </code> + <code> dpuuid </code> combinatie kaarten aan een andere AAM UUID, wordt de opt-out opgeslagen onder AAM UUID die in het verzoek wordt overgegaan ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabelen en syntaxis voor [!UICONTROL Declared IDs] {#variables-and-syntax}

In de volgende tabel worden de sleutelwaardeparen weergegeven die in uw [!DNL Audience Manager] de gegevensleverancier-id en de gebruikers-id&#39;s of integratiecodes, indien gebruikt. Opmerking: *cursief* Hiermee wordt een tijdelijke aanduiding voor een variabele aangegeven. Er zijn spaties toegevoegd om deze beter leesbaar te maken.

In elk zeer belangrijk-waardepaar:

* De `=` Hiermee scheidt u de toets van de gerelateerde waarden.
* Niet-afdrukbaar [!DNL ASCII] teken `%01` scheidt de waarden.

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
   <td colname="col2"> <p>Bevat een gegevensleverancier-id en een bijbehorende unieke gebruikers-id in één sleutel-waardepaar. <code> d_cid </code> vervangt <code> d_dpid </code> en <code> d_dpuuid </code>, die als afgekeurd worden beschouwd, maar nog steeds worden ondersteund. Zie <a href="../reference/cid.md">CID vervangt DPID en DPUUID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Bevat een integratiecode en een bijbehorende unieke gebruiker - identiteitskaart in één enkel zeer belangrijk-waardepaar. <code> d_cid_ic </code> vervangt <code> d_dpid </code> en <code> d_dpuuid </code>, die zijn vervangen, maar nog steeds worden ondersteund. Zie <a href="../reference/cid.md">CID vervangt DPID en DPUUID</a>. </p> </td> 
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

Beschrijft de configuratievariabelen die worden gebruikt om over te gaan [!UICONTROL declared IDs] doorheen [!UICONTROL DIL] tot [!DNL Audience Manager.]

## [!UICONTROL DIL] gebruikt de [!DNL Adobe Experience Platform Identity Service] Aan controle [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Indien gebruikt met de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), hoeft u niet meer door te geven [!UICONTROL declared IDs] met de afgekeurde `dpid` en `dpuuid` variabelen. In plaats daarvan, de huidige versies van [!UICONTROL DIL] zich op de `visitorService` functie om de [!UICONTROL declared IDs] van de `setCustomerIDs` in de [!UICONTROL Adobe Experience Platform Identity Service]. Zie voor meer informatie [Klant-id&#39;s en verificatiestatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). U wilt bellen `visitorService` in `DIL.create` zoals hieronder weergegeven.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In de `namespace` sleutelwaardepaar, `MCORG` is uw [!DNL Experience Cloud] Organisatie-id. Als u deze id niet hebt, kunt u deze vinden in het dialoogvenster [!UICONTROL Administration] van de [!DNL Experience Cloud] dashboard. U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie [Beheer: Core Services](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## Verouderde functies {#deprecated-functions}

Met de nieuwste versies van [!UICONTROL DIL] (6.2+), te hoeven u niet deze zeer belangrijk-waardeparen te gebruiken om binnen over te gaan [!UICONTROL declared IDs]. Dat komt omdat [!UICONTROL DIL] is nu afhankelijk van de `visitorService` in het bovenstaande codevoorbeeld. Deze functie krijgt [!UICONTROL declared IDs] van de [!UICONTROL Adobe Experience Platform Identity Service]. Maar we verwijzen hier naar deze variabelen voor historische en oudere doeleinden. Zie de code hieronder voor een voorbeeld van hoe te vormen `DIL.create` om een [!UICONTROL declared ID] van de [!UICONTROL Visitor ID Service].
In de volgende tabel worden de oudere variabelen beschreven die door de `declaredId` object:

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

[!DNL Audience Manager] vergelijkt en past gecombineerd aan `DPID` en `DPUUID` aan een overeenkomstige gebruiker - identiteitskaart in ons systeem. Als een id niet bestaat, [!DNL Audience Manager] maakt een nieuwe gebruikersnaam en synchroniseert deze met de `DPID/DPUUID` combinatie. Eenmaal [!DNL Audience Manager] komt overeen met of maakt een gebruikers-id (de `UUID`) wordt die id geretourneerd in het dialoogvenster [!DNL JSON] reactie op de [!DNL cookie] in het domein van de client (first-party) [!DNL cookie]) of andere lokale opslag.

Roep deze functie aan wanneer u gebruikt [!UICONTROL DIL] v6.1 of eerder. Deze functie is echter vervangen door de nieuwe versie die [!UICONTROL declared IDs] van de [!DNL Adobe Experience Platform Identity Service].

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
>U moet programmatically de code ontwikkelen die de waarden van identiteitskaart voor `d_dpuuid` en `d_dpid` toetsen.

### ID&#39;s doorgeven na [!UICONTROL DIL] Instantiëren

>[!NOTE]
>
>Als u een [!DNL API] vraag met een verschillende `declaredID` combinatie, zal de nieuwe combinatie slechts voor die vraag worden gebruikt. Verdere regelmatige gebeurtenisvraag zal origineel gebruiken `DIL.create`  `declaredID` combinatie.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Voorbeelden van aanvragen/antwoorden {#request-response-examples}

De aanvraag verzendt een gegevensaanbieder en een gebruikersnaam naar [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

De reactie retourneert de Audience Manager-id (bijvoorbeeld `UUID`) die naar een cookie van de eerste partij in het paginadomein wordt geschreven.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Niet de Vraag van het Doel en van de Weigering {#do-not-target}

De [!UICONTROL declared ID] proces respecteert voorkeuren sitebezoekers om te weigeren [!DNL Audience Manager] door uw website. Wanneer [!DNL Audience Manager] ontvangt een &quot;opt-out&quot;-verzoek, [!DNL DCS] retourneert een lege waarde [!DNL JSON] object in plaats van het [!DNL Audience Manager] gebruikersnaam.

>[!MORELIKETHIS]
>
>* [CID vervangt DPID en DPUUID](../reference/cid.md)

