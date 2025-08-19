---
description: Audience Manager en de Adobe Experience Platform Identity Service maken aanroepen naar en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk extern domein, maar dat is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Inzicht krijgen in oproepen van het demdex-domein
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 4%

---

# Werken met aanroepen naar het [!DNL Demdex] -domein {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] en [!DNL Adobe Experience Platform Identity Service] maken aanroepen naar en ontvangen gegevens van het `demdex.net` -domein. Dit lijkt er misschien op dat [!DNL Adobe] werkt met een ongebruikelijk domein van derden, maar dit is niet het geval. In deze sectie worden de elementen in een `demdex.net` -aanroep beschreven.

| Elementen aanroepen | Beschrijving |
|---|---|
| `demdex.net` | Dit is een verouderd domein dat wordt beheerd door [!DNL Adobe] . De naam weerspiegelt de oorspronkelijke naam van [!DNL Audience Manager] ([!DNL Demdex]) vóór de overname. [!DNL Adobe] nam [!DNL Demdex] over in 2011 en wijzigde het merk van het bedrijf in [!DNL Audience Manager]. Het is moeilijk om dit domein te wijzigen omdat het diep is verweven met [!DNL Audience Manager], de [!DNL Adobe Experience Cloud ID Service] en onze geïnstalleerde gebruikersbasis. Andere voorvoegsels worden mogelijk gekoppeld aan oudere `demdex.net` -aanroepen (bijvoorbeeld `dcs.demdex.net` , `fast.demdex.net` , enzovoort). Een aanroep van `something.demdex.net` is altijd een aanroep van [!DNL Adobe] , ongeacht het voorvoegsel, en niet van een onbekend of verdacht domein van een derde. |
| `dpm` | [!DNL DPM] is een afkorting voor [!DNL Data Provider Match] . Dit vertelt interne [!DNL Adobe] systemen dat een aanroep van [!DNL Audience Manager] of [!DNL Adobe Experience Cloud ID Service] klantgegevens doorgeeft voor synchronisatie of een id aanvraagt. Dit is de meest voorkomende `demdex.net` oproep die u kunt zien vanuit [!DNL Audience Manager] of [!DNL Adobe Experience Cloud ID Service] . <br><br>[!DNL DPM] basisbeginselen van oproepen: <ul><li>[!DNL Audience Manager]: Een [!DNL DPM] aanroep van [!DNL Audience Manager] verzendt gegevens naar de [!DNL Data Collection Servers] en [!DNL Profile Cache Servers] . Zie [Onderdelen voor dataverzameling](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Een [!DNL DPM] aanroep van de [!DNL Adobe Experience Cloud ID Service] is een aanvraag voor een bezoeker-id. Zie [ Cookies en de Dienst van de Identiteit van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=nl-NL) en [ hoe de Verzoeken van de Dienst van de Identiteit van Adobe Experience Platform en plaatst IDs ](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html?lang=nl-NL).</li></ul><br> Opmerking: [!DNL Adobe Experience Cloud ID Service] klanten kunnen het voorvoegsel [!DNL DPM] wijzigen in de domeinnaam. Zie {de Server van 0} publiekManager en publiekManagerServerSecure [.](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html?lang=nl-NL) |

>[!MORELIKETHIS]
>
>* [ de Dienst van de Identiteit van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL)
>* [ de Koekjes van Audience Manager ](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=nl-NL)
