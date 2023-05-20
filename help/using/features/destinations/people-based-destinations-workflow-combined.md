---
description: Deze pagina omvat geleidelijke begeleiding op hoe te om off-line gegevens van CRM met gedragsgegevens te combineren die u reeds in Audience Manager hebt om nieuwe publiekssegmenten tot stand te brengen, dan deze publiekssegmenten naar Op mensen-Gebaseerde Doelen te verzenden.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: Workflow A - Personalisatie gebaseerd op alle online activiteiten gecombineerd met offline data
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 6%

---

# Workflow A - Personalisatie gebaseerd op alle online activiteiten gecombineerd met offline data {#workflow-a}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina bevat stapsgewijze instructies voor het combineren van offline [!DNL CRM] gegevens met gedragsgegevens die u reeds in Audience Manager hebt om nieuwe publiekssegmenten tot stand te brengen, dan deze publiekssegmenten te verzenden naar [!DNL People-Based Destinations].

## Stap 1 - de Montages van de Gegevensbron vormen {#configure-data-source-settings}

Afhankelijk van of uw [DPUUID&#39;s](../../reference/ids-in-aam.md) Als het om kleine letters gaat, kan het zijn dat u de gegevensbron moet vormen die de gehakte e-mailadressen zal opslaan.

 

**Scenario 1: uw [DPUUID&#39;s](../../reference/ids-in-aam.md) zijn al kleine, gehashte e-mailadressen.**

In dit geval moet u de overeenkomstige gegevensbron als dusdanig etiketteren:

1. Ga naar [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Zoek de gegevensbron die uw [DPUUID&#39;s](../../reference/ids-in-aam.md)en klik erop.
1. In de **[!UICONTROL ID Type]** vervolgkeuzelijst, selecteert u **[!UICONTROL Cross Device]**.
1. Controleer of de optie [!UICONTROL Cannot be tied to personally identifiable information] is uitgeschakeld.
1. In de **[!UICONTROL Data Source Settings]** selecteert u beide **[!UICONTROL Inbound]** en **[!UICONTROL Outbound]** en schakelt u de **[!UICONTROL Share associated cross-device IDs in people-based destinations]** optie.
1. Selecteer in het keuzemenu de optie **[!UICONTROL Emails(SHA256, lowercased)]** label voor deze gegevensbron.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. De Audience Manager hash de gegevens bij deze stap niet. Zorg ervoor dat de e-mailadressen die u wilt opslaan in deze gegevensbron al zijn gehasht met de [!DNL SHA256] algoritme. Anders kunt u deze niet gebruiken [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Sla de gegevensbroninstellingen op.

 

**Scenario 2: uw [DPUUID&#39;s](../../reference/ids-in-aam.md) zijn geen kleine, gehashte e-mailadressen.**

In dit geval moet u een nieuwe gegevensbron voor meerdere apparaten maken waarin uw gehashte e-mailadressen worden opgeslagen. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** en klik op **[!UICONTROL Add New]**.
1. Voer een [!UICONTROL Name] en [!UICONTROL Description] voor uw nieuwe gegevensbron.
1. In de **[!UICONTROL ID Type]** vervolgkeuzelijst, selecteert u **[!UICONTROL Cross Device]**.
1. In de **[!UICONTROL Data Source Settings]** selecteert u beide **[!UICONTROL Inbound]** en **[!UICONTROL Outbound]** en schakelt u de **[!UICONTROL Share associated cross-device IDs in people-based destinations]** optie.
1. Selecteer in het keuzemenu de optie **[!UICONTROL Emails(SHA256, lowercased)]** label voor deze gegevensbron.
   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. De Audience Manager hash de gegevens bij deze stap niet. Zorg ervoor dat de e-mailadressen die u wilt opslaan in deze gegevensbron al zijn gehasht met de [!DNL SHA256] algoritme. Anders kunt u deze niet gebruiken [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Sla de gegevensbroninstellingen op.

Bekijk de onderstaande video voor een videozelfstudie over het maken van een gegevensbron voor [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Zie [Gegevens aan boord](people-based-destinations-prerequisites.md#data-onboarding) voor vaak gestelde vragen over hoe u uw off-line gegevens in Audience Manager voor Op mensen-Gebaseerde Doelen zou moeten brengen.

## Stap 2 - Identiteitskaart van de Gelijke aan Onderbroken E-mailadressen via dossier-Gebaseerde Synchronisatie van identiteitskaart {#match-ids-emails}

>[!IMPORTANT]
>
> Deze stap is alleen van toepassing op [Scenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) hierboven beschreven. Als uw bestaande [DPUUID&#39;s](../../reference/ids-in-aam.md) zijn al gehashte e-mailadressen, sla aan over [Stap 3 - creeer een Regel van de Fusie van het Profiel voor Segmentatie](people-based-destinations-workflow-combined.md#create-merge-rule).

Stel dat u uw bestaande [DPUUID&#39;s](../../reference/ids-in-aam.md) aan de gehakte e-mailadressen van de lijst hieronder (juiste kolom), en sla de gehakte e-mailadressen in de nieuwe gegevensbron op die u creeerde bij [Stap 1 - de Montages van de Gegevensbron vormen](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (CRM-ID) | E-mailadres | Onderbroken e-mailadres |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

U kunt maximaal 10 gehashte e-mailadressen aan één adres koppelen [DPUUID](../../reference/ids-in-aam.md). Hiervoor scheidt u de gehashte e-mailadressen door een `<TAB>`, in het synchronisatiebestand.

In ons voorbeeld hebt u nu twee gegevensbronnen.

| Gegevensbron-id | Inhoud gegevensbron |
| -------------- | -------------------------- |
| 999999 | Bestaande DPUUID&#39;s (CRM-ID&#39;s) |
| 987654 | Onderbroken e-mailadressen |

 

Uw [ID-synchronisatiebestand](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) zou de volgende inhoud hebben:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

De [ID-synchronisatiebestand](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) moet de volgende naamgevingsstructuur volgen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

In het bovenstaande voorbeeld ziet de bestandsnaam er als volgt uit:
`c2c_id_999999_987654_1560431657.sync`

[Voorbeeldbestand hier downloaden](assets/c2c_id_999999_987654_1560431657.sync).

Nadat u het bestand voor id-synchronisatie hebt gemaakt, moet u het uploaden naar een [!DNL Amazon S3] emmertje. Ga voor meer informatie over het uploaden van ID-synchronisatiebestanden naar [Batchgegevens naar Audience Manager verzenden](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Stap 3 - creeer een Regel van de Fusie van het Profiel voor Segmentatie {#create-merge-rule}

De volgende stap is het creëren van een nieuwe fusieregel die u zal helpen de publiekssegmenten tot stand brengen om naar uw op mensen-gebaseerde bestemmingen te verzenden.

>[!IMPORTANT]
>
> Als er al een regel is gedefinieerd met de [!UICONTROL Current Authenticated Profiles] of [!UICONTROL Last Authenticated Profiles] opties, kunt u overslaan naar [Stap 4 - Audience-segmenten maken](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Klik op **[!UICONTROL Add New Rule]**.
1. Een regel voor het samenvoegen van profielen invoeren **[!UICONTROL Name]** en **[!UICONTROL Description]**.
1. In de **[!UICONTROL Profile Merge Rule Setup]** selecteert u de **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]** opties.
1. In de **[!UICONTROL Cross-Device Profile Options]** Selecteer de gegevensbronnen waarop u de segmentatie wilt uitvoeren. Dit moeten de gegevensbronnen zijn die uw bestaande [DPUUID&#39;s](../../reference/ids-in-aam.md).

## Stap 4 - Audience-segmenten maken {#create-audience-segments}

Als u nieuwe publiekssegmenten wilt maken, gebruikt u de opdracht [Segment Builder](../segments/segment-builder.md). Als u bestaande publiekssegmenten hebt waarnaar u wilt verzenden [!DNL People-Based Destinations], ga naar [Stap 5 - Vorm op mensen-Gebaseerde Authentificatie van het Platform](people-based-destinations-workflow-combined.md#configure-authentication).

## Stap 5 - Vorm op mensen-Gebaseerde Authentificatie van het Platform {#configure-authentication}

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![op mensen gebaseerde integratie](assets/pbd-config.png)
1. Klik op **[!UICONTROL Add Account]**.
1. Gebruik de **[!UICONTROL People-Based Platform]** vervolgkeuzelijst om het platform te selecteren waarmee u de integratie wilt configureren.
   ![op mensen gebaseerd platform](assets/pbd-add.png)
1. Klikken **[!UICONTROL Confirm]** om te worden omgeleid naar de authentificatiepagina van het geselecteerde platform.
1. Nadat u zich hebt geverifieerd op uw account voor het sociale platform, wordt u omgeleid naar de Audience Manager waar de accounts van uw adverteerders moeten worden weergegeven. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]**.
1. Audience Manager geeft boven aan de pagina een melding weer om te laten weten of de account is toegevoegd. Met de melding kunt u ook een contact-e-mailadres toevoegen om meldingen te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

>[!IMPORTANT]
>
>Een manager van het nut behandelt de integratie met sociale platforms door authentificatietokens die na een bepaalde hoeveelheid tijd verlopen. Zie Verificatietokens vernieuwen voor meer informatie over het vernieuwen van de verlopen tokens.

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
1. In de **[!UICONTROL Segment Mappings]** selecteert u de segmenten die u naar dit doel wilt verzenden. Dit zouden de segmenten zijn die u bij creeerde [Stap 4 - Audience-segmenten maken](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Sla het doel op.
