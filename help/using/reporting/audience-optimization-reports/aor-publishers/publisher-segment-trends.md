---
description: Het rapport van de Trend van het Segment keert gegevens over indrukkingen en klikthrough tarieven van in kaart gebrachte en unmapped segmenten in tijd terug. Een in kaart gebracht segment is een segment u creeert en naar een bestemming verzendt voor het richten. Een niet in kaart gebracht segment is een segment dat u hebt gecreeerd maar niet verzonden naar een bestemming voor het richten. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. Een in kaart gebracht segment is een segment u creeert en naar een bestemming verzendt voor het richten. Een niet in kaart gebracht segment is een segment dat u hebt gecreeerd maar niet verzonden naar een bestemming voor het richten. Vergelijk trends en volume voor de geselecteerde metriek om een beter beeld te krijgen van hoe uw publiek zich gedraagt in de loop van de tijd.
seo-title: Trend-rapport segment
solution: Audience Manager
title: Trend-rapport segment
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 0%

---


# Trend-rapport segment{#segment-trend-report}

Het rapport van de Trend van het Segment keert gegevens over indrukkingen en klikthrough tarieven van in kaart gebrachte en unmapped segmenten in tijd terug.

Een in kaart gebracht segment is een segment u creeert en naar een bestemming verzendt voor het richten. Een niet in kaart gebracht segment is een segment dat u hebt gecreeerd maar niet verzonden naar een bestemming voor het richten.

Vergelijk trends en volume voor de geselecteerde metriek om een beter beeld te krijgen van hoe uw publiek zich gedraagt in de loop van de tijd.

## Hoofdletters gebruiken {#use-cases}

Gebruik het [!UICONTROL Segment Trend] rapport om de prestaties van een segment in de loop der tijd te valideren en trends vast te stellen op basis van sterke prestaties of schaal.

Met dit rapport, kunt u begrijpen welke van uw Web-eigenschappen een dip of defecte verhoging tonen en zonodig problemen oplossen. Dit rapport is de volgende stap nadat u uw publiek van belang in het [!UICONTROL Segment Performance] rapport hebt geïdentificeerd, om ervoor te zorgen dat de sterke of slechte prestaties die u op het [!UICONTROL Segment Performance] lusje zag in tijd verenigbaar zijn.

## Het rapport Segment Trend gebruiken {#using-the-report}

Schakel tussen **[!UICONTROL Mapped]** en **[!UICONTROL Unmapped]** om segmenten te selecteren die wel of niet aan een doel zijn toegewezen. Selecteer **[!UICONTROL All]** om al uw segmenten in het rapport op te nemen.

Pas het terugblik venster met de **[!UICONTROL Date Through]** schuif aan.

Klik op een van de segmenten onder de **[!UICONTROL Date Through]** schuifregelaar om de optie voor alleen dat segment in het rapport op te nemen of uit te sluiten.

Gebruik het **[!UICONTROL Line Item]** drop-down vakje om de eigenschappen in uw portefeuille te selecteren waarvoor u informatie wilt terugkeren.

In de **[!UICONTROL Segment Data Source]** drop-down doos, selecteer de gegevensbronnen die de segmenten bevatten u in het rapport wilt zien.

Gebruik de **[!UICONTROL Segment]** drop-down doos om te selecteren welke segmenten u in het rapport wilt zien.

>[!IMPORTANT]
>
>Wanneer het toelaten [!UICONTROL Audience Optimization for Publishers], moet u beschrijvende meta-gegevens voor identiteitskaart [!UICONTROL Line Item] &#39;s omvatten, zoals die in Stap 3 van de Dossiers van Gegevens DFP van de [Invoer in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)wordt beschreven. Door dit te doen, verzekert u dat het rapport de Webbezit als [!UICONTROL Line Item] in plaats van [!UICONTROL Line Item] identiteitskaart detailleert.

## De resultaten interpreteren {#interpreting-results}

Het [!UICONTROL Segment Trend] rapport retourneert alleen gegevens in een lijngrafiek voor een interval van 14 dagen. In dit voorbeeld toont het rapport de indruk en doorkliktendensen voor een reeks in kaart gebrachte en unmapped segmenten.

Houd over om het even welke lijn om meer informatie over die bepaalde segmenttrend te verkrijgen. Zie beschrijvingen voor de aanvullende informatie in de tabel onder het voorbeeldrapport.

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment</span> </p> </td> 
   <td colname="col2"> <p>De alfanumerieke naam die u aan dit segment hebt toegewezen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment-id</span> </p> </td> 
   <td colname="col2"> <p>De unieke id van dit segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Lijnitem</span> </p> </td> 
   <td colname="col2"> <p>De webeigenschap waarvoor u dit rapport ziet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Klikken</span> </p> </td> 
   <td colname="col2"> <p>Het aantal keren dat leden van deze eigenschap op items in uw webeigenschap hebben geklikt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressies</span> </p> </td> 
   <td colname="col2"> <p>Het aantal keren dat leden van deze eigenschap aan uw voorraad zijn blootgesteld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Doorklikfrequentie. Met deze metrische waarde wordt het percentage van de afbeeldingen weergegeven dat wordt gevolgd door klikken. Verdeel kliks door impressies om dit metrisch te verkrijgen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment Uniques</span> </p> </td> 
   <td colname="col2"> <p>Het aantal segmentleden, in de laatste 30 dagen. </p> </td> 
  </tr> 
 </tbody> 
</table>
