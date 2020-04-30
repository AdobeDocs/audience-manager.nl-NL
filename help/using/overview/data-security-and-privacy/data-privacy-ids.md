---
description: In dit document worden de typen ID's van Audience Manager beschreven die u kunt gebruiken in privacyverzoeken voor gegevens.
seo-description: In dit document worden de typen ID's van Audience Manager beschreven die u kunt gebruiken in privacyverzoeken voor gegevens.
seo-title: Id's van Audience Manager
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Id's van Audience Manager
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Id&#39;s van Audience Manager {#aam-ids}

Wanneer u [gegevensprivacyverzoeken](data-privacy-requests.md) naar Adobe Audience Manager verzendt, moet u een van de onderstaande id&#39;s (id&#39;s) opnemen. Meer informatie over de id-indelingen vindt u in onze [index met id&#39;s](../../reference/ids-in-aam.md)van Audience Manager.

## Unieke gebruikersnaam in Adobe Audience Manager

* **Gebruikersnaam**: `aam_uuid`
* **Definitie**: Unieke gebruikersnaam in Adobe Audience Manager
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
>U kunt ook de [!DNL CORE] naamruimte gebruiken.

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

## Adobe Experience Cloud-id

* **Gebruikersnaam**: `mid`
* **Definitie**: [!DNL Adobe Experience Cloud ID], voorheen bekend als [!DNL Visitor ID] of [!DNL Marketing Cloud ID]
* **Naamruimte-id**: 4

>[!NOTE]
>
>U kunt ook de [!DNL ECID] naamruimte gebruiken. Zie het tweede [!DNL JSON] voorbeeld.

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

**Gebruikersnaam**: `cid`

**Definitie**: Klantnummer, zoals een cookie die u instelt voor anonieme sitebezoekers of een [!DNL CRM] id van een offline systeem of een gehashte gebruikersnaam.

**Naamruimte-id**: Klantspecifiek. Ga naar de instantie Audience Manager.

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

**Gebruikersnaam**: `d_cid`

**Definitie**: Mobiele advertentie-id&#39;s.

**Naamruimte-id**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Zie [Algemene gegevensbronnen](../../features/global-data-sources.md) voor meer informatie.

>[!IMPORTANT]
>
> Als u de mobiele telefoon gebruikt [!DNL SDK], moet u ook de Experience Cloud-id (`MID`) samen met de mobiele advertentie-id&#39;s verzenden voor volledige toegang en reacties verwijderen.

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

**Gebruikersnaam**: `d_cid_ic`

**Definitie**: Een integratiecode voor de gegevensbron. Dit kan in de aanvraag aan worden gebruikt in plaats van de id/naamruimte-id van de gegevensbron [!DNL API] [!DNL Adobe Experience Cloud Privacy Core Service].

**Naamruimte-id**: Niet van toepassing

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
