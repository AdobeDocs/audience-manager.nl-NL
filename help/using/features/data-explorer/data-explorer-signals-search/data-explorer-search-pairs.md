---
description: Zoek naar één of veelvoudige signalen, die op hun respectieve sleutel-waarde paren worden gebaseerd.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Signalen zoeken op sleutelwaardeparen
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# De signalen van het onderzoek door zeer belangrijke paren {#search-signals-by-key-value-pairs}

Zoek naar één of veelvoudige signalen, die op hun respectieve sleutel-waarde paren worden gebaseerd.
Als u naar meer dan één signaal wilt zoeken, klikt u op de knop ![Toevoegen](assets/icon_add.png) knop. Voer de sleutelwaardeparen in waarnaar u wilt zoeken en gebruik vervolgens de volgende filters om de resultaten te beperken.

* **Signaalstatus**: zoeken naar signalen inbegrepen in eigenschappen, ongebruikte signalen, of allebei.
* **Records weergeven voor**: Selecteer het tijdinterval waarin om naar ontvangen signalen te zoeken.
* **Minimumaantal**: tonen slechts signalen met het gespecificeerde minimum totale aantal in het geselecteerde interval.

>[!IMPORTANT]
>
>Voor een gestroomlijnde gebruikerservaring zijn de zoekresultaten van sleutelwaardepaarten gebaseerd op gegevensbemonstering. Zie [Gegevensbemonstering en foutenpercentages](/help/using/reporting/report-sampling.md) voor meer informatie over hoe [!DNL Audience Manager] gebruikt gegevensbemonstering en waarom kleine resultaatvariaties kunnen verschijnen wanneer het vergelijken van zeer belangrijk-waardeonderzoek met algemene onderzoeken.

Wanneer het zoeken naar signalen die veelvoudige zeer belangrijk-waardeparen gebruiken, [!DNL Audience Manager] verbindt de paren gebruikend logisch **EN** operator. Stel dat u een zoekopdracht uitvoert met de volgende sleutelwaardeparen:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Deze zoekopdracht retourneert alleen resultaten die in aanmerking komen voor alle drie de filters in dezelfde aanroep: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Signalen die zijn uitgesloten van signaalzoekopdracht {#excluded-signals}

Sleutelvariabelen die door de Audience Manager worden gebruikt en vooraf door de `d_` en `h_` voorvoegsels worden niet vervangen door [!UICONTROL Signals Search]. Zie [Voorvoegselvereisten voor belangrijkste variabelen](../../traits/trait-variable-prefixes.md) voor meer informatie.

## Hoofdlettergevoeligheid en automatisch zoeken {#case-insensitivity}

De velden voor het zoeken naar sleutels en waarden zijn hoofdlettergevoelig. Het belangrijkste onderzoeksgebied omvat auto-voltooide suggesties.

![](assets/signal-search-suggestions.png)

Laten we zeggen [!DNL Audience Manager] de volgende signalen hebben ontvangen:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Wanneer u `product` in het sleutelzoekveld ontvangt u automatisch aangevulde suggesties voor `productCategory` en `product`.

Op dezelfde manier wanneer u zoekt naar `product == PHONE`, [!UICONTROL Data Explorer] retourneert alleen resultaten voor `product == PHONE`.

Achtergevulde taakrealisaties zijn ook hoofdlettergevoelig. Een eigenschap die het signaal met het zeer belangrijk-waardepaar bevat `PRODUCT == SMARTPHONE` kwalificeert niet het signaal met sleutel-waarde paar `product == smartphone`.
