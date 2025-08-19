---
description: Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen in Audience Manager
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace for Data Buyers
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 0%

---

# [!UICONTROL Audience Marketplace] voor gegevenskopers {#audience-marketplace-for-data-buyers}

Overzicht en workflow voor gegevenskopers die gegevens van derden willen kopen vanuit [!DNL Audience Manager] .

>[!NOTE]
>[ Op rol-gebaseerde toestemmingen ](../../../reporting/reports-dashboard.md) controletoegang tot [!UICONTROL Audience Marketplace] eigenschappen.
>
>* Beheerders kunnen gegevensfeeds maken, abonnees beheren en zich abonneren op gegevensfeeds.
>* Gebruikers kunnen alleen feeds zoeken en weergeven.

## The [!UICONTROL Marketplace]: About {#about-marketplace}

De [!UICONTROL Marketplace] is een [!DNL Audience Manager] -functie voor gegevenskopers die een lijst bevat met gegevensfeeds waarop u zich kunt abonneren. Er worden platte gegevens, [!DNL CPM] en privégegevens weergegeven. Deze feeds worden geleverd door externe leveranciers die [!DNL Audience Manager] gebruiken om gegevens te verkopen.

In [!UICONTROL Marketplace] kunt u met rapportagegereedschappen het gebruik van feed en de overlapping tussen uw [!UICONTROL traits] en de gegevens in een geabonneerde gegevensfeed bijhouden. Tot slot zorgt [!UICONTROL Audience Marketplace] voor facturen en betaalde kosten (hoewel u het gebruik zelf moet melden wanneer u zich abonneert op een [!DNL Adobe] feed). [!DNL CPM] Met deze functies kunt u effectieve gegevensbronnen vinden zonder dat u tijd verspilt aan het zoeken naar een gegevensaanbieder.

