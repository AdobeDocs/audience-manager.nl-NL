---
description: Het Laboratorium van het publiek laat verscheidene gebruiksgevallen toe door u toe te staan om basislijnsegmenten voor het creëren van testgroepen te gebruiken. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Gebruiksscenario’s voor Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 1%

---

# Gebruiksscenario’s voor Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] laat verscheidene gebruiksgevallen toe door u toe te staan om basislijnsegmenten voor het creëren van testgroepen te gebruiken. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.

## Modellen vergelijken in Audience Lab {#compare-models}

U kunt verschillende typen en bronnen van modellen gebruiken in [!DNL Audience Manager]. [!UICONTROL Audience Lab] biedt een eenvoudige manier om de conversiekoersen van uw klanten te vergelijken in uw actieve modellen.

<!-- audience-lab-compare-models.xml -->

In dit geval vergelijkt u verschillende modellen. U kunt of modellen gebruiken die via een intern gegevenspakhuis worden gecreeerd en hen invoeren in [!DNL Audience Manager] als [Treinen aan boord](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) of u kunt de [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) functie in [!DNL Audience Manager].

1. Maak twee modellen in de [Model Builder](../../features/algorithmic-models/create-model.md)of via een extern platform.
1. Maken [algoritmische kenmerken](../../features/traits/create-algorithmic-traits.md) uit het algoritmische model of importeer uw eigen modellen als onboventaristische kenmerken.
1. Maak wederzijds uitsluitende segmenten zodat gebruikers in beide modellen elkaar niet overlappen:

   * Een *Model 1 segment* en *Model 2 segment*.
   * Heb de segmentregel voor *Model 1 segment* de kenmerken van model 1 zijn [!DNL AND NOT] model 2-kenmerk en vice versa voor *Model 2 segment*.

1. [Twee segmenttestgroepen maken](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], één met *Model 1 segment* als basislijn, andere met *Model 2 segment* als basislijn.

   * De variabelen voor beide testgroepen gelijk houden: dezelfde doelen, creatieve doelen, conversiekenmerken.
   * Zorg ervoor dat de testsegmenten een vergelijkbaar aantal gebruikers hebben (1,6 miljoen en 1,8 miljoen is bijvoorbeeld in orde, 1,6 miljoen en 16 miljoen niet).
   * Reserveer een controlesegment in elke testgroep van het testsegment. Op deze manier kunt u een klein deel van elk segment opzij zetten en niet expliciet in de test als doel instellen.

1. Onderzoek de resultaten:

   * De [Audiolabrapportweergave](../../features/audience-lab/audience-lab-reporting-view.md) toont het aantal omzettingen dat elk model bestuurt. Voor op conversie gebaseerde campagnes, zal het testsegment dat de meeste omzettingen drijft het model betekenen dat het best presteert.
   * Omdat u controlesegmenten hebt, kunt u ook evalueren hoe het model tegen &quot;standaard het richten.&quot;deed U test niet alleen het ene model versus het andere, maar test de vraag of dit model beter is dan normale praktijken.

## Creatieven testen op verschillende doelen {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Gebruiken [!UICONTROL Audience Lab] om het aantal omzettingen te meten rijdt een creatief over verschillende bestemmingen. Met dit gebruiksgeval kunt u ook de conversies van de creatieve elementen meten aan de hand van natuurlijk voorkomende omzettingen.

1. [Een segmenttestgroep maken](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)selecteert u het segment dat u wilt testen op het creatieve gedeelte en gebruikt u als basislijnsegment.
1. Splits het basislijnsegment in testsegmenten en besturingssegmenten.
1. Wijs de testsegmenten aan de verschillende bestemmingen toe u wenst om te testen.
1. Het controlesegment kan worden ingehouden en niet aan om het even welke bestemming in kaart worden gebracht. Het controlesegment mag niet worden gericht op de creatieve test om een resultatenbasislijn in te stellen voor natuurlijk voorkomende omzettingen.
1. Geef een begindatum en een einddatum voor de test op.
1. Opstelling het segment en creatief in de bestemmingen.
1. De [Audiolabrapportweergave](../../features/audience-lab/audience-lab-reporting-view.md) zal het aantal omzettingen tonen creatief over de bestemmingen drijft.
1. Omdat u een controlesegment creeerde, kunt u ook evalueren hoe creatief tegen natuurlijk optredende omzettingen deed. U test de vraag: &quot;Heeft dit creatief een hogere omrekeningskoers dan normale praktijken veroorzaakt?&quot;
