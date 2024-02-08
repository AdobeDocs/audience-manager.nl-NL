---
description: Informatie over algemene vereisten, verificatie, optionele queryparameters, verzoek-URL's en andere referenties.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Aan de slag met REST-API’s
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2558'
ht-degree: 0%

---

# Aan de slag met [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek [!DNL URLs]en andere verwijzingen.

## API-vereisten en Recommendations {#api-requirements-recommendations}

Let op het volgende wanneer u werkt met [Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **Parameters aanvragen:** alle aanvraagparameters zijn vereist, tenzij anders aangegeven.
* **Aanvraagkoppen**: bij gebruik [Adobe Developer](https://www.adobe.io/) tokens, u moet de `x-api-key` header. U kunt uw [!DNL API] door de instructies in de [Integratie van serviceaccount](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) pagina.
* **[!DNL JSON]inhoudstype:** Opgeven `content-type: application/json`  *en*  `accept: application/json` in uw code.
* **Verzoeken en antwoorden:** Aanvragen verzenden als een correct opgemaakt bestand [!DNL JSON] object. [!DNL Audience Manager] reageert met [!DNL JSON] opgemaakte gegevens. Serverreacties kunnen gevraagde gegevens, een statuscode of beide bevatten.
* **Toegang:** Uw [!DNL Audience Manager] consultant zal u een klant-id en een sleutel geven waarmee u [!DNL API] verzoeken.
* **Documentatie en codevoorbeelden:** Tekst in *cursief* vertegenwoordigt een variabele die u verstrekt of binnen overgaat wanneer het maken of het ontvangen [!DNL API] gegevens. Vervangen *cursief* tekst met uw eigen code, parameters of andere vereiste informatie.

## Verificatie {#authentication}

De [!DNL Audience Manager] [!DNL REST APIs] drie verificatiemethoden ondersteunen.

* [!BADGE Aanbevolen]{type=positive}[OAuth Server-to-Server Authentificatie](#oauth-adobe-developer) gebruiken [Adobe Developer Console](https://www.adobe.io/). [!DNL Adobe Developer] is het ecosysteem en de gemeenschap van ontwikkelaars van Adobe. Hieronder vallen [API&#39;s voor alle Adobe producten](https://developer.adobe.com/apis/). Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs]. Meer informatie over [OAuth Server-to-Server Authentificatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) in de Adobe Developer documentation.
* [!BADGE Vervangen]{type=negative}[JWT-verificatie (serviceaccount)](#jwt) gebruiken [Adobe Developer Console](https://www.adobe.io/). [!DNL Adobe Developer] is het ecosysteem en de gemeenschap van ontwikkelaars van Adobe. Hieronder vallen [API&#39;s voor alle Adobe producten](https://developer.adobe.com/apis/).
* [!BADGE Vervangen]{type=negative}[Oudere OAuth-verificatie](#oauth-deprecated). Hoewel deze methode is vervangen, kunnen klanten met bestaande [!DNL OAuth] Deze methode kan worden gebruikt voor integraties.

>[!IMPORTANT]
>
>Afhankelijk van uw verificatiemethode moet u uw verzoek aanpassen [!DNL URLs] dienovereenkomstig. Zie de [Omgevingen](#environments) voor details over hostnames die u zou moeten gebruiken.

## OAuth Server-to-Server Authentificatie gebruikend Adobe Developer {#oauth-adobe-developer}

Deze sectie behandelt hoe te om de vereiste geloofsbrieven te verzamelen om Audience Manager API vraag voor authentiek te verklaren, zoals die in het stroomschema hieronder wordt geschetst. U kunt de meeste vereiste geloofsbrieven in eerste éénmalige opstelling verzamelen. Het toegangstoken, echter, moet om de 24 uur worden verfrist.

![Het diagram van de de authentificatiestroom van Audience Managers.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Adobe Developer - Overzicht {#developer-overview}

[!DNL Adobe Developer] is het ecosysteem en de gemeenschap van ontwikkelaars van Adobe. Hieronder vallen [API&#39;s voor alle Adobe producten](https://developer.adobe.com/apis).

Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs].

### Vereisten {#prerequisites-server-to-server}

Voordat u kunt configureren [!DNL OAuth Server-to-Server] verificatie, zorg ervoor dat u toegang hebt tot de [Adobe Developer Console](https://developer.adobe.com/console/home) in [Adobe Developer](https://developer.adobe.com/). Neem contact op met uw organisatiebeheerder voor verzoeken om toegang.

### Verificatie {#oauth}

Voer de onderstaande stappen uit om te configureren [!DNL OAuth Server-to-Server] verificatie met [!DNL Adobe Developer]:

1. Aanmelden bij de [Adobe Developer Console](https://developer.adobe.com/console/home).
1. Voer de stappen in het dialoogvenster [OAuth Server-to-Server referentie implementatiegids](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Tijdens [Stap 2: voeg API aan uw project toe gebruikend de authentificatie van de Rekening van de Dienst](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), kiest u de [!DNL Audience Manager] [!DNL API] -optie.
1. Probeer de verbinding uit door eerst uw [!DNL API] vraag gebaseerd op de instructies van [Stap 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Om te vormen en met het [!DNL Audience Manager] [!DNL REST APIs] op een geautomatiseerde manier, kunt u cliëntgeheimen programmatically roteren. Zie [de ontwikkelaarsdocumentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) voor gedetailleerde instructies.

### Audience Manager-API toevoegen aan een project {#add-aam-api-to-project}

Ga naar [Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) en meld u aan met uw Adobe ID. Voer vervolgens de stappen uit die in de zelfstudie worden beschreven [een leeg project maken](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) in de Adobe Developer Console-documentatie.

Als u een nieuw project hebt gemaakt, selecteert u **[!UICONTROL Add API]** op de **[!UICONTROL Project Overview]** scherm.

>[!TIP]
>
>Als u provisioned voor verscheidene organisaties bent, gebruik de organisatieselecteur in de hogere juiste hoek van de interface om ervoor te zorgen dat u in de organisatie bent u nodig hebt.

![Scherm Developer Console met de optie Add API gemarkeerd.](/help/using/api/rest-api-main/assets/add-api.png)

De **[!UICONTROL Add an API]** wordt weergegeven. Selecteer het productpictogram voor Adobe Experience Cloud en kies **[!UICONTROL Audience Manager API]** voordat u selecteert **[!UICONTROL Next]**.

![Selecteer Audience Manager-API.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Selecteer de **[!UICONTROL View docs]** om in een afzonderlijk browservenster naar het volledige venster te navigeren [Referentiedocumentatie voor Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#).

### Selecteer het verificatietype OAuth Server-to-Server {#select-oauth-server-to-server}

Selecteer vervolgens het verificatietype dat u wilt maken voor het genereren van toegangstokens en voor toegang tot de Audience Manager-API.

>[!IMPORTANT]
>
>Selecteer de **[!UICONTROL OAuth Server-to-Server]** de enige methode die wordt ondersteund om verder te gaan. De **[!UICONTROL Service Account (JWT)]** is vervangen. Terwijl de integratie die de authentificatiemethode JWT gebruikt tot 1 Januari, 2025 zal blijven werken, adviseert de Adobe sterk dat u bestaande integratie aan de nieuwe server-aan-server methode OAuth vóór die datum migreert.

![Selecteer OAuth-verificatiemethode.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Selecteer de productprofielen voor uw integratie {#select-product-profiles}

In de **[!UICONTROL Configure API]** selecteert u de gewenste productprofielen. Via de hier geselecteerde productprofielen krijgt het serviceaccount van uw integratie toegang tot korrelfuncties.

![Selecteer productprofielen voor uw integratie.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Selecteren **[!UICONTROL Save configured API]** wanneer u klaar bent.

### Referenties verzamelen {#gather-credentials}

Zodra API aan het project is toegevoegd, **[!UICONTROL Audience Manager API]** De pagina voor het project toont de volgende geloofsbrieven die in alle vraag aan Audience Manager APIs worden vereist:

![Integratiegegevens na het toevoegen van een API in de Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Een toegangstoken genereren {#generate-access-token}

De volgende stap bestaat uit het genereren van een `{ACCESS_TOKEN}` referentie voor gebruik in Audience Manager API vraag. In tegenstelling tot de waarden voor `{API_KEY}` en `{ORG_ID}`moet om de 24 uur een nieuw token worden gegenereerd om Audience Manager API&#39;s te kunnen blijven gebruiken. Selecteren **[!UICONTROL Generate access token]**, zoals hieronder weergegeven.

![Toon hoe te om toegangstoken te produceren](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Een API-aanroep testen {#test-api-call}

Nadat u het token van de verificatiehouder hebt opgehaald, voert u een API-aanroep uit om te testen of u nu toegang hebt tot Audience Manager-API&#39;s.

1. Ga naar de [API-naslagdocumentatie](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Selecteren **[!UICONTROL Authorize]** en plak het toegangstoken dat u in het [toegangstoken genereren](#generate-access-token) stap.

   ![API-aanroepen autoriseren](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Voer een vraag van de GET aan uit `/datasources` API eindpunt om een lijst van alle globaal beschikbare gegevensbronnen terug te winnen, zoals die in wordt vermeld [API-naslagdocumentatie](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Selecteren **[!UICONTROL Try it out]**, gevolgd door **[!UICONTROL Execute]**, zoals hieronder weergegeven.

   ![API-aanroepen uitvoeren](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB API-verzoek]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB API-reactie bij gebruik van de juiste token]


Wanneer het gebruiken van een werkend toegangstoken, keert het API eindpunt een 200 reactie, samen met een antwoordlichaam terug dat alle globale gegevensbronnen omvat die uw organisatie toegang heeft tot.

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE Vervangen]{type=negative}[!DNL JWT] ([!DNL Service Account]) Verificatie met Adobe Developer {#jwt}

+++ Informatie weergeven over de vervangen [!DNL JWT] ([!DNL Service Account]) methode om verificatietokens te verkrijgen.

### Adobe Developer - Overzicht {#adobeio}

[!DNL Adobe Developer] is het ecosysteem en de gemeenschap van ontwikkelaars van Adobe. Hieronder vallen [API&#39;s voor alle Adobe producten](https://www.adobe.io/apis.html).

Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs].

### Vereisten {#prerequisites}

Voordat u kunt configureren [!DNL JWT] verificatie, zorg ervoor dat u toegang hebt tot de [Adobe Developer Console](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). Neem contact op met uw organisatiebeheerder voor verzoeken om toegang.

### Verificatie {#auth}

Voer de onderstaande stappen uit om te configureren [!DNL JWT (Service Account)] verificatie met [!DNL Adobe Developer]:

1. Aanmelden bij de [Adobe Developer Console](https://console.adobe.io/).
1. Voer de stappen uit in [Verbinding serviceaccount](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Tijdens [Stap 2: voeg API aan uw project toe gebruikend de authentificatie van de Rekening van de Dienst](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), kiest u de [!DNL Audience Manager] [!DNL API] -optie.
1. Probeer de verbinding uit door eerst uw [!DNL API] vraag gebaseerd op de instructies van [Stap 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Om te vormen en met het [!DNL Audience Manager] [!DNL REST APIs] op een geautomatiseerde manier kunt u de [!DNL JWT] programmatisch. Zie [JWT-verificatie (serviceaccount)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) voor gedetailleerde instructies.

### Machtigingen voor RBAC&#39;s van technische rekeningen

Als uw Audience Manager-account [Op rollen gebaseerd Toegangsbeheer](../../features/administration/administration-overview.md), moet u een technische gebruikersrekening van de Audience Manager tot stand brengen en het toevoegen aan de Audience Manager RBAC groep die de API vraag zal maken.

Voer de onderstaande stappen uit om een technische gebruikersaccount te maken en deze toe te voegen aan een RBAC-groep:

1. Maak een `GET` oproep aan `https://aam.adobe.io/v1/users/self`. De vraag zal tot een technische gebruikersrekening leiden die u in kunt zien [!UICONTROL Admin Console]in de [!UICONTROL Users] pagina.

   ![technische rekening](assets/technical-account.png)

1. Meld u aan bij uw Audience Manager-account en [toevoegen aan de technische gebruikersaccount](../../features/administration/administration-overview.md#create-group) aan de gebruikersgroep die de API vraag zal maken.

+++

## [!BADGE Vervangen]{type=negative}[!DNL OAuth] Verificatie (afgekeurd) {#oauth-deprecated}

+++ Informatie weergeven over de verouderde nalatenschap [!DNL OAuth] Verificatiemethode voor het verkrijgen van verificatietokens.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] tokenauthentificatie en vernieuwing via [!DNL OAuth 2.0] is nu afgekeurd.
>
> Gebruik [JWT-verificatie (serviceaccount)](#jwt-service-account-authentication-jwt) in plaats daarvan.

De [!DNL Audience Manager] [!UICONTROL REST API] volgt [!DNL OAuth 2.0] normen voor tokenauthentificatie en vernieuwing. In de onderstaande secties wordt beschreven hoe u de verificatie uitvoert en met de functie [!DNL API]s.

### Een generiek bestand maken [!DNL API] Gebruiker {#requirements}

We raden u aan een aparte, technische gebruikersaccount te maken voor het werken met de [!DNL Audience Manager] [!DNL API]s. Dit is een generieke account die niet is gekoppeld aan of gekoppeld aan een specifieke gebruiker in uw organisatie. Dit type van [!DNL API] Met gebruikersaccount kunt u twee dingen doen:

* Identificeer welke dienst roept [!DNL API] (Bijvoorbeeld, vraag van uw apps die onze gebruiken [!DNL API]s of van andere gereedschappen die [!DNL API] verzoeken).
* Ononderbroken toegang tot de [!DNL API]s. Een account die aan een bepaalde persoon is gekoppeld, kan worden verwijderd wanneer deze uw bedrijf verlaat. Zo voorkomt u dat u met de beschikbare [!DNL API] code. Met een algemene account die niet aan een bepaalde werknemer is gekoppeld, voorkomt u dit probleem.

Als voorbeeld of gebruiksgeval voor dit type van rekening, laten wij zeggen u veel segmenten in één keer met wilt veranderen [Bulkbeheertools](../../reference/bulk-management-tools/bulk-management-intro.md). Wel, om dit te doen, heeft uw gebruikersrekening nodig [!DNL API] toegang. In plaats van machtigingen toe te voegen aan een specifieke gebruiker, maakt u een niet-specifieke gebruiker. [!DNL API] gebruikersaccount met de juiste gegevens, sleutel en geheim om [!DNL API] oproepen. Dit is ook handig als u uw eigen toepassingen ontwikkelt die gebruikmaken van de [!DNL Audience Manager] [!DNL API]s.

Werk met uw [!DNL Audience Manager] consultant voor het opzetten van een generiek [!DNL API]-only user account.

### Workflow voor wachtwoordverificatie {#password-authentication-workflow}

Wachtwoordverificatie veilige toegang tot onze [!DNL REST API]. De onderstaande stappen geven een overzicht van de workflow voor wachtwoordverificatie via een [!DNL JSON] in uw browser.

>[!TIP]
>
>Codeer toegang en vernieuw tokens als u hen in een gegevensbestand opslaat.

#### Stap 1: Verzoek [!DNL API] Toegang

Contacteer uw manager van de Oplossingen van de Partner. Zij zullen u van een [!DNL API] client-id en geheim. De id en het geheim verifiëren u aan [!DNL API].

Opmerking: als u een vernieuwingstoken wilt ontvangen, geeft u dat op wanneer u een aanvraag indient [!DNL API] toegang.

#### Stap 2: De token aanvragen

Geef een symbolische aanvraag door aan uw voorkeur [!DNL JSON] client. Wanneer u het verzoek bouwt:

* Een `POST` methode om aan te roepen `https://api.demdex.com/oauth/token`.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. Bijvoorbeeld de referenties `testId : testSecret` omzetten in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Geef in [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded` . De koptekst kan er bijvoorbeeld als volgt uitzien: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Stel de aanvraaginstantie als volgt in:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Stap 3: Ontvang het token

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

* Een `POST` methode om aan te roepen `https://api.demdex.com/oauth/token`.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. Bijvoorbeeld de referenties `testId : testSecret` omzetten in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Geef in de HTTP-headers door `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded`. De koptekst kan er bijvoorbeeld als volgt uitzien: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Vermeld in de aanvraaginstantie de `grant_type:refresh_token` en ga binnen vernieuwen teken u in uw vorig toegangsverzoek ontving. Het verzoek moet er als volgt uitzien: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Stap 2: Ontvang het Nieuwe Token

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

+++

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
| `search` | Retourneert resultaten op basis van de opgegeven tekenreeks die u als zoekparameter wilt gebruiken. Bijvoorbeeld, laten wij zeggen u resultaten voor alle modellen wilt vinden die het woord &quot;Test&quot;in om het even welke waardegebieden voor dat punt hebben. Uw voorbeeldverzoek kan er als volgt uitzien:   `GET https://aam.adobe.io/v1/models/?search=Test`.  U kunt zoeken op elke waarde die wordt geretourneerd door &quot;[!DNL get all]&quot;. |
| `folderId` | Retourneert alle id&#39;s voor [!UICONTROL traits] in de opgegeven map. Niet beschikbaar voor alle methoden. |
| `permissions` | Retourneert een lijst met segmenten op basis van de opgegeven machtiging. `READ` is standaard. Bevoegdheden omvatten:<ul><li>`READ` : De terugkeer en meningsinformatie over een segment.</li><li>`WRITE` : Gebruik  `PUT`  een segment bijwerken.</li><li>`CREATE` : Gebruik  `POST`  om een segment te maken.</li><li>`DELETE` : Een segment verwijderen. Vereist toegang tot eventuele onderliggende kenmerken. Bijvoorbeeld, zult u rechten nodig hebben om de eigenschappen te schrappen die tot een segment behoren als u het wilt verwijderen.</li></ul><br>Geef meerdere machtigingen op met afzonderlijke sleutelwaardeparen. Als u bijvoorbeeld een lijst met segmenten wilt retourneren met  `READ`  en  `WRITE`  alleen machtigingen, doorgeven  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Instellen op `true` om uw toestemmingen voor het segment terug te keren. Standaard is `false`. |

{style="table-layout:auto"}

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

### Verzoek [!DNL URLs] voor de [!BADGE Aanbevolen]{type=positive}[!BADGE Vervangen]{type=negative}[!DNL JWT] Verificatie via Adobe Developer {#request-urls-jwt}

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

{style="table-layout:auto"}

### Verzoek [!DNL URLs] voor de [!BADGE Vervangen]{type=negative}[!DNL OAuth] Verificatie {#request-urls-oauth}

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

{style="table-layout:auto"}

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

Nieuwe versies van deze [!DNL API]s worden vrijgegeven volgens een regelmatig schema. Een nieuwe release verhoogt de [!DNL API] versienummer. Naar het versienummer wordt verwezen in de aanvraag [!DNL URL] als `v<version number>` zoals in het volgende voorbeeld wordt getoond:

`https://<host>/v1/...`

## Responscodes gedefinieerd {#response-codes-defined}

`HTTP` statuscodes en reactietekst die door de [!DNL Audience Manager] [!UICONTROL REST API].

| Antwoordcode-id | Antwoordtekst | Definitie |
|---|---|---|
| `200` | `OK` | De aanvraag is verwerkt. Hiermee worden de verwachte inhoud of gegevens geretourneerd, indien vereist. |
| `201` | `Created` | De bron is gemaakt. Retourneert voor `PUT` en `POST` verzoeken. |
| `204` | `No Content` | De bron is verwijderd. De responsinstantie is leeg. |
| `400` | `Bad Request` | De server begrijpt het verzoek niet. Gewoonlijk vanwege een onjuiste syntaxis. Controleer uw verzoek en probeer het opnieuw. |
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
