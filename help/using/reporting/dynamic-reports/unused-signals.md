---
description: Dit rapport retourneert een frequentietelling van alle ongebruikte gegevens die in je voorraad zijn verzameld en naar Audience Manager zijn verzonden.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Rapport Ongebruikte signalen
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 9c980b8fd5c3cb6ba7b3031726da726ee5caeec6
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Rapport Ongebruikte signalen{#unused-signals-report}

Dit rapport retourneert een frequentietelling van alle ongebruikte gegevens die in je voorraad zijn verzameld en naar Audience Manager zijn verzonden. Om tot dit rapport toegang te hebben, navigeer aan **Analytics > de Rapporten van het publiek > Andere Rapporten > Ongebruikte Signalen**.

>[!NOTE]
>
>Als u het bericht &quot;U hebt geen toegang tot Audience Reports&quot; ziet, neemt u contact op met uw Audience Manager-consultant of de klantenservice om het rapport aan u voor te leggen.

![&#x200B; Schermafbeelding van het Ongebruikte Rapport van Signalen &#x200B;](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Overzicht

Een signaal is informatie van uw website die binnen aan [!DNL Audience Manager] in de vorm van [&#x200B; wordt overgegaan sleutel-waarde paren &#x200B;](../../reference/key-value-pairs-explained.md) (b.v., `color=blue, price>100, gender=female`, enz.).

Ongebruikte signalen bestaan uit gegevens die u verzamelt, maar die niet aan een eigenschap zijn toegewezen. Het [!UICONTROL Unused Signals] rapport toont gegevens in een lijst door datum, sleutel, waarde, en frequentietelling. Elk niet-toegewezen signaal dat ten minste 100 keer per dag wordt doorgegeven aan [!DNL Audience Manager] , komt in aanmerking voor het [!UICONTROL Unused Signals] -rapport.

Ongebruikte signalen worden gedurende 45 dagen opgeslagen en daarna weggegooid. Het ongebruikte signaalrapport toont gegevens van de afgelopen 10 dagen.

Herzie dit rapport helpen orphaned signalen identificeren die aan nieuwe of bestaande eigenschappen kunnen worden toegewezen.

>[!NOTE]
>
>Geef een sleutel- of waardennaam op in de zoekvelden om de resultaten te beperken tot specifieke records.

## Gevallen gebruiken

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Voorbeelden </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> verzeker de Uniformiteit van het Staal of voeg Verwante Waarden aan Één enkele Sleutel </b> toe </p> </td> 
   <td colname="col2"> <p>Herzie het rapport om verschillende waardevariaties voor een bepaald signaal rekenschap te geven. </p> <p>Stel dat u een kenmerk hebt voor de status "North Carolina", gedefinieerd in een sleutelwaardepaar als <code> c_state = North Carolina</code> . Het rapport kan u helpen naamvarianten zoeken en deze aan de eigenschap toevoegen (bijvoorbeeld <code> c_state = North Carolina, NC, N.C., NCarolina</code> ). U kunt ook naamvarianten door het rapport vervangen en ze door een uniforme waarde op alle sites vervangen. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> creeer Nieuwe Lijsten </b> </p> </td> 
   <td colname="col2"> <p>Controleer het rapport om te zien welke nieuwe waarden op een bepaalde sleutel worden doorgegeven. U kunt nieuwe sleutel-waardeparen tot stand brengen die op deze nieuwe waarden worden gebaseerd. </p> <p> <p>Opmerking: controleer het rapport twee keer per week op waarden die vaak veranderen (bijvoorbeeld shows, campagnes, beroemdheden, enz.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> vindt Ontvangen Waarden </b> </p> </td> 
   <td colname="col2"> <p>Controleer het rapport voor nummer 1. Het getal 1 in een rapport <span class="wintitle"> Ongebruikte signalen </span> vertegenwoordigt een null-waarde. Dat is niet per se slecht. Het betekent eenvoudig dat een bepaalde sleutel geen bijbehorende waardetoewijzing heeft. Wanneer u veel van 1 waarden voor een belangrijke variabele ziet, raadpleegt u uw siteteam om te controleren of al uw pagina's correct zijn gecodeerd. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aanbevolen procedures

Voer het [!UICONTROL Unused Signals] -rapport uit en controleer het:

* Nadat u een eigenschap hebt gemaakt of de regels van het updatetekenmerk hebt aangepast. Zo kunt u ervoor zorgen dat uw eigenschappen en regels op de juiste wijze zijn ingesteld. Het getal 1 in de resultaten geeft aan dat een nieuw kenmerk mogelijk niet correct is geconfigureerd.
* Twee weken of maandelijks. Geplande revisies helpen ervoor te zorgen dat de toewijzingen van de eigenschap up-to-date zijn.

>[!NOTE]
>
>Houd rekening met het volgende wanneer u naar ongebruikte waarden in het rapport zoekt. Er is een verschil in expressie tussen de twee onderstaande voorbeelden:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23)
* In beide voorbeelden wordt een kenmerk getoond dat twee sleutelwaardeparen v en a bevat. De eerste expressie wordt omgezet in: de eigenschap bevat toets v met de waarde 1 [!UICONTROL AND NOT] de toets a met de waarde 23. De tweede expressie bevat key v met de waarde 1 [!UICONTROL AND] de key a met de waarde [!UICONTROL NOT EQUAL] 23.
* Gezien de twee verschillende bovenstaande expressies, laten we zeggen dat u in [!UICONTROL Unused Signals Report] naar de waarden zoekt die op key a worden doorgegeven met een andere waarde dan 23, zult u alleen resultaten in het eerste geval krijgen omdat waarden voor key niet BIJ ALL werden verzonden. In het tweede geval zijn andere waarden dan 23 verzonden, zodat sleutel a niet ongebruikt is.

## Bulkspoor maken

Neem contact op met de vertegenwoordiger van de Partner Solutions als u een groot aantal kenmerken moet maken op basis van gegevens die u uit het [!UICONTROL Unused Signals] -rapport hebt ontvangen.
