---
description: Verzamel gegevens die vanuit FLA-bestanden naar Analytics zijn verzonden en werk in de Audience Manager met die gegevens.
seo-description: Verzamel gegevens die vanuit FLA-bestanden naar Analytics zijn verzonden en werk in de Audience Manager met die gegevens.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 2%

---


# Flash DIL{#flash-dil}

Verzamel gegevens die vanuit FLA-bestanden naar Analytics zijn verzonden en werk in de Audience Manager met die gegevens.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] is een  [!DNL ActionScript] codebibliotheek waarmee u in Audience Manager kunt werken met videoafspeelgegevens. [!DNL Flash DIL] werkt door SWF-inhoud vast te leggen die de Adobe- [!UICONTROL AppMeasurement] bibliotheek doorgeeft aan Analytics. [!DNL Flash DIL] verzendt die gegevens naar de afzonderlijke module van de  [!UICONTROL DIL] gegevensinzameling JavaScript, die die informatie tot Audience Manager overgaat. Analysegegevens ( [!UICONTROL Props], [!UICONTROL eVars], gebeurtenissen, enz.) die zijn vastgelegd vanuit het [!DNL FLA]-bestand, is beschikbaar in de Audience Manager als karakteristieken of ongebruikte signalen.

## Vereisten voor gegevensverzameling Flash DIL {#requirements}

Algemene eisen inzake implementatie en code.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementatievereisten**

[!UICONTROL Flash] gegevensverzameling vereist:

* De [!UICONTROL DIL] klassenbibliotheek ( `dil.swc`). Verkrijg de [!UICONTROL DIL] klassenbibliotheek van uw contact van de Oplossingen van de Partner.

