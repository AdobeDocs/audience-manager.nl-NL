---
description: Het Laboratorium van het publiek laat verscheidene gebruiksgevallen toe door u toe te staan om basislijnsegmenten voor het creëren van testgroepen te gebruiken. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.
seo-description: Het Laboratorium van het publiek laat verscheidene gebruiksgevallen toe door u toe te staan om basislijnsegmenten voor het creëren van testgroepen te gebruiken. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.
seo-title: Gebruiksscenario’s voor Audience Lab
solution: Audience Manager
title: Gebruiksscenario’s voor Audience Lab
topic-edit: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: 'Audience Lab '
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Gebruiksscenario’s voor Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] laat verscheidene gebruiksgevallen toe door u toe te staan om basislijnsegmenten voor het creëren van testgroepen te gebruiken. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.

## Modellen vergelijken in Audience Lab {#compare-models}

U kunt verscheidene verschillende types en bronnen van modellen in [!DNL Audience Manager] gebruiken. [!UICONTROL Audience Lab] biedt een eenvoudige manier om de conversiekoersen van uw klanten te vergelijken in uw actieve modellen.

<!-- audience-lab-compare-models.xml -->

In dit geval vergelijkt u verschillende modellen. U kunt of modellen gebruiken die via een intern gegevenspakhuis worden gecreeerd en hen in [!DNL Audience Manager] als [Onboted Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) invoeren of u kunt [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) eigenschap in [!DNL Audience Manager] gebruiken.

1. Maak twee modellen in de [Model Builder](../../features/algorithmic-models/create-model.md) of via een extern platform.
1. Maak [algoritmische kenmerken](../../features/traits/create-algorithmic-traits.md) van het algoritmische model of importeer uw eigen modellen als onboekbare kenmerken.
1. Maak wederzijds uitsluitende segmenten zodat gebruikers in beide modellen elkaar niet overlappen:

   * Maak een *Model 1 Segment* en een *Model 2 Segment*.
   * De segmentregel voor *Model 1 Segment* zijn model 1 eigenschap [!DNL AND NOT] model 2 eigenschap, en omgekeerd voor *Model 2 Segment*.

1. [Maak twee segment test ](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) groepen  [!UICONTROL Audience Lab], één met  *Model 1* Segmentas de basislijn, de andere met  *Model 2* Segmentatie als basislijn.

   * De variabelen voor beide testgroepen gelijk houden: dezelfde doelen, creatieve doelen, conversiekenmerken.
   * Zorg ervoor dat de testsegmenten een vergelijkbaar aantal gebruikers hebben (1,6 miljoen en 1,8 miljoen is bijvoorbeeld in orde, 1,6 miljoen en 16 miljoen niet).
   * Reserveer een controlesegment in elke testgroep van het testsegment. Op deze manier kunt u een klein deel van elk segment opzij zetten en niet expliciet in de test als doel instellen.

1. Onderzoek de resultaten:

   * In de [Audience Lab-rapportageweergave](../../features/audience-lab/audience-lab-reporting-view.md) wordt het aantal conversies weergegeven dat elk model bestuurt. Voor op conversie gebaseerde campagnes, zal het testsegment dat de meeste omzettingen drijft het model betekenen dat het best presteert.
   * Omdat u controlesegmenten hebt, kunt u ook evalueren hoe het model tegen &quot;standaard het richten.&quot;deed U test niet alleen het ene model versus het andere, maar test de vraag of dit model beter is dan normale praktijken.

## Creatieven testen op verschillende doelen {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Gebruik [!UICONTROL Audience Lab] om het aantal omzettingen te meten creatief over verschillende bestemmingen drijft. Met dit gebruiksgeval kunt u ook de conversies van de creatieve elementen meten aan de hand van natuurlijk voorkomende omzettingen.

1. [Maak een segmenttestgroep](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) door het segment te selecteren waarmee u de creatieve versie wilt testen als basislijnsegment.
1. Splits het basislijnsegment in testsegmenten en besturingssegmenten.
1. Wijs de testsegmenten aan de verschillende bestemmingen toe u wenst om te testen.
1. Het controlesegment kan worden ingehouden en niet aan om het even welke bestemming in kaart worden gebracht. Het controlesegment mag niet worden gericht op de creatieve test om een resultatenbasislijn in te stellen voor natuurlijk voorkomende omzettingen.
1. Geef een begindatum en een einddatum voor de test op.
1. Opstelling het segment en creatief in de bestemmingen.
1. De [Audience Lab rapporteringsmening](../../features/audience-lab/audience-lab-reporting-view.md) zal het aantal omzettingen tonen creatief over de bestemmingen drijft.
1. Omdat u een controlesegment creeerde, kunt u ook evalueren hoe creatief tegen natuurlijk optredende omzettingen deed. U test de vraag: &quot;Heeft deze creatieve actie een hogere conversiegraad opgeleverd dan normale praktijken?&quot;
