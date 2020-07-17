---
description: In dit artikel wordt beschreven hoe publiek wordt gedeeld tussen Audience Manager en Adobe Experience Platform.
seo-description: In dit artikel wordt beschreven hoe publiek wordt gedeeld tussen Audience Manager en Adobe Experience Platform.
seo-title: Doelgroepen delen tussen Audience Manager en Adobe Experience Platform
solution: Audience Manager
title: Doelgroepen delen tussen Audience Manager en Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 3%

---


# Doelgroepen delen tussen Audience Manager en Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Neem contact op met uw Adobe-vertegenwoordiger om de toegang tot deze functionaliteit te ontgrendelen.

## Overzicht {#overview}

De publiek delende functionaliteit tussen Audience Manager en Adobe Experience Platform staat u toe om uw eigenschappen en segmenten van de Audience Manager aan Adobe Experience Platform en vice versa te delen. U hebt de Schakelaar [van de](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) Audience Manager nodig om publiek toe te laten delend tussen Audience Manager en Adobe Experience Platform.

U kunt de eigenschappen en de segmenten van de Audience Manager in Experience Platform gebruiken om de gegevens van de Audience Manager aan uw klantenprofielen toe te voegen en van de dienst [van de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)segmentatie van het Experience Platform te profiteren.

In Audience Manager, kunt u de segmenten van het Experience Platform voor de gebruiksgevallen van het Platform van het Beheer van Gegevens gebruiken, zoals:
* Gegevens van [derden toevoegen](/help/using/overview/data-types-collected.md#third-party-data) aan uw segmenten;
* [Algorithmic modelling](/help/using/features/algorithmic-models/understanding-models.md);
* Activeer uw segmenten aan bestemmingen die nog niet in de [bestemmingscatalogus](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)van het Experience Platform worden gesteund.

Bovendien worden uw Experience Platforms segmenten gedeeld met andere Experience Cloud-oplossingen, via [Core Services](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Zie de onderstaande tabel voor een overzicht van de gebruikte gevallen voor het delen van het publiek:

| **Gebruiksscenario** | **Adobe Experience Platform** | **Audience Manager** | **Core Services** |
---------|----------|---------|---------
| **Delen van publiek** | <ul><li>Klantprofielen verrijken met Audience Manager-gegevens</li><li>Audience Manager-gegevens gebruiken in segmentatie van Experience Platform</li></ul> | <ul><li>Gegevens van derden toevoegen aan segmenten</li><li>Algorithmming</li><li>Activering naar andere bestemmingen</li></ul> | Gebruik Experience Platform-segmenten in andere Experience Cloud-oplossingen, zoals Adobe Target of Analytics. |

<br> 

## Audience Managers en kenmerken in Adobe Experience Platform {#aam-segments-traits-in-aep}

Uw sporen en de segmenten van de Audience Manager verschijnen in Experience Platform als **Publiek** in het segmentwerkschema. Voor meer informatie over uw segmenten en de eigenschappen van de Audience Manager in Experience Platform, zie:

* [Overzicht van segmentatieservice](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Gebruikershandleiding voor Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Adobe Experience Platforms segmenten in Audience Manager {#aep-segments-in-aam}

De segmenten die u in Experience Platform creeert verschijnen in uw interface van de Audience Manager als trekken en segmenten, met de volgende samenstellingsregels:
* Trait: De gedragregel is identiteitskaart van het segment van het Experience Platform.
* Segment: Het segment bestaat uit de hierboven beschreven kenmerken.

### Eigenschappen {#aep-segments-as-aam-traits}

Audience Manager maakt automatisch een map met het kenmerk **Experience Platforms** in de opslagruimte.

![Traits van het dashboard van het Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

U kunt automatisch gemaakte kenmerken in segmenten naast andere kenmerken gebruiken. U kunt bijvoorbeeld kenmerken die zijn gemaakt op basis van Experience Platform-segmenten, combineren met externe transacties die zijn aangeschaft via de [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Zie de onderstaande schermafbeelding voor een voorbeeld van een eigenschap die automatisch wordt gemaakt van een Experience Platform-segment:

![Traject van Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Objectnummer | Naam | Beschrijving |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | De treits die van de segmenten van het Experience Platform worden gecreeerd worden gecreeerd als ongebogen eigenschappen in Audience Manager. |
| 2 | [!UICONTROL Data Source] | Automatisch gemaakt. Alle eigenschappen en segmenten die automatisch van de segmenten van het Experience Platform worden gecreeerd worden opgeslagen in de gegevensbron **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | De integratiecode beantwoordt aan segmentidentiteitskaart in Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | De expressie trait is `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Een automatisch gecreeerd segment dat dit bezit als zijn samenstelling gebruikt. |

<br> 

### Segmenten {#aep-segments-as-aam-segments}

Audience Manager leidt automatisch tot een segmentomslag genoemd de Segmenten **van het** Experience Platform in uw segmentopslag.

![Schermafbeelding van dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Zie de onderstaande schermafbeelding voor een voorbeeld van een segment dat automatisch wordt gemaakt van een Experience Platform-segment:

![Schermafbeelding van segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Objectnummer | Naam | Beschrijving |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | De integratiecode beantwoordt aan segmentidentiteitskaart in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatisch gemaakt. Alle eigenschappen en segmenten die automatisch van de segmenten van het Experience Platform worden gecreeerd worden opgeslagen in de gegevensbron **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** Geeft aan dat automatisch gemaakte segmenten de in Experience Platform ingestelde samenvoegbeleidsinstelling volgen. |
| 4 | [!UICONTROL Segment Rule] | Het segment bestaat uit de eigenschap die in de sectie [](#aep-segments-as-aam-traits)Traits wordt beschreven. |

## Ondersteuning voor Audience Manager Data Export Control in Experience Platform {#aam-data-export-control-in-aep}

Om de naleving van het gegevensgebruik in Experience Platform af te dwingen, moeten alle toepasselijke datasets en gebieden de aangewezen etiketten [van het](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)gegevensgebruik worden gegeven. Daarnaast moet het beleid [voor](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) gegevensgebruik worden ingeschakeld voor specifieke marketingacties tegen deze labels, zoals wordt beschreven in het kader [voor](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)gegevensgebruikslabels en -handhaving (DULE).

In het publiek dat proces tussen Audience Manager en Experience Platform deelt, worden om het even welke Controles van de Uitvoer van Gegevens die op de segmenten van de Audience Manager zijn toegepast vertaald in gelijkwaardige etiketten en marketing acties die door de Governance van Gegevens van het Experience Platform worden erkend, en vice versa.

>[!NOTE] Voor meer algemene informatie over de Controles van de Uitvoer van Gegevens, gelieve te verwijzen naar de documentatie [van de Controles van de Uitvoer van](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)Gegevens.
Dit document verstrekt een verwijzing voor hoe de specifieke Controles van de Uitvoer van de Gegevens van de Audience Manager aan de etiketten van het gegevensgebruik en marketing acties in Platform in kaart brengen.

### Besturingselementen voor gegevensexport naar labels voor gegevensgebruik

De volgende lijst schetst hoe de specifieke Controles van de Uitvoer van Gegevens aan erkende etiketten van het gegevensgebruik in kaart brengen:

| Besturingselement voor exporteren van gegevens | Label voor gegevensgebruik |
| --- | --- |
| Kan niet worden gebruikt met persoonlijk identificeerbare informatie | C3: Gegevens kunnen niet worden gecombineerd of anderszins worden gebruikt met rechtstreeks identificeerbare informatie |
| Kan niet worden gebruikt voor offsite advertentie | C5: Gegevens kunnen niet worden gebruikt voor op rente gebaseerde, cross-site gerichte adressering van inhoud of advertenties |
| Kan niet gebruiken voor onsite advertentie | C6: Gegevens kunnen niet worden gebruikt voor on-site en doelgericht |
| Kan niet worden gebruikt voor onsite personalisatie | C7: Gegevens kunnen niet worden gebruikt voor het on-site maken van inhoud |

### Besturingselementen voor gegevensexport naar marketingacties

In de volgende tabel wordt aangegeven hoe specifieke gegevensuitvoerlabels worden toegewezen aan erkende marketingacties:

| Label voor gegevensexport | Handeling |
| --- | --- |
| Deze bestemming kan een combinatie met persoonlijk identificeerbare informatie (PII) toelaten | Combineren met PII |
| Deze bestemming kan voor off-site en het richten worden gebruikt | Secundaire doelen voor meerdere sites |
| Deze bestemming kan worden gebruikt voor on-site en doelgericht | Onsite reclame |
| Deze bestemming kan voor onsite en verpersoonlijking worden gebruikt | Onsite personalisatie |

## Begrijp de verschillen van de segmentpopulatie tussen Audience Manager en Experience Platform

De de bevolkingsaantallen van het segment kunnen tussen uw Audience Manager en Experience Platform segmenten variëren. Hoewel segmentnummers voor vergelijkbare of identieke doelgroepen dicht bij elkaar moeten liggen, kunnen verschillen in populaties het gevolg zijn van:

* Segmentatietaken worden uitgevoerd. Audience Manager stelt een segmentatietaak in werking die de aantallen in de interface eens per dag bijwerkt. Deze baan richt zich zelden op de segmentatietaken in Experience Platform.
* [De Regels](/help/using/features/profile-merge-rules/merge-rules-overview.md) van de Fusie van het profiel in Audience Manager en het Beleid [van de](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) Fusie in Experience Platform werken verschillend, en de identiteitsgrafiek die voor elk wordt gebruikt varieert. Hierdoor worden enkele verschillen tussen segmentpopulaties verwacht.

>[!MORELIKETHIS]
>
>* [Overzicht van segmentatieservice](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Gebruikershandleiding voor Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)