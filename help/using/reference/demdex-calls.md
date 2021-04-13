---
description: De Audience Manager en de Dienst van de Identiteit van Adobe Experience Platform maken vraag aan en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk extern domein, maar dat is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-description: De Audience Manager en de Dienst van de Identiteit van Adobe Experience Platform maken vraag aan en ontvangen gegevens van het domein demdex.net. Dit lijkt misschien alsof Adobe werkt met een ongebruikelijk extern domein, maar dat is niet het geval. Deze sectie beschrijft de elementen in een vraag demdex.net.
seo-title: Inzicht in calls naar het Demdex-domein
solution: Audience Manager
title: Inzicht in calls naar het Demdex-domein
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: 'Referenties '
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 15%

---

# Het begrip Vraag van [!DNL Demdex] Domein {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] en de  [!DNL Adobe Experience Platform Identity Service] maak vraag aan en ontvangt gegevens van het  `demdex.net` domein. Dit lijkt misschien alsof [!DNL Adobe] met een ongebruikelijk derdedomein werkt, maar dit is niet het geval. Deze sectie beschrijft de elementen in een `demdex.net` vraag.

| Elementen aanroepen | Beschrijving |
|---|---|
| `demdex.net` | Dit is een verouderd domein dat wordt beheerd door [!DNL Adobe]. Het weerspiegelt de originele, pre-aanschafnaam van [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] nam [!DNL Demdex] over in 2011 en wijzigde het merk van het bedrijf in [!DNL Audience Manager]. Het is moeilijk om dit domein te veranderen omdat het diep met [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service], en onze geïnstalleerde gebruikersbasis wordt verweven. U kunt andere voorvoegsels zien verbonden aan erfenis `demdex.net` vraag (b.v., `dcs.demdex.net`, `fast.demdex.net`, enz.). Ongeacht het voorvoegsel, is een vraag aan `something.demdex.net` altijd een vraag aan [!DNL Adobe] en niet aan één of ander onbekend of verdacht derdedomein. |
| `dpm` | [!DNL DPM] is een afkorting voor  [!DNL Data Provider Match]. Het vertelt interne, [!DNL Adobe] systemen dat een vraag van [!DNL Audience Manager] of [!DNL Adobe Experience Cloud ID Service] klantgegevens voor synchronisatie of het vragen van een identiteitskaart overgaat. Dit is de gemeenschappelijkste `demdex.net` vraag u van [!DNL Audience Manager] of [!DNL Adobe Experience Cloud ID Service] zult zien. <br><br>[!DNL DPM] basisbeginselen van oproepen: <ul><li>[!DNL Audience Manager]: Een  [!DNL DPM] vraag van  [!DNL Audience Manager] verzendt gegevens naar  [!DNL Data Collection Servers] en  [!DNL Profile Cache Servers]. Zie [Onderdelen voor dataverzameling](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Een  [!DNL DPM] oproep van de gebruiker  [!DNL Adobe Experience Cloud ID Service] is een aanvraag voor een bezoekersidentiteitskaart Zie [Cookies en de Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/nl-NL/id-service/using/intro/cookies.html) en [Hoe de Adobe Experience Platform Identity Service id&#39;s aanvraagt en instelt](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Opmerking:  [!DNL Adobe Experience Cloud ID Service] klanten kunnen het  [!DNL DPM] voorvoegsel in de domeinnaam wijzigen. Zie [publiekManager Server en publiekManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Audience Manager Cookies](https://docs.adobe.com/content/help/nl-NL/core-services/interface/ec-cookies/cookies-am.html)

