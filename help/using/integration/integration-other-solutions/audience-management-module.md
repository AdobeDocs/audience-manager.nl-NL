---
description: Voeg de Module van het Beheer van de Publiek aan Adobe Analytics AppMeasurement toe om de gegevens van Analytics aan Audience Manager door te sturen in plaats van het hebben van de code van de Data Integration Library van de Audience Manager (DIL) een pixel van de pagina verzendt.
keywords: publieksanalyses; analytische gegevens; ssf; server side forward
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementeer de module Audience Management
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# Gegevens doorsturen van [!DNL Adobe Analytics] tot [!DNL Audience Manager] {#implement-the-audience-management-module}

Voer de stappen in deze zelfstudie uit om door te sturen [!DNL Analytics] gegevens naar [!DNL Audience Manager] in plaats van de [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) een pixel van de pagina verzenden.

>[!TIP]
>
>We raden u aan [!DNL Adobe Experience Platform Tags] doorsturen [!UICONTROL Analytics] gegevens in [!DNL Audience Manager]. Met [!UICONTROL Tags], hoeft u code niet handmatig te kopiëren naar [!DNL AppMeasurement], zoals weergegeven op deze pagina.

## Vereisten {#prereqs}

Naast het inschakelen van de extensies of het implementeren van de code die in dit document wordt beschreven, moet u ook:

* Implementeer de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Inschakelen [Server-kant doorsturen](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) voor rapportageopties in de [!UICONTROL Adobe Analytics Admin Console].

## Implementatie {#implementation}

Er zijn twee methodes om gegevens uit te voeren door:sturen van [!DNL Adobe Analytics] tot [!DNL Audience Manager], afhankelijk van de oplossing voor tagbeheer die u gebruikt.

### Implementatie met [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] raadt u aan de [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) uitbreiding van het instrument [!DNL Adobe Analytics] en [!DNL Audience Manager] op uw eigenschappen. In dit geval hoeft u geen code handmatig te kopiëren. In plaats daarvan moet u het delen van gegevens inschakelen in het dialoogvenster [!DNL Analytics] zoals weergegeven in de onderstaande afbeelding. Zie ook de [Adobe Analytics-extensie](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) documentatie.

>[!TIP]
>
>Als u de [!DNL Adobe Analytics] uitbreiding, *niet* installeer ook de [!DNL Audience Manager] extensie. Gegevens doorsturen vanuit de [!DNL Analytics] de extensie vervangt de extensie [!DNL Audience Manager] extensiefunctionaliteit.

![Hoe te om gegevens toe te laten delend van de uitbreiding van Adobe Analytics aan Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Codeelementen gedefinieerd {#code-elements-defined}

In de volgende tabel worden belangrijke variabelen in het codevoorbeeld gedefinieerd.

| Parameter | Beschrijving |
|--- |--- |
| `partner` | Vereist. Dit is een partnernaam die aan u door wordt toegewezen [!DNL Adobe]. Het wordt soms bedoeld als uw [!UICONTROL partner ID] of subdomein van partner.  Neem contact op met uw [!DNL Adobe] consultant of [Klantenservice](https://helpx.adobe.com/marketing-cloud/contact-support.html) als u uw partnernaam niet kent. |
| `containerNSID` | Vereist. De meeste klanten kunnen enkel plaatsen  `"containerNSID":0` . Als uw bedrijf de id-syncs echter moet aanpassen met een andere container, kunt u die container-id hier opgeven. |
| `uuidCookie` | Optioneel. Met deze configuratie kunt u een [!DNL Adobe] cookie in het domein van de eerste fabrikant. Dit [!DNL cookie] bevat de [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Vereist. De `namespace` parameter is vereist als u [!DNL AudienceManagement] module gebundeld met [!UICONTROL AppMeasurement] versie 2.10 of hoger. Dit [!UICONTROL AudienceManagement] vereist dat u [!UICONTROL Adobe Experience Platform Identity Service] 3.3 of hoger. <br><br>De [!UICONTROL Experience Cloud Organization ID] is identiteitskaart die een bedrijf bij het ondertekenen voor wordt voorzien [!UICONTROL Experience Cloud]. Zoek de organisatie-id van uw bedrijf op [Organisaties en account koppelen](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Resultaten: Gegevens doorsturen naar [!DNL Audience Manager] {#results-data-forwarding}

Uw [!DNL Analytics] implementatie verzendt gegevens naar [!DNL Audience Manager] nadat u:

* Ingeschakeld [!UICONTROL Server-Side Forwarding] (overleg met uw consultant over deze functie);
* Geïmplementeerd [!DNL Adobe Experience Platform Identity Service];
* Volg de implementatiestappen in deze zelfstudie.

Tijdens dit proces worden gegevens verzonden naar [!DNL Audience Manager]:

* Aanroepen in de paginaweergave;
* van bijgehouden koppelingen;
* Op basis van videobeelden met mijlpaal en hartslag.

>[!NOTE]
>
>De variabelen die naar [!DNL Audience Manager] van [!DNL Analytics] speciale voorvoegsels gebruiken. U moet deze voorvoegsels begrijpen en er rekening mee houden wanneer u [!DNL Audience Manager] kenmerken. Zie voor meer informatie over deze voorvoegsels [Voorvoegselvereisten voor belangrijkste variabelen](../../features/traits/trait-variable-prefixes.md).
