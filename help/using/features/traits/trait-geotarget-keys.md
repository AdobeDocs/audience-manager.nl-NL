---
description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw rekening van de Manager van de Publiek te richten.
seo-description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw rekening van de Manager van de Publiek te richten.
seo-title: Geotarcering met toetsen op platformniveau
solution: Audience Manager
title: Geotarcering met toetsen op platformniveau
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Geotarcering met toetsen op platformniveau {#geotargeting-with-platform-level-keys}

Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw rekening van de Manager van de Publiek te richten.

<!-- c_tb_platform_vars.xml -->

## Doel van variabelen op platformniveau {#platform-variables}

Met variabelen op platformniveau kunt u gegevens van een bepaalde site gebruiken en deze beschikbaar maken voor alle eigenschappen in uw [!DNL Audience Manager] account. Deze variabelen worden gevormd door [sleutel-waardeparen](../../reference/key-value-pairs-explained.md) met de sleutel die door `d_` zoals hieronder wordt getoond vooraf wordt bepaald.

## Waarden toevoegen aan toetsen op platformniveau {#adding-values}

Voor sommige toetsen op platformniveau kunt u zelf de waarde opgeven. Met anderen, worden de sleutels geassocieerd met overeenkomstige [!DNL IP] adressen die op een gebeurtenisvraag worden overgegaan. In beide gevallen moet u nog steeds de waarde opgeven wanneer u kenmerken maakt [!UICONTROL Trait Builder].

## Door de gebruiker gedefinieerde toetsen op platformniveau {#user-defined-keys}

U geeft de waarde op wanneer u kenmerken samenstelt met deze sleutelwaardeparen:

| Sleutel | Voor gerichte |
|---|---|
| `d_zx` | Postcode (bijvoorbeeld `d_zx=10022`). |

## Sleutels van het Niveau van het platform die door IP Adres worden bepaald {#keys-ip-address}

We werken samen met [Digital Envoy](https://www.digitalenvoy.com/) om de demografische en geografische gegevens voor de onderstaande sleutels te verkrijgen en bij te werken. De waarden voor deze sleutels worden bepaald door overeenkomstige [!DNL IP] adressen aan overeenkomstige geografische en demografische gegevens aan te passen. Nochtans, zult u nog de waardeparameter moeten ingaan wanneer het creëren van het sleutel-waardepaar binnen [!UICONTROL Trait Builder].

| Sleutel | Voor gerichte |
|--- |--- |
| d_area_code | [Gebiedscodes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)voor Noord-Amerika.  Bijvoorbeeld: <ul><li>**Trait**:  d_area_code=801</li><li>**Naam** dienstreis: Utah</li></ul> |
| d_city | Steden en steden. Download de lijst met [steden](assets/d_city.txt).  Bijvoorbeeld: <ul><li>Trait:  d_city=bonn</li><li>Naam dienstreis: Bonn</li></ul> **Tip**: U kunt `d_city` in combinatie met gebruiken om er zeker van `d_country` te zijn dat u zich niet richt op twee steden met dezelfde naam in verschillende landen. U kunt zelfs specifieker in uw richten zijn door te gebruiken `d_postal_code`. |
| d_country | De waarden komen overeen met de ISO-landencodes. Raadpleeg het [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home)voor zoekopdrachten in de lijst met codes. <br>  Het is het enige speciale geval dat zich niet houdt aan ISO 3166. Gebruik &quot;UK&quot; in plaats van &quot;GB&quot; voor doelwit in het Verenigd Koninkrijk.  Om zich op de Nederlandse Antillen te richten, is de code &quot;AN&quot; sinds 2010 afgekeurd. Het gebied is ontbonden in vijf afzonderlijke territoriale eenheden. De implicatie is dat voor het richten in de Nederlandse Antillen, u niet &quot;AN,&quot;maar een combinatie landcodes voor &quot;CW,&quot;SX,&quot;en &quot;BQ&quot;zou moeten gebruiken.  Bijvoorbeeld:  <br>Trait:  d_country=CZ <br>naam dienstreis: Trait Tsjechië <br>:  d_country=UK <br>Trait Name: Verenigd Koninkrijk <br>Trait:  d_country=CW OR d_country=SX OR d_country=BQ <br>Trait Name: Nederlandse Antillen |
| d_dma_code | DMA-codes voor metropolitane gebieden. Download de lijst met [DMA-regio&#39;s](assets/DMAregions.csv) (.csv-indeling).  Bijvoorbeeld: <ul><li>Trait:  d_dma_code=807</li><li>Naam dienstreis: San Francisco</li></ul> |
| d_lat | Latitude (bv. d_lat=40,75). Download de [lijst](assets/d_lat.txt)latitudes. |
| d_long | Lengtegraad (bv. d_long=73,98). Download de [lengtenlijst](assets/d_long.txt). |
| d_postal_code | ZIP-codes (exclusief de uitgebreide +4-code). Download de lijst met [postcodes](assets/d_postal_code.txt).  Bijvoorbeeld: <ul><li>Trait:  d_postal_code=84004 </li><li>Naam dienstreis: Alpen</li></ul> |
| d_state | Afkorting van 2 tekens voor een Amerikaanse staat. Download de lijst met [statuscodes](assets/d_state.txt).  Bijvoorbeeld: <ul><li>Trait:  d_state=NY </li><li>Naam dienstreis: New York</li></ul>d_state bevat herhaalde waarden voor verschillende staten in verschillende landen. Zo komt d_state == &quot;on&quot; bijvoorbeeld overeen met meerdere statussen: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibië). We raden je aan dit signaal te koppelen aan anderen, zoals d_country, voor specifiekere oriëntatie. |
| d_region | Regionale alfanumerieke id&#39;s. Download de lijst met [regio&#39;s](assets/Country_RegionCodes_City.csv).  Vervolgens kunt u deze lijst gebruiken om regio-id&#39;s aan regionamen te koppelen. |
| d_isp | ISP/organisatie. Download de [ISP Lijst](assets/d_isp.txt). |

De lijst van [alle op locatie gebaseerde signalen](assets/all.csv) omvat alle bovenstaande signalen, in de volgende volgorde: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Voorvoegselvereisten voor belangrijkste variabelen](../../features/traits/trait-variable-prefixes.md)

