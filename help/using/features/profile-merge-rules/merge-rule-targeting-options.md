---
description: De opties van de Regels van de Fusie van het profiel laten u publieksnadruk op specifiek publiek uitbreiden of versterken dat op bedrijfsbehoeften of doelstellingen wordt gebaseerd. Deze algemene gebruiksgevallen onderzoeken hoe u beschikbare opties kunt gebruiken en fusieregels kunt maken voor individuele, huishoudelijke en apparaatspecifieke toepassingen.
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: Algemene gebruiksscenario’s voor regels voor profielsamenvoeging
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 2%

---

# Algemene gebruiksscenario’s voor regels voor profielsamenvoeging {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] met opties kunt u de doelgroep meer of sterker richten op specifieke doelgroepen op basis van zakelijke behoeften of doelstellingen. Deze algemene gebruiksgevallen onderzoeken hoe u beschikbare opties kunt gebruiken en fusieregels kunt maken voor individuele, huishoudelijke en apparaatspecifieke toepassingen. [!UICONTROL Profile Merge Rules] werken met realtime en batchbestemmingen.

>[!TIP]
>
>Voor definities en beschrijvingen van deze [!UICONTROL Merge Rule] instellingen, zie [Opties voor regel voor samenvoegen van profiel gedefinieerd](merge-rule-definitions.md).

## Apparaatgericht {#device-personalization}

Dit scenario is op marketers van toepassing die één enkel apparatenprofiel voor een publiekssegment willen evalueren dat in Audience Manager wordt bepaald, om een verenigbare ervaring aan het apparaat te leveren gebruikend richtende platforms die apparaat IDs steunen (DSP, op-plaats verpersoonlijkingsplatforms en andere op apparaat-gebaseerde het richten platforms), die geen rekening houden met gebruikersauthentificatie.

Selecteer **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![alleen apparaat](assets/device-only.png)

Laten we zeggen dat John drie smartphones heeft. Twee ervan zijn iPhone 7s op Data Plan A, en één daarvan is een Samsung op Data Plan B. Zonder rekening te houden met zijn voor authentiek verklaarde staat op om het even welke drie apparaten, wil de mobiele drager van John hem een verbetering van het gegevensplan, maar slechts voor iPhone 7 apparaten aanbieden die op Plan A van Gegevens lopen.

Met de **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** regel, [!DNL Device 1] en [!DNL Device 3] beide komen voor het segment in aanmerking, terwijl Apparaat 2 wordt genegeerd.

![alleen apparaat](assets/device-management.png)

## Gedeelde apparaatdoelen {#target-shared-devices}

Laten we zeggen dat John en zijn vrouw, Jane, dezelfde laptop gebruiken om een online winkel te bezoeken en verschillende artikelen te bestellen.

John gebruikt zijn eigen account om reistickets en speciale deals te boeken, terwijl Jane haar eigen account gebruikt om muziek en films te kopen.

Het marketingteam van de winkel kan de **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** regel om John en Jane met specifieke overeenkomsten te richten, die op hun authentiek verklaarde activiteit worden gebaseerd.

![current-no-device](assets/current-no-device.png)

Door deze regel te gebruiken, negeert de Audience Manager volledig het apparatenprofiel, kwalificerend identiteitskaart van CRM van John voor het segment, en niet kwalificerend identiteitskaart van CRM van Jane.

![gedeelde apparaatgericht](assets/shared-device-targeting.png)

## Online/offline gericht {#device-household-targeting}

Dit gebruiksgeval heeft betrekking op identiteitsbeheer van huishoudens. Een bedrijf kan één enkel apparatenprofiel met het laatste profiel samenvoegen dat op dat apparaat voor authentiek verklaarde, gebruikend **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** regel.

![last-device-profile](assets/last-device-profile.png)

Laten we eens kijken naar een segment van huishoudens met een inkomen van meer dan $100.000/jaar, dat minstens één apparaat bevat dat een [!DNL iPhone 7] op [!DNL Data Plan B]. We hebben twee huishoudelijke profielen (profielen voor verschillende apparaten), die elk zijn aangesloten op twee verschillende apparaatprofielen. De kenmerken die nodig zijn om voor het segment in aanmerking te komen, worden verdeeld over het apparaat en de profielen voor alle apparaten.

