---
description: Een optionele, Booleaanse configuratie die bepaalt of DIL gegevens naar de Adobe Experience Cloud Device Co-op verzendt (of niet verzendt).
seo-description: An optional, Boolean configuration that determines if DIL sends (or does not send) data to the Adobe Experience Cloud Device Co-op.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
feature: DIL Implementation
exl-id: 33dca495-6923-4966-9ec3-8b0fd2f17649
hide: true
hidefromtoc: true
index: n
source-git-commit: 3f4a161ee856357b5cb5eb757ad779dee5357b09
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 1%

---

# isCoopSafe{#iscoopsafe}

>[!WARNING]
>
>Deze functie is vervangen.

Een optionele, Booleaanse configuratie die bepaalt of DIL gegevens naar de Adobe Experience Cloud Device Co-op verzendt (of niet verzendt).

## Vereisten {#requirements}

Te gebruiken `isCoopSafe` u moet:

* Gebruiken [!UICONTROL DIL] v6.11 of hoger.
* Deelnemen aan de [Experience Cloud Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/home.html). De prospectieve coopleden zouden deze documentatie ook moeten herzien om te bepalen of `isCoopSafe` Hiermee worden mogelijke problemen opgelost met betrekking tot de manier waarop gegevens worden gebruikt om de apparaatgrafiek te maken.

* Werk met uw [!DNL Adobe] adviseur om een lijst van gewenste personen of een vlag van de lijst van gewezen personen op uw Co-op rekening van het Apparaat te plaatsen. Er is geen zelfbedieningspad om deze markeringen in te schakelen.

## Gevallen gebruiken {#use-cases}

`isCoopSafe` helpt twee gebruiksgevallen oplossen die verband houden met gegevensverzameling door huidige of toekomstige leden van de Device Co-op. Deze gebruiksgevallen hebben betrekking op de manier waarop bezoekersgegevens van de site worden doorgegeven aan de copop van het apparaat om de apparaatgrafiek samen te stellen. In de volgende tabel wordt beschreven hoe `isCoopSafe` werkt met deze gebruiksgevallen om gegevens te blokkeren of naar de apparaatgrafiek te verzenden

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gebruiksscenario </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Geverifieerde bezoekers</b> </p> </td> 
   <td colname="col2"> <p>Toevoegen <code> isCoopSafe </code> aan uw <span class="wintitle"> DIL </span> code om te controleren hoe gegevens voor geverifieerde bezoekers die gebruiksovereenkomsten hebben of niet hebben geaccepteerd, door de Co-op van het Apparaat worden gebruikt om de apparaatgrafiek te maken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL op sites van derden</b> </p> </td> 
   <td colname="col2"> <p>Toevoegen <code> isCoopSafe </code> aan uw <span class="wintitle"> DIL </span> code voor gebruik op derdeplaatsen waar u: </p> <p> 
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

* `isCoopSafe: true`: Gegevens van bezoekers verzameld door een mobiele SDK of website *kan* worden gebruikt om de apparaatgrafiek samen te stellen.

* `isCoopSafe: false`: Gegevens van bezoekers verzameld door een mobiele SDK of website *kan* worden gebruikt om de apparaatgrafiek samen te stellen.

**Codevoorbeeld**

Stel dit in wanneer DIL instantieert.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## Parameters POST gebeurtenisaanroep {#post-parameters}

Afhankelijk van de vlag die u instelt ( `true` of `false`), [!UICONTROL DIL] translate `isCoopSafe` in deze parameters van de POST en verzendt hen naar [!DNL Adobe] bij een gebeurtenisoproep:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

De parameters van de POST vertellen [!DNL Experience Cloud] Coop van apparaat als het gebruikersgegevens in de apparatengrafiek kan of kan omvatten. In de onderstaande tabel wordt de relatie tussen de `isCoopSafe` De vlaggen Van Boole en de parameters van de POST die op een gebeurtenisvraag worden overgegaan. Als u het niet gebruikt `isCoopSafe`, worden geen van beide doorgegeven in een gebeurtenisaanroep.

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuratiestatus </th> 
   <th colname="col2" class="entry"> Parameter POST </th> 
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

Met deze API&#39;s kunt u de `isCoopSafe` status. Deze zijn nodig omdat u hiermee de postinstantiërings- of postaanmeldingsstatus van een bezoeker kunt wijzigen op een site of in een app van één pagina waar de pagina niet wordt vernieuwd. U moet deze API&#39;s bijvoorbeeld aanroepen als een gebruiker zich op uw site of app aanmeldt en later een gebruiksbeleid accepteert waarmee de Device Co-op hun gegevens kan gebruiken.

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
   <td colname="col2"> <p>Hiermee wordt de parameter POST ingesteld <code> d_coop_safe=1 </code> in alle volgende gebeurtenisoproepen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>Hiermee wordt de parameter POST ingesteld <code> d_coop_unsafe=1 </code> in alle volgende gebeurtenisoproepen. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->
