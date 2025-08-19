---
description: Verzamel gegevens die vanuit FLA-bestanden naar Analytics zijn verzonden en werk in Audience Manager met die gegevens.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 1%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de extensie [!DNL Data Integration Library (DIL)] en [!DNL DIL] stopgezet.
>
>Bestaande klanten kunnen hun [!DNL DIL] -implementatie blijven gebruiken. Adobe ontwikkelt [!DNL DIL] echter niet verder dan dit punt. De klanten worden aangemoedigd om [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) voor hun lange termijn strategie van de gegevensinzameling te evalueren.
>
>De klanten die nieuwe integratie van de gegevensinzameling na Juli 2023 willen uitvoeren zouden [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) in plaats daarvan moeten gebruiken.

Verzamel gegevens die vanuit FLA-bestanden naar Analytics zijn verzonden en werk in Audience Manager met die gegevens.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] is een [!DNL ActionScript] -codebibliotheek waarmee u in Audience Manager kunt werken met videoafspeelgegevens. [!DNL Flash DIL] werkt door SWF-inhoud vast te leggen die de Adobe [!UICONTROL AppMeasurement] -bibliotheek doorgeeft aan Analytics. [!DNL Flash DIL] verzendt die gegevens naar de afzonderlijke [!UICONTROL DIL] JavaScript-module voor gegevensverzameling, die die informatie doorgeeft aan Audience Manager. Analytische gegevens ( [!UICONTROL Props] , [!UICONTROL eVars] , gebeurtenissen, enz.) die uit het [!DNL FLA] -bestand zijn vastgelegd, zijn in Audience Manager beschikbaar als kenmerkende of ongebruikte signalen.

## Vereisten voor Flash DIL-gegevensverzameling {#requirements}

Algemene eisen inzake implementatie en code.

<!-- 

c_flash_dil_intro.xml

 -->

**Vereisten van de Implementatie**

[!UICONTROL Flash] gegevensverzameling vereist:

* De [!UICONTROL DIL] -klassebibliotheek ( `dil.swc` ). Verkrijg de [!UICONTROL DIL] klassenbibliotheek van uw contact van de Oplossingen van de Partner.

