---
description: Leer hoe u gegevensdeling inschakelt en hoe publiek wordt gedeeld tussen Audience Manager en Adobe Experience Platform
solution: Audience Manager
title: Experience Platform-segmentdeling met Audience Manager en andere Experience Cloud-oplossingen
keywords: AEP-publiek delen, AEP-segmenten, platformsegmenten, delen van segmenten, publiek delen, deelsegmenten, AAM AEP-segment delen
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 0%

---

# Experience Platform-segmentdeling met Audience Manager en andere Experience Cloud-oplossingen

## Overzicht {#overview}

Met de functionaliteit voor het delen van publiek tussen Audience Manager en Adobe Experience Platform kunt u uw Audience Manager-kenmerken en -segmenten delen met Adobe Experience Platform- en Experience Platform-segmenten naar Audience Manager.

U hebt [[!DNL Audience Manager source connector] ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) en [ het 3&rbrace; doel van het publiek van Experience Cloud &lbrace;in Experience Platform nodig om publiek toe te laten delend tussen Audience Manager en Adobe Experience Platform.](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html)

U kunt de eigenschappen en de segmenten van Audience Manager in Experience Platform gebruiken om de gegevens van Audience Manager aan uw klantenprofielen toe te voegen en van de Experience Platform [ segmenteringsdienst ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en) te profiteren.

