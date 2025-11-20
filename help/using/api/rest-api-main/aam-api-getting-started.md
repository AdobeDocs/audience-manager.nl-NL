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
source-wordcount: '2563'
ht-degree: 0%

---

# Aan de slag met [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informatie over algemene vereisten, authentificatie, facultatieve vraagparameters, verzoek [!DNL URLs], en andere verwijzingen.

## API-vereisten en aanbevelingen {#api-requirements-recommendations}

Neem nota van het volgende wanneer het werken met [&#x200B; Audience Manager API &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **de parameters van het Verzoek:** alle verzoekparameters worden vereist tenzij anders gespecificeerd.
* **de kopballen van het Verzoek**: wanneer het gebruiken van [&#x200B; Adobe Developer &#x200B;](https://www.adobe.io/) tokens, moet u de `x-api-key` kopbal verstrekken. U kunt uw [!DNL API] sleutel krijgen door de instructies in de [&#x200B; pagina van de Integratie van de Rekening van de Dienst te volgen &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]inhoudstype:** specificeer `content-type: application/json` *en* `accept: application/json` in uw code.
* **Verzoeken en reacties:** verzend verzoeken als behoorlijk geformatteerd [!DNL JSON] voorwerp. [!DNL Audience Manager] reageert met [!DNL JSON] opgemaakte gegevens. Serverreacties kunnen gevraagde gegevens, een statuscode of beide bevatten.
* **Toegang:** Uw [!DNL Audience Manager] consultant zal u van een cliëntidentiteitskaart en een sleutel voorzien die u [!DNL API] verzoeken laat maken.
* **Documentatie en codesteekproeven:** Tekst in *cursief* vertegenwoordigt een variabele die u verstrekt of binnen overgaat wanneer het maken van of het ontvangen van [!DNL API] gegevens. Vervang *cursief* tekst met uw eigen code, parameters, of andere vereiste informatie.

## Verificatie {#authentication}

De [!DNL Audience Manager] [!DNL REST APIs] ondersteunt drie verificatiemethoden.

* [!BADGE &#x200B; geadviseerde &#x200B;]{type=positive} [&#x200B; OAuth Server-aan-Server Authentificatie &#x200B;](#oauth-adobe-developer) gebruikend [&#x200B; de ontwikkelaarsconsole van Adobe &#x200B;](https://www.adobe.io/). [!DNL Adobe Developer] is het Adobe-ontwikkelaarsecosysteem en -gemeenschap. Het omvat [&#x200B; APIs voor alle producten van Adobe &#x200B;](https://developer.adobe.com/apis/). Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs] in te stellen en te gebruiken. Lees meer over [&#x200B; Server-aan-Server Authentificatie &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) OAuth in de de ontwikkelaarsdocumentatie van Adobe.
* [!BADGE &#x200B; Vervangen &#x200B;]{type=negative} [&#x200B; JWT (de Rekening van de Dienst) Authentificatie &#x200B;](#jwt) gebruikend [&#x200B; de ontwikkelaarsconsole van Adobe &#x200B;](https://www.adobe.io/). [!DNL Adobe Developer] is het Adobe-ontwikkelaarsecosysteem en -gemeenschap. Het omvat [&#x200B; APIs voor alle producten van Adobe &#x200B;](https://developer.adobe.com/apis/).
* [!BADGE &#x200B; Vervangen &#x200B;]{type=negative} [&#x200B; Verouderde OAuth Authentificatie &#x200B;](#oauth-deprecated). Hoewel deze methode is afgekeurd, kunnen klanten met bestaande [!DNL OAuth] -integratie deze methode blijven gebruiken.

>[!IMPORTANT]
>
>Afhankelijk van uw verificatiemethode moet u uw verzoek [!DNL URLs] dienovereenkomstig aanpassen. Zie de [&#x200B; sectie van Milieu&#39;s &#x200B;](#environments) voor details over hostnames die u zou moeten gebruiken.

## OAuth Server-to-Server Authentificatie gebruikend Adobe Developer {#oauth-adobe-developer}

In deze sectie wordt beschreven hoe u de vereiste referenties kunt verzamelen voor het verifiëren van Audience Manager API-aanroepen, zoals hieronder in het stroomschema wordt beschreven. U kunt de meeste vereiste geloofsbrieven in eerste éénmalige opstelling verzamelen. Het toegangstoken, echter, moet om de 24 uur worden verfrist.

![&#x200B; diagram van de de authentificatiestroom van Audience Manager.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Adobe Developer - Overzicht {#developer-overview}

[!DNL Adobe Developer] is het Adobe-ontwikkelaarsecosysteem en -gemeenschap. Het omvat [&#x200B; APIs voor alle producten van Adobe &#x200B;](https://developer.adobe.com/apis).

Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs] in te stellen en te gebruiken.

### Vereisten {#prerequisites-server-to-server}

Alvorens u [!DNL OAuth Server-to-Server] authentificatie kunt vormen, zorg ervoor u toegang tot [&#x200B; Adobe Developer Console &#x200B;](https://developer.adobe.com/console/home) in [&#x200B; Adobe Developer &#x200B;](https://developer.adobe.com/) hebt. Neem contact op met uw organisatiebeheerder voor verzoeken om toegang.

### Verificatie {#oauth}

Voer de onderstaande stappen uit om [!DNL OAuth Server-to-Server] verificatie te configureren met [!DNL Adobe Developer] :

1. Login aan [&#x200B; Adobe Developer Console &#x200B;](https://developer.adobe.com/console/home).
1. Volg de stappen in de [&#x200B; Server-aan-Server referentie van OAuth implementatiegids &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Tijdens [&#x200B; Stap 2: voeg API aan uw project toe gebruikend de authentificatie van de Rekening van de Dienst &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), kies de [!DNL Audience Manager] [!DNL API] optie.
1. Probeer uit de verbinding door uw eerste [!DNL API] vraag te maken die op de instructies van [&#x200B; wordt gebaseerd Stap 3 &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Als u de [!DNL Audience Manager] [!DNL REST APIs] automatisch wilt configureren en gebruiken, kunt u de clientgeheimen programmatisch roteren. Zie [&#x200B; de ontwikkelaardocumentatie &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) voor gedetailleerde instructies.

### Audience Manager API toevoegen aan een project {#add-aam-api-to-project}

Ga naar [&#x200B; Adobe Developer Console &#x200B;](https://www.adobe.com/go/devs_console_ui) en teken binnen met uw Adobe ID. Daarna, volg de stappen die in het leerprogramma worden geschetst op [&#x200B; creërend een leeg project &#x200B;](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) in de documentatie van Adobe Developer Console.

Wanneer u een nieuw project hebt gemaakt, selecteert u **[!UICONTROL Add API]** op het **[!UICONTROL Project Overview]** -scherm.

>[!TIP]
>
>Als u provisioned voor verscheidene organisaties bent, gebruik de organisatieselecteur in de hogere juiste hoek van de interface om ervoor te zorgen dat u in de organisatie bent u nodig hebt.

![&#x200B; het scherm van Developer Console met Add wordt benadrukt API optie.](/help/using/api/rest-api-main/assets/add-api.png)

Het scherm **[!UICONTROL Add an API]** wordt weergegeven. Selecteer het productpictogram voor Adobe Experience Cloud en kies vervolgens **[!UICONTROL Audience Manager API]** voordat u **[!UICONTROL Next]** selecteert.

![&#x200B; Uitgezochte Audience Manager API.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Selecteer de **[!UICONTROL View docs]** optie om in een afzonderlijk browser venster aan de volledige [&#x200B; Audience Manager API verwijzingsdocumentatie &#x200B;](https://bank.demdex.com/portal/swagger/index.html#) te navigeren.

### Selecteer het verificatietype OAuth Server-to-Server {#select-oauth-server-to-server}

Selecteer vervolgens het verificatietype dat u wilt genereren voor toegangstokens en toegang tot de Audience Manager API.

>[!IMPORTANT]
>
>Selecteer de methode **[!UICONTROL OAuth Server-to-Server]** omdat dit de enige methode is die vooruit wordt ondersteund. De methode **[!UICONTROL Service Account (JWT)]** is vervangen. Terwijl de integratie die de authentificatiemethode JWT gebruikt tot 1 Januari, 2025 zal blijven werken, adviseert Adobe sterk dat u bestaande integratie aan de nieuwe server-aan-server methode OAuth vóór die datum migreert.

![&#x200B; Uitgezochte OAuth authentificatiemethode.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Selecteer de productprofielen voor uw integratie {#select-product-profiles}

Selecteer in het scherm **[!UICONTROL Configure API]** de gewenste productprofielen. Via de hier geselecteerde productprofielen krijgt het serviceaccount van uw integratie toegang tot korrelfuncties.

![&#x200B; Uitgezochte productprofielen voor uw integratie.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Selecteer **[!UICONTROL Save configured API]** wanneer u klaar bent.

### Referenties verzamelen {#gather-credentials}

Zodra API aan het project is toegevoegd, **[!UICONTROL Audience Manager API]** toont de pagina voor het project de volgende geloofsbrieven die in alle vraag aan Audience Manager APIs worden vereist:

![&#x200B; de informatie van de Integratie na het toevoegen van API in Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Een toegangstoken genereren {#generate-access-token}

De volgende stap bestaat uit het genereren van een `{ACCESS_TOKEN}` -referentie voor gebruik in Audience Manager API-aanroepen. In tegenstelling tot de waarden voor `{API_KEY}` en `{ORG_ID}` , moet om de 24 uur een nieuw token worden gegenereerd om Audience Manager API&#39;s te kunnen blijven gebruiken. Selecteer **[!UICONTROL Generate access token]**, zoals hieronder wordt weergegeven.

![&#x200B; toon hoe te om toegangstoken &#x200B;](/help/using/api/rest-api-main/assets/generate-acces-token.gif) te produceren

## Een API-aanroep testen {#test-api-call}

Nadat u uw token voor de verificatiehouder hebt opgehaald, voert u een API-aanroep uit om te testen of u nu toegang hebt tot Audience Manager API&#39;s.

1. Navigeer aan de [&#x200B; API verwijzingsdocumentatie &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Selecteer **[!UICONTROL Authorize]** en kleef het toegangstoken dat u in [&#x200B; hebt verkregen het toegangstoken &#x200B;](#generate-access-token) stap produceert.

   ![&#x200B; autoriseer API vraag &#x200B;](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Voer een vraag van GET aan het `/datasources` API eindpunt uit om een lijst van alle globaal beschikbare gegevensbronnen terug te winnen, zoals vermeld in de [&#x200B; API verwijzingsdocumentatie &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Selecteer **[!UICONTROL Try it out]** , gevolgd door **[!UICONTROL Execute]** , zoals hieronder wordt weergegeven.

   ![&#x200B; voer API vraag uit &#x200B;](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB  API verzoek ]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB  API reactie in het geval van het gebruiken van het correcte dragerteken ]


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

## [!BADGE &#x200B; Vervangen &#x200B;]{type=negative} [!DNL JWT] ([!DNL Service Account]) Authentificatie die Adobe Developer gebruikt {#jwt}

+++ Informatie weergeven over de afgekeurde methode [!DNL JWT] ([!DNL Service Account] ) voor het verkrijgen van verificatietokens.

### Adobe Developer - Overzicht {#adobeio}

[!DNL Adobe Developer] is het Adobe-ontwikkelaarsecosysteem en -gemeenschap. Het omvat [&#x200B; APIs voor alle producten van Adobe &#x200B;](https://www.adobe.io/apis.html).

Dit is de aanbevolen manier om [!DNL Adobe] [!DNL APIs] in te stellen en te gebruiken.

### Vereisten {#prerequisites}

Alvorens u [!DNL JWT] authentificatie kunt vormen, zorg ervoor u toegang tot [&#x200B; Adobe Developer Console &#x200B;](https://console.adobe.io/) in [&#x200B; Adobe Developer &#x200B;](https://www.adobe.io/) hebt. Neem contact op met uw organisatiebeheerder voor verzoeken om toegang.

### Verificatie {#auth}

Voer de onderstaande stappen uit om [!DNL JWT (Service Account)] verificatie te configureren met [!DNL Adobe Developer] :

1. Login aan [&#x200B; Adobe Developer Console &#x200B;](https://console.adobe.io/).
1. Volg de stappen in [&#x200B; Verbinding van de Rekening van de Dienst &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Tijdens [&#x200B; Stap 2: voeg API aan uw project toe gebruikend de authentificatie van de Rekening van de Dienst &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), kies de [!DNL Audience Manager] [!DNL API] optie.
1. Probeer uit de verbinding door uw eerste [!DNL API] vraag te maken die op de instructies van [&#x200B; wordt gebaseerd Stap 3 &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Als u de [!DNL Audience Manager] [!DNL REST APIs] automatisch wilt configureren en bewerken, kunt u de [!DNL JWT] programmatisch genereren. Zie [&#x200B; JWT (de Rekening van de Dienst) Authentificatie &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) voor gedetailleerde instructies.

### Machtigingen voor RBAC&#39;s van technische rekeningen

Als uw Audience Manager rekening [&#x200B; Op rol-Gebaseerd Toegangsbeheer &#x200B;](../../features/administration/administration-overview.md) gebruikt, moet u een Audience Manager technische gebruikersrekening tot stand brengen en het toevoegen aan de groep van Audience Manager RBAC die de API vraag zal maken.

Voer de onderstaande stappen uit om een technische gebruikersaccount te maken en deze toe te voegen aan een RBAC-groep:

1. Roep `GET` aan `https://aam.adobe.io/v1/users/self` . Met de aanroep wordt een technische gebruikersaccount gemaakt die u kunt zien op de pagina [!UICONTROL Admin Console] in [!UICONTROL Users] .

   ![&#x200B; technische rekening &#x200B;](assets/technical-account.png)

1. Login aan uw rekening van Audience Manager en [&#x200B; voeg de technische gebruikersrekening &#x200B;](../../features/administration/administration-overview.md#create-group) aan de gebruikersgroep toe die de API vraag zal maken.

+++

## [!BADGE &#x200B; Vervangen &#x200B;]{type=negative} [!DNL OAuth] Authentificatie (Vervangen) {#oauth-deprecated}

+++ Informatie weergeven over de vervangen verificatiemethode van [!DNL OAuth] voor het verkrijgen van verificatietokens.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] tokenverificatie en -vernieuwing via [!DNL OAuth 2.0] is nu afgekeurd.
>
> Gelieve te gebruiken [&#x200B; JWT (de Rekening van de Dienst) Authentificatie &#x200B;](#jwt-service-account-authentication-jwt) in plaats daarvan.

De [!DNL Audience Manager] [!UICONTROL REST API] volgt [!DNL OAuth 2.0] -standaarden voor tokenverificatie en -vernieuwing. De secties beschrijven hieronder om voor authentiek te verklaren en beginnen werkend met [!DNL API] s.

### Een algemene [!DNL API] gebruiker maken {#requirements}

Wij adviseren u een afzonderlijke, technische gebruikersrekening voor het werken met [!DNL Audience Manager] tot stand brengen [!DNL API] s. Dit is een generieke account die niet is gekoppeld aan of gekoppeld aan een specifieke gebruiker in uw organisatie. Met dit type [!DNL API] -gebruikersaccount kunt u twee dingen doen:

* Identificeer welke dienst [!DNL API] roept (b.v., vraag van uw apps die onze [!DNL API] s of van andere hulpmiddelen gebruiken die [!DNL API] verzoeken indienen).
* Verstrek ononderbroken toegang tot [!DNL API] s. Een account die aan een bepaalde persoon is gekoppeld, kan worden verwijderd wanneer deze uw bedrijf verlaat. Zo voorkomt u dat u met de beschikbare [!DNL API] -code werkt. Met een algemene account die niet aan een bepaalde werknemer is gekoppeld, voorkomt u dit probleem.

Als voorbeeld of gebruiksgeval voor dit type van rekening, zeg u een hoop segmenten meteen met de [&#x200B; Hulpmiddelen van het Beheer van het Bulk &#x200B;](../../reference/bulk-management-tools/bulk-management-intro.md) wilt veranderen. Uw gebruikersaccount heeft hiervoor [!DNL API] toegang nodig. In plaats van machtigingen toe te voegen aan een specifieke gebruiker, maakt u een niet-specifieke [!DNL API] gebruikersaccount met de juiste referenties, sleutel en geheim om [!DNL API] -aanroepen uit te voeren. Dit is ook nuttig als u uw eigen toepassingen ontwikkelt die [!DNL Audience Manager] gebruiken [!DNL API] s.

Werk samen met uw [!DNL Audience Manager] -consultant om een algemene [!DNL API] -gebruikersaccount in te stellen.

### Workflow voor wachtwoordverificatie {#password-authentication-workflow}

Wachtwoordverificatie is beveiligd met toegang tot onze [!DNL REST API] . In de onderstaande stappen wordt een overzicht gegeven van de workflow voor wachtwoordverificatie van een [!DNL JSON] -client in uw browser.

>[!TIP]
>
>Codeer toegang en vernieuw tokens als u hen in een gegevensbestand opslaat.

#### Stap 1: Toegang aanvragen [!DNL API]

Contacteer uw manager van de Oplossingen van de Partner. Ze geven u een [!DNL API] client-id en een geheim. De id en het geheim verifiëren u aan [!DNL API].

Opmerking: als u een token voor vernieuwen wilt ontvangen, geeft u dat op wanneer u [!DNL API] toegang aanvraagt.

#### Stap 2: De token aanvragen

Geef een symbolische aanvraag door met de voorkeursclient [!DNL JSON] . Wanneer u het verzoek bouwt:

* Gebruik een methode `POST` om `https://api.demdex.com/oauth/token` aan te roepen.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. De gegevens `testId : testSecret` worden bijvoorbeeld omgezet in `dGVzdElkOnRlc3RTZWNyZXQ=` .
* Geef de [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded` door. De koptekst kan er bijvoorbeeld als volgt uitzien: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Stel de aanvraaginstantie als volgt in:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Stap 3: Ontvang het token

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

De sleutel `expires_in` vertegenwoordigt het aantal seconden tot het toegangstoken verloopt. U kunt het beste korte vervaltijden gebruiken om de belichting te beperken als het token ooit wordt blootgesteld.

### Token vernieuwen {#refresh-token}

Tokens vernieuwen vernieuwt [!DNL API] de toegang nadat het oorspronkelijke token is verlopen. Indien gevraagd, bevat de reactie [!DNL JSON] in de wachtwoordworkflow een token voor vernieuwen. Als u ontvangt vernieuw symbolisch, creeer nieuwe door het proces van de wachtwoordauthentificatie.

U kunt ook een vernieuwingstoken gebruiken om een nieuw token te genereren voordat het bestaande toegangstoken verloopt.

Als uw toegangstoken is verlopen, ontvangt u een `401 Status Code` en de volgende kopbal in de reactie:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

In de volgende stappen wordt een overzicht gegeven van de workflow voor het gebruik van een vernieuwingstoken om een nieuw toegangstoken te maken van een [!DNL JSON] -client in uw browser.

#### Stap 1: Nieuwe token aanvragen

Geef een vernieuwingstoken-aanvraag door aan uw voorkeursclient [!DNL JSON] . Wanneer u het verzoek bouwt:

* Gebruik een methode `POST` om `https://api.demdex.com/oauth/token` aan te roepen.
* Zet uw cliënt ID en geheim in een basis-64 gecodeerde koord om. Scheid de id en het geheim tijdens het conversieproces met een dubbele punt. De gegevens `testId : testSecret` worden bijvoorbeeld omgezet in `dGVzdElkOnRlc3RTZWNyZXQ=` .
* Geef de HTTP-headers `Authorization:Basic <base-64 clientID:clientSecret>` en `Content-Type: application/x-www-form-urlencoded` door. De koptekst kan er bijvoorbeeld als volgt uitzien: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* In het aanvraaglichaam, specificeer `grant_type:refresh_token` en ga in vernieuwt token over u in uw vorige toegangsverzoek ontving. De aanvraag moet er als volgt uitzien: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Stap 2: Ontvang het Nieuwe Token

De reactie [!DNL JSON] bevat uw nieuwe toegangstoken. De reactie moet er als volgt uitzien:

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

[!DNL Audience Manager] [!UICONTROL REST API] ondersteunt machtigingscode en impliciete verificatie. Als u deze toegangsmethoden wilt gebruiken, moeten uw gebruikers zich aanmelden bij `https://api.demdex.com/oauth/authorize` om toegang te krijgen tot tokens en deze te vernieuwen.

+++

## [!DNL API] Verzoeken voor authentiek maken {#authenticated-api-requests}

Vereisten voor het aanroepen van [!DNL API] -methoden nadat u een verificatietoken hebt ontvangen.

U kunt als volgt oproepen met de beschikbare [!DNL API] -methoden:

* Stel in de header `HTTP` `Authorization: Bearer <token>` in.
* Wanneer het gebruiken van [&#x200B; JWT (de Rekening van de Dienst) Authentificatie &#x200B;](#jwt), moet u de `x-api-key` kopbal verstrekken, die het zelfde als uw `client_id` zal zijn. U kunt uw `client_id` van de [&#x200B; integratie van Adobe Developer &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) pagina krijgen.
* Roep de vereiste [!DNL API] -methode aan.

## Optionele [!DNL API] queryparameters {#optional-api-query-parameters}

Stel de optionele parameters in die beschikbaar zijn voor methoden die alle eigenschappen voor een object retourneren.

U kunt deze facultatieve parameters met [!DNL API] methodes gebruiken die *alle* eigenschappen voor een voorwerp terugkeren. Stel deze opties in de aanvraagtekenreeks in wanneer u die query aan de [!DNL API] doorgeeft.

| Parameter | Beschrijving |
|--- |--- |
| `page` | Geeft resultaten op paginanummer. De nummering begint bij 0. |
| `pageSize` | Stelt het aantal reactieresultaten in dat door de aanvraag wordt geretourneerd (10 is standaard). |
| `sortBy` | Sorteert en retourneert resultaten volgens de opgegeven eigenschap [!DNL JSON] . |
| `descending` | Sorteert en retourneert resultaten in aflopende volgorde. `ascending` is standaard. |
| `search` | Retourneert resultaten op basis van de opgegeven tekenreeks die u als zoekparameter wilt gebruiken. Bijvoorbeeld, laten wij zeggen u resultaten voor alle modellen wilt vinden die het woord &quot;Test&quot;in om het even welke waardegebieden voor dat punt hebben. Uw voorbeeldverzoek kan er als volgt uitzien:   `GET https://aam.adobe.io/v1/models/?search=Test`.  U kunt op om het even welke waarde zoeken die door een &quot;[!DNL get all]&quot;methode is teruggekeerd. |
| `folderId` | Retourneert alle id&#39;s voor [!UICONTROL traits] in de opgegeven map. Niet beschikbaar voor alle methoden. |
| `permissions` | Retourneert een lijst met segmenten op basis van de opgegeven machtiging. `READ` is standaard. Bevoegdheden omvatten:<ul><li>`READ` : retourneer en bekijk informatie over een segment.</li><li>`WRITE` : gebruik `PUT` om een segment bij te werken.</li><li>`CREATE` : gebruik `POST` om een segment te maken.</li><li>`DELETE` : Verwijder een segment. Vereist toegang tot eventuele onderliggende kenmerken. Bijvoorbeeld, zult u rechten nodig hebben om de eigenschappen te schrappen die tot een segment behoren als u het wilt verwijderen.</li></ul><br> specificeer veelvoudige toestemmingen met afzonderlijke zeer belangrijk-waardeparen. Als u bijvoorbeeld een lijst met segmenten wilt retourneren die alleen `READ` en `WRITE` machtigingen hebben, geeft u `"permissions":"READ"` en `"permissions":"WRITE"` door. |
| `includePermissions` | ([!DNL Boolean]) Reeks aan `true` om uw toestemmingen voor het segment terug te keren. De standaardwaarde is `false` . |

{style="table-layout:auto"}

### Een opmerking over paginaopties

Wanneer de paginainformatie *niet* wordt gespecificeerd, keert het verzoek gewone [!DNL JSON] resultaten in een serie terug. Als de paginainformatie ** wordt gespecificeerd, dan wordt de teruggekeerde lijst verpakt in een [!DNL JSON] voorwerp dat informatie over het totale resultaat en de huidige pagina bevat. Uw voorbeeldverzoek met behulp van paginaopties kan er als volgt uitzien:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] voor aanvragen, testomgevingen en productieomgevingen en versies.

## Verzoek [!DNL URLs] {#request-urls}

In de volgende tabel wordt de aanvraag [!DNL URLs] weergegeven die wordt gebruikt om [!DNL API] -aanvragen via methode door te geven.

Afhankelijk van de verificatiemethode die u gebruikt, moet u uw verzoek [!DNL URLs] aanpassen aan de hand van de onderstaande tabellen.

### Verzoek [!DNL URLs] voor [!BADGE &#x200B; Geadviseerde &#x200B;]{type=positive} Server-aan-Server en [!BADGE &#x200B; Vervangen &#x200B;]{type=negative} [!DNL JWT] Authentificatie door Adobe Developer {#request-urls-jwt}

| [!DNL API] Methoden | Verzoek [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Traits: `https://aam.adobe.io/v1/folders/traits /`<br> Segmenten: `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

{style="table-layout:auto"}

### Verzoek [!DNL URLs] voor [!BADGE &#x200B; Afgekeurde &#x200B;]{type=negative} erfenis [!DNL OAuth] Authentificatie {#request-urls-oauth}

| [!DNL API] Methoden | Verzoek [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Traits: `https://api.demdex.com/v1/folders/traits /`<br> Segmenten: `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

{style="table-layout:auto"}

## Omgevingen {#environments}

De [!DNL Audience Manager] [!DNL API] verleent toegang tot verschillende het werk milieu&#39;s. Deze milieu&#39;s helpen u code tegen afzonderlijke gegevensbestanden testen zonder levende, productiegegevens te beïnvloeden. De volgende tabel bevat een lijst met de beschikbare [!DNL API] -omgevingen en de bijbehorende hostnamen van bronnen.

Afhankelijk van de verificatiemethode die u gebruikt, moet u de omgeving [!DNL URLs] aanpassen aan de hand van de onderstaande tabel.

| Omgeving | Hostnaam voor [!DNL JWT] verificatie | Hostnaam voor [!DNL OAuth] verificatie |
|---|---|---|
| **Productie** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>De bètaomgeving van [!DNL Audience Manager] is een zelfstandige, kleinere versie van de productieomgeving. Alle gegevens die u wilt testen, moeten in deze omgeving worden ingevoerd en verzameld.

## Versies {#versions}

De nieuwe versies van deze [!DNL API] s worden vrijgegeven op een regelmatig programma. Een nieuwe versie verhoogt het [!DNL API] versienummer. In de aanvraag [!DNL URL] wordt naar het versienummer verwezen als `v<version number>` , zoals in het volgende voorbeeld wordt getoond:

`https://<host>/v1/...`

## Responscodes gedefinieerd {#response-codes-defined}

`HTTP` -statuscodes en reactietekst die door de [!DNL Audience Manager] [!UICONTROL REST API] worden geretourneerd.

| Antwoordcode-id | Antwoordtekst | Definitie |
|---|---|---|
| `200` | `OK` | De aanvraag is verwerkt. Hiermee worden de verwachte inhoud of gegevens geretourneerd, indien vereist. |
| `201` | `Created` | De bron is gemaakt. Retourneert voor `PUT` - en `POST` -aanvragen. |
| `204` | `No Content` | De bron is verwijderd. De responsinstantie is leeg. |
| `400` | `Bad Request` | De server begrijpt het verzoek niet. Gewoonlijk vanwege een onjuiste syntaxis. Controleer uw verzoek en probeer het opnieuw. |
| `403` | `Forbidden` | U hebt geen toegang tot de bron. |
| `404` | `Not Found` | De bron kan niet worden gevonden voor het opgegeven pad. |
| `409` | `Conflict` | Het verzoek kon niet worden voltooid wegens een conflict met de staat van de bron. |
| `500` | `Server Error` | De server heeft een onverwachte fout aangetroffen waardoor deze de aanvraag niet kan uitvoeren. |

>[!MORELIKETHIS]
>
>* [&#x200B; JWT (de Rekening van de Dienst) Authentificatie &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [&#x200B; OAuth Authentificatie &#x200B;](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [&#x200B; OAuth 2.0 &#x200B;](https://oauth.net/2/)
>* [&#x200B; OAuth 2 Vereenvoudigd &#x200B;](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
