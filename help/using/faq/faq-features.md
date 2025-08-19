---
description: Algemene vragen en problemen in verband met producten en functies.
keywords: cookies van publieksmanager
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: Veelgestelde vragen over productkenmerken en -functies
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 87%

---

# Veelgestelde vragen over productkenmerken en -functies{#product-features-and-functions-faq}

Algemene vragen en problemen in verband met producten en functies.

 

<!-- 

faq_features_functions.xml

 -->

**Wat is mijn organisatie-id en hoe kan ik die vinden?**

De *`Organization ID`* is een unieke id die uw organisatie identificeert in [!DNL Audience Manager] en [!DNL Adobe Experience Cloud]. De id bestaat uit een hoofdlettergevoelige, alfanumerieke reeks van 24 tekens, gevolgd door [!UICONTROL @AdobeOrg].

Een *`Organization ID`* kan er bijvoorbeeld zo uitzien: `1FD6776A524453CC0A490D44@AdobeOrg`.

De *`Organization ID`* wordt gebruikt door de [DIL](../dil/dil-overview.md)-API van Audience Manager, de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL) en andere [!DNL Experience Cloud] oplossingen. Gebruikers met beheerdertoestemmingen kunnen de *`Organization ID`* op de [!DNL Adobe Admin Console] vinden. Zie [Veelgestelde vragen over Beheer - User Management](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=nl-NL).

 

**Kan ik eigenschappen of bestemmingen in bulk maken?**

Ja. Zie [Bulkbeheertools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>De [!UICONTROL Bulk Management Tools] *worden niet* ondersteund door [!DNL Audience Manager]. Ze zijn beschikbaar voor uw gemak. Voor bulkwijzigingen raden we u aan om in plaats daarvan te werken met de [Audience Manager-API’s](../api/api.md).

 

**wanneer het uitvoeren van een bulkidentiteitskaart- uitvoer naar een bestemming, ontbreken sommige klant IDs. Waarom gebeurt dat?**

Wanneer een apparatenidentiteitskaart ([ AAM UUID ](../reference/ids-in-aam.md)) met veelvoudige CRM IDs ([ DPUUIDs ](../reference/ids-in-aam.md)) wordt verbonden, slechts wordt de recentste afbeelding uitgevoerd. Daarom ziet u mogelijk een lager dan verwacht aantal apparaat-id&#39;s dat wordt geëxporteerd.

 

**Kan [!DNL Audience Manager] de noodzaak voor tags of pixels van derden verminderen en de laadtijden van pagina’s verminderen?**

Als [!DNL Audience Manager] is geïntegreerd met uw externe datapartner, kunt u hun pixels en tags vervangen door een server-naar-server-id-call naar [!DNL Audience Manager]. In dit geval zou [!DNL Audience Manager] één id-call sturen wanneer we een gebruiker voor de eerste keer zien, en die informatie synchroniseren met uw externe partner. Dit elimineert de noodzaak om vanaf elke pagina een call met meerdere pixels te maken. Het verminderen van pixelcalls kan de laadtijden van de pagina verbeteren.

 

**Ik ben lid geworden van een datafeed. Waar worden die data opgeslagen?**

Uw datafeed en alle eigenschappen in de feed worden weergegeven als submappen en eigenschappen in [!DNL Audience Manager]. Ga naar **[!UICONTROL Audience Data > Traits]** en vouw de map [!UICONTROL 3rd-Party Data] uit om uw eigenschappen te bekijken, of maak segmenten en modellen met deze data.

 

**Wat is [!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager gebruikt [!UICONTROL Tag Insertion Manager] (TIM) om [!UICONTROL data collection code (DIL)] te maken en te beheren. Deze functie is verouderd en is eerst vervangen door [!UICONTROL Dynamic Tag Manager (DTM)] en later door [!DNL Adobe Experience Platform Tags]. Voor meer informatie, zie [ de Markeringen van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=nl-NL).

 

**Wat zijn de verschillen tussen Algorithmic Models en Trait Recommendations? Wanneer moet ik welke gebruiken?**

**Algorithmic Models**

Met Algorithmic Models worden niet alleen de meest invloedrijke eigenschappen gevonden, maar worden gebruikers ook geturfd op basis van deze eigenschappen en wordt aan elke gebruiker een afzonderlijke score toegewezen. Vervolgens maakt u algoritmische eigenschappen om uw gebruikers te targeten. Met de besturingselementen voor nauwkeurigheid en bereik in Eigenschapbuilder kunt u opgeven welke gebruikers u wilt targeten van alle gebruikers met de gewenste invloedrijke eigenschappen.

Met Algorithmic Models kunt u gebruikers op verschillende nauwkeurigheidsniveaus selecteren en in Audience Lab testen welke groep gebruikers het beste converteert. Zie het gedetailleerde gebruiksscenario in [Modellen vergelijken in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

In Algorithmic Models wordt het model elke acht dagen uitgevoerd en worden de gebruikers vernieuwd die voor algoritmische eigenschappen zijn gekwalificeerd.

**Trait Recommendations**

Trait Recommendations is een snelle manier om inzicht te krijgen in andere eigenschappen die lijken op degene die u in een segment gebruikt.

U kunt Trait Recommendations het best gebruiken in de volgende gevallen:

* U hebt snelle inzichten nodig tijdens het bouwen van een segment;
* U gebruikt de segmenten voor korte campagnes of wanneer u snelle suppressie wilt toepassen op een converterende doelgroep;
* U probeert het bereik te maximaliseren.

 

**Is er een verschil tussen de segmenten van Adobe Analytics en Audience Manager?**

Ja, lees [Inzicht in segmenten in Analytics en Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=nl-NL) voor een uitgebreide beschrijving van de verschillen.
