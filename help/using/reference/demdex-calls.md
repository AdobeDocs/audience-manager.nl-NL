---
description: De Audience Manager en de Dienst van de Identiteit van het Adobe Experience Platform maken vraag aan en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk domein van derden, maar dit is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-description: De Audience Manager en de Dienst van de Identiteit van het Adobe Experience Platform maken vraag aan en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk domein van derden, maar dit is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-title: Inzicht in calls naar het Demdex-domein
solution: Audience Manager
title: Inzicht in calls naar het Demdex-domein
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 14%

---


# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] en het [!DNL Adobe Experience Platform Identity Service] maken vraag aan en ontvangen gegevens van het `demdex.net` domein. Dit lijkt misschien wel [!DNL Adobe] te werken met een ongebruikelijk extern domein, maar dat is niet het geval. Deze sectie beschrijft de elementen in een `demdex.net` vraag.

| Elementen aanroepen | Beschrijving |
|---|---|
| `demdex.net` | This is a legacy domain controlled by [!DNL Adobe]. Het geeft de oorspronkelijke naam van [!DNL Audience Manager] ([!DNL Demdex]) vóór de verwerving weer. [!DNL Adobe] nam [!DNL Demdex] over in 2011 en wijzigde het merk van het bedrijf in [!DNL Audience Manager]. Het is moeilijk om dit domein te veranderen omdat het diep met [!DNL Audience Manager], de [!DNL Adobe Experience Cloud ID Service], en onze geïnstalleerde gebruikersbasis wordt verweven. U kunt andere prefixen zien verbonden aan erfenisvraag (b.v., `demdex.net` , `dcs.demdex.net``fast.demdex.net`, enz.). Ongeacht het voorvoegsel, is een vraag aan altijd een vraag aan `something.demdex.net` [!DNL Adobe] en niet aan één of ander onbekend of verdacht derdedomein. |
| `dpm` | [!DNL DPM] is een afkorting voor [!DNL Data Provider Match]. It tells internal, [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the [!DNL Adobe Experience Cloud ID Service] is passing in customer data for synchronization or requesting an ID. Dit is de gemeenschappelijkste `demdex.net` vraag u van [!DNL Audience Manager] of de [!DNL Adobe Experience Cloud ID Service]zult zien. <br><br>[!DNL DPM] basisbeginselen van oproepen: <ul><li>[!DNL Audience Manager]: Een [!DNL DPM] vraag van [!DNL Audience Manager] verzendt gegevens naar [!DNL Data Collection Servers] en [!DNL Profile Cache Servers]. Zie [Onderdelen voor dataverzameling](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Een [!DNL DPM] vraag van [!DNL Adobe Experience Cloud ID Service] is een verzoek om bezoekersidentiteitskaart Zie [Cookies en de Dienst](https://docs.adobe.com/content/help/nl-NL/id-service/using/intro/cookies.html) van de Identiteit van het Adobe Experience Platform en [hoe de Verzoeken en plaatst van de Dienst van de Identiteit van het Adobe Experience Platform IDs](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html.</li></ul><br>Opmerking: [!DNL Adobe Experience Cloud ID Service] klanten kunnen het [!DNL DPM] voorvoegsel in de domeinnaam wijzigen. Zie [publiekManager Server en publiekManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/nl-NL/id-service/using/home.html)
>* [Audience Manager Cookies](https://docs.adobe.com/content/help/nl-NL/core-services/interface/ec-cookies/cookies-am.html)

