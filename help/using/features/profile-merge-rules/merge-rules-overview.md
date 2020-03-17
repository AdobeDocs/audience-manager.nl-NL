---
description: Met de Regels van de Fusie van het Profiel krijgt u controle over de gegevensreeksen die voor segmentatie worden gebruikt en kan een persoon nauwkeurig over veelvoudige apparaten richten.
seo-description: Met de Regels van de Fusie van het Profiel krijgt u controle over de gegevensreeksen die voor segmentatie worden gebruikt en kan een persoon nauwkeurig over veelvoudige apparaten richten.
seo-title: Overzicht van regels voor samenvoegen van profielen
solution: Audience Manager
title: Overzicht van regels voor samenvoegen van profielen
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Overzicht van regels voor samenvoegen van profielen {#profile-merge-rules-overview}

Met [!UICONTROL Profile Merge Rules] u kunt bepalen welke gegevenssets worden gebruikt voor segmentatie en kunt u gebruikers nauwkeurig als doel instellen op meerdere apparaten.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Gegevensverzameling en het richten met anonieme en voor authentiek verklaarde profielen {#data-collection-targeting}

Doorgaans is segmentering van het publiek en gericht afhankelijk van gegevens die zijn verzameld bij alle gebruikers op een apparaat. Gegevensverzameling en -gerichtheid op basis van apparaatgegevens heeft enkele nadelen. U kunt bijvoorbeeld geen onderscheid maken tussen meerdere gebruikers die een apparaat delen of gebruikers op meerdere apparaten nauwkeurig als doel instellen. Apparaatgecentreerde gegevensverzameling is niet langer voldoende voor digitale marketingcampagnes of het maken van apparaatspecifieke doelgroepen.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] verandert fundamenteel hoe gegevens en segmenten gebruikers voor het richten [!DNL Audience Manager] verzamelen. Hiermee kunt u werken met twee verschillende typen profielen, een apparaatprofiel en een [geverifieerd profiel](../../reference/visitor-authentication-states.md).

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Profieltype </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Apparaatprofiel </td> 
   <td colname="col2"> <p>Een apparaatprofiel is gekoppeld aan een id voor een bepaald apparaat, zoals een cookie-id of een mobiele apparaat-id. Het omvat: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Op regel-gebaseerde eigenschappen die worden gerealiseerd wanneer een gebruiker niet voor authentiek wordt verklaard. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Aan boord genomen kenmerken die zijn gekoppeld aan een apparaat-id, zoals op cookie gebaseerde gegevens van derden. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Geverifieerd profiel </td> 
   <td colname="col2"> <p>Het geverifieerde profiel is gekoppeld aan een gebruikers-id die wordt doorgegeven wanneer een persoon zich aanmeldt bij uw site. Hieronder vallen </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Op regel-gebaseerde eigenschappen die over apparaten worden verzameld wanneer een gebruiker voor authentiek wordt verklaard. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Gecontroleerde kenmerken in een offlinebestand dat aan dezelfde gebruiker-id is gekoppeld. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Deze verschillende profielen bepalen de gegevens die u voor segmentatie kunt gebruiken. Met een [geverifieerd profiel](../../reference/visitor-authentication-states.md)kunt u bijvoorbeeld nauwkeurige segmenten maken op basis van gegevens van meerdere apparaten voor één gebruiker. Dit betekent dat u klanten op meerdere apparaten een consistente merkervaring kunt bieden. De Manager van de publiek bereikt dit door de afbeelding van de verschillende apparaten op te slaan een persoon voor hun online activiteiten aan hun [voor authentiek verklaard profiel](../../reference/visitor-authentication-states.md)gebruikt. Deze toewijzingen worden het [!UICONTROL Profile Link Device Graph]genoemd.

![](assets/authenticated2.png)

## Voordelen {#advantages}

Met [!UICONTROL Profile Merge Rules] u kunt:

* Doelgebruikers op basis van [geverifieerd profiel](../../reference/visitor-authentication-states.md), anonieme profielen of combinaties van beide.
* Richt een specifieke klant over hun apparaten.
* Bouw een apparatengrafiek die op deterministische gegevens wordt gebaseerd.
* U kunt de gegevens in de segmenten nauwkeurig afstemmen op basis van verschillende profielen.
* Verbeter extra inzicht in uw publiek.
