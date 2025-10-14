---
description: Het Laboratorium van het publiek laat verscheidene gebruiksgevallen toe door u toe te staan om basislijnsegmenten voor het creëren van testgroepen te gebruiken. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Gebruiksscenario's voor ADL
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Gebruiksscenario&#39;s voor ADL {#audience-lab-use-cases}

[!UICONTROL Audience Lab] maakt verschillende gebruiksgevallen mogelijk door basislijnsegmenten te gebruiken voor het maken van testgroepen. U kunt testgroepen in verscheidene wederzijds uitsluitende testsegmenten verdelen, deze aan verschillende bestemmingen in kaart brengen en dan bepalen welke van de segmenten het meest effectief in het drijven omzettingen zijn.

## Modellen vergelijken in Audience Lab {#compare-models}

U kunt in [!DNL Audience Manager] verschillende typen en bronnen van modellen gebruiken. [!UICONTROL Audience Lab] biedt een eenvoudige manier om de conversiekoersen van uw klanten te vergelijken voor alle actieve modellen.

<!-- audience-lab-compare-models.xml -->

In dit geval vergelijkt u verschillende modellen. U kunt of modellen gebruiken die via een intern gegevenspakhuis worden gecreeerd en hen invoeren in [!DNL Audience Manager] als [&#x200B; Onboted Traits &#x200B;](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) of u kunt de [&#x200B; Algorithmic Modellen &#x200B;](../../features/algorithmic-models/understanding-models.md) eigenschap in [!DNL Audience Manager] gebruiken.

1. Creeer twee modellen, of in de [&#x200B; ModelBouwer &#x200B;](../../features/algorithmic-models/create-model.md), of via een buitenplatform.
1. Creeer [&#x200B; algoritmische eigenschappen &#x200B;](../../features/traits/create-algorithmic-traits.md) van het algoritmische model of de invoer uw eigen modellen als onboard trekken.
1. Maak wederzijds uitsluitende segmenten zodat gebruikers in beide modellen elkaar niet overlappen:

   * Creeer a *Model 1 Segment* en a *Model 2 Segment*.
   * Heb de segmentregel voor *Model 1 Segment* model 1 eigenschap [!DNL AND NOT] model 2 eigenschap, en vice versa voor *Model 2 Segment* zijn.

1. [&#x200B; creeer twee groepen van de segmenttest &#x200B;](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], met *Model 1 Segment* als basislijn, andere met *Model 2 Segment* als basislijn.

   * Zorg dat de variabelen voor beide testgroepen hetzelfde blijven: dezelfde bestemmingen, creatieve kenmerken en conversietekenmerken.
   * Zorg ervoor dat de testsegmenten een vergelijkbaar aantal gebruikers hebben (1,6 miljoen en 1,8 miljoen is bijvoorbeeld in orde, 1,6 miljoen en 16 miljoen niet).
   * Reserve een controlesegment in elke testgroep van het testsegment. Op deze manier kunt u een klein deel van elk segment opzij zetten en niet expliciet in de test als doel instellen.

1. Onderzoek de resultaten:

   * Het [&#x200B; Laboratorium van de Publiek rapporteert mening &#x200B;](../../features/audience-lab/audience-lab-reporting-view.md) zal het aantal omzettingen tonen elk model drijft. Voor op conversie gebaseerde campagnes, zal het testsegment dat de meeste omzettingen drijft het model betekenen dat het best presteert.
   * Omdat u controlesegmenten hebt, kunt u ook evalueren hoe het model tegen &quot;standaard het richten.&quot;deed U test niet alleen het ene model tegenover het andere, maar test ook de vraag of dit model beter is dan normale praktijken.

## Creatieven testen op verschillende doelen {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Gebruik [!UICONTROL Audience Lab] om het aantal conversies te meten dat een creatieve toepassing gebruikt voor verschillende doelen. Met dit gebruiksgeval kunt u ook de conversies van de creatieve elementen meten aan de hand van natuurlijk voorkomende omzettingen.

1. [&#x200B; creeer een Groep van de Test van het Segment &#x200B;](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), die het segment selecteert u creatief tegen als basislijnsegment wilt testen.
1. Splits het basislijnsegment in testsegmenten en besturingssegmenten.
1. Wijs de testsegmenten aan de verschillende bestemmingen toe u wenst om te testen.
1. Het controlesegment kan worden ingehouden en niet aan om het even welke bestemming in kaart worden gebracht. Het controlesegment mag niet worden gericht op de creatieve test om een resultatenbasislijn in te stellen voor natuurlijk voorkomende omzettingen.
1. Geef een begindatum en een einddatum voor de test op.
1. Opstelling het segment en creatief in de bestemmingen.
1. Het [&#x200B; Laboratorium van de Publiek rapporteert mening &#x200B;](../../features/audience-lab/audience-lab-reporting-view.md) zal het aantal omzettingen tonen creatief over de bestemmingen drijft.
1. Omdat u een controlesegment creeerde, kunt u ook evalueren hoe creatief tegen natuurlijk optredende omzettingen deed. U test de vraag: &quot;Heeft dit creatieve project een hogere conversiesnelheid opgeleverd dan normaal?&quot;
