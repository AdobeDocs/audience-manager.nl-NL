---
description: Tot de onderdelen voor tagbeheer voor Audience Managers behoren het clientportaal, Adobe Tag Manager (afgekeurd ten gunste van Adobe Dynamic Tag Manager en Adobe Experience Platform Launch), DIL, Akamai en de besturingsdatabase.
seo-description: Tot de onderdelen voor tagbeheer voor Audience Managers behoren het clientportaal, Adobe Tag Manager (afgekeurd ten gunste van Adobe Dynamic Tag Manager en Adobe Experience Platform Launch), DIL, Akamai en de besturingsdatabase.
seo-title: Onderdelen voor Tag Management
solution: Audience Manager
title: Onderdelen voor Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 5%

---

# Onderdelen voor Tag Management{#tag-management-components}

Tot de onderdelen voor tagbeheer voor Audience Managers behoren het clientportaal, Adobe Tag Manager (afgekeurd ten gunste van Adobe Dynamic Tag Manager en Adobe Experience Platform Launch), DIL, Akamai en de besturingsdatabase.

<!-- 

c_comptag.xml

 -->

Audience Manager bevat de volgende componenten:

* [Clientportal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-container](../../reference/system-components/components-tag-management.md#dil-tim)
* [Gegevensinformatiebibliotheek (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Besturingsdatabase](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

Het clientportaal is de primaire gebruikersinterface (UI) voor tag- en gegevensbeheer. De klanten gebruiken het portaal om met markeringen te werken, eigenschappen en segmenten te bouwen, opstellingsbestemmingen, en campagneprestaties met rapporten te controleren.

## DIL/TIM-container {#dil-tim}

Met de container [!UICONTROL DIL] kunt u [!DNL Audience Manager] code voor gegevensverzameling op uw website implementeren. [!UICONTROL TIM] is het vervangen van Taginvoegingsbeheer. Het wordt niet meer gebruikt door [!DNL Audience Manager]. In plaats daarvan gebruikt u [Dynamisch tagbeheer](https://docs.adobe.com/content/help/nl-NL/dtm/using/dtm-home.html) of de extensie [!DNL Audience Manager] in [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) om containercode te configureren en te genereren die u op pagina&#39;s in uw overzicht plaatst. De [!UICONTROL DTM]-container werkt met [!UICONTROL Data Information Library (DIL)] om gegevens van uw site te verzamelen en naar [!DNL Audience Manager] te verzenden.

## Data Integration Library (DIL) {#dil}

De [Gegevensinformatiebibliotheek](../../dil/dil-overview.md) (DIL) is een zelfstandige API-module die gegevens van uw website verzamelt. [!UICONTROL DIL] helpt u te voorkomen dat u speciale code hoeft te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens. [!UICONTROL DIL] voert deze acties automatisch uit. Daarnaast is [!UICONTROL DIL] compact. Het is een zelfstandige codebibliotheek die helpt de hoeveelheid code verminderen die wordt vereist om informatie te verzamelen. Tot slot [!UICONTROL DIL] helpt u [!DNL Audience Manager] met andere producten in [!DNL Adobe] Experience Cloud integreren.

## Akamai {#akamai}

[!DNL Audience Manager] gebruikt  [](https://www.akamai.com/us/en/about/) Akamaito-host en levert containercode van ons eigen tagbeheerplatform, bekend als  [!UICONTROL TIM (Tag Insertion Manager)]. Codeimplementatie met [!UICONTROL TIM] is echter afgebouwd ten gunste van [!DNL Adobe Dynamic Tag Management] en [!DNL Adobe Experience Platform Launch].

## Database {#control-database} beheren

De besturingsdatabase:

* Verwerkt cliëntinput van het portaal (bijvoorbeeld, creërend eigenschappen en bestemmingen).
* Hiermee worden gegevens naar Akamai verzonden, die gegevens bevat die worden gebruikt om de containersjabloon en doelpublicatie-iFrame samen te stellen.
* Retourneert gegevens voor UI-rapportagesystemen.