>[!TIP]
>
>Gebruik de **[Vinder van de Auditie van Adobe ](https://www.adobe-audience-finder.com/)** om hoogwaardig gegevensvoer te vinden dat u kunt intekenen aan. Dan, ga terug in het [!DNL Audience Manager] gebruikersinterface of gebruik [ de Koper API van Audience Marketplace ](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) om aan de feeds in te tekenen u vond.

![ koper-markt-plaats-overzicht ](assets/buyer-marketplace-overview.png)

De lijst [!UICONTROL Marketplace] bevat informatie die u kunt sorteren en zoeken naar de juiste gegevensfeed voor u. Objecten in de lijst met kopers van [!UICONTROL Marketplace] zijn:

* **[!UICONTROL Search]**: zoek gegevensfeeds op naam of beschrijving van tekst.
* **[!UICONTROL Similar Traits]**: toont u het aantal gelijksoortige [!UICONTROL traits] van een gegevensvoer. Deze kolom wordt weergegeven nadat u in de sectie [!UICONTROL trait] een [!UICONTROL segment] of **[!UICONTROL Similarity To]** hebt ingevoerd om door te filteren.
* **[!UICONTROL Name]**: naam van de gegevensfeed.
* **[!UICONTROL Description]**: informatie over de inhoud van een gegevensfeed.
* **[!UICONTROL Provider]**: naam van de gegevensaanbieder.
* **[!UICONTROL Traits]**: Het aantal [!UICONTROL traits] in een gegevensfeed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Het aantal unieke gebruikers dat in de laatste 30 dagen is weergegeven.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Het aantal gebruikers in uw account dat de gebruikers in de account van de provider overlappen.
* **[!UICONTROL Feed Overlap]**: De 30 dagen overlapte de uniques-waarde, weergegeven in percentages, berekend als: Gegevenskoper 30 dagen overlapte uniques/Data-koper 30 dagen uniques) x 100.
* **[!UICONTROL Private Feeds]**: Zie [ Privégegevensvoer ](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Het aantal abonnementen dat u hebt bij een gegevensaanbieder.

 

Gebruik de volgende filters aan de linkerkant van de pagina [!UICONTROL Marketplace] om gemakkelijk de beste gegevensfeeds voor uw behoeften te vinden:

* **[!UICONTROL Similarity To]**: Gegevens filteren op basis van de gelijkenis met een [!UICONTROL trait] of [!UICONTROL segment] van uw keuze. Wanneer u de [!UICONTROL trait] - of segmentgegevens opgeeft die u wilt vergelijken, kunt u de [!UICONTROL trait] - of [!UICONTROL segment] -id of hun respectievelijke namen gebruiken.
* **[!UICONTROL Similarity Cutoff]**: Sleep de schuifregelaar om de gegevensfeeds te filteren op basis van de gelijkenis tussen de [!UICONTROL traits] en de geselecteerde [!UICONTROL trait] of [!UICONTROL segment] . Om meer over [!UICONTROL trait] gelijkheidsscores te leren, zie [ Score van de Gelijkwaardigheid van het Tonen ](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filter de gegevensfeeds op basis van uw abonnementsstatus.
* **[!UICONTROL Plan Use Case]**: Gegevens filteren op basis van de ondersteunde gebruiksgevallen: **[!UICONTROL Activation]** , **[!UICONTROL Segments and Overlap]** en **[!UICONTROL Modelling]** .
* **[!UICONTROL Plan Unit]**: Gegevensfeeds filteren op basis van het prijstype.

## Gelijkend zoeken [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] biedt u de mogelijkheid om [!UICONTROL traits] te zoeken vanuit verschillende gegevensfeeds, op basis van de gelijkenis met uw bestaande [!UICONTROL traits] of segmenten. Dit doet u als volgt:

1. Ga naar **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]** .
2. Gebruik de kiezer van **[!UICONTROL Similarity To]** om te kiezen tussen filteren op basis van een [!UICONTROL trait] of [!UICONTROL segment] . U kunt filteren op basis van [!UICONTROL trait]/[!UICONTROL segment] ID of naam. In het zoekvak worden automatisch relevante suggesties weergegeven op basis van uw invoer.
3. Nadat u de eigenschap of het segment hebt geïdentificeerd waarop u wilt filteren, klikt u erop in de lijst met suggesties.
4. Als u de resultaten wilt verkleinen, gebruikt u de schuifregelaar **[!UICONTROL Similarity Cutoff]** om van minder overeenkomende [!UICONTROL traits] naar meer vergelijkbare resultaten te gaan.

Wanneer het filteren is voltooid, ziet u een nieuwe kolom op de resultatenpagina: **[!UICONTROL Similar Traits]** . In deze kolom ziet u het aantal [!UICONTROL traits] items dat lijkt op het aantal dat u hebt gefilterd in elke gegevensfeed die voldoet aan de filtercriteria.

Klik op het nummer in de kolom **[!UICONTROL Similar Traits]** om de volledige lijst met vergelijkbare kenmerken weer te geven.

>[!NOTE]
>
> In Audience Marketplace worden de 500 meest vergelijkbare [!UICONTROL trait] resultaten uit de verschillende gegevensfeeds weergegeven.

Bekijk de onderstaande video voor een volledig overzicht van het zoeken naar vergelijkbare informatie [!UICONTROL traits] .

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Privégegevensfeeds {#private-data-feeds}

In de lijst [!UICONTROL Marketplace] worden de naam van de provider en [!UICONTROL trait] -gegevens soms gemarkeerd als private. Dit wijst op a [ privé gegevensvoer ](../../../features/audience-marketplace/marketplace-private-feeds.md). Met een persoonlijke gegevensinvoer kunnen verkopers de toegang van kopers tot hun gegevens beperken. Verkopers kunnen feeds privé maken wanneer ze speciale aanbiedingen, kortingen aanbieden of wanneer hun privacy en toegangsbeheer belangrijk zijn. Als koper moet je een aanvraag voor een abonnement naar de verkoper sturen als je toegang wilt tot een privéfeed. Zie [ aan een Privé Invoer van Gegevens ](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) voor details intekenen.

>[!MORELIKETHIS]
>
>* [ Begrijpend de Pagina van de Details van het Plan in Audience Marketplace ](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [ Kortingen voor de Kopers van Gegevens ](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