De Audience Manager voegt elk apparaat + dwars-apparatenprofielpaar samen om te zien of kwalificeert de samengevoegde reeks eigenschappen voor het segment. Aangezien Audience Manager elk profiel evalueert dat in de samenvoeging was opgenomen, kunnen zowel een apparaatprofiel als een huishoudelijk profiel worden gesegmenteerd.

Dankzij de koppeling tussen het apparaat en het profiel van het huishouden kan de Audience Manager in aanmerking komen [!DNL Household 2] voor het segment, maar niet [!DNL Household 1]. Van [!DNL Household 2], alleen [!DNL Device 3] kwalificeert voor het segment. Dit [!UICONTROL Profile Merge Rule] heeft de tellers toegelaten om een verenigbaar marketing bericht aan een individueel apparaat te leveren ([!DNL Device 3]) en het bredere huishouden ([!DNL Household 2]).

![beheer van huishoudens](assets/household-management.png)

## Doelen voor op mensen gebaseerde bestemmingen {#all-cross-device}

>[!IMPORTANT]
>
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Dit scenario is alleen beschikbaar voor klanten die het [!DNL People-Based Destinations] invoegtoepassing. Deze regel staat marketers toe om klanten te bereiken die op hun eigen, voor authentiek verklaarde gegevens worden gebaseerd.

Laten we zeggen dat een online detailhandelaar bestaande klanten wil bereiken via sociale platforms en hun persoonlijke aanbiedingen wil laten zien op basis van hun eerdere bestellingen. Met [!UICONTROL People-Based Destinations], kunnen ze hashes-e-mailadressen vanuit hun eigen e-mailadres invoeren [!DNL CRM] in de Audience Manager, maak segmenten van de off-line gegevens, en verzend deze segmenten naar de sociale platforms zij willen adverteren op, gebruikend dat haastige herkenningsteken, optimaliserend hun reclame-uitgaven.

Ga voor meer informatie over deze optie naar [Bestemmingen op basis van personen](../destinations/people-based-destinations-overview.md).

![alles-over-apparaat](assets/all-cross-device.png)

## Grafiekopties apparaat {#device-graph-options}

Een [!UICONTROL device graph] optie voor een [!UICONTROL Profile Merge] de regel hangt van voorwaarden uniek aan uw digitale eigenschappen en bedrijfsdoelstellingen af. Deze algemene richtlijnen kunnen u helpen begrijpen wanneer om één type van grafiek tegenover een andere te gebruiken. Opmerking: als u deze opties wilt gebruiken, moet u een contractuele relatie hebben met een externe apparaatgrafiek. Raadpleeg de onderstaande tabel voor algemene informatie over de keuze van een grafiekoptie voor apparaten. Voor specifieke gevallen van gebruik, zie [Gebruiksscenario&#39;s voor grafiekgebruik van profielkoppeling](profile-link-use-case.md) en [Gebruiksscenario&#39;s externe apparaatgrafiek](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type apparaatgrafiek </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Apparaatgrafiek profielkoppeling</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profielsamenvoeging</span> met de <span class="wintitle"> Profielkoppeling</span> Deze optie is ideaal voor: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Digitale eigenschappen die een hoog niveau van klantenauthentificatie hebben. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Gerichte, weinig bereikbare campagnes. De <span class="wintitle"> Profielkoppeling</span> apparaatgrafiek is alleen gebaseerd op deterministische gegevens. Deze groep apparaatprofielen is altijd kleiner dan de groep niet-geverifieerde gebruikers en apparaten. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Gebruik gevallen waarin klanten zich in een geverifieerde status moeten bevinden om in aanmerking te komen voor segmentatie. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opties externe apparaatgrafiek </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profielsamenvoeging</span> regels die zijn gebouwd met elke externe apparaatgrafiek die is geïntegreerd met <span class="keyword"> Audience Manager</span> zijn ideaal voor: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Digitale eigenschappen die een laag niveau van klantenauthentificatie hebben. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Brede, geavanceerde merkcampagnes. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Gebruik gevallen waarin klanten zich niet in een geverifieerde staat hoeven te bevinden om in aanmerking te komen voor segmentatie. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Bekijk de onderstaande video voor een overzicht van mogelijke gebruiksgevallen voor [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Gebruiksscenario’s voor apparaatgrafieken van profielkoppelingen](profile-link-use-case.md)
>* [Gebruiksscenario’s voor grafiek van externe apparaten](external-graph-use-cases.md)
>* [Veelgestelde vragen over regels voor samenvoegen van profielen](../../faq/faq-profile-merge.md)

