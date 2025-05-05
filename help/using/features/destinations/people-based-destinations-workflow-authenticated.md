---
description: Deze pagina omvat geleidelijke begeleiding op hoe te om off-line gegevens van CRM met gedragsgegevens in real time voor voor authentiek verklaarde gebruikers te combineren om publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar Op mensen-Gebaseerde Doelen te verzenden.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: Workflow C - Personalisatie gebaseerd op geverifieerde activiteit gecombineerd met offline data
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 4%

---

# Workflow C - Personalisatie gebaseerd op geverifieerde activiteit gecombineerd met offline data {#workflow-c}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina bevat stapsgewijze instructies voor het combineren van offline [!DNL CRM] gegevens met gedragsgegevens in real time voor geverifieerde gebruikers om publiekssegmenten te maken en deze publiekssegmenten vervolgens naar [!DNL People-Based Destinations].

## Stap 1 - de Montages van de Gegevensbron vormen {#configure-data-source-settings}

Afhankelijk van of uw [DPUUID&#39;s](../../reference/ids-in-aam.md) Als het om kleine letters gaat, kan het zijn dat u de gegevensbron moet vormen die de gehakte e-mailadressen zal opslaan.

 

**Scenario 1: uw [DPUUID&#39;s](../../reference/ids-in-aam.md) zijn al kleine, gehashte e-mailadressen.**

In dit geval gaat u verder met [Stap 5 - Vorm op mensen-Gebaseerde Authentificatie van het Platform](#configure-authentication).

 

**Scenario 2: uw [DPUUID&#39;s](../../reference/ids-in-aam.md) zijn geen kleine, gehashte e-mailadressen.**

In dit geval moet u een nieuwe gegevensbron voor meerdere apparaten maken waarin uw gehashte e-mailadressen worden opgeslagen. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** en klik op **[!UICONTROL Add New]**.
1. Voer een **[!UICONTROL Name]** en **[!UICONTROL Description]** voor uw nieuwe gegevensbron.
1. In de **[!UICONTROL ID Type]** vervolgkeuzelijst, selecteert u **[!UICONTROL Cross Device]**.
1. In de **[!UICONTROL Data Source Settings]** selecteert u beide **[!UICONTROL Inbound]** en **[!UICONTROL Outbound]** en schakelt u de **[!UICONTROL Share associated cross-device IDs in people-based destinations]** optie.
1. Selecteer in het keuzemenu de optie **[!UICONTROL Emails(SHA256, lowercased)]** label voor deze gegevensbron.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. De Audience Manager hash de gegevens bij deze stap niet. Zorg ervoor dat de e-mailadressen die u wilt opslaan in deze gegevensbron al zijn gehasht met de [!DNL SHA256] algoritme. Anders kunt u deze niet gebruiken [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Zie [Gegevens aan boord](people-based-destinations-prerequisites.md#data-onboarding) voor vaak gestelde vragen over hoe u uw off-line gegevens in Audience Manager voor Op mensen-Gebaseerde Doelen zou moeten brengen.

Bekijk de onderstaande video voor een videozelfstudie over het maken van een gegevensbron voor [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Stap 2 - Gebruik Gedeclareerde IDs om DPUUIDs aan Onderbroken E-mailadressen via Echte - tijdVraag van HTTP aan te passen {#match-email-addresses}

Om voor authentiek verklaarde gebruikers voor op regel-gebaseerde eigenschappen te kwalificeren, moet u de vakkwalificatie door verzenden [gedeclareerde id&#39;s](../declared-ids.md).

### Voorbeeld

Stel dat u de volgende twee gegevensbronnen hebt gemaakt.

| Gegevensbron-id | Inhoud gegevensbron |
| -------------- | -------------------------- |
| 999999 | Bestaande DPUUID&#39;s (CRM-ID&#39;s) |
| 987654 | Onderbroken e-mailadressen |

 

Vervolgens wilt u de onderstaande CRM-id&#39;s kwalificeren voor de eigenschap in de tabel.

| DPUUID (CRM-ID) | E-mailadres | Onderbroken e-mailadres | Eigenschap |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

Voor de opgegeven id moet deze syntaxis worden gebruikt:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

In het bovenstaande voorbeeld zou de gedeclareerde id-aanroep er als volgt moeten uitzien:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Stap 3 - creeer een Regel van de Fusie van het Profiel voor Segmentatie {#create-profile-merge-rule-segmentation}

De volgende stap is het creëren van een nieuwe fusieregel die u zal helpen de publiekssegmenten tot stand brengen om naar uw te verzenden [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Als er al een regel is gedefinieerd met de **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]** opties, kunt u overslaan naar [Stap 4 - Audience-segmenten maken](#create-audience-segments).

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Klik op **[!UICONTROL Add New Rule]**.
3. Een regel voor het samenvoegen van profielen invoeren **[!UICONTROL Name]** en **[!UICONTROL Description]**.
4. In de **[!UICONTROL Profile Merge Rule Setup]** selecteert u de **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]** van de **[!UICONTROL Cross-Device Options]** lijst.
5. In de **[!UICONTROL Cross-Device Profile Options]** Selecteer de gegevensbronnen waarop u de segmentatie wilt uitvoeren. Dit moeten de gegevensbronnen zijn die uw bestaande DPUUIDs bevatten.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Stap 4 - Audience-segmenten maken {#create-audience-segments}

Als u nieuwe segmenten wilt maken, gebruikt u de opdracht [Segment Builder](../segments/segment-builder.md). Als u bestaande publiekssegmenten hebt waarnaar u wilt verzenden [!DNL People-Based Destinations], ga naar [Stap 5 - Vorm op mensen-Gebaseerde Authentificatie van het Platform](#configure-authentication).

## Stap 5 - Vorm op mensen-Gebaseerde Authentificatie van het Platform {#configure-authentication}

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![op mensen gebaseerde integratie](assets/pbd-config.png)
2. Klik op **[!UICONTROL Add Account]**.
3. Gebruik de **[!UICONTROL People-Based Platform]** vervolgkeuzelijst om het platform te selecteren waarmee u de integratie wilt configureren.
   ![op mensen gebaseerd platform](assets/pbd-add.png)
4. Klikken **[!UICONTROL Confirm]** om te worden omgeleid naar de authentificatiepagina van het geselecteerde platform.
5. Nadat u zich hebt geverifieerd op uw account voor het sociale platform, wordt u omgeleid naar de Audience Manager waar de accounts van uw adverteerders moeten worden weergegeven. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]**.
6. Audience Manager geeft boven aan de pagina een melding weer om te laten weten of de account is toegevoegd. Met de melding kunt u ook een contact-e-mailadres toevoegen om meldingen te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

>[!IMPORTANT]
>
>De Audience Manager behandelt de integratie met sociale platforms door authentificatietokens die na een bepaalde hoeveelheid tijd verlopen. Zie Verificatietokens vernieuwen voor meer informatie over het vernieuwen van de verlopen tokens.

## Stap 6 - creeer een op mensen-gebaseerde Bestemming {#create-destination}

1. Meld u aan bij uw Audience Manager-account, ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** en klik op **[!UICONTROL Create Destination]**.
1. In de **[!UICONTROL Basic Information]** in, voert u een **[!UICONTROL Name]** en **[!UICONTROL Description]** voor uw nieuwe gegevensbron, en gebruik de volgende montages:
   * **[!UICONTROL Category]**: geïntegreerde Platforms;
   * **[!UICONTROL Type]**: personen;
   * **[!UICONTROL Platform]**: selecteer het op mensen-gebaseerde platform dat u publiekssegmenten naar wilt verzenden;
   * **[!UICONTROL Account]**: Selecteer het gewenste adverteerderaccount dat aan het geselecteerde platform is gekoppeld.

      ![create-destination](assets/pbd-create-destination.png)
1. Klik op **[!UICONTROL Next]**.
1. Kies de optie **[!UICONTROL Data Export Labels]** die u voor dit doel wilt instellen.
1. In de **[!UICONTROL Configuration]** selecteert u de gegevensbron die uw gehashte gegevensbronnen bevat.
1. In de **[!UICONTROL Segment Mappings]** selecteert u de segmenten die u naar dit doel wilt verzenden. Dit zouden de segmenten zijn die u bij creeerde [Stap 4 - Audience-segmenten maken](#create-audience-segments).
1. Sla het doel op.
