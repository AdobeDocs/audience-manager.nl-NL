---
description: Een doel URL maakt pixelvraag van een pagina aan uw bestemming. Volg deze instructies om een bestemming tot stand te brengen URL met de Bouwer van de Bestemming.
seo-description: Een doel URL maakt pixelvraag van een pagina aan uw bestemming. Volg deze instructies om een bestemming tot stand te brengen URL met de Bouwer van de Bestemming.
seo-title: Een URL-doel configureren
solution: Audience Manager
title: Een URL-doel configureren
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# Een URL-doel configureren {#configure-url-destination}

Een [!DNL URL] doel doet pixelvraag van een pagina aan uw bestemming. Volg deze instructies om een [!DNL URL] bestemming te creëren met [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Als u een nieuwe [!DNL URL] bestemming wilt maken, gaat u naar de volgende secties **[!UICONTROL Audience Data > Destinations > Create New Destination]** en vult u deze in.

## Basisinformatie {#basic-info}

Deze sectie bevat velden en opties waarmee het proces voor het maken van de URL-bestemming wordt gestart. Deze sectie voltooien:

1. Klik **[!UICONTROL Basic Information]** om de besturingselementen beschikbaar te maken.
2. Geef het doel een naam. Vermijd afkortingen en speciale tekens.
3. *(Optioneel)* Beschrijf de bestemming. Een beknopte beschrijving is een effectieve manier om meer informatie over een bestemming te definiëren of te verstrekken.
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. Selecteer in de **[!UICONTROL Environment]** lijst de omgeving waarin het URL-doel moet worden geactiveerd.
6. Klik in de **[!UICONTROL Type]** lijst op **[!UICONTROL URL]**.
7. *(Optioneel)* Selecteer een **[!UICONTROL Auto-fill Destination Mapping]**. De volgende opties zijn beschikbaar:
   * **[!UICONTROL Segment ID]**: Voegt automatisch segmentidentiteitskaart aan en verzendt naar de bestemming toe.
   * **[!UICONTROL Integration Code Value]**: Voegt automatisch de code van de segmentintegratie aan de bestemmingstoewijzing toe en verzendt. De integratiecode is een uniek herkenningsteken dat door de klant wordt gecreeerd en wordt gebruikt. De waarde is beperkt tot maximaal 255 tekens.
8. Klik **[!UICONTROL Next]** om naar de [!UICONTROL Configuration] instellingen te gaan of klik **[!UICONTROL Data Export Labels]** om besturingselementen voor exporteren toe te passen op de bestemming.

## Labels voor gegevensexport {#data-export-labels-dest}

Deze sectie bevat opties die de controles [van de](../../features/data-export-controls.md) gegevensuitvoer op een [!DNL URL] bestemming toepassen. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klik **[!UICONTROL Data Export Labels]** om de besturingselementen beschikbaar te maken.
2. Selecteer een label dat overeenkomt met het besturingselement voor gegevensexport dat op de bestemming wordt toegepast (zie Labels exporteren [toevoegen aan een bestemming](/help/using/features/destinations/add-data-export-labels.md) voor meer informatie).
3. Klik op **[!UICONTROL Save]**.

## Configuratie {#configure-base-data}

Deze sectie bevat opties waarmee u een basis- [!DNL URL] en gegevensscheidingstekens kunt instellen die door de [!DNL URL] tekenreeks worden doorgegeven. Deze sectie is optioneel. Deze sectie voltooien:

1. Klik **[!UICONTROL Configuration]** om de besturingselementen beschikbaar te maken.
1. *(Optioneel)* Schakel het **[!UICONTROL Serialize]** selectievakje in.
Dit laat u segmenten naar een bestemming opeenvolgend verzenden eerder dan het maken van afzonderlijke vraag voor elk segment. Serienummering helpt gegevensoverdracht efficiënt te maken. Als u dit selectievakje inschakelt, worden de velden URL en scheidingstekens weergegeven. Voor meer informatie, zie [Standaard en Serie zeer belangrijke - waardeparen](../../features/destinations/key-value-pairs.md).
1. Als u **[!UICONTROL Serialize]** deze optie selecteert, moet u ook de hieronder beschreven velden URL en scheidingsteken configureren.

| Veld | Beschrijving |
|--- |--- |
| Basis-URL | Het basisgedeelte van een standaard `HTTP` [!DNL URL] dat niet verandert. Ook, moet u de `%ALIAS%` placeholder macro [](../../features/destinations/destination-macros.md#destination-macros-defined) in basis URL plaatsen. Voorbeeld: `https://www.myCompany.com/%alias%...` |
| Beveiligde URL | Het basisgedeelte van een beveiliging `HTTPS` [!DNL URL] dat niet verandert. Ook, moet u de `%ALIAS%` placeholder macro [](../../features/destinations/destination-macros.md#destination-macros-defined) in basis URL plaatsen. Voorbeeld: `https://www.myCompany.com/%alias%...` |
| Scheidingsteken | Het symbool dat de segmentvariabelen in de [!DNL URL] tekenreeks scheidt. Dit is meestal een komma of een puntkomma. Krijg deze informatie van uw bestemmingspartner. |

## Segmenttoewijzingen {#segment-mappings}

In deze sectie kunt u zoeken naar segmenten en deze toevoegen aan uw doel. Deze sectie voltooien:

1. Klik **[!UICONTROL Segment Mappings]** om de besturingselementen beschikbaar te maken.
1. Typ in het **[!UICONTROL Search and Add Segments]** vak de naam van een segment of klik op **[!UICONTROL Browse All Segments]** Bladeren in een lijst met beschikbare segmenten.
1. Klik **[!UICONTROL Add Selected Segments]** wanneer u het segment vindt u wilt gebruiken. Als u een segment toevoegt, wordt het [!UICONTROL Edit Mapping] venster geopend.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geef de sleutelwaardeparen op die door het segment worden gebruikt.
   * **[!UICONTROL Start Date]** en **[!UICONTROL End Date]**: Kies een begin- en einddatum voor het doel. Als de einddatum leeg is, verloopt de bestemming nooit.
1. Klik op **[!UICONTROL Done]**.