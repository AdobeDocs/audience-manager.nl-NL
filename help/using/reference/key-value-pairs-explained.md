---
description: Definieert en beschrijft standaard en geserialiseerde sleutel-waarde paren.
keywords: integratiecode
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: Sleutelwaardeparen
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 2%

---

# Sleutelwaardeparen{#key-value-pairs-explained}

Definieert en beschrijft standaard en geserialiseerde sleutel-waarde paren.

<!-- 

c_key_value_explained.xml

 -->

Een sleutelwaardepaar bestaat uit twee gerelateerde gegevenselementen: Een sleutel, die een constante is die de gegevensset definieert (bijvoorbeeld geslacht, kleur, prijs), en een waarde, die een variabele is die tot de set behoort (bijvoorbeeld mannelijk/vrouwelijk, groen, 100). Volledig gevormd, kon een zeer belangrijk-waardepaar als dit kijken:

* `gender = male`
* `color = green`
* `price > 100`

## Standaard en seriële sleutelwaardeparen {#standard-serialized-pairs}

Doelen accepteren sleutelwaardegegevens in *`standard`* of *`serialized`* gebruiken. Bij de standaardopmaak worden gegevens in afzonderlijke sleutelwaardeparen ingedeeld. Elke toets wordt expliciet vermeld, zelfs wanneer deze opnieuw wordt gebruikt om een andere waarde te definiëren. Door geserialiseerde opmaak daarentegen worden meerdere waarden omgezet in één set die door één toets wordt gedefinieerd. Ook, in een geserialiseerd paar, wordt een speciale indicator gebruikt om de waarden binnen de zeer belangrijk-waardereeks te scheiden. Tot slot kunnen de standaard en geserialiseerde sleutel-waarden enige of veelvoudige waarden bevatten. De volgende tabel bevat voorbeelden van standaardindelingen en indelingen voor seriële sleutels en waarden.

| Opmaak | Enkele toets | Belangrijke paren |
|---|---|---|
| **Standaard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Gesserveerd** | `x=1;2` | `x=1;2&y=3;4` |



## Toetsen, scheidingstekens en scheidingstekens {#keys-delimiters-separators}

Wanneer u werkt met geserialiseerde gegevens, moet u de tekens opgeven die waarden scheiden *binnen* en *Tussen* de sleutel-waardeparen. Elementen in sleutelwaardeparen worden als volgt gedefinieerd:

* **Sleutel:** Een unieke id in het sleutelwaardepaar.
* **Waardescheidingsteken:** Hiermee scheidt u afzonderlijke sleutel-waardeparen.
* **Scheidingsteken hoofdwaarde:** Scheidt een sleutel van de waarden binnen een zeer belangrijk-waardepaar.
* **Seriescheidingsteken:** Scheidt individuele waarden binnen geserialiseerde sleutel-waarde paren.

## Standaard en geserialiseerde sleutelwaardeelementen {#standard-serialized-key-value-elements}


| Type | Voorbeeld | Sleutel | Scheidingsteken sleutelwaarde | Scheidingsteken voor sleutelwaarde | Seriescheidingsteken |
|---------|----------|---------|---------|----------|---------|
| **Eén toets** (standaard) | `x=1&x=2` | `x` | `=` | `&` | n.v.t. |
| **Sleutelwaardeparen** (standaard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n.v.t. |
| **Eén toets** (serieel) | `x=1;2;3` | `x` | `=` | n.v.t. | `;` |
| **Sleutelwaardeparen** (serieel) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
