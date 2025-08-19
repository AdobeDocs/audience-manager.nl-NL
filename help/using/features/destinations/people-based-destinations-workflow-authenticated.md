---
description: Deze pagina omvat geleidelijke begeleiding op hoe te om off-line gegevens van CRM met gedragsgegevens in real time voor voor authentiek verklaarde gebruikers te combineren om publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar Op mensen-Gebaseerde Doelen te verzenden.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: Workflow C - Personalization gebaseerd op geverifieerde activiteiten gecombineerd met offlinegegevens
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 0%

---

# Workflow C - Personalization gebaseerd op geverifieerde activiteiten gecombineerd met offlinegegevens {#workflow-c}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina bevat stapsgewijze instructies voor het combineren van offline [!DNL CRM] -gegevens met realtime gedragsgegevens voor geverifieerde gebruikers om publiekssegmenten te maken en deze publiekssegmenten vervolgens naar [!DNL People-Based Destinations] te verzenden.

## Stap 1 - Source-instellingen voor gegevens configureren {#configure-data-source-settings}

Afhankelijk van of uw [ DPUUIDs ](../../reference/ids-in-aam.md) kleine letters zijn, gehakt e-mailadressen, zou u de gegevensbron kunnen moeten vormen die de gehakt e-mailadressen zal opslaan.

 

**Scenario 1: uw [ DPUUIDs ](../../reference/ids-in-aam.md) zijn reeds in kleine letters, gehakt e-mailadressen.**

