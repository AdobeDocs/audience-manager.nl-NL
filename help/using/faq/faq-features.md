---
description: Algemene vragen en problemen met betrekking tot producten en functies.
keywords: audience manager cookies
seo-description: Algemene vragen en problemen met betrekking tot producten en functies.
seo-title: Veelgestelde vragen over productfuncties en -functies
solution: Audience Manager
title: Veelgestelde vragen over productfuncties en -functies
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Veelgestelde vragen over productfuncties en -functies{#product-features-and-functions-faq}

Algemene vragen en problemen met betrekking tot producten en functies.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Wat is mijn organisatie-id en hoe vind ik het?**

Het *`Organization ID`* is een unieke id die uw organisatie identificeert voor [!DNL Audience Manager] en [!DNL Adobe Experience Cloud]. Het bestaat uit een hoofdlettergevoelige, alfanumerieke tekenreeks van 24 tekens, gevolgd door [!UICONTROL @AdobeOrg].

Een *`Organization ID`* ziet er bijvoorbeeld als volgt uit: `1FD6776A524453CC0A490D44@AdobeOrg`.

Deze *`Organization ID`* wordt gebruikt door de [DIL](../dil/dil-overview.md) -API van Audience Manager, de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)en andere [!DNL Experience Cloud] oplossingen. Gebruikers met beheerdersmachtigingen kunnen de instructies *`Organization ID`* op het [!DNL Adobe Admin Console]scherm vinden. Zie [Beheer - Veelgestelde vragen](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)over Gebruikersbeheer.

<br> 

**Kan ik eigenschappen of bestemmingen in bulk tot stand brengen?**

Ja. Zie [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>De [!UICONTROL Bulk Management Tools] gereedschappen *worden niet* ondersteund door [!DNL Audience Manager]. Ze zijn alleen beschikbaar voor gemak en als hoffelijkheid. Voor grote wijzigingen raden we u aan om in plaats daarvan met de API&#39;s van [Audience Manager](../api/api.md) te werken.

<br> 

**Kan de noodzaak van tags of pixels van derden[!DNL Audience Manager]verminderen en de laadtijden van pagina&#39;s verbeteren?**

Als [!DNL Audience Manager] is geïntegreerd met uw gegevenspartner van derden, kunt u hun pixels en tags vervangen door een server-naar-server-id-aanroep naar [!DNL Audience Manager]. In dit geval, zou één enkele vraag van identiteitskaart in brand steken de eerste keer wij een gebruiker zien en die informatie synchroniseren met uw derdepartner. [!DNL Audience Manager] Dit elimineert de behoefte om veelvoudige pixelvraag van elke pagina te maken. Het verminderen van pixelaanroepen kan de laadtijden van de pagina verbeteren.

<br> 

**Ik heb me geabonneerd op een gegevensfeed. Waar worden die gegevens opgeslagen?**

Uw gegevensfeed en alle kenmerken in de feed worden weergegeven als submappen en kenmerken in [!DNL Audience Manager]. Ga naar **[!UICONTROL Audience Data > Traits]** en breid de [!UICONTROL 3rd-Party Data] map uit om uw kenmerken weer te geven of maak segmenten en modellen met deze gegevens.

<br> 

**Wat is[!UICONTROL Tag Insertion Manager (TIM)]dat?**

Audience Manager gebruikt [!UICONTROL Tag Insertion Manager] (TIM) om [!UICONTROL data collection code (DIL)] te maken en te beheren. Deze functie is verouderd en is eerst vervangen door [!UICONTROL Dynamic Tag Manager (DTM)] en later door [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

<br> 

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

<br> 

**Is er een verschil tussen de segmenten Adobe Analytics en Audience Manager?**

Ja, lees Segmenten [begrijpen in Analytics en Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) voor een diepgaande beschrijving van de verschillen.
