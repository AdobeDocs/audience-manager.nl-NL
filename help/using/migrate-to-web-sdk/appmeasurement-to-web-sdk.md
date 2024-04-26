---
title: Werk uw bibliotheek van de gegevensinzameling voor Audience Manager van de bibliotheek van AppMeasurement JavaScript aan de bibliotheek van SDK JavaScript van het Web bij.
description: Begrijp de stappen om uw bibliotheek van de gegevensinzameling voor Audience Manager van de AppMeasurement JavaScript bibliotheek aan de bibliotheek van SDK JavaScript van het Web bij te werken.
source-git-commit: b0c35d79a07b481e332ddf8f4aedab5484416a51
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---


# Werk uw bibliotheek van de gegevensinzameling voor Audience Manager van de bibliotheek van AppMeasurement JavaScript aan de bibliotheek van SDK JavaScript van het Web bij

## Beoogd publiek {#intended-audience}

Deze pagina is bedoeld voor klanten van de Audience Manager die AppMeasurement gebruiken om de gegevens van de Webinzameling in Audience Manager te brengen. Voor klanten die [Audience Manager, tagextensie](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview), lees de handleiding over het bijwerken van de bibliotheek voor gegevensverzameling voor Audience Manager [van de de markeringsuitbreiding van de Audience Manager aan de de markeringsuitbreiding van SDK van het Web](dil-extension-to-web-sdk.md).

## Voordelen en nadelen van dit implementatiepad

Het gebruik van deze migratiebenadering heeft zowel voor- als nadelen. Let zorgvuldig op elke optie om te bepalen welke benadering het beste is voor uw organisatie.

| Voordelen | Nadelen |
| --- | --- |
| <ul><li>**Gebruikt uw bestaande implementatie**: Hoewel deze aanpak enige wijzigingen in de implementatie vereist, is er geen volledig nieuwe implementatie nodig. U kunt uw bestaande gegevenslaag en code met minimale veranderingen in implementatielogica gebruiken.</li><li>**Geen schema vereist**: Voor dit stadium van het migreren aan het Web SDK, hebt u geen schema XDM nodig. In plaats daarvan kunt u de `data` -object, dat gegevens rechtstreeks naar de Audience Manager verzendt. Zodra de migratie naar SDK van het Web volledig is, dan kunt u een schema voor uw organisatie tot stand brengen en gegevensstroomafbeelding gebruiken om toepasselijke gebieden te bevolken XDM. Als een schema in dit stadium van het migratieproces werd vereist, zou uw organisatie worden gedwongen om een Audience Manager XDM schema te gebruiken. Het gebruik van dit schema maakt het voor uw organisatie moeilijker om uw eigen schema in de toekomst te gebruiken.</li></ul> | <ul><li>**Technische schuld implementeren**: Aangezien deze benadering een gewijzigde vorm van uw bestaande implementatie gebruikt, kan het moeilijker zijn om implementatielogica te volgen en veranderingen in de toekomst uit te voeren wanneer nodig.</li><li>**Vereist toewijzing om gegevens naar Platform te verzenden**: Als uw organisatie klaar is om Real-Time CDP te gebruiken, moet u gegevens naar een gegevensset in Adobe Experience Platform verzenden. Deze handeling vereist dat elk veld in het dialoogvenster `data` -object is een item in het hulpprogramma voor gegevenstoewijzing dat het toewijst aan een XDM-schemaveld. Voor deze workflow hoeft u slechts één keer toewijzingen uit te voeren, en dit betekent niet dat u implementatiewijzigingen aanbrengt. Het is echter een extra stap die niet vereist is bij het verzenden van gegevens in een XDM-object.</li></ul> |

De Adobe beveelt aan dit implementatiepad in de volgende scenario&#39;s te volgen:

* U hebt een bestaande implementatie met de Adobe Analytics AppMeasurement JavaScript-bibliotheek. Als u een implementatie hebt met de tagextensie Audience Manager, volgt u [Migreren van de tagextensie Audience Manager naar de webSDK-tagextensie](dil-extension-to-web-sdk.md) in plaats daarvan.
* U bent van plan om Real-Time CDP in de toekomst te gebruiken, maar wilt niet uw implementatie van de Audience Manager met een implementatie van SDK van het Web van kras vervangen. Het vervangen van uw implementatie van kras op het Web SDK vereist de meeste inspanning, maar ook biedt de meest levensvatbare implementatiearchitectuur op lange termijn aan. Als uw organisatie bereid is door de inspanning van een schone implementatie van SDK van het Web te gaan, zie [Web SDK-documentatie](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) voor meer informatie .

## Stappen vereist om naar SDK van het Web te migreren

De volgende stappen bevatten concrete doelstellingen die moeten worden nagestreefd. Klik op elke stap voor gedetailleerde instructies over hoe u deze kunt uitvoeren.

+++**1. Een gegevensstroom maken en configureren**

Maak een gegevensstroom in de gegevensverzameling van Adobe Experience Platform. Wanneer u gegevens naar deze gegevensstroom verzendt, stuurt het gegevens door naar de Audience Manager. In de toekomst stuurt dezelfde gegevensstroom gegevens door naar Real-Time CDP.

