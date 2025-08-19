---
description: Wanneer een binnenkomend server-aan-server dossier wordt verwerkt, wordt een ontvangstbewijs verzonden via e-mail naar partneroplossingen en, indien gevormd, naar de partner.
seo-description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-title: Sample Message to Partners after Inbound Processing
solution: Audience Manager
title: Het Bericht van de steekproef aan Partners na Binnenkomende verwerking
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# Het Bericht van de steekproef aan Partners na Binnenkomende verwerking{#sample-message-to-partners-after-inbound-processing}

Wanneer een binnenkomend [!UICONTROL Server-to-Server] dossier wordt verwerkt, wordt een ontvangstbewijs verzonden via e-mail naar partneroplossingen en, indien gevormd, naar de partner.

<!-- r_inbound_message.xml -->

Het volgende voorbeeld is een voorbeeld-e-mailbericht. In de tabel onder het bericht worden de verschillende regels in het bericht beschreven.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Van: aam-noreply@adobe.com </b> </p> <p> <b> Onderwerp: Server-aan-Server van Adobe Audience Manager het Resultaat van de Verwerking:</b> </p> <p> <b> Beste Partner van Adobe: (identiteitskaart:7) </b> <b></b> </p> <p> <b> wij hebben uw Adobe Audience Manager Server-aan-Server dossierlevering </b> ontvangen </p> <p> <b> Naam van het Dossier:</b> <i></i> </p> <p> <b> s3n://&lt;<i> bucket_name&gt; </i> /2018-05-17/ftp_dpm_7_901_1368806402.sync </b> </p> <p> <b> s3n://&lt;<i> bucket_name&gt; </i> /2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b> s3n://&lt;<i> bucket_name&gt; </i> /2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b> s3n://&lt;<i> bucket_name&gt; </i> /2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b> s3n://&lt;<i> bucket_name&gt; </i> /2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b> s3n://&lt;<i> bucket_name&gt; </i> /2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b> s3n://&lt;<i> bucket_name&gt; </i> /2018-05-17/ftp_dpm_7_901_1368806404.sync </b> </p> <p> <b> Ontvangen Verslagen: 40669900 </b> </p> <p><b> Fouten van het Formaat: 0 </b> </p> <p> <b> Ongeldige AAM-id: 112 </b> </p> <p> <b> Geen overeenkomende AAM-id: 0 </b> </p> <p> <b> Geen spoor gerealiseerd: 26730823 </b> </p> <p> <b> Verwerkte records: 40669900 </b> </p> <p> <b> Opgeslagen Verslagen: 13938958 </b> </p> <p> <b> Totale apparaten: 21 </b> </p> <p> <b> Totale signalen: 918878926 </b> </p> <p> <b> Totaal ongebruikte signalen: 660348376 </b> </p> <p> <b> Totale gerealiseerde eigenschappen: 258086908 </b> </p> <p> <b> Totaal verwijderde kenmerken: 0 </b> </p> <p> <b> Totaal aantal fouten is mislukt validatie: 0 </b> </p> <p> <b> Totale gebruikers die eigenschappen hebben die bevestiging ontbrak: 0 </b> </p> <p> <b> de begintijd van de Baan: 2018-05-17 18 :07: 49 </b> </p> <p> <b> Eind van de Baan tijd: 2018-05-17 18 :45: 02 </b> </p> </td> 
  </tr> 
 </tbody> 
</table>

De volgende tabel bevat rijen die overeenkomen met regels in het ontvangen e-mailbericht.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Lijn </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Bestandsnaam </td> 
   <td colname="col2"> <p>Lijst van alle binnenkomende dossiers die Adobe voor deze partner ontving die samen werden verwerkt. In het vorige voorbeeld-e-mailbericht is de partner-id 7 en de eigenaar-id van de gegevens 901. </p> <p>Het staartnummer (1,2,3...) is het splitsingsnummer dat door de klant of door de binnenkomende distributeur wordt toegevoegd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ontvangen records </td> 
   <td colname="col2"> <p>Het totale aantal records dat Adobe heeft ontvangen voor alle bestanden. In de meeste gevallen moet dit het totale aantal regels in inkomende bestanden zijn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fouten opmaken </td> 
   <td colname="col2"> <p>Aantal regels dat niet overeenkomt met de verwachte indeling. Deze lijnen waren niet herkenbaar door de binnenkomende baan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ongeldige AAM-id </td> 
   <td colname="col2"> <p>Aantal Audience Manager UUID's dat niet overeenkomt met de verwachte 38-cijferige indeling. De Audience Manager-UUID's die in het bestand worden verzonden, zijn geen getallen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Geen overeenkomende AAM-id </td> 
   <td colname="col2"> <p>Het totale aantal gebruikers voor wie Audience Manager geen overeenkomende UUID heeft gevonden. Deze bestanden zijn niet met de id gesynchroniseerd, dus Audience Manager kan de UUID niet opzoeken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Geen spoor gereproduceerd </td> 
   <td colname="col2"> <p>Aantal records waarbij geen van de signalen op de lijn is toegewezen aan een Audience Manager-kenmerk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verwerkte gegevens </td> 
   <td colname="col2"> <p>Het totale aantal records dat Audience Manager heeft verwerkt. In de meeste gevallen, zou dit aantal het zelfde als "Ontvangen Verslagen moeten zijn." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opgeslagen records </td> 
   <td colname="col2"> <p>Aantal records dat resulteert in gegevens die in het systeem moeten worden geladen = Records Verwerkt - Indelingsfouten - Ongeldige AAM-id's - Geen overeenkomstige AAM-id - Geen uitvoer gerealiseerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totaal aantal apparaten </td> 
   <td colname="col2"> <p>Aantal apparaten waarvoor gegevens in het systeem zijn geladen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totaal aantal signalen </td> 
   <td colname="col2"> <p> Het totale aantal signalen voor alle gebruikers over alle binnenkomende dossiers (totaal aantal sleutel/waardeparen in de verwerkte verslagen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totaal aantal ongebruikte signalen </td> 
   <td colname="col2"> <p>Het totale aantal ongebruikte signalen voor alle gebruikers in alle binnenkomende bestanden (sleutel-/waardeparen die niet aan Audience Manager-kenmerken zijn toegewezen). In de meeste gevallen betekent dit dat Audience Manager geen regels heeft gedefinieerd voor het signaal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totaal gerealiseerde kenmerken </td> 
   <td colname="col2"> <p>Het aantal Audience Manager-kenmerken voor alle gebruikers in alle binnenkomende bestanden op basis van de signalen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totaal aantal verwijderde kenmerken </td> 
   <td colname="col2"> <p> Het totale aantal verwijderde kenmerken voor alle gebruikers in alle binnenkomende bestanden. Voor volledige syncs, gebeurt dit als de gebruiker de eigenschap in een vorige looppas maar niet in de huidige looppas had. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Validatie van alle kenmerken is mislukt </td> 
   <td colname="col2"> <p>Geeft het aantal kenmerken aan die niet bij de gegevensbron horen die in de bestandsnaam is gedeclareerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totaal aantal gebruikers met eigenschappen die niet zijn gevalideerd </td> 
   <td colname="col2"> <p>Het aantal records met eigenschappen die niet zijn gevalideerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Begintijd taak </td> 
   <td colname="col2"> <p>De tijd waarop de binnenkomende taak begint. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eindtijd van taak </td> 
   <td colname="col2"> <p>De tijd waarop de binnenkomende taak eindigt. </p> </td> 
  </tr> 
 </tbody> 
</table>
