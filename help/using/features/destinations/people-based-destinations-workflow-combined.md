---
description: 'Deze pagina omvat geleidelijke begeleiding op hoe te om off-line gegevens van CRM met gedragsgegevens te combineren die u reeds in de Manager van het Publiek hebt om nieuwe publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar Op mensen-Gebaseerde Doelen te verzenden.  '
seo-description: 'Deze pagina omvat geleidelijke begeleiding op hoe te om off-line gegevens van CRM met gedragsgegevens te combineren die u reeds in de Manager van het Publiek hebt om nieuwe publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar Op mensen-Gebaseerde Doelen te verzenden.   '
seo-title: Workflow A - Personalisatie gebaseerd op alle online activiteiten gecombineerd met offlinegegevens
solution: Audience Manager
title: Workflow A - Personalisatie gebaseerd op alle online activiteiten gecombineerd met offlinegegevens
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Workflow A - Personalisatie gebaseerd op alle online activiteiten gecombineerd met offlinegegevens {#workflow-a}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina omvat geleidelijke begeleiding op hoe te om off-line [!DNL CRM] gegevens met gedragsgegevens te combineren die u reeds in de Manager van het Publiek hebt om nieuwe publiekssegmenten tot stand te brengen, dan deze publiekssegmenten te verzenden naar [!DNL People-Based Destinations].

## Stap 1 - de Montages van de Gegevensbron vormen {#configure-data-source-settings}

Afhankelijk van het feit of uw [DPUUIDs](../../reference/ids-in-aam.md) in kleine letters, gehakt e-mailadressen zijn, zou u de gegevensbron kunnen moeten vormen die de gehakte e-mailadressen zal opslaan.

 

**Scenario 1: uw[DPUUIDs](../../reference/ids-in-aam.md)zijn reeds kleine, gehakte e-mailadressen.**

In dit geval moet u de overeenkomstige gegevensbron als dusdanig etiketteren:

1. Ga naar [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Zoek de gegevensbron die uw [DPUUIDs](../../reference/ids-in-aam.md)bevat, en klik het.
1. In the **[!UICONTROL ID Type]** drop-down menu, select **[!UICONTROL Cross Device]**.
1. Controleer of de optie [!UICONTROL Cannot be tied to personally identifiable information] is uitgeschakeld.
1. Selecteer in de **[!UICONTROL Data Source Settings]** sectie zowel de **[!UICONTROL Inbound]** als de **[!UICONTROL Outbound]** opties en schakel de **[!UICONTROL Share associated cross-device IDs in people-based destinations]** optie in.
1. Selecteer het **[!UICONTROL Emails(SHA256, lowercased)]** label voor deze gegevensbron in het keuzemenu.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. Audience Manager verbergt de gegevens bij deze stap niet. Zorg ervoor dat de e-mailadressen die u bij het opslaan in deze gegevensbron wilt opslaan, al met het [!DNL SHA256] algoritme zijn gehasht. Anders kunt u het niet gebruiken voor [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Sla de gegevensbroninstellingen op.

 

**Scenario 2: uw[DPUUIDs](../../reference/ids-in-aam.md)zijn geen kleine, gehakte e-mailadressen.**

In dit geval moet u een nieuwe gegevensbron voor meerdere apparaten maken waarin uw gehashte e-mailadressen worden opgeslagen. Dit doet u als volgt:

1. Meld u aan bij uw account Audience Manager en ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** en klik op **[!UICONTROL Add New]**.
1. Voer een [!UICONTROL Name] en [!UICONTROL Description] voor de nieuwe gegevensbron in.
1. In the **[!UICONTROL ID Type]** drop-down menu, select **[!UICONTROL Cross Device]**.
1. Selecteer in de **[!UICONTROL Data Source Settings]** sectie zowel de **[!UICONTROL Inbound]** als de **[!UICONTROL Outbound]** opties en schakel de **[!UICONTROL Share associated cross-device IDs in people-based destinations]** optie in.
1. Selecteer het **[!UICONTROL Emails(SHA256, lowercased)]** label voor deze gegevensbron in het keuzemenu.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. Audience Manager verbergt de gegevens bij deze stap niet. Zorg ervoor dat de e-mailadressen die u bij het opslaan in deze gegevensbron wilt opslaan, al met het [!DNL SHA256] algoritme zijn gehasht. Anders kunt u het niet gebruiken voor [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Sla de gegevensbroninstellingen op.

Bekijk de onderstaande video voor een videozelfstudie over het maken van een gegevensbron voor [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Zie [Gegevens onboarding](people-based-destinations-prerequisites.md#data-onboarding) voor vaak gestelde vragen over hoe u uw off-line gegevens in de Manager van de Publiek voor Op mensen-Gebaseerde Doelen zou moeten brengen.

## Stap 2 - Identiteitskaart van de Gelijke aan Onderbroken E-mailadressen via dossier-Gebaseerde Synchronisatie van identiteitskaart {#match-ids-emails}

>[!IMPORTANT]
>
> Deze stap is alleen van toepassing op [hierboven beschreven scenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) . Als uw bestaande [DPUUIDs](../../reference/ids-in-aam.md) reeds gehakt e-mailadressen zijn, overslaan aan [Stap 3 - creeer een Regel van de Fusie van het Profiel voor Segmentatie](people-based-destinations-workflow-combined.md#create-merge-rule).

Stel dat u uw bestaande [DPUUIDs](../../reference/ids-in-aam.md) aan de gehakte e-mailadressen van de lijst hieronder (juiste kolom) wilt aanpassen, en de gehakte e-mailadressen in de nieuwe gegevensbron wilt opslaan die u bij [Stap 1 creeerde - de Montages](people-based-destinations-workflow-combined.md#configure-data-source-settings)van de Gegevensbron vormen.

| DPUUID (CRM-ID) | E-mailadres | Onderbroken e-mailadres |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

U kunt maximaal 10 gehashte e-mailadressen koppelen aan één [DPUUID](../../reference/ids-in-aam.md). Hiervoor scheidt u de gehashte e-mailadressen met een komma in het synchronisatiebestand.

In ons voorbeeld hebt u nu twee gegevensbronnen.

| Gegevensbron-id | Inhoud gegevensbron |
| -------------- | -------------------------- |
| 999999 | Bestaande DPUUID&#39;s (CRM-ID&#39;s) |
| 987654 | Onderbroken e-mailadressen |

 

Het synchronisatiebestand [van uw](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) id bevat de volgende inhoud:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Het [id-synchronisatiebestand](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) moet de volgende naamgevingsstructuur hebben:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

In het bovenstaande voorbeeld ziet de bestandsnaam er als volgt uit:
`c2c_id_999999_987654_1560431657.sync`

[Download hier](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)een voorbeeldbestand.

Zodra u uw dossier van de synchronisatie van identiteitskaart hebt gecreeerd, moet u het aan een [!DNL Amazon S3] emmertje uploaden. Zie Batchgegevens [verzenden naar Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)voor meer informatie over het uploaden van ID-synchronisatiebestanden.

## Stap 3 - creeer een Regel van de Fusie van het Profiel voor Segmentatie {#create-merge-rule}

De volgende stap is het creëren van een nieuwe fusieregel die u zal helpen de publiekssegmenten tot stand brengen om naar uw op mensen-gebaseerde bestemmingen te verzenden.

>[!IMPORTANT]
>
> Als u reeds een regel hebt die met de [!UICONTROL Current Authenticated Profiles] of de [!UICONTROL Last Authenticated Profiles] opties wordt bepaald, kunt u aan [Stap 4 overslaan - creeer de Segmenten](people-based-destinations-workflow-combined.md#create-audience-segments)van het Publiek.

1. Meld u aan bij uw account Audience Manager en ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Klik op **[!UICONTROL Add New Rule]**.
1. Voer een regel voor het samenvoegen van profielen in **[!UICONTROL Name]** en **[!UICONTROL Description]**.
1. Selecteer in de **[!UICONTROL Profile Merge Rule Setup]** sectie de **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]** opties.
1. Selecteer in de **[!UICONTROL Cross-Device Profile Options]** lijst de gegevensbronnen waarop u de segmentatie wilt uitvoeren. Dit moeten de gegevensbronnen zijn die uw bestaande [DPUUIDs bevatten](../../reference/ids-in-aam.md).

## Stap 4 - Audience-segmenten maken {#create-audience-segments}

Om nieuwe publiekssegmenten tot stand te brengen, gebruik de Bouwer [van het](../segments/segment-builder.md)Segment. Als u bestaande publiekssegmenten hebt die u wilt verzenden naar [!DNL People-Based Destinations], overslaan aan [Stap 5 - vorm op mensen-Gebaseerde Authentificatie](people-based-destinations-workflow-combined.md#configure-authentication)van het Platform.

## Stap 5 - Vorm op mensen-Gebaseerde Authentificatie van het Platform {#configure-authentication}

1. Meld u aan bij uw account Audience Manager en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![op mensen gebaseerde integratie](assets/pbd-config.png)
1. Klik op **[!UICONTROL Add Account]**.
1. Gebruik het **[!UICONTROL People-Based Platform]** drop-down menu om het platform te selecteren dat u de integratie met wilt vormen.
   ![op mensen gebaseerd platform](assets/pbd-add.png)
1. Klik **[!UICONTROL Confirm]** om naar de authentificatiepagina van het geselecteerde platform worden opnieuw gericht.
1. Nadat u zich hebt aangemeld bij uw account voor het sociale platform, wordt u omgeleid naar Audience Manager waar de accounts van uw adverteerders worden weergegeven. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]**.
1. Audience Manager geeft boven aan de pagina een bericht weer om te laten weten of de account is toegevoegd. Met de melding kunt u ook een contact-e-mailadres toevoegen om meldingen te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

>[!IMPORTANT]
>
>Een manager van het nut behandelt de integratie met sociale platforms door authentificatietokens die na een bepaalde hoeveelheid tijd verlopen. Zie Verificatietokens vernieuwen voor meer informatie over het vernieuwen van de verlopen tokens.

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
1. Selecteer in de **[!UICONTROL Segment Mappings]** sectie de segmenten die u naar dit doel wilt verzenden. Dit zouden de segmenten zijn die u bij [Stap 4 creeerde - creeer de Segmenten](people-based-destinations-workflow-combined.md#create-audience-segments)van het Publiek.
1. Sla het doel op.
