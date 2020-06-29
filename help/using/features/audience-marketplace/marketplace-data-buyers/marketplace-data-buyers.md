---
description: Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen vanuit de Audience Manager
seo-description: Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen vanuit de Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace for Data Buyers
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 0%

---


# [!UICONTROL Audience Marketplace] voor gegevenskopers {#audience-marketplace-for-data-buyers}

Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen vanuit de toepassing zelf [!DNL Audience Manager].

>[!NOTE]
>[Op rollen gebaseerde toestemmingen](../../../reporting/reports-dashboard.md) controleren toegang tot [!UICONTROL Audience Marketplace] eigenschappen.
>
>* Beheerders kunnen gegevensfeeds maken, abonnees beheren en zich abonneren op gegevensfeeds.
>* Gebruikers kunnen alleen feeds zoeken en weergeven.


## De [!UICONTROL Marketplace]: Info {#about-marketplace}

Het [!UICONTROL Marketplace] is een [!DNL Audience Manager] functie voor kopers van gegevens waarin de gegevensfeeds worden vermeld waarop je je kunt abonneren. Er worden platte gegevens, [!DNL CPM]en privégegevens weergegeven. Deze feeds worden geleverd door externe leveranciers die gegevens [!DNL Audience Manager] verkopen.

In [!UICONTROL Marketplace], laat het melden hulpmiddelen u voedergebruik en de overlapping tussen uw [!UICONTROL traits] en die in een geabonneerde gegevensvoer volgen. Tot slot, met [!UICONTROL Audience Marketplace], zorgt [!DNL Adobe] voor facturen en vergoedingsbetalingen (hoewel u gebruik moet zelf melden wanneer geabonneerd op een [!DNL CPM] voer). Met deze functies kunt u effectieve gegevensbronnen vinden zonder dat u tijd verspilt aan het zoeken naar een gegevensaanbieder.

>[!TIP]
>
>Met de **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**kunt u naar gegevensfeeds van hoge kwaliteit zoeken waarop u zich kunt abonneren. Ga vervolgens terug naar de[!DNL Audience Manager]gebruikersinterface of gebruik de[Audience Marketplace-API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)voor kopers om u te abonneren op de feeds die u hebt gevonden.

![koper-marketing-overzicht](assets/buyer-marketplace-overview.png)

De [!UICONTROL Marketplace] lijst bevat informatie die u kunt sorteren en zoeken om de gegevenstoevoer te vinden die voor u geschikt is. Objecten in de lijst met [!UICONTROL Marketplace] kopers zijn:

