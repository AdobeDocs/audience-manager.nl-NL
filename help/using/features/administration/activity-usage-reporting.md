---
description: De Rapportering van het Gebruik van de activiteit helpt u het activiteitengebruik voor uw instantie van de Audience Manager bekijken en volgen, zodat kunt u uw daadwerkelijke gebruik met uw contractuele verplichting vergelijken.
keywords: activiteit, gebruik, rapportage, toezegging
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: Gebruik van activiteiten rapporteren
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Overzicht {#overview}

Het [!UICONTROL Activity Usage Report] helpt u het gebruik van activiteiten van uw Audience Manager-instantie te zien en te volgen, zodat u een duidelijk beeld krijgt van uw gebruik van activiteiten vergeleken bij uw contractuele verplichting.

Bovendien kunt u de [!UICONTROL Activity Usage Report] waar nodig, voor het bijhouden van registers en aangepaste analyses.

## Overwegingen {#considerations}

De [!UICONTROL Activity Usage Report] is beschikbaar voor alle gebruikers van de Audience Manager met [beheerdersrechten](edit-account-settings.md).

>[!IMPORTANT]
>
>De [!UICONTROL Activity Usage Report] toont u de statistieken van het activiteitengebruik van uw instantie van de Audience Manager. Neem contact op met uw Adobe-vertegenwoordiger voor alle vragen over facturering die betrekking hebben op het gebruik van uw activiteiten.

## Gevallen gebruiken {#use-cases}

Er zijn twee belangrijke gebruiksgevallen van de [!UICONTROL Activity Usage Report]:

* **Actief gebruik van instance-activiteiten bijhouden op basis van de gebruiksverplichting van uw activiteit**: De meeste klanten hebben een maandelijkse geschatte activiteitenverplichting per instantie van de Audience Manager, die dan wordt gecumuleerd in een jaarlijkse activiteitenverplichting in alle gevallen. Hoewel dit rapport geen factureringsrapport is, kan het nuttige begeleiding verstrekken over of u het toegewijde activiteitengebruik overschrijdt.
* **Validatie voor wijzigingen in de implementatie**: Als u onlangs uw implementatie hebt bijgewerkt, zoals het instellen van [!DNL Adobe Analytics] server-kant door:sturen, of het veranderen van uw [!DNL Adobe Target] de montages van de servervraag, kan dit rapport u helpen controleren of het nieuwe activiteitenvolume in overeenstemming met uw verwacht activiteitenvolume is.

## Met de [!UICONTROL Activity Usage Report] {#using}

Als u de [!UICONTROL Activity Usage Report], meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Gebruik vervolgens de **[!UICONTROL Reporting Interval]** filter om het tijdinterval te selecteren om het rapport voor te produceren. U kunt kiezen tussen 30, 60, 90 dagen of een aangepast datumbereik.

Zodra uw rapport laadt, kunt u een onderbreking van uw zien [!UICONTROL Activities] voor de geselecteerde periode.

[!UICONTROL Activities] het totale totaal van alle onsite en externe interacties met Audience Manager definiëren, uitgesplitst in de volgende categorieën:

* **[!UICONTROL Server Calls]**: Alle gegevensverzamelings- of ophaalgebeurtenissen die via websites, servers, e-mail, mobiele toepassingen of andere systemen naar de Audience Manager worden verzonden.
* **[!UICONTROL Pixel Calls](voorheen bekend als [!UICONTROL Impression Server Calls])**: Gegevens die zijn verzameld op advertenties (zoals het impressievolume van een doelplatform) of e-mailimpressies die zijn uitgevoerd op de Audience Manager. Hiervoor is de aanwezigheid van `d_event` in de queryreeks.
* **[!UICONTROL On-Boarded Records]**: Unieke verslagen die van uw eigen systeem van het klantenrelatiebeheer (CRM) of andere off-line gegevensdossiers, zoals de verslagen van het vraagcentrum, apparaat IDs, en de voer van douanegegevens van externe gegevensleveranciers worden opgenomen.
* **[!UICONTROL Log File Records]**: Unieke verslagen van logboekdossiers die in Audience Manager van een gericht platform worden opgenomen.

>[!NOTE]
>
>Een uniek verslag bepaalt elk individueel verslag van gegevens in een dossier dat door Adobe namens een klant van de Audience Manager wordt opgeslagen.

Daarnaast kunt u de opdracht [!UICONTROL Activity Usage Trends] grafiektypen om te schakelen tussen twee grafiektypen.

![aur-ui-grafieken](assets/aur-ui-graphs.png)

U kunt de cursor ook boven een bepaalde datum in de tijdlijn plaatsen om het gedetailleerde gebruik voor die datum te zien.

![aur-hover](assets/aur-hover.png)

## Exporteren [!UICONTROL Activity Usage Reports] {#export}

Voor een beter overzicht van het gebruikte niveau van de activiteit van uw Audience Manager, kunt u uitvoeren [!UICONTROL Activity Usage Report] op basis van het type records dat u wilt opnemen.

![automatisch exporteren](assets/aur-export.png)

De **[!UICONTROL Onboarded Records Breakdown]** en **[!UICONTROL Onsite Server Calls Breakdown]** de rapporten verstrekken het meest gedetailleerde inzicht in brongegevens beschikbaar voor deze activiteiten. Het volume dat aan deze uitsplitsingen wordt toegewezen is gebaseerd op uw implementatie.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Dit rapport bevat niet-geregistreerde records uitgesplitst naar gegevensbron.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Dit rapport bevat een verdeling van servervraag uit drie bronnen: [!UICONTROL Analytics], [!UICONTROL Target], en [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Dit zijn factureerbare servervraag die van allen wordt overgegaan [!UICONTROL Adobe Analytics] instanties aan Audience Manager, met inbegrip van server-kant door:sturen. De secundaire servervraag of dubbele servervraag (zoals in het geval van server zijdoor:sturen van veelvoudige rapportreeksen) zijn geen factureerbare activiteiten, zodat zij niet inbegrepen in deze mislukking zijn.
* **[!UICONTROL Target]**: Dit zijn serveraanroepen van [!UICONTROL Adobe Target] aan Audience Manager, om de gesegmenteerde gegevens van de Audience Manager als deel van een server-aan-server integratie terug te winnen.
* **[!UICONTROL Other]**: Omvat vraag van om het even welke andere website of systeem (partnerplaatsen, directe servervraag, enz.), mobiele browser/app vraag via [!DNL SDK], [!DNL DIL], gebeurtenisaanroepen, en [!DNL DCS] oproepen. Omvat ook vraag van [!DNL Target] indien ingesteld als een cookieintegratie (in plaats van server-naar-server).
