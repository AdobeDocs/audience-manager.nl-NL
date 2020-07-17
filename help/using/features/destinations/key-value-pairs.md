---
description: Een sleutelwaardepaar bestaat uit verwante elementen A. Sleutel, die een constante is die de gegevensset definieert (bijv. geslacht, kleur, prijs) en een waarde, die een variabele is die tot de reeks behoort (bijv. man/vrouw, groen, 100). De Bouwer van de bestemming verzendt gegevens die als zeer belangrijk-waardeparen worden geformatteerd.
seo-description: Een sleutelwaardepaar bestaat uit verwante elementen A. Sleutel, die een constante is die de gegevensset definieert (bijv. geslacht, kleur, prijs) en een waarde, die een variabele is die tot de reeks behoort (bijv. man/vrouw, groen, 100). De Bouwer van de bestemming verzendt gegevens die als zeer belangrijk-waardeparen worden geformatteerd.
seo-title: Standaard en seriële sleutelwaardeparen
solution: Audience Manager
title: Standaard en seriële sleutelwaardeparen
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 3%

---


# Standaard en seriële sleutelwaardeparen {#standard-and-serial-key-value-pairs}

Een sleutelwaardepaar bestaat uit verwante elementen: Een sleutel, die een constante is die de gegevensset definieert (bijv. geslacht, kleur, prijs) en een waarde, die een variabele is die tot de set behoort (bijv. man/vrouw, groen, 100). [!UICONTROL Destination Builder] verzendt gegevens die als sleutel-waardeparen worden geformatteerd.

## Standaard sleutelwaardeparen {#basic-key-value-pairs}

Volledig gevormd, kon een basisreeks van zeer belangrijk-waardepaar als dit kijken:

* `gender = male`
* `color = green`
* `price > 100`

## Standaard en seriële sleutelwaardeparen {#standard-serial-key-value-pairs}

Doelen accepteren sleutelwaardegegevens in *`standard`* of *`serialized`* formaat.

* **Standaard sleutelwaardeparen:** Hiermee maakt u doelgegevens op in afzonderlijke sleutelwaardeparen. Elke toets wordt expliciet vermeld, zelfs wanneer deze opnieuw wordt gebruikt om een andere waarde te definiëren.
* **Geserialiseerde sleutel-waarde paren:** Verkleurt veelvoudige waarden in één enkel zeer belangrijk-waardepaar. In een geserialiseerd sleutel-waardepaar, scheidt een speciale indicator de waarden binnen de sleutel-waarde reeks.

Zowel standaard als geserialiseerde sleutel-waarden kunnen enige of veelvoudige waarden bevatten. De volgende tabel bevat voorbeelden van standaardindelingen en indelingen voor seriële sleutels en waarden.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opmaak </th>
   <th colname="col2" class="entry"> Enkele sleutelwaardeparen </th>
   <th colname="col3" class="entry"> Meerdere sleutelwaardeparen </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standaard</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Gesserveerd</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Scheidingstekens en scheidingstekens {#delimiters-separators}

De tekens die waarden binnen en tussen toetsen en waarden scheiden, worden *`delimiters`* en *`separators`*. Deze worden vooral belangrijk wanneer u segmenten naar een bestemming in een periodieke formaat verzendt. Met serienummering kunt u meerdere waarden doorgeven met één sleutel en sleutelwaardeparen combineren. Scheidingstekens en scheidingstekens worden als volgt gedefinieerd:

* **Scheidingsteken hoofdwaarde:** Scheidt een sleutel en een waarde binnen een zeer belangrijk-waardepaar.
* **Scheidingsteken voor hoofdwaarden:** Hiermee scheidt u sets sleutelwaardeparen.
* **Seriescheidingsteken:** Scheidt veelvoudige waarden binnen reeksen van geserialiseerde sleutel-waarde paren.

## Voorbeelden {#examples}

Met [!UICONTROL Destination Builder] u kunt sleutel-waardegegevens op verscheidene verschillende manieren formatteren. Laten we eens kijken naar enkele voorbeelden van elk type.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Voorbeelden van sleutelwaardeparen </th> 
   <th colname="col2" class="entry"> Voorbeeld </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standaard enkele toets</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Een eenvoudige set sleutelwaardeparen. Het voorbeeld bevat de volgende elementen: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Sleutel: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Waarden: 1,2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Scheidingsteken: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Scheidingsteken voor hoofdwaarden: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Meerdere sleutelwaardeparen</b> (niet-serieel) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Een set van meerdere sleutelwaardeparen die waarden doorgeven met afzonderlijke toetsensets. Het voorbeeld bevat de volgende elementen: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Toetsen: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Waarden: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Scheidingsteken: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Scheidingsteken voor hoofdwaarden: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Seriële enkele toets</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>Een sleutel-waarde die in veelvoudige waarden met één enkele sleutel overgaat. Omdat deze sleutel veelvoudige waarden heeft, is het gekend als geserialiseerd zeer belangrijk-waardepaar. Het voorbeeld bevat de volgende elementen: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Sleutel: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Waarden: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Scheidingsteken: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Seriescheidingsteken: puntkomma </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Meerdere sleutelwaardeparen</b> (serieel) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>Een set van meerdere sleutelwaardeparen die meerdere waarden doorgeven op afzonderlijke toetsen. Het voorbeeld bevat de volgende elementen: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Toetsen: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Waarden: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Scheidingsteken: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Scheidingsteken: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Seriescheidingsteken: puntkomma </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Serienummering bestemming {#destination-serialized}

Een geserialiseerde bestemming combineert veelvoudige eigenschappen in één enkel koord en verzendt die informatie naar een bestemming.

<!-- c_dest_serialized.xml -->

Geserialiseerde gegevensoverdracht draagt bij tot een efficiëntere werking omdat meerdere kenmerken achtereenvolgens worden afgehandeld in plaats van parallel. Dit verstrekt de bestemmingsserver genoeg tijd om, gegevens te ontvangen te verwerken en terug te keren alvorens op extra verzoeken te antwoorden.

### Ondersteunde doelen

In [!DNL Audience Manager], kunt u gegevens aan enkel om het even welke bestemming serialiseren en verzenden u wilt werken met. Voordat u deze functie kunt gebruiken, moet u echter weten wat het doel is [!DNL URL] en waar u bepaalde vereiste of optionele macro&#39;s wilt plaatsen. Verkrijg de informatie over macroplaatsing van uw bestemmingspartner. Zie [Gedefinieerde](../../features/destinations/destination-macros.md#destination-macros-defined) doelmacro&#39;s voor meer informatie.