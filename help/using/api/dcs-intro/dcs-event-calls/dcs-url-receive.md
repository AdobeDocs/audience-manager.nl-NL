---
description: Ga hier voor informatie over hoe te om om een reactie DCS in een /event vraag te verzoeken. Deze sectie omvat een reactievoorbeeld en definities voor gemeenschappelijke gegevenselementen in een reactie.
seo-description: Ga hier voor informatie over hoe te om om een reactie DCS in een /event vraag te verzoeken. Deze sectie omvat een reactievoorbeeld en definities voor gemeenschappelijke gegevenselementen in een reactie.
seo-title: Gegevens ontvangen van de DCS
solution: Audience Manager
title: Gegevens ontvangen van de DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---


# Gegevens ontvangen van de DCS {#receive-data-from-the-dcs}

Ga hier voor informatie over hoe te om een [!DNL DCS] reactie in een `/event` vraag te verzoeken. Deze sectie omvat een reactievoorbeeld en definities voor gemeenschappelijke gegevenselementen in een reactie.

Zie Gegevens [verzenden naar de DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)voordat u deze inhoud controleert.

## DCS-responsparameters: Een revisie {#dcs-response-parameters}

Uw [!DNL DCS] verzoek moet omvatten `d_rtbd=json` als u een antwoord van [!DNL DCS]. De gegevens worden [!DNL DCS] niet geretourneerd als u deze parameter weglaat. Een basisvraag aan de [!DNL DCS] om gegevens te verzoeken gebruikt deze syntaxis:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Samplereactie {#sample-response}

Herinnering dat van de [Send Gegevens naar de documentatie DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) , het fictieve bedrijf deze vraag [!DNL Acme, Inc.] maakte:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Aangezien deze vraag de vereiste reactieparameter omvat, [!DNL DCS] die wordt teruggestuurd het hieronder getoonde [!DNL JSON] voorwerp. U kunt gelijkaardig of complexer zijn.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Responsparameters {#response-parameters}

De onderstaande tabel bevat een lijst met en definieert de meer algemene parameters die u in een reactie van de [!DNL DCS]code kunt zien. Dit is van toepassing op gebeurtenisaanroepen of andere [!DNL DCS] [!DNL API] query&#39;s die gegevens retourneren.

| Parameter | Beschrijving |
|--- |--- |
| `c` | Een URL die is ingesteld als een [URL-doel](../../../features/destinations/create-url-destination.md). |
| `cn` | De naam of id die is ingesteld in het veld Naam cookie van een [doel](../../../features/destinations/create-cookie-destination.md)van het cookie. |
| `cv` | De waarden die naar het doel worden verzonden dat door de parameter &quot;cn&quot;:&quot;(doelnaam) wordt gedefinieerd. |
| `dcs_region` | De [server-aan-server DCS vraag](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Dit object bevat informatie voor alle URL-doelen die in de gebruikersinterface zijn geconfigureerd. De lijst van dit object is dynamisch op basis van de acties van de gebruiker. |
| `dmn` | Dit is het domein dat is opgegeven in het veld Cookie-domein voor een cookie-bestemming. Zie [Optionele instellingen voor Cookie-doelen](../../../features/destinations/cookie-destination-options.md).  Voor Server aan de integratie van de Server adviseren wij gebruikend een domein als `aam-api.com`. |
| `e` | De beveiligde URL die is ingesteld in een URL-doel. |
| `stuff` | Dit object bevat informatie voor alle Cookie-doelen. De lijst van dit object is dynamisch op basis van de acties van de gebruiker. |
| `tid` | Transactie-id. Dit is een unieke id van 12 tekens die wordt gebruikt voor foutopsporingsdoeleinden. Elke /event vraag aan DCS ontvangt een tid die u in steunonderzoeken voor een betere en snellere reactie kunt van verwijzingen voorzien. |
| `ttl` | De tijd-tot-live waarde van het cookie in dagen. |
| `u` en `uuid` | Unieke gebruikersnaam toegewezen door Audience Manager. Dit wordt vereist als u [server-aan-server DCS vraag](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)maakt. |
| `y` | Doeltype, iFrame (`iframe`) of afbeelding (`img`). |

>[!MORELIKETHIS]
>
>* [Belangrijke voorvoegsels en variabelen die door DCS worden ondersteund](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

