---
description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw Audience Manager rekening te richten.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting met toetsen op platformniveau
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 2de7aba53e3c88d31270f2acb4fa29389f940312
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# Geotargeting met toetsen op platformniveau {#geotargeting-with-platform-level-keys}

Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met geografische variabelen over alle eigenschappen in uw Audience Manager rekening te richten.

<!-- c_tb_platform_vars.xml -->

## Doel van variabelen op platformniveau {#platform-variables}

Met variabelen op platformniveau kunt u gegevens van een bepaalde site gebruiken en deze beschikbaar maken voor alle eigenschappen in uw [!DNL Audience Manager] -account. Deze variabelen worden gevormd door [&#x200B; zeer belangrijk-waardeparen &#x200B;](../../reference/key-value-pairs-explained.md) met de sleutel die door `d_` zoals hieronder getoond wordt vooraf bepaald.

## Waarden toevoegen aan toetsen op platformniveau {#adding-values}

Voor sommige toetsen op platformniveau kunt u zelf de waarde opgeven. Met andere gebruikers worden de sleutels gekoppeld aan de overeenkomende [!DNL IP] -adressen die worden doorgegeven aan een gebeurtenisaanroep. In beide gevallen moet u nog steeds de waarde opgeven wanneer u kenmerken maakt in [!UICONTROL Trait Builder] .

## Door gebruiker gedefinieerde toetsen op platformniveau {#user-defined-keys}

Als u reeds hebt, of een proces vestigen om zeer belangrijk-waardeparen te bepalen en te verzamelen, dan gebruik deze optie. Als u sleutels wilt gebruiken die door IP adres vooraf worden bepaald, ga aan de volgende sectie verder. In het geval van user-defined sleutels, specificeert u de waarde wanneer het bouwen van eigenschappen met deze zeer belangrijke-waardeparen:

| Sleutel | Voor doelgericht |
|---|---|
| `d_zx` | ZIP-code (bijvoorbeeld `d_zx=10022`). |

## Platform-vlakke Sleutels die door IP Adres worden bepaald {#keys-ip-address}

Wij werken met [&#x200B; Digitale gezant &#x200B;](https://www.digitalenvoy.com/) om de demografische en geografische gegevens voor de hieronder sleutels te verkrijgen en bij te werken. De waarden voor deze sleutels worden bepaald door [!DNL IP] -adressen aan de overeenkomstige geografische en demografische gegevens te koppelen. U moet echter wel de parameter value invoeren wanneer u het sleutelwaardepaar maakt in [!UICONTROL Trait Builder] .

| Sleutel | Voor doelgericht |
|--- |--- |
| d_area_code | [&#x200B; Noord-Amerika gebiedscodes &#x200B;](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Bijvoorbeeld: <ul><li>**Spoor**: d_area_code=801</li><li>**Naam van het Tandreis**: Utah</li></ul> |
| d_city | Steden en steden Download de [&#x200B; lijst van steden &#x200B;](assets/d_city.txt).  Bijvoorbeeld: <ul><li>Trait: d_city=bonn</li><li>Naam dienblad: Bonn</li></ul> **Uiteinde**: U kunt `d_city` gebruiken die met `d_country` wordt gekoppeld om zeker te zijn u niet aan twee steden met de zelfde naam in verschillende landen richt. U kunt nog specifieker zijn wanneer u een doelwitbewerking uitvoert met `d_postal_code` . |
| d_country | De waarden komen overeen met de ISO-landencodes. Voor een doorzoekbare lijst van codes, zie [&#x200B; Online het Bladeren Platform van ISO &#x200B;](https://www.iso.org/obp/ui/#home). <br>  Het is het enige speciale geval dat zich niet houdt aan ISO 3166. Gebruik &quot;UK&quot; in plaats van &quot;GB&quot; voor doelwit in het Verenigd Koninkrijk.  Om zich op de Nederlandse Antillen te richten, is de code &quot;AN&quot; sinds 2010 afgekeurd. Het gebied is ontbonden in vijf afzonderlijke territoriale eenheden. De implicatie is dat voor het richten in de Nederlandse Antillen, u niet &quot;AN,&quot;maar een combinatie landcodes voor &quot;CW,&quot;SX,&quot;en &quot;BQ&quot;zou moeten gebruiken.  Bijvoorbeeld: <br>  Trait: d_country=CZ <br>  Naam reiskenmerk: Tsjechië <br>  Trait: d_country=UK <br>  Naam dienstreis: Verenigd Koninkrijk <br>  Trait: d_country=CW OR d_country=SX OR d_country=BQ <br>  Naam dienblad: Nederlandse Antillen |
| d_dma_code | DMA-codes voor metropolitane gebieden. Download de [&#x200B; DMA gebiedlijst &#x200B;](assets/DMAregions.csv) (.csv formaat).  Bijvoorbeeld: <ul><li>Trait: d_dma_code=807</li><li>Naam dienblad: San Francisco</li></ul> |
| d_lat | Latitude (bijvoorbeeld d_lat=40,75). Download de [&#x200B; lijst van breedten &#x200B;](assets/d_lat.txt). |
| d_long | Lengtegraad (bijvoorbeeld d_long=73,98). Download de [&#x200B; lijst van lengten &#x200B;](assets/d_long.txt). |
| d_postal_code | ZIP-codes (exclusief de uitgebreide +4-code). Download de [&#x200B; lijst van postcodes &#x200B;](assets/d_postal_code.txt).  Bijvoorbeeld: <ul><li>Trait: d_postal_code=84004 </li><li>Naam dienblad: Alpine</li></ul> |
| d_state | Afkorting van 2 tekens voor een Amerikaanse staat. Download de [&#x200B; lijst van statuscodes &#x200B;](assets/d_state.txt).  Bijvoorbeeld: <ul><li>Traject: d_state=NY </li><li>Naam dienblad: New York</li></ul>d_state bevat herhaalde waarden voor verschillende staten in verschillende landen. Zo komt d_state == &quot;on&quot; bijvoorbeeld overeen met meerdere staten: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibië). We raden je aan dit signaal te koppelen aan anderen, zoals d_country, voor specifiekere oriëntatie. |
| d_region | Regionale alfanumerieke id&#39;s. Download de [&#x200B; gebiedslijst &#x200B;](assets/Country_RegionCodes_City.csv).  Vervolgens kunt u deze lijst gebruiken om regio-id&#39;s aan regionamen te koppelen. |
| d_isp | ISP/organisatie. Download de [&#x200B; ISP Lijst &#x200B;](assets/d_isp.txt). |

De lijst van [&#x200B; alle op plaats-gebaseerde signalen &#x200B;](assets/all.txt) omvat alle signalen hierboven, in de volgende orde: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Voorvoegselvereisten voor belangrijke variabelen](../../features/traits/trait-variable-prefixes.md)

