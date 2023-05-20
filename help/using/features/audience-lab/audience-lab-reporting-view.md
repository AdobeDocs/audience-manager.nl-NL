---
description: De rapporteringssectie van de testgroep bevat informatie over de omzettingen van de testgroep, zodat de werkzaamheid van het testsegment gemakkelijk kan worden vergeleken. Er zijn talrijke filters en afmetingen beschikbaar voor gegevensvisualisatie.
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: Testgroeprapportage
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 2%

---

# Testgroeprapportage {#test-group-reporting}

De rapporteringssectie van de testgroep bevat informatie over de omzettingen van de testgroep, zodat de werkzaamheid van het testsegment gemakkelijk kan worden vergeleken. Er zijn talrijke filters en afmetingen beschikbaar voor gegevensvisualisatie.

[!UICONTROL Audience Lab] retourneert gedetailleerde rapportgegevens voor de testsegmenten die u hebt gemaakt en kunt u de rapportgegevens opslaan als [!DNL CSV] bestanden. U kunt kiezen tussen **[!UICONTROL Aggregate Reporting]** en **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** retourneert de absolute getallen voor uw testsegmenten. **[!UICONTROL Trend Reporting]** geeft een grafiek van de trend weer *over een specifieke periode*. Met vier tabbladen kunt u de rapporten aanpassen:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Omzetsnelheid bevolking</span></b> </p> </td> 
   <td colname="col2"> <p>Retourneert het percentage apparaten dat tot een bepaald testsegment behoort en dat zijn omgezet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Converters</span></b> </p> </td> 
   <td colname="col2"> <p>Retourneert het aantal apparaten dat de in de testgroepen geselecteerde conversietekenmerken heeft/hebben tentoongesteld. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Deze video bekijken</a> voor meer informatie over het maken van conversiekenmerken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Totaal conversies</span></b> </p> </td> 
   <td colname="col2"> <p>Retourneert het aantal omzettingen dat door de testsegmenten wordt gegenereerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Testsegmentpopulaties</span></b> </p> </td> 
   <td colname="col2"> <p>Retourneert het aantal apparaten dat tot de testsegmenten behoort. Schakelen tussen <b><span class="uicontrol"> Totale populatie</span></b> of <b><span class="uicontrol"> Real-time populatie</span></b>. Het verschil wordt verklaard in het <a href="../../faq/faq-reporting.md"> Veelgestelde vragen over rapportage</a> . </p> </td>
  </tr>
 </tbody>
</table>

U kunt een specifieke omzettingseigenschap selecteren waarvoor om het rapport te produceren of u kunt alle eigenschappen samen selecteren. U kunt een datumbereik definiëren waarvoor de informatie moet worden geretourneerd en het rapport exporteren als een [!DNL CSV] bestand.

>[!NOTE]
>
>* De rapportering voor een testgroep zal de dag na zijn begindatum bevolken.
>* Een conversie wordt alleen geteld voor een apparaat na de begindatum van een test en nadat het apparaat aan een testsegment is toegevoegd. Als er voor dat apparaat een conversie plaatsvindt voordat er een testgroep aan wordt toegewezen, wordt de conversie niet geteld.


Een geretourneerde waarde **[!UICONTROL Aggregate Reporting]** de grafiek kan er als volgt uitzien :

![](assets/aggregate-reporting.PNG)

Een geretourneerde waarde **[!UICONTROL Trend Reporting]** de grafiek kan er zo uitzien als hieronder. Selecteren **[!UICONTROL Normalized]** in de controledoos als u de absolute aantallen wilt negeren en eenvoudig zich op de tendensen van de testsegmenten wilt concentreren.

![](assets/trend-reporting.PNG)
