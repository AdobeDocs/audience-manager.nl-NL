---
description: Tot de onderdelen voor tagbeheer van Audience Managers behoren het clientportaal, Adobe Tag Manager (afgekeurd ten gunste van Adobe Experience Platform Launch), DIL, Akamai en de controledatabase.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Onderdelen voor Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 2%

---

# Onderdelen voor Tag Management{#tag-management-components}

Tot de componenten voor het beheer van tags voor Audience Managers behoren het clientportaal, Adobe Tag Manager (afgekeurd ten gunste van Adobe Experience Platform Tags), DIL, Akamai en de database voor besturingselementen.

<!-- 

c_comptag.xml

 -->

Audience Manager bevat de volgende componenten:

* [Clientportal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-container](../../reference/system-components/components-tag-management.md#dil-tim)
* [Gegevensinformatiebibliotheek (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Besturingsdatabase](../../reference/system-components/components-tag-management.md#control-database)

## Clientportal {#client-portal}

Het clientportaal is de primaire gebruikersinterface (UI) voor tag- en gegevensbeheer. De klanten gebruiken het portaal om met markeringen te werken, eigenschappen en segmenten te bouwen, opstellingsbestemmingen, en campagneprestaties met rapporten te controleren.

## DIL/TIM-container {#dil-tim}

De [!UICONTROL DIL] container helpt implementeren [!DNL Audience Manager] code voor gegevensverzameling naar uw website. [!UICONTROL TIM] is het vervangen van Taginvoegingsbeheer. Het wordt niet meer gebruikt door [!DNL Audience Manager]. In plaats daarvan gebruikt u de [!DNL Audience Manager] extensie in [Adobe Experience Platform-tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) om containercode te configureren en te genereren die u op pagina&#39;s in uw overzicht plaatst.

## Data Integration Library (DIL) {#dil}

De [Gegevensinformatiebibliotheek](../../dil/dil-overview.md) (DIL) is een zelfstandige API-module die gegevens van uw website verzamelt. [!UICONTROL DIL] helpt u te voorkomen dat u speciale code hoeft te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens. [!UICONTROL DIL] voert deze acties automatisch uit. Daarnaast [!UICONTROL DIL] is compact. Het is een zelfstandige codebibliotheek die helpt de hoeveelheid code verminderen die wordt vereist om informatie te verzamelen. Tot slot: [!UICONTROL DIL] helpt u te integreren [!DNL Audience Manager] met andere producten in de [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] gebruik [Akamai](https://www.akamai.com/us/en/about/) om containercode te hosten en leveren vanuit ons eigen tagbeheerplatform, bekend als [!UICONTROL TIM (Tag Insertion Manager)]. Nochtans, codeplaatsing met [!UICONTROL TIM] is afgebouwd ten gunste van [!DNL Adobe Experience Platform Tags].

## Besturingsdatabase {#control-database}

De besturingsdatabase:

* Verwerkt cliëntinput van het portaal (bijvoorbeeld, creërend eigenschappen en bestemmingen).
* Hiermee worden gegevens naar Akamai verzonden, die gegevens bevat die worden gebruikt om de containersjabloon en doelpublicatie-iFrame samen te stellen.
* Retourneert gegevens voor UI-rapportagesystemen.
