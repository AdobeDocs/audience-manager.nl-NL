---
description: Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek URLs, en andere verwijzingen.
seo-description: Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek URLs, en andere verwijzingen.
seo-title: Aan de slag met REST API's
solution: Audience Manager
title: Aan de slag met REST API's
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: b78dc6df380d43b809ae169f23eea208cd951a4b
workflow-type: tm+mt
source-wordcount: '1890'
ht-degree: 1%

---


# Aan de slag met REST API&#39;s {#getting-started-with-rest-apis}

Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek URLs, en andere verwijzingen.

<!-- c_rest_api_overview.xml -->

## API-vereisten en aanbevelingen {#api-requirements-recommendations}

Wat u moet en moet doen wanneer u met de Manager [!DNL API]van de Publiek werkt.

<!-- aam-api-requirements.xml -->

Let op het volgende wanneer u werkt met API [-code van](https://bank.demdex.com/portal/swagger/index.html#/) Audience Manager:

* **Parameters aanvragen:** Alle verzoekparameters worden vereist tenzij anders gespecificeerd.
* **Aanvraagkopteksten**: wanneer u [Adobe I/O](https://www.adobe.io/) -tokens gebruikt, moet u de `x-api-key` koptekst opgeven. U kunt uw API-sleutel ophalen door de instructies op de pagina [Servicerekenintegratie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) op te volgen.
* **[!DNL JSON]inhoudstype:**Geef de code op`content-type: application/json`en geef **`accept: application/json`deze op.

* **Verzoeken en antwoorden:** Verstuur aanvragen als een correct opgemaakt [!DNL JSON] object. [!DNL Audience Manager] reageert met [!DNL JSON] opgemaakte gegevens. Serverreacties kunnen gevraagde gegevens, een statuscode of beide bevatten.

* **Toegang:** Uw [!DNL Audience Manager] consultant geeft u een client-id en sleutel waarmee u [!DNL API] aanvragen kunt indienen.

* **Documentatie en codevoorbeelden:** Tekst *cursief* staat voor een variabele die u opgeeft of doorgeeft bij het maken of ontvangen van [!DNL API] gegevens. Vervang *cursieve* tekst door uw eigen code, parameters of andere vereiste informatie.

## Verificatie {#authentication}

De API&#39;s van de Audience Manager REST ondersteunen twee verificatiemethoden.

* [JWT-verificatie (serviceaccount)](#jwt). Dit is de geadviseerde authentificatiemethode.
* [OAuth-verificatie (afgekeurd)](#oauth). Terwijl deze methode verouderd is, kunnen de klanten met bestaande integratie OAuth blijven gebruiken deze methode.

>[!IMPORTANT]
>
>Afhankelijk van uw authentificatiemethode, moet u uw verzoek URLs dienovereenkomstig aanpassen. Zie de sectie [Omgevingen](#environments) voor meer informatie over de hostnamen die u moet gebruiken.

## JWT-verificatie (serviceaccount) {#jwt}

### Vereisten {#prerequisites}

Voordat u JWT-verificatie kunt configureren, moet u ervoor zorgen dat u toegang hebt tot de [Adobe Developer Console](https://console.adobe.io/). Neem contact op met uw organisatiebeheerder voor verzoeken om toegang.

### Verificatie

Voer de onderstaande stappen uit om JWT-verificatie (serviceaccount) te configureren:

1. Meld u aan bij de [Adobe Developer Console](https://console.adobe.io/).
1. Volg de stappen in de Verbinding [van de Rekening van de](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Dienst.
   * Tijdens [stap 2: Voeg een API aan uw project toe gebruikend de authentificatie](https://www.adobe.io/authentication/auth-methods.html#step-2-add-an-api-to-your-project-using-service-account-authentication)van de Rekening van de Dienst, kies de optie van de Manager API van de Publiek.
1. Probeer de verbinding uit door uw eerste API vraag te maken die op de instructies van [Stap 3](https://www.adobe.io/authentication/auth-methods.html#step-3-try-it.)wordt gebaseerd.

>[!NOTE]
>
>Als u de REST API&#39;s van Audience Manager automatisch wilt configureren en ermee wilt werken, kunt u de JWT programmatisch genereren. Zie [JWT-verificatie (serviceaccount)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) voor gedetailleerde instructies.

## OAuth-verificatie (afgekeurd) {#oauth}

>[!WARNING]
> De symbolische authentificatie en de vernieuwing van de Manager van de Audience [!UICONTROL REST API] via [!DNL OAuth 2.0] is nu verouderd.
>
> Gebruik in plaats hiervan [JWT-verificatie](#jwt-service-account-authentication-jwt) (serviceaccount).

De Manager van de Publiek [!UICONTROL REST API] volgt [!DNL OAuth 2.0] normen voor symbolische authentificatie en vernieuwing. In de onderstaande secties wordt beschreven hoe u de [!DNL API]s kunt verifiëren en waarmee u kunt gaan werken.

### Een generieke API-gebruiker maken {#requirements}

Wij adviseren u een afzonderlijke, technische gebruikersrekening voor het werken met de Manager [!DNL API]van de Publiek tot stand brengen. Dit is een generieke account die niet is gekoppeld aan of gekoppeld aan een specifieke gebruiker in uw organisatie. Met dit type [!DNL API] gebruikersaccount kunt u twee dingen doen:

* Identificeer welke dienst de [!DNL API] (bijvoorbeeld, vraag van uw apps die onze [!DNL API]s of van andere hulpmiddelen gebruiken die [!DNL API] verzoeken indienen) roept.
* Ononderbroken toegang tot de [!DNL API]bestanden bieden. Een account die aan een bepaalde persoon is gekoppeld, kan worden verwijderd wanneer deze uw bedrijf verlaat. Zo voorkomt u dat u met de beschikbare [!DNL API] code werkt. Met een algemene account die niet aan een bepaalde werknemer is gekoppeld, voorkomt u dit probleem.

Als voorbeeld of gebruiksgeval voor dit type van rekening, laten wij zeggen u veel segmenten in één keer met de Hulpmiddelen [van het Beheer van het](../../reference/bulk-management-tools/bulk-management-intro.md)Bulk wilt veranderen. Je gebruikersaccount heeft hiervoor [!DNL API] toegang nodig. In plaats van toestemmingen aan een specifieke gebruiker toe te voegen, creeer een niet-specifieke, [!DNL API] gebruikersrekening die de aangewezen geloofsbrieven, de sleutel, en het geheim heeft om [!DNL API] vraag te maken. Dit is ook nuttig als u uw eigen toepassingen ontwikkelt die de Manager [!DNL API]van de Publiek gebruiken.

Werk samen met uw consultant voor Audience Manager om een algemene gebruikersaccount in te stellen die [!DNL API]alleen beschikbaar is.

### Workflow voor wachtwoordverificatie {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Wachtwoordverificatie maakt veilige toegang tot onze [!DNL REST API]. In de onderstaande stappen wordt een overzicht gegeven van de workflow voor wachtwoordverificatie van een [!DNL JSON] client in uw browser.

>[!TIP]
>
>Codeer toegang en vernieuw tokens als u hen in een gegevensbestand opslaat.

#### Stap 1: API-toegang aanvragen

Contacteer uw manager van de Oplossingen van de Partner. Ze geven je een [!DNL API] client-id en een geheim. De id en het geheim verifiëren u aan de [!DNL API].

Opmerking: Als u een vernieuwingstoken wilt ontvangen, specificeer dat wanneer u om [!DNL API] toegang verzoekt.

#### Stap 2: Token aanvragen

Geef een tokenverzoek door aan uw voorkeursclient [!DNL JSON] . Wanneer u het verzoek bouwt:

* Gebruik een `POST` methode om aan te roepen `https://api.demdex.com/oauth/token`.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. De referenties worden bijvoorbeeld `testId : testSecret` omgezet in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Geef in de [!DNL HTTP] kopballen `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded` door. De koptekst kan er bijvoorbeeld als volgt uitzien: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
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
* Geef de HTTP-headers `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded`. De koptekst kan er bijvoorbeeld als volgt uitzien: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In het verzoeklichaam, specificeer `grant_type:refresh_token` en ga in vernieuwt teken over u in uw vorig toegangsverzoek ontving. Het verzoek moet er als volgt uitzien: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

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

De Manager van de Publiek [!UICONTROL REST API] steunt vergunningscode en impliciete authentificatie. Om deze toegangsmethodes te gebruiken, moeten uw gebruikers login aan `https://api.demdex.com/oauth/authorize` om toegang te krijgen en tokens te verfrissen.

## Erkende API-verzoeken maken {#authenticated-api-requests}

Vereisten voor het roepen van [!DNL API] methodes nadat u een authentificatietoken ontvangt.

<!-- c_oauth_call_methods.xml -->

Om vraag tegen de beschikbare [!DNL API] methodes te maken:

* Stel in de `HTTP` koptekst de waarde in `Authorization: Bearer <token>`.
* Wanneer u [JWT-verificatie](#jwt)(serviceaccount) gebruikt, moet u de `x-api-key` koptekst opgeven. Deze zal hetzelfde zijn als uw `client_id`account. U kunt uw `client_id` van de [Adobe I/O integratiepagina](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) krijgen.
* Roep de vereiste [!DNL API] methode aan.

## Optionele API-queryparameters {#optional-api-query-parameters}

Stel de optionele parameters in die beschikbaar zijn voor methoden die alle eigenschappen voor een object retourneren.

<!-- c_rest_api_optional.xml -->

U kunt deze optionele parameters gebruiken met [!DNL API] methoden die *alle* eigenschappen van een object retourneren. Plaats deze opties in het verzoekkoord wanneer het overgaan van die vraag in aan het [!DNL API].

| Parameter | Beschrijving |
|--- |--- |
| page | Geeft resultaten op paginanummer. De nummering begint bij 0. |
| pageSize | Stelt het aantal reactieresultaten in dat door de aanvraag wordt geretourneerd (10 is standaard). |
| sortBy | Sorteert en retourneert resultaten volgens de opgegeven [!DNL JSON] eigenschap. |
| Aflopend | Sorteert en retourneert resultaten in aflopende volgorde. Oplopend is standaard. |
| zoeken | Retourneert resultaten op basis van de opgegeven tekenreeks die u als zoekparameter wilt gebruiken. Stel dat u resultaten wilt zoeken voor alle modellen die het woord &quot;Testen&quot; hebben in een van de waardevelden voor dat item. Uw voorbeeldverzoek kan er als volgt uitzien:   `GET https://aam.adobe.io/v1/models/?search=Test`.  U kunt zoeken op elke waarde die door de methode &quot;get all&quot; wordt geretourneerd. |
| folderId | Retourneert alle id&#39;s voor kenmerken in de opgegeven map. Niet beschikbaar voor alle methoden. |
| machtigingen | Retourneert een lijst met segmenten op basis van de opgegeven machtiging.  LEZEN is standaard. Bevoegdheden omvatten:<ul><li>`READ` : De terugkeer en bekijkt informatie over een segment.</li><li>`WRITE` : Gebruik deze optie `PUT` om een segment bij te werken.</li><li>`CREATE` : Gebruik deze optie `POST` om een segment te maken.</li><li>`DELETE` : Een segment verwijderen. Vereist toegang tot eventuele onderliggende kenmerken. Bijvoorbeeld, zult u rechten nodig hebben om de eigenschappen te schrappen die tot een segment behoren als u het wilt verwijderen.</li></ul><br>Geef meerdere machtigingen op met afzonderlijke sleutelwaardeparen. Als u bijvoorbeeld een lijst met segmenten wilt retourneren met alleen `READ` en alleen `WRITE` machtigingen, geeft u deze door `"permissions":"READ"`, `"permissions":"WRITE"` . |
| includePermissions | (Boolean) Ingesteld op true om uw machtigingen voor het segment te retourneren. De standaardwaarde is false. |

### Een opmerking over paginaopties

Wanneer pagina-informatie niet ** wordt opgegeven, retourneert de aanvraag onbewerkte [!DNL JSON] resultaten in een array. Als pagina-informatie *is* opgegeven, wordt de geretourneerde lijst omsloten in een [!DNL JSON] object dat informatie bevat over het totale resultaat en de huidige pagina. Uw voorbeeldverzoek met behulp van paginaopties kan er als volgt uitzien:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## API-URL&#39;s {#api-urls}

[!DNL URLs] voor verzoeken, het opvoeren en productiemilieu&#39;s, en versies.

<!-- r_rest_urls.xml -->

## Aanvraag-URL&#39;s {#request-urls}

De volgende lijst maakt een lijst van verzoek URLs die wordt gebruikt om [!DNL API] verzoeken, door methode over te gaan.

Afhankelijk van de verificatiemethode die u gebruikt, moet u de aanvraag-URL&#39;s aanpassen aan de hand van de onderstaande tabellen.

### URL&#39;s aanvragen voor JWT-verificatie {#request-urls-jwt}

| [!DNL API] Methoden | Verzoek [!DNL URL] |
|--- |--- |
| Algorithmic Modeling | `https://aam.adobe.io/v1/models/` |
| Gegevensbron | `https://aam.adobe.io/v1/datasources/` |
| Afgeleide signalen | `https://aam.adobe.io/v1/signals/derived/` |
| Doelen | `https://aam.adobe.io/v1/destinations/` |
| Domeinen | `https://aam.adobe.io/v1/partner-sites/` |
| Mappen | Tanden:  `https://aam.adobe.io/v1/folders/traits /`<br>Segmenten:  `https://aam.adobe.io/v1/folders/segments /` |
| Schema | `https://aam.adobe.io/v1/schemas/` |
| Segmenten | `https://aam.adobe.io/v1/segments/` |
| Treinen | `https://aam.adobe.io/v1/traits/` |
| Typen sporen | `https://aam.adobe.io/v1/customer-trait-types` |
| Taxonomie | `https://aam.adobe.io/v1/taxonomies/0/` |

### Aanvraag-URL&#39;s voor OAuth-verificatie (afgekeurd) {#request-urls-oauth}

| [!DNL API] Methoden | Verzoek [!DNL URL] |
|--- |--- |
| Algorithmic Modeling | `https://api.demdex.com/v1/models/` |
| Gegevensbron | `https://api.demdex.com/v1/datasources/` |
| Afgeleide signalen | `https://api.demdex.com/v1/signals/derived/` |
| Doelen | `https://api.demdex.com/v1/destinations/` |
| Domeinen | `https://api.demdex.com/v1/partner-sites/` |
| Mappen | Tanden:  `https://api.demdex.com/v1/folders/traits /`<br>Segmenten:  `https://api.demdex.com/v1/folders/segments /` |
| Schema | `https://api.demdex.com/v1/schemas/` |
| Segmenten | `https://api.demdex.com/v1/segments/` |
| Treinen | `https://api.demdex.com/v1/traits/` |
| Typen sporen | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomie | `https://api.demdex.com/v1/taxonomies/0/` |

## Omgevingen {#environments}

De [!DNL Audience Manager] [!DNL API]programma&#39;s bieden toegang tot verschillende werkomgevingen. Deze milieu&#39;s helpen u code tegen afzonderlijke gegevensbestanden testen zonder levende, productiegegevens te beïnvloeden. De volgende lijst maakt een lijst van de beschikbare [!DNL API] milieu&#39;s en overeenkomstige middel hostnames.

Afhankelijk van de verificatiemethode die u gebruikt, moet u de omgeving-URL&#39;s aanpassen aan de hand van de onderstaande tabel.

| Omgeving | Hostnaam voor JWT-verificatie | Hostnaam voor OAuth-verificatie |
|---|---|---|
| **Productie** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |


>[!NOTE]
>
>De bètaomgeving van Audience Manager is een kleinschaligere, zelfstandige versie van de productieomgeving. Alle gegevens die u wilt testen, moeten in deze omgeving worden ingevoerd en verzameld.

## Versies {#versions}

De nieuwe versies van deze [!DNL API]s worden vrijgegeven op een regelmatig programma. Een nieuwe versie verhoogt het [!DNL API] versienummer. In de aanvraag-URL wordt naar het versienummer verwezen, zoals in het volgende voorbeeld wordt `v<version number>` getoond:

`https://<host>/v1/...`

## Responscodes gedefinieerd {#response-codes-defined}

`HTTP` statuscodes en reactietekst die door de Manager van de Publiek zijn teruggekeerd [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| Antwoordcode-id | Antwoordtekst | Definitie |
|---|---|---|
| 200 | OK | De aanvraag is verwerkt. Hiermee worden de verwachte inhoud of gegevens geretourneerd, indien vereist. |
| 201 | Gemaakt | De bron is gemaakt. Retourneert voor `PUT` en `POST` aanvragen. |
| 204 | Geen inhoud | De bron is verwijderd. De responsinstantie is leeg. |
| 400 | Ongeldig verzoek | De server begrijpt het verzoek niet. Gewoonlijk als gevolg van een onjuiste syntaxis. Controleer uw verzoek en probeer het opnieuw. |
| 403 | Verboden | U hebt geen toegang tot de bron. |
| 404 | Niet gevonden | De bron kan niet worden gevonden voor het opgegeven pad. |
| 409 | Conflict | Het verzoek kon niet worden voltooid wegens een conflict met de staat van de bron. |
| 500 | Serverfout | De server heeft een onverwachte fout aangetroffen waardoor deze de aanvraag niet kan uitvoeren. |

>[!MORELIKETHIS]
>
>* [JWT-verificatie (serviceaccount)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth-verificatie](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 Vereenvoudigd](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

