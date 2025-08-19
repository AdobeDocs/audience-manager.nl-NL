---
description: Een koekjesbestemming keert en schrijft gegevens aan een koekje in browser van de gebruiker terug. Het cookie bevat gegevens die kunnen worden gelezen door andere platforms die toegang hebben tot de pagina. Volg deze instructies om een koekjesbestemming met [!UICONTROL Destination Builder] tot stand te brengen.
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Een Cookie-bestemming configureren
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Een Cookie-bestemming configureren {#create-cookie-destination}

Een koekjesbestemming keert en schrijft gegevens aan een koekje in browser van de gebruiker terug. Het cookie bevat gegevens die kunnen worden gelezen door andere platforms die toegang hebben tot de pagina. Volg deze instructies om een koekjesbestemming met [!UICONTROL Destination Builder] tot stand te brengen.

<!-- create-cookie-destination.xml -->

Ga naar **[!UICONTROL Audience Data > Destinations > Create New Destination]** en vul de secties in zoals hieronder beschreven om een nieuw doel voor een cookie te maken.

## Basisinformatie {#basic-information}

Deze sectie bevat velden en opties waarmee het aanmaakproces van de cookie-bestemming wordt gestart. Deze sectie voltooien:

1. Klik op **[!UICONTROL Basic Information]** om de besturingselementen weer te geven.
2. Geef het doel een naam. Vermijd afkortingen en speciale tekens.
3. *(Facultatief)* beschrijf de bestemming. Een beknopte beschrijving is een effectieve manier om meer informatie over een bestemming te definiëren of te verstrekken.
4. Kies **[!UICONTROL Category]** in de lijst **[!UICONTROL Custom]** .
5. Selecteer **[!UICONTROL Environment]** in de lijst **[!UICONTROL Browser]** . U kunt geen cookiedoelen configureren voor systeemeigen mobiele omgevingen, zoals Android- of iOS-toepassingen.
6. Klik in de lijst **[!UICONTROL Type]** op **[!UICONTROL Cookie]** .
7. *(Optioneel)* Selecteer een **[!UICONTROL Auto-fill Destination Mapping]** . U kunt onder andere de volgende opties kiezen:
   * **[!UICONTROL Segment ID]**: hiermee wordt de segment-id automatisch toegevoegd en naar het doel verzonden.
   * **[!UICONTROL Integration Code Value]**: voegt automatisch de code van de segmentintegratie toe en verzendt naar de bestemmingstoewijzing. De integratiecode is een uniek herkenningsteken dat door de klant wordt gecreeerd en wordt gebruikt. De waarde is beperkt tot maximaal 255 tekens.
8. Klik op **[!UICONTROL Next]** om naar de instellingen van [!UICONTROL Configuration] te gaan of klik op **[!UICONTROL Data Export Labels]** om besturingselementen voor exporteren toe te passen op het doel.

## Labels voor gegevensexport {#data-export-labels-cookies}

Deze sectie bevat opties die [ de controles van de gegevensuitvoer ](../../features/data-export-controls.md) op een koekjesbestemming toepassen. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klik op **[!UICONTROL Data Export Labels]** om de besturingselementen weer te geven.
2. Selecteer een etiket dat aan de controle beantwoordt van de gegevensuitvoer die op de bestemming wordt toegepast (zie [ de Etiketten van de Uitvoer aan een Doel ](/help/using/features/destinations/add-data-export-labels.md) voor details toevoegen).
3. Klik op **[!UICONTROL Save]**.

## Configuratie {#configuration}

Deze sectie bevat velden en opties waarmee u de cookie voor uw bestemming kunt instellen.

>[!NOTE]
>
>[!DNL Audience Manager] codeert gegevens die naar het doelcookie zijn geschreven. Spaties worden bijvoorbeeld gecodeerd als `%20` en puntkomma&#39;s als `%3B` .

Deze sectie voltooien:

1. Klik op **[!UICONTROL Configuration]** om de besturingselementen weer te geven
1. Geef de cookie een naam. Vermijd afkortingen en speciale tekens.
1. Kies een optie voor de gegevensindeling. Met deze opties kunt u de scheidingstekens en scheidingstekens kiezen voor de sleutelwaardeparen die segmentgegevens naar een bestemming verzenden. Indelingsopties zijn:
   * **Enige sleutel:** laat u de sleutel in een zeer belangrijk-waardepaar plaatsen. U stelt de waarde in nadat u een segment hebt geselecteerd in de onderstaande sectie [!UICONTROL Segment Mappings] .
   * **Multi sleutel:** laat u de sleutel en de waarde voor een zeer belangrijk-waardepaar plaatsen. U zult het zeer belangrijk-waardepaar tot stand brengen nadat u een segment in de sectie van de Toewijzingen van het Segment hieronder selecteert.
Zie [ Standaard en Serie Zeer belangrijk-Waarde paren ](../../features/destinations/key-value-pairs.md) voor meer informatie over deze gegevenselementen.
1. Klik op **[!UICONTROL Save]**.

Alle andere instellingen zijn optioneel. Voor meer informatie over **[!UICONTROL Cookie Domain]** en **[!UICONTROL Publish data to]** montages, zie [ Facultatieve Montages voor de Doelen van het Koekje ](/help/using/features/destinations/cookie-destination-options.md).

## Segmenttoewijzingen {#segments-mapping}

In deze sectie kunt u zoeken naar segmenten en deze toevoegen aan uw doel. Deze sectie voltooien:

1. Klik op **[!UICONTROL Segment Mappings]** om de besturingselementen weer te geven.
1. Typ in het vak **[!UICONTROL Search and Add Segments]** de naam van een segment of klik op **[!UICONTROL Browse All Segments]** om door een lijst met beschikbare segmenten te bladeren.
1. Klik op **[!UICONTROL Add Selected Segments]** wanneer u het gewenste segment vindt. Als u een segment toevoegt, wordt het venster [!UICONTROL Edit Mapping] geopend.
1. In het dialoogvenster [!UICONTROL Edit Mapping] :
   * Met **[!UICONTROL Mapping]** kunt u een waarde instellen voor de toets die in de bovenstaande sectie Configuratie is opgegeven.
   * Met **[!UICONTROL Publish from]** kunt u de begin- en einddatum voor het doel instellen. Als de einddatum leeg is, verloopt de bestemming nooit.
1. Klik op **[!UICONTROL Save]**.
1. Klik op **[!UICONTROL Done]**.