* **[!UICONTROL Search]**: Gegevensfeeds zoeken op naam of tekstbeschrijving.
* **[!UICONTROL Similar Traits]**: Hier ziet u het aantal gelijksoortige gegevens [!UICONTROL traits] uit een gegevensinvoer. Deze kolom wordt getoond nadat u een [!UICONTROL trait] of [!UICONTROL segment] om door in de **[!UICONTROL Similarity To]** sectie te filtreren ingaat.
* **[!UICONTROL Name]**: Naam van de gegevensinvoer.
* **[!UICONTROL Description]**: Informatie over de inhoud van een gegevensfeed.
* **[!UICONTROL Provider]**: Naam van de gegevensaanbieder.
* **[!UICONTROL Traits]**: The number of [!UICONTROL traits] in a data feed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Het aantal unieke gebruikers dat in de laatste 30 dagen is weergegeven.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Het aantal gebruikers in uw account dat de gebruikers in de account van de provider overlappen.
* **[!UICONTROL Feed Overlap]**: De 30 dagen overlapte uniques-waarde, weergegeven in percentages, berekend als: Gegevenskoper 30 dagen overlapte uniques/Data koper 30 dagen uniques) x 100.
* **[!UICONTROL Private Feeds]**: Zie [Privégegevensfeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Het aantal abonnementen dat u hebt bij een gegevensaanbieder.

 

Gebruik de volgende filters aan de linkerkant van de [!UICONTROL Marketplace] pagina om gemakkelijk de beste gegevensfeeds voor uw behoeften te vinden:

* **[!UICONTROL Similarity To]**: Gegevens filteren op basis van de gelijkenis met een [!UICONTROL trait] of [!UICONTROL segment] van uw keuze. Wanneer u het [!UICONTROL trait] of segment opgeeft dat u wilt vergelijken, kunt u de [!UICONTROL trait] id of [!UICONTROL segment] id of hun respectievelijke namen gebruiken.
* **[!UICONTROL Similarity Cutoff]**: Sleep de schuifregelaar om de gegevensfeeds te filteren op basis van de mate waarin deze overeenkomen met de [!UICONTROL traits] geselecteerde [!UICONTROL trait] of [!UICONTROL segment]. Zie Score [!UICONTROL trait] Trait-gelijkenis voor meer informatie over scores op [gelijkenis](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filter de gegevensfeeds op basis van uw abonnementsstatus.
* **[!UICONTROL Plan Use Case]**: Gegevensfeeds filteren op basis van de ondersteunde gebruiksgevallen: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** en **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Gegevens filteren op basis van hun prijstype.

## Gelijkend zoeken [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] biedt u de optie om uit diverse gegevensvoer te vinden, die op hun gelijkenis met uw bestaande [!UICONTROL traits] [!UICONTROL traits] of segmenten wordt gebaseerd. Dit doet u als volgt:

1. Ga naar **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Gebruik de **[!UICONTROL Similarity To]** kiezer om te kiezen tussen filteren op basis van een [!UICONTROL trait] of [!UICONTROL segment]. U kunt filteren op basis van [!UICONTROL trait]/[!UICONTROL segment] ID of naam. In het zoekvak worden automatisch relevante suggesties weergegeven op basis van uw invoer.
3. Nadat u de eigenschap of het segment hebt geïdentificeerd waarop u wilt filteren, klikt u erop in de lijst met suggesties.
4. Als u de resultaten wilt verkleinen, gebruikt u de **[!UICONTROL Similarity Cutoff]** schuifregelaar om van minder vergelijkbare [!UICONTROL traits]naar meer vergelijkbare resultaten te gaan.

Zodra het filtreren volledig is, zult u een nieuwe kolom in de resultatenpagina zien: **[!UICONTROL Similar Traits]**. Deze kolom toont u het aantal gelijkend op [!UICONTROL traits] die u door, van elke gegevensvoer filtreerde die aan de het filtreren criteria voldoet.

Klik op het nummer in de **[!UICONTROL Similar Traits]** kolom om de volledige lijst met vergelijkbare kenmerken weer te geven.

>[!NOTE]
>
> In Audience Marketplace worden de 500 meest vergelijkbare [!UICONTROL trait] resultaten van de gegevensinvoer weergegeven.

Bekijk de video hieronder voor een volledig overzicht van het vinden van gelijkaardig [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Privédatafeeds {#private-data-feeds}

In de [!UICONTROL Marketplace] lijst worden de naam en de [!UICONTROL trait] gegevens van de provider soms gemarkeerd als private. Dit geeft een [persoonlijke gegevensfeed](../../../features/audience-marketplace/marketplace-private-feeds.md)aan. Met een persoonlijke gegevensinvoer kunnen verkopers de toegang van kopers tot hun gegevens beperken. Verkopers kunnen feeds privé maken wanneer ze speciale aanbiedingen, kortingen aanbieden of wanneer hun privacy en toegangsbeheer belangrijk zijn. Als koper moet je een aanvraag voor een abonnement naar de verkoper sturen als je toegang wilt tot een privéfeed. Zie [Abonneren op een privégegevensfeed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) voor meer informatie.

>[!MORELIKETHIS]
>
>* [De pagina met abonnementsdetails in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Kortingen voor gegevenskopers](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

