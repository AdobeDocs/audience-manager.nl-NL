---
description: Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen vanuit de Audience Manager
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace voor datakopers
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# [!UICONTROL Audience Marketplace] voor gegevenskopers {#audience-marketplace-for-data-buyers}

Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen vanuit [!DNL Audience Manager].

>[!NOTE]
>[Machtigingen op basis van rollen](../../../reporting/reports-dashboard.md) toegang tot [!UICONTROL Audience Marketplace] functies.
>
>* Beheerders kunnen gegevensfeeds maken, abonnees beheren en zich abonneren op gegevensfeeds.
>* Gebruikers kunnen alleen feeds zoeken en weergeven.


## De [!UICONTROL Marketplace]: Info {#about-marketplace}

De [!UICONTROL Marketplace] is een [!DNL Audience Manager] functie voor gegevenskopers die een lijst bevat met gegevensfeeds waarop je je kunt abonneren. In de lijst staat een vast tarief, [!DNL CPM]en persoonlijke gegevensfeeds. Deze feeds worden geleverd door externe leveranciers die [!DNL Audience Manager] om gegevens te verkopen.

In de [!UICONTROL Marketplace]Met de rapportgereedschappen kunt u het gebruik van feed en de overlapping tussen uw [!UICONTROL traits] en gegevens in een geabonneerde gegevensfeed. Tot slot, met [!UICONTROL Audience Marketplace], [!DNL Adobe] zorgt voor facturen en betaalde vergoedingen (hoewel u zelf het gebruik moet melden wanneer u zich op een [!DNL CPM] voer). Met deze functies kunt u effectieve gegevensbronnen vinden zonder dat u tijd verspilt aan het zoeken naar een gegevensaanbieder.

>[!TIP]
>
>Gebruik de **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** om te zoeken naar gegevensfeeds van hoge kwaliteit waarop u zich kunt abonneren. Ga dan terug naar de [!DNL Audience Manager] gebruikersinterface of [Audience Marketplace-koper-API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) om in te schrijven op de feeds die u hebt gevonden.

![koper-marketing-overzicht](assets/buyer-marketplace-overview.png)

De [!UICONTROL Marketplace] De lijst bevat informatie die u kunt sorteren en zoeken om de gegevenstoevoer te vinden die voor u geschikt is. Items in het dialoogvenster [!UICONTROL Marketplace] De lijst met kopers bevat:

* **[!UICONTROL Search]**: Gegevensfeeds zoeken op naam of tekstbeschrijving.
* **[!UICONTROL Similar Traits]**: Hier ziet u het aantal gelijksoortige [!UICONTROL traits] uit een gegevensfeed. Deze kolom wordt weergegeven nadat u een [!UICONTROL trait] of [!UICONTROL segment] om te filteren op **[!UICONTROL Similarity To]** sectie.
* **[!UICONTROL Name]**: Naam van de gegevensinvoer.
* **[!UICONTROL Description]**: Informatie over de inhoud van een gegevensfeed.
* **[!UICONTROL Provider]**: Naam van de gegevensaanbieder.
* **[!UICONTROL Traits]**: Het aantal [!UICONTROL traits] in een gegevensfeed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Het aantal unieke gebruikers dat in de laatste 30 dagen is weergegeven.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Het aantal gebruikers in uw account dat de gebruikers in de account van de provider overlappen.
* **[!UICONTROL Feed Overlap]**: De 30 dagen overlapte uniques-waarde, weergegeven in percentages, berekend als: Gegevenskoper 30 dagen overlapte uniques/Data koper 30 dagen uniques) x 100.
* **[!UICONTROL Private Feeds]**: Zie [Privégegevensfeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Het aantal abonnementen dat u hebt bij een gegevensaanbieder.

 

Gebruik de volgende filters aan de linkerkant van het dialoogvenster [!UICONTROL Marketplace] pagina:

* **[!UICONTROL Similarity To]**: Gegevensfeeds filteren op basis van hun gelijkenis met een van de [!UICONTROL trait] of [!UICONTROL segment] van uw keuze. Wanneer u de [!UICONTROL trait] of segment dat u wilt vergelijken, kunt u de opdracht [!UICONTROL trait] of [!UICONTROL segment] Id, of hun respectievelijke namen.
* **[!UICONTROL Similarity Cutoff]**: Sleep de schuifregelaar om de gegevensfeeds te filteren op basis van hoe vergelijkbaar hun [!UICONTROL traits] zijn geselecteerd [!UICONTROL trait] of [!UICONTROL segment]. Meer informatie over [!UICONTROL trait] vergelijkbare scores, zie [Gelijksoortige score volgen](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filter de gegevensfeeds op basis van uw abonnementsstatus.
* **[!UICONTROL Plan Use Case]**: Gegevensfeeds filteren op basis van de ondersteunde gebruiksgevallen: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]**, en **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Gegevens filteren op basis van hun prijstype.

## Gelijkend zoeken [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] geeft u de optie om te zoeken [!UICONTROL traits] van verschillende gegevensfeeds, op basis van hun gelijkenis met uw bestaande [!UICONTROL traits] of segmenten. Dit doet u als volgt:

1. Ga naar **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Gebruik de **[!UICONTROL Similarity To]** kiezer om te kiezen tussen filteren op basis van een [!UICONTROL trait] of [!UICONTROL segment]. U kunt filteren op basis van [!UICONTROL trait]/[!UICONTROL segment] ID of naam. In het zoekvak worden automatisch relevante suggesties weergegeven op basis van uw invoer.
3. Nadat u de eigenschap of het segment hebt geïdentificeerd waarop u wilt filteren, klikt u erop in de lijst met suggesties.
4. Als u de resultaten wilt verkleinen, gebruikt u de opdracht **[!UICONTROL Similarity Cutoff]** schuifregelaar voor verplaatsing van minder vergelijkbare [!UICONTROL traits], op meer gelijkaardige.

Zodra het filtreren volledig is, zult u een nieuwe kolom in de resultatenpagina zien: **[!UICONTROL Similar Traits]**. In deze kolom ziet u het aantal gelijksoortige [!UICONTROL traits] naar de filter u door, van elke gegevensvoer filtreerde die aan de het filtreren criteria voldoet.

Als u de volledige lijst met vergelijkbare kenmerken wilt weergeven, klikt u op het nummer in het dialoogvenster **[!UICONTROL Similar Traits]** kolom.

>[!NOTE]
>
> Audience Marketplace geeft de bovenste 500 vergelijkbare beeldschermen weer [!UICONTROL trait] resulteert uit alle gegevensfeeds.

Bekijk de video hieronder voor een volledig overzicht van hoe u vergelijkbare objecten kunt vinden [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Privédatafeeds {#private-data-feeds}

In de [!UICONTROL Marketplace] lijst, soms de naam van de leverancier en [!UICONTROL trait] gegevens zijn gemarkeerd als private. Dit geeft een [privégegevenstoevoer](../../../features/audience-marketplace/marketplace-private-feeds.md). Met een persoonlijke gegevensinvoer kunnen verkopers de toegang van kopers tot hun gegevens beperken. Verkopers kunnen feeds privé maken wanneer ze speciale aanbiedingen, kortingen aanbieden of wanneer hun privacy en toegangsbeheer belangrijk zijn. Als koper moet je een aanvraag voor een abonnement naar de verkoper sturen als je toegang wilt tot een privéfeed. Zie [Abonneren op een privégegevensfeed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) voor meer informatie.

>[!MORELIKETHIS]
>
>* [De pagina Details abonnement in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Kortingen voor gegevenskopers](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

