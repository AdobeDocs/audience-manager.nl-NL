---
description: Een koekjesbestemming keert en schrijft gegevens aan een koekje in browser van de gebruiker terug. Het cookie bevat gegevens die kunnen worden gelezen door andere platforms die toegang hebben tot de pagina. Volg deze instructies om een koekjesbestemming met [!UICONTROL de Bouwer van de Bestemming te creëren].
seo-description: Een koekjesbestemming keert en schrijft gegevens aan een koekje in browser van de gebruiker terug. Het cookie bevat gegevens die kunnen worden gelezen door andere platforms die toegang hebben tot de pagina. Volg deze instructies om een koekjesbestemming met [!UICONTROL de Bouwer van de Bestemming te creëren].
seo-title: Een Cookie-bestemming configureren
solution: Audience Manager
title: Een Cookie-bestemming configureren
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---


# Een Cookie-bestemming configureren {#create-cookie-destination}

Een koekjesbestemming keert en schrijft gegevens aan een koekje in browser van de gebruiker terug. Het cookie bevat gegevens die kunnen worden gelezen door andere platforms die toegang hebben tot de pagina. Volg deze instructies om een koekjesbestemming met te creëren [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Ga naar de secties die hieronder worden beschreven en vul de secties in om een nieuwe cookiebestemming te maken. **[!UICONTROL Audience Data > Destinations > Create New Destination]**

## Basisinformatie {#basic-information}

Deze sectie bevat velden en opties waarmee het aanmaakproces van de cookie-bestemming wordt gestart. Deze sectie voltooien:

1. Klik **[!UICONTROL Basic Information]** om de besturingselementen beschikbaar te maken.
2. Geef het doel een naam. Vermijd afkortingen en speciale tekens.
3. *(Optioneel)* Beschrijf de bestemming. Een beknopte beschrijving is een effectieve manier om meer informatie over een bestemming te definiëren of te verstrekken.
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. In the **[!UICONTROL Environment]** list, select **[!UICONTROL Browser]**. U kunt geen cookiedoelen configureren voor systeemeigen mobiele omgevingen, zoals Android- of iOS-toepassingen.
6. Klik in de **[!UICONTROL Type]** lijst op **[!UICONTROL Cookie]**.
7. *(Optioneel)* Selecteer een **[!UICONTROL Auto-fill Destination Mapping]**. De volgende opties zijn beschikbaar:
   * **[!UICONTROL Segment ID]**: Voegt automatisch segmentidentiteitskaart aan en verzendt naar de bestemming toe.
   * **[!UICONTROL Integration Code Value]**: Voegt automatisch de code van de segmentintegratie aan de bestemmingstoewijzing toe en verzendt. De integratiecode is een uniek herkenningsteken dat door de klant wordt gecreeerd en wordt gebruikt. De waarde is beperkt tot maximaal 255 tekens.
8. Klik **[!UICONTROL Next]** om naar de [!UICONTROL Configuration] instellingen te gaan of klik **[!UICONTROL Data Export Labels]** om besturingselementen voor exporteren toe te passen op de bestemming.

## Labels voor gegevensexport {#data-export-labels-cookies}

Deze sectie bevat opties die besturingselementen [voor het exporteren van](../../features/data-export-controls.md) gegevens toepassen op een cookiebestemming. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klik **[!UICONTROL Data Export Labels]** om de besturingselementen beschikbaar te maken.
2. Selecteer een label dat overeenkomt met het besturingselement voor gegevensexport dat op de bestemming is toegepast (zie Labels exporteren [toevoegen aan een bestemming](/help/using/features/destinations/add-data-export-labels.md) voor meer informatie).
3. Klik op **[!UICONTROL Save]**.

## Configuratie {#configuration}

Deze sectie bevat velden en opties waarmee u de cookie voor uw bestemming kunt instellen.

>[!NOTE]
>
>[!DNL Audience Manager] codeert gegevens die naar het bestemmingskoekje worden geschreven. Spaties worden bijvoorbeeld gecodeerd als `%20` en puntkomma&#39;s worden gecodeerd als `%3B`.

Deze sectie voltooien:

1. Klik **[!UICONTROL Configuration]** om de besturingselementen weer te geven
1. Geef de cookie een naam. Vermijd afkortingen en speciale tekens.
1. Kies een optie voor de gegevensindeling. Met deze opties kunt u de scheidingstekens en scheidingstekens kiezen voor de sleutelwaardeparen die segmentgegevens naar een bestemming verzenden. Indelingsopties zijn:
   * **Eén toets:** Hiermee kunt u de sleutel instellen in een sleutelwaardepaar. U zult de waarde plaatsen nadat u een segment in de hieronder [!UICONTROL Segment Mappings] sectie selecteert.
   * **Meerdere toetsen:** Hiermee kunt u de sleutel en waarde voor een sleutelwaardepaar instellen. U zult het zeer belangrijk-waardepaar tot stand brengen nadat u een segment in de sectie van de Toewijzingen van het Segment hieronder selecteert.
Zie [Standaard en Periodieke zeer belangrijke-Waarde paren](../../features/destinations/key-value-pairs.md) voor meer informatie over deze gegevenselementen.
1. Klik op **[!UICONTROL Save]**.

Alle andere instellingen zijn optioneel. Voor meer informatie over de **[!UICONTROL Cookie Domain]** en **[!UICONTROL Publish data to]** montages, zie [Facultatieve Montages voor de Doelen](/help/using/features/destinations/cookie-destination-options.md)van het Koekje.

## Segmenttoewijzingen {#segments-mapping}

In deze sectie kunt u zoeken naar segmenten en deze toevoegen aan uw doel. Deze sectie voltooien:

1. Klik **[!UICONTROL Segment Mappings]** om de besturingselementen beschikbaar te maken.
1. Typ in het **[!UICONTROL Search and Add Segments]** vak de naam van een segment of klik **[!UICONTROL Browse All Segments]** om door een lijst met beschikbare segmenten te bladeren.
1. Klik **[!UICONTROL Add Selected Segments]** wanneer u het segment vindt u wilt gebruiken. Als u een segment toevoegt, wordt het [!UICONTROL Edit Mapping] venster geopend.
1. In the [!UICONTROL Edit Mapping] dialog:
   * **[!UICONTROL Mapping]** laat u een waarde voor de sleutel plaatsen die in de sectie van de Configuratie hierboven wordt gespecificeerd.
   * **[!UICONTROL Publish from]** Hiermee kunt u de begin- en einddatum voor het doel instellen. Als de einddatum leeg is, verloopt de bestemming nooit.
1. Klik op **[!UICONTROL Save]**.
1. Klik op **[!UICONTROL Done]**.