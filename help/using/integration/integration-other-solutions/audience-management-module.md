---
description: Voeg de Module van het Beheer van de Publiek aan Adobe Analytics AppMeasurement toe om de gegevens van Analytics aan Audience Manager door te sturen in plaats van het hebben van de code van de Data Integration Library van de Audience Manager (DIL) een pixel van de pagina verzendt.
keywords: publieksanalyses; analytische gegevens; ssf; server side forward
seo-description: Voeg de Module van het Beheer van de Publiek aan Adobe Analytics AppMeasurement toe om de gegevens van Analytics aan Audience Manager door te sturen in plaats van het hebben van de code van de Data Integration Library van de Audience Manager (DIL) een pixel van de pagina verzendt.
seo-title: Implementeer de module Audience Management
solution: Audience Manager
title: Implementeer de module Audience Management
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics-integratie
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 2%

---

# Gegevens doorsturen van [!DNL Adobe Analytics] naar [!DNL Audience Manager] {#implement-the-audience-management-module}

Voer de stappen in deze zelfstudie uit om [!DNL Analytics] gegevens door te sturen naar [!DNL Audience Manager] in plaats van de [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) code een pixel van de pagina te laten verzenden.

>[!TIP]
>
>We raden u aan [!DNL Adobe Experience Platform Launch] te gebruiken om [!UICONTROL Analytics] gegevens door te sturen naar [!DNL Audience Manager]. Door [!UICONTROL Launch] te gebruiken, moet u code niet manueel kopiëren in [!DNL AppMeasurement], zoals aangetoond op deze pagina.

## Vereisten {#prereqs}

Naast het inschakelen van de extensies of het implementeren van de code die in dit document wordt beschreven, moet u ook:

* Implementeer [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/nl-NL/id-service/using/home.html).
* Schakel [Server-Side Forwarding](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) in voor rapportsuites in [!UICONTROL Adobe Analytics Admin Console].

## Implementatie {#implementation}

Er zijn twee methodes om gegevens uit te voeren door:sturen van [!DNL Adobe Analytics] aan [!DNL Audience Manager], afhankelijk van de oplossing van het markeringsbeheer die u gebruikt.

### Implementatie met [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] raadt u aan de  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launchextension te gebruiken voor instrumenten  [!DNL Adobe Analytics] en  [!DNL Audience Manager] voor eigenschappen. In dit geval hoeft u geen code handmatig te kopiëren. In plaats daarvan moet u gegevensdeling inschakelen in de extensie [!DNL Analytics Launch], zoals in de onderstaande afbeelding wordt getoond. Zie ook de [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) documentatie.

>[!TIP]
>
>Als u de [!DNL Adobe Analytics] uitbreiding installeert, *installeer niet* ook de [!DNL Audience Manager] uitbreiding. Door gegevens uit de extensie [!DNL Analytics] te verzenden, wordt de extensiefunctie [!DNL Audience Manager] vervangen.

![Hoe te om gegevens toe te laten delend van de uitbreiding van Adobe Analytics aan Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Codeelementen gedefinieerd {#code-elements-defined}

In de volgende tabel worden belangrijke variabelen in het codevoorbeeld gedefinieerd.

| Parameter | Beschrijving |
|--- |--- |
| `partner` | Vereist. Dit is een partnernaam die aan u door [!DNL Adobe] wordt toegewezen. Het wordt soms bedoeld als uw [!UICONTROL partner ID] of partnersubdomain.  Neem contact op met uw [!DNL Adobe] consultant of [Klantenservice](https://helpx.adobe.com/marketing-cloud/contact-support.html) als u de naam van uw partner niet kent. |
| `containerNSID` | Vereist. De meeste klanten kunnen `"containerNSID":0` enkel plaatsen. Als uw bedrijf de id-syncs echter moet aanpassen met een andere container, kunt u die container-id hier opgeven. |
| `uuidCookie` | Optioneel. Met deze configuratie kunt u een [!DNL Adobe]-cookie instellen in het domein van de eerste partij. Deze [!DNL cookie] bevat [UUID](../../reference/ids-in-aam.md). |
| `visitorService` -  `namespace` | Vereist. De `namespace` parameter wordt vereist als u [!DNL AudienceManagement] module gebruikt die met [!UICONTROL AppMeasurement] versie 2.10 of nieuwer wordt gebundeld. Deze [!UICONTROL AudienceManagement] module vereist dat u [!UICONTROL Adobe Experience Platform Identity Service] 3.3 of nieuwer gebruikt. <br><br>De id  [!UICONTROL Experience Cloud Organization ID] is de id waarmee een bedrijf wordt uitgerust wanneer het zich aanmeldt voor de  [!UICONTROL Experience Cloud]account. Ontdek de organisatie-id van uw bedrijf in [Organisaties en Account Linking](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Resultaten: Gegevens doorsturen naar [!DNL Audience Manager] {#results-data-forwarding}

Uw [!DNL Analytics] implementatie verzendt gegevens naar [!DNL Audience Manager] nadat u hebt:

* Ingeschakeld [!UICONTROL Server-Side Forwarding] (overleg met uw consultant over deze functie);
* geïmplementeerd [!DNL Adobe Experience Platform Identity Service];
* Volg de implementatiestappen in deze zelfstudie.

Tijdens dit proces worden gegevens verzonden naar [!DNL Audience Manager]:

* Aanroepen in de paginaweergave;
* van bijgehouden koppelingen;
* Op basis van videobeelden met mijlpaal en hartslag.

>[!NOTE]
>
>Voor de variabelen die vanuit [!DNL Analytics] naar [!DNL Audience Manager] worden verzonden, worden speciale voorvoegsels gebruikt. U moet deze voorvoegsels begrijpen en hiermee rekening houden wanneer u [!DNL Audience Manager]-kenmerken maakt. Zie [Voorvoegselvereisten voor belangrijke variabelen](../../features/traits/trait-variable-prefixes.md) voor meer informatie over deze voorvoegsels.
