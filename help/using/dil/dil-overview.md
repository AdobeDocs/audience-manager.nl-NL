---
description: Een overzicht van DIL en hoe het werkt.
seo-description: Een overzicht van DIL en hoe het werkt.
seo-title: Inzicht in de Data Integration Library (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Inzicht in de Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 18%

---


# Het begrip [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Overzicht, begonnen worden, en codemethodes beschikbaar in [!DNL Audience Manager DIL] codebibliotheek.

>[!IMPORTANT]
>
>Vanaf versie 8.0 (uitgebracht in augustus 2018) is [!UICONTROL DIL] sterk afhankelijk van [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/nl-NL/id-service/using/home.html), versie 3.3 of hoger. Het steunt op [!DNL ID Service] om de syncs van identiteitskaart en bestemmingen URL in brand te steken. Er treedt een fout op als [!DNL ID Service] ontbreekt, oud is of niet is geconfigureerd.
>
>We raden u aan [!DNL Adobe Experience Platform Launch] te gebruiken om uw [!DNL DIL]- en [!DNL Adobe Experience Platform Identity Service]-bibliotheken te implementeren en te beheren.

Nochtans, kunt u de recentste Experience Cloud en [!DNL DIL] versies van onze pagina ook downloaden GitHub. Zie onderstaande downloadkoppelingen:

* Download de [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases) downloaden

## Doel van DIL {#purpose-dil}

[!UICONTROL DIL] is een API-bibliotheek. U kunt het als lichaam van helpercode voor [!DNL Adobe Audience Manager] denken. [!DNL Audience Manager] hoeft niet te worden gebruikt, maar de methoden en functies [!UICONTROL DIL] bieden aan dat u uw eigen code niet hoeft te ontwikkelen om gegevens naar [!DNL Audience Manager] te verzenden. [!UICONTROL DIL] is ook anders dan de API die wordt geleverd door [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html). Deze service is ontworpen om de identiteit van bezoekers in verschillende [!DNL Experience Cloud]-oplossingen te beheren. [!UICONTROL DIL] is daarentegen ontworpen om:

* Maak gebeurtenisvraag en verzend gegevens naar [de Server van de Inzameling van Gegevens](../reference/system-components/components-data-collection.md).
* Gegevens verzenden naar [bestemmingen](../features/destinations/destinations.md).

## DIL-code {#get-implement-dil-code} ophalen en implementeren

[!UICONTROL DIL] code kan  **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** worden gedownload. Houd er rekening mee dat [!UICONTROL DIL] vanaf versie 8.0 (uitgebracht in augustus 2018) sterk afhankelijk is van [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), versie 3.3 of hoger. Het steunt op [!DNL ID Service] aan brand ID syncs en [!DNL URL destinations]. Er treedt een fout op als [!DNL ID Service] ontbreekt, oud is of niet is geconfigureerd.

In plaats van met [!UICONTROL DIL] te werken en [!DNL Audience Manager] manueel op te zetten, adviseren wij dat u [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) in plaats daarvan gebruikt. [!DNL Adobe Experience Platform Launch] is het geadviseerde implementatiehulpmiddel omdat het codeplaatsing, plaatsing, en versiebeheer vereenvoudigt. Lees meer over [Audience Manager uitbreiding](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in [!DNL Adobe Experience Platform Launch].

[!DNL Adobe Experience Platform Launch] is de opvolger van  [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Voorbeeld van aanroep {#sample-code}

[!UICONTROL DIL] verzendt gegevens naar  [!DNL Audience Manager] in een gebeurtenisvraag. Een gebeurtenisaanroep is een XML HTTP-aanvraag van uw pagina. Het gebruikt een `POST` methode om gegevens in het lichaam van het verzoek te verzenden.

| Gebeurtenisoproepelement | Beschrijving |
|--- |--- |
| URL | Voor aanroepen van DIL-gebeurtenissen wordt de volgende syntaxis gebruikt: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Lichaam | Zoals in voorbeeld hieronder wordt getoond, geeft DIL gegevens door als sleutel-waardeparen. De speciale prefixkarakters identificeren de zeer belangrijk-waardeparen als Audience Manager of partnervariabelen.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Zie ook:
* [Voorvoegselvereisten voor belangrijke variabelen](../features/traits/trait-variable-prefixes.md)
* [Ondersteunde attributen voor DCS-API-calls](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Verwante koppelingen

* [DIL-gebruiksscenario’s en codevoorbeelden](/help/using/dil/dil-use-cases.md)
* [DIL-methoden op klasseniveau ](/help/using/dil/dil-class-overview/dil-start.md)
* [DIL-methoden op instantieniveau](/help/using/dil/dil-instance-methods.md)
* [DIL-modules](/help/using/dil/dil-modules.md)
* [DIL-tools](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)