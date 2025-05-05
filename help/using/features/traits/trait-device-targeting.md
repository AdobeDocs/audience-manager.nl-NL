---
description: Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met apparaat-verwante variabelen over alle eigenschappen in uw rekening van de Audience Manager te richten.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Apparaattargeting met sleutels op platformniveau
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 5%

---

# Apparaattargeting met sleutels op platformniveau {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google heeft de functionaliteit van [!DNL Google Chrome] en alle [!DNL Chromium]-gebaseerde browsers om de informatie die via de `User-Agent` header.
>Vanaf maart 2023 ondersteunt Audience Manager deze updates door gebruik te maken van [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL). Doorgaan met gebruik van de via het `User-Agent` header, moet u gebruiken [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) en [High Entropine User-Agent de Tips van de Cliënt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=nl-NL).
>Deze updates worden niet ondersteund door [DIL](../../../using/dil/dil-overview.md), dus Audience Manager klanten die [!DNL DIL] kan geen informatie over de eigenschap verzamelen via de `User-Agent` header.

Beschrijft gemeenschappelijke platform-vlakke zeer belangrijke-waardeparen u kunt gebruiken om gebruikers met apparaat-verwante variabelen over alle eigenschappen in uw rekening van de Audience Manager te richten.

## Doel van variabelen op het niveau van de Platform {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Met variabelen op Platform-niveau kunt u gegevens van een bepaalde site gebruiken en deze beschikbaar maken voor alle eigenschappen in uw [!DNL Audience Manager] account. Deze variabelen worden gevormd door [sleutelwaardeparen](../../reference/key-value-pairs-explained.md) met de toets vooraf ingesteld door `d_` zoals hieronder weergegeven.

## Sleutels op Platform-niveau die door de Agent van de Gebruiker worden bepaald {#keys-user-agent}

De [!UICONTROL Data Collection Servers] extraheer de waarden voor deze toetsen uit de [user agent header](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` verzoeken. De waarden vertegenwoordigen apparaatniveauinformatie van de [!UICONTROL Device Atlas] database. De signalen in de onderstaande tabel zijn beschikbaar, zoals u uit het voorbeeld van de gebruikersagent hebt opgehaald. [Een lijst met de meest gebruikte toetsen downloaden](assets/device_keys.csv)volgens [!UICONTROL Device Atlas] metingen.

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