In Audience Manager kunt u Experience Platform-segmenten gebruiken voor gegevensbeheerplatform, zoals:
* Voeg [ derdegegevens ](/help/using/overview/data-types-collected.md#third-party-data) aan uw segmenten toe;
* [ Algorithmic modelling ](/help/using/features/algorithmic-models/understanding-models.md);
* Activeer uw segmenten aan bestemmingen die nog niet in de Experience Platform [ bestemmingscatalogus ](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html) worden gesteund.

Bovendien, worden uw segmenten van Experience Platform gedeeld aan andere oplossingen van Experience Cloud, via [ Diensten van de Kern ](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * U hebt een Audience Manager-licentie nodig om de hierboven vermelde gevallen van gegevensbeheerplatform in te schakelen.
> * U *hebt* geen vergunning van Audience Manager nodig om de segmenten van Experience Platform met de Wolk van de Reclame van Adobe, Adobe Target, Marketo, en andere oplossingen van Experience Cloud, via de integratie van de Diensten van de Kern te delen.

Zie de onderstaande tabel voor een overzicht van de gebruikte gevallen voor het delen van het publiek:

| **Geval van het Gebruik** | **Adobe Experience Platform** | **Audience Manager** | **de Diensten van de Kern** |
|---------|----------|---------|---------|
| **het Delen van het publiek** | <ul><li>Klantprofielen verrijken met Audience Manager-gegevens</li><li>Audience Manager-gegevens gebruiken in Experience Platform-segmentatie</li></ul> | <ul><li>Gegevens van derden toevoegen aan segmenten</li><li>Algorithmming</li><li>Activering naar andere bestemmingen</li></ul> | Gebruik Experience Platform-segmenten in andere Experience Cloud-oplossingen, zoals Adobe Target, Advertising Cloud of Marketo. |

{style="table-layout:auto"}

## Audience Manager-segmenten en -kenmerken in Adobe Experience Platform {#aam-segments-traits-in-aep}

In de volgende secties wordt beschreven hoe u het delen van gegevens van Audience Manager naar Experience Platform kunt inschakelen en hoe u Audience Manager-kenmerken en -segmenten in Experience Platform kunt gebruiken.

### Delen van gegevens van Audience Manager naar Experience Platform inschakelen {#enable-aam-to-aep-data}

Als u segmenten en traits van Audience Manager naar Experience Platform wilt verzenden, moet u de Audience Manager-bronconnector instellen in de Experience Platform-broncatalogus. Dit is een workflow voor zelfbediening waarvoor geen betrokkenheid van de Adobe Customer Care- of engineeringteams vereist is. U kunt als volgt de Audience Manager-bronaansluiting instellen:

* [ bron van Audience Manager ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [ creeer een Adobe Audience Manager bronverbinding in UI ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe raadt klanten aan de verbinding te configureren zonder de opties **[!UICONTROL Select all segments]** en **[!UICONTROL Select all traits]** te selecteren, zoals hieronder wordt weergegeven. De opname van grote Audience Manager-segmentpopulaties heeft een directe invloed op het totale aantal profielen wanneer u eerst een Audience Manager-segment naar Platform verzendt met de Audience Manager-bron. Dit betekent dat het selecteren van alle segmenten kan leiden tot een aantal profielen dat groter is dan uw gebruiksrechten voor licenties.
>
>![ Schermafbeelding die de Select all segments en Select all traits options uncheck in the workflow weergeeft om verbinding te maken met de Audience Manager source-connector.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Audience Manager-kenmerken en -segmenten gebruiken in Experience Platform {#use-aam-data-in-aep}

Na vestiging de bron van Audience Manager schakelaar om sporen en segmenten van Audience Manager in te voeren, verschijnen uw gegevens van Audience Manager in Experience Platform als **Soorten publiek** in het segmentwerkschema. Lees voor meer informatie over uw Audience Manager-segmenten en -kenmerken in Experience Platform:

* [ overzicht van de Dienst van de Segmentatie ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [ Experience Platform Segment Builder gebruikersgids ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Adobe Experience Platform-segmenten in Audience Manager {#aep-segments-in-aam}

In de volgende secties wordt beschreven hoe u het delen van gegevens van Experience Platform naar Audience Manager kunt inschakelen en hoe u Experience Platform-segmenten in Audience Manager kunt gebruiken.

### Delen van gegevens van Experience Platform naar Audience Manager inschakelen {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> In deze sectie wordt de integratie beschreven van Experience Platform tot Audience Manager voor het delen van oudere segmenten. U kunt deze integratie nu instellen zonder ondersteuning van Adobe-vertegenwoordigers voor klanten. Voor meer informatie, lees de [ bestemmingsdocumentatie van het publiek 0&rbrace; Experience Cloud.](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html)

>[!NOTE]
>
> Neem contact op met de Adobe Customer Success Manager of Customer Care om de toegang tot deze functionaliteit te ontgrendelen.

Als u segmenten van Experience Platform naar Audience Manager wilt verzenden, dient u contact op te nemen met de klantenservice of met de Customer Success Manager. De teams van de Zorg van de Klant en het Beheer van de Steun van de Klant moeten een kaartje (zie malplaatjekaartje AAM-52354) indienen om de verbinding van Platform aan Audience Manager toe te laten.

Zorg ervoor dat u plannen deelt voor de gegevensoverdracht van Platform naar Audience Manager om ervoor te zorgen dat de verbinding correct is ingesteld. Als u bijvoorbeeld regionale gegevens wilt delen voor segmenten die naar Adobe Target worden verzonden, moet deze informatie in het ticket worden vermeld. De verbinding voor het uitwisselen van gegevens tussen Experience Platform en Audience Manager wordt tot stand gebracht binnen zes werkdagen na de indiening van het verzoek.

### Experience Platform-segmenten gebruiken in Audience Manager {#use-aep-data-in-aam}

De segmenten die u in Experience Platform creeert verschijnen in uw interface van Audience Manager als signalen, trekken, en segmenten, met de volgende samenstellingsregels:

* Signal: Voor elk Experience Platform-segment worden de signalen in de vorm `segID = segment ID` weergegeven.
* Trait: De regel trait is de ID van het Experience Platform-segment.
* Segment: Het segment bestaat uit de hierboven beschreven kenmerken.

### Signalen {#aep-segments-as-aam-signals}

Selecteer **[!UICONTROL Audience Data > Signals > General Online Data]** en zoek op `SegId` om signalen te zoeken die vanuit Experience Platform binnenkomen. U kunt dit scherm gebruiken voor foutopsporingsdoeleinden om te controleren of de integratie tussen Experience Platform en Audience Manager correct is ingesteld.

![ zie de signalen van Experience Platform in Audience Manager in het dashboard van Signalen ](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Treinen {#aep-segments-as-aam-traits}

Audience Manager leidt automatisch tot een trekomslag genoemd **de Beetjes van Experience Platform** in uw dienstafopslag.

![ Treinen van het dashboard van Experience Platform ](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

U kunt automatisch gemaakte kenmerken in segmenten naast andere kenmerken gebruiken. Bijvoorbeeld, kunt u eigenschappen mengen die van de segmenten van Experience Platform met derderderdeverrichtingen worden gecreeerd die door [ Audience Marketplace ](/help/using/features/audience-marketplace/audience-marketplace.md) worden verworven.

Zie de onderstaande schermafbeelding voor een voorbeeld van een kenmerk dat automatisch wordt gemaakt van een Experience Platform-segment:

![ Spoor van Experience Platform ](/help/using/integration/integration-aep/assets/aep-trait.png)


| Objectnummer | Naam | Beschrijving |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Traits die op basis van Experience Platform-segmenten worden gemaakt, worden in Audience Manager gemaakt als onbemande traits. |
| 2 | [!UICONTROL Data Source] | Automatisch gemaakt. Alle kenmerken en segmenten die automatisch worden gemaakt op basis van Experience Platform-segmenten, worden opgeslagen in de gegevensbron **[!UICONTROL Adobe Experience Platform Audience Sharing]** . |
| 3 | [!UICONTROL Integration Code] | De integratiecode komt overeen met de segment-id in Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | De expressie trait is `segID = segment ID in Experience Platform` . |
| 5 | [!UICONTROL Segments with this Trait] | Een automatisch gecreeerd segment dat dit bezit als zijn samenstelling gebruikt. |

{style="table-layout:auto"}

### Segmenten {#aep-segments-as-aam-segments}

Audience Manager leidt automatisch tot een segmentomslag genoemd **Segmenten van Experience Platform** in uw segmentopslag.

![ Schermafbeelding van dashboard ](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Zie de onderstaande schermafbeelding voor een voorbeeld van een segment dat automatisch is gemaakt van een Experience Platform-segment:

![ Schermafbeelding van segment ](/help/using/integration/integration-aep/assets/aep-segment.png)

| Objectnummer | Naam | Beschrijving |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | De integratiecode komt overeen met de segment-id in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatisch gemaakt. Alle kenmerken en segmenten die automatisch worden gemaakt op basis van Experience Platform-segmenten, worden opgeslagen in de gegevensbron **[!DNL Adobe Experience Platform Audience Sharing]** . |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** geeft aan dat automatisch gemaakte segmenten het samenvoegbeleid volgen dat in Experience Platform is ingesteld. |
| 4 | [!UICONTROL Segment Rule] | Het segment bestaat uit het bezit dat in de [ sectie van Tanden ](#aep-segments-as-aam-traits) wordt beschreven. |

{style="table-layout:auto"}

## Ondersteuning voor Audience Manager Data Export Control in Experience Platform {#aam-data-export-control-in-aep}

Om de naleving van het gegevensgebruik in Experience Platform af te dwingen, moeten alle toepasselijke datasets en de gebieden aangewezen [ etiketten van het gegevensgebruik ](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html) worden gegeven. Bovendien [ beleid van het gegevensgebruik ](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html) moet voor specifieke marketing acties tegen die etiketten worden toegelaten, zoals die door het [ de Etikettering en de Handhaving van het Gebruik van Gegevens (DULE) kader ](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework) worden geschetst.

In het proces voor het delen van het publiek tussen Audience Manager en Experience Platform worden alle gegevensexportcontroles die zijn toegepast op Audience Manager-segmenten, vertaald naar equivalente labels en marketingacties die worden erkend door Experience Platform Data Governance, en andersom.

>[!NOTE]
>
>Voor meer algemene informatie over de Controles van de Uitvoer van Gegevens, gelieve te verwijzen naar de [ documentatie van de Controles van de Uitvoer van Gegevens ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>Dit document verstrekt een verwijzing voor hoe de specifieke Controles van de Uitvoer van Gegevens van Audience Manager aan de etiketten van het gegevensgebruik en marketing acties in Platform in kaart brengen.

### Besturingselementen voor gegevensexport naar labels voor gegevensgebruik

De volgende lijst schetst hoe de specifieke Controles van de Uitvoer van Gegevens aan erkende etiketten van het gegevensgebruik in kaart brengen:

| Besturing van gegevensuitvoer | Label voor gegevensgebruik |
| --- | --- |
| Kan niet worden gebruikt met persoonlijk identificeerbare informatie | C3: Gegevens kunnen niet worden gecombineerd of anderszins worden gebruikt met rechtstreeks identificeerbare informatie |
| Kan niet worden gebruikt voor offsite advertentie | C5: gegevens kunnen niet worden gebruikt voor het maken van interlokale, intersite doelwitten op inhoud of advertenties |
| Kan niet worden gebruikt voor onsite advertentie | C6: gegevens kunnen niet worden gebruikt voor on-site advertenties |
| Kan niet worden gebruikt voor onsite personalisatie | C7: gegevens kunnen niet worden gebruikt voor het ter plaatse richten van inhoud |

{style="table-layout:auto"}

### Besturingselementen voor gegevensexport naar marketingacties

In de volgende tabel wordt aangegeven hoe specifieke gegevensuitvoerlabels worden toegewezen aan erkende marketingacties:

| Label voor gegevensexport | Handeling |
| --- | --- |
| Deze bestemming kan een combinatie met persoonlijk identificeerbare informatie (PII) toelaten | Combineren met PII |
| Deze bestemming kan voor off-site en het richten worden gebruikt | Secundaire doelen voor meerdere sites |
| Deze bestemming kan worden gebruikt voor on-site en doelgericht | Onsite Advertising |
| Deze bestemming kan voor onsite en verpersoonlijking worden gebruikt | Onsite Personalization |

{style="table-layout:auto"}

## Begrijp de verschillen van de segmentpopulatie tussen Audience Manager en Experience Platform {#aep-aam-segment-population-differences}

De aantallen van de segmentbevolking kunnen tussen uw segmenten van Audience Manager en van Experience Platform variëren. Hoewel de segmentnummers voor vergelijkbare of identieke doelgroepen dicht bij elkaar moeten liggen, kunnen verschillen in populaties het gevolg zijn van de hieronder vermelde factoren.

### Segmentbeoordeling in Experience Platform

Audience Manager werkt de rapportnummers in de interface eenmaal per dag bij. De timing van deze update wordt zelden afgestemd op de tijd van de segmentbeoordeling in Experience Platform.

### Verschillen tussen de Regels van de Fusie van het Profiel en het Beleid van de Fusie

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager en [[!UICONTROL Merge Policies] ](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) in Experience Platform werken verschillend, en de identiteitsgrafiek die voor elk wordt gebruikt varieert. Hierdoor worden enkele verschillen tussen segmentpopulaties verwacht.

>[!NOTE]
>
> Wanneer het delen van segmenten van Experience Platform aan Audience Manager, neemt uw organisatie van het Platform [ standaardsamenvoegbeleid ](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) belangrijkheid over het [ fusiebeleid dat door het segment ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) wordt gebruikt met Audience Manager wordt gedeeld. Bijvoorbeeld, als het de fusiebeleid van het gedeelde segment voor [ identiteitskaart het stitching ](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure) toestaat, maar het standaard van de organisatie fusiebeleid niet, zou dit in populatieverschillen tussen Platform en Audience Manager kunnen resulteren.

### Segmentsamenstelling in Experience Platform

De integratie tussen Adobe Experience Platform en Audience Manager deelt een aantal standaard [ identiteitsnamespaces ](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) voor alle klanten: ECID, IDFA, GAID, gehakt e-mailadressen (EMAIL_LC_SHA256), identiteitskaart AdCloud Als in uw Experience Platform-segmenten een van deze profielen wordt gebruikt als primaire identiteit voor de gekwalificeerde profielen, worden de profielen geteld in Audience Manager-kenmerken en -segmenten.

>[!NOTE]
>
> Soorten publiek in Experience Platform met identiteiten die rauwe e-mails afspelen, komen nooit voor in Audience Manager.

Als u bijvoorbeeld een Experience Platform-segment &quot;Al mijn klanten&quot; had en de gekwalificeerde profielen CRM-id&#39;s, ECID, IDFA, Raw- en hashed-e-mailadressen waren, zou het bijbehorende segment in Audience Manager alleen profielen bevatten die zijn afgesloten met ECID-, IDFA- en gehashte e-mailadressen. De segmentpopulatie in Audience Manager zou kleiner zijn dan die in Experience Platform.

![ Experience Platform aan het segment dat van Audience Manager - segmentsamenstelling deelt ](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [ overzicht van de Dienst van de Segmentatie ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [ Experience Platform Segment Builder gebruikersgids ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [ Verbinding van Audience Manager ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
