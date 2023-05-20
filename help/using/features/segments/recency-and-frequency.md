---
description: In de Bouwer van het Segment, laten de recentie en de frequentie u bezoekers segmenteren die op acties voorkomen of zich over een bepaald dagelijks interval herhalen.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: Recentheid en frequentie
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 2%

---

# Recentheid en frequentie {#recency-and-frequency}

In [!UICONTROL Segment Builder]kunt u bezoekers segmenteren op basis van acties die plaatsvinden of die gedurende een ingesteld dagelijks interval worden herhaald.

Audience Manager definieert [!DNL recency] en [!DNL frequency] als volgt:

* **[!UICONTROL Recency]:** Hoe recent een gebruiker voor één (of meerdere) bekeken of gekwalificeerd [!UICONTROL traits].
* **[!UICONTROL Frequency]:** De snelheid waarmee een gebruiker een (of meer) gebruiker heeft bekeken of gekwalificeerd [!UICONTROL traits].

[!UICONTROL Recency] en [!UICONTROL Frequency] met instellingen kunt u bezoekers segmenteren op basis van hun werkelijke (of waargenomen) interesse voor een site, sectie of bepaalde creatieve functies. Gebruikers die bijvoorbeeld in aanmerking komen voor een segment met hoge eisen inzake recentie/frequentie, hebben wellicht meer belangstelling voor een site of een product dan gebruikers die minder vaak of minder vaak een bezoek brengen.

## Locatie van [!UICONTROL Recency and Frequency] Instellingen {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] en [!UICONTROL Frequency] de instellingen bevinden zich in de [!UICONTROL Basic View] van de [!UICONTROL Traits] deelvenster. Klik het klokpictogram om deze controles bloot te stellen.

![](assets/recency_frequency.png)

## Beperkingen en regels {#limitations-rules}

U kunt deze limieten en regels controleren en begrijpen wanneer u de frequentie en frequentie wilt toepassen op kenmerken in uw segmenten.

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limiet of regel </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Minimumwaarde</b> </p> </td> 
   <td colname="col2"> <p>De frequentie moet groter zijn dan 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Typen sporen</b> </p> </td> 
   <td colname="col2"> <p>U kunt recentiecontroles op regel-gebaseerde en omslageigenschappen slechts toepassen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Treinen van derden</b> </p> </td> 
   <td colname="col2"> <p>U kunt geen recentieregels op individuele derdeattributen of handelsgroepen plaatsen die derdetrekken bevatten. De frequentie en de frequentie zijn alleen van toepassing op uw eigen kenmerken. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limiet of regel </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Treinen van derden</b> </p> </td> 
   <td colname="col2"> <p>U kunt geen frequentieregels instellen voor individuele eigenschappen van derden of groepen van handelsmerken die eigenschappen van derden bevatten. De frequentie en de frequentie zijn alleen van toepassing op uw eigen kenmerken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Typen sporen</b> </p> </td> 
   <td colname="col2"> <p>U kunt frequentiecontroles op regel-gebaseerde en omslageigenschappen slechts toepassen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Recente vereisten</b> </p> </td> 
   <td colname="col2"> <p>U kunt frequentievereisten configureren <i>zonder</i> noodvereisten configureren. Stel gewoon een frequentiewaarde in en laat het veld voor recentie leeg. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regels voor profielsamenvoeging</b> </p> </td> 
   <td colname="col2"> <p>Zie <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs en Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeelden van recentie {#recency-examples}

Hieronder volgen twee voorbeelden van de werking van recentiepunten, afhankelijk van uw selectie in de gebruikersinterface:

### Een operator gebruiken die kleiner is dan of gelijk is aan (&lt;=)

![Kleiner dan gelijk aan](assets/less-than-equal-to.png)

In dit voorbeeld selecteert u de operator &lt;=, zoals wordt weergegeven in de schermafbeelding. Dit kwalificeert uw gebruiker voor [!UICONTROL segment] indien zij in aanmerking komen voor een van de drie [!UICONTROL traits] ten minste driemaal in de laatste vijf dagen. In de onderstaande tijdlijn ziet u de [!UICONTROL segment] kwalificatie op het tijdstip waarop [!UICONTROL segment] wordt gemaakt op 1 oktober en tien dagen later.

![Laatste vijf dagen](assets/last-5-days.png)

### Een operator (=>) gebruiken die groter is dan of gelijk is aan

![Groter dan gelijk aan](assets/greater-than-equal-to.png)

In dit voorbeeld selecteert u de operator =>, zoals in de schermafbeelding wordt getoond. Dit kwalificeert uw gebruiker voor [!UICONTROL segment] indien zij in aanmerking komen voor een van de drie [!UICONTROL traits] minimaal drie keer tussen hun eerste kwalificatie op het Audience Manager-platform en de afsluittijd vijf dagen geleden. In de onderstaande tijdlijn ziet u de [!UICONTROL segment] kwalificatie op het tijdstip waarop [!UICONTROL segment] wordt gemaakt op 1 oktober en tien dagen later.

![Eerdere kwalificatie](assets/earlier-qualification.png)


## Voorbeelden van frequentiecortering {#frequency-capping}

De frequentie-begrensende uitdrukkingen omvatten alle gebruikers het waarvan aantal [!UICONTROL trait] de realisaties liggen onder de gewenste waarde . Hier volgen enkele voorbeelden van Rechts en Verkeerd:

* Onjuist - De uitdrukking `frequency([1000T]) <= 5` inclusief alle gebruikers die de [!UICONTROL trait] met de id &quot;1000&quot; maximaal vijf keer, maar ook voor gebruikers die het [!UICONTROL trait]. Daarom valideert Audience Manager deze expressie niet om redenen van prestaties, omdat er te veel gebruikers in aanmerking zouden komen voor de functie [!UICONTROL segment].

* Rechts - Als u alle gebruikers wilt opnemen die de [!UICONTROL trait] met ID &quot;1000&quot;een maximum van vijf keer, voeg een andere voorwaarde aan de uitdrukking toe, om ervoor te zorgen de gebruikers voor kwalificeren [!UICONTROL trait] ten minste eenmaal:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Rechts - Als u eisen voor recentie/frequentie wilt hebben die lager zijn dan een bepaald aantal tijden of dagen, voegt u zich bij die vereisten [!UICONTROL trait] aan een andere `AND` operator. Met het voorbeeld in het eerste opsommingsteken wordt deze expressie geldig wanneer deze wordt gecombineerd met een andere expressie [!UICONTROL trait] zoals hieronder getoond: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Rechts - Voor gebruiksgevallen met frequentiecorrectie kunt u een [!UICONTROL segment] soortgelijke regel : `(frequency([1000T] <= 2D) >= 5)`. Deze expressie omvat alle gebruikers die de [!UICONTROL trait] met de ID &quot;1000&quot; in de afgelopen twee dagen ten minste vijf keer. Frequentiecontrole instellen door deze te verzenden [!UICONTROL segment] naar de advertentieserver met een `NOT` op de [!UICONTROL segment] in de advertentieserver. Deze aanpak levert betere prestaties bij [!DNL Audience Manager] terwijl zij nog steeds hetzelfde doel dienen voor het aftappen van frequenties.

>[!MORELIKETHIS]
>
>* [Besturingselementen voor Segment Builder: Sectie Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Gebruikte codesyntaxis in de Segment Expression Editor](../../features/segments/segment-code-syntax.md)