In dit geval, overslaan aan [ Stap 5 - vorm op mensen-Gebaseerde Authentificatie van het Platform ](#configure-authentication).

 

**Scenario 2: uw [ DPUUIDs ](../../reference/ids-in-aam.md) zijn geen kleine letter, gehakt e-mailadressen.**

In dit geval moet u een nieuwe gegevensbron voor meerdere apparaten maken waarin uw gehashte e-mailadressen worden opgeslagen. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account, ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** en klik op **[!UICONTROL Add New]** .
1. Voer een **[!UICONTROL Name]** en **[!UICONTROL Description]** in voor de nieuwe gegevensbron.
1. Selecteer **[!UICONTROL ID Type]** in de vervolgkeuzelijst **[!UICONTROL Cross Device]** .
1. Selecteer in de sectie **[!UICONTROL Data Source Settings]** zowel de opties **[!UICONTROL Inbound]** als **[!UICONTROL Outbound]** en schakel de optie **[!UICONTROL Share associated cross-device IDs in people-based destinations]** in.
1. Gebruik het vervolgkeuzemenu om het label **[!UICONTROL Emails(SHA256, lowercased)]** voor deze gegevensbron te selecteren.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. Audience Manager hash de gegevens op dit moment niet. Controleer of de e-mailadressen die u wilt opslaan in deze gegevensbron al zijn gehasht met het algoritme [!DNL SHA256] . Anders kunt u deze niet gebruiken voor [!DNL People-Based Destinations] .

   ![ pbd-datasource-settings ](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Zie [ Gegevens onboarding ](people-based-destinations-prerequisites.md#data-onboarding) voor vaak gestelde vragen over hoe u uw off-line gegevens in Audience Manager voor op mensen-Gebaseerde Doelen zou moeten brengen.

Bekijk de onderstaande video voor een videozelfstudie over het maken van een gegevensbron voor [!UICONTROL People-Based Destinations] .

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Stap 2 - Gebruik Gedeclareerde IDs om DPUUIDs aan Onderbroken E-mailadressen via Echte - tijdVraag van HTTP aan te passen {#match-email-addresses}

Om voor authentiek verklaarde gebruikers voor op regel-gebaseerde eigenschappen te kwalificeren, moet u de vakkwalificatie door [ verklaarde IDs ](../declared-ids.md) verzenden.

### Voorbeeld

Stel dat u de volgende twee gegevensbronnen hebt gemaakt.

| Gegevensbron-id | Inhoud gegevensbron |
| -------------- | -------------------------- |
| 999999 | Bestaande DPUUID&#39;s (CRM-ID&#39;s) |
| 987654 | Onderbroken e-mailadressen |

 

Vervolgens wilt u de onderstaande CRM-id&#39;s kwalificeren voor de eigenschap in de tabel.

| DPUUID (CRM-ID) | E-mailadres | Onderbroken e-mailadres | Trait |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 | location = US |

 

Voor de opgegeven id moet deze syntaxis worden gebruikt:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

In het bovenstaande voorbeeld zou de gedeclareerde id-aanroep er als volgt moeten uitzien:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Stap 3 - creeer een Regel van de Fusie van het Profiel voor Segmentatie {#create-profile-merge-rule-segmentation}

De volgende stap bestaat uit het maken van een nieuwe samenvoegregel waarmee u de publiekssegmenten kunt maken die naar uw [!DNL People-Based Destinations] moeten worden verzonden.

>[!IMPORTANT]
>
>Als u reeds een regel hebt die met **[!UICONTROL Current Authenticated Profiles]** wordt bepaald of **[!UICONTROL Last Authenticated Profiles]** opties, kunt u aan [ Stap 4 overslaan - creeer de Segmenten van het Publiek ](#create-audience-segments).

1. Log in bij je Audience Manager account en ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]** .
2. Klik op **[!UICONTROL Add New Rule]**.
3. Voer een regel voor het samenvoegen van profielen in **[!UICONTROL Name]** en **[!UICONTROL Description]** .
4. Selecteer in de sectie **[!UICONTROL Profile Merge Rule Setup]** de regel **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]** in de lijst **[!UICONTROL Cross-Device Options]** .
5. Selecteer in de lijst **[!UICONTROL Cross-Device Profile Options]** de gegevensbronnen waarop u de segmentatie wilt uitvoeren. Dit moeten de gegevensbronnen zijn die uw bestaande DPUUIDs bevatten.
   ![ fusie-regel-opstelling ](assets/pbd-pmr-combined.png)

## Stap 4 - Audience-segmenten maken {#create-audience-segments}

Om nieuwe segmenten tot stand te brengen, gebruik de [ Bouwer van het Segment ](../segments/segment-builder.md). Als u bestaande publiekssegmenten hebt die u aan [!DNL People-Based Destinations] wilt verzenden, overslaan aan [ Stap 5 - vorm op mensen-Gebaseerde Authentificatie van het Platform ](#configure-authentication).

## Stap 5 - Vorm op mensen-Gebaseerde Authentificatie van het Platform {#configure-authentication}

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]** . Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![ op mensen-gebaseerde-integratie ](assets/pbd-config.png)
2. Klik op **[!UICONTROL Add Account]**.
3. Gebruik het vervolgkeuzemenu **[!UICONTROL People-Based Platform]** om het platform te selecteren waarmee u de integratie wilt configureren.
   ![ op mensen-gebaseerd-platform ](assets/pbd-add.png)
4. Klik op **[!UICONTROL Confirm]** om te worden omgeleid naar de verificatiepagina van het geselecteerde platform.
5. Zodra je je hebt geverifieerd op je account bij een sociaal platform, word je doorgestuurd naar Audience Manager waar je de bijbehorende adverteerderaccounts kunt bekijken. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]** .
6. Audience Manager geeft boven aan de pagina een melding weer om aan te geven of de account is toegevoegd. Met de melding kunt u ook een contact-e-mailadres toevoegen om meldingen te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

>[!IMPORTANT]
>
>Audience Manager handelt de integratie met sociale platforms door authentificatietokens af die na een bepaalde hoeveelheid tijd verlopen. Zie Verificatietokens vernieuwen voor meer informatie over het vernieuwen van de verlopen tokens.

## Stap 6 - creeer een op mensen-gebaseerde Bestemming {#create-destination}

1. Meld u aan bij uw Audience Manager-account, ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** en klik op **[!UICONTROL Create Destination]** .
1. Voer in de sectie **[!UICONTROL Basic Information]** een **[!UICONTROL Name]** en **[!UICONTROL Description]** in voor de nieuwe gegevensbron en gebruik de volgende instellingen:
   * **[!UICONTROL Category]**: geïntegreerde platforms;
   * **[!UICONTROL Type]**: op personen gebaseerd;
   * **[!UICONTROL Platform]**: selecteer het op mensen gebaseerde platform waarnaar u publiekssegmenten wilt verzenden;
   * **[!UICONTROL Account]** : selecteer het gewenste adverteerderaccount dat aan het geselecteerde platform is gekoppeld.
     ![ creeer-bestemming ](assets/pbd-create-destination.png)
1. Klik op **[!UICONTROL Next]**.
1. Kies de **[!UICONTROL Data Export Labels]** die u voor dit doel wilt instellen.
1. Selecteer in de sectie **[!UICONTROL Configuration]** de gegevensbron die de gehashte gegevensbronnen bevat.
1. Selecteer in de sectie **[!UICONTROL Segment Mappings]** de segmenten die u naar dit doel wilt verzenden. Dit zou de segmenten zijn die u bij [ Stap 4 creeerde - creeer de Segmenten van het Publiek ](#create-audience-segments).
1. Sla het doel op.
