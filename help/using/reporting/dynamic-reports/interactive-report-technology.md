---
description: Beschrijft de onderliggende software die de interactieve rapporten en het programma van de gegevensupdate bevoegdheden.
seo-description: Beschrijft de onderliggende software die de interactieve rapporten en het programma van de gegevensupdate bevoegdheden.
seo-title: Rapporttechnologie
solution: Audience Manager
title: Rapporttechnologie
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Rapporttechnologie{#report-technology}

Beschrijft de onderliggende software die de interactieve rapporten en het programma van de gegevensupdate bevoegdheden.

<!-- 

c_report_technology.xml

 -->

## Interactieve rapporten gebruiken Tableau-technologie

[!DNL Audience Manager] gebruikt de [software van Tableau](https://www.tableausoftware.com/) om gegevens in de interactieve rapporten te tonen. Met [!DNL Tableau], gebruiken de [!UICONTROL Delivery and Overlap] rapporten visuele aanwijzingen en symbolen die u helpen:

* Kies voor hoge en lage prestaties.
* Steunkleurovergangen en -segmenten met een lage en hoge unieke bezoekersoverlapping.
* Gebruik overlappende gegevens om doelsegmenten samen te stellen.
* Breid bereik uit door verwante kenmerken met een lage overlapping te identificeren.

## Gegevensupdateschema

De rapportgegevens worden elke zondag wekelijks bijgewerkt. De update verwerkt gegevens van zaterdag (de dag daarvoor) terug naar vorige zondag.

## Vormen, kleuren en grootten die worden gebruikt in interactieve rapporten {#shapes-colors-sizes}

De meeste interactieve rapporten geven resultaten weer met vormen van verschillende grootten en kleuren. Deze weergave-indeling is ontworpen om u te helpen visueel inzicht te krijgen in de gegevens zonder dat u door rijen en kolommen met getallen hoeft te bladeren.

<!-- 

r_legend.xml

 -->

### Legenda rapporteren

In de volgende tabel worden de vormen, grootten en kleuren gedefinieerd die worden gebruikt in dynamische rapporten.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gegevenselement </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Vormen</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">De cirkels wijzen op uw eigen eerstepartijeigenschappen. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Vierkantjes geven de eigenschappen van derden aan. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kleuren</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Rode schaduwen geven <i>een lage</i> overlapping aan. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Groene tinten geven <i>een hoge</i> overlapping aan. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grootte</b> </td> 
   <td colname="col2"> De grootte neemt toe of daalt direct in verhouding tot bereik (het aantal of % van kliks of unieke gebruikers in een eigenschap of een segment). </td> 
  </tr> 
 </tbody> 
</table>

## Verklaarde pictogrammen en gereedschappen rapporteren {#icons-tools-explained}

Beschrijft hoe te om diverse pictogram-hulpmiddelen te zoeken en te gebruiken die in de dynamische rapporten worden gebruikt.

<!-- 

r_icons.xml

 -->

### Gegevenspictogrammen en -gereedschappen

De volgende pictogrammen-hulpmiddelen zijn beschikbaar bij de bodem van elk dynamisch rapportvenster. In de volgende afbeelding vindt u meer informatie over deze gereedschappen.

![](assets/tools_icons90.png)

### Gegevens exporteren

Met deze gereedschappen kunt u gegevens uit het rapport in vier verschillende indelingen exporteren.

| Exportoptie | Gegevens worden geëxporteerd |
|---|---|
| **[!UICONTROL Image]** | Als afbeeldingsbestand (.png). Nuttig wanneer u rapportgegevens in zijn originele, grafische formaat wilt downloaden en delen. |
| **[!UICONTROL PDF]** | Als PDF-bestand. |
| **[!UICONTROL Data]** | In een nieuw browservenster als numerieke gegevens in kolommen en rijen. |
| **[!UICONTROL Crosstab]** | Als CSV-bestand. |

### Wijzigingen herstellen

Selecteer dit hulpmiddel om het even welke interactieve klikveranderingen ongedaan te maken u op het rapport kunt uitgevoerd.

### Automatische updates

De [!UICONTROL Delivery-Performance] en [!UICONTROL Trait-to-Trait Overlap] rapporten zijn dynamische rapporten die antwoorden en veranderen gebaseerd op acties van de gebruikersklik.

Stel bijvoorbeeld dat u verschillende adverteerders in het [!UICONTROL Overlap] rapport wilt selecteren. Als deze optie is ingeschakeld, worden automatisch bijgewerkte gegevens geretourneerd zodra u een selectievakje hebt ingeschakeld. Dit dynamische gedrag kan uw werkstroom onderbreken omdat u moet wachten tot het rapport klaar is met verwerken voordat u een andere adverteerder selecteert. Gebruik dit gereedschap om die functie naar wens uit te schakelen (en weer in te schakelen).

### Gegevens vernieuwen

Klik op het pictogram Vernieuwen om een rapport uit te voeren of de gegevensset opnieuw te laden. Wanneer de automatische updates weg zijn, verfrist de klik zich om het rapport in werking te stellen of bij te werken.

### Zoeken

De zoekopdracht wordt aangeduid met een generiek vergrootglaspictogram (niet weergegeven). Het zoekveld wordt verborgen totdat u op de selectielabels aan de linkerkant van het scherm klikt. In de onderstaande tabel wordt de locatie van het zoekprogramma voor elk rapport beschreven.

| Rapport | Als u een zoekopdracht wilt zoeken, houdt u de muisaanwijzer boven |
|---|---|
| [!UICONTROL Delivery and Performance] verslag | Het label Advertiser Name. |
| [!UICONTROL Overlap] rapporten | Het label &#39;SID Name&#39;. |
