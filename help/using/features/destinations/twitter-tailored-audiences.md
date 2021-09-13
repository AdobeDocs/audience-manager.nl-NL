---
description: In dit artikel wordt uitgelegd hoe u Aangepast publiek voor Twitter kunt configureren voor zowel nieuwe als bestaande integratie.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Aangepast publiek voor Twitter configureren als op apparaat gebaseerde zelfbediening
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 8023bfe1e4ea415867e1233f143627ff179cce42
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# [!DNL Twitter Custom Audiences] als Op apparaat-Gebaseerde Bestemming van de Zelfbediening vormen {#configure-twitter}

In dit artikel wordt uitgelegd hoe u integratie kunt configureren met [Twitter Custom Audiences](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Vereisten {#prerequisites}

Voordat u de bestemming [!DNL Twitter Custom Audiences] configureert, moet u controleren of aan de volgende Twitter-voorwaarden is voldaan.

1. Uw [!DNL Twitter Ads]-account moet in aanmerking komen voor advertenties. Nieuwe [!DNL Twitter Ads]-accounts komen de eerste twee weken na het maken niet in aanmerking voor reclame.
2. Uw [!DNL Twitter] gebruikersrekening die u toegang voor in Audience Manager toeliet moet [Toegelaten van het publiek van de Partner manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) hebben.
3. Wanneer u de eerste [!DNL Twitter Custom Audiences]-bestemming in uw Audience Manager-exemplaar maakt, neemt u contact op met Adobe Consulting of de klantenservice om de synchronisatie van [!DNL Twitter]-id (Data Source ID = 1123) voor uw account in te schakelen. Dit wordt vereist voor de correcte synchronisatie tussen Audience Manager en [!DNL Twitter].

## Nieuw [!DNL Twitter Custom Audiences]-doel toevoegen {#add-new-twitter-destination}

Deze sectie beschrijft de stappen u moet volgen wanneer het vormen van een nieuwe op apparaat-gebaseerde bestemming voor [!DNL Twitter Custom Audiences]. In dit scenario wordt ervan uitgegaan dat u geen bestaande [!DNL Twitter Custom Audiences]-bestemming hebt die via uw Adobe-consultant of klantenservice is geconfigureerd.

### Stap 1. Verifiëren met [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Voordat u de op een apparaat gebaseerde bestemming kunt toevoegen, moet u Audience Manager en uw [!DNL Twitter Custom Audiences]-account koppelen. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!DNL Administration > Integrated Accounts]**. Als u een eerder gevormde integratie met een bestemmingsplatform hebt, zou u het in deze pagina moeten zien die. Anders is de pagina leeg.
1. Klik op **[!DNL Add Account]**.
1. Selecteer [!DNL Twitter Custom Audiences] en klik **[!DNL Confirm]** om naar de authentificatiepagina worden opnieuw gericht.

   ![geïntegreerde platforms](assets/dbd-integrated-platforms.png)

1. Nadat u de verificatie hebt voltooid, wordt u doorgestuurd naar de Audience Manager waar u de bijbehorende adverteerderaccounts kunt bekijken. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!DNL Confirm]**.

### Stap 2. Een nieuwe op apparaten gebaseerde bestemming maken {#step2-create-new-destination}

Nadat u Audience Manager en uw [!DNL Twitter Custom Audiences] hebt verbonden, kunt u de nieuwe bestemming tot stand brengen. Dit doet u als volgt:

>[!NOTE]
>
>U kunt de naam van een bestaand op apparaat gebaseerd doel niet wijzigen. Zorg ervoor om een naam te verstrekken die u zal helpen de bestemming correct identificeren.

1. Meld u aan bij uw Audience Manager-account, ga naar **[!DNL Audience Data > Destinations]** en klik op **[!DNL Create Destination]**.
1. Voer in de sectie **[!DNL Basic Information]** een **[!DNL Name]** en **[!DNL Description]** in voor uw nieuwe bestemming en gebruik de onderstaande instellingen: ![setup](assets/dbd-new-basic.png)
1. Klik op **[!DNL Next]**.
1. Kies de [Labels voor gegevensexport](/help/using/features/data-export-controls.md#controls-labels) die u voor deze bestemming wilt instellen.
1. Klik op **[!DNL Save]**.
1. Selecteer in de sectie **[!DNL Segment Mappings]** de publiekssegmenten die u naar deze bestemming wilt verzenden.
1. Sla het doel op.

## Overwegingen bij het toewijzen van segmenten {#segment-mapping-considerations}

Wanneer het in kaart brengen van publiekssegmenten aan [!UICONTROL Twitter], zorg ervoor om aan de volgende segment noemende vereisten te voldoen:

* Verstrek de mens-leesbare namen van de segmentafbeelding. Wij adviseren gebruikend de zelfde naam die u voor de segmenten van de Audience Manager gebruikte.
* Gebruik geen speciale tekens (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) in segment- en segmenttoewijzingsnamen. Als uw Audience Manager segmentnaam deze karakters bevat, te verwijderen gelieve hen alvorens het segment aan een [!UICONTROL Twitter] bestemming in kaart te brengen.

### Voorbeeld

* Segment- of toewijzingsnaam corrigeren: &quot;Amerikaanse en Europese kopers&quot;;
* Onjuiste segment- of toewijzingsnaam: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>U kunt de namen van al toegewezen segmenten niet wijzigen. Audience Manager gebruikt de segmentnamen om de segmenten in de integratie correct te identificeren.

## Aandachtspunten {#match-rates-considerations}

* De integratie tussen Audience Manager en [!UICONTROL Twitter Custom Audiences] steunt historische publieksbackfills. Alle segmentkwalificaties worden verzonden naar [!UICONTROL Twitter] wanneer u de bestemming creeert.
