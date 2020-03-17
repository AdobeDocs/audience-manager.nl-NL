---
description: In dit artikel wordt uitgelegd hoe u het Twitter-publiek op maat kunt configureren voor zowel nieuwe als bestaande integratie.
seo-description: In dit artikel wordt uitgelegd hoe u het Twitter-publiek op maat kunt configureren voor zowel nieuwe als bestaande integratie.
seo-title: Configureer Twitter-doelgroepen op maat als op apparaat gebaseerde zelfbediening
solution: Audience Manager
title: Configureer Twitter-doelgroepen op maat als op apparaat gebaseerde zelfbediening
translation-type: tm+mt
source-git-commit: 0f1ab99b648dd6e1eda5f2e5b6bd1f620c0331ee

---


# Vorm [!DNL Twitter Tailored Audiences] als Op apparaat-Gebaseerde Bestemming van de Zelfbediening {#configure-twitter}

In dit artikel wordt uitgelegd hoe u een integratie met [Twitter Tailored Audiences](https://business.twitter.com/en/targeting/tailored-audiences.html)configureert.

## Vereisten {#prerequisites}

Controleer voordat u uw [!DNL Twitter Tailored Audiences] bestemming configureert de volgende Twitter-voorwaarden waaraan u moet voldoen.

1. Je [!DNL Twitter Ads] account moet in aanmerking komen voor reclame. Nieuwe [!DNL Twitter Ads] accounts komen de eerste twee weken na het aanmaken ervan niet in aanmerking voor reclame.
2. Uw [!DNL Twitter] gebruikersrekening die u toegang voor in de Manager van het Publiek erkende moet de toegelaten toestemming van de [het publieksmanager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) van de Partner hebben.
3. Neem bij het maken van de eerste [!DNL Twitter Tailored Audiences] bestemming in de instantie Audience Manager contact op met de consultant van Adobe of de klantenservice om de synchronisatie van de [!DNL Twitter] id (gegevensbron-id = 1123) voor uw account in te schakelen. Dit is vereist voor de correcte synchronisatie tussen de Manager van de Publiek en [!DNL Twitter].

## Een nieuw [!DNL Twitter Tailored Audiences] doel toevoegen {#add-new-twitter-destination}

Deze sectie beschrijft de stappen u moet volgen wanneer het vormen van een nieuwe op apparaat-gebaseerde bestemming voor [!DNL Twitter Tailored Audiences]. In dit scenario wordt ervan uitgegaan dat er geen bestaande [!DNL Twitter Tailored Audiences] bestemming is geconfigureerd via uw Adobe-consultant of de klantenservice.

### Stap 1. Verifiëren met [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Voordat u de op een apparaat gebaseerde bestemming kunt toevoegen, moet u Audience Manager en uw [!DNL Twitter Tailored Audiences] account koppelen. Dit doet u als volgt:

1. Meld u aan bij uw account Audience Manager en ga naar **[!DNL Administration > Integrated Accounts]**. Als u een eerder gevormde integratie met een bestemmingsplatform hebt, zou u het in deze pagina moeten zien die. Anders is de pagina leeg.
1. Klik op **[!DNL Add Account]**.
1. Selecteer [!DNL Twitter Tailored Audiences] en klik **[!DNL Confirm]** om naar de authentificatiepagina worden opnieuw geleid.                     ![geïntegreerde platforms](assets/dbd-integrated-platforms.png)
1. Zodra u voor authentiek hebt verklaard, wordt u opnieuw gericht aan de Manager van het Publiek waar u uw bijbehorende adverteerderrekeningen zou moeten zien. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!DNL Confirm]**.

### Stap 2. Een nieuwe op apparaten gebaseerde bestemming maken {#step2-create-new-destination}

Nadat u Audience Manager en uw [!DNL Twitter Tailored Audiences]aan elkaar hebt gekoppeld, kunt u de nieuwe bestemming tot stand brengen. Dit doet u als volgt:

>[!NOTE]
>
>U kunt de naam van een bestaand op apparaat gebaseerd doel niet wijzigen. Zorg ervoor om een naam te verstrekken die u zal helpen de bestemming correct identificeren.

1. Meld u aan bij uw account Audience Manager, ga naar **[!DNL Audience Data > Destinations]**, en klik op **[!DNL Create Destination]**.
1. Voer in de **[!DNL Basic Information]** sectie een **[!DNL Name]** en **[!DNL Description]** voor uw nieuwe bestemming in en gebruik de onderstaande instellingen: ![instellen](assets/dbd-new-basic.png)
1. Klik op **[!DNL Next]**.
1. Kies de labels voor [gegevensexport](/help/using/features/data-export-controls.md#controls-labels) die u voor dit doel wilt instellen.
1. Klik op **[!DNL Save]**.
1. Selecteer in de **[!DNL Segment Mappings]** sectie de publiekssegmenten die u naar deze bestemming wilt verzenden.
1. Sla het doel op.

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## Overwegingen bij het toewijzen van segmenten {#segment-mapping-considerations}

Wanneer het in kaart brengen van publiekssegmenten aan [!UICONTROL Twitter], zorg ervoor om aan de volgende segment noemende vereisten te voldoen:

* Verstrek de mens-leesbare namen van de segmentafbeelding. Wij adviseren gebruikend de zelfde naam die u voor de segmenten van de Manager van de Publiek gebruikte.
* Gebruik geen speciale tekens (`,``%` `:``;` `@` `/``=` `?` `$`) in segment- en segmenttoewijzingsnamen. Als uw het segmentnaam van de Manager van de Publiek deze karakters bevat, te verwijderen gelieve hen alvorens het segment aan een [!UICONTROL Twitter] bestemming toe te wijzen.

### Voorbeeld

* Segment- of toewijzingsnaam corrigeren: &quot;Amerikaanse en Europese kopers&quot;;
* Onjuiste segment- of toewijzingsnaam: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>U kunt de namen van al toegewezen segmenten niet wijzigen. De Manager van het publiek gebruikt de segmentnamen om de segmenten in de integratie correct te identificeren.

## Aandachtspunten {#match-rates-considerations}

* Bij gebruik [!UICONTROL Twitter Tailored Audiences]worden op de doelpagina geen waarden weergegeven voor de waarden [!UICONTROL Segment Addressable Audience] en [!UICONTROL Segment Match Rate] metriek. Dit is normaal gedrag, aangezien de publiek die samen met de gelijke tarieven voor deze bestemming aanpassen worden behandeld en ontvangen door, [!UICONTROL Twitter]niet Adobe.
* Momenteel ondersteunt de integratie tussen Audience Manager en [!UICONTROL Twitter Tailored Audiences] geen historische publieksbackfills. Dit betekent dat alleen de segmentkwalificaties die *nadat* het segment is toegewezen aan een Twitter-bestemming, in real-time worden verzonden [!UICONTROL Twitter] naar.
