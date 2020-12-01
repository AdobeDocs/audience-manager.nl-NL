---
description: Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen vanuit de Audience Manager
seo-description: Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen vanuit de Audience Manager
seo-title: Audience Marketplace voor datakopers
solution: Audience Manager
title: Audience Marketplace voor datakopers
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 2%

---


# [!UICONTROL Audience Marketplace] voor gegevenskopers  {#audience-marketplace-for-data-buyers}

Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen binnen [!DNL Audience Manager].

>[!NOTE]
>[Op rol-gebaseerde toestemmingen](../../../reporting/reports-dashboard.md) controleren toegang tot [!UICONTROL Audience Marketplace] eigenschappen.
>
>* Beheerders kunnen gegevensfeeds maken, abonnees beheren en zich abonneren op gegevensfeeds.
>* Gebruikers kunnen alleen feeds zoeken en weergeven.


## De [!UICONTROL Marketplace]: Info {#about-marketplace}

De [!UICONTROL Marketplace] is een [!DNL Audience Manager] functie voor gegevenskopers die een lijst bevat met gegevensfeeds waarop u zich kunt abonneren. Er worden platte gegevens, [!DNL CPM] en privégegevens weergegeven. Deze feeds worden geleverd door externe leveranciers die [!DNL Audience Manager] gebruiken om gegevens te verkopen.

In [!UICONTROL Marketplace], laten de rapporteringshulpmiddelen u voedergebruik en de overlapping tussen uw [!UICONTROL traits] en die in een geabonneerde gegevensvoer volgen. Tot slot zorgt [!UICONTROL Audience Marketplace] voor facturen en betaalde kosten (hoewel u zelf gebruik moet melden wanneer u bent geabonneerd op een [!DNL CPM] feed). [!DNL Adobe] Met deze functies kunt u effectieve gegevensbronnen vinden zonder dat u tijd verspilt aan het zoeken naar een gegevensaanbieder.

>[!TIP]
>
>Gebruik **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** om gegevensfeeds van hoge kwaliteit te vinden waarop u zich kunt abonneren. Dan, ga terug in [!DNL Audience Manager] gebruikersinterface of gebruik [Audience Marketplace koper API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) om op de feeds in te tekenen u vond.

![koper-marketing-overzicht](assets/buyer-marketplace-overview.png)

De lijst [!UICONTROL Marketplace] bevat informatie die u kunt sorteren en zoeken om de gegevenstoevoer te vinden die voor u geschikt is. De volgende objecten staan in de lijst van [!UICONTROL Marketplace]-kopers:

