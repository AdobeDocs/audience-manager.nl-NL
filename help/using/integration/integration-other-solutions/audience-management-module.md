---
description: Voeg de module Audience Management aan Adobe Analytics AppMeasurement toe om analysegegevens door te sturen naar Audience Manager in plaats van de Audience Manager Data Integration Library-code (DIL) een pixel van de pagina te laten verzenden.
keywords: publieksanalyses; analyses; ssf; server side forward
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementeer de module Audience Management
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Gegevens doorsturen van [!DNL Adobe Analytics] naar [!DNL Audience Manager] {#implement-the-audience-management-module}

Voer de stappen in deze zelfstudie uit om [!DNL Analytics] -gegevens door te sturen naar [!DNL Audience Manager] in plaats van de [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL] )-code een pixel van de pagina te laten verzenden.

>[!TIP]
>
>We raden u aan [!DNL Adobe Experience Platform Tags] te gebruiken om [!UICONTROL Analytics] -gegevens door te sturen naar [!DNL Audience Manager] . Als u [!UICONTROL Tags] gebruikt, hoeft u niet handmatig code naar [!DNL AppMeasurement] te kopiëren, zoals op deze pagina wordt getoond.

## Vereisten {#prereqs}

Naast het inschakelen van de extensies of het implementeren van de code die in dit document wordt beschreven, moet u ook:

* Voer de [&#x200B; Dienst van de Identiteit van Adobe Experience Platform &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL) uit.
* Laat [&#x200B; Server-kant door:sturen &#x200B;](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=nl-NL) voor rapportreeksen in toe [!UICONTROL Adobe Analytics Admin Console].

## Implementatie {#implementation}

Er zijn twee methoden om het doorsturen van gegevens van [!DNL Adobe Analytics] naar [!DNL Audience Manager] te implementeren, afhankelijk van de oplossing voor tagbeheer die u gebruikt.

### Implementatie met [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] adviseert u de [&#x200B; 2&rbrace; uitbreiding van Markeringen {aan instrument &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=nl-NL) en [!DNL Adobe Analytics] op uw eigenschappen gebruikt. [!DNL Audience Manager] In dit geval hoeft u geen code handmatig te kopiëren. In plaats daarvan moet u gegevensdeling inschakelen in de extensie [!DNL Analytics] , zoals in de onderstaande afbeelding wordt getoond. Zie ook de [&#x200B; documentatie van de Uitbreiding van 0} Adobe Analytics.](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=nl-NL#adobe-audience-manager)

>[!TIP]
>
>Als u de [!DNL Adobe Analytics] uitbreiding installeert, *installeert* ook niet de [!DNL Audience Manager] uitbreiding. Door gegevens van de extensie [!DNL Analytics] te verzenden, vervangt u de extensiefunctie [!DNL Audience Manager] .

![&#x200B; hoe te om gegevens toe te laten delend van de uitbreiding van Adobe Analytics aan Audience Manager &#x200B;](/help/using/integration/assets/analytics-to-aam.png)

## Codeelementen gedefinieerd {#code-elements-defined}

In de volgende tabel worden belangrijke variabelen in het codevoorbeeld gedefinieerd.

| Parameter | Beschrijving |
|--- |--- |
| `partner` | Vereist. Dit is een partnernaam die door [!DNL Adobe] aan u wordt toegewezen. Het wordt soms bedoeld als uw [!UICONTROL partner ID] of partnersubdomain.  Contacteer uw [!DNL Adobe] adviseur of [&#x200B; Zorg van de Klant &#x200B;](https://helpx.adobe.com/nl/marketing-cloud/contact-support.html) als u uw partnernaam niet kent. |
| `containerNSID` | Vereist. De meeste klanten kunnen gewoon `"containerNSID":0` instellen. Als uw bedrijf de id-syncs echter moet aanpassen met een andere container, kunt u die container-id hier opgeven. |
| `uuidCookie` | Optioneel. Met deze configuratie kunt u een [!DNL Adobe] -cookie instellen in het domein van de eerste partij. Dit [!DNL cookie] bevat [&#x200B; UUID &#x200B;](../../reference/ids-in-aam.md). |
| `visitorService` - `namespace` | Vereist. De parameter `namespace` is vereist als u de [!DNL AudienceManagement] module gebruikt die is gebundeld met [!UICONTROL AppMeasurement] versie 2.10 of hoger. Voor deze [!UICONTROL AudienceManagement] -module moet u [!UICONTROL Adobe Experience Platform Identity Service] 3.3 of hoger gebruiken. <br><br> [!UICONTROL Experience Cloud Organization ID] is identiteitskaart die een bedrijf bij het ondertekenen voor [!UICONTROL Experience Cloud] wordt voorzien. Kom identiteitskaart van de Organisatie van uw bedrijf in [&#x200B; Organisaties en de Verbinding van de Rekening &#x200B;](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=nl-NL) te weten. |

## Resultaten: gegevens doorsturen naar [!DNL Audience Manager] {#results-data-forwarding}

Uw [!DNL Analytics] -implementatie verzendt gegevens naar [!DNL Audience Manager] nadat u:

* Ingeschakeld [!UICONTROL Server-Side Forwarding] (overleg met uw consultant over deze functie);
* Implemented the [!DNL Adobe Experience Platform Identity Service];
* Volg de implementatiestappen in deze zelfstudie.

Tijdens dit proces worden gegevens verzonden naar [!DNL Audience Manager] :

* Aanroepen in de paginaweergave;
* van bijgehouden koppelingen;
* Op basis van videobeelden met mijlpaal en hartslag.

>[!NOTE]
>
>Voor de variabelen die vanuit [!DNL Audience Manager] naar [!DNL Analytics] worden verzonden, worden speciale voorvoegsels gebruikt. U moet deze voorvoegsels begrijpen en er rekening mee houden wanneer u [!DNL Audience Manager] -kenmerken maakt. Voor meer informatie over deze prefixen, zie [&#x200B; Eisen van het Prefix voor Zeer belangrijke Variabelen &#x200B;](../../features/traits/trait-variable-prefixes.md).
