---
description: Het Laboratorium van het publiek laat verscheidene gebruiksgevallen toe door u toe te staan om basislijnsegmenten voor het creëren van testgroepen te gebruiken. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.
seo-description: Het Laboratorium van het publiek laat verscheidene gebruiksgevallen toe door u toe te staan om basislijnsegmenten voor het creëren van testgroepen te gebruiken. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.
seo-title: Gebruiksscenario's voor ADL
solution: Audience Manager
title: Gebruiksscenario's voor ADL
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---


# Gebruiksscenario&#39;s voor ADL {#audience-lab-use-cases}

[!UICONTROL Audience Lab] laat verscheidene gebruiksgevallen toe door u toe te staan om basislijnsegmenten voor het creëren van testgroepen te gebruiken. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.

## Modellen vergelijken in Audience Lab {#compare-models}

U kunt verschillende typen en bronnen van modellen gebruiken in [!DNL Audience Manager]. [!UICONTROL Audience Lab] biedt een eenvoudige manier om de conversiekoersen van uw klanten te vergelijken in uw actieve modellen.

<!-- audience-lab-compare-models.xml -->

In dit geval vergelijkt u verschillende modellen. U kunt of modellen gebruiken die via een interne data warehouse worden gecreeerd en hen invoeren [!DNL Audience Manager] als [Onboded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) of u kunt de eigenschap van de Modellen [van het](../../features/algorithmic-models/understanding-models.md) Algoritme in gebruiken [!DNL Audience Manager].

1. Maak twee modellen in de [Modelbouwer](../../features/algorithmic-models/create-model.md)of via een extern platform.
1. Maak [algoritmische kenmerken](../../features/traits/create-algorithmic-traits.md) van het algoritmische model of importeer uw eigen modellen als onboekbare kenmerken.
1. Maak wederzijds uitsluitende segmenten zodat gebruikers in beide modellen elkaar niet overlappen:

   * Maak een *Model 1-segment* en een *Model 2-segment*.
   * Heb de segmentregel voor *Model 1 Segment* model 1 de eigenschap [!DNL AND NOT] van het trekkenmodel 2, en vice versa voor *Model 2 Segment* zijn.

1. [Maak twee segmenttestgroepen](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], één met *Model 1 Segment* als basislijn, de andere met *Model 2 Segment* als basislijn.

   * De variabelen voor beide testgroepen gelijk houden: dezelfde doelen, creatieve doelen, conversiekenmerken.
   * Zorg ervoor dat de testsegmenten een vergelijkbaar aantal gebruikers hebben (1,6 miljoen en 1,8 miljoen is bijvoorbeeld in orde, 1,6 miljoen en 16 miljoen niet).
   * Reserveer een controlesegment in elke testgroep van het testsegment. Op deze manier kunt u een klein deel van elk segment opzij zetten en niet expliciet in de test als doel instellen.

1. Onderzoek de resultaten:

   * Het [Audience Lab rapporteringsmening](../../features/audience-lab/audience-lab-reporting-view.md) zal het aantal omzettingen tonen elk model drijft. Voor op conversie gebaseerde campagnes, zal het testsegment dat de meeste omzettingen drijft het model betekenen dat het best presteert.
   * Omdat u controlesegmenten hebt, kunt u ook evalueren hoe het model tegen &quot;standaard het richten.&quot;deed U test niet alleen het ene model versus het andere, maar test de vraag of dit model beter is dan normale praktijken.

## Creatieven testen op verschillende doelen {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Gebruik deze optie [!UICONTROL Audience Lab] om het aantal conversies te meten dat een creatieve toepassing gebruikt voor verschillende bestemmingen. Met dit gebruiksgeval kunt u ook de conversies van de creatieve elementen meten aan de hand van natuurlijk voorkomende omzettingen.

1. [Maak een segmenttestgroep](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)door het segment te selecteren waarmee u de creatieve versie wilt testen als basislijnsegment.
1. Splits het basislijnsegment in testsegmenten en besturingssegmenten.
1. Wijs de testsegmenten aan de verschillende bestemmingen toe u wenst om te testen.
1. Het controlesegment kan worden ingehouden en niet aan om het even welke bestemming in kaart worden gebracht. Het controlesegment mag niet worden gericht op de creatieve test om een resultatenbasislijn in te stellen voor natuurlijk voorkomende omzettingen.
1. Geef een begindatum en een einddatum voor de test op.
1. Opstelling het segment en creatief in de bestemmingen.
1. In de rapportweergave [van het](../../features/audience-lab/audience-lab-reporting-view.md) Audience Lab ziet u het aantal conversies dat de creatieve onderneming naar andere bestemmingen voert.
1. Omdat u een controlesegment creeerde, kunt u ook evalueren hoe creatief tegen natuurlijk optredende omzettingen deed. U test de vraag: &quot;Heeft dit creatief een hogere omrekeningskoers dan normale praktijken veroorzaakt?&quot;