1. Navigeren naar [experience.adobe.com](https://experience.adobe.com) en meld u aan met uw referenties.
1. Gebruik de homepage of productkiezer in de rechterbovenhoek om naar **[!UICONTROL Data Collection]**.
1. Selecteer in de linkernavigatie de optie **[!UICONTROL Datastreams]**.
1. Selecteren **[!UICONTROL New Datastream]**.
1. Voer de gewenste naam in en selecteer **[!UICONTROL Save]**.
1. Wanneer de gegevensstroom is gemaakt, selecteert u **[!UICONTROL Add Service]**.
1. Selecteer in het vervolgkeuzemenu Service de optie **[!UICONTROL Audience Manager]**.

   ![Audience Manager-service toevoegen](assets/add-service.png) {style="border:1px solid lightslategray"}

Uw gegevensstroom is nu klaar om gegevens te ontvangen en door te geven aan Audience Manager. Noteer de gegevensstroom-id, aangezien deze id vereist is voor het configureren van de Web SDK in code.

+++

+++**2. De Web SDK JavaScript-bibliotheek installeren**

Zie [De SDK van het Web installeren met de JavaScript-bibliotheek](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) voor details en codeblokken aan gebruik. Verwijs naar de recentste versie van `alloy.js` zo kan zijn methodevraag worden gebruikt.

+++

+++**3. De SDK van het web configureren**

Opstelling uw implementatie om aan de datastream te richten die in stap 1 wordt gecreeerd door het Web SDK te gebruiken [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) gebruiken. De `configure` moet op elke pagina worden ingesteld, zodat u deze naast de installatiecode van de bibliotheek kunt plaatsen.

Gebruik de [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) en [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) eigenschappen binnen de Web SDK `configure` opdracht:

* Stel de `edgeConfigId` naar de gegevensstroom-id die u hebt opgehaald uit de vorige stap.
* Stel de `orgId` naar de IMS org-id van uw organisatie.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

U kunt desgewenst andere eigenschappen instellen in het dialoogvenster [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) afhankelijk van de implementatievereisten van uw organisatie.

+++

+++**4. Codelogica bijwerken voor het gebruik van een JSON-payload**

Verander uw implementatie van de Audience Manager zodat het niet op baseert `AppMeasurement.js` of de `s` object. In plaats daarvan kunt u variabelen instellen in een JavaScript-object met de juiste indeling. Dit object wordt omgezet in een JSON-object wanneer het naar de Adobe wordt verzonden. Met een [gegevenslaag](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) op uw site helpt u enorm bij het instellen van waarden, aangezien u kunt blijven verwijzen naar dezelfde waarden.

Om gegevens naar Audience Manager te verzenden, moet de nuttige lading van SDK van het Web gebruiken `data.__adobe.audiencemanager` met alle analytische variabelen die binnen dit object zijn ingesteld. Variabelen in dit object hebben dezelfde namen en indelingen als de variabele tegenhangers van het AppMeasurement. Als u bijvoorbeeld de opdracht `products` variabele, niet in individuele voorwerpen verdelen zoals u met XDM zou doen. In plaats daarvan neemt u de eigenschap als tekenreeks op als u de instelling `s.products` variabele:

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

Uiteindelijk bevat deze lading alle gewenste waarden, en alle verwijzingen naar `s` -object in uw implementatie wordt verwijderd. U kunt alle bronnen die JavaScript biedt, gebruiken om dit payload-object in te stellen, inclusief puntnotatie voor het instellen van individuele waarden.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5. De methodevraag van de update om SDK van het Web te gebruiken**

Werk alle instanties bij waar u roept [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) en [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method), die worden vervangen door de [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) gebruiken. Er zijn drie scenario&#39;s om te overwegen:

* **Paginaweergave bijhouden**: Vervang de volgende vraag van de paginamening met het Web SDK `sendEvent` opdracht:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Automatisch koppelingen bijhouden**: De [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) configuratie-eigenschap is standaard ingeschakeld. De juiste variabelen voor het bijhouden van koppelingen worden automatisch ingesteld om gegevens naar de Audience Manager te verzenden. Als u automatische koppeling bijhouden wilt uitschakelen, stelt u deze eigenschap in op `false` binnen de [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) gebruiken.

* **Handmatige koppeling bijhouden**: De SDK van het Web heeft geen afzonderlijke bevelen tussen de vraag van de paginalevening en niet van de paginaleving. Geef dat onderscheid op in het object payload.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Wijzigingen valideren en publiceren**

Als u alle verwijzingen naar het AppMeasurement en de `s` -objecten, publiceert u uw wijzigingen in uw ontwikkelomgeving om te controleren of de nieuwe implementatie werkt. Nadat u hebt gecontroleerd dat alles correct werkt, kunt u uw updates publiceren voor productie.

Als de migratie correct is, `AppMeasurement.js` is niet meer vereist op uw site en alle verwijzingen naar dit script kunnen worden verwijderd.

+++

Op dit punt, wordt uw implementatie van de Audience Manager volledig gemigreerd aan het Web SDK en is bereid om zich aan Real-Time CDP in de toekomst te bewegen.
