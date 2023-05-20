---
description: Een koekjesbestemming keert en schrijft gegevens aan een koekje in browser van de gebruiker terug. Het cookie bevat gegevens die kunnen worden gelezen door andere platforms die toegang hebben tot de pagina. Volg deze instructies om een koekjesbestemming tot stand te brengen met [!UICONTROL Destination Builder].
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Een cookiebestemming configureren
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 2%

---

# Een cookiebestemming configureren {#create-cookie-destination}

Een koekjesbestemming keert en schrijft gegevens aan een koekje in browser van de gebruiker terug. Het cookie bevat gegevens die kunnen worden gelezen door andere platforms die toegang hebben tot de pagina. Volg deze instructies om een koekjesbestemming tot stand te brengen met [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Ga naar **[!UICONTROL Audience Data > Destinations > Create New Destination]** en voltooi de hieronder beschreven secties.

## Basisinformatie {#basic-information}

Deze sectie bevat velden en opties waarmee het aanmaakproces van de cookie-bestemming wordt gestart. Deze sectie voltooien:

1. Klikken **[!UICONTROL Basic Information]** om de besturingselementen zichtbaar te maken.
2. Geef het doel een naam. Vermijd afkortingen en speciale tekens.
3. *(Optioneel)* Beschrijf de bestemming. Een beknopte beschrijving is een effectieve manier om meer informatie over een bestemming te definiëren of te verstrekken.
4. In de **[!UICONTROL Category]** lijst, kiest u **[!UICONTROL Custom]**.
5. In de **[!UICONTROL Environment]** list, selecteer **[!UICONTROL Browser]**. U kunt geen cookiedoelen configureren voor systeemeigen mobiele omgevingen, zoals Android- of iOS-toepassingen.
6. In de **[!UICONTROL Type]** lijst, klikt u op **[!UICONTROL Cookie]**.
7. *(Optioneel)* Selecteer een **[!UICONTROL Auto-fill Destination Mapping]**. De volgende opties zijn beschikbaar:
   * **[!UICONTROL Segment ID]**: Voegt automatisch segmentidentiteitskaart aan en verzendt naar de bestemming toe.
   * **[!UICONTROL Integration Code Value]**: Voegt automatisch de code van de segmentintegratie aan de bestemmingstoewijzing toe en verzendt. De integratiecode is een uniek herkenningsteken dat door de klant wordt gecreeerd en wordt gebruikt. De waarde is beperkt tot maximaal 255 tekens.
8. Klikken **[!UICONTROL Next]** om naar de [!UICONTROL Configuration] instellingen of klik op **[!UICONTROL Data Export Labels]** om exportbesturingselementen toe te passen op de bestemming.

## Labels voor gegevensexport {#data-export-labels-cookies}

Deze sectie bevat opties die van toepassing zijn [besturingselementen voor exporteren van gegevens](../../features/data-export-controls.md) naar een cookiebestemming. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klikken **[!UICONTROL Data Export Labels]** om de besturingselementen zichtbaar te maken.
2. Selecteer een label dat overeenkomt met het besturingselement voor gegevensexport dat op de bestemming is toegepast (zie [Exportlabels toevoegen aan een doel](/help/using/features/destinations/add-data-export-labels.md) voor meer informatie).
3. Klik op **[!UICONTROL Save]**.

## Configuratie {#configuration}

Deze sectie bevat velden en opties waarmee u de cookie voor uw bestemming kunt instellen.

>[!NOTE]
>
>[!DNL Audience Manager] codeert gegevens die naar het bestemmingskoekje worden geschreven. Spaties worden bijvoorbeeld gecodeerd als `%20` en puntkomma&#39;s worden gecodeerd als `%3B`.

Deze sectie voltooien:

1. Klikken **[!UICONTROL Configuration]** om de besturingselementen zichtbaar te maken
1. Geef de cookie een naam. Vermijd afkortingen en speciale tekens.
1. Kies een optie voor de gegevensindeling. Met deze opties kunt u de scheidingstekens en scheidingstekens kiezen voor de sleutelwaardeparen die segmentgegevens naar een bestemming verzenden. Indelingsopties zijn:
   * **Eén toets:** Hiermee kunt u de sleutel instellen in een sleutelwaardepaar. U zult de waarde plaatsen nadat u een segment in selecteert [!UICONTROL Segment Mappings] hieronder.
   * **Meerdere toetsen:** Hiermee kunt u de sleutel en waarde voor een sleutelwaardepaar instellen. U zult het zeer belangrijk-waardepaar tot stand brengen nadat u een segment in de sectie van de Toewijzingen van het Segment hieronder selecteert.
Zie [Standaard en seriële sleutelwaardeparen](../../features/destinations/key-value-pairs.md) voor meer informatie over deze gegevenselementen.
1. Klik op **[!UICONTROL Save]**.

Alle andere instellingen zijn optioneel. Voor meer informatie over de **[!UICONTROL Cookie Domain]** en **[!UICONTROL Publish data to]** instellingen, zie [Optionele instellingen voor Cookie-doelen](/help/using/features/destinations/cookie-destination-options.md).

## Segmenttoewijzingen {#segments-mapping}

In deze sectie kunt u zoeken naar segmenten en deze toevoegen aan uw doel. Deze sectie voltooien:

1. Klikken **[!UICONTROL Segment Mappings]** om de besturingselementen zichtbaar te maken.
1. In de **[!UICONTROL Search and Add Segments]** , begint u de naam van een segment te typen of klikt u op **[!UICONTROL Browse All Segments]** om door een lijst met beschikbare segmenten te bladeren.
1. Klikken **[!UICONTROL Add Selected Segments]** wanneer u het segment vindt u wilt gebruiken. Als u een segment toevoegt, wordt het dialoogvenster [!UICONTROL Edit Mapping] venster.
1. In de [!UICONTROL Edit Mapping] dialoogvenster:
   * **[!UICONTROL Mapping]** laat u een waarde voor de sleutel plaatsen die in de sectie van de Configuratie hierboven wordt gespecificeerd.
   * **[!UICONTROL Publish from]** Hiermee kunt u de begin- en einddatum voor het doel instellen. Als de einddatum leeg is, verloopt de bestemming nooit.
1. Klik op **[!UICONTROL Save]**.
1. Klik op **[!UICONTROL Done]**.
