---
description: Een overzicht van DIL en hoe het werkt.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Data Integration Library begrijpen (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# De [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de extensie [!DNL Data Integration Library (DIL)] en [!DNL DIL] stopgezet.
>
>Bestaande klanten kunnen hun [!DNL DIL] -implementatie blijven gebruiken. Adobe ontwikkelt [!DNL DIL] echter niet verder dan dit punt. De klanten worden aangemoedigd om [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun lange termijn strategie van de gegevensinzameling te evalueren.
>
>De klanten die nieuwe integratie van de gegevensinzameling na Juli 2023 willen uitvoeren zouden [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan moeten gebruiken.

Overzicht, aan de slag en codemethoden beschikbaar in de [!DNL Audience Manager DIL] codebibliotheek.

>[!IMPORTANT]
>
>Beginnend met versie 8.0 (vrijgegeven Augustus 2018), [!UICONTROL DIL] heeft een harde afhankelijkheid van de [ Dienst van de Identiteit van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL), versie 3.3 of hoger. De methode is gebaseerd op de [!DNL ID Service] voor het activeren van id-syncs en URL-doelen. Er treedt een fout op als [!DNL ID Service] ontbreekt, oud is of niet is geconfigureerd.
>
>We raden u aan [!DNL Adobe Experience Platform Tags] te gebruiken om uw [!DNL DIL] - en [!DNL Adobe Experience Platform Identity Service] -bibliotheken te implementeren en te beheren.

Nochtans, kunt u de recentste Experience Cloud en [!DNL DIL] versies van onze pagina ook downloaden GitHub. Zie onderstaande downloadkoppelingen:

* Download de [ Dienst van de Identiteit van Adobe Experience Platform ](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [ DIL ](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Doel van DIL {#purpose-dil}

[!UICONTROL DIL] is een API-bibliotheek. U kunt het als een lichaam van helpercode voor [!DNL Adobe Audience Manager] denken. [!DNL Audience Manager] hoeft niet te worden gebruikt, maar de methoden en functies van [!UICONTROL DIL] betekenen dat u geen eigen code hoeft te ontwikkelen om gegevens naar [!DNL Audience Manager] te verzenden. Ook, is [!UICONTROL DIL] verschillend dan API die door de [ Dienst van de Identiteit van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL) wordt verstrekt. Deze service is ontworpen om de identiteit van bezoekers in verschillende [!DNL Experience Cloud] -oplossingen te beheren. [!UICONTROL DIL] is daarentegen ontworpen om:

* Maak gebeurtenisvraag en verzend gegevens naar de [ Server van de Inzameling van Gegevens ](../reference/system-components/components-data-collection.md).
* Verzend gegevens naar [ bestemmingen ](../features/destinations/destinations.md).

## DIL-code ophalen en implementeren {#get-implement-dil-code}

[!UICONTROL DIL] code is beschikbaar voor download **[hier ](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Gelieve te merken op dat het beginnen met versie 8.0 (vrijgegeven Augustus 2018), [!UICONTROL DIL] een harde afhankelijkheid van de [ Dienst van de Identiteit van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL) heeft, versie 3.3 of hoger. De functie is afhankelijk van de syntaxis van de id in [!DNL ID Service] en [!DNL URL destinations] . Er treedt een fout op als [!DNL ID Service] ontbreekt, oud is of niet is geconfigureerd.

Eerder dan het werk met [!UICONTROL DIL] en opstelling [!DNL Audience Manager] manueel, adviseren wij dat u [ Markeringen van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=nl-NL) in plaats daarvan gebruikt. [!DNL Adobe Experience Platform Tags] is het aanbevolen implementatieprogramma omdat het de implementatie, plaatsing en versiebeheer van code vereenvoudigt. Lees meer over de [ uitbreiding van Audience Manager ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=nl-NL) in [!DNL Adobe Experience Platform Tags].

## Voorbeeld van oproep {#sample-code}

[!UICONTROL DIL] verzendt gegevens naar [!DNL Audience Manager] in een gebeurtenisaanroep. Een gebeurtenisaanroep is een XML HTTP-aanvraag van uw pagina. Er wordt een `POST` -methode gebruikt om gegevens in de hoofdtekst van de aanvraag te verzenden.

| Gebeurtenisoproepelement | Beschrijving |
|--- |--- |
| URL | DIL-gebeurtenisaanroepen gebruiken de volgende syntaxis: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Lichaam | Zoals in voorbeeld hieronder wordt getoond, geeft DIL gegevens door als sleutel-waardeparen. De speciale prefixkarakters identificeren de zeer belangrijk-waardeparen als Audience Manager of partnervariabelen.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Zie ook:
* [Voorvoegselvereisten voor belangrijkste variabelen](../features/traits/trait-variable-prefixes.md)
* [Ondersteunde kenmerken voor DCS API-aanroepen](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Verwante koppelingen

* [DIL Use cases and Code Samples](/help/using/dil/dil-use-cases.md)
* [DIL-methoden op klasseniveau](/help/using/dil/dil-class-overview/dil-start.md)
* [DIL-methoden op instantieniveau](/help/using/dil/dil-instance-methods.md)
* [DIL-modules](/help/using/dil/dil-modules.md)
* [DIL Tools](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