* **[!UICONTROL Search]**: Gegevensfeeds zoeken op naam of tekstbeschrijving.
* **[!UICONTROL Similar Traits]**: Hier ziet u het aantal items dat vergelijkbaar is  [!UICONTROL traits] met een gegevensfeed. Deze kolom wordt getoond nadat u [!UICONTROL trait] of [!UICONTROL segment] om door in **[!UICONTROL Similarity To]** sectie typt te filtreren.
* **[!UICONTROL Name]**: Naam van de gegevensinvoer.
* **[!UICONTROL Description]**: Informatie over de inhoud van een gegevensfeed.
* **[!UICONTROL Provider]**: Naam van de gegevensaanbieder.
* **[!UICONTROL Traits]**: The number of  [!UICONTROL traits] in a data feed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Het aantal unieke gebruikers dat in de laatste 30 dagen is weergegeven.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Het aantal gebruikers in uw account dat de gebruikers in de account van de provider overlappen.
* **[!UICONTROL Feed Overlap]**: De 30 dagen overlapte uniques-waarde, weergegeven in percentages, berekend als: Gegevenskoper 30 dagen overlapte uniques/Data koper 30 dagen uniques) x 100.
* **[!UICONTROL Private Feeds]**: Zie  [Privégegevensfeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Het aantal abonnementen dat u hebt bij een gegevensaanbieder.

 

Om de beste gegevensvoer voor uw behoeften gemakkelijk te vinden, gebruik de volgende filters beschikbaar op de linkerkant van [!UICONTROL Marketplace] pagina:

* **[!UICONTROL Similarity To]**: Gegevens filteren op basis van de gelijkenis met een  [!UICONTROL trait] of  [!UICONTROL segment] de keuze. Bij het ingaan van [!UICONTROL trait] of segment om te vergelijken met, kunt u [!UICONTROL trait] of [!UICONTROL segment] identiteitskaart, of hun respectieve namen gebruiken.
* **[!UICONTROL Similarity Cutoff]**: Sleep de schuifregelaar om de gegevensfeeds te filteren op basis van de mate van overeenkomst  [!UICONTROL traits] met de geselecteerde  [!UICONTROL trait] of  [!UICONTROL segment]menuopties. Voor meer informatie over [!UICONTROL trait] gelijkheidsscores, zie [Score van de Gelijkaardige Score van de Trait](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filter de gegevensfeeds op basis van uw abonnementsstatus.
* **[!UICONTROL Plan Use Case]**: Gegevensfeeds filteren op basis van de ondersteunde gebruiksgevallen:  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]** en  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Gegevens filteren op basis van hun prijstype.

## Gelijkend [!UICONTROL Traits] {#finding-similar-traits} zoeken

[!UICONTROL Audience Marketplace] biedt u de optie om  [!UICONTROL traits] van diverse gegevensvoer, gebaseerd op hun gelijkenis met uw bestaande  [!UICONTROL traits] of segmenten te vinden. Dit doet u als volgt:

1. Ga naar **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Met de kiezer **[!UICONTROL Similarity To]** kunt u kiezen tussen filteren op basis van een [!UICONTROL trait] of [!UICONTROL segment]. U kunt filteren op [!UICONTROL trait]/[!UICONTROL segment] identiteitskaart of naam. In het zoekvak worden automatisch relevante suggesties weergegeven op basis van uw invoer.
3. Nadat u de eigenschap of het segment hebt geïdentificeerd waarop u wilt filteren, klikt u erop in de lijst met suggesties.
4. Als u de resultaten wilt verkleinen, gebruikt u de schuifregelaar **[!UICONTROL Similarity Cutoff]** om van minder vergelijkbare [!UICONTROL traits] naar meer vergelijkbare schuifregelaars te gaan.

Zodra het filtreren volledig is, zult u een nieuwe kolom in de resultatenpagina zien: **[!UICONTROL Similar Traits]**. Deze kolom toont u het aantal gelijkaardige [!UICONTROL traits] aan die u door, van elke gegevensvoer filterde die aan de het filtreren criteria voldoet.

Klik op het nummer in de kolom **[!UICONTROL Similar Traits]** om de volledige lijst met vergelijkbare kenmerken weer te geven.

>[!NOTE]
>
> Audience Marketplace geeft de top 500 van vergelijkbare [!UICONTROL trait] resultaten van over de gegevensfeeds weer.

Bekijk de video hieronder voor een volledig overzicht van hoe u vergelijkbare [!UICONTROL traits] kunt vinden.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Privédatafeeds {#private-data-feeds}

In de lijst [!UICONTROL Marketplace] worden soms de naam van de provider en [!UICONTROL trait] gegevens gemarkeerd als private. Dit geeft een [persoonlijke gegevensfeed](../../../features/audience-marketplace/marketplace-private-feeds.md) aan. Met een persoonlijke gegevensinvoer kunnen verkopers de toegang van kopers tot hun gegevens beperken. Verkopers kunnen feeds privé maken wanneer ze speciale aanbiedingen, kortingen aanbieden of wanneer hun privacy en toegangsbeheer belangrijk zijn. Als koper moet je een aanvraag voor een abonnement naar de verkoper sturen als je toegang wilt tot een privéfeed. Zie [Abonneren op een privégegevensfeed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) voor meer informatie.

>[!MORELIKETHIS]
>
>* [De pagina Details abonnement in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Kortingen voor gegevenskopers](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

