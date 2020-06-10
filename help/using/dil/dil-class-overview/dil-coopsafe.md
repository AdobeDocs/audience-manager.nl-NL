---
description: Een optionele, Booleaanse configuratie die bepaalt of DIL gegevens verzendt (of niet verzendt) naar de Adobe Experience Cloud Device Co-op.
seo-description: Een optionele, Booleaanse configuratie die bepaalt of DIL gegevens verzendt (of niet verzendt) naar de Adobe Experience Cloud Device Co-op.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 0%

---


# isCoopSafe{#iscoopsafe}

Een optionele, Booleaanse configuratie die bepaalt of DIL gegevens verzendt (of niet verzendt) naar de Adobe Experience Cloud Device Co-op.

## Vereisten {#requirements}

Als u `isCoopSafe` het volgende wilt gebruiken:

* Gebruik [!UICONTROL DIL] v6.11 of hoger.
* Neem deel aan de [Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html). De perspectiefleden van coop zouden deze documentatie ook moeten herzien om te bepalen als `isCoopSafe` mogelijke bezorgdheid over hoe de gegevens worden gebruikt om de apparatengrafiek tot stand te brengen.

* Werk samen met uw [!DNL Adobe] consultant om een allowlist- of een denylist-vlag in te stellen op uw Device Co-op-account. Er is geen zelfbedieningspad om deze markeringen in te schakelen.

## Gevallen gebruiken {#use-cases}

`isCoopSafe` helpt twee gebruiksgevallen oplossen die verband houden met gegevensverzameling door huidige of toekomstige leden van de Device Co-op. Deze gebruiksgevallen hebben betrekking op de manier waarop bezoekersgegevens van de site worden doorgegeven aan de copop van het apparaat om de apparaatgrafiek samen te stellen. In de volgende tabel wordt beschreven hoe u met deze gebruiksgevallen gegevens kunt blokkeren of verzenden naar de apparaatgrafiek `isCoopSafe`

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Hoofdletters gebruiken </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Geverifieerde bezoekers</b> </p> </td> 
   <td colname="col2"> <p>Voeg <code> isCoopSafe </code> aan uw <span class="wintitle"> DIL- </span> code toe om te bepalen hoe gegevens voor geverifieerde bezoekers die gebruiksovereenkomsten hebben of niet hebben geaccepteerd, door de Co-op van het Apparaat worden gebruikt om de apparaatgrafiek te maken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL op sites van derden</b> </p> </td> 
   <td colname="col2"> <p>Voeg <code> isCoopSafe </code> aan uw <span class="wintitle"> DIL- </span> code toe voor gebruik op sites van derden waar u: </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">Kan niet garanderen dat geregistreerde bezoekers gebruiksovereenkomsten hebben of niet hebben geaccepteerd. </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">Behoefte om te controleren hoe dat gegeven door Co-op van het Apparaat wordt gebruikt om de apparatengrafiek te bouwen. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Syntaxis en codevoorbeeld {#syntax-code-sample}

**Syntaxis:** `isCoopSafe: true | false`

De opties Van Boole bepalen hoe de klantengegevens door Co-op van het Apparaat worden gebruikt of niet.

* `isCoopSafe: true`: De door een mobiele SDK of website verzamelde bezoekersgegevens *kunnen* worden gebruikt om de apparaatgrafiek te maken.

* `isCoopSafe: false`: Bezoekersgegevens die zijn verzameld door een mobiele SDK of website *kunnen niet* worden gebruikt om de apparaatgrafiek samen te stellen.

**Codevoorbeeld**

Stel dit in wanneer DIL een instantie maakt.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## POST-parameters voor gebeurtenisaanroep {#post-parameters}

Afhankelijk van de markering die u instelt ( `true` of `false`), [!UICONTROL DIL] vertaalt `isCoopSafe` in deze POST-parameters en verzendt deze naar [!DNL Adobe] in een gebeurtenisaanroep:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

De POST-parameters vertellen de [!DNL Experience Cloud] apparaatcoop of er gebruikersgegevens kunnen of kunnen worden opgenomen in de apparaatgrafiek. In de onderstaande tabel wordt de relatie gedefinieerd tussen de `isCoopSafe` Booleaanse markeringen en de POST-parameters die bij een gebeurtenisaanroep worden doorgegeven. Als u niet gebruikt `isCoopSafe`, worden geen van beide overgegaan in een gebeurtenisvraag.

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuratiestatus </th> 
   <th colname="col2" class="entry"> POST-parameter </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>De interface van het Apparaat kan bezoekersgegevens gebruiken helpen de apparatengrafiek bouwen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>De interface van het Apparaat kan bezoekersgegevens niet gebruiken helpen de apparatengrafiek bouwen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Post-Instantiatie-API&#39;s {#post-instantiation}

Met deze API&#39;s kunt u de `isCoopSafe` status overschrijven. Deze zijn nodig omdat u hiermee de postinstantiërings- of postaanmeldingsstatus van een bezoeker kunt wijzigen op een site of in een app van één pagina waar de pagina niet wordt vernieuwd. U moet deze API&#39;s bijvoorbeeld aanroepen als een gebruiker zich op uw site of app aanmeldt en later een gebruiksbeleid accepteert waarmee de Device Co-op hun gegevens kan gebruiken.

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>Stelt de parameter POST <code> d_coop_safe=1 </code> in alle volgende gebeurtenisaanroepen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>Stelt de parameter POST <code> d_coop_unsafe=1 </code> in alle volgende gebeurtenisaanroepen. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->

