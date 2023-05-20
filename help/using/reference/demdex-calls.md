---
description: De Audience Manager en de Dienst van de Identiteit van Adobe Experience Platform maken vraag aan en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk extern domein, maar dat is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Inzicht in calls naar het Demdex-domein
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 7%

---

# Het begrip roept aan [!DNL Demdex] Domein {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] en de [!DNL Adobe Experience Platform Identity Service] Maak vraag aan en ontvang gegevens van `demdex.net` domein. Dit kan lijken [!DNL Adobe] werkt met een ongebruikelijk extern domein, maar dat is niet het geval. In deze sectie worden de elementen in een `demdex.net` vraag.

| Elementen aanroepen | Beschrijving |
|---|---|
| `demdex.net` | Dit is een verouderd domein dat wordt beheerd door [!DNL Adobe]. De oorspronkelijke naam van vóór de overname [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] nam [!DNL Demdex] over in 2011 en wijzigde het merk van het bedrijf in [!DNL Audience Manager]. Het is moeilijk om dit domein te veranderen omdat het diep met wordt verweven [!DNL Audience Manager]de [!DNL Adobe Experience Cloud ID Service]en onze geïnstalleerde gebruikersbasis. Mogelijk ziet u andere voorvoegsels die zijn gekoppeld aan verouderde `demdex.net` oproepen (bv. `dcs.demdex.net`, `fast.demdex.net`, enz.). Ongeacht het voorvoegsel, roept een vraag aan `something.demdex.net` is altijd een vraag aan [!DNL Adobe] en niet op een onbekend of verdacht derdedomein. |
| `dpm` | [!DNL DPM] is een afkorting van [!DNL Data Provider Match]. Het vertelt intern, [!DNL Adobe] systemen die een oproep van [!DNL Audience Manager] of de [!DNL Adobe Experience Cloud ID Service] geeft klantgegevens door voor synchronisatie of vraagt een id aan. Dit is de meest voorkomende `demdex.net` bel u van zult zien [!DNL Audience Manager] of de [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] basisbeginselen van oproepen: <ul><li>[!DNL Audience Manager]: A [!DNL DPM] oproep van [!DNL Audience Manager] gegevens naar de [!DNL Data Collection Servers] en [!DNL Profile Cache Servers]. Zie [Onderdelen voor dataverzameling](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: A [!DNL DPM] oproep van de [!DNL Adobe Experience Cloud ID Service] is een aanvraag voor een bezoekersidentiteitskaart Zie [Cookies en de Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) en [Hoe de Adobe Experience Platform Identity Service id&#39;s aanvraagt en instelt](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>Opmerking: [!DNL Adobe Experience Cloud ID Service] klanten kunnen de [!DNL DPM] in de domeinnaam. Zie [publiekManager Server en publiekManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)

