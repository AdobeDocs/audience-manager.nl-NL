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
ht-degree: 0%

---

# De signalen van het onderzoek door zeer belangrijke paren {#search-signals-by-key-value-pairs}

Zoek naar één of veelvoudige signalen, die op hun respectieve sleutel-waarde paren worden gebaseerd.
Om naar meer dan één signaal te zoeken, klik ![ toevoegen ](assets/icon_add.png) knoop. Voer de sleutelwaardeparen in waarnaar u wilt zoeken en gebruik vervolgens de volgende filters om de resultaten te beperken.

* **status van het Signaal**: onderzoek naar signalen inbegrepen in eigenschappen, ongebruikte signalen, of allebei.
* **verslagen van de Mening voor**: selecteer het tijdinterval waarin om naar ontvangen signalen te zoeken.
* **Minimumtellingen**: vertoning slechts signalen met de gespecificeerde minimum totale telling in het geselecteerde interval.

>[!IMPORTANT]
>
>Voor een gestroomlijnde gebruikerservaring zijn de zoekresultaten van sleutelwaardepaarten gebaseerd op gegevensbemonstering. Zie [ de Steekproef van Gegevens en Tarieven van de Fout ](/help/using/reporting/report-sampling.md) voor details over hoe [!DNL Audience Manager] gegevensbemonstering gebruikt en waarom de lichte resultaatvariaties wanneer het vergelijken van zeer belangrijk-waardeonderzoek aan algemene onderzoeken kunnen verschijnen.

Wanneer het zoeken naar signalen die veelvoudige zeer belangrijk-waardeparen gebruiken, [!DNL Audience Manager] verbindt de paren gebruikend de logische **EN** exploitant. Stel dat u een zoekopdracht uitvoert met de volgende sleutelwaardeparen:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Deze zoekopdracht levert alleen resultaten op die in aanmerking komen voor alle drie de filters in dezelfde aanroep: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"` .

![](assets/signals-search.png)

## Signalen die zijn uitgesloten van signaalzoekopdracht {#excluded-signals}

Keyvariabelen die door Audience Manager worden gebruikt en die door de voorvoegsels `d_` en `h_` worden voorgefixeerd, worden niet door [!UICONTROL Signals Search] omringd. Zie [ Vereisten van de Prefix voor Zeer belangrijke Variabelen ](../../traits/trait-variable-prefixes.md) voor details.

## Hoofdlettergevoeligheid en automatisch zoeken {#case-insensitivity}

De velden voor het zoeken naar sleutels en waarden zijn hoofdlettergevoelig. Het belangrijkste onderzoeksgebied omvat auto-voltooide suggesties.

![](assets/signal-search-suggestions.png)

Laten we zeggen dat [!DNL Audience Manager] de volgende signalen heeft ontvangen:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Wanneer u `product` invoert in het sleutelzoekveld, ontvangt u automatisch aangevulde suggesties voor `productCategory` en `product` .

Op dezelfde manier retourneert `product == PHONE` alleen resultaten voor [!UICONTROL Data Explorer] wanneer u naar `product == PHONE` zoekt.

Achtergevulde taakrealisaties zijn ook hoofdlettergevoelig. Een eigenschap die het signaal bevat met het sleutelwaardepaar `PRODUCT == SMARTPHONE` kwalificeert het signaal niet met het sleutelwaardepaar `product == smartphone`.
