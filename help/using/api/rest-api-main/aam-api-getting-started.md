---
description: Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek URLs, en andere verwijzingen.
seo-description: Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek URLs, en andere verwijzingen.
seo-title: Aan de slag met REST-API’s
solution: Audience Manager
title: Aan de slag met REST-API’s
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: f7b9c30f120b24f9294afa4aa6727ce8c4236acf
workflow-type: tm+mt
source-wordcount: '1860'
ht-degree: 2%

---


# Aan de slag met [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek [!DNL URLs], en andere verwijzingen.

<!-- c_rest_api_overview.xml -->

## API-vereisten en -aanbevelingen {#api-requirements-recommendations}

Wat u moet en moet doen wanneer u met de [!DNL Audience Manager] [!DNL API]s werkt.

<!-- aam-api-requirements.xml -->

Let op het volgende wanneer u werkt met [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) -code:

* **Parameters aanvragen:** alle aanvraagparameters zijn vereist, tenzij anders aangegeven.
* **Aanvraagkoppen**: wanneer u [Adobe I/O](https://www.adobe.io/) -tokens gebruikt, moet u de `x-api-key` koptekst opgeven. U kunt uw [!DNL API] sleutel krijgen door de instructies in de pagina van de Integratie [van de Rekening van de](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) Dienst te volgen.
* **[!DNL JSON]inhoudstype:** Geef de code op `content-type: application/json` en geef ** `accept: application/json` deze op.
* **Verzoeken en antwoorden:** Verstuur aanvragen als een correct opgemaakt [!DNL JSON] object. [!DNL Audience Manager] reageert met [!DNL JSON] opgemaakte gegevens. Serverreacties kunnen gevraagde gegevens, een statuscode of beide bevatten.
* **Toegang:** Uw [!DNL Audience Manager] consultant geeft u een client-id en sleutel waarmee u [!DNL API] aanvragen kunt indienen.
* **Documentatie en codevoorbeelden:** Tekst in *cursief* staat voor een variabele die u opgeeft of doorgeeft bij het maken of ontvangen van [!DNL API] gegevens. Vervang *cursieve* tekst door uw eigen code, parameters of andere vereiste informatie.

## Verificatie {#authentication}

De [!DNL Audience Manager] [!DNL REST APIs] ondersteuning biedt twee verificatiemethoden.

* [JWT-verificatie (serviceaccount)](#jwt) met [Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] is Adobe. Het bevat de [Adobe I/O-ontwikkelaarsgereedschappen en API&#39;s](https://www.adobe.io/apis/experienceplatform.html) en [API&#39;s voor alle Adobe-producten](https://www.adobe.io/apis.html). Dit is de aanbevolen manier om instellingen en toepassingen in te stellen [!DNL Adobe][!DNL APIs].
* [OAuth-verificatie (afgekeurd)](#oauth). Hoewel deze methode is afgekeurd, kunnen klanten met bestaande [!DNL OAuth] integratie deze methode blijven gebruiken.

>[!IMPORTANT]
>
>Afhankelijk van uw authentificatiemethode, moet u uw verzoek [!DNL URLs] dienovereenkomstig aanpassen. Zie de sectie [Omgevingen](#environments) voor meer informatie over de hostnamen die u moet gebruiken.

## [!DNL JWT] ([!DNL Service Account]) Verificatie met behulp van Adobe I/O {#jwt}

### Adobe I/O-overzicht {#adobeio}

[!DNL Adobe I/O] is Adobe. Het bevat de [Adobe I/O-ontwikkelaarsgereedschappen en API&#39;s](https://www.adobe.io/apis/experienceplatform.html) en [API&#39;s voor alle Adobe-producten](https://www.adobe.io/apis.html).

Dit is de aanbevolen manier om instellingen en toepassingen in te stellen [!DNL Adobe][!DNL APIs].

### Vereisten {#prerequisites}

Voordat u [!DNL JWT] verificatie kunt configureren, moet u ervoor zorgen dat u toegang hebt tot de [Adobe Developer Console](https://console.adobe.io/) in [Adobe I/O](https://www.adobe.io/). Neem contact op met uw organisatiebeheerder voor verzoeken om toegang.

### Verificatie

Voer de onderstaande stappen uit om [!DNL JWT (Service Account)] verificatie te configureren met [!DNL Adobe I/O]:

1. Meld u aan bij de [Adobe Developer Console](https://console.adobe.io/).
1. Volg de stappen in de Verbinding [van de Rekening van de](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Dienst.
   * Tijdens [stap 2: Voeg een API aan uw project toe gebruikend de authentificatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)van de Rekening van de Dienst, kies de [!DNL Audience Manager] [!DNL API] optie.
1. Probeer uit de verbinding door uw eerste [!DNL API] vraag te maken die op de instructies van [Stap 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)wordt gebaseerd.

>[!NOTE]
>
>Om met het [!DNL Audience Manager] op een geautomatiseerde manier te vormen en te werken, kunt u [!DNL REST APIs] [!DNL JWT] programmatically produceren. Zie [JWT-verificatie (serviceaccount)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) voor gedetailleerde instructies.

## [!DNL OAuth] Verificatie (afgekeurd) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] tokenauthentificatie en vernieuwing via [!DNL OAuth 2.0] is nu afgekeurd .
>
> Gebruik in plaats hiervan [JWT-verificatie](#jwt-service-account-authentication-jwt) (serviceaccount).

De [!DNL Audience Manager][!UICONTROL REST API] volgende [!DNL OAuth 2.0] normen voor symbolische authentificatie en vernieuwing. In de onderstaande secties wordt beschreven hoe u de [!DNL API]s kunt verifiëren en waarmee u kunt gaan werken.

### Een algemene [!DNL API] gebruiker maken {#requirements}

We raden u aan een aparte, technische gebruikersaccount te maken voor het werken met de [!DNL Audience Manager] [!DNL API]s. Dit is een generische rekening die niet aan of verbonden met een specifieke gebruiker in uw organisatie is. Met dit type [!DNL API] gebruikersaccount kunt u twee dingen doen:

* Identificeer welke dienst de [!DNL API] (bijvoorbeeld, vraag van uw apps die onze [!DNL API]s of van andere hulpmiddelen gebruiken die [!DNL API] verzoeken indienen) roept.
* Ononderbroken toegang tot de [!DNL API]bestanden bieden. Een account die aan een bepaalde persoon is gekoppeld, kan worden verwijderd wanneer deze uw bedrijf verlaat. Zo voorkomt u dat u met de beschikbare [!DNL API] code werkt. Met een algemene account die niet aan een bepaalde werknemer is gekoppeld, voorkomt u dit probleem.

Als voorbeeld of gebruiksgeval voor dit type van rekening, laten wij zeggen u veel segmenten in één keer met de Hulpmiddelen [van het Beheer van het](../../reference/bulk-management-tools/bulk-management-intro.md)Bulk wilt veranderen. Je gebruikersaccount heeft hiervoor [!DNL API] toegang nodig. In plaats van toestemmingen aan een specifieke gebruiker toe te voegen, creeer een niet-specifieke, [!DNL API] gebruikersrekening die de aangewezen geloofsbrieven, de sleutel, en het geheim heeft om [!DNL API] vraag te maken. Dit is ook nuttig als u uw eigen toepassingen ontwikkelt die de [!DNL Audience Manager] [!DNL API]s gebruiken.

Werk samen met uw [!DNL Audience Manager] consultant om een algemene, [!DNL API]alleen-Engelstalige gebruikersaccount in te stellen.

### Workflow voor wachtwoordverificatie {#password-authentication-workflow}

Wachtwoordverificatie maakt veilige toegang tot onze [!DNL REST API]. In de onderstaande stappen wordt een overzicht gegeven van de workflow voor wachtwoordverificatie van een [!DNL JSON] client in uw browser.

>[!TIP]
>
>Codeer toegang en vernieuw tokens als u hen in een gegevensbestand opslaat.

#### Stap 1: Toegang aanvragen [!DNL API]

Contacteer uw manager van de Oplossingen van de Partner. Ze geven je een [!DNL API] client-id en een geheim. De id en het geheim verifiëren u aan de [!DNL API].

Opmerking: Als u een vernieuwingstoken wilt ontvangen, specificeer dat wanneer u om [!DNL API] toegang verzoekt.

#### Stap 2: Token aanvragen

Geef een tokenverzoek door aan uw voorkeursclient [!DNL JSON] . Wanneer u het verzoek bouwt:

* Gebruik een `POST` methode om aan te roepen `https://api.demdex.com/oauth/token`.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. De referenties worden bijvoorbeeld `testId : testSecret` omgezet in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Geef het document door [!DNL HTTP] en [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` `Content-Type: application/x-www-form-urlencoded` . De koptekst kan er bijvoorbeeld als volgt uitzien: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
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

De `expires_in` sleutel vertegenwoordigt het aantal seconden tot het toegangstoken verloopt. U kunt het beste korte vervaltijden gebruiken om de belichting te beperken als het token ooit wordt blootgesteld.

### Token vernieuwen {#refresh-token}

Vernieuw tokens vernieuwen [!DNL API] toegang nadat het originele token is verlopen. Indien gevraagd, bevat de reactie [!DNL JSON] in de wachtwoordworkflow een token voor vernieuwen. Als u ontvangt vernieuw symbolisch, creeer nieuwe door het proces van de wachtwoordauthentificatie.

U kunt ook een vernieuwingstoken gebruiken om een nieuw token te genereren voordat het bestaande toegangstoken verloopt.

Als uw toegangstoken is verlopen, ontvangt u een `401 Status Code` en volgende kopbal in de reactie:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

In de volgende stappen wordt een overzicht gegeven van de workflow voor het gebruik van een vernieuwingstoken om een nieuw toegangstoken te maken van een [!DNL JSON] client in uw browser.

#### Stap 1: Nieuwe token aanvragen

Geef een aanvraag voor een vernieuwingstoken door aan de gewenste [!DNL JSON] client. Wanneer u het verzoek bouwt:

* Gebruik een `POST` methode om aan te roepen `https://api.demdex.com/oauth/token`.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. De referenties worden bijvoorbeeld `testId : testSecret` omgezet in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Geef de HTTP-headers `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded`. De koptekst kan er bijvoorbeeld als volgt uitzien: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* In het verzoeklichaam, specificeer `grant_type:refresh_token` en ga in vernieuwt teken over u in uw vorig toegangsverzoek ontving. Het verzoek moet er als volgt uitzien: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Stap 2: Het nieuwe token ontvangen

De [!DNL JSON] reactie bevat uw nieuwe toegangstoken. De reactie moet er als volgt uitzien:

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

De [!DNL Audience Manager] [!UICONTROL REST API] ondersteuning voor machtigingscode en impliciete verificatie. Om deze toegangsmethodes te gebruiken, moeten uw gebruikers login aan `https://api.demdex.com/oauth/authorize` om toegang te krijgen en tokens te verfrissen.

## Voor authentiek verklaarde [!DNL API] verzoeken maken {#authenticated-api-requests}

Vereisten voor het roepen van [!DNL API] methodes nadat u een authentificatietoken ontvangt.

Om vraag tegen de beschikbare [!DNL API] methodes te maken:

* Stel in de `HTTP` koptekst de waarde in `Authorization: Bearer <token>`.
* Wanneer u [JWT-verificatie](#jwt)(serviceaccount) gebruikt, moet u de `x-api-key` koptekst opgeven. Deze zal hetzelfde zijn als uw `client_id`account. U kunt uw `client_id` van de [Adobe I/O integratiepagina](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) krijgen.
* Roep de vereiste [!DNL API] methode aan.

## Optionele [!DNL API] queryparameters {#optional-api-query-parameters}

Stel de optionele parameters in die beschikbaar zijn voor methoden die alle eigenschappen voor een object retourneren.

U kunt deze optionele parameters gebruiken met [!DNL API] methoden die *alle* eigenschappen van een object retourneren. Plaats deze opties in het verzoekkoord wanneer het overgaan van die vraag in aan het [!DNL API].

| Parameter | Beschrijving |
|--- |--- |
| `page` | Geeft resultaten op paginanummer. De nummering begint bij 0. |
| `pageSize` | Stelt het aantal reactieresultaten in dat door de aanvraag wordt geretourneerd (10 is standaard). |
| `sortBy` | Sorteert en retourneert resultaten volgens de opgegeven [!DNL JSON] eigenschap. |
| `descending` | Sorteert en retourneert resultaten in aflopende volgorde. `ascending` is standaard. |
| `search` | Retourneert resultaten op basis van de opgegeven tekenreeks die u als zoekparameter wilt gebruiken. Bijvoorbeeld, laten wij zeggen u resultaten voor alle modellen wilt vinden die het woord &quot;Test&quot;in om het even welke waardegebieden voor dat punt hebben. Uw voorbeeldverzoek kan er als volgt uitzien:   `GET https://aam.adobe.io/v1/models/?search=Test`.  U kunt zoeken op elke waarde die door de methode &quot;[!DNL get all]&quot; wordt geretourneerd. |
| `folderId` | Retourneert alle id&#39;s voor [!UICONTROL traits] de opgegeven map. Niet beschikbaar voor alle methoden. |
| `permissions` | Retourneert een lijst met segmenten op basis van de opgegeven machtiging. `READ` is standaard. Bevoegdheden omvatten:<ul><li>`READ` : De terugkeer en bekijkt informatie over een segment.</li><li>`WRITE` : Gebruik deze optie `PUT` om een segment bij te werken.</li><li>`CREATE` : Gebruik deze optie `POST` om een segment te maken.</li><li>`DELETE` : Een segment verwijderen. Vereist toegang tot eventuele onderliggende kenmerken. Bijvoorbeeld, zult u rechten nodig hebben om de eigenschappen te schrappen die tot een segment behoren als u het wilt verwijderen.</li></ul><br>Geef meerdere machtigingen op met afzonderlijke sleutelwaardeparen. Als u bijvoorbeeld een lijst met segmenten wilt retourneren met alleen `READ` en alleen `WRITE` machtigingen, geeft u deze door `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Reeks aan `true` om uw toestemmingen voor het segment terug te keren. Standaard is dit `false`. |

### Een opmerking over paginaopties

Wanneer pagina-informatie niet ** wordt opgegeven, retourneert de aanvraag onbewerkte [!DNL JSON] resultaten in een array. Als pagina-informatie *is* opgegeven, wordt de geretourneerde lijst omsloten in een [!DNL JSON] object dat informatie bevat over het totale resultaat en de huidige pagina. Uw voorbeeldverzoek met behulp van paginaopties kan er als volgt uitzien:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] voor verzoeken, het opvoeren en productiemilieu&#39;s, en versies.

## Verzoek [!DNL URLs] {#request-urls}

De volgende lijst maakt een lijst van het verzoek [!DNL URLs] wordt gebruikt om [!DNL API] verzoeken, door methode over te gaan die.

Afhankelijk van de authentificatiemethode die u gebruikt, moet u uw verzoek [!DNL URLs] volgens de hieronder lijsten aanpassen.

### Verzoek [!DNL URLs] om [!DNL JWT] verificatie {#request-urls-jwt}

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

### Aanvraag [!DNL URLs] voor [!DNL OAuth] verificatie (afgekeurd) {#request-urls-oauth}

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

De [!DNL Audience Manager] [!DNL API]programma&#39;s bieden toegang tot verschillende werkomgevingen. Deze milieu&#39;s helpen u code tegen afzonderlijke gegevensbestanden testen zonder levende, productiegegevens te beïnvloeden. De volgende lijst maakt een lijst van de beschikbare [!DNL API] milieu&#39;s en overeenkomstige middel hostnames.

Afhankelijk van de verificatiemethode die u gebruikt, moet u de omgeving aanpassen [!DNL URLs] volgens de onderstaande tabel.

| Omgeving | Hostnaam voor [!DNL JWT] verificatie | Hostnaam voor [!DNL OAuth] verificatie |
|---|---|---|
| **Productie** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>De [!DNL Audience Manager] bètaomgeving is een kleinschalige, zelfstandige versie van de productieomgeving. Alle gegevens die u wilt testen, moeten in deze omgeving worden ingevoerd en verzameld.

## Versies {#versions}

De nieuwe versies van deze [!DNL API]s worden vrijgegeven op een regelmatig programma. Een nieuwe versie verhoogt het [!DNL API] versienummer. In de aanvraag wordt naar het versienummer verwezen, [!DNL URL] zoals in het volgende voorbeeld wordt `v<version number>` getoond:

`https://<host>/v1/...`

## Responscodes gedefinieerd {#response-codes-defined}

`HTTP` statuscodes en reactietekst die door de [!DNL Audience Manager] [!UICONTROL REST API]gebruiker worden geretourneerd.

| Antwoordcode-id | Antwoordtekst | Definitie |
|---|---|---|
| `200` | `OK` | De aanvraag is verwerkt. Hiermee worden de verwachte inhoud of gegevens geretourneerd, indien vereist. |
| `201` | `Created` | De bron is gemaakt. Retourneert voor `PUT` en `POST` aanvragen. |
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

