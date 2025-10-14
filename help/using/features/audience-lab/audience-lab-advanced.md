---
description: In dit artikel worden twee functies beschreven die geavanceerde functionaliteit bieden voor Audience Lab Duplicate Allocation Template en Segment Holdout.
seo-description: This article describes two features which provide advanced functionality for Audience Lab  Duplicate Allocation Template and Segment Holdout.
seo-title: Audience Lab Advanced Functionality
solution: Audience Manager
title: Geavanceerde functionaliteit van het laboratorium van het publiek
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---

# [!DNL Audience Lab] Geavanceerde functionaliteit {#audience-lab-advanced-functionality}

In dit artikel worden twee functies beschreven die geavanceerde functionaliteit bieden voor [!DNL Audience Lab] : [!DNL Duplicate Allocation Template] en [!DNL Segment Holdout] .

## Toewijzingssjabloon dupliceren {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab] vertegenwoordigt [!DNL Allocation Template] de verschillende selecties die u maakt bij het maken van een testgroep:

* de verdeling van de voorzieningen tussen de testsegmenten;
* het in kaart brengen van testsegmenten naar bestemmingen;
* De omzettingskenmerken die u voor een testgroep gebruikt;
* De datumwaaier waarin de testgroep aan uw geselecteerde bestemmingen publiceert.

Door een toewijzingsmalplaatje te dupliceren, kunt u de zelfde distributie van testsegmenten en bestemmingen voor een verschillend basissegment, in een nieuwe testgroep opnieuw gebruiken. Een voorbeeld van een toewijzingssjabloon wordt hieronder weergegeven. Het beeld wordt genomen van de [!UICONTROL Summary & Finalize] stap in **creeer het werkschema van de Groep van de Test**.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Dubbele toewijzingssjabloon gebruiken

Maak een eerste testgroep en selecteer vervolgens **[!UICONTROL Duplicate Allocation Template]** om dezelfde instellingen opnieuw te gebruiken voor meerdere testgroepen. Bijvoorbeeld, kunt u deze eigenschap gebruiken als u een test in werking stelt waar u de doeltreffendheid van verscheidene bestemmingen voor veelvoudige segmenten wilt bepalen.

1. Zoek in de hoofdweergave van het laboratorium van het publiek naar de testgroep waarvan u de toewijzingssjabloon wilt weergeven in een nieuwe testgroep. Selecteer **[!UICONTROL Duplicate Allocation Template]** in de vervolgkeuzelijst.

   ![](assets/duplicate-allocation-template.png)

2. In de wizard [!UICONTROL Create Test Group] kunt u een basissegment opgeven en desgewenst de naam van de testsegmenten wijzigen.
3. U *kunt niet* wijzigen:

   * de verdeling van de voorzieningen tussen de testsegmenten;
   * de omzettingskenmerken;
   * De toewijzing van testsegmenten aan bestemmingen. U kunt de toewijzingssleutel alleen invullen voor de doelen die deze vereisen.
   * De datumwaaier waarin uw testgroep aan uw geselecteerde bestemmingen zal publiceren.

4. Controleer de gegevens die u in de vorige stappen hebt toegevoegd en selecteer **[!UICONTROL Finalize Group]** .

## Uitsluiting testsegment {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] is een geavanceerde functionaliteit die op verzoek van de klant wordt geactiveerd. Neem contact op met [!DNL Customer Care] of [!DNL Adobe Consulting] om deze functie te activeren.

Gebruik deze functie om te voorkomen dat een deel van het publiek wordt opgenomen in de test. Het percentage dat u selecteert, blijft buiten de test. Op deze manier kunt u het aantal conversies van doelgroepen (geactiveerd op doelen) en niet-doelgroepen (holdout groep) meten en vergelijken.

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Testsegmentvastlegging gebruiken

1. Maak een nieuwe testgroep met de wizard [!UICONTROL Create Test Group] .
1. In de stap **[!UICONTROL Allocate Test Segment]** kunt u een deel van het publiek selecteren dat u niet wilt testen.

   ![&#x200B; Punt van de Lijst &#x200B;](assets/test-segment-holdout.png)

1. Gebruik de schuifregelaar om aan te passen hoeveel apparaten u niet wilt testen. Merk op dat testsegment 1 en testsegment 2 nu slechts 70% van de totale apparaten uitmaken.

   ![](assets/test-segment-holdout-selected.png)

1. Doorloop de overige stappen in de **[!UICONTROL Create Test Group]** -workflow en selecteer **[!UICONTROL Finalize Group]** wanneer u tevreden bent met de selectie. U hebt nu een testgroep waarvan een deel van het publiek niet meer kan testen.
