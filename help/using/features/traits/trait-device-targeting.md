---
description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met apparaat-verwante variabelen over alle eigenschappen in uw rekening van de Manager van de Publiek te richten.
seo-description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met apparaat-verwante variabelen over alle eigenschappen in uw rekening van de Manager van de Publiek te richten.
seo-title: Apparaatgericht met toetsen op platformniveau
solution: Audience Manager
title: Apparaatgericht met toetsen op platformniveau
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Apparaatgericht met toetsen op platformniveau {#device-targeting-with-platform-level-keys}

Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met apparaat-verwante variabelen over alle eigenschappen in uw rekening van de Manager van de Publiek te richten.

## Doel van variabelen op platformniveau {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Met variabelen op platformniveau kunt u gegevens van een bepaalde site gebruiken en deze beschikbaar maken voor alle eigenschappen in uw [!DNL Audience Manager] account. Deze variabelen worden gevormd door [sleutel-waardeparen](../../reference/key-value-pairs-explained.md) met de sleutel die door `d_` zoals hieronder wordt getoond vooraf wordt bepaald.

## Sleutels op platformniveau die door de Agent van de Gebruiker worden bepaald {#keys-user-agent}

De [!UICONTROL Data Collection Servers] extractie de waarden voor deze sleutels uit de kopbal [van de](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) gebruikersagent in `HTTP` verzoeken. De waarden vertegenwoordigen apparaatinformatie uit de [!UICONTROL Device Atlas] database. De signalen in de onderstaande tabel zijn beschikbaar, zoals u uit het voorbeeld van de gebruikersagent hebt opgehaald. [Download een lijst met de meest gebruikte toetsen](assets/device_keys.csv)op basis van [!UICONTROL Device Atlas] metingen.

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>Zelfs als één of meerdere signalen niet van de kopbal van de gebruikersagent kunnen worden teruggewonnen, zullen de andere signalen nog worden overgegaan tot [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Voorvoegselvereisten voor belangrijkste variabelen](../../features/traits/trait-variable-prefixes.md)

