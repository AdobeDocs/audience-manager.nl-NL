---
description: Verzamel gegevens die van FLA-bestanden naar Analytics zijn verzonden en werk in de Audience Manager met die gegevens.
seo-description: Verzamel gegevens die van FLA-bestanden naar Analytics zijn verzonden en werk in de Audience Manager met die gegevens.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---


# Flash DIL{#flash-dil}

Verzamel gegevens die van FLA-bestanden naar Analytics zijn verzonden en werk in de Audience Manager met die gegevens.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] is een [!DNL ActionScript] codebibliotheek waarmee u in Audience Manager kunt werken met videoafspeelgegevens. [!DNL Flash DIL] werkt door SWF-inhoud vast te leggen die de Adobe- [!UICONTROL AppMeasurement] bibliotheek doorgeeft aan Analytics. [!DNL Flash DIL] verzendt die gegevens naar de afzonderlijke module van de [!UICONTROL DIL] gegevensinzameling JavaScript, die die informatie tot Audience Manager overgaat. Analytics-gegevens ( [!UICONTROL Props], [!UICONTROL eVars], gebeurtenissen, enz.) die uit het [!DNL FLA] bestand zijn vastgelegd, is beschikbaar in de Audience Manager als karakteristieken of ongebruikte signalen.

## Vereisten voor Flash DIL-gegevensverzameling {#requirements}

Algemene eisen inzake implementatie en code.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementatievereisten**

[!UICONTROL Flash] gegevensverzameling vereist:

* De [!UICONTROL DIL] klassebibliotheek ( `dil.swc`). Verkrijg de [!UICONTROL DIL] klassenbibliotheek van uw contact van de Oplossingen van de Partner.

