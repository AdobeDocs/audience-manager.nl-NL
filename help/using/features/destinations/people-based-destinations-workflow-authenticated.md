---
description: 'Deze pagina omvat geleidelijke begeleiding op hoe te om off-line gegevens van CRM met gedragsgegevens in real time voor voor authentiek verklaarde gebruikers te combineren om publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar Op mensen-Gebaseerde Doelen te verzenden. '
seo-description: 'Deze pagina omvat geleidelijke begeleiding op hoe te om off-line gegevens van CRM met gedragsgegevens in real time voor voor authentiek verklaarde gebruikers te combineren om publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar Op mensen-Gebaseerde Doelen te verzenden.  '
seo-title: Workflow C - Personalisatie gebaseerd op geverifieerde activiteiten gecombineerd met offlinegegevens
solution: Audience Manager
title: Workflow C - Personalisatie gebaseerd op geverifieerde activiteiten gecombineerd met offlinegegevens
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Workflow C - Personalisatie gebaseerd op geverifieerde activiteiten gecombineerd met offlinegegevens {#workflow-c}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina omvat geleidelijke begeleiding op hoe te om off-line [!DNL CRM] gegevens met gedragsgegevens in real time voor voor voor authentiek verklaarde gebruikers te combineren om publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar [!DNL People-Based Destinations].

## Stap 1 - de Montages van de Gegevensbron vormen {#configure-data-source-settings}

Afhankelijk van het feit of uw [DPUUIDs](../../reference/ids-in-aam.md) in kleine letters, gehakt e-mailadressen zijn, zou u de gegevensbron kunnen moeten vormen die de gehakte e-mailadressen zal opslaan.

 

**Scenario 1: uw[DPUUIDs](../../reference/ids-in-aam.md)zijn reeds kleine, gehakte e-mailadressen.**

In dit geval, sla aan [Stap 5 over - vorm op mensen-Gebaseerde Authentificatie](#configure-authentication)van het Platform.

 

**Scenario 2: uw[DPUUIDs](../../reference/ids-in-aam.md)zijn geen kleine, gehakte e-mailadressen.**

In dit geval moet u een nieuwe gegevensbron voor meerdere apparaten maken waarin uw gehashte e-mailadressen worden opgeslagen. Dit doet u als volgt:

1. Meld u aan bij uw account Audience Manager en ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** en klik op **[!UICONTROL Add New]**.
1. Voer een **[!UICONTROL Name]** en **[!UICONTROL Description]** voor de nieuwe gegevensbron in.
1. In the **[!UICONTROL ID Type]** drop-down menu, select **[!UICONTROL Cross Device]**.
1. Selecteer in de **[!UICONTROL Data Source Settings]** sectie zowel de **[!UICONTROL Inbound]** als de **[!UICONTROL Outbound]** opties en schakel de **[!UICONTROL Share associated cross-device IDs in people-based destinations]** optie in.
1. Selecteer het **[!UICONTROL Emails(SHA256, lowercased)]** label voor deze gegevensbron in het keuzemenu.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. Audience Manager verbergt de gegevens bij deze stap niet. Zorg ervoor dat de e-mailadressen die u bij het opslaan in deze gegevensbron wilt opslaan, al met het [!DNL SHA256] algoritme zijn gehasht. Anders kunt u het niet gebruiken voor [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Zie [Gegevens onboarding](people-based-destinations-prerequisites.md#data-onboarding) voor vaak gestelde vragen over hoe u uw off-line gegevens in de Manager van de Publiek voor Op mensen-Gebaseerde Doelen zou moeten brengen.

Bekijk de onderstaande video voor een videozelfstudie over het maken van een gegevensbron voor [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Stap 2 - Gebruik Gedeclareerde IDs om DPUUIDs aan Onderbroken E-mailadressen via Echte - tijdVraag van HTTP aan te passen {#match-email-addresses}

Om voor authentiek verklaarde gebruikers voor op regel-gebaseerde eigenschappen te kwalificeren, moet u de vakkwalificatie door [verklaarde IDs](../declared-ids.md)verzenden.

### Voorbeeld

Stel dat u de volgende twee gegevensbronnen hebt gemaakt.

| Gegevensbron-id | Inhoud gegevensbron |
| -------------- | -------------------------- |
| 999999 | Bestaande DPUUID&#39;s (CRM-ID&#39;s) |
| 987654 | Onderbroken e-mailadressen |

 

Vervolgens wilt u de onderstaande CRM-id&#39;s kwalificeren voor de eigenschap in de tabel.

| DPUUID (CRM-ID) | E-mailadres | Onderbroken e-mailadres | Trait |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

Voor de opgegeven id moet deze syntaxis worden gebruikt:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

In het bovenstaande voorbeeld zou de gedeclareerde id-aanroep er als volgt moeten uitzien:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Stap 3 - creeer een Regel van de Fusie van het Profiel voor Segmentatie {#create-profile-merge-rule-segmentation}

De volgende stap is het creëren van een nieuwe fusieregel die u zal helpen de publiekssegmenten tot stand brengen om naar uw [!DNL People-Based Destinations]te verzenden.

>[!IMPORTANT]
>
>Als u reeds een regel hebt die met de **[!UICONTROL Current Authenticated Profiles]** of de **[!UICONTROL Last Authenticated Profiles]** opties wordt bepaald, kunt u aan [Stap 4 overslaan - creeer de Segmenten](#create-audience-segments)van het Publiek.

1. Meld u aan bij uw account voor Audience Manager en ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Klik op **[!UICONTROL Add New Rule]**.
3. Voer een regel voor het samenvoegen van profielen in **[!UICONTROL Name]** en **[!UICONTROL Description]**.
4. Selecteer in de **[!UICONTROL Profile Merge Rule Setup]** sectie de **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]** regel in de **[!UICONTROL Cross-Device Options]** lijst.
5. Selecteer in de **[!UICONTROL Cross-Device Profile Options]** lijst de gegevensbronnen waarop u de segmentatie wilt uitvoeren. Dit moeten de gegevensbronnen zijn die uw bestaande DPUUIDs bevatten.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Stap 4 - Audience-segmenten maken {#create-audience-segments}

Als u nieuwe segmenten wilt maken, gebruikt u de [Segmentbouwer](../segments/segment-builder.md). Als u bestaande publiekssegmenten hebt die u wilt verzenden naar [!DNL People-Based Destinations], overslaan aan [Stap 5 - vorm op mensen-Gebaseerde Authentificatie](#configure-authentication)van het Platform.

## Stap 5 - Vorm op mensen-Gebaseerde Authentificatie van het Platform {#configure-authentication}

1. Meld u aan bij uw account Audience Manager en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![op mensen gebaseerde integratie](assets/pbd-config.png)
2. Klik op **[!UICONTROL Add Account]**.
3. Gebruik het **[!UICONTROL People-Based Platform]** drop-down menu om het platform te selecteren dat u de integratie met wilt vormen.
   ![op mensen gebaseerd platform](assets/pbd-add.png)
4. Klik **[!UICONTROL Confirm]** om naar de authentificatiepagina van het geselecteerde platform worden opnieuw gericht.
5. Nadat u zich hebt aangemeld bij uw account voor het sociale platform, wordt u omgeleid naar Audience Manager waar de accounts van uw adverteerders worden weergegeven. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]**.
6. Audience Manager geeft boven aan de pagina een bericht weer om te laten weten of de account is toegevoegd. Met de melding kunt u ook een contact-e-mailadres toevoegen om meldingen te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

>[!IMPORTANT]
>
>De Manager van de publiek behandelt de integratie met sociale platforms door authentificatietokens die na een bepaalde hoeveelheid tijd verlopen. Zie Verificatietokens vernieuwen voor meer informatie over het vernieuwen van de verlopen tokens.

## Stap 6 - creeer een op mensen-gebaseerde Bestemming {#create-destination}

1. Meld u aan bij uw account Audience Manager, ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** en klik op **[!UICONTROL Create Destination]**.
1. Voer in de **[!UICONTROL Basic Information]** sectie een **[!UICONTROL Name]** en een **[!UICONTROL Description]** waarde in voor de nieuwe gegevensbron en gebruik de volgende instellingen:
   * **[!UICONTROL Category]**: geïntegreerde platforms;
   * **[!UICONTROL Type]**: personen;
   * **[!UICONTROL Platform]**: selecteer het op mensen-gebaseerde platform dat u publiekssegmenten naar wilt verzenden;
   * **[!UICONTROL Account]**: Selecteer het gewenste adverteerderaccount dat aan het geselecteerde platform is gekoppeld.
      ![create-destination](assets/pbd-create-destination.png)
1. Klik op **[!UICONTROL Next]**.
1. Kies de **[!UICONTROL Data Export Labels]** waarde die u voor deze bestemming wilt instellen.
1. Selecteer in de **[!UICONTROL Configuration]** sectie de gegevensbron die de gehashte gegevensbronnen bevat.
1. Selecteer in de **[!UICONTROL Segment Mappings]** sectie de segmenten die u naar dit doel wilt verzenden. Dit zouden de segmenten zijn die u bij [Stap 4 creeerde - creeer de Segmenten](#create-audience-segments)van het Publiek.
1. Sla het doel op.
