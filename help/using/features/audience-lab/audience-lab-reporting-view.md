---
description: De rapporteringssectie van de testgroep bevat informatie over de omzettingen van de testgroep, zodat de werkzaamheid van het testsegment gemakkelijk kan worden vergeleken. Er zijn talrijke filters en afmetingen beschikbaar voor gegevensvisualisatie.
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: Rapportering testgroep
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Rapportering testgroep {#test-group-reporting}

De rapporteringssectie van de testgroep bevat informatie over de omzettingen van de testgroep, zodat de werkzaamheid van het testsegment gemakkelijk kan worden vergeleken. Er zijn talrijke filters en afmetingen beschikbaar voor gegevensvisualisatie.

[!UICONTROL Audience Lab] retourneert gedetailleerde rapportgegevens voor de testsegmenten die u hebt gemaakt. U kunt de rapportgegevens opslaan als [!DNL CSV] -bestanden. U kunt kiezen tussen **[!UICONTROL Aggregate Reporting]** en **[!UICONTROL Trend Reporting]** .

**[!UICONTROL Aggregate Reporting]** retourneert de absolute getallen voor uw testsegmenten. **[!UICONTROL Trend Reporting]** keert een grafiek van de trend *over een specifieke periode* terug. Met vier tabbladen kunt u de rapporten aanpassen:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bevolkingsconversiesnelheid </span></b> </p> </td> 
   <td colname="col2"> <p>Retourneert het percentage apparaten dat tot een bepaald testsegment behoort en dat zijn omgezet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Converters </span></b> </p> </td> 
   <td colname="col2"> <p>Retourneert het aantal apparaten dat de in de testgroepen geselecteerde conversietekenmerken heeft/hebben tentoongesteld. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Bekijk deze video </a> om te leren hoe u omzettingskenmerken kunt maken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Totaal aantal conversies </span></b> </p> </td> 
   <td colname="col2"> <p>Retourneert het aantal omzettingen dat door de testsegmenten wordt gegenereerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Populaties van segmenten testen </span></b> </p> </td> 
   <td colname="col2"> <p>Retourneert het aantal apparaten dat tot de testsegmenten behoort. Wissel tussen <b><span class="uicontrol"> Totale Bevolking </span></b> of <b><span class="uicontrol"> Realtime Bevolking </span></b>. Het verschil wordt uitgelegd in de <a href="../../faq/faq-reporting.md"> Veelgestelde vragen over rapportage </a> . </p> </td>
  </tr>
 </tbody>
</table>

U kunt een specifieke omzettingseigenschap selecteren waarvoor om het rapport te produceren of u kunt alle eigenschappen samen selecteren. U kunt een datumbereik definiëren waarvoor de informatie moet worden geretourneerd en het rapport exporteren als een [!DNL CSV] -bestand.

>[!NOTE]
>
>* De rapportering voor een testgroep zal de dag na zijn begindatum bevolken.
>* Een conversie wordt alleen geteld voor een apparaat na de begindatum van een test en nadat het apparaat aan een testsegment is toegevoegd. Als er voor dat apparaat een conversie plaatsvindt voordat er een testgroep aan wordt toegewezen, wordt de conversie niet geteld.

Een geretourneerde **[!UICONTROL Aggregate Reporting]** -grafiek kan er als volgt uitzien:

![](assets/aggregate-reporting.PNG)

Een geretourneerde **[!UICONTROL Trend Reporting]** -grafiek kan er ongeveer zo uitzien als hieronder. Selecteer **[!UICONTROL Normalized]** in het selectievakje als u de absolute getallen wilt negeren en de trends voor de testsegmenten wilt volgen.

![](assets/trend-reporting.PNG)