* JavaScript-code voor [!UICONTROL DIL] gegevensverzameling op de pagina.
* [DIL ActionScript bibliotheek](../dil/dil-flash.md#flash-dil-actionscript) geladen in het voorwerp van de Flits u gegevens wilt verzamelen van.
* In de Adobe [!DNL AppMeasurement] -bibliotheek (versie 3.5.2 of hoger) is het [!DNL AS] [!DNL Flash] object geladen waarvan u gegevens wilt verzamelen.

**AllowScriptAccess instellen op`Always`of`sameDomain`**

De `AllowScriptAccess` in HTML-code waarmee een SWF-bestand wordt geladen, bepaalt de mogelijkheid om uitgaande URL-toegang uit te voeren vanuit het SWF-bestand. Wanneer u een [!UICONTROL Flash DIL] gegevensintegratie configureert, moet u ervoor zorgen dat de Flash- `AllowScriptAccess` parameter is ingesteld op `always` of `sameDomain`. [!UICONTROL Flash DIL] gegevensverzameling werkt niet als `AllowScriptAccess` deze is ingesteld op `never`. Zie Toegang [tot scripts of Webpagina](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)van de host beheren.

**Plaatsing JS-[!UICONTROL DIL]code**

Probeer de JS- [!UICONTROL DIL] gegevensverzamelingsmodule op de pagina te plaatsen, zodat deze voor het [!DNL FLA] bestand wordt geladen. Wanneer het [!DNL FLA] dossier eerst laadt, alvorens de [!UICONTROL DIL] gegevensinzameling klaar is, kunt u de aanvankelijke gegevenssignalen missen die naar die module [!UICONTROL Flash DIL] verzenden. Wanneer de [!UICONTROL DIL] gegevensverzamelingsmodule echter eenmaal is geïnstantieerd, worden alle volgende SWF-bestandsgegevens vastgelegd die door [!UICONTROL Flash DIL]de gegevensverzamelingsmodule worden doorgegeven.

## Gegevens verzameld door Flash DIL {#data-collected}

[!UICONTROL Flash DIL] Hiermee legt u paginaweergave, koppelingen bijhouden, media bijhouden en andere mediaweergavegebeurtenissen vast uit de Adobe- [!UICONTROL AppMeasurement] bibliotheek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Paginaweergavegebeurtenissen**

Tenzij anders aangegeven door `s.trackVars`, [!UICONTROL Flash DIL] worden de volgende gegevens verzameld van Adobe AppMeturement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Gebeurtenissen voor bijhouden van koppelingen**

Tenzij anders aangegeven door `s.linkTrackVars`, [!UICONTROL Flash DIL] worden de volgende gegevens verzameld bij Adobe [!UICONTROL AppMeasurement]:

* `pe` (Type spoorverbinding geroepen)
* `pev1` (Koppeling-URL)
* `pev2`(Koppelingstekst)

**Gebeurtenissen voor het bijhouden van media**

Tenzij anders aangegeven door `s.Media.trackVars`[!UICONTROL Flash DIL] , worden alle gegevens verzameld die in de sectie Gebeurtenissen paginaweergave zijn opgesomd.

**Andere gegevenspunten**

De gegevens van deze parameters worden standaard verzameld:

* `mediaName` (Naam media/video-element)
* `mediaAdName` (Advertentienaam)
* `mediaAdParentName` (Naam van de inhoud van het primaire medium waarop de advertentie is genest)
* `mediaAdParentPod` (De pod of het ad-einde binnen de primaire inhoud waar de advertentie wordt afgespeeld)
* `mediaAdParentPodPos` (De numerieke positie binnen de pod waarin de advertentie wordt afgespeeld. Meer dan één advertentie kan in een pod worden afgespeeld.

## Flash DIL-gegevens in Audience Manager {#flash-dil-data}

De [!UICONTROL Flash DIL] module zet Adobe AppMeturement-gegevens om in Audience Manager-eigenschappen en ongebruikte signalen.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars]en gebeurtenissen werken als eigenschappen in de Audience Manager. De sporen zijn zeer belangrijk-waardeparen en worden gebruikt om segmenten te bouwen. In een Analytics-proxy `c30=foo`is dit bijvoorbeeld `c30` de sleutel (een constante) en `foo` de waarde (een variabele).

**Audience Manager traits afstemmen op Analytics-variabelen**

Als u de Analytics-gegevens wilt gebruiken die zijn doorgegeven, [!UICONTROL Flash DIL]moet u Audience Manager-eigenschappen maken waarvan de hoofdwaarde vooraf is bepaald `c_`.

Zie de tabel voor voorbeelden:

| Analytics-gegevenselement | Analytics-voorbeeld | Als Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **vervagen** | `v35=bar` | `c_evar35=bar` |
| **gebeurtenissen** | `events=event10` | `c_events=event10` |

**DIL/Analytics-gegevens als ongebruikte signalen**

Audience Manager accepteert Analytics [!UICONTROL Props], [!UICONTROL eVars]en gebeurtenissen zelfs zonder overeenkomende eigenschap. In dit geval zijn de gegevens niet beschikbaar voor het maken van sporen en worden deze in plaats daarvan weergegeven in het rapport [](../reporting/dynamic-reports/unused-signals.md) Ongebruikte signalen. Als u deze informatie optimaal wilt benutten, maakt u Audience Managers die overeenkomen met de Analytics-gegevens die door de [!UICONTROL Flash DIL] bibliotheek worden doorgegeven.

## Flash DIL ActionScript-bibliotheek {#flash-dil-actionscript}

Code voor uw [!DNL Flash] object om Analytics-gegevens naar de Audience Manager te verzenden.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Voor elk [!DNL Flash] voorwerp, steunt de code slechts één partnerinstantie ( `d.partner`).
   >
   >
* Hiervoor is Adobe [!UICONTROL AppMeasurement] [!DNL AS] Library versie 3.5.2 of hoger vereist.


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
>* [Treinen](../features/traits/trait-details-page.md)
>* [Signalen, Traits en Segmenten](../reference/signal-trait-segment.md)
>* [Belangrijke paar uitgelegd](../reference/key-value-pairs-explained.md)
>* [Voorvoegselvereisten voor belangrijkste variabelen](../features/traits/trait-variable-prefixes.md)

