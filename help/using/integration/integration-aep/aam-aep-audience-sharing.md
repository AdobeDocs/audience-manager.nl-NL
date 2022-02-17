---
description: In dit artikel wordt beschreven hoe publiek wordt gedeeld tussen Audience Manager en Adobe Experience Platform
solution: Audience Manager
title: Experience Platform segmentdelen met Audience Manager en andere Experience Cloud-oplossingen
keywords: AEP-publieksdeling, AEP-segmenten, Platform-segmenten, segmentdeling, publiek delen, deelsegmenten AAM AEP-segmentdeling
feature: Platform Integration
source-git-commit: f0df41e71340d08e873d8d7e33b481987110c58d
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 1%

---

# Experience Platform segmentdelen met Audience Manager en andere Experience Cloud-oplossingen

>[!NOTE]
>
> Neem contact op met uw Adobe-verkoper om de toegang tot deze functie te ontgrendelen.

## Overzicht {#overview}

Met de functionaliteit voor het delen van publiek tussen Audience Manager en Adobe Experience Platform kunt u uw eigenschappen en segmenten van Audience Managers delen met Adobe Experience Platform en vice versa. U hebt de [[!DNL Audience Manager Connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) om het delen van het publiek tussen Audience Manager en Adobe Experience Platform mogelijk te maken.

U kunt de Audience Manager en de segmenten in Experience Platform gebruiken om de gegevens van de Audience Manager aan uw klantenprofielen toe te voegen en van het Experience Platform te profiteren [segmenteringsservice](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md).

In Audience Manager, kunt u de segmenten van het Experience Platform voor de gebruiksgevallen van het Platform van het Beheer van Gegevens gebruiken, zoals:
* Toevoegen [gegevens van derden](/help/using/overview/data-types-collected.md#third-party-data) naar uw segmenten;
* [Algorithmming](/help/using/features/algorithmic-models/understanding-models.md);
* Activeer uw segmenten aan bestemmingen die nog niet in het Experience Platform worden gesteund [doelcatalogus](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Bovendien, worden uw Experience Platform segmenten gedeeld aan andere oplossingen van Experience Cloud, via [Core Services](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * U hebt een licentie voor Audience Managers nodig om de hierboven vermelde gebruiksgevallen van het Platform voor gegevensbeheer in te schakelen.
> * U *niet nodig* een licentie van de Audience Manager om Experience Platform-segmenten te delen met Adobe Advertising Cloud, Adobe Target, Marketo en andere Experience Cloud-oplossingen, via de Core Services-integratie.


Zie de onderstaande tabel voor een overzicht van de gebruikte gevallen voor het delen van het publiek:

| **Gebruiksscenario** | **Adobe Experience Platform** | **Audience Manager** | **Core Services** |
|---------|----------|---------|---------|
| **Delen van publiek** | <ul><li>Klantprofielen verrijken met Audience Manager-gegevens</li><li>Audience Manager-gegevens gebruiken in segmentatie van Experience Platform</li></ul> | <ul><li>Gegevens van derden toevoegen aan segmenten</li><li>Algorithmming</li><li>Activering naar andere bestemmingen</li></ul> | Gebruik Experience Platform-segmenten in andere Experience Cloud-oplossingen, zoals Adobe Target, Advertising Cloud of Marketo. |

{style=&quot;table-layout:auto&quot;}

## Audience Managers en kenmerken in Adobe Experience Platform {#aam-segments-traits-in-aep}

De eigenschappen en segmenten van uw Audience Manager worden in het Experience Platform weergegeven als **Soorten publiek** in de segmentworkflow. Voor meer informatie over uw segmenten en de eigenschappen van de Audience Manager in Experience Platform, zie:

* [Overzicht van segmentatieservice](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Gebruikershandleiding voor Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

## Adobe Experience Platform-segmenten in Audience Manager {#aep-segments-in-aam}

De segmenten die u in Experience Platform creeert verschijnen in uw interface van de Audience Manager als signalen, trekken, en segmenten, met de volgende samenstellingsregels:

* Signaal: Voor elk segment van het Experience Platform, zou u signalen in vorm moeten zien `segID = segment ID`.
* Trait: De gedragregel is identiteitskaart van het segment van het Experience Platform.
* Segment: Het segment bestaat uit de hierboven beschreven kenmerken.

### Signalen {#aep-segments-as-aam-signals}

Selecteren **[!UICONTROL Audience Data > Signals > General Online Data]** en zoeken op `SegId` om signalen te vinden die van Experience Platform binnenkomen. U kunt dit scherm voor het zuiveren doeleinden gebruiken, om te controleren of is de integratie tussen Experience Platform en Audience Manager correct opstelling.

![Zie Experience Platform signalen in Audience Manager in het dashboard van Signals](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Eigenschappen  {#aep-segments-as-aam-traits}

Audience Manager maakt automatisch een map met het kenmerk &#39;Map&#39; **Experience Platforms** in uw standaardopslag.

![Traits van het dashboard van het Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

U kunt automatisch gemaakte kenmerken in segmenten naast andere kenmerken gebruiken. Bijvoorbeeld, kunt u eigenschappen mengen die van de segmenten van het Experience Platform met derderderetuilen worden gecreeerd die door [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Zie de onderstaande schermafbeelding voor een voorbeeld van een eigenschap die automatisch wordt gemaakt van een Experience Platform-segment:

![Traject van Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Objectnummer | Naam | Beschrijving |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | De treits die van de segmenten van het Experience Platform worden gecreeerd worden gecreeerd als ongebogen eigenschappen in Audience Manager. |
| 2 | [!UICONTROL Data Source] | Automatisch gemaakt. Alle eigenschappen en segmenten die automatisch van de segmenten van het Experience Platform worden gecreeerd worden opgeslagen in de gegevensbron **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | De integratiecode beantwoordt aan segmentidentiteitskaart in Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | De uitdrukking van het kenmerk is `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Een automatisch gecreeerd segment dat dit bezit als zijn samenstelling gebruikt. |

{style=&quot;table-layout:auto&quot;}

### Segmenten  {#aep-segments-as-aam-segments}

Audience Manager maakt automatisch een segmentmap met de naam **Segmenten Experience Platform** in uw segmentopslag.

![Schermafbeelding van dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Zie de onderstaande schermafbeelding voor een voorbeeld van een segment dat automatisch wordt gemaakt van een Experience Platform-segment:

![Schermafbeelding van segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Objectnummer | Naam | Beschrijving |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | De integratiecode beantwoordt aan segmentidentiteitskaart in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatisch gemaakt. Alle eigenschappen en segmenten die automatisch van de segmenten van het Experience Platform worden gecreeerd worden opgeslagen in de gegevensbron **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** Geeft aan dat automatisch gemaakte segmenten de in Experience Platform ingestelde samenvoegbeleidsinstelling volgen. |
| 4 | [!UICONTROL Segment Rule] | Het segment bestaat uit de in het [Sectie Traits](#aep-segments-as-aam-traits). |

{style=&quot;table-layout:auto&quot;}

## Ondersteuning voor Audience Manager Data Export Control in Experience Platform {#aam-data-export-control-in-aep}

Om de naleving van het gegevensgebruik in Experience Platform af te dwingen, moeten alle toepasselijke datasets en gebieden aangewezen worden gegeven [gegevensgebruikslabels](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html). Daarnaast [beleid voor gegevensgebruik](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html) moet worden ingeschakeld voor specifieke marketingacties tegen deze labels, zoals aangegeven door de [Het kader van de Etikettering en van de Handhaving van het Gebruik van gegevens (DULE)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework).

In het publiek dat proces tussen Audience Manager en Experience Platform deelt, worden om het even welke Controles van de Uitvoer van Gegevens die op de segmenten van de Audience Manager zijn toegepast vertaald in gelijkwaardige etiketten en marketing acties die door de Governance van Gegevens van het Experience Platform worden erkend, en vice versa.

>[!NOTE]
>
>Voor meer algemene informatie over de Controles van de Uitvoer van Gegevens, gelieve te verwijzen naar [Documentatie over exportfuncties](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>Dit document verstrekt een verwijzing voor hoe de specifieke Controles van de Uitvoer van de Gegevens van de Audience Manager aan de etiketten van het gegevensgebruik en marketing acties in Platform in kaart brengen.

### Besturingselementen voor gegevensexport naar labels voor gegevensgebruik

De volgende lijst schetst hoe de specifieke Controles van de Uitvoer van Gegevens aan erkende etiketten van het gegevensgebruik in kaart brengen:

| Besturingselement voor exporteren van gegevens | Label voor gegevensgebruik |
| --- | --- |
| Kan niet worden gebruikt met persoonlijk identificeerbare informatie | C3: Gegevens kunnen niet worden gecombineerd of anderszins worden gebruikt met rechtstreeks identificeerbare informatie |
| Kan niet worden gebruikt voor offsite advertentie | C5: Gegevens kunnen niet worden gebruikt voor op rente gebaseerde, cross-site gerichte adressering van inhoud of advertenties |
| Kan niet gebruiken voor onsite advertentie | C6: Gegevens kunnen niet worden gebruikt voor on-site en doelgericht |
| Kan niet worden gebruikt voor onsite personalisatie | C7: Gegevens kunnen niet worden gebruikt voor het on-site maken van inhoud |

{style=&quot;table-layout:auto&quot;}

### Besturingselementen voor gegevensexport naar marketingacties

In de volgende tabel wordt aangegeven hoe specifieke gegevensuitvoerlabels worden toegewezen aan erkende marketingacties:

| Label voor gegevensexport | Handeling |
| --- | --- |
| Deze bestemming kan een combinatie met persoonlijk identificeerbare informatie (PII) toelaten | Combineren met PII |
| Deze bestemming kan voor off-site en het richten worden gebruikt | Secundaire doelen voor meerdere sites |
| Deze bestemming kan worden gebruikt voor on-site en doelgericht | Onsite reclame |
| Deze bestemming kan voor onsite en verpersoonlijking worden gebruikt | Onsite personalisatie |

{style=&quot;table-layout:auto&quot;}

## Begrijp de verschillen van de segmentpopulatie tussen Audience Manager en Experience Platform {#aep-aam-segment-population-differences}

De de bevolkingsaantallen van het segment kunnen tussen uw Audience Manager en Experience Platform segmenten variëren. Hoewel segmentnummers voor vergelijkbare of identieke doelgroepen dicht bij elkaar moeten liggen, kunnen verschillen in populaties het gevolg zijn van de hieronder vermelde factoren.

### Segmentbeoordeling in Experience Platform

Audience Manager werkt rapportaantallen in de interface eens per dag bij.   De timing van deze update richt zich zelden op de tijd van de segmentevaluatie in Experience Platform.

### Verschillen tussen de Regels van de Fusie van het Profiel en het Beleid van de Fusie

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager en [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) in Experience Platform werken verschillend, en de identiteitsgrafiek die voor elk wordt gebruikt varieert. Hierdoor worden enkele verschillen tussen segmentpopulaties verwacht.

### Segmentsamenstelling in Experience Platform

De integratie tussen Adobe Experience Platform en Audience Manager is volgens een aantal normen [naamruimten](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) voor alle klanten: ECID, IDFA, GAID, gehashte e-mailadressen (EMAIL_LC_SHA256), AdCloud-id. Als in uw Experience Platform-segmenten een van deze profielen wordt gebruikt als primaire identiteit voor de gekwalificeerde profielen, worden de profielen geteld in de kenmerken en segmenten van de Audience Manager.

>[!NOTE]
>
> Soorten publiek in Experience Platform met identiteiten die rauwe e-mails afspelen, komen nooit voor in de Audience Manager.

Bijvoorbeeld, als u een segment van het Experience Platform &quot;Al mijn klanten&quot;had, en de gekwalificeerde profielen CRM IDs, ECID, IDFA, ruwe en gehashed e-mailadressen waren, zou het overeenkomstige segment in Audience Manager slechts profielen omvatten die van ECID, IDFA, en gehakt e-mailadressen worden afgeveegd. De segmentpopulatie in Audience Manager zou kleiner zijn dan die in Experience Platform.

![Experience Platform tot delen van Audience Manager - segmentcompositie](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Overzicht van segmentatieservice](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Gebruikershandleiding voor Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