* JavaScript [!UICONTROL DIL] -code voor gegevensverzameling op de pagina.
* [ de bibliotheek van ActionScript van DIL ](../dil/dil-flash.md#flash-dil-actionscript) geladen in het voorwerp van de Flits u gegevens van wilt verzamelen.
* Adobe [!DNL AppMeasurement] [!DNL AS] library (versie 3.5.2 of hoger) heeft het [!DNL Flash] -object geladen waarvan u gegevens wilt verzamelen.

**plaats AllowScriptAccess aan `Always` of`sameDomain`**

De `AllowScriptAccess` in HTML-code die een SWF-bestand laadt, bepaalt de mogelijkheid om uitgaande URL-toegang uit te voeren vanuit het SWF-bestand. Wanneer u een [!UICONTROL Flash DIL] -gegevensintegratie configureert, moet u ervoor zorgen dat de Flash-parameter `AllowScriptAccess` is ingesteld op `always` of `sameDomain` . [!UICONTROL Flash DIL] -gegevensverzameling werkt niet als `AllowScriptAccess` is ingesteld op `never` . Zie {de Toegang van 0} Controle tot Manuscripten of Web-pagina van de Gastheer [.](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)

**JS [!UICONTROL DIL] Plaatsing van de Code**

Probeer de JS [!UICONTROL DIL] -gegevensverzamelingsmodule op de pagina te plaatsen, zodat deze voor het [!DNL FLA] -bestand wordt geladen. Wanneer het [!DNL FLA] -bestand het eerst wordt geladen, voordat [!UICONTROL DIL] -gegevensverzameling gereed is, kunt u de eerste gegevenssignalen die [!UICONTROL Flash DIL] naar die module verzendt, overslaan. Als de gegevensverzamelingsmodule [!UICONTROL DIL] echter eenmaal is geïnstantieerd, worden alle volgende SWF-bestandsgegevens vastgelegd die door [!UICONTROL Flash DIL] worden doorgegeven.

## Gegevens verzameld door Flash DIL {#data-collected}

[!UICONTROL Flash DIL] legt paginaweergave, koppelingen bijhouden, media bijhouden en andere mediaweergavegebeurtenissen vast vanuit de Adobe [!UICONTROL AppMeasurement] -bibliotheek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Gebeurtenissen van de Mening van de Pagina**

Tenzij anders opgegeven door `s.trackVars` , verzamelt [!UICONTROL Flash DIL] de volgende gegevens vanuit Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Verbinding die Gebeurtenissen** volgen

Tenzij anders opgegeven door `s.linkTrackVars` , verzamelt [!UICONTROL Flash DIL] de volgende gegevens vanuit Adobe [!UICONTROL AppMeasurement] :

* `pe` (Type spoorverbinding geroepen)
* `pev1` (URL van koppeling)
* `pev2` (Koppelingstekst)

**Media die Gebeurtenissen volgen**

Tenzij anders opgegeven door `s.Media.trackVars` , verzamelt [!UICONTROL Flash DIL] alle gegevens die zijn opgesomd in de sectie Gebeurtenissen paginaweergave.

**Andere Punten van Gegevens**

De gegevens van deze parameters worden standaard verzameld:

* `mediaName` (naam media/video-element)
* `mediaAdName` (Advertentienaam)
* `mediaAdParentName` (Naam van de primaire media-inhoud waaronder de advertentie is genest)
* `mediaAdParentPod` (De pod of het ad-einde binnen de primaire inhoud waar de advertentie wordt afgespeeld)
* `mediaAdParentPodPos` (De numerieke positie in de pod waarin de advertentie wordt afgespeeld. Meer dan één advertentie kan in een pod worden afgespeeld.

## Flash DIL-gegevens in Audience Manager {#flash-dil-data}

De module [!UICONTROL Flash DIL] verandert Adobe AppMeasurement-gegevens in Audience Manager-kenmerken en ongebruikte signalen.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analyses [!UICONTROL Props] , [!UICONTROL eVars] en gebeurtenissen werken als eigenschappen in Audience Manager. De sporen zijn zeer belangrijk-waardeparen en worden gebruikt om segmenten te bouwen. In een analysehulpmiddel als `c30=foo` is `c30` bijvoorbeeld de sleutel (een constante) en `foo` de waarde (een variabele).

**de Rondjes van de Gelijke Audience Manager aan de Variabelen van Analytics**

Als u de analysegegevens wilt gebruiken die door [!UICONTROL Flash DIL] worden doorgegeven, moet u Audience Manager-kenmerken maken waarvan de hoofdwaarde vooraf is bepaald door `c_` .

Zie de tabel voor voorbeelden:

| Gegevenselement Analytics | Voorbeeld van analyse | Als Audience Manager Trait |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **gebeurtenissen** | `events=event10` | `c_events=event10` |

**Gegevens DIL/Analytics als Ongebruikte Signalen**

Audience Manager accepteert Analytics [!UICONTROL Props] , [!UICONTROL eVars] en gebeurtenissen, zelfs zonder bijbehorend kenmerk. In dit geval, zijn de gegevens niet beschikbaar voor het verwezenlijking van de eigenschap en verschijnen in het [ Ongebruikte rapport van Signalen ](../reporting/dynamic-reports/unused-signals.md) in plaats daarvan. Als u deze informatie optimaal wilt benutten, maakt u Audience Manager-kenmerken die overeenkomen met de analysegegevens die door de [!UICONTROL Flash DIL] -bibliotheek worden doorgegeven.

## Flash DIL ActionScript-bibliotheek {#flash-dil-actionscript}

Code voor het [!DNL Flash] -object waarmee de analysegegevens naar Audience Manager worden verzonden.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Voor elk [!DNL Flash] -object ondersteunt de code slechts één partnerinstantie ( `d.partner` ).
>
>* Vereist Adobe [!UICONTROL AppMeasurement] [!DNL AS] library versie 3.5.2 of hoger.

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
>* [ Tanden ](../features/traits/trait-details-page.md)
>* [Signalen, eigenschappen en segmenten](../reference/signal-trait-segment.md)
>* [Sleutelwaardeparen](../reference/key-value-pairs-explained.md)
>* [Voorvoegselvereisten voor belangrijke variabelen](../features/traits/trait-variable-prefixes.md)