* JavaScript [!UICONTROL DIL]-code voor gegevensverzameling op de pagina.
* [DIL ActionScript-](../dil/dil-flash.md#flash-dil-actionscript) bibliotheek geladen in het Flash-object waarvan u gegevens wilt verzamelen.
* Adobe [!DNL AppMeasurement] [!DNL AS]-bibliotheek (versie 3.5.2 of hoger) heeft het [!DNL Flash]-object geladen waarvan u gegevens wilt verzamelen.

**AllowScriptAccess instellen op  `Always` of`sameDomain`**

Met de `AllowScriptAccess` in HTML-code waarmee een SWF-bestand wordt geladen, kunt u uitgaande URL-toegang uitvoeren vanuit het SWF-bestand. Wanneer u een [!UICONTROL Flash DIL] gegevensintegratie vormt, zorg ervoor de Flash `AllowScriptAccess` parameter aan `always` of `sameDomain` wordt geplaatst. [!UICONTROL Flash DIL] gegevensverzameling werkt niet als  `AllowScriptAccess` deze is ingesteld op  `never`. Zie [Toegang tot scripts of Web-pagina van host](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html) beheren.

**Plaatsing van JS- [!UICONTROL DIL] code**

Plaats de JS [!UICONTROL DIL]-module voor gegevensverzameling op de pagina, zodat deze wordt geladen vóór het [!DNL FLA]-bestand. Wanneer het [!DNL FLA] dossier eerst laadt, alvorens [!UICONTROL DIL] gegevensinzameling klaar is, kunt u de aanvankelijke gegevenssignalen missen die [!UICONTROL Flash DIL] naar die module verzendt. Als de gegevensverzamelingsmodule [!UICONTROL DIL] echter eenmaal is geïnstantieerd, worden alle volgende SWF-bestandsgegevens vastgelegd die door [!UICONTROL Flash DIL] worden doorgegeven.

## Gegevens verzameld door Flash DIL {#data-collected}

[!UICONTROL Flash DIL] Hiermee legt u paginaweergave, koppelingen bijhouden, media bijhouden en andere mediaweergavegebeurtenissen vast uit de  [!UICONTROL AppMeasurement] Adobe-bibliotheek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Paginaweergavegebeurtenissen**

Tenzij anders gespecificeerd door `s.trackVars`, verzamelt [!UICONTROL Flash DIL] de volgende gegevens van Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Gebeurtenissen voor bijhouden van koppelingen**

Tenzij anders aangegeven door `s.linkTrackVars`, verzamelt [!UICONTROL Flash DIL] de volgende gegevens van Adobe [!UICONTROL AppMeasurement]:

* `pe` (Type spoorverbinding geroepen)
* `pev1` (Koppeling-URL)
* `pev2`(Koppelingstekst)

**Gebeurtenissen voor het bijhouden van media**

Tenzij anders gespecificeerd door `s.Media.trackVars`, [!UICONTROL Flash DIL] verzamelt alle gegevens die in de sectie van de Gebeurtenissen van de Mening van de Pagina worden opgesomd.

**Andere gegevenspunten**

De gegevens van deze parameters worden standaard verzameld:

* `mediaName` (Naam media/video-element)
* `mediaAdName` (Advertentienaam)
* `mediaAdParentName` (Naam van de inhoud van het primaire medium waarop de advertentie is genest)
* `mediaAdParentPod` (De pod of het ad-einde binnen de primaire inhoud waar de advertentie wordt afgespeeld)
* `mediaAdParentPodPos` (De numerieke positie binnen de pod waarin de advertentie wordt afgespeeld. Meer dan één advertentie kan in een pod worden afgespeeld.

## Flash DIL-gegevens in Audience Manager {#flash-dil-data}

Met de module [!UICONTROL Flash DIL] worden Adobe AppMeasurement-gegevens omgezet in Audience Manager-eigenschappen en ongebruikte signalen.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analyses [!UICONTROL Props], [!UICONTROL eVars] en gebeurtenissen werken als kenmerken in de Audience Manager. De sporen zijn zeer belangrijk-waardeparen en worden gebruikt om segmenten te bouwen. In een analysehulpmiddel zoals `c30=foo` is `c30` bijvoorbeeld de sleutel (een constante) en `foo` is de waarde (een variabele).

**Audience Manager-eigenschappen afstemmen op analytische variabelen**

Als u de analysegegevens wilt gebruiken die door [!UICONTROL Flash DIL] worden doorgegeven, moet u Audience Manager-eigenschappen maken die de hoofdwaarde hebben die vooraf met `c_` is ingesteld.

Zie de tabel voor voorbeelden:

| Gegevenselement Analytics | Voorbeeld van analyse | Als Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **vervagen** | `v35=bar` | `c_evar35=bar` |
| **gebeurtenissen** | `events=event10` | `c_events=event10` |

**DIL-/analysegegevens als ongebruikte signalen**

Audience Manager accepteert Analytics [!UICONTROL Props], [!UICONTROL eVars] en gebeurtenissen, zelfs zonder overeenkomende eigenschap. In dit geval zijn de gegevens niet beschikbaar voor het maken van sporen en worden deze in plaats daarvan weergegeven in het [rapport Niet-gebruikte signalen](../reporting/dynamic-reports/unused-signals.md). Om het grootste deel van deze informatie te maken, creeer de eigenschappen van de Audience Manager die de gegevens van Analytics aanpassen die door de [!UICONTROL Flash DIL] bibliotheek worden overgegaan.

## Flash DIL ActionScript-bibliotheek {#flash-dil-actionscript}

Code voor het object [!DNL Flash] om analysegegevens naar de Audience Manager te verzenden.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Voor elk [!DNL Flash] voorwerp, steunt de code slechts één partnerinstantie ( `d.partner`).
   >
   >
* Vereist de Adobe [!UICONTROL AppMeasurement] [!DNL AS] bibliotheekversie 3.5.2 of hoger.


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [Eigenschappen ](../features/traits/trait-details-page.md)
>* [Signalen, eigenschappen en segmenten](../reference/signal-trait-segment.md)
>* [Sleutelwaardeparen](../reference/key-value-pairs-explained.md)
>* [Voorvoegselvereisten voor belangrijke variabelen](../features/traits/trait-variable-prefixes.md)

