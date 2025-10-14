---
description: Met Activity Usage Reporting kunt u het activiteitengebruik voor uw Audience Manager-exemplaar bekijken en volgen, zodat u uw feitelijke gebruik kunt vergelijken met uw contractuele verplichting.
keywords: activiteit, gebruik, rapportage, toezegging
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: Gebruik van activiteiten rapporteren
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Overzicht {#overview}

Het [!UICONTROL Activity Usage Report] helpt u het gebruik van activiteiten van uw Audience Manager-instantie te zien en te volgen, zodat u een duidelijk beeld krijgt van uw gebruik van activiteiten vergeleken bij uw contractuele verplichting.

Daarnaast kunt u de [!UICONTROL Activity Usage Report] altijd downloaden wanneer dat nodig is, voor het bijhouden van records en aangepaste analyse.

## Overwegingen {#considerations}

[!UICONTROL Activity Usage Report] is beschikbaar aan alle gebruikers van Audience Manager met [&#x200B; beheerdervoorrechten &#x200B;](edit-account-settings.md).

>[!IMPORTANT]
>
>In [!UICONTROL Activity Usage Report] ziet u de statistieken over het gebruik van activiteiten in uw Audience Manager-instantie. Neem contact op met uw Adobe-vertegenwoordiger voor alle vragen over facturering die betrekking hebben op uw gebruik van activiteiten.

## Gevallen gebruiken {#use-cases}

Er zijn twee belangrijke gebruiksgevallen van [!UICONTROL Activity Usage Report]:

* **Volgend daadwerkelijke gebruik van de instantieactiviteit tegen uw verplichting van het activiteitengebruik**: De meeste klanten hebben een maandelijkse geschatte activiteitenverplichting per instantie van Audience Manager, die dan in een jaarlijkse activiteitenverplichting over alle instanties wordt gecumuleerd. Hoewel dit rapport geen factureringsrapport is, kan het nuttige begeleiding verstrekken over of u het toegewijde activiteitengebruik overschrijdt.
* **Bevestiging voor implementatieveranderingen**: Als u onlangs uw implementatie, zoals vestiging [!DNL Adobe Analytics] server-zij door:sturen, of het veranderen van uw [!DNL Adobe Target] montages van de servervraag bijwerkte, kan dit rapport u helpen controleren of het nieuwe activiteitenvolume in lijn met uw verwacht activiteitenvolume is.

## De [!UICONTROL Activity Usage Report] gebruiken {#using}

Als u [!UICONTROL Activity Usage Report] wilt bekijken, meldt u zich aan bij uw Audience Manager-account en gaat u naar **[!UICONTROL Administration]** > **[!UICONTROL Usage]** .

![&#x200B; aur-ui &#x200B;](assets/aur-ui.png)

Gebruik vervolgens het filter **[!UICONTROL Reporting Interval]** om het tijdsinterval te selecteren waarvoor het rapport moet worden gegenereerd. U kunt kiezen tussen 30, 60, 90 dagen of een aangepast datumbereik.

Wanneer uw rapport is geladen, ziet u een uitsplitsing van uw [!UICONTROL Activities] voor de geselecteerde periode.

[!UICONTROL Activities] definieert het totale totaal van alle onsite en externe interacties met Audience Manager, gesplitst in de volgende categorieën:

* **[!UICONTROL Server Calls]**: elke gebeurtenis voor gegevensverzameling of -herstel die via websites, servers, e-mail, mobiele toepassingen of andere systemen naar Audience Manager wordt verzonden.
* **[!UICONTROL Pixel Calls] (vroeger gekend als [!UICONTROL Impression Server Calls])**: Gegevens die uit advertenties (zoals het beeldvolume van een gericht platform) worden verzameld of e-mailimkopvraag die aan Audience Manager wordt gemaakt. Hiervoor is de aanwezigheid van de parameter `d_event` in de queryreeks vereist.
* **[!UICONTROL On-Boarded Records]**: Unieke records die u van uw eigen CRM-systeem (customer relationship management system) of andere offlinegegevensbestanden, zoals callcenter-records, apparaat-id&#39;s en aangepaste gegevensfeeds van externe gegevensleveranciers hebt ingesloten.
* **[!UICONTROL Log File Records]**: Unieke records van logbestanden die vanuit een doelplatform in Audience Manager worden ingevoerd.

>[!NOTE]
>
>Een unieke record definieert elke afzonderlijke record met gegevens in een bestand dat door Adobe namens een Audience Manager-klant wordt opgeslagen.

Bovendien kunt u de grafiektypen van [!UICONTROL Activity Usage Trends] gebruiken om te schakelen tussen twee typen grafieken.

![&#x200B; aur-ui-grafieken &#x200B;](assets/aur-ui-graphs.png)

U kunt de cursor ook boven een bepaalde datum in de tijdlijn plaatsen om het gedetailleerde gebruik voor die datum te zien.

![&#x200B; aur-hover &#x200B;](assets/aur-hover.png)

## Exporteren [!UICONTROL Activity Usage Reports] {#export}

Voor een beter overzicht van het gebruiksniveau van uw Audience Manager-activiteit, kunt u de [!UICONTROL Activity Usage Report] exporteren op basis van het type records dat u wilt opnemen.

![&#x200B; aur-export &#x200B;](assets/aur-export.png)

De rapporten **[!UICONTROL Onboarded Records Breakdown]** en **[!UICONTROL Onsite Server Calls Breakdown]** verschaffen de meest granulaire insight van brongegevens die beschikbaar zijn voor deze activiteiten. Het volume dat aan deze uitsplitsingen wordt toegewezen is gebaseerd op uw implementatie.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Dit rapport bevat niet-geregistreerde records uitgesplitst naar gegevensbron.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Dit rapport bevat een uitsplitsing van serveraanroepen vanuit drie bronnen: [!UICONTROL Analytics] , [!UICONTROL Target] en [!UICONTROL Other] .

* **[!UICONTROL Analytics]**: dit zijn factureerbare serveraanroepen die van alle [!UICONTROL Adobe Analytics] -instanties aan Audience Manager worden doorgegeven, inclusief serververzending. De secundaire servervraag of dubbele servervraag (zoals in het geval van server zijdoor:sturen van veelvoudige rapportreeksen) zijn geen factureerbare activiteiten, zodat zij niet inbegrepen in deze mislukking zijn.
* **[!UICONTROL Target]**: dit zijn serveraanroepen van [!UICONTROL Adobe Target] naar Audience Manager om Audience Manager-segmentgegevens op te halen als onderdeel van een server-naar-server integratie.
* **[!UICONTROL Other]**: omvat aanroepen van andere websites of systemen (partnersites, directe serveraanroepen, enz.), mobiele browser-/app-aanroepen via de aanroepen [!DNL SDK] , [!DNL DIL] , gebeurtenissen en [!DNL DCS] . Omvat ook vraag van [!DNL Target] als opstelling als koekjesintegratie (eerder dan server-aan-server).
