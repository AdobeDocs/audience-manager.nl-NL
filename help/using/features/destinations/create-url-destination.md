---
description: Een doel URL maakt pixelvraag van een pagina aan uw bestemming. Volg deze instructies om een bestemming tot stand te brengen URL met de Bouwer van de Bestemming.
seo-description: Een doel URL maakt pixelvraag van een pagina aan uw bestemming. Volg deze instructies om een bestemming tot stand te brengen URL met de Bouwer van de Bestemming.
seo-title: Een URL-bestemming configureren
solution: Audience Manager
title: Een URL-bestemming configureren
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# Een [!DNL URL Destination] {#configure-url-destination} configureren

Een [!DNL URL destination] maakt pixelaanroepen van een pagina naar uw [!DNL destination]. Volg deze instructies om een [!DNL URL] [!DNL destination] met [!UICONTROL Destination Builder] te creëren.

<!-- create-url-destination.xml -->

Als u een nieuwe [!DNL URL] [!DNL destination] wilt maken, gaat u naar **[!UICONTROL Audience Data > Destinations > Create New Destination]** en vult u de hieronder beschreven secties in.

## Basisinformatie {#basic-info}

Deze sectie bevat velden en opties waarmee het aanmaakproces [!DNL URL destination] wordt gestart. Deze sectie voltooien:

1. Klik **[!UICONTROL Basic Information]** om de controles bloot te stellen.
2. Geef de [!DNL destination] een naam. Vermijd afkortingen en speciale tekens.
3. *(Optioneel)* Beschrijf de  [!DNL destination]code. Een beknopte beschrijving is een effectieve manier om meer informatie over een [!DNL destination] te definiëren of te verschaffen.
4. Kies **[!UICONTROL Custom]** in de lijst **[!UICONTROL Category]**.
5. Selecteer in de lijst **[!UICONTROL Environment]** de omgeving waarin de [!DNL URL destination] moet worden geactiveerd.
6. Klik in de lijst **[!UICONTROL Type]** op **[!UICONTROL URL]**.
7. *(Optioneel)* Selecteer een  **[!UICONTROL Auto-fill Destination Mapping]** optie. De volgende opties zijn beschikbaar:
   * **[!UICONTROL Segment ID]**: Voegt automatisch segmentidentiteitskaart aan toe en verzendt naar  [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Voegt automatisch de code van de segmentintegratie aan de bestemmingstoewijzing toe en verzendt. De integratiecode is een uniek herkenningsteken dat door de klant wordt gecreeerd en wordt gebruikt. De waarde is beperkt tot maximaal 255 tekens.
8. Klik **[!UICONTROL Next]** om naar [!UICONTROL Configuration] montages te gaan of **[!UICONTROL Data Export Labels]** te klikken om de uitvoercontroles op [!DNL destination] toe te passen.

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Deze sectie bevat opties die [besturingselementen voor gegevensexport](../../features/data-export-controls.md) toepassen op een [!DNL URL]-bestemming. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klik **[!UICONTROL Data Export Labels]** om de controles bloot te stellen.
2. Selecteer een label dat overeenkomt met het besturingselement voor gegevensexport dat op de bestemming wordt toegepast (zie [Labels exporteren toevoegen aan een doel](/help/using/features/destinations/add-data-export-labels.md) voor meer informatie).
3. Klik op **[!UICONTROL Save]**.

## Configuratie {#configure-base-data}

Deze sectie bevat opties waarmee u een basis [!DNL URL] en gegevensscheidingstekens kunt instellen die door de [!DNL URL]-tekenreeks worden doorgegeven. Deze sectie is optioneel. Deze sectie voltooien:

1. Klik **[!UICONTROL Configuration]** om de controles bloot te stellen.
1. *(Optioneel)* Selecteer het  **[!UICONTROL Serialize]** selectievakje.
Dit laat u segmenten naar [!DNL destination] opeenvolgend verzenden eerder dan het maken van afzonderlijke vraag voor elk segment. Serienummering helpt gegevensoverdracht efficiënt te maken. Als u dit selectievakje inschakelt, worden de velden URL en scheidingstekens weergegeven. Voor meer informatie, zie [Standaard en Serie zeer belangrijke-waardeparen](../../features/destinations/key-value-pairs.md).
1. Als u **[!UICONTROL Serialize]** selecteert, dan moet u ook de hieronder beschreven gebieden URL en afbakening vormen.

| Veld | Beschrijving |
|--- |--- |
| [!UICONTROL Base URL] | Het basisdeel van een standaard `HTTP` [!DNL URL] dat niet verandert. Ook, moet u `%ALIAS%` [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in basis URL plaatsen. Voorbeeld: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Het basisgedeelte van een beveiligde `HTTPS` [!DNL URL] die niet wordt gewijzigd. Ook moet u `%ALIAS%` plaatsen   [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in basis URL. Voorbeeld: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Het symbool dat de segmentvariabelen in de tekenreeks [!DNL URL] scheidt. Dit is meestal een komma of een puntkomma. Krijg deze informatie van uw bestemmingspartner. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Met deze sectie kunt u zoeken naar segmenten en deze toevoegen aan uw [!UICONTROL destination]. Deze sectie voltooien:

1. Klik **[!UICONTROL Segment Mappings]** om de controles bloot te stellen.
1. Start in het tekstvak **[!UICONTROL Search and Add Segments]** de naam van een segment of klik op **[!UICONTROL Browse All Segments]** om door een lijst met beschikbare segmenten te bladeren.
1. Klik **[!UICONTROL Add Selected Segments]** wanneer u het segment vindt u wilt gebruiken. Als u een segment toevoegt, wordt het venster [!UICONTROL Edit Mapping] geopend.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geef de sleutelwaardeparen op die door het segment worden gebruikt.
   * **[!UICONTROL Start Date]** en  **[!UICONTROL End Date]**: Kies een begin- en einddatum voor de  [!DNL destination]. Als de einddatum leeg is, verloopt [!DNL destination] nooit.
1. Klik op **[!UICONTROL Done]**.