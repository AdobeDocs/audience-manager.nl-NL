---
description: Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek URLs, en andere verwijzingen.
seo-description: Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek URLs, en andere verwijzingen.
seo-title: Aan de slag met REST-API’s
solution: Audience Manager
title: Aan de slag met REST-API’s
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: ab8745a8ba24154793201893a39a039b5a098833
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 2%

---


# Aan de slag met [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek [!DNL URLs], en andere verwijzingen.

<!-- c_rest_api_overview.xml -->

## API-vereisten en -aanbevelingen {#api-requirements-recommendations}

Wat u moet en moet doen wanneer u met [!DNL Audience Manager] [!DNL API]s werkt.

<!-- aam-api-requirements.xml -->

Let op het volgende wanneer u werkt met [Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#/)-code:

* **Request-parameters:** alle aanvraagparameters zijn vereist, tenzij anders is opgegeven.
* **Aanvraagkoppen**: wanneer u  [Adobe I/](https://www.adobe.io/) Otokens gebruikt, moet u de  `x-api-key` kopbal verstrekken. U kunt uw [!DNL API] sleutel krijgen door de instructies in [de pagina van de Rekening van de Dienst te volgen Integratie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]inhoudssoort:** Geef  `content-type: application/json`  **  `accept: application/json` en in de code op.
* **Verzoeken en reacties:** Verstuur aanvragen als een correct opgemaakt  [!DNL JSON] object. [!DNL Audience Manager] reageert met  [!DNL JSON] opgemaakte gegevens. Serverreacties kunnen gevraagde gegevens, een statuscode of beide bevatten.
* **Toegang:** Uw  [!DNL Audience Manager] consultant geeft u een client-id en sleutel waarmee u  [!DNL API] aanvragen kunt indienen.
* **Documentatie en codevoorbeelden:** Tekst in  ** cursief vertegenwoordigt een variabele die u opgeeft of doorgeeft bij het maken of ontvangen van  [!DNL API] gegevens. Vervang *cursieve* tekst met uw eigen code, parameters, of andere vereiste informatie.

## Verificatie {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] steunt twee authentificatiemethodes.

* [JWT-](#jwt) verificatie (serviceaccount) met  [Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] is Adobe. Het omvat [Adobe I/O ontwikkelaarshulpmiddelen en APIs](https://www.adobe.io/apis/experienceplatform.html) en [APIs voor alle producten van de Adobe](https://www.adobe.io/apis.html). Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs] in te stellen en te gebruiken.
* [OAuth-verificatie (afgekeurd)](#oauth). Hoewel deze methode is afgekeurd, kunnen klanten met bestaande [!DNL OAuth]-integratie deze methode blijven gebruiken.

>[!IMPORTANT]
>
>Afhankelijk van uw authentificatiemethode, moet u uw verzoek [!DNL URLs] dienovereenkomstig aanpassen. Zie de sectie [Omgevingen](#environments) voor meer informatie over de hostnamen die u moet gebruiken.

## [!DNL JWT] ([!DNL Service Account]) Verificatie met Adobe I/O  {#jwt}

### Adobe I/O - overzicht {#adobeio}

[!DNL Adobe I/O] is Adobe. Het omvat [Adobe I/O ontwikkelaarshulpmiddelen en APIs](https://www.adobe.io/apis/experienceplatform.html) en [APIs voor alle producten van de Adobe](https://www.adobe.io/apis.html).

Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs] in te stellen en te gebruiken.

### Vereisten {#prerequisites}

Voordat u [!DNL JWT]-verificatie kunt configureren, moet u ervoor zorgen dat u toegang hebt tot de [Adobe Developer Console](https://console.adobe.io/) in [Adobe I/O](https://www.adobe.io/). Neem contact op met uw organisatiebeheerder voor verzoeken om toegang.

### Verificatie {#auth}

Voer de onderstaande stappen uit om [!DNL JWT (Service Account)]-verificatie te configureren met [!DNL Adobe I/O]:

1. Meld u aan bij [Adobe Developer Console](https://console.adobe.io/).
1. Voer de stappen in [Servicerekening Connection](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) uit.
   * Tijdens [Stap 2: Voeg een API aan uw project toe gebruikend de authentificatie van de Rekening van de Dienst](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), kies [!DNL Audience Manager] [!DNL API] optie.
1. Probeer uit de verbinding door uw eerste [!DNL API] vraag te maken die op de instructies van [Stap 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) wordt gebaseerd.

>[!NOTE]
>
>Als u [!DNL Audience Manager] [!DNL REST APIs] automatisch wilt configureren en gebruiken, kunt u [!DNL JWT] programmatisch genereren. Zie [JWT-verificatie (serviceaccount)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) voor gedetailleerde instructies.

## [!DNL OAuth] Verificatie (afgekeurd)  {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] tokenauthentificatie en vernieuwing via  [!DNL OAuth 2.0] is nu afgekeurd .
>
> Gebruik in plaats hiervan [JWT-verificatie (serviceaccount)](#jwt-service-account-authentication-jwt).

[!DNL Audience Manager] [!UICONTROL REST API] volgt [!DNL OAuth 2.0] normen voor tokenauthentificatie en vernieuwing. In de onderstaande secties wordt beschreven hoe u de [!DNL API]s kunt verifiëren en waarmee u kunt gaan werken.

### Een algemene [!DNL API]-gebruiker {#requirements} maken

We raden u aan een aparte, technische gebruikersaccount te maken voor het werken met de [!DNL Audience Manager] [!DNL API]s. Dit is een generische rekening die niet aan of verbonden met een specifieke gebruiker in uw organisatie is. Dit type van [!DNL API] gebruikersrekening helpt u 2 dingen verwezenlijken:

* Identificeer welke dienst [!DNL API] (b.v., vraag van uw apps die onze [!DNL API]s of van andere hulpmiddelen gebruiken die [!DNL API] verzoeken indienen) roept.
* Ononderbroken toegang tot de [!DNL API]s bieden. Een account die aan een bepaalde persoon is gekoppeld, kan worden verwijderd wanneer deze uw bedrijf verlaat. Zo voorkomt u dat u met de beschikbare [!DNL API]-code werkt. Met een algemene account die niet aan een bepaalde werknemer is gekoppeld, voorkomt u dit probleem.

Als voorbeeld of gebruiksgeval voor dit type van rekening, laten wij zeggen u een hoop segmenten in één keer met [Bulk de Hulpmiddelen van het Beheer wilt veranderen](../../reference/bulk-management-tools/bulk-management-intro.md). Wel, om dit te doen, heeft uw gebruikersrekening [!DNL API] toegang nodig. In plaats van toestemmingen aan een specifieke gebruiker toe te voegen, creeer een niet-specifieke, [!DNL API] gebruikersrekening die de aangewezen geloofsbrieven, de sleutel, en het geheim heeft om [!DNL API] vraag te maken. Dit is ook nuttig als u uw eigen toepassingen ontwikkelt die [!DNL Audience Manager] [!DNL API]s gebruiken.

Werk samen met uw [!DNL Audience Manager]-consultant om een algemene, [!DNL API]-alleen-gebruikersaccount in te stellen.

### Workflow {#password-authentication-workflow} voor wachtwoordverificatie

Veilige toegang tot onze [!DNL REST API] voor wachtwoordverificatie. In de onderstaande stappen wordt een overzicht gegeven van de workflow voor wachtwoordverificatie van een [!DNL JSON]-client in uw browser.

>[!TIP]
>
>Codeer toegang en vernieuw tokens als u hen in een gegevensbestand opslaat.

#### Stap 1: Toegang aanvragen [!DNL API]

Contacteer uw manager van de Oplossingen van de Partner. Ze geven u een [!DNL API] client-id en een geheim. De id en het geheim verklaren u aan [!DNL API] voor authentiek.

Opmerking: Als u een vernieuwingstoken wilt ontvangen, specificeer dat wanneer u [!DNL API] toegang verzoekt.

#### Stap 2: Token aanvragen

Geef een symbolisch verzoek door met uw aangewezen [!DNL JSON] cliënt. Wanneer u het verzoek bouwt:

* Gebruik een `POST` methode om `https://api.demdex.com/oauth/token` te roepen.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. Bijvoorbeeld, zetten de geloofsbrieven `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=` om.
* Geef [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded` door. De koptekst kan er bijvoorbeeld als volgt uitzien: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Stel de aanvraaginstantie als volgt in:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Stap 3: Token ontvangen

De reactie [!DNL JSON] bevat uw toegangstoken. De reactie moet er als volgt uitzien:

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

### Token {#refresh-token} vernieuwen

Verfris tokens vernieuwen [!DNL API] toegang nadat het originele teken verloopt. Indien gevraagd, bevat het antwoord [!DNL JSON] in de wachtwoordwerkstroom een vernieuwingstoken. Als u ontvangt vernieuw symbolisch, creeer nieuwe door het proces van de wachtwoordauthentificatie.

U kunt ook een vernieuwingstoken gebruiken om een nieuw token te genereren voordat het bestaande toegangstoken verloopt.

Als uw toegangstoken is verlopen, ontvangt u een `401 Status Code` en de volgende kopbal in de reactie:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

In de volgende stappen wordt een overzicht gegeven van de workflow voor het gebruik van een vernieuwingstoken om een nieuw toegangstoken te maken op basis van een [!DNL JSON]-client in uw browser.

#### Stap 1: Nieuwe token aanvragen

Geef een vernieuwingstoken-aanvraag door met de gewenste [!DNL JSON]-client. Wanneer u het verzoek bouwt:

* Gebruik een `POST` methode om `https://api.demdex.com/oauth/token` te roepen.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. Bijvoorbeeld, zetten de geloofsbrieven `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=` om.
* Geef de HTTP-headers `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded` door. De koptekst kan er bijvoorbeeld als volgt uitzien: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* In het verzoeklichaam, specificeer `grant_type:refresh_token` en ga in vernieuwt teken over u in uw vorig toegangsverzoek ontving. Het verzoek moet er als volgt uitzien: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Stap 2: Het nieuwe token ontvangen

De reactie [!DNL JSON] bevat uw nieuw toegangstoken. De reactie moet er als volgt uitzien:

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

[!DNL Audience Manager] [!UICONTROL REST API] steunt vergunningscode en impliciete authentificatie. Om deze toegangsmethodes te gebruiken, moeten uw gebruikers login aan `https://api.demdex.com/oauth/authorize` om toegang te krijgen en tokens te verfrissen.

## Voor authentiek [!DNL API] verzoeken {#authenticated-api-requests} maken

Vereisten voor het aanroepen van [!DNL API]-methoden nadat u een verificatietoken hebt ontvangen.

Om vraag tegen de beschikbare [!DNL API] methodes te maken:

* Stel `Authorization: Bearer <token>` in de koptekst `HTTP` in.
* Wanneer u [JWT (serviceaccount)-verificatie](#jwt) gebruikt, moet u de `x-api-key`-header opgeven, die hetzelfde zal zijn als uw `client_id`. U kunt uw `client_id` van de [Adobe I/O integratie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) pagina krijgen.
* Roep de vereiste [!DNL API] methode aan.

## Optionele [!DNL API] Query-parameters {#optional-api-query-parameters}

Stel de optionele parameters in die beschikbaar zijn voor methoden die alle eigenschappen voor een object retourneren.

U kunt deze optionele parameters gebruiken met [!DNL API] methoden die *all* eigenschappen voor een object retourneren. Plaats deze opties in het verzoekkoord wanneer het overgaan van die vraag binnen aan [!DNL API].

| Parameter | Beschrijving |
|--- |--- |
| `page` | Geeft resultaten op paginanummer. De nummering begint bij 0. |
| `pageSize` | Stelt het aantal reactieresultaten in dat door de aanvraag wordt geretourneerd (10 is standaard). |
| `sortBy` | Sorteert en retourneert resultaten volgens de opgegeven [!DNL JSON]-eigenschap. |
| `descending` | Sorteert en retourneert resultaten in aflopende volgorde. `ascending` is standaard. |
| `search` | Retourneert resultaten op basis van de opgegeven tekenreeks die u als zoekparameter wilt gebruiken. Bijvoorbeeld, laten wij zeggen u resultaten voor alle modellen wilt vinden die het woord &quot;Test&quot;in om het even welke waardegebieden voor dat punt hebben. Uw voorbeeldverzoek kan er als volgt uitzien:   `GET https://aam.adobe.io/v1/models/?search=Test`.  U kunt op om het even welke waarde zoeken die door &quot;[!DNL get all]&quot;methode is teruggekeerd. |
| `folderId` | Retourneert alle id&#39;s voor [!UICONTROL traits] in de opgegeven map. Niet beschikbaar voor alle methoden. |
| `permissions` | Retourneert een lijst met segmenten op basis van de opgegeven machtiging. `READ` is standaard. Bevoegdheden omvatten:<ul><li>`READ` : De terugkeer en bekijkt informatie over een segment.</li><li>`WRITE` : Gebruik deze optie   `PUT`  om een segment bij te werken.</li><li>`CREATE` : Gebruik deze optie   `POST`  om een segment te maken.</li><li>`DELETE` : Een segment verwijderen. Vereist toegang tot eventuele onderliggende kenmerken. Bijvoorbeeld, zult u rechten nodig hebben om de eigenschappen te schrappen die tot een segment behoren als u het wilt verwijderen.</li></ul><br>Geef meerdere machtigingen op met afzonderlijke sleutelwaardeparen. Als u bijvoorbeeld een lijst wilt retourneren met alleen `READ`- en `WRITE`-machtigingen, geeft u `"permissions":"READ"`, `"permissions":"WRITE"` door. |
| `includePermissions` | ([!DNL Boolean]) Reeks aan `true` om uw toestemmingen voor het segment terug te keren. De standaardwaarde is `false`. |

### Een opmerking over paginaopties

Wanneer de paginainformatie *niet* gespecificeerd is, keert het verzoek duidelijke [!DNL JSON] in een serie terug. Als paginainformatie *is* gespecificeerd, dan wordt de teruggekeerde lijst verpakt in een [!DNL JSON] voorwerp dat informatie over het totale resultaat en de huidige pagina bevat. Uw voorbeeldverzoek met behulp van paginaopties kan er als volgt uitzien:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] voor verzoeken, het opvoeren en productiemilieu&#39;s, en versies.

## Verzoek [!DNL URLs] {#request-urls}

De volgende lijst maakt een lijst van het verzoek [!DNL URLs] wordt gebruikt om binnen [!DNL API] verzoeken, door methode over te gaan die.

Afhankelijk van de authentificatiemethode die u gebruikt, moet u uw verzoek [!DNL URLs] volgens de hieronder lijsten aanpassen.

### Verzoek [!DNL URLs] om [!DNL JWT]-verificatie {#request-urls-jwt}

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

### Verzoek [!DNL URLs] om [!DNL OAuth] (Afgekeurd) {#request-urls-oauth}

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

Met de [!DNL Audience Manager] [!DNL API]s hebt u toegang tot verschillende werkomgevingen. Deze milieu&#39;s helpen u code tegen afzonderlijke gegevensbestanden testen zonder levende, productiegegevens te beïnvloeden. De volgende lijst maakt een lijst van de beschikbare [!DNL API] milieu&#39;s en overeenkomstige middel hostnames.

Afhankelijk van de verificatiemethode die u gebruikt, moet u de omgeving [!DNL URLs] aanpassen volgens de onderstaande tabel.

| Omgeving | Hostnaam voor [!DNL JWT]-verificatie | Hostnaam voor [!DNL OAuth]-verificatie |
|---|---|---|
| **Productie** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>De bètaomgeving [!DNL Audience Manager] is een zelfstandige, kleinere versie van de productieomgeving. Alle gegevens die u wilt testen, moeten in deze omgeving worden ingevoerd en verzameld.

## Versies {#versions}

Nieuwe versies van deze [!DNL API]s worden vrijgegeven op een regelmatig programma. Een nieuwe versie verhoogt het [!DNL API] versienummer. In het verzoek [!DNL URL] wordt naar het versienummer verwezen als `v<version number>`, zoals in het volgende voorbeeld wordt getoond:

`https://<host>/v1/...`

## Responscodes gedefinieerd {#response-codes-defined}

`HTTP` statuscodes en reactietekst die door de  [!DNL Audience Manager] [!UICONTROL REST API].

| Antwoordcode-id | Antwoordtekst | Definitie |
|---|---|---|
| `200` | `OK` | De aanvraag is verwerkt. Hiermee worden de verwachte inhoud of gegevens geretourneerd, indien vereist. |
| `201` | `Created` | De bron is gemaakt. Retourneert voor `PUT`- en `POST`-aanvragen. |
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

