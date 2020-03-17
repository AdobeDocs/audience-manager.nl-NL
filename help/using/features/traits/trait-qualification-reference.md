---
description: De kwalificatie van het spoor, of de realisatie van het bezit, wordt behandeld verschillend in de Manager van de Auditie, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: De kwalificatie van het spoor, of de realisatie van het bezit, wordt behandeld verschillend in de Manager van de Auditie, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.
seo-title: Verwijzing naar beroepskwalificatie
solution: Audience Manager
title: Verwijzing naar beroepskwalificatie
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 2f8662aba70254e550bc15417463c3c06492a9d5

---


# Verwijzing naar beroepskwalificatie {#trait-qualification-reference}

De kwalificatie van het spoor, of de realisatie van het bezit, wordt behandeld verschillend in de Manager van de Auditie, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.

## Kwalificatie volgens type dienstreis {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type overtrek </th> 
   <th colname="col2" class="entry"> Kwalificatiecriteria </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Op regels gebaseerde tradities </p> </td> 
   <td colname="col2"> <p>De vakkwalificatie gebeurt in real time, aangezien de gebruikers voor een eigenschap in hun browser kwalificeren. Uw gebruikers zullen ongeveer 4 uur nadat u de eigenschap <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> in de gebruikersinterface hebt</a> gemaakt, in aanmerking komen voor een op regels gebaseerde eigenschap. </p> <p>De op regel-gebaseerde eigenschappen staan u toe om <a href="../../features/segments/recency-and-frequency.md"> recentie en frequentiecontroles</a> voor ad frequentietoewijzing en andere gebruiksgevallen te gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Treinen aan boord </p> </td> 
   <td colname="col2"> <p>De kwalificatie van het spoor gebeurt nadat een binnenkomend dossier wordt verwerkt, d.w.z. het binnenkomende dossier wordt <a href="../../faq/faq-inbound-data-ingestion.md"> ingevoerd in de Manager</a> van het Publiek en dat is wanneer de karakterkwalificatie gebeurt. U moet ongeveer 4 uur wachten nadat u een ingebouwd kenmerk hebt gemaakt voordat u een binnenkomend bestand uploadt voor verwerking.  </p> <p> Voor niet-geregistreerde kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algorithmic Traits </p> </td> 
   <td colname="col2"> <p>Voor algoritmische kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maptrajecten </p> </td> 
   <td colname="col2"> <p>Een mapkenmerk geeft een overzicht van de kwalificaties van de kenmerken die het bevat. </p> <p>Maptraits voor lezen <a href="../../features/traits/about-folder-traits.md"> : Informatie over</a> meer informatie. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Actieve doelgroepen en gesynchroniseerde gegevensbronnen </p> </td> 
   <td colname="col2"> <p>Een <span class="wintitle"> Actief bezit van het Publiek</span> bevat alle apparaten die in beheer in uw rekening van de Manager <span class="wintitle"> van de</span> Publiek worden. </p> <p><span class="wintitle"> De Bron van gegevens de Gesynchroniseerde Tanden</span> volgen alle gebruikers verbonden aan een gegevensbron. </p> <p>Lees meer over de Actief Traits van het Publiek en de Bron van Gegevens - Gesynchroniseerde Traits <a href="../../features/traits/client-activity-synced-audience-traits.md"></a>. </p> </td>
  </tr>
 </tbody>
</table>

## Unieke realisaties van sporen en totale populatie van trekkers {#unique-trait-realizations}

![](assets/utr-ttp1.png)

Het **[!UICONTROL Unique Trait Realizations]** aantal bezoekers dat de eigenschap aan hun profiel heeft toegevoegd, binnen verschillende tijdbereiken.

Het **[!UICONTROL Total Trait Population]** geeft het aantal bezoekers aan dat deze eigenschap in hun profiel heeft.

Denk aan de cijfers op deze manier. In de bovenstaande afbeelding geeft 181 vanuit de weergave [Details](../../features/traits/trait-details-page.md) over spoor het aantal actieve apparaten aan dat uw eigenschappen gisteren heeft bezocht. De waarde [!UICONTROL Total Trait Population] van 1.595 geeft het aantal gebruikers aan dat momenteel voor dit kenmerk in aanmerking komt. Het [!UICONTROL Total Trait Population] cijfer is bedoeld om de totale hoeveelheid gebruikers te tonen die voor segmentatie/het richten zou kunnen worden gebruikt. Gebruikers blijven doorgaans 120 dagen deel uitmaken van een eigenschap.

Omdat we twee verschillende computertaken uitvoeren om de twee populaties te berekenen, loopt de groep [!UICONTROL Total Trait Population] altijd 24 uur achter op de [!UICONTROL Unique Trait Realizations] groep. In de bovenstaande grafiek zie je 175 [!UICONTROL Unique Trait Realizations] en een [!UICONTROL Total Trait Population] van 6 voor 11 februari. De volgende dag worden de 175 profielen toegevoegd aan de [!UICONTROL Total Trait Population] lijst.

Om het punt naar huis te rijden, als je op dit moment een piek van 10.000 bezoekers zou ervaren, zouden ze morgen verschijnen [!UICONTROL Unique Trait Realizations], maar pas 24 uur later in de [!UICONTROL Total Trait Population]stad.

## Grenswaarde voor beroepskwalificatie {#trait-qualification-limit}

Voor elk gebruikersprofiel geldt een limiet van 150.000 vakkwalificaties. Dit is een geverifieerd profiel ( [DPUUID](../../reference/ids-in-aam.md)) of een apparaat-id ( [UUID](../../reference/ids-in-aam.md)). Merk op dat hoewel DPUUIDs voor een specifiek geval van [!DNL Audience Manager], UUIDs uniek zijn over het [!DNL Audience Manager] platform wordt gedeeld. Voor [!UICONTROL UUID]ons leggen we een billijkheidsbeleid op bij het opslaan van beroepskwalificaties. Een algoritme zorgt ervoor dat een gelijk aandeel van het [!UICONTROL UUID] profiel voor elke instantie van beschikbaar wordt gemaakt [!DNL Audience Manager].
