---
description: De Audience Manager en de Dienst van de Identiteit van het Adobe Experience Platform maken vraag aan en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk domein van derden, maar dit is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-description: De Audience Manager en de Dienst van de Identiteit van het Adobe Experience Platform maken vraag aan en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk domein van derden, maar dit is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-title: Inzicht krijgen in oproepen van het demdex-domein
solution: Audience Manager
title: Inzicht krijgen in oproepen van het demdex-domein
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---


# Het begrip Vraag aan het [!DNL Demdex] Domein {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] en het [!DNL Adobe Experience Platform Identity Service] maken vraag aan en ontvangen gegevens van het `demdex.net` domein. Dit lijkt misschien wel [!DNL Adobe] te werken met een ongebruikelijk extern domein, maar dat is niet het geval. Deze sectie beschrijft de elementen in een `demdex.net` vraag.

| Elementen aanroepen | Beschrijving |
|---|---|
| `demdex.net` | Dit is een bestaand domein dat wordt beheerd door [!DNL Adobe]. Het geeft de oorspronkelijke naam van [!DNL Audience Manager] ([!DNL Demdex]) vóór de verwerving weer. [!DNL Adobe] overgenomen [!DNL Demdex] in 2011 en hermerkten de onderneming als [!DNL Audience Manager]. Het is moeilijk om dit domein te veranderen omdat het diep met [!DNL Audience Manager], de [!DNL Adobe Experience Cloud ID Service], en onze geïnstalleerde gebruikersbasis wordt verweven. U kunt andere prefixen zien verbonden aan erfenisvraag (b.v., `demdex.net` , `dcs.demdex.net``fast.demdex.net`, enz.). Ongeacht het voorvoegsel, is een vraag aan altijd een vraag aan `something.demdex.net` [!DNL Adobe] en niet aan één of ander onbekend of verdacht derdedomein. |
| `dpm` | [!DNL DPM] is een afkorting voor [!DNL Data Provider Match]. Het vertelt intern, [!DNL Adobe] systemen dat een vraag van [!DNL Audience Manager] of de [!DNL Adobe Experience Cloud ID Service] klantengegevens voor synchronisatie of het vragen van een identiteitskaart overgaat. Dit is de gemeenschappelijkste `demdex.net` vraag u van [!DNL Audience Manager] of de [!DNL Adobe Experience Cloud ID Service]zult zien. <br><br>[!DNL DPM] basisbeginselen van oproepen: <ul><li>[!DNL Audience Manager]: Een [!DNL DPM] vraag van [!DNL Audience Manager] verzendt gegevens naar [!DNL Data Collection Servers] en [!DNL Profile Cache Servers]. Zie [Componenten](../reference/system-components/components-data-collection.md)voor gegevensverzameling.</li><li>[!DNL Adobe Experience Cloud ID Service]: Een [!DNL DPM] vraag van [!DNL Adobe Experience Cloud ID Service] is een verzoek om bezoekersidentiteitskaart Zie [Cookies en de Dienst](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) van de Identiteit van het Adobe Experience Platform en [hoe de Verzoeken en plaatst van de Dienst van de Identiteit van het Adobe Experience Platform IDs](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html.</li></ul><br>Opmerking: [!DNL Adobe Experience Cloud ID Service] klanten kunnen het [!DNL DPM] voorvoegsel in de domeinnaam wijzigen. Zie [publiekManager Server en publiekManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Audience Manager Cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

