---
description: Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek URLs, en andere verwijzingen.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Aan de slag met REST-API’s
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 1%

---

# Aan de slag met [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek [!DNL URLs]en andere verwijzingen.

<!-- c_rest_api_overview.xml -->

## API-vereisten en -aanbevelingen {#api-requirements-recommendations}

Wat u moet en moet doen wanneer u met de [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Let op het volgende wanneer u werkt met [Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **Parameters aanvragen:** alle aanvraagparameters zijn vereist, tenzij anders aangegeven.
* **Aanvraagkoppen**: wanneer u [Adobe Developer](https://www.adobe.io/) tokens, u moet de `x-api-key` header. U kunt uw [!DNL API] door de instructies in de [Integratie van serviceaccount](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) pagina.
* **[!DNL JSON]inhoudstype:** Opgeven `content-type: application/json`  *en*  `accept: application/json` in uw code.
* **Verzoeken en antwoorden:** Aanvragen verzenden als een correct opgemaakt bestand [!DNL JSON] object. [!DNL Audience Manager] reageert met [!DNL JSON] opgemaakte gegevens. Serverreacties kunnen gevraagde gegevens, een statuscode of beide bevatten.
* **Toegang:** Uw [!DNL Audience Manager] consultant zal u een klant-id en een sleutel geven waarmee u [!DNL API] verzoeken.
* **Documentatie en codevoorbeelden:** Tekst in *cursief* vertegenwoordigt een variabele die u verstrekt of binnen overgaat wanneer het maken of het ontvangen [!DNL API] gegevens. Vervangen *cursief* tekst met uw eigen code, parameters of andere vereiste informatie.

## Verificatie {#authentication}

De [!DNL Audience Manager] [!DNL REST APIs] ondersteuning voor twee verificatiemethoden.

* [JWT-verificatie (serviceaccount)](#jwt) gebruiken [Adobe Developer](https://www.adobe.io/). [!DNL Adobe Developer] is Adobe. Hieronder vallen [API&#39;s voor alle Adobe-producten](https://www.adobe.io/apis.html). Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs].
* [OAuth-verificatie (afgekeurd)](#oauth). Hoewel deze methode is afgekeurd, kunnen klanten met bestaande [!DNL OAuth] Deze methode kan worden gebruikt voor integraties.

>[!IMPORTANT]
>
>Afhankelijk van uw authentificatiemethode, moet u uw verzoek aanpassen [!DNL URLs] dienovereenkomstig. Zie de [Omgevingen](#environments) voor details over hostnames die u zou moeten gebruiken.

## [!DNL JWT] ([!DNL Service Account]) Verificatie met Adobe Developer {#jwt}

### Adobe Developer - Overzicht {#adobeio}

[!DNL Adobe Developer] is Adobe. Hieronder vallen [API&#39;s voor alle Adobe-producten](https://www.adobe.io/apis.html).

Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs].

### Vereisten {#prerequisites}

Voordat u kunt configureren [!DNL JWT] verificatie, zorg ervoor dat u toegang hebt tot de [Adobe Developer Console](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). Neem contact op met uw organisatiebeheerder voor verzoeken om toegang.

### Verificatie {#auth}

Voer de onderstaande stappen uit om te configureren [!DNL JWT (Service Account)] verificatie met [!DNL Adobe Developer]:

1. Aanmelden bij de [Adobe Developer Console](https://console.adobe.io/).
1. Voer de stappen uit in [Verbinding serviceaccount](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Tijdens [Stap 2: Een API toevoegen aan uw project met de verificatie van de serviceaccount](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), kiest u de [!DNL Audience Manager] [!DNL API] optie.
1. Probeer de verbinding uit door eerst uw [!DNL API] vraag gebaseerd op de instructies van [Stap 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Om te vormen en met het [!DNL Audience Manager] [!DNL REST APIs] op een geautomatiseerde manier kunt u de [!DNL JWT] programmatisch. Zie [JWT-verificatie (serviceaccount)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) voor gedetailleerde instructies.

### Machtigingen voor RBAC&#39;s van technische rekeningen

Als uw Audience Manager-account [Op rollen gebaseerd Toegangsbeheer](../../features/administration/administration-overview.md), moet u een technische gebruikersrekening van de Audience Manager tot stand brengen en het toevoegen aan de Audience Manager RBAC groep die de API vraag zal maken.

Voer de onderstaande stappen uit om een technische gebruikersaccount te maken en deze toe te voegen aan een RBAC-groep:

1. Een `GET` oproep aan `https://aam.adobe.io/v1/users/self`. De vraag zal tot een technische gebruikersrekening leiden die u in kunt zien [!UICONTROL Admin Console]in de [!UICONTROL Users] pagina.

   ![technische rekening](assets/technical-account.png)

1. Meld u aan bij uw Audience Manager-account en [toevoegen aan de technische gebruikersaccount](../../features/administration/administration-overview.md#create-group) aan de gebruikersgroep die de API vraag zal maken.

## [!DNL OAuth] Verificatie (afgekeurd) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] tokenauthentificatie en vernieuwing via [!DNL OAuth 2.0] is nu afgekeurd.
>
> Gebruik [JWT-verificatie (serviceaccount)](#jwt-service-account-authentication-jwt) in plaats daarvan.

De [!DNL Audience Manager] [!UICONTROL REST API] volgt [!DNL OAuth 2.0] normen voor tokenauthentificatie en vernieuwing. In de onderstaande secties wordt beschreven hoe u de verificatie uitvoert en met de functie [!DNL API]s.

### Een algemeen document maken [!DNL API] Gebruiker {#requirements}

We raden u aan een aparte, technische gebruikersaccount te maken voor het werken met de [!DNL Audience Manager] [!DNL API]s. Dit is een generische rekening die niet aan of verbonden met een specifieke gebruiker in uw organisatie is. Dit type van [!DNL API] Met gebruikersaccount kunt u twee dingen doen:

* Identificeer welke dienst roept [!DNL API] (Bijvoorbeeld, vraag van uw apps die onze gebruiken [!DNL API]s of van andere gereedschappen [!DNL API] verzoeken).
* Ononderbroken toegang tot de [!DNL API]s. Een account die aan een bepaalde persoon is gekoppeld, kan worden verwijderd wanneer deze uw bedrijf verlaat. Zo voorkomt u dat u met de beschikbare [!DNL API] code. Met een algemene account die niet aan een bepaalde werknemer is gekoppeld, voorkomt u dit probleem.

Als voorbeeld of gebruiksgeval voor dit type van rekening, laten wij zeggen u veel segmenten in één keer met wilt veranderen [Bulkbeheertools](../../reference/bulk-management-tools/bulk-management-intro.md). Wel, om dit te doen, heeft uw gebruikersrekening nodig [!DNL API] toegang. In plaats van machtigingen toe te voegen aan een specifieke gebruiker, maakt u een niet-specifieke gebruiker. [!DNL API] gebruikersaccount met de juiste gegevens, sleutel en geheim om [!DNL API] oproepen. Dit is ook handig als u uw eigen toepassingen ontwikkelt die gebruikmaken van de [!DNL Audience Manager] [!DNL API]s.

Werk met uw [!DNL Audience Manager] consultant voor het opzetten van een generiek [!DNL API]-only user account.

### Workflow voor wachtwoordverificatie {#password-authentication-workflow}

Wachtwoordverificatie veilige toegang tot onze [!DNL REST API]. In de onderstaande stappen wordt een overzicht gegeven van de workflow voor wachtwoordverificatie via een [!DNL JSON] in uw browser.

>[!TIP]
>
>Codeer toegang en vernieuw tokens als u hen in een gegevensbestand opslaat.

#### Stap 1: Verzoek [!DNL API] Toegang

Contacteer uw manager van de Oplossingen van de Partner. Zij zullen u van een [!DNL API] client-id en geheim. De id en het geheim verifiëren u aan [!DNL API].

Opmerking: Als u een vernieuwingstoken wilt ontvangen, specificeer dat wanneer u verzoekt [!DNL API] toegang.

#### Stap 2: Token aanvragen

Geef een symbolische aanvraag door aan uw voorkeur [!DNL JSON] client. Wanneer u het verzoek bouwt:

* Een `POST` methode `https://api.demdex.com/oauth/token`.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. Bijvoorbeeld, de geloofsbrieven `testId : testSecret` omzetten in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Geef in [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded` . De koptekst kan er bijvoorbeeld als volgt uitzien: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Stel de aanvraaginstantie als volgt in:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Stap 3: Token ontvangen

De [!DNL JSON] reactie bevat uw toegangstoken. De reactie moet er als volgt uitzien:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

De `expires_in` key vertegenwoordigt het aantal seconden tot het toegangstoken verloopt. U kunt het beste korte vervaltijden gebruiken om de belichting te beperken als het token ooit wordt blootgesteld.

### Token vernieuwen {#refresh-token}

Tokens vernieuwen [!DNL API] toegang nadat het originele teken verloopt. Indien gevraagd, het antwoord [!DNL JSON] in de wachtwoordworkflow bevat een token voor vernieuwen. Als u ontvangt vernieuw symbolisch, creeer nieuwe door het proces van de wachtwoordauthentificatie.

U kunt ook een vernieuwingstoken gebruiken om een nieuw token te genereren voordat het bestaande toegangstoken verloopt.

Als uw toegangstoken is verlopen, ontvangt u een `401 Status Code` en de volgende koptekst in het antwoord:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

In de volgende stappen wordt een overzicht gegeven van de workflow voor het gebruik van een vernieuwingstoken om een nieuw toegangstoken te maken van een [!DNL JSON] in uw browser.

#### Stap 1: Nieuwe token aanvragen

Geef een vernieuwingstoken-aanvraag door aan uw voorkeur [!DNL JSON] client. Wanneer u het verzoek bouwt:

* Een `POST` methode `https://api.demdex.com/oauth/token`.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. Bijvoorbeeld, de geloofsbrieven `testId : testSecret` omzetten in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Geef in de HTTP-headers door `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded`. De koptekst kan er bijvoorbeeld als volgt uitzien: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Vermeld in de aanvraaginstantie de `grant_type:refresh_token` en ga binnen vernieuwen teken u in uw vorig toegangsverzoek ontving. Het verzoek moet er als volgt uitzien: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Stap 2: Het nieuwe token ontvangen

De [!DNL JSON] de reactie bevat uw nieuw toegangstoken. De reactie moet er als volgt uitzien:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### Autorisatiecode en impliciete verificatie {#authentication-code-implicit}

De [!DNL Audience Manager] [!UICONTROL REST API] steunt vergunningscode en impliciete authentificatie. Om deze toegangsmethodes te gebruiken, moeten uw gebruikers login aan `https://api.demdex.com/oauth/authorize` om tokens te openen en te vernieuwen.

## Verifiëren [!DNL API] Verzoeken {#authenticated-api-requests}

Vereisten voor oproepen [!DNL API] methoden nadat u een verificatietoken hebt ontvangen.

Om vraag tegen beschikbaar te maken [!DNL API] methoden:

* In de `HTTP` header, set `Authorization: Bearer <token>`.
* Wanneer u [JWT-verificatie (serviceaccount)](#jwt), moet u de `x-api-key` koptekst, die hetzelfde zal zijn als uw `client_id`. U kunt uw `client_id` van de [Adobe Developer-integratie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) pagina.
* De vereiste vraag [!DNL API] methode.

## Optioneel [!DNL API] Zoekparameters {#optional-api-query-parameters}

Stel de optionele parameters in die beschikbaar zijn voor methoden die alle eigenschappen voor een object retourneren.

U kunt deze optionele parameters gebruiken met [!DNL API] methoden die worden geretourneerd *alles* eigenschappen voor een object. Stel deze opties in de tekenreeks request wanneer u die query doorgeeft aan de [!DNL API].

| Parameter | Beschrijving |
|--- |--- |
| `page` | Geeft resultaten op paginanummer. De nummering begint bij 0. |
| `pageSize` | Stelt het aantal reactieresultaten in dat door de aanvraag wordt geretourneerd (10 is standaard). |
| `sortBy` | Hiermee worden de resultaten gesorteerd en geretourneerd volgens de opgegeven waarden [!DNL JSON] eigenschap. |
| `descending` | Sorteert en retourneert resultaten in aflopende volgorde. `ascending` is standaard. |
| `search` | Retourneert resultaten op basis van de opgegeven tekenreeks die u als zoekparameter wilt gebruiken. Bijvoorbeeld, laten wij zeggen u resultaten voor alle modellen wilt vinden die het woord &quot;Test&quot;in om het even welke waardegebieden voor dat punt hebben. Uw voorbeeldverzoek kan er als volgt uitzien:   `GET https://aam.adobe.io/v1/models/?search=Test`.  U kunt zoeken op elke waarde die wordt geretourneerd door een &quot;[!DNL get all]&quot;. |
| `folderId` | Retourneert alle id&#39;s voor [!UICONTROL traits] in de opgegeven map. Niet beschikbaar voor alle methoden. |
| `permissions` | Retourneert een lijst met segmenten op basis van de opgegeven machtiging. `READ` is standaard. Bevoegdheden omvatten:<ul><li>`READ` : De terugkeer en bekijkt informatie over een segment.</li><li>`WRITE` : Gebruiken  `PUT`  om een segment bij te werken.</li><li>`CREATE` : Gebruiken  `POST`  om een segment te maken.</li><li>`DELETE` : Een segment verwijderen. Vereist toegang tot eventuele onderliggende kenmerken. Bijvoorbeeld, zult u rechten nodig hebben om de eigenschappen te schrappen die tot een segment behoren als u het wilt verwijderen.</li></ul><br>Geef meerdere machtigingen op met afzonderlijke sleutelwaardeparen. Als u bijvoorbeeld een lijst met segmenten wilt retourneren met  `READ`  en  `WRITE`  alleen machtigingen, doorgeven  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Instellen op `true` om uw toestemmingen voor het segment terug te keren. Standaard is `false`. |

### Een opmerking over paginaopties

Wanneer paginagegevens *is niet* gespecificeerd, keert het verzoek onbewerkt terug [!DNL JSON] resulteert in een array. Als paginagegevens *is* opgegeven, wordt de geretourneerde lijst opgenomen in een [!DNL JSON] object dat informatie bevat over het totale resultaat en de huidige pagina. Uw voorbeeldverzoek met behulp van paginaopties kan er als volgt uitzien:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] voor verzoeken, het opvoeren en productiemilieu&#39;s, en versies.

## Verzoek [!DNL URLs] {#request-urls}

De volgende tabel bevat de aanvraag [!DNL URLs] gebruikt om binnen te gaan [!DNL API] verzoeken, via methode.

Afhankelijk van de authentificatiemethode die u gebruikt, moet u uw verzoek aanpassen [!DNL URLs] volgens onderstaande tabellen.

### Verzoek [!DNL URLs] for [!DNL JWT] Verificatie {#request-urls-jwt}

| [!DNL API] Methoden | Verzoek [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Tanden:  `https://aam.adobe.io/v1/folders/traits /`<br>Segmenten:  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### Verzoek [!DNL URLs] for [!DNL OAuth] Verificatie (afgekeurd) {#request-urls-oauth}

| [!DNL API] Methoden | Verzoek [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Tanden:  `https://api.demdex.com/v1/folders/traits /`<br>Segmenten:  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## Omgevingen {#environments}

De [!DNL Audience Manager] [!DNL API]s biedt toegang tot verschillende werkomgevingen. Deze milieu&#39;s helpen u code tegen afzonderlijke gegevensbestanden testen zonder levende, productiegegevens te beïnvloeden. In de volgende tabel worden de beschikbare [!DNL API] omgevingen en bijbehorende hostnamen van bronnen.

Afhankelijk van de verificatiemethode die u gebruikt, moet u uw omgeving aanpassen [!DNL URLs] volgens onderstaande tabel.

| Omgeving | Hostnaam voor [!DNL JWT] verificatie | Hostnaam voor [!DNL OAuth] verificatie |
|---|---|---|
| **Productie** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>De [!DNL Audience Manager] bètaomgeving is een kleinschalige, zelfstandige versie van de productieomgeving. Alle gegevens die u wilt testen, moeten in deze omgeving worden ingevoerd en verzameld.

## Versies {#versions}

Nieuwe versies van deze [!DNL API]s worden vrijgegeven volgens een regelmatig schema. Een nieuwe release verhoogt de [!DNL API] versienummer. Naar het versienummer wordt verwezen in de aanvraag [!DNL URL] als `v<version number>` zoals getoond in het volgende voorbeeld:

`https://<host>/v1/...`

## Responscodes gedefinieerd {#response-codes-defined}

`HTTP` statuscodes en reactietekst die door de [!DNL Audience Manager] [!UICONTROL REST API].

| Antwoordcode-id | Antwoordtekst | Definitie |
|---|---|---|
| `200` | `OK` | De aanvraag is verwerkt. Hiermee worden de verwachte inhoud of gegevens geretourneerd, indien vereist. |
| `201` | `Created` | De bron is gemaakt. Retourneert voor `PUT` en `POST` verzoeken. |
| `204` | `No Content` | De bron is verwijderd. De responsinstantie is leeg. |
| `400` | `Bad Request` | De server begrijpt het verzoek niet. Gewoonlijk als gevolg van een onjuiste syntaxis. Controleer uw verzoek en probeer het opnieuw. |
| `403` | `Forbidden` | U hebt geen toegang tot de bron. |
| `404` | `Not Found` | De bron kan niet worden gevonden voor het opgegeven pad. |
| `409` | `Conflict` | Het verzoek kon niet worden voltooid wegens een conflict met de staat van de bron. |
| `500` | `Server Error` | De server heeft een onverwachte fout aangetroffen waardoor deze de aanvraag niet kan uitvoeren. |

>[!MORELIKETHIS]
>
>* [JWT-verificatie (serviceaccount)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth-verificatie](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 Vereenvoudigd](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

