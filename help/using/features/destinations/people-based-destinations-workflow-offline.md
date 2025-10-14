---
description: Deze pagina omvat geleidelijke begeleiding op hoe te om publiekssegmenten van off-line-enige klantengegevens te bouwen, en hen te verzenden naar op mensen-Gebaseerde Doelen.
seo-description: This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.
seo-title: Workflow B - Personalization Based on Offline-Only Data
solution: Audience Manager
title: Workflow B - Personalization gebaseerd op gegevens die alleen offline beschikbaar zijn
feature: People-based Destinations
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---

# Workflow B - Personalization gebaseerd op gegevens die alleen offline beschikbaar zijn {#workflow-b}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina omvat geleidelijke begeleiding op hoe te om publiekssegmenten van off-line-enige klantengegevens te bouwen, en hen te verzenden naar op mensen-Gebaseerde Doelen.

## Stap 1 - Offline treinreizen {#step-1-onboard-traits}

De eerste stap die publiekssegmenten in dit scenario tot stand brengt is uw off-line klantengegevens in Audience Manager te brengen.

>[!IMPORTANT]
>
> Alvorens verder te gaan, zorg ervoor dat de klantenactiviteit die u op het punt staat aan boord reeds in Audience Manager met het overeenkomstige [&#x200B; wordt bepaald onbaardeigenschappen &#x200B;](../traits/trait-and-segment-qualification-reference.md).

Ongeacht of uw bestaande klant IDs van Audience Manager ([&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md)) gehashed e-mails of niet zijn, moet u het bezit op het instappen tegen de gegevensbron uitvoeren die uw [&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md) bevat.

### Voorbeeld

U wilt de klant-id&#39;s uit de onderstaande tabel kwalificeren voor de bijbehorende onbeheerde handels-id&#39;s. Denk eraan dat uw [&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md) in een gegevensbron met identiteitskaart 999999 wordt opgeslagen, en uw gegevensbronidentiteitskaart van Audience Manager is 123.

| Customer ID (DPUUID) | Aan boord genomen Trait ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345 2345 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

Om de klant IDs in het voorbeeld hierboven voor de overeenkomstige onboded eigenschappen te kwalificeren, moet u een [&#x200B; binnenkomend gegevensbestand &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) met de volgende inhoud uploaden:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

De bestandsnaam zou er als volgt uitzien: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Zie [&#x200B; Amazon S3 Naam en de Vereisten van de Grootte van het Dossier voor de Binnenkomende Dossiers van Gegevens &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) voor gedetailleerde informatie over de dossier - noem structuur.

## Stap 2 - Source-instellingen voor gegevens configureren {#configure-data-source-settings}

Afhankelijk van of uw [&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md) kleine letters zijn, gehakt e-mailadressen, zou u de gegevensbron kunnen moeten vormen die de gehakt e-mailadressen zal opslaan.

 

**Scenario 1: uw [&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md) zijn reeds in kleine letters, gehakt e-mailadressen.**

In dit geval moet u de overeenkomstige gegevensbron als dusdanig etiketteren:

1. Ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** .
1. Vind de gegevensbron die uw [&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md) bevat, en klik het.
1. Controleer of de optie **[!UICONTROL Cannot be tied to personally identifiable information]** is uitgeschakeld.
1. Sla de gegevensbroninstellingen op.

 

**Scenario 2: uw [&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md) zijn geen kleine letter, gehakt e-mailadressen.**

In dit geval moet u een nieuwe gegevensbron voor meerdere apparaten maken waarin uw gehashte e-mailadressen worden opgeslagen. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account, ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** en klik op **[!UICONTROL Add New]** .
1. Voer een **[!UICONTROL Name]** en **[!UICONTROL Description]** in voor de nieuwe gegevensbron.
1. Selecteer **[!UICONTROL ID Type]** in de vervolgkeuzelijst **[!UICONTROL Cross Device]** .
1. Selecteer in de sectie **[!UICONTROL Data Source Settings]** zowel de opties **[!UICONTROL Inbound]** als **[!UICONTROL Outbound]** en schakel de optie **[!UICONTROL Share associated cross-device IDs in people-based destinations]** in.
1. Gebruik het vervolgkeuzemenu om het label **[!UICONTROL Emails(SHA256, lowercased)]** voor deze gegevensbron te selecteren.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. Audience Manager hash de gegevens op dit moment niet. Controleer of de e-mailadressen die u wilt opslaan in deze gegevensbron al zijn gehasht met het algoritme [!DNL SHA256] . Anders kunt u deze niet gebruiken voor [!DNL People-Based Destinations] .

   ![&#x200B; pbd-datasource-settings &#x200B;](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Zie [&#x200B; Gegevens onboarding &#x200B;](people-based-destinations-prerequisites.md#data-onboarding) voor vaak gestelde vragen over hoe u uw off-line gegevens in Audience Manager voor op mensen-Gebaseerde Doelen zou moeten brengen.

Bekijk de onderstaande video voor een videozelfstudie over het maken van een gegevensbron voor [!UICONTROL People-Based Destinations] .

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Stap 3 - Identiteitskaart van de Gelijke aan Onderbroken E-mailadressen via dossier-Gebaseerde Synchronisatie van identiteitskaart {#match-ids-emails}

>[!IMPORTANT]
>
> Deze stap is slechts op [&#x200B; hierboven beschreven Scenario 2 van toepassing &#x200B;](people-based-destinations-workflow-offline.md#configure-data-source-settings). Als uw bestaande [&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md) reeds gehakt e-mailadressen zijn, overslaan aan [&#x200B; Stap 4 - creeer een Regel van de Fusie van het Profiel voor Segmentatie &#x200B;](#create-profile-merge-rule).

Laten wij zeggen u uw bestaande [&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md) van het voorbeeld bij Stap 1 aan de gehakte e-mailadressen van de lijst hieronder (juiste kolom) wilt aanpassen, en de gehakte e-mailadressen in de nieuwe gegevensbron opslaan die u bij [&#x200B; Stap 2 creeerde - vorm de Montages van Source van Gegevens &#x200B;](#configure-data-source-settings).

Ter herinnering: u hebt nu twee gegevensbronnen:

| Gegevensbron-id | Inhoud gegevensbron |
| -------------- | -------------------------- |
| 999999 | Bestaande DPUUID&#39;s (CRM-ID&#39;s) |
| 987654 | Onderbroken e-mailadressen |

| DPUUID&#39;s (CRM-ID&#39;s) | E-mailadres | Onderbroken e-mailadres |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

In ons voorbeeld, zou uw [&#x200B; dossier van de synchronisatie van identiteitskaart &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de volgende inhoud hebben:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Het [&#x200B; dossier van de synchronisatie van identiteitskaart &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) moet deze noemende structuur volgen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

In het bovenstaande voorbeeld ziet de bestandsnaam er als volgt uit:
`c2c_id_999999_987654_1560431657.sync`

[&#x200B; Download voorbeelddossier hier &#x200B;](assets/c2c_id_999999_987654_1560431657.sync).

Nadat u het bestand voor id-synchronisatie hebt gemaakt, moet u het uploaden naar een [!DNL Amazon S3] emmertje. Leren hoe te om de synchronisatiedossiers van identiteitskaart te uploaden, zie [&#x200B; de Gegevens van de Partij naar Audience Manager &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) verzenden.

## Stap 4 - creeer een Regel van de Fusie van het Profiel voor Segmentatie {#create-profile-merge-rule}

De volgende stap bestaat uit het maken van een nieuwe samenvoegregel waarmee u de publiekssegmenten kunt maken die naar uw [!DNL People-Based Destinations] moeten worden verzonden.

1. Log in bij je Audience Manager account en ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]** .
2. Klik op [!UICONTROL Add New Rule].
3. Voer een regel voor het samenvoegen van profielen in **[!UICONTROL Name]** en **[!UICONTROL Description]** .
4. Selecteer in de sectie **[!UICONTROL Profile Merge Rule Setup]** de regel **[!UICONTROL All Cross-Device Profiles]** in de lijst **[!UICONTROL Cross-Device Options]** .
5. Selecteer in de lijst **[!UICONTROL Cross-Device Profile Options]** de gegevensbron waartegen uw kenmerken zijn beveiligd.
   ![&#x200B; fusie-regel-opstelling &#x200B;](assets/pbd-pmr.png)

## Stap 5 - Audience-segmenten maken {#create-audience-segments}

Om nieuwe segmenten van off-line-slechts gegevens tot stand te brengen, gebruik de [&#x200B; Bouwer van het Segment &#x200B;](../segments/segment-builder.md) en zorg ervoor u de nieuwe regel van de profielfusie gebruikt die u in de vorige stap creeerde toen het creëren van het segment.

## Stap 6 - Vorm op mensen-Gebaseerde Authentificatie van het Platform {#configure-authentication}

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]** . Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![&#x200B; op mensen-gebaseerde-integratie &#x200B;](assets/pbd-config.png)
1. Klik op **[!UICONTROL Add Account]**.
1. Gebruik het vervolgkeuzemenu **[!UICONTROL People-Based Platform]** om het platform te selecteren waarmee u de integratie wilt configureren.
   ![&#x200B; op mensen-gebaseerd-platform &#x200B;](assets/pbd-add.png)
1. Klik op **[!UICONTROL Confirm]** om te worden omgeleid naar de verificatiepagina van het geselecteerde platform.
1. Zodra je je hebt geverifieerd op je account bij een sociaal platform, word je doorgestuurd naar Audience Manager waar je de bijbehorende adverteerderaccounts kunt bekijken. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]** .
1. Audience Manager geeft boven aan de pagina een melding weer om aan te geven of de account is toegevoegd. Met de melding kunt u ook een contact-e-mailadres toevoegen om meldingen te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

>[!IMPORTANT]
>
>Audience Manager handelt de integratie met sociale platforms door authentificatietokens af die na een bepaalde hoeveelheid tijd verlopen. Zie Verificatietokens vernieuwen voor meer informatie over het vernieuwen van de verlopen tokens.

## Stap 7 - creeer een op mensen-gebaseerde Bestemming {#create-destination}

1. Meld u aan bij uw Audience Manager-account, ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** en klik op **[!UICONTROL Create Destination]** .
1. Voer in de sectie **[!UICONTROL Basic Information]** een **[!UICONTROL Name]** en **[!UICONTROL Description]** in voor de nieuwe gegevensbron en gebruik de volgende instellingen:
   * **[!UICONTROL Category]**: geïntegreerde platforms;
   * **[!UICONTROL Type]**: op personen gebaseerd;
   * **[!UICONTROL Platform]**: selecteer het op mensen gebaseerde platform waarnaar u publiekssegmenten wilt verzenden;
   * **[!UICONTROL Account]** : selecteer het gewenste adverteerderaccount dat aan het geselecteerde platform is gekoppeld.
     ![&#x200B; creeer-bestemming &#x200B;](assets/pbd-create-destination.png)
1. Klik op **[!UICONTROL Next]**.
1. Kies de **[!UICONTROL Data Export Labels]** die u voor dit doel wilt instellen.
1. Selecteer in de sectie **[!UICONTROL Configuration]** de gegevensbron die de gehashte gegevensbronnen bevat.
1. Selecteer in de sectie **[!UICONTROL Segment Mappings]** de segmenten die u naar dit doel wilt verzenden. Dit zou de segmenten zijn die u bij [&#x200B; Stap 5 creeerde - creeer de Segmenten van het Publiek &#x200B;](people-based-destinations-workflow-offline.md#create-audience-segments).
1. Sla het doel op.
