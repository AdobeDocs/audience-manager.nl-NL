---
description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw rekening van de Audience Manager te richten.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting met sleutels op platformniveau
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 366589d51601f438999bfdc6a10c306eb1186742
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 3%

---

# Geotargeting met sleutels op platformniveau {#geotargeting-with-platform-level-keys}

Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw rekening van de Audience Manager te richten.

<!-- c_tb_platform_vars.xml -->

## Doel van variabelen op het niveau van de Platform {#platform-variables}

Met variabelen op Platform-niveau kunt u gegevens van een bepaalde site gebruiken en deze beschikbaar maken voor alle eigenschappen in uw [!DNL Audience Manager] account. Deze variabelen worden gevormd door [sleutelwaardeparen](../../reference/key-value-pairs-explained.md) met de toets vooraf ingesteld door `d_` zoals hieronder weergegeven.

## Waarden toevoegen aan toetsen op Platform-niveau {#adding-values}

Voor sommige toetsen op platformniveau kunt u zelf de waarde opgeven. Met andere toetsen worden de sleutels gekoppeld aan de bijbehorende [!DNL IP] adressen die op een gebeurtenisvraag worden overgegaan. In beide gevallen moet u nog steeds de waarde opgeven wanneer u kenmerken maakt [!UICONTROL Trait Builder].

## Door de gebruiker gedefinieerde toetsen op het niveau van het Platform {#user-defined-keys}

Als u reeds hebt, of een proces vestigen om zeer belangrijk-waardeparen te bepalen en te verzamelen, dan gebruik deze optie. Als u sleutels wilt gebruiken die door IP adres vooraf worden bepaald, ga aan de volgende sectie verder. In het geval van user-defined sleutels, specificeert u de waarde wanneer het bouwen van eigenschappen met deze zeer belangrijke-waardeparen:

| Sleutel | Voor gerichte |
|---|---|
| `d_zx` | Postcode (bijvoorbeeld `d_zx=10022`). |

## Platform-vlakke Sleutels die door IP Adres worden bepaald {#keys-ip-address}

We werken met [Digitale gezant](https://www.digitalenvoy.com/) de demografische en geografische gegevens voor de onderstaande sleutels te verkrijgen en bij te werken. De waarden voor deze toetsen worden bepaald door [!DNL IP] wordt gericht op overeenkomstige geografische en demografische gegevens. Nochtans, zult u nog de waardeparameter moeten ingaan wanneer het creëren van het sleutel-waardepaar binnen [!UICONTROL Trait Builder].

| Sleutel | Voor gerichte |
|--- |--- |
| d_area_code | [Gebiedscodes Noord-Amerika](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Bijvoorbeeld: <ul><li>**Trait**: d_area_code=801</li><li>**Naam dienblad**: Utah</li></ul> |
| d_city | Steden en steden. Download de [lijst met steden](assets/d_city.txt).  Bijvoorbeeld: <ul><li>Trait: d_city=bonn</li><li>Naam dienstreis: Bonn</li></ul> **Tip**: U kunt `d_city` gekoppeld met `d_country` om er zeker van te zijn dat u zich niet richt op twee steden met dezelfde naam in verschillende landen . U kunt zelfs specifieker in uw richten door te gebruiken `d_postal_code`. |
| d_country | De waarden komen overeen met de ISO-landencodes. Voor een doorzoekbare lijst met codes raadpleegt u de [Platform voor online surfen op ISO](https://www.iso.org/obp/ui/#home). <br>  Het is het enige speciale geval dat zich niet houdt aan ISO 3166. Gebruik &quot;UK&quot; in plaats van &quot;GB&quot; voor doelwit in het Verenigd Koninkrijk.  Om zich op de Nederlandse Antillen te richten, is de code &quot;AN&quot; sinds 2010 afgekeurd. Het gebied is ontbonden in vijf afzonderlijke territoriale eenheden. De implicatie is dat voor het richten in de Nederlandse Antillen, u niet &quot;AN,&quot;maar een combinatie landcodes voor &quot;CW,&quot;SX,&quot;en &quot;BQ&quot;zou moeten gebruiken.  Bijvoorbeeld:  <br>  Trait: d_country=CZ  <br>  Naam dienstreis: Tsjechië <br>  Trait: d_country=UK <br>  Naam dienstreis: Verenigd Koninkrijk  <br>  Trait: d_country=CW OR d_country=SX OR d_country=BQ  <br>  Naam dienstreis: Nederlandse Antillen |
| d_dma_code | DMA-codes voor metropolitane gebieden. Download de [DMA-gebiedslijst](assets/DMAregions.csv) (CSV-indeling).  Bijvoorbeeld: <ul><li>Trait: d_dma_code=807</li><li>Naam dienstreis: San Francisco</li></ul> |
| d_lat | Latitude (bv. d_lat=40,75). Download de [latitudenlijst](assets/d_lat.txt). |
| d_long | Lengtegraad (bv. d_long=73,98). Download de [lengtenlijst](assets/d_long.txt). |
| d_postal_code | ZIP-codes (exclusief de uitgebreide +4-code). Download de  [postcodes](assets/d_postal_code.txt).  Bijvoorbeeld: <ul><li>Trait: d_postal_code=84004 </li><li>Naam dienstreis: Alpen</li></ul> |
| d_state | Afkorting van 2 tekens voor een Amerikaanse staat. Download de [Statuscodes](assets/d_state.txt).  Bijvoorbeeld: <ul><li>Trait: d_state=NY </li><li>Naam dienstreis: New York</li></ul>d_state bevat herhaalde waarden voor verschillende staten in verschillende landen. Zo komt d_state == &quot;on&quot; bijvoorbeeld overeen met meerdere statussen: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibië). We raden je aan dit signaal te koppelen aan anderen, zoals d_country, voor specifiekere oriëntatie. |
| d_region | Regionale alfanumerieke id&#39;s. Download de [lijst met regio&#39;s](assets/Country_RegionCodes_City.csv).  Vervolgens kunt u deze lijst gebruiken om regio-id&#39;s aan regionamen te koppelen. |
| d_isp | ISP/organisatie. Download de [ISP-lijst](assets/d_isp.txt). |

De lijst van [alle locatiegebaseerde signalen](assets/all.txt) omvat alle bovenstaande signalen in de volgende volgorde: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Voorvoegselvereisten voor belangrijke variabelen](../../features/traits/trait-variable-prefixes.md)

