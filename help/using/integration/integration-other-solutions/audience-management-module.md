---
description: Voeg de module Audience Management toe aan Adobe Analytics AppMeasurement om Analytics-gegevens door te sturen naar Audience Manager in plaats van dat de DIL-code (Audience Manager Data Integration Library) een pixel van de pagina verzendt.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Voeg de module Audience Management toe aan Adobe Analytics AppMeasurement om Analytics-gegevens door te sturen naar Audience Manager in plaats van dat de DIL-code (Audience Manager Data Integration Library) een pixel van de pagina verzendt.
seo-title: Implementeer de module Audience Management
solution: Audience Manager
title: Implementeer de module Audience Management
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 4%

---


# How to forward data from [!DNL Adobe Analytics] to [!DNL Audience Manager] {#implement-the-audience-management-module}

Voer de stappen in deze zelfstudie uit om [!DNL Analytics] gegevens door te sturen naar [!DNL Audience Manager] in plaats van de [!DNL Audience Manager] ( [!UICONTROL Data Integration Library][!DNL DIL]) code een pixel van de pagina te laten verzenden.

>[!TIP]
>
>We raden u aan gegevens door [!DNL Adobe Experience Platform Launch] te sturen [!UICONTROL Analytics] naar [!DNL Audience Manager]. Door te gebruiken, moet u code niet manueel kopiëren in [!UICONTROL Launch][!DNL AppMeasurement], zoals aangetoond op deze pagina.

## Vereisten {#prereqs}

Naast het inschakelen van de extensies of het implementeren van de code die in dit document wordt beschreven, moet u ook:

* Implement the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/nl-NL/id-service/using/home.html).
* Schakel [Server-Side Forwarding](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) in voor rapportsuites in de [!UICONTROL Adobe Analytics Admin Console].

## Implementatie {#implementation}

Er zijn twee methodes om gegevens uit te voeren door:sturen van [!DNL Adobe Analytics] aan [!DNL Audience Manager], afhankelijk van de oplossing van het markeringsbeheer die u gebruikt.

### Implementatie met [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] raadt u aan de extensie [Starten](https://docs.adobe.com/content/help/en/launch/using/overview.html) te gebruiken voor instrumenten [!DNL Adobe Analytics] en [!DNL Audience Manager] eigenschappen. In dit geval hoeft u geen code handmatig te kopiëren. In plaats daarvan moet u gegevensdeling inschakelen in de [!DNL Analytics Launch] extensie, zoals in de onderstaande afbeelding wordt getoond. Zie ook de [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) documentatie.

>[!TIP]
>
>Installeer de [!DNL Adobe Analytics] extensie *niet* [!DNL Audience Manager] als u deze installeert. Door gegevens van de [!DNL Analytics] extensie te verzenden, vervangt u de [!DNL Audience Manager] extensiefunctie.

![Gegevens delen inschakelen van de Adobe Analytics-extensie naar Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementatie met [!DNL Adobe Digital Tag Management (DTM)] of een andere oplossing voor tagbeheer

>[!WARNING]
>
>[!DNL Adobe] heeft plannen gepubliceerd om tegen eind 2020 te verzonnen [!DNL DTM] . Raadpleeg [!DNL DTM] Abonnementen voor een zonsondergang in de forums [van de](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)Adobe-community voor meer informatie en planning.

Implementeer de [!UICONTROL Audience Management Module] toepassing met [Adobe DTM](https://docs.adobe.com/content/help/nl-NL/dtm/using/dtm-home.html) of een andere oplossing voor tagbeheer:

1. Download [!UICONTROL AppMeasurement] met behulp van [Analytics Code Manager](https://docs.adobe.com/content/help/nl-NL/analytics/admin/admin-tools/code-manager-admin.html) (versie 1.5 of hoger vereist).
1. Werk uw [!UICONTROL AppMeasurement] code bij naar de versie die in het gedownloade ZIP-bestand staat.
1. Kopieer alle code uit `AppMeasurement_Module_AudienceManagement.js` het ZIP-bestand. Plak het in het `appMeasurement.js` bestand net boven de tekst, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Voeg de code toe, `s.loadModule("AudienceManagement");`net boven de `AppMeasurement_Module_AudienceManagement.js` code die u zojuist hebt toegevoegd in de vorige stap.
1. Werk de onderstaande code bij en kopieer deze naar de `doPlugins` functie in het `AppMeasurement.js` bestand.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>De `audienceManagement.setup` functie deelt parameters met de [!DNL Audience Manager] `DIL.create` functie, die u in deze code kunt vormen. Zie [DIL maken](../../dil/dil-class-overview/dil-create.md#dil-create)voor meer informatie over deze parameters.

## Codeelementen gedefinieerd {#code-elements-defined}

In de volgende tabel worden belangrijke variabelen in het codevoorbeeld gedefinieerd.

| Parameter | Beschrijving |
|--- |--- |
| `partner` | Vereist. Dit is een partnernaam die aan u door wordt toegewezen [!DNL Adobe]. Het wordt soms bedoeld als uw [!UICONTROL partner ID] of partnersubdomain.  Neem contact op met uw [!DNL Adobe] consultant of [klantenservice](https://helpx.adobe.com/marketing-cloud/contact-support.html) als u uw partnernaam niet kent. |
| `containerNSID` | Vereist. De meeste klanten kunnen enkel plaatsen `"containerNSID":0` . Als uw bedrijf de id-syncs echter moet aanpassen met een andere container, kunt u die container-id hier opgeven. |
| `uuidCookie` | Optioneel. Met deze configuratie kunt u een [!DNL Adobe] cookie instellen in het domein van de eerste fabrikant. Dit [!DNL cookie] bevat de [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Vereist. De `namespace` parameter is vereist als u de [!DNL AudienceManagement] module gebruikt die is gebundeld met [!UICONTROL AppMeasurement] versie 2.10 of hoger. Deze [!UICONTROL AudienceManagement] module vereist dat u [!UICONTROL Adobe Experience Platform Identity Service] 3.3 of hoger gebruikt. <br><br>De id [!UICONTROL Experience Cloud Organization ID] is de id waarmee een bedrijf wordt voorzien wanneer het zich aanmeldt voor de [!UICONTROL Experience Cloud]account. Zoek de organisatie-id van uw bedrijf op in [Organisaties en Account Linking](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Resultaten: Gegevens doorsturen naar [!DNL Audience Manager] {#results-data-forwarding}

Uw [!DNL Analytics] implementatie verzendt gegevens naar [!DNL Audience Manager] nadat u hebt:

* Ingeschakeld [!UICONTROL Server-Side Forwarding] (overleg met uw consultant over deze functie);
* ten uitvoer gelegd [!DNL Adobe Experience Platform Identity Service];
* Volg de implementatiestappen in deze zelfstudie.

Tijdens dit proces worden gegevens verzonden naar [!DNL Audience Manager]:

* Aanroepen in de paginaweergave;
* van bijgehouden koppelingen;
* Op basis van videobeelden met mijlpaal en hartslag.

>[!NOTE]
>
>De variabelen die naar [!DNL Audience Manager] van het [!DNL Analytics] gebruik speciale prefixen worden verzonden. U moet deze voorvoegsels begrijpen en er rekening mee houden wanneer u [!DNL Audience Manager] eigenschappen maakt. Voor meer informatie over deze prefixen, zie de Vereisten van het [Prefix voor Zeer belangrijke Variabelen](../../features/traits/trait-variable-prefixes.md).
