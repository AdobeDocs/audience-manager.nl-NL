---
description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met apparaat-verwante variabelen over alle eigenschappen in uw rekening van Audience Manager te richten.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Apparaatgericht met toetsen op platformniveau
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# Apparaatgericht met toetsen op platformniveau {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google heeft de functionaliteit van [!DNL Google Chrome] en alle [!DNL Chromium] gebaseerde browsers bijgewerkt om de informatie die via de header `User-Agent` wordt verzameld, tot een minimum te beperken.
>&#x200B;>Beginnend met Maart 2023, steunt Audience Manager deze updates door leveraging [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). Om het gebruiken van eigenschapinformatie voort te zetten die via de `User-Agent` kopbal wordt verstrekt, moet u [ SDK van het Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) gebruiken en [ Hints van de Cliënt van Entropy Gebruiker-Agent ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en) toelaten.
>&#x200B;>Deze updates worden niet gesteund door [ DIL ](../../../using/dil/dil-overview.md), zodat zullen de klanten van Audience Manager die [!DNL DIL] gebruiken geen trekinformatie via de `User-Agent` kopbal kunnen verzamelen.

Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met apparaat-verwante variabelen over alle eigenschappen in uw rekening van Audience Manager te richten.

## Doel van variabelen op platformniveau {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Met variabelen op platformniveau kunt u gegevens van een bepaalde site gebruiken en deze beschikbaar maken voor alle eigenschappen in uw [!DNL Audience Manager] -account. Deze variabelen worden gevormd door [ zeer belangrijk-waardeparen ](../../reference/key-value-pairs-explained.md) met de sleutel die door `d_` zoals hieronder getoond wordt vooraf bepaald.

## Sleutels op platformniveau die door de Agent van de Gebruiker worden bepaald {#keys-user-agent}

[!UICONTROL Data Collection Servers] haalt de waarden voor deze sleutels uit de [ kopbal van de gebruikersagent ](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` verzoeken. De waarden vertegenwoordigen informatie op apparaatniveau uit de [!UICONTROL Device Atlas] -database. De signalen in de onderstaande tabel zijn beschikbaar, zoals u uit het voorbeeld van de gebruikersagent hebt geëxtraheerd. [ Download een lijst van de gemeenschappelijkste sleutels ](assets/device_keys.csv), volgens [!UICONTROL Device Atlas] metingen.

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
>* [Voorvoegselvereisten voor belangrijke variabelen](../../features/traits/trait-variable-prefixes.md)
