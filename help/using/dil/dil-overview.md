---
description: Een overzicht van DIL en hoe het werkt.
seo-description: Een overzicht van DIL en hoe het werkt.
seo-title: De Data Integration Library (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: De Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---


# De [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Overzicht, aan de slag gaan en codemethoden beschikbaar in de [!DNL Audience Manager DIL] codebibliotheek.

>[!IMPORTANT]
>
>Vanaf versie 8.0 (uitgebracht in augustus 2018) [!UICONTROL DIL] is er een sterke afhankelijkheid van de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), versie 3.3 of hoger. Het is afhankelijk van de syntaxis van de [!DNL ID Service] te branden identiteitskaart en de bestemmingen URL. Er treedt een fout op als de code ontbreekt, oud [!DNL ID Service] is of niet is geconfigureerd.
>
>We raden u aan uw [!DNL Adobe Experience Platform Launch] bibliotheken [!DNL DIL] en [!DNL Adobe Experience Platform Identity Service] bibliotheken te implementeren en te beheren.

Nochtans, kunt u recentste Experience Cloud en [!DNL DIL] versies van onze pagina ook downloaden GitHub. Zie onderstaande downloadkoppelingen:

* Download de [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* DIL [downloaden](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Doel van DIL {#purpose-dil}

[!UICONTROL DIL] is een API-bibliotheek. Je kan het zien als een helpercode voor [!DNL Adobe Audience Manager]. Het is niet vereist om te gebruiken [!DNL Audience Manager], maar de methodes en de functies [!UICONTROL DIL] verstrekken middelen u niet uw eigen code moet ontwikkelen om gegevens naar [!DNL Audience Manager]te verzenden. Bovendien [!UICONTROL DIL] is deze API anders dan de API die wordt geleverd door de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html). Deze service is ontworpen om de identiteit van bezoekers op verschillende [!DNL Experience Cloud] oplossingen te beheren. Het is daarentegen [!UICONTROL DIL] ontworpen om:

* Maak gebeurtenisvraag en verzend gegevens naar de Server [van de](../reference/system-components/components-data-collection.md)Inzameling van Gegevens.
* Gegevens verzenden naar [doelen](../features/destinations/destinations.md).

## DIL-code ophalen en implementeren {#get-implement-dil-code}

[!UICONTROL DIL] code kan **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**worden gedownload. Houd er rekening mee dat vanaf versie 8.0 (uitgebracht in augustus 2018)[!UICONTROL DIL]een sterke afhankelijkheid bestaat van de[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), versie 3.3 of hoger. Het is afhankelijk van de syncs[!DNL ID Service]to fire ID en[!DNL URL destinations]. Er treedt een fout op als de code ontbreekt, oud[!DNL ID Service]is of niet is geconfigureerd.

In plaats van handmatig te werken met [!UICONTROL DIL] en in te stellen, raden we u aan [!DNL Audience Manager] Adobe Experience Platform starten [](https://docs.adobelaunch.com/) te gebruiken. [!DNL Adobe Experience Platform Launch] is het geadviseerde implementatiehulpmiddel omdat het codeplaatsing, plaatsing, en versiebeheer vereenvoudigt. Lees meer over de extensie [van de](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Audience Manager in [!DNL Adobe Experience Platform Launch].

[!DNL Adobe Experience Platform Launch] is de opvolger van [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Voorbeeld van oproep {#sample-code}

[!UICONTROL DIL] verzendt gegevens naar [!DNL Audience Manager] in een gebeurtenisvraag. Een gebeurtenisaanroep is een XML HTTP-aanvraag van uw pagina. Het gebruikt een `POST` methode om gegevens in het lichaam van het verzoek te verzenden.

| Gebeurtenisoproepelement | Beschrijving |
|--- |--- |
| URL | Voor DIL-gebeurtenisaanroepen wordt de volgende syntaxis gebruikt: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Lichaam | Zoals in voorbeeld hieronder wordt getoond, geeft DIL gegevens door als sleutel-waardeparen. Speciale voorvoegseltekens identificeren de sleutel-waardeparen als Audience Manager- of partnervariabelen.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Zie ook:
* [Voorvoegselvereisten voor belangrijkste variabelen](../features/traits/trait-variable-prefixes.md)
* [Ondersteunde kenmerken voor DCS API-aanroepen](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Verwante koppelingen

* [DIL-gebruik van tassen en codevoorbeelden](/help/using/dil/dil-use-cases.md)
* [DIL-methoden op klasseniveau](/help/using/dil/dil-class-overview/dil-start.md)
* [Instantie-niveau DIL-methoden](/help/using/dil/dil-instance-methods.md)
* [DIL-modules](/help/using/dil/dil-modules.md)
* [DIL-gereedschappen](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)