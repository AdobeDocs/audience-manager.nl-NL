---
description: Algemene vragen en problemen met betrekking tot producten en functies.
keywords: audience manager cookies
seo-description: Algemene vragen en problemen met betrekking tot producten en functies.
seo-title: Veelgestelde vragen over productfuncties en -functies
solution: Audience Manager
title: Veelgestelde vragen over productfuncties en -functies
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 3%

---


# Veelgestelde vragen over productfuncties en -functies{#product-features-and-functions-faq}

Algemene vragen en problemen met betrekking tot producten en functies.

 

<!-- 

faq_features_functions.xml

 -->

**Wat is mijn organisatie-id en hoe vind ik het?**

Het *`Organization ID`* is een unieke id die uw organisatie identificeert voor [!DNL Audience Manager] en [!DNL Adobe Experience Cloud]. Het bestaat uit een hoofdlettergevoelige, alfanumerieke tekenreeks van 24 tekens, gevolgd door [!UICONTROL @AdobeOrg].

Een *`Organization ID`* ziet er bijvoorbeeld als volgt uit: `1FD6776A524453CC0A490D44@AdobeOrg`.

Het *`Organization ID`* wordt gebruikt door [DIL](../dil/dil-overview.md) API van Audience Manager, de Dienst [van de Identiteit van het](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform, en andere [!DNL Experience Cloud] oplossingen. Gebruikers met beheerdersmachtigingen kunnen de instructies *`Organization ID`* op het [!DNL Adobe Admin Console]scherm vinden. Zie [Beheer - Veelgestelde vragen](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)over Gebruikersbeheer.

 

**Kan ik eigenschappen of bestemmingen in bulk tot stand brengen?**

Ja. Zie [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>De [!UICONTROL Bulk Management Tools] gereedschappen *worden niet* ondersteund door [!DNL Audience Manager]. Ze zijn alleen beschikbaar voor gemak en als hoffelijkheid. Voor bulkwijzigingen raden we u aan met de [Audience Manager-API&#39;s](../api/api.md) te werken.

 

**Bij het exporteren van een bulk-id naar een doel ontbreken enkele klant-id&#39;s. Waarom gebeurt dat?**

Wanneer een apparaat-id ([AAM UUID](../reference/ids-in-aam.md)) is gekoppeld aan meerdere CRM-id&#39;s ([DPUUIDs](../reference/ids-in-aam.md)), wordt alleen de meest recente toewijzing geëxporteerd. Daarom ziet u mogelijk een lager dan verwacht aantal apparaat-id&#39;s dat wordt geëxporteerd.

 

**Kan de noodzaak van tags of pixels van derden[!DNL Audience Manager]verminderen en de laadtijden van pagina&#39;s verbeteren?**

Als [!DNL Audience Manager] is geïntegreerd met uw gegevenspartner van derden, kunt u hun pixels en tags vervangen door een server-naar-server-id-aanroep naar [!DNL Audience Manager]. In dit geval, zou één enkele vraag van identiteitskaart in brand steken de eerste keer wij een gebruiker zien en die informatie synchroniseren met uw derdepartner. [!DNL Audience Manager] Dit elimineert de behoefte om veelvoudige pixelvraag van elke pagina te maken. Het verminderen van pixelaanroepen kan de laadtijden van de pagina verbeteren.

 

**Ik heb me geabonneerd op een gegevensfeed. Waar worden die gegevens opgeslagen?**

Uw gegevensfeed en alle kenmerken in de feed worden weergegeven als submappen en kenmerken in [!DNL Audience Manager]. Ga naar **[!UICONTROL Audience Data > Traits]** en breid de [!UICONTROL 3rd-Party Data] map uit om uw kenmerken weer te geven of maak segmenten en modellen met deze gegevens.

 

**Wat is[!UICONTROL Tag Insertion Manager (TIM)]dat?**

Audience Manager gebruikt [!UICONTROL Tag Insertion Manager] (TIM) om [!UICONTROL data collection code (DIL)] te maken en te beheren. Deze functie is verouderd en is eerst vervangen door [!UICONTROL Dynamic Tag Manager (DTM)] en later door [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

 

**Wat zijn de verschillen tussen Algorithmic Models en Trait Recommendations? Wanneer moet ik ze allemaal gebruiken?**

**Algorithmic Models**

Met Algorithmic Models worden niet alleen de meest invloedrijke kenmerken gevonden, maar worden gebruikers ook gescores gegeven op basis van deze kenmerken en wordt aan elke gebruiker een individuele score toegewezen. Vervolgens maakt u algoritmische kenmerken om uw gebruikers als doel in te stellen. Met nauwkeurigheid en bereikcontroles in Trait Builder, kunt u specificeren welke gebruikers onder allen die de invloedrijke eigenschappen hebben u wilt richten.

Met Algorithmic Models kunt u gebruikers op verschillende nauwkeurigheidsniveaus selecteren en in Audience Lab testen welke groep gebruikers het beste converteert. Zie het gedetailleerde gebruiksgeval in [Compare Modellen in het Laboratorium](../features/audience-lab/audience-lab-use-cases.md#compare-models)van de Publiek.

In Algorithmic Models wordt het model elke acht dagen uitgevoerd en worden de gebruikers vernieuwd die zijn gekwalificeerd voor algoritmische kenmerken.

**Aanbevolen stappen**

De Aanbevelingen van het spoor is een snelle manier om inzicht in andere eigenschappen te krijgen die aan degenen gelijkaardig zijn u in een segment gebruikt.

U moet Trait Recommendations gebruiken wanneer:

* U hebt snelle inzichten nodig terwijl het bouwen van een segment;
* U gebruikt de segmenten voor korte campagnes of wanneer u publiek snel wilt onderdrukken die omzet;
* U probeert het bereik te maximaliseren.

 

**Is er enig verschil tussen Adobe Analytics en de segmenten van de Audience Manager?**

Ja, lees Segmenten [begrijpen in Analytics en Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) voor een diepgaande beschrijving van de verschillen.
