---
description: Zoek naar één of veelvoudige signalen, die op hun respectieve sleutel-waarde paren worden gebaseerd.
seo-description: Zoek naar één of veelvoudige signalen, die op hun respectieve sleutel-waarde paren worden gebaseerd.
seo-title: Signalen zoeken op sleutelwaardeparen
title: Signalen zoeken op sleutelwaardeparen
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
translation-type: tm+mt
source-git-commit: 2206b5e40f7024084953fed52bb02fcc46ea36f1

---


# Signalen zoeken op sleutelwaardeparen {#search-signals-by-key-value-pairs}

Zoek naar één of veelvoudige signalen, die op hun respectieve sleutel-waarde paren worden gebaseerd.
Als u naar meer dan één signaal wilt zoeken, klikt u op de knop ![Toevoegen](assets/icon_add.png) . Voer de sleutelwaardeparen in waarnaar u wilt zoeken en gebruik vervolgens de volgende filters om de resultaten te beperken.

* **Signaalstatus**: zoeken naar signalen inbegrepen in eigenschappen, ongebruikte signalen, of allebei.
* **Records weergeven voor**: Selecteer het tijdinterval waarin om naar ontvangen signalen te zoeken.
* **Minimumaantal**: tonen slechts signalen met het gespecificeerde minimum totale aantal in het geselecteerde interval.

>[!IMPORTANT]
>
>Voor een gestroomlijnde gebruikerservaring zijn de zoekresultaten van sleutelwaardepaarten gebaseerd op gegevensbemonstering. Zie [Gegevensbemonstering en foutenpercentages](/help/using/reporting/report-sampling.md) voor details over hoe [!DNL Audience Manager] gegevensbemonstering gebruikt en waarom kleine resultaatvariaties kunnen verschijnen wanneer het vergelijken van zeer belangrijk-waardeonderzoek met algemene onderzoeken.

Wanneer het zoeken naar signalen die veelvoudige zeer belangrijk-waardeparen gebruiken, [!DNL Audience Manager] verbindt de paren gebruikend de logische exploitant **AND** . Stel dat u een zoekopdracht uitvoert met de volgende sleutelwaardeparen:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Deze zoekopdracht retourneert alleen resultaten die in aanmerking komen voor alle drie de filters in dezelfde aanroep: `c_creative == "12345"` `AND` `c_product == "smartphone"``AND` . `c_location == "europe"`.

![](assets/signals-search.png)

## Signalen die zijn uitgesloten van Signal Search {#excluded-signals}

De belangrijkste variabelen die door de Manager van de Auditie worden gebruikt en door de `d_` en `h_` prefixen worden voorgefixeerd worden niet bedekt door [!UICONTROL Signals Search]. Zie [Voorvoegselvereisten voor belangrijke variabelen](../../traits/trait-variable-prefixes.md) voor meer informatie.

## Ongevoeligheid van hoofdletters en kleine letters zoeken {#case-insensitivity}

De velden voor het zoeken naar sleutels en waarden zijn niet hoofdlettergevoelig. Het belangrijkste onderzoeksgebied omvat auto-voltooide suggesties.

![](assets/signal-search-suggestions.png)

Laten we zeggen dat we de volgende signalen [!DNL Audience Manager] hebben ontvangen:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Wanneer u `product` in het belangrijkste onderzoeksgebied ingaat, ontvangt u automatisch voltooide suggesties voor `productCategory`, `newProduct`, `PRODUCT`, en `product`.

Op dezelfde manier wanneer u naar `product == phone`zoekt, keert [!UICONTROL Data Explorer] resultaten voor zowel `PRODUCT == phone` als `product == PHONE`.
De gemaakte fouten in de modus Achtergevuld zijn niet hoofdlettergevoelig. Een eigenschap die het signaal met het zeer belangrijk-waardepaar bevat kwalificeert `PRODUCT == SMARTPHONE` ook het signaal met het zeer belangrijk-waardepaar `product == smartphone`.