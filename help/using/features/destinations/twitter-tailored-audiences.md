---
description: In dit artikel wordt uitgelegd hoe u het Twitter-publiek op maat kunt configureren voor zowel nieuwe als bestaande integratie.
seo-description: In dit artikel wordt uitgelegd hoe u het Twitter-publiek op maat kunt configureren voor zowel nieuwe als bestaande integratie.
seo-title: Configureer Twitter-doelgroepen op maat als op apparaat gebaseerde zelfbediening
solution: Audience Manager
title: Configureer Twitter-doelgroepen op maat als op apparaat gebaseerde zelfbediening
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 8ff76decc1cbd7f7babd619dd1ce9fe047541337
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 0%

---


# Vorm [!DNL Twitter Tailored Audiences] als Op apparaat-Gebaseerde Bestemming van de Zelfbediening {#configure-twitter}

In dit artikel wordt uitgelegd hoe u een integratie met [Twitter Tailored Audiences](https://business.twitter.com/en/targeting/tailored-audiences.html)configureert.

## Vereisten {#prerequisites}

Controleer voordat u uw [!DNL Twitter Tailored Audiences] bestemming configureert de volgende Twitter-voorwaarden waaraan u moet voldoen.

1. Je [!DNL Twitter Ads] account moet in aanmerking komen voor reclame. Nieuwe [!DNL Twitter Ads] accounts komen de eerste twee weken na het aanmaken ervan niet in aanmerking voor reclame.
2. Uw [!DNL Twitter] gebruikersrekening die u toegang voor in Audience Manager erkende moet de toegelaten toestemming van de [het publieksmanager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) van de Partner hebben.
3. Wanneer u de eerste [!DNL Twitter Tailored Audiences] bestemming in uw exemplaar van de Audience Manager maakt, neemt u contact op met Adobe Consulting of de klantenservice om de synchronisatie van de [!DNL Twitter] id (gegevensbron-id = 1123) voor uw account in te schakelen. Dit is vereist voor de juiste synchronisatie tussen Audience Manager en [!DNL Twitter].

## Een nieuw [!DNL Twitter Tailored Audiences] doel toevoegen {#add-new-twitter-destination}

Deze sectie beschrijft de stappen u moet volgen wanneer het vormen van een nieuwe op apparaat-gebaseerde bestemming voor [!DNL Twitter Tailored Audiences]. In dit scenario wordt ervan uitgegaan dat er geen bestaande [!DNL Twitter Tailored Audiences] bestemming is geconfigureerd via uw Adobe-consultant of de klantenservice.

### Stap 1. Verifiëren met [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Voordat u de op een apparaat gebaseerde bestemming kunt toevoegen, moet u Audience Manager en uw [!DNL Twitter Tailored Audiences] account koppelen. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!DNL Administration > Integrated Accounts]**. Als u een eerder gevormde integratie met een bestemmingsplatform hebt, zou u het in deze pagina moeten zien die. Anders is de pagina leeg.
1. Klik op **[!DNL Add Account]**.
1. Selecteer [!DNL Twitter Tailored Audiences] en klik **[!DNL Confirm]** om naar de authentificatiepagina worden opnieuw geleid.                     ![geïntegreerde platforms](assets/dbd-integrated-platforms.png)
1. Nadat u de verificatie hebt voltooid, wordt u doorgestuurd naar de Audience Manager waar u de bijbehorende adverteerderaccounts kunt bekijken. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!DNL Confirm]**.

### Stap 2. Een nieuwe op apparaten gebaseerde bestemming maken {#step2-create-new-destination}

Nadat u Audience Manager en uw [!DNL Twitter Tailored Audiences], u hebt verbonden kunt tot de nieuwe bestemming leiden. Dit doet u als volgt:

>[!NOTE]
>
>U kunt de naam van een bestaand op apparaat gebaseerd doel niet wijzigen. Zorg ervoor om een naam te verstrekken die u zal helpen de bestemming correct identificeren.

1. Meld u aan bij uw Audience Manager-account, ga naar **[!DNL Audience Data > Destinations]** en klik op **[!DNL Create Destination]**.
1. Voer in de **[!DNL Basic Information]** sectie een **[!DNL Name]** en **[!DNL Description]** voor uw nieuwe bestemming in en gebruik de onderstaande instellingen: ![instellen](assets/dbd-new-basic.png)
1. Klik op **[!DNL Next]**.
1. Kies de labels voor [gegevensexport](/help/using/features/data-export-controls.md#controls-labels) die u voor dit doel wilt instellen.
1. Klik op **[!DNL Save]**.
1. Selecteer in de **[!DNL Segment Mappings]** sectie de publiekssegmenten die u naar deze bestemming wilt verzenden.
1. Sla het doel op.

## Overwegingen bij het toewijzen van segmenten {#segment-mapping-considerations}

Wanneer het in kaart brengen van publiekssegmenten aan [!UICONTROL Twitter], zorg ervoor om aan de volgende segment noemende vereisten te voldoen:

* Verstrek de mens-leesbare namen van de segmentafbeelding. Wij adviseren gebruikend de zelfde naam die u voor de segmenten van de Audience Manager gebruikte.
* Gebruik geen speciale tekens (`,``%` `:``;` `@` `/``=` `?` `$`) in segment- en segmenttoewijzingsnamen. Als uw Audience Manager segmentnaam deze karakters bevat, gelieve te verwijderen hen alvorens het segment aan een [!UICONTROL Twitter] bestemming toe te wijzen.

### Voorbeeld

* Segment- of toewijzingsnaam corrigeren: &quot;Amerikaanse en Europese kopers&quot;;
* Onjuiste segment- of toewijzingsnaam: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>U kunt de namen van al toegewezen segmenten niet wijzigen. Audience Manager gebruikt de segmentnamen om de segmenten in de integratie correct te identificeren.

## Aandachtspunten {#match-rates-considerations}

* De integratie tussen Audience Manager en [!UICONTROL Twitter Tailored Audiences] steunt historische publieksbackfills. Alle segmentkwalificaties worden verzonden naar [!UICONTROL Twitter] wanneer u de bestemming maakt.
