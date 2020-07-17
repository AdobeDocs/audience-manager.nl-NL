---
description: De Rapportering van het Gebruik van de activiteit helpt u het activiteitengebruik voor uw instantie van de Audience Manager bekijken en volgen, zodat kunt u uw daadwerkelijke gebruik met uw contractuele verplichting vergelijken.
keywords: activity, usage, reporting, commitment
seo-description: De Rapportering van het Gebruik van de activiteit helpt u het activiteitengebruik voor uw instantie van de Audience Manager bekijken en volgen, zodat kunt u uw daadwerkelijke gebruik met uw contractuele verplichting vergelijken.
seo-title: Gebruik van activiteiten rapporteren
solution: Audience Manager
title: Gebruik van activiteiten rapporteren
topic: Activity Usage Reporting
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 5%

---


# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Overzicht {#overview}

Het [!UICONTROL Activity Usage Report] helpt u het gebruik van activiteiten van uw Audience Manager-instantie te zien en te volgen, zodat u een duidelijk beeld krijgt van uw gebruik van activiteiten vergeleken bij uw contractuele verplichting.

Bovendien kunt u de gegevens op elk gewenst moment downloaden voor het bijhouden van records en aangepaste analyses. [!UICONTROL Activity Usage Report]

## Overwegingen {#considerations}

Het [!UICONTROL Activity Usage Report] is beschikbaar aan alle gebruikers van de Audience Manager met [beheerdervoorrechten](edit-account-settings.md).

>[!IMPORTANT]
>
>Het [!UICONTROL Activity Usage Report] toont u de statistieken van het activiteitengebruik van uw instantie van de Audience Manager. Neem contact op met uw Adobe-vertegenwoordiger voor alle vragen over facturering die betrekking hebben op uw gebruik van activiteiten.

## Gevallen gebruiken {#use-cases}

Er zijn twee belangrijke gevallen van gebruik van het [!UICONTROL Activity Usage Report]volgende:

* **Actief gebruik van instance-activiteiten bijhouden op basis van uw verplichting** om activiteiten te gebruiken: De meeste klanten hebben een maandelijkse geschatte activiteitenverplichting per instantie van de Audience Manager, die dan wordt gecumuleerd in een jaarlijkse activiteitenverplichting in alle gevallen. Hoewel dit rapport geen factureringsrapport is, kan het nuttige begeleiding verstrekken over of u het toegewijde activiteitengebruik overschrijdt.
* **Validatie voor implementatiewijzigingen**: Als u onlangs uw implementatie, zoals vestiging [!DNL Adobe Analytics] server-kant het door:sturen, of het veranderen van uw montages van de [!DNL Adobe Target] servervraag hebt bijgewerkt, kan dit rapport u helpen controleren of het nieuwe activiteitenvolume in lijn met uw verwacht activiteitenvolume is.

## Met de [!UICONTROL Activity Usage Report] {#using}

Als u het venster wilt zien, meldt u zich aan bij uw Audience Manager-account en gaat u naar [!UICONTROL Activity Usage Report]> **[!UICONTROL Administration]** **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Vervolgens gebruikt u het **[!UICONTROL Reporting Interval]** filter om het tijdsinterval te selecteren waarvoor het rapport moet worden gegenereerd. U kunt kiezen tussen 30, 60, 90 dagen of een aangepast datumbereik.

Zodra uw rapport laadt, kunt u een onderbreking van uw [!UICONTROL Activities] voor de geselecteerde periode zien.

[!UICONTROL Activities] het totale totaal van alle onsite en externe interacties met Audience Manager definiëren, uitgesplitst in de volgende categorieën:

* **[!UICONTROL Server Calls]**: Alle gegevensverzamelings- of ophaalgebeurtenissen die via websites, servers, e-mail, mobiele toepassingen of andere systemen naar de Audience Manager worden verzonden.
* **[!UICONTROL Pixel Calls](voorheen bekend als[!UICONTROL Impression Server Calls])**: Gegevens die zijn verzameld op advertenties (zoals het impressievolume van een doelplatform) of e-mailimpressies die zijn uitgevoerd op de Audience Manager. Deze vereisen de aanwezigheid van de`d_event`parameter in het vraagkoord.
* **[!UICONTROL On-Boarded Records]**: Unieke verslagen die van uw eigen systeem van het klantenrelatiebeheer (CRM) of andere off-line gegevensdossiers, zoals de verslagen van het vraagcentrum, apparaat IDs, en de voer van douanegegevens van externe gegevensleveranciers worden opgenomen.
* **[!UICONTROL Log File Records]**: Unieke verslagen van logboekdossiers die in Audience Manager van een gericht platform worden opgenomen.

>[!NOTE]
>
>Een unieke record definieert elke afzonderlijke record met gegevens in een bestand dat door Adobe namens een klant van de Audience Manager wordt opgeslagen.

Bovendien kunt u de [!UICONTROL Activity Usage Trends] grafiektypen gebruiken om te schakelen tussen twee typen grafieken.

![aur-ui-grafieken](assets/aur-ui-graphs.png)

U kunt de cursor ook boven een bepaalde datum in de tijdlijn plaatsen om het gedetailleerde gebruik voor die datum te zien.

![aur-hover](assets/aur-hover.png)

## Exporteren [!UICONTROL Activity Usage Reports] {#export}

Voor een beter overzicht van het gebruik van uw Audience Manager-activiteiten kunt u het bestand exporteren [!UICONTROL Activity Usage Report] op basis van het type records dat u wilt opnemen.

![automatisch exporteren](assets/aur-export.png)

De **[!UICONTROL Onboarded Records Breakdown]** en **[!UICONTROL Onsite Server Calls Breakdown]** rapporten bieden het meest gedetailleerde inzicht in de brongegevens die voor deze activiteiten beschikbaar zijn. Het volume dat aan deze uitsplitsingen wordt toegewezen is gebaseerd op uw implementatie.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Dit rapport bevat niet-geregistreerde records uitgesplitst naar gegevensbron.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Dit rapport bevat een verdeling van servervraag uit drie bronnen: [!UICONTROL Analytics], [!UICONTROL Target]en [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Dit zijn factureerbare servervraag die van alle [!UICONTROL Adobe Analytics] instanties tot Audience Manager, met inbegrip van server-zijdoor:sturen wordt overgegaan. De secundaire servervraag of dubbele servervraag (zoals in het geval van server zijdoor:sturen van veelvoudige rapportreeksen) zijn geen factureerbare activiteiten, zodat zij niet inbegrepen in deze mislukking zijn.
* **[!UICONTROL Target]**: Dit zijn server-zijvraag van [!UICONTROL Adobe Target] aan Audience Manager, om de gegevens van het het segmentsegment van de Audience Manager als deel van een server-aan-server integratie terug te winnen.
* **[!UICONTROL Other]**: Omvat vraag van een andere website of systeem (partnerplaatsen, directe servervraag, enz.), mobiele browser/app vraag via [!DNL SDK], [!DNL DIL], gebeurtenisvraag, en [!DNL DCS] vraag. Omvat ook vraag van [!DNL Target] als opstelling als koekjesintegratie (eerder dan server-aan-server).
