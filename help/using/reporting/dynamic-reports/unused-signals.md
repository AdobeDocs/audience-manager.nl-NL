---
description: Dit rapport retourneert een frequentietelling van alle ongebruikte gegevens die in uw voorraad zijn verzameld en naar Audience Manager zijn verzonden.
seo-description: Dit rapport retourneert een frequentietelling van alle ongebruikte gegevens die in uw voorraad zijn verzameld en naar Audience Manager zijn verzonden.
seo-title: Rapport Ongebruikte signalen
solution: Audience Manager
title: Rapport Ongebruikte signalen
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
translation-type: tm+mt
source-git-commit: dcc44161df89b44ca1a234070c4afbb0210dc723

---


# Rapport Ongebruikte signalen{#unused-signals-report}

Dit rapport retourneert een frequentietelling van alle ongebruikte gegevens die in uw voorraad zijn verzameld en naar Audience Manager zijn verzonden. Voor toegang tot dit rapport gaat u naar **Analytics > Audience Reports > Other Reports > Unused Signals**.

>[!NOTE]
>
>Als het bericht &quot;U hebt geen toegang tot Audience Reports&quot; wordt weergegeven, neemt u contact op met uw consultant van Audience Manager of de klantenservice om het rapport aan u voor te leggen.

![Screenshot van het rapport Ongebruikte signalen](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Overzicht

Een signaal is informatie van uw website die wordt doorgegeven aan [!DNL Audience Manager] in de vorm van [sleutelwaardeparen](../../reference/key-value-pairs-explained.md) (bijvoorbeeld, `color=blue, price>100, gender=female`enz.).

Ongebruikte signalen bestaan uit gegevens die u verzamelt, maar die niet aan een eigenschap zijn toegewezen. Het [!UICONTROL Unused Signals] rapport toont gegevens in een lijst door datum, sleutel, waarde, en frequentietelling. Om het even welk unmapped signaal dat binnen aan [!DNL Audience Manager] minstens 100 keer in een dag wordt overgegaan kwalificeert voor het [!UICONTROL Unused Signals] rapport.

Herzie dit rapport helpen orphaned signalen identificeren die aan nieuwe of bestaande eigenschappen kunnen worden in kaart gebracht.

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
   <td colname="col1"> <p><b>Zorg voor Trait Uniformity of voeg gerelateerde waarden toe aan één toets</b> </p> </td> 
   <td colname="col2"> <p>Herzie het rapport om verschillende waardevariaties voor een bepaald signaal rekenschap te geven. </p> <p>Stel bijvoorbeeld dat u een kenmerk hebt voor de staat "North Carolina", gedefinieerd in een sleutelwaardepaar als <code> c_state = North Carolina</code>. Het rapport kan u helpen naamvarianten vinden en die toevoegen aan het bezit (b.v., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). U kunt ook naamvarianten door het rapport vervangen en ze door een uniforme waarde op alle sites vervangen. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nieuwe kenmerken maken</b> </p> </td> 
   <td colname="col2"> <p>Controleer het rapport om te zien welke nieuwe waarden op een bepaalde sleutel worden doorgegeven. U kunt nieuwe sleutel-waardeparen tot stand brengen die op deze nieuwe waarden worden gebaseerd. </p> <p> <p>Opmerking:  Controleer het rapport om de week op waarden die vaak veranderen (bijvoorbeeld, toont, campagnes, beroemdheden, enz.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Niet-toegewezen waarden zoeken</b> </p> </td> 
   <td colname="col2"> <p>Controleer het rapport voor nummer 1. Het getal 1 in een <span class="wintitle"> rapport Ongebruikte signalen</span> vertegenwoordigt de waarde null. Dat is niet per se slecht. Het betekent eenvoudig dat een bepaalde sleutel geen bijbehorende waardetoewijzing heeft. Wanneer u veel van 1 waarden voor een belangrijke variabele ziet, raadpleegt u uw siteteam om te controleren of al uw pagina's correct zijn gecodeerd. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aanbevolen werkwijzen

Voer en controleer het [!UICONTROL Unused Signals] rapport:

* Nadat u een eigenschap hebt gemaakt of de regels van het updatetekenmerk hebt aangepast. Zo kunt u ervoor zorgen dat uw eigenschappen en regels op de juiste wijze zijn ingesteld. Het getal 1 in de resultaten geeft aan dat een nieuw kenmerk mogelijk niet correct is geconfigureerd.
* Twee weken of maandelijks. Geplande revisies helpen ervoor te zorgen dat de toewijzingen van de eigenschap up-to-date zijn.

>[!NOTE]
>
>Houd rekening met het volgende wanneer u naar ongebruikte waarden in het rapport zoekt. Er is een verschil in expressie tussen de twee onderstaande voorbeelden:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* In beide voorbeelden wordt een kenmerk getoond dat twee sleutelwaardeparen v en a bevat. De eerste expressie wordt vertaald in: de eigenschap bevat toets v met de waarde 1 de toets a met de waarde 23. [!UICONTROL AND NOT] De tweede expressie bevat key v met de waarde 1 [!UICONTROL AND] de key a met de waarde [!UICONTROL NOT EQUAL] 23.
* Gezien de twee verschillende hierboven uitdrukkingen, laten wij zeggen u in [!UICONTROL Unused Signals Report] voor de waarden zoekt die op sleutel a met om het even welke waarde verschillend dan 23 worden overgegaan, zult u slechts resultaten in het eerste geval verkrijgen omdat de waarden voor sleutel niet BIJ ALLE werden verzonden. In het tweede geval zijn andere waarden dan 23 verzonden, zodat sleutel a niet ongebruikt is.

## Bulkspoor maken

Contacteer uw vertegenwoordiger van de Oplossingen van de Partner als u een hoop van eigenschappen moet bulksgewijs tot stand brengen die op gegevens worden gebaseerd uit het [!UICONTROL Unused Signals] rapport worden verkregen.
