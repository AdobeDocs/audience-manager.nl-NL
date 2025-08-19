---
description: Een doel URL maakt pixelvraag van een pagina aan uw bestemming. Volg deze instructies om een bestemming tot stand te brengen URL met de Bouwer van de Bestemming.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Een URL-doel configureren
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Een [!DNL URL Destination] configureren {#configure-url-destination}

Een [!DNL URL destination] maakt pixelaanroepen van een pagina naar uw [!DNL destination] . Volg deze instructies om een [!DNL URL] [!DNL destination] with [!UICONTROL Destination Builder] -object te maken.

<!-- create-url-destination.xml -->

Als u een nieuwe [!DNL URL] [!DNL destination] wilt maken, gaat u naar **[!UICONTROL Audience Data > Destinations > Create New Destination]** en vult u de secties in zoals hieronder beschreven.

## Basisinformatie {#basic-info}

Deze sectie bevat velden en opties waarmee het maken van [!DNL URL destination] wordt gestart. Deze sectie voltooien:

1. Klik op **[!UICONTROL Basic Information]** om de besturingselementen weer te geven.
2. Geef de [!DNL destination] een naam. Vermijd afkortingen en speciale tekens.
3. *(Facultatief)* beschrijf [!DNL destination]. Een beknopte beschrijving is een effectieve manier om meer informatie over een [!DNL destination] te definiëren of te verschaffen.
4. Kies **[!UICONTROL Category]** in de lijst **[!UICONTROL Custom]** .
5. Selecteer in de lijst **[!UICONTROL Environment]** de omgeving waarin de [!DNL URL destination] moet worden geactiveerd.
6. Klik in de lijst **[!UICONTROL Type]** op **[!UICONTROL URL]** .
7. *(Optioneel)* Selecteer een **[!UICONTROL Auto-fill Destination Mapping]** . U kunt onder andere de volgende opties kiezen:
   * **[!UICONTROL Segment ID]**: hiermee wordt de segment-id automatisch toegevoegd en verzonden naar de [!DNL destination] .
   * **[!UICONTROL Integration Code Value]**: voegt automatisch de code van de segmentintegratie toe en verzendt naar de bestemmingstoewijzing. De integratiecode is een uniek herkenningsteken dat door de klant wordt gecreeerd en wordt gebruikt. De waarde is beperkt tot maximaal 255 tekens.
8. Klik op **[!UICONTROL Next]** om naar de instellingen van [!UICONTROL Configuration] te gaan of klik op **[!UICONTROL Data Export Labels]** om besturingselementen voor exporteren toe te passen op de [!DNL destination] .

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Deze sectie bevat opties die [ de controles van de gegevensuitvoer ](../../features/data-export-controls.md) op een [!DNL URL] bestemming toepassen. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klik op **[!UICONTROL Data Export Labels]** om de besturingselementen weer te geven.
2. Selecteer een etiket dat aan de controle beantwoordt van de gegevensuitvoer die op de bestemming wordt toegepast (zie [ de Etiketten van de Uitvoer aan een Bestemming ](/help/using/features/destinations/add-data-export-labels.md) voor details toevoegen).
3. Klik op **[!UICONTROL Save]**.

## Configuratie {#configure-base-data}

Deze sectie bevat opties waarmee u een basis [!DNL URL] en gegevensscheidingstekens kunt instellen die door de [!DNL URL] -tekenreeks worden doorgegeven. Deze sectie is optioneel. Deze sectie voltooien:

1. Klik op **[!UICONTROL Configuration]** om de besturingselementen weer te geven.
1. *(Optioneel)* Selecteer het selectievakje **[!UICONTROL Serialize]** .
Hierdoor kunt u segmenten opeenvolgend naar een [!DNL destination] verzenden in plaats van afzonderlijke aanroepen voor elk segment te maken. Serienummering helpt gegevensoverdracht efficiënt te maken. Als u dit selectievakje inschakelt, worden de velden URL en scheidingstekens weergegeven. Voor meer informatie, zie [ Standaard en Serie zeer belangrijke - waardeparen ](../../features/destinations/key-value-pairs.md).
1. Als u **[!UICONTROL Serialize]** selecteert, moet u ook de hieronder beschreven velden URL en scheidingsteken configureren.

| Veld | Beschrijving |
|--- |--- |
| [!UICONTROL Base URL] | Het basisgedeelte van een standaard `HTTP` [!DNL URL] dat niet wordt gewijzigd. Ook, moet u `%ALIAS%` [ placeholder macro ](../../features/destinations/destination-macros.md#destination-macros-defined) in de basis URL plaatsen. Voorbeeld: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Het basisgedeelte van een beveiligde `HTTPS` [!DNL URL] dat niet wordt gewijzigd. Ook moet u de `%ALIAS%`   [ placeholder macro ](../../features/destinations/destination-macros.md#destination-macros-defined) in basis URL. Voorbeeld: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Het symbool dat de segmentvariabelen in de tekenreeks [!DNL URL] scheidt. Dit is meestal een komma of een puntkomma. Krijg deze informatie van uw bestemmingspartner. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

In deze sectie kunt u zoeken naar segmenten en deze toevoegen aan uw [!UICONTROL destination] . Deze sectie voltooien:

1. Klik op **[!UICONTROL Segment Mappings]** om de besturingselementen weer te geven.
1. Typ in het vak **[!UICONTROL Search and Add Segments]** de naam van een segment of klik op **[!UICONTROL Browse All Segments]** om door een lijst met beschikbare segmenten te bladeren.
1. Klik op **[!UICONTROL Add Selected Segments]** wanneer u het gewenste segment vindt. Als u een segment toevoegt, wordt het venster [!UICONTROL Edit Mapping] geopend.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: geef de sleutelwaardeparen op die door het segment worden gebruikt.
   * **[!UICONTROL Start Date]** en **[!UICONTROL End Date]**: kies een begin- en einddatum voor de [!DNL destination] . Als de einddatum leeg is, verloopt het object [!DNL destination] nooit.
1. Klik op **[!UICONTROL Done]**.
