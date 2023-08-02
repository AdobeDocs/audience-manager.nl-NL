---
description: Verzamel gegevens die vanuit FLA-bestanden naar Analytics zijn verzonden en werk in de Audience Manager met die gegevens.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 2%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangemoedigd om te evalueren [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) voor hun strategie voor het verzamelen van gegevens op lange termijn.
>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) in plaats daarvan.

Verzamel gegevens die vanuit FLA-bestanden naar Analytics zijn verzonden en werk in de Audience Manager met die gegevens.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] is een [!DNL ActionScript] codebibliotheek waarmee u met videoplaybackgegevens in Audience Manager kunt werken. [!DNL Flash DIL] werkt door SWF-inhoud op te nemen in de Adobe [!UICONTROL AppMeasurement] De bibliotheek wordt doorgegeven aan Analytics. [!DNL Flash DIL] verzendt die gegevens naar de afzonderlijke [!UICONTROL DIL] JavaScript-gegevensverzamelingsmodule, die die informatie doorgeeft aan de Audience Manager. Analytische gegevens ( [!UICONTROL Props], [!UICONTROL eVars], evenementen, enz.) die zijn vastgelegd in [!DNL FLA] bestand is beschikbaar in Audience Manager als karakteristieken of ongebruikte signalen.

## Vereisten voor gegevensverzameling Flash DIL {#requirements}

Algemene eisen inzake implementatie en code.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementatievereisten**

[!UICONTROL Flash] gegevensverzameling vereist:

* De [!UICONTROL DIL] klassenbibliotheek ( `dil.swc`). Verkrijg [!UICONTROL DIL] klassenbibliotheek van uw contact van de Oplossingen van de Partner.

* JavaScript [!UICONTROL DIL] code voor gegevensverzameling op de pagina.
* [DIL ActionScript-bibliotheek](../dil/dil-flash.md#flash-dil-actionscript) geladen in het Flash-object waarvan u gegevens wilt verzamelen.
* Adobe [!DNL AppMeasurement] [!DNL AS] bibliotheek (versie 3.5.2 of hoger) geladen in de [!DNL Flash] -object waarvan u gegevens wilt verzamelen.

**AllowScriptAccess instellen op `Always` of`sameDomain`**

De `AllowScriptAccess` in de code van HTML die een dossier van de SWF laadt controleert de capaciteit om uitgaande toegang URL van binnen het dossier van de SWF uit te voeren. Wanneer u een [!UICONTROL Flash DIL] gegevensintegratie, zorg ervoor de Flash `AllowScriptAccess` parameter is ingesteld op `always` of `sameDomain`. [!UICONTROL Flash DIL] gegevensverzameling werkt niet als `AllowScriptAccess` is ingesteld op `never`. Zie [Toegang tot scripts of hostwebpagina beheren](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Plaatsing code**

Probeer de JS te plaatsen [!UICONTROL DIL] de module van de gegevensinzameling op de pagina zodat laadt het vóór [!DNL FLA] bestand. Wanneer de [!DNL FLA] bestand wordt eerst geladen, voordat [!UICONTROL DIL] de gegevensinzameling is klaar, kunt u de aanvankelijke gegevenssignalen missen die [!UICONTROL Flash DIL] verzendt naar die module. Maar als het eenmaal is geïnstantieerd, [!UICONTROL DIL] in de module voor gegevensverzameling worden alle volgende gegevens van het SWF-bestand vastgelegd die door [!UICONTROL Flash DIL].

## Gegevens verzameld door Flash DIL {#data-collected}

[!UICONTROL Flash DIL] legt paginaweergave, koppelingen bijhouden, media bijhouden en andere mediaweergavegebeurtenissen van de Adobe vast [!UICONTROL AppMeasurement] bibliotheek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Paginaweergavegebeurtenissen**

Tenzij anders bepaald door `s.trackVars`, [!UICONTROL Flash DIL] Verzamelt de volgende gegevens van Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Gebeurtenissen voor bijhouden van koppelingen**

Tenzij anders bepaald door `s.linkTrackVars`, [!UICONTROL Flash DIL] verzamelt de volgende gegevens van Adobe [!UICONTROL AppMeasurement]:

* `pe` (Type spoorverbinding geroepen)
* `pev1` (Koppeling-URL)
* `pev2`(Koppelingstekst)

**Gebeurtenissen voor het bijhouden van media**

Tenzij anders bepaald door `s.Media.trackVars`, [!UICONTROL Flash DIL] Hiermee worden alle opgesomde gegevens verzameld in de sectie Gebeurtenissen paginaweergave.

**Andere gegevenspunten**

De gegevens van deze parameters worden standaard verzameld:

* `mediaName` (Naam media/video-element)
* `mediaAdName` (Advertentienaam)
* `mediaAdParentName` (Naam van de inhoud van het primaire medium waarop de advertentie is genest)
* `mediaAdParentPod` (De pod of het ad-einde binnen de primaire inhoud waar de advertentie wordt afgespeeld)
* `mediaAdParentPodPos` (De numerieke positie binnen de pod waarin de advertentie wordt afgespeeld. Meer dan één advertentie kan in een pod worden afgespeeld.

## Flash DIL-gegevens in Audience Manager {#flash-dil-data}

De [!UICONTROL Flash DIL] van Adobe AppMeasurement gegevens in Audience Manager eigenschappen en ongebruikte signalen omzet.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analyse [!UICONTROL Props], [!UICONTROL eVars]en gebeurtenissen werken als eigenschappen in de Audience Manager. De sporen zijn zeer belangrijk-waardeparen en worden gebruikt om segmenten te bouwen. Bijvoorbeeld in een analysehulpmiddel als `c30=foo`, `c30` is de sleutel (een constante) en `foo` is de waarde (een variabele).

**Audience Manager-eigenschappen afstemmen op analytische variabelen**

De analysegegevens gebruiken die door [!UICONTROL Flash DIL], zou u Audience Manager eigenschappen moeten tot stand brengen die de belangrijkste waarde met vooraf bepalen hebben `c_`.

Zie de tabel voor voorbeelden:

| Gegevenselement Analytics | Voorbeeld van analyse | Als Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **vervagen** | `v35=bar` | `c_evar35=bar` |
| **gebeurtenissen** | `events=event10` | `c_events=event10` |

**DIL-/analysegegevens als ongebruikte signalen**

Audience Manager accepteert Analytics [!UICONTROL Props], [!UICONTROL eVars]en gebeurtenissen, zelfs zonder bijbehorend kenmerk. In dit geval zijn de gegevens niet beschikbaar voor het maken van de eigenschap en worden deze weergegeven in het dialoogvenster [Rapport Ongebruikte signalen](../reporting/dynamic-reports/unused-signals.md) in plaats daarvan. Als u deze informatie optimaal wilt benutten, maakt u Audience Manager-eigenschappen die overeenkomen met de analysegegevens die door de [!UICONTROL Flash DIL] bibliotheek.

## Flash DIL ActionScript-bibliotheek {#flash-dil-actionscript}

Code voor uw [!DNL Flash] -object om analysegegevens naar de Audience Manager te verzenden.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Voor elke [!DNL Flash] object, ondersteunt de code één partnerinstantie ( `d.partner`alleen ).
>
>* Vereist de Adobe [!UICONTROL AppMeasurement] [!DNL AS] bibliotheekversie 3.5.2 of hoger.

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
