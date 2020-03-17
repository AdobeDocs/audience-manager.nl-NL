---
description: Bepaalt en beschrijft standaard en geserialiseerde sleutel-waarde paren.
keywords: integration code
seo-description: Bepaalt en beschrijft standaard en geserialiseerde sleutel-waarde paren.
seo-title: Belangrijke paar uitgelegd
solution: Audience Manager
title: Belangrijke paar uitgelegd
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Belangrijke paar uitgelegd{#key-value-pairs-explained}

Bepaalt en beschrijft standaard en geserialiseerde sleutel-waarde paren.

<!-- 

c_key_value_explained.xml

 -->

Een sleutelwaardepaar bestaat uit twee gerelateerde gegevenselementen: Een sleutel, die een constante is die de gegevensset definieert (bijvoorbeeld geslacht, kleur, prijs), en een waarde, die een variabele is die tot de set behoort (bijvoorbeeld mannelijk/vrouwelijk, groen, 100). Volledig gevormd, kon een zeer belangrijk-waardepaar als dit kijken:

* `gender = male`
* `color = green`
* `price > 100`

## Standaard en seriële sleutelwaardeparen {#standard-serialized-pairs}

Doelen accepteren sleutelwaardegegevens in *`standard`* of *`serialized`* formaat. Bij de standaardopmaak worden gegevens in afzonderlijke sleutelwaardeparen ingedeeld. Elke toets wordt expliciet vermeld, zelfs wanneer deze opnieuw wordt gebruikt om een andere waarde te definiëren. Door geserialiseerde opmaak daarentegen worden meerdere waarden omgezet in één set die door één toets wordt gedefinieerd. Ook, in een geserialiseerd paar, wordt een speciale indicator gebruikt om de waarden binnen de zeer belangrijk-waardereeks te scheiden. Tot slot kunnen de standaard en geserialiseerde sleutel-waarden enige of veelvoudige waarden bevatten. De volgende tabel bevat voorbeelden van standaardindelingen en indelingen voor seriële sleutels en waarden.

| Opmaak | Enkele toets | Belangrijke paren |
|---|---|---|
| **Standaard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Gesserveerd** | `x=1;2` | `x=1;2&y=3;4` |



## Toetsen, scheidingstekens en scheidingstekens {#keys-delimiters-separators}

Wanneer u werkt met geserialiseerde gegevens, moet u de tekens opgeven die waarden scheiden *binnen* en *tussen* de sleutelwaardeparen. Elementen in sleutelwaardeparen worden als volgt gedefinieerd:

* **Sleutel:** Een unieke id in het sleutelwaardepaar.
* **Waardescheidingsteken:** Hiermee scheidt u afzonderlijke sleutel-waardeparen.
* **Scheidingsteken hoofdwaarde:** Scheidt een sleutel van de waarden binnen een zeer belangrijk-waardepaar.
* **Seriescheidingsteken:** Scheidt individuele waarden binnen geserialiseerde sleutel-waarde paren.

## Standaard en geserialiseerde sleutelwaardeelementen {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Voorbeeld </th> 
   <th colname="col3" class="entry"> Sleutel </th> 
   <th colname="col4" class="entry"> Scheidingsteken sleutelwaarde </th> 
   <th colname="col5" class="entry"> Scheidingsteken voor sleutelwaarde </th> 
   <th colname="col6" class="entry"> Seriescheidingsteken </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Eén toets</b> <p>(standaard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n.v.t. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sleutelwaardeparen</b> <p>(standaard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Eén toets</b> <p>(serieel) </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n.v.t. </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sleutelwaardeparen</b> (serieel) </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

