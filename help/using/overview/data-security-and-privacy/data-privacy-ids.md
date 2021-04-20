---
description: In dit document worden de soorten Audience Manager-id’s besproken die u kunt gebruiken in Data Privacy-aanvragen.
seo-description: In dit document worden de soorten Audience Manager-id’s besproken die u kunt gebruiken in Data Privacy-aanvragen.
seo-title: Audience Manager-id’s
solution: Audience Manager
keywords: GDPR-interface, GDPR-API, CCPA, privacy, AAM-id
title: Audience Manager-id’s
feature: Data Governance & Privacy
exl-id: 5f18ed0a-c875-4596-a4d1-f9a7fe871d1b
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 95%

---

# Audience Manager-id’s {#aam-ids}

Wanneer u [Data Privacy-aanvragen](data-privacy-requests.md) verzendt naar Adobe Audience Manager, moet u een van de hieronder vermelde id’s opnemen. U vindt meer informatie over de id-indelingen in onze [index met Audience Manager-id’s](../../reference/ids-in-aam.md).

## Unieke Adobe Audience Manager-gebruikers-id

* **Gebruikers-id**: `aam_uuid`
* **Definitie**: unieke gebruikers-id in Adobe Audience Manager
* **Naamruimte-id**: 0

**JSON-voorbeeld**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>U kunt ook de [!DNL CORE]-naamruimte gebruiken.

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **Gebruikers-id**: `mid`
* **Definitie**: [!DNL Adobe Experience Cloud ID], vroeger bekend als [!DNL Visitor ID] of [!DNL Marketing Cloud ID]
* **Naamruimte-id**: 4

>[!NOTE]
>
>U kunt ook de [!DNL ECID]-naamruimte gebruiken. Zie het tweede [!DNL JSON]-voorbeeld.

**JSON-voorbeeld**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## Klant-id

**Gebruikers-id**: `cid`

**Definitie**: klant-id, zoals een cookie dat u instelt voor anonieme websitebezoekers of een [!DNL CRM]-id van een offline systeem of een gehashte gebruikersnaam.

**Naamruimte-id**: klantspecifiek. Haal deze uit uw Audience Manager-instantie.

**JSON-voorbeeld**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## Mobiele advertentie-id

**Gebruikers-id**: `d_cid`

**Definitie**: mobiele advertentie-id’s.

**Naamruimte-id**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Zie [Algemene databronnen](../../features/global-data-sources.md) voor meer informatie.

>[!IMPORTANT]
>
> Als u de Mobile [!DNL SDK] gebruikt, moet u ook de Experience Cloud ID (`MID`) verzenden samen met mobiele advertentie-id’s voor volledige toegangs- en verwijderingsreacties.

**JSON-voorbeeld**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## Integratiecode

**Gebruikers-id**: `d_cid_ic`

**Definitie**: een integratiecode voor de databron. Dit kan worden gebruikt in plaats van de databron-id/naamruimte-id in de [!DNL API]-aanvraag bij [!DNL Adobe Experience Cloud Privacy Core Service].

**Naamruimte-id**: niet van toepassing

**JSON-voorbeeld**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
