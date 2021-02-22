---
description: 'Deze pagina omvat geleidelijke begeleiding op hoe te om off-line gegevens van CRM met gedragsgegevens te combineren die u reeds in Audience Manager hebt om nieuwe publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar Op mensen-Gebaseerde Doelen te verzenden.  '
seo-description: 'Deze pagina omvat geleidelijke begeleiding op hoe te om off-line gegevens van CRM met gedragsgegevens te combineren die u reeds in Audience Manager hebt om nieuwe publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar Op mensen-Gebaseerde Doelen te verzenden.   '
seo-title: Workflow A - Personalisatie gebaseerd op alle online activiteiten gecombineerd met offline data
solution: Audience Manager
title: Workflow A - Personalisatie gebaseerd op alle online activiteiten gecombineerd met offline data
feature: Persoonsgebaseerde bestemmingen
translation-type: tm+mt
source-git-commit: 6e3a06da8149c91a9192b5b3ee582e46fbb1790c
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 7%

---


# Workflow A - Personalisatie gebaseerd op alle online activiteiten gecombineerd met offline data {#workflow-a}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina omvat geleidelijke begeleiding op hoe te om off-line [!DNL CRM] gegevens met gedragsgegevens te combineren die u reeds in Audience Manager hebt om nieuwe publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar [!DNL People-Based Destinations] te verzenden.

## Stap 1 - vorm de Montages van de Gegevensbron {#configure-data-source-settings}

Afhankelijk van het feit of uw [DPUUIDs](../../reference/ids-in-aam.md) kleine letters zijn, gehakt e-mailadressen, zou u de gegevensbron kunnen moeten vormen die de gehakte e-mailadressen zal opslaan.

 

**Scenario 1: uw  [](../../reference/ids-in-aam.md) DPUUIDsare reeds kleine -, gehakte e-mailadressen.**

In dit geval moet u de overeenkomstige gegevensbron als dusdanig etiketteren:

