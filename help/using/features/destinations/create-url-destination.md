---
description: Een doel URL maakt pixelvraag van een pagina aan uw bestemming. Volg deze instructies om een bestemming tot stand te brengen URL met de Bouwer van de Bestemming.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Een URL-bestemming configureren
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 2%

---

# Een [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] maakt pixelaanroepen van een pagina naar uw [!DNL destination]. Volg deze instructies om een [!DNL URL] [!DNL destination] with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Een nieuwe [!DNL URL] [!DNL destination], ga naar **[!UICONTROL Audience Data > Destinations > Create New Destination]** en voltooi de hieronder beschreven secties.

## Basisinformatie {#basic-info}

Deze sectie bevat velden en opties waarmee u het dialoogvenster [!DNL URL destination] aanmaakproces. Deze sectie voltooien:

1. Klikken **[!UICONTROL Basic Information]** om de besturingselementen zichtbaar te maken.
2. Geef de naam [!DNL destination]. Vermijd afkortingen en speciale tekens.
3. *(Optioneel)* Beschrijf het [!DNL destination]. Een beknopte beschrijving is een effectieve manier om meer informatie over een [!DNL destination].
4. In de **[!UICONTROL Category]** lijst, kiest u **[!UICONTROL Custom]**.
5. In de **[!UICONTROL Environment]** Selecteer de omgeving waarin u de [!DNL URL destination].
6. In de **[!UICONTROL Type]** lijst, klikt u op **[!UICONTROL URL]**.
7. *(Optioneel)* Selecteer een **[!UICONTROL Auto-fill Destination Mapping]**. De volgende opties zijn beschikbaar:
   * **[!UICONTROL Segment ID]**: Voegt automatisch segment-id toe en verzendt deze naar [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Voegt automatisch de code van de segmentintegratie aan de bestemmingstoewijzing toe en verzendt. De integratiecode is een uniek herkenningsteken dat door de klant wordt gecreeerd en wordt gebruikt. De waarde is beperkt tot maximaal 255 tekens.
8. Klikken **[!UICONTROL Next]** om naar de [!UICONTROL Configuration] instellingen of klik op **[!UICONTROL Data Export Labels]** om uitvoercontroles toe te passen op [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Deze sectie bevat opties die van toepassing zijn [besturingselementen voor exporteren van gegevens](../../features/data-export-controls.md) een [!DNL URL] bestemming. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klikken **[!UICONTROL Data Export Labels]** om de besturingselementen zichtbaar te maken.
2. Selecteer een label dat overeenkomt met het besturingselement voor gegevensexport dat op het doel is toegepast (zie [Exportlabels toevoegen aan een doel](/help/using/features/destinations/add-data-export-labels.md) voor meer informatie).
3. Klik op **[!UICONTROL Save]**.

## Configuratie {#configure-base-data}

Deze sectie bevat opties waarmee u een basis kunt instellen [!DNL URL] en gegevensscheidingstekens die door de [!DNL URL] tekenreeks. Deze sectie is optioneel. Deze sectie voltooien:

1. Klikken **[!UICONTROL Configuration]** om de besturingselementen zichtbaar te maken.
1. *(Optioneel)* Selecteer **[!UICONTROL Serialize]** selectievakje.
Hiermee kunt u segmenten naar een [!DNL destination] opeenvolgend eerder dan het maken van afzonderlijke vraag voor elk segment. Serienummering helpt gegevensoverdracht efficiënt te maken. Als u dit selectievakje inschakelt, worden de velden URL en scheidingstekens weergegeven. Zie voor meer informatie [Standaard en seriële sleutelwaardeparen](../../features/destinations/key-value-pairs.md).
1. Als u **[!UICONTROL Serialize]** moet u ook de hieronder beschreven velden URL en delimiter configureren.

| Veld | Beschrijving |
|--- |--- |
| [!UICONTROL Base URL] | Het basisgedeelte van een norm `HTTP` [!DNL URL] dat verandert niet . Ook moet u de opdracht `%ALIAS%`  [plaatsaanduidingsmacro](../../features/destinations/destination-macros.md#destination-macros-defined) in de basis-URL. Voorbeeld: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Het basisgedeelte van een beveiligde `HTTPS` [!DNL URL] dat verandert niet . Ook moet u de opdracht `%ALIAS%`   [plaatsaanduidingsmacro](../../features/destinations/destination-macros.md#destination-macros-defined) in de basis-URL. Voorbeeld: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Het symbool dat de segmentvariabelen in het dialoogvenster [!DNL URL] tekenreeks. Dit is meestal een komma of een puntkomma. Krijg deze informatie van uw bestemmingspartner. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

In deze sectie kunt u zoeken naar segmenten en deze toevoegen aan uw [!UICONTROL destination]. Deze sectie voltooien:

1. Klikken **[!UICONTROL Segment Mappings]** om de besturingselementen zichtbaar te maken.
1. In de **[!UICONTROL Search and Add Segments]** , begint u de naam van een segment te typen of klikt u op **[!UICONTROL Browse All Segments]** Blader door een lijst met beschikbare segmenten.
1. Klikken **[!UICONTROL Add Selected Segments]** wanneer u het segment vindt u wilt gebruiken. Als u een segment toevoegt, wordt het dialoogvenster [!UICONTROL Edit Mapping] venster.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geef de sleutelwaardeparen op die door het segment worden gebruikt.
   * **[!UICONTROL Start Date]** en **[!UICONTROL End Date]**: Kies een begin- en einddatum voor de [!DNL destination]. Als de einddatum leeg is, wordt [!DNL destination] verloopt nooit.
1. Klik op **[!UICONTROL Done]**.
