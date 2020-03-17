---
description: Voeg de module Audience Management toe aan Adobe Analytics AppMeasurement om analysegegevens door te sturen naar Audience Manager in plaats van dat de DIL-code (Audience Manager Data Integration Library) een pixel van de pagina verzendt.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Voeg de module Audience Management toe aan Adobe Analytics AppMeasurement om analysegegevens door te sturen naar Audience Manager in plaats van dat de DIL-code (Audience Manager Data Integration Library) een pixel van de pagina verzendt.
seo-title: Implementeer de module Audience Management
solution: Audience Manager
title: Implementeer de module Audience Management
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Gegevens van Adobe Analytics doorsturen naar Audience Manager {#implement-the-audience-management-module}

Voer de stappen in deze zelfstudie uit om [!DNL Analytics] gegevens door te sturen naar Audience Manager in plaats van de code Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) een pixel van de pagina te laten verzenden.

>[!TIP]
>
>We raden u aan gegevens door te sturen [!DNL Adobe Experience Platform Launch] [!UICONTROL Analytics] naar Audience Manager. Door te gebruiken, moet u code niet manueel kopiëren in [!UICONTROL Launch][!UICONTROL AppMeasurement], zoals aangetoond op deze pagina.

## Vereisten {#prereqs}

Naast het inschakelen van de extensies of het implementeren van de code die in dit document wordt beschreven, moet u ook:

* Implementeer de identiteitsservice [van het](https://marketing.adobe.com/resources/help/en_US/mcvid/)Adobe Experience Platform.
* Schakel [Server-Side Forwarding](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) in voor rapportsuites in de [!UICONTROL Adobe Analytics Admin Console].

## Implementatie {#implementation}

Er zijn twee methoden om gegevens door:sturen van Adobe Analytics naar Audience Manager te implementeren, afhankelijk van de oplossing voor tagbeheer die u gebruikt.

### Implementatie met Adobe Experience Platform Launch

Adobe raadt u aan de extensie [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) te gebruiken om Adobe Analytics en Audience Manager te instrumenteren voor uw eigenschappen. In dit geval hoeft u geen code handmatig te kopiëren. In plaats daarvan moet u gegevensdeling inschakelen in de extensie Analytics Launch, zoals in de onderstaande afbeelding wordt getoond. Zie ook de documentatie bij [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Als u de extensie Adobe Analytics installeert, installeert u *niet* ook de extensie Audience Manager. Door gegevens uit de extensie Analytics te verzenden, wordt de extensiefunctie Audience Manager vervangen.

![Gegevens delen inschakelen vanuit de extensie Adobe Analytics naar Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementatie met Adobe Digital Tag Management (DTM) of een andere oplossing voor tagbeheer


>[!WARNING]
>
>Adobe heeft plannen gepubliceerd om de DTM tegen eind 2020 te onderbreken. Raadpleeg DTM-plannen voor een zonsondergang in de [Adobe-communityforums](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)voor meer informatie en planning.

Implementeer de [!UICONTROL Audience Management Module] toepassing met [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) of een andere oplossing voor tagbeheer:

1. Download dit [!UICONTROL AppMeasurement] met [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (vereist versie 1.5 of hoger).
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
>De `audienceManagement.setup` functie deelt parameters met de `DIL.create` functie van de Manager van de Publiek, die u in deze code kunt vormen. Zie [DIL maken](../../dil/dil-class-overview/dil-create.md#dil-create)voor meer informatie over deze parameters.

## Codeelementen gedefinieerd {#code-elements-defined}

In de volgende tabel worden belangrijke variabelen in het codevoorbeeld gedefinieerd.

| Parameter | Beschrijving |
|--- |--- |
| `partner` | Vereist. Dit is een partnernaam die door Adobe aan u is toegewezen. Het wordt soms bedoeld als uw &quot;partner identiteitskaart&quot;of &quot;partner subdomain.&quot;  Neem contact op met uw Adobe-consultant of [klantenservice](https://helpx.adobe.com/marketing-cloud/contact-support.html) als u de naam van uw partner niet kent. |
| `containerNSID` | Vereist. De meeste klanten kunnen enkel plaatsen `"containerNSID":0` . Als uw bedrijf de id-syncs echter moet aanpassen met een andere container, kunt u die container-id hier opgeven. |
| `uuidCookie` | Optioneel. Met deze configuratie kunt u een Adobe-cookie instellen in het domein van de eerste fabrikant. Deze cookie bevat de [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Vereist. De `namespace` parameter wordt vereist als u de module AudienceManagement gebruikt die met [!UICONTROL AppMeasurement] versie 2.10 of hoger wordt gebundeld. Deze [!UICONTROL AudienceManagement] module vereist dat u [!UICONTROL Adobe Experience Platform Identity Service] 3.3 of hoger gebruikt. <br> De id [!UICONTROL Experience Cloud Organization ID] is de id waarmee een bedrijf wordt voorzien wanneer het zich aanmeldt voor de [!UICONTROL Experience Cloud]account. Zoek de organisatie-id van uw bedrijf op in [Organisaties en Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Resultaten: Gegevens doorsturen naar Audience Manager {#results-data-forwarding}

Uw [!DNL Analytics] implementatie verzendt gegevens naar de Manager van het Publiek nadat u hebt:

* Ingeschakeld [!UICONTROL Server-Side Forwarding] (overleg met uw consultant over deze functie);
* De Adobe Experience Platform Identity Service geïmplementeerd;
* Volg de implementatiestappen in deze zelfstudie.

Tijdens dit proces worden gegevens verzonden naar [!DNL Audience Manager]:

* Aanroepen in de paginaweergave;
* van bijgehouden koppelingen;
* Op basis van videobeelden met mijlpaal en hartslag.

>[!NOTE]
>
>De variabelen die vanuit speciale voorvoegsels naar Audience Manager worden verzonden. [!DNL Analytics] U moet deze voorvoegsels begrijpen en in aanmerking nemen wanneer u de kenmerken van Audience Manager maakt. Voor meer informatie over deze prefixen, zie de Vereisten van het [Prefix voor Zeer belangrijke Variabelen](../../features/traits/trait-variable-prefixes.md).