1. Ga naar [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Zoek de gegevensbron die uw [DPUUIDs](../../reference/ids-in-aam.md) bevat, en klik het.
1. Selecteer **[!UICONTROL Cross Device]** in het vervolgkeuzemenu **[!UICONTROL ID Type]**.
1. Controleer of de optie [!UICONTROL Cannot be tied to personally identifiable information] is uitgeschakeld.
1. Selecteer in de sectie **[!UICONTROL Data Source Settings]** zowel de opties **[!UICONTROL Inbound]** als **[!UICONTROL Outbound]** en schakel de optie **[!UICONTROL Share associated cross-device IDs in people-based destinations]** in.
1. Gebruik het drop-down menu om het **[!UICONTROL Emails(SHA256, lowercased)]** etiket voor deze gegevensbron te selecteren.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. De Audience Manager hash de gegevens bij deze stap niet. Zorg ervoor dat de e-mailadressen die u bij het opslaan in deze gegevensbron wilt gebruiken, al zijn gehasht met het algoritme [!DNL SHA256]. Anders, zult u niet het voor [!DNL People-Based Destinations] kunnen gebruiken.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Sla de gegevensbroninstellingen op.

 

**Scenario 2: uw  [](../../reference/ids-in-aam.md) DPUUIDs is geen kleine, gehakte e-mailadressen.**

In dit geval moet u een nieuwe gegevensbron voor meerdere apparaten maken waarin uw gehashte e-mailadressen worden opgeslagen. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account, ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** en klik op **[!UICONTROL Add New]**.
1. Voer een [!UICONTROL Name] en [!UICONTROL Description] in voor de nieuwe gegevensbron.
1. Selecteer **[!UICONTROL Cross Device]** in het vervolgkeuzemenu **[!UICONTROL ID Type]**.
1. Selecteer in de sectie **[!UICONTROL Data Source Settings]** zowel de opties **[!UICONTROL Inbound]** als **[!UICONTROL Outbound]** en schakel de optie **[!UICONTROL Share associated cross-device IDs in people-based destinations]** in.
1. Gebruik het drop-down menu om het **[!UICONTROL Emails(SHA256, lowercased)]** etiket voor deze gegevensbron te selecteren.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. De Audience Manager hash de gegevens bij deze stap niet. Zorg ervoor dat de e-mailadressen die u bij het opslaan in deze gegevensbron wilt gebruiken, al zijn gehasht met het algoritme [!DNL SHA256]. Anders, zult u niet het voor [!DNL People-Based Destinations] kunnen gebruiken.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Sla de gegevensbroninstellingen op.

Bekijk de onderstaande video voor een videozelfstudie over het maken van een gegevensbron voor [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Zie [Gegevens aan boord](people-based-destinations-prerequisites.md#data-onboarding) voor vaak gestelde vragen over hoe u uw off-line gegevens in Audience Manager voor op mensen-Gebaseerde Doelen zou moeten brengen.

## Stap 2 - Identiteitskaart van de Gelijke aan Onderbroken E-mailadressen via dossier-Gebaseerde Synchronisatie {#match-ids-emails}

>[!IMPORTANT]
>
> Deze stap is slechts op [hierboven beschreven Scenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) van toepassing. Als uw bestaande [DPUUIDs](../../reference/ids-in-aam.md) reeds gehakt e-mailadressen zijn, overslaan aan [Stap 3 - creeer een Regel van de Fusie van het Profiel voor Segmentatie](people-based-destinations-workflow-combined.md#create-merge-rule).

Stel dat u uw bestaande [DPUUIDs](../../reference/ids-in-aam.md) aan de gehakte e-mailadressen van de lijst hieronder (juiste kolom) wilt aanpassen, en de gehakte e-mailadressen in de nieuwe gegevensbron opslaan die u bij [Stap 1 - vorm de Montages van de Gegevensbron ](people-based-destinations-workflow-combined.md#configure-data-source-settings) creeerde.

| DPUUID (CRM-ID) | E-mailadres | Onderbroken e-mailadres |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 6741268208341199572553870443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

U kunt maximaal 10 gehashte e-mailadressen koppelen aan één [DPUUID](../../reference/ids-in-aam.md). Hiervoor scheidt u de gehashte e-mailadressen met een `<TAB>` in het synchronisatiebestand.

In ons voorbeeld hebt u nu twee gegevensbronnen.

| Gegevensbron-id | Inhoud gegevensbron |
| -------------- | -------------------------- |
| 999999 | Bestaande DPUUID&#39;s (CRM-ID&#39;s) |
| 987654 | Onderbroken e-mailadressen |

 

Uw [ID synchronisatiebestand](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) zou de volgende inhoud hebben:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Het [ID-synchronisatiebestand](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) moet de volgende naamgevingsstructuur volgen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

In het bovenstaande voorbeeld ziet de bestandsnaam er als volgt uit:
`c2c_id_999999_987654_1560431657.sync`

[Download hier](assets/c2c_id_999999_987654_1560431657.sync) een voorbeeldbestand.

Zodra u uw dossier van de synchronisatie van identiteitskaart hebt gecreeerd, moet u het aan een [!DNL Amazon S3] emmertje uploaden. Zie [Batchgegevens verzenden naar Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) voor meer informatie over het uploaden van ID-synchronisatiebestanden.

## Stap 3 - creeer een Regel van de Fusie van het Profiel voor Segmentatie {#create-merge-rule}

De volgende stap is het creëren van een nieuwe fusieregel die u zal helpen de publiekssegmenten tot stand brengen om naar uw op mensen-gebaseerde bestemmingen te verzenden.

>[!IMPORTANT]
>
> Als u al een regel hebt die met [!UICONTROL Current Authenticated Profiles] of [!UICONTROL Last Authenticated Profiles] opties wordt bepaald, kunt u aan [Stap 4 overslaan - creeer de Segmenten van het Publiek](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Klik op **[!UICONTROL Add New Rule]**.
1. Voer een regel **[!UICONTROL Name]** en **[!UICONTROL Description]** voor het samenvoegen van profielen in.
1. Selecteer in de sectie **[!UICONTROL Profile Merge Rule Setup]** de opties **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]**.
1. Selecteer in de lijst **[!UICONTROL Cross-Device Profile Options]** de gegevensbronnen waarop u de segmentatie wilt uitvoeren. Dit moeten de gegevensbronnen zijn die uw bestaande [DPUUIDs](../../reference/ids-in-aam.md) bevatten.

## Stap 4 - creeer de Segmenten van het Publiek {#create-audience-segments}

Om nieuwe publiekssegmenten tot stand te brengen, gebruik [de Bouwer van het Segment](../segments/segment-builder.md). Als u bestaande publiekssegmenten hebt die u aan [!DNL People-Based Destinations] wilt verzenden, overslaan aan [Stap 5 - vorm op mensen-Gebaseerde Authentificatie van het Platform](people-based-destinations-workflow-combined.md#configure-authentication).

## Stap 5 - Vorm op mensen-Gebaseerde Authentificatie {#configure-authentication}

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![op mensen gebaseerde integratie](assets/pbd-config.png)
1. Klik op **[!UICONTROL Add Account]**.
1. Gebruik het vervolgkeuzemenu **[!UICONTROL People-Based Platform]** om het platform te selecteren waarmee u de integratie wilt configureren.
   ![op mensen gebaseerd platform](assets/pbd-add.png)
1. Klik op **[!UICONTROL Confirm]** om te worden omgeleid naar de verificatiepagina van het geselecteerde platform.
1. Nadat u zich hebt geverifieerd op uw account voor het sociale platform, wordt u omgeleid naar de Audience Manager waar de accounts van uw adverteerders moeten worden weergegeven. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]**.
1. Audience Manager geeft boven aan de pagina een melding weer om te laten weten of de account is toegevoegd. Met de melding kunt u ook een contact-e-mailadres toevoegen om meldingen te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

>[!IMPORTANT]
>
>Een manager van het nut behandelt de integratie met sociale platforms door authentificatietokens die na een bepaalde hoeveelheid tijd verlopen. Zie Verificatietokens vernieuwen voor meer informatie over het vernieuwen van de verlopen tokens.

## Stap 6 - creeer een op mensen-gebaseerde Bestemming {#create-destination}

1. Meld u aan bij uw Audience Manager-account, ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** en klik op **[!UICONTROL Create Destination]**.
1. Voer in de sectie **[!UICONTROL Basic Information]** een **[!UICONTROL Name]** en **[!UICONTROL Description]** in voor de nieuwe gegevensbron en gebruik de volgende instellingen:
   * **[!UICONTROL Category]**: geïntegreerde Platforms;
   * **[!UICONTROL Type]**: personen;
   * **[!UICONTROL Platform]**: selecteer het op mensen-gebaseerde platform dat u publiekssegmenten naar wilt verzenden;
   * **[!UICONTROL Account]**: Selecteer het gewenste adverteerderaccount dat aan het geselecteerde platform is gekoppeld.
      ![create-destination](assets/pbd-create-destination.png)
1. Klik op **[!UICONTROL Next]**.
1. Kies de **[!UICONTROL Data Export Labels]** die u voor deze bestemming wilt plaatsen.
1. Selecteer in de sectie **[!UICONTROL Configuration]** de gegevensbron die de gehashte gegevensbronnen bevat.
1. Selecteer in de sectie **[!UICONTROL Segment Mappings]** de segmenten die u naar deze bestemming wilt verzenden. Dit zouden de segmenten zijn die u bij [Stap 4 creeerde - creeer de Segmenten van het Publiek](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Sla het doel op.
