---
description: In dit artikel wordt beschreven hoe publiek wordt gedeeld tussen Audience Manager en Adobe Experience Platform.
seo-description: In dit artikel wordt beschreven hoe publiek wordt gedeeld tussen Audience Manager en Adobe Experience Platform.
seo-title: Publiek delen tussen Audience Manager en Adobe Experience Platform
solution: Audience Manager
title: Publiek delen tussen Audience Manager en Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: af43becaf841909174fad097f4d4d5040c279b47

---


# Publiek delen tussen Audience Manager en Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Neem contact op met uw Adobe-vertegenwoordiger om de toegang tot deze functionaliteit te ontgrendelen.

## Overzicht {#overview}

Met de functionaliteit voor het delen van publiek tussen Audience Manager en Adobe Experience Platform kunt u de eigenschappen en segmenten van Audience Manager delen met het Adobe Experience Platform en vice versa. U hebt de [Audience Manager-aansluiting](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html) nodig om publiek delen tussen Audience Manager en Adobe Experience Platform mogelijk te maken.

U kunt de eigenschappen en de segmenten van de Manager van de Publiek in het Platform van de Ervaring gebruiken om de gegevens van de Manager van de Publiek aan uw klantenprofielen toe te voegen en van de [segmenteringsdienst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)van het Platform van de Ervaring te profiteren.

In de Manager van de Publiek, kunt u de segmenten van het Platform van de Ervaring voor de gebruiksgevallen van het Platform van het Gegevensbeheer, zoals gebruiken:
* Gegevens van [derden toevoegen](/help/using/overview/data-types-collected.md#third-party-data) aan uw segmenten;
* [Algorithmic modelling](/help/using/features/algorithmic-models/understanding-models.md);
* Activeer uw segmenten aan bestemmingen die nog niet in de de [bestemmingscatalogus](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)van het Platform van de Ervaring worden gesteund.

Daarnaast worden uw Experience Platform-segmenten gedeeld met andere Experience Cloud-oplossingen, via [Core Services](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Zie de onderstaande tabel voor een overzicht van de gebruikte gevallen voor het delen van het publiek:

| **Hoofdletters gebruiken** | **Adobe Experience Platform** | **Auditiebeheer** | **Core Services** |
---------|----------|---------|---------
| **Delen van publiek** | <ul><li>Klantprofielen verrijken met gegevens van Auditions Manager</li><li>De gegevens van de Manager van het publiek van het Gebruik in de segmentatie van het Platform van de Ervaring</li></ul> | <ul><li>Gegevens van derden toevoegen aan segmenten</li><li>Algorithmming</li><li>Activering naar andere bestemmingen</li></ul> | Gebruik de segmenten Experience Platform in andere Experience Cloud-oplossingen, zoals Adobe Target of Analytics. |

<br> 

## Segmenten en kenmerken van Auditions Manager in het Adobe Experience Platform {#aam-segments-traits-in-aep}

Uw sporen en de segmenten van de Manager van de Publiek verschijnen in het Platform van de Ervaring als **Publiek** in het segmentwerkschema. Voor meer informatie over uw segmenten en de eigenschappen van de Manager van de Publiek in het Platform van de Ervaring, zie:

* [Overzicht van segmentatieservice](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Gebruikershandleiding voor de functie Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Aansluiting Auditiebeheer](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html)

<br> 

## Segmenten voor Adobe Experience Platform in Audience Manager {#aep-segments-in-aam}

De segmenten die u in het Platform van de Ervaring creeert verschijnen in uw interface van de Manager van de Publiek als trekken en segmenten, met de volgende samenstellingsregels:
* Trait: De trekregel is identiteitskaart van het segment van het Platform van de Ervaring.
* Segment: Het segment bestaat uit de hierboven beschreven kenmerken.

### Treinen {#aep-segments-as-aam-traits}

Audience Manager maakt automatisch een taakmap met de naam **Experience Platform Traits** in de opslagruimte.

![Treinen van het dashboard van het Platform van de Ervaring](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

U kunt automatisch gemaakte kenmerken in segmenten naast andere kenmerken gebruiken. Bijvoorbeeld, kunt u eigenschappen mengen die van de segmenten van het Platform van de Ervaring met derderderderdeverrichtingen worden gecreeerd die door de Marketplace [van het](/help/using/features/audience-marketplace/audience-marketplace.md)publiek worden verworven.

Een voorbeeld van een eigenschap die automatisch van een segment van het Platform van de Ervaring wordt gecreeerd, zie hieronder het schermschot:

![Traject van ervaringsplatform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Objectnummer | Naam | Beschrijving |
---------|----------|---------
| 1 | Type overtrek | De treits die van de segmenten van het Platform van de Ervaring worden gecreeerd worden gecreeerd als ongeboete eigenschappen in de Manager van de Publiek. |
| 2 | Gegevensbron | Automatisch gemaakt. Alle kenmerken en segmenten die automatisch worden gemaakt op basis van de segmenten Experience Platform, worden opgeslagen in de gegevensbron **Adobe Experience Platform Audience Sharing**. |
| 3 | Integratiecode | De integratiecode beantwoordt aan segmentidentiteitskaart in het Platform van de Ervaring. |
| 4 | Trainingsexpressie | De expressie trait is `segID = segment ID in Experience Platform`. |
| 5 | Segmenten met dit spoor | Een automatisch gecreeerd segment dat dit bezit als zijn samenstelling gebruikt. |

<br> 

### Segmenten {#aep-segments-as-aam-segments}

Audience Manager maakt automatisch een segmentmap met de naam **Experience Platform Segments** in uw segmentopslag.

![Schermafbeelding van dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Een voorbeeld van een segment dat automatisch van een segment van het Platform van de Ervaring wordt gecreeerd, zie hieronder het schermschot:

![Schermafbeelding van segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Objectnummer | Naam | Beschrijving |
---------|----------|---------
| 1 | Integratiecode | De integratiecode beantwoordt aan segmentidentiteitskaart in het Platform van de Ervaring. |
| 2 | Gegevensbron | Automatisch gemaakt. Alle kenmerken en segmenten die automatisch worden gemaakt op basis van de segmenten Experience Platform, worden opgeslagen in de gegevensbron **Adobe Experience Platform Audience Sharing**. |
| 3 | Regel voor samenvoegen van profiel | **Het externe Beleid** van de Fusie wijst erop dat de automatisch gecreeerde segmenten de opstelling van het fusiebeleid in het Platform van de Ervaring volgen. |
| 4 | Segmentregel | Het segment bestaat uit de eigenschap die in de sectie [](#aep-segments-as-aam-traits)Traits wordt beschreven. |
