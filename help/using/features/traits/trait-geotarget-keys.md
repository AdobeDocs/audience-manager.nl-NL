---
description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw rekening van de Audience Manager te richten.
seo-description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw rekening van de Audience Manager te richten.
seo-title: Geotargeting met sleutels op platformniveau
solution: Audience Manager
title: Geotargeting met sleutels op platformniveau
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---


# Geotargeting met sleutels op platformniveau {#geotargeting-with-platform-level-keys}

Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw rekening van de Audience Manager te richten.

<!-- c_tb_platform_vars.xml -->

## Doel van variabelen op Platform-niveau {#platform-variables}

Met variabelen op Platform-niveau kunt u gegevens van een bepaalde site gebruiken en deze beschikbaar maken voor alle eigenschappen in uw [!DNL Audience Manager]-account. Deze variabelen worden gevormd door [sleutel-waardeparen](../../reference/key-value-pairs-explained.md) met de sleutel vooraf bepaald door `d_` zoals hieronder getoond.

## Waarden toevoegen aan toetsen op niveau van Platform {#adding-values}

Voor sommige toetsen op platformniveau kunt u zelf de waarde opgeven. Met anderen, worden de sleutels geassocieerd met overeenkomstige [!DNL IP] adressen die op een gebeurtenisvraag worden overgegaan. In beide gevallen moet u nog steeds de waarde opgeven bij het bouwen van kenmerken in [!UICONTROL Trait Builder].

## Door gebruiker gedefinieerde toetsen op Platform-niveau {#user-defined-keys}

U geeft de waarde op wanneer u kenmerken samenstelt met deze sleutelwaardeparen:

| Sleutel | Voor gerichte |
|---|---|
| `d_zx` | ZIP-code (bijvoorbeeld `d_zx=10022`). |

## Sleutels van het Niveau van het Platform die door IP Adres {#keys-ip-address} worden bepaald

We werken met [Digital Engezant](https://www.digitalenvoy.com/) om de demografische en geografische gegevens voor de onderstaande sleutels te verkrijgen en bij te werken. De waarden voor deze sleutels worden bepaald door [!DNL IP] adressen aan overeenkomstige geografische en demografische gegevens aan te passen. Nochtans, zult u nog de waardeparameter moeten ingaan wanneer het creëren van het zeer belangrijk-waardepaar in [!UICONTROL Trait Builder].

| Sleutel | Voor gerichte |
|--- |--- |
| d_area_code | [Gebiedscodes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes) voor Noord-Amerika.  Bijvoorbeeld: <ul><li>**Trait**: d_area_code=801</li><li>**Naam** dienstreis: Utah</li></ul> |
| d_city | Steden en steden. Download de [lijst met steden](assets/d_city.txt).  Bijvoorbeeld: <ul><li>Trait:  d_city=bonn</li><li>Naam dienstreis: Bonn</li></ul> **Tip**: U kunt  `d_city` in combinatie met gebruiken om er zeker van  `d_country` te zijn dat u zich niet richt op twee steden met dezelfde naam in verschillende landen. U kunt zelfs specifieker in uw richten zijn door `d_postal_code` te gebruiken. |
| d_country | De waarden komen overeen met de ISO-landencodes. Raadpleeg het Platform [Online bladeren door ISO](https://www.iso.org/obp/ui/#home) voor een doorzoekbare lijst met codes. <br>  Het is het enige speciale geval dat zich niet houdt aan ISO 3166. Gebruik &quot;UK&quot; in plaats van &quot;GB&quot; voor doelwit in het Verenigd Koninkrijk.  Om zich op de Nederlandse Antillen te richten, is de code &quot;AN&quot; sinds 2010 afgekeurd. Het gebied is ontbonden in vijf afzonderlijke territoriale eenheden. De implicatie is dat voor het richten in de Nederlandse Antillen, u niet &quot;AN,&quot;maar een combinatie landcodes voor &quot;CW,&quot;SX,&quot;en &quot;BQ&quot;zou moeten gebruiken.  Bijvoorbeeld:  <br>  Trait:  d_country=CZ <br>  Naam dienstreis: Tsjechië <br>  Trait:  d_country=UK <br>  Naam dienstreis: Verenigd Koninkrijk <br>  Trait:  d_country=CW OR d_country=SX OR d_country=BQ <br>  Naam dienstreis: Nederlandse Antillen |
| d_dma_code | DMA-codes voor metropolitane gebieden. Download [DMA region list](assets/DMAregions.csv) (.csv formaat).  Bijvoorbeeld: <ul><li>Trait:  d_dma_code=807</li><li>Naam dienstreis: San Francisco</li></ul> |
| d_lat | Latitude (bv. d_lat=40,75). Download de [latitudes list](assets/d_lat.txt). |
| d_long | Lengtegraad (bv. d_long=73,98). Download de [lengtenlijst](assets/d_long.txt). |
| d_postal_code | ZIP-codes (exclusief de uitgebreide +4-code). Download de [postcodelijst](assets/d_postal_code.txt).  Bijvoorbeeld: <ul><li>Trait:  d_postal_code=84004 </li><li>Naam dienstreis: Alpen</li></ul> |
| d_state | Afkorting van 2 tekens voor een Amerikaanse staat. Download de [statuscodelijst](assets/d_state.txt).  Bijvoorbeeld: <ul><li>Trait:  d_state=NY </li><li>Naam dienstreis: New York</li></ul>d_state bevat herhaalde waarden voor verschillende staten in verschillende landen. Zo komt d_state == &quot;on&quot; bijvoorbeeld overeen met meerdere statussen: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibië). We raden je aan dit signaal te koppelen aan anderen, zoals d_country, voor specifiekere oriëntatie. |
| d_region | Regionale alfanumerieke id&#39;s. Download [region list](assets/Country_RegionCodes_City.csv).  Vervolgens kunt u deze lijst gebruiken om regio-id&#39;s aan regionamen te koppelen. |
| d_isp | ISP/organisatie. Download [ISP List](assets/d_isp.txt). |

De lijst van [alle op plaats-gebaseerde signalen](assets/all.txt) omvat alle bovenstaande signalen, in de volgende orde: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Voorvoegselvereisten voor belangrijke variabelen](../../features/traits/trait-variable-prefixes.md)

