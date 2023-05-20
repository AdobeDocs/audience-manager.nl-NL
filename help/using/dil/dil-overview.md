---
description: Een overzicht van DIL en hoe het werkt.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil. l,
solution: Audience Manager
title: Inzicht in de Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 11%

---

# De [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Overzicht, aan de slag gaan en codemethoden beschikbaar in het dialoogvenster [!DNL Audience Manager DIL] codebibliotheek.

>[!IMPORTANT]
>
>Vanaf versie 8.0 (uitgebracht in augustus 2018), [!UICONTROL DIL] is sterk afhankelijk van de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), versie 3.3 of hoger. Het steunt op [!DNL ID Service] om ID syncs en bestemmingen in brand te steken URL. Er treedt een fout op als de [!DNL ID Service] ontbreekt, oud of niet geconfigureerd.
>
>We raden u aan [!DNL Adobe Experience Platform Tags] om uw [!DNL DIL] en [!DNL Adobe Experience Platform Identity Service] bibliotheken.

U kunt echter ook de nieuwste Experience Cloud en [!DNL DIL] versies van onze pagina GitHub. Zie onderstaande downloadkoppelingen:

* Download de [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Downloaden [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Doel van DIL {#purpose-dil}

[!UICONTROL DIL] is een API-bibliotheek. Je kunt het zien als een helpercode voor [!DNL Adobe Audience Manager]. Het is niet verplicht [!DNL Audience Manager], maar de methoden en functies [!UICONTROL DIL] verstrekt middelen u niet uw eigen code moet ontwikkelen om gegevens te verzenden naar [!DNL Audience Manager]. Ook, [!UICONTROL DIL] is anders dan de API die door de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). Deze service is ontworpen om de identiteit van bezoekers te beheren voor verschillende [!DNL Experience Cloud] oplossingen. Daarentegen [!UICONTROL DIL] is ontworpen om:

* Gebeurtenisaanroepen maken en gegevens verzenden naar de [Gegevensverzamelingsserver](../reference/system-components/components-data-collection.md).
* Gegevens verzenden naar [bestemmingen](../features/destinations/destinations.md).

## DIL-code ophalen en implementeren {#get-implement-dil-code}

[!UICONTROL DIL] code is beschikbaar voor downloaden **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Let op: vanaf versie 8.0 (uitgebracht in augustus 2018), [!UICONTROL DIL] is sterk afhankelijk van de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), versie 3.3 of hoger. Het steunt op [!DNL ID Service] om ID syncs te branden en [!DNL URL destinations]. Er treedt een fout op als de [!DNL ID Service] ontbreekt, oud of niet geconfigureerd.

In plaats van met te werken [!UICONTROL DIL] en instellen [!DNL Audience Manager] Wij raden u aan [Adobe Experience Platform-tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) in plaats daarvan. [!DNL Adobe Experience Platform Tags] is het geadviseerde implementatiehulpmiddel omdat het codeplaatsing, plaatsing, en versiebeheer vereenvoudigt. Meer informatie over de [Audience Manager, extensie](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## Voorbeeld van oproep {#sample-code}

[!UICONTROL DIL] gegevens verzenden naar [!DNL Audience Manager] in een gebeurtenisaanroep. Een gebeurtenisaanroep is een XML HTTP-aanvraag van uw pagina. Er wordt een `POST` methode voor het verzenden van gegevens in de hoofdtekst van het verzoek.

| Gebeurtenisoproepelement | Beschrijving |
|--- |--- |
| URL | Voor aanroepen van DIL-gebeurtenissen wordt de volgende syntaxis gebruikt: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Lichaam | Zoals in voorbeeld hieronder wordt getoond, geeft DIL gegevens door als sleutel-waardeparen. Speciale voorvoegseltekens identificeren de sleutel-waardeparen als Audience Manager- of partnervariabelen.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
