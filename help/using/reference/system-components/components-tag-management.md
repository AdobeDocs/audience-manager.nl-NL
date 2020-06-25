---
description: Tot de onderdelen voor tagbeheer voor Audience Managers behoren het clientportaal, Adobe Tag Manager (vervangen door Adobe Dynamic Tag Manager en het starten van Adobe Experience Platforms), DIL, Akamai en de database van besturingselementen.
seo-description: Tot de onderdelen voor tagbeheer voor Audience Managers behoren het clientportaal, Adobe Tag Manager (vervangen door Adobe Dynamic Tag Manager en het starten van Adobe Experience Platforms), DIL, Akamai en de database van besturingselementen.
seo-title: Onderdelen voor tagbeheer
solution: Audience Manager
title: Onderdelen voor tagbeheer
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 0%

---


# Onderdelen voor tagbeheer{#tag-management-components}

Tot de onderdelen voor tagbeheer voor Audience Managers behoren het clientportaal, Adobe Tag Manager (vervangen door Adobe Dynamic Tag Manager en het starten van Adobe Experience Platforms), DIL, Akamai en de database van besturingselementen.

<!-- 

c_comptag.xml

 -->

Audience Manager bevat de volgende componenten:

* [Clientportal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-container](../../reference/system-components/components-tag-management.md#dil-tim)
* [Data Information Library (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Besturingsdatabase](../../reference/system-components/components-tag-management.md#control-database)

## Clientportal {#client-portal}

Het clientportaal is de primaire gebruikersinterface (UI) voor tag- en gegevensbeheer. De klanten gebruiken het portaal om met markeringen te werken, eigenschappen en segmenten te bouwen, opstellingsbestemmingen, en campagneprestaties met rapporten te controleren.

## DIL/TIM-container {#dil-tim}

Met de [!UICONTROL DIL] container kunt u code voor [!DNL Audience Manager] gegevensverzameling op uw website implementeren. [!UICONTROL TIM] is het vervangen van Taginvoegingsbeheer. Het wordt niet meer gebruikt door [!DNL Audience Manager]. In plaats daarvan gebruikt u [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) of de [!DNL Audience Manager] extensie in [Adobe Experience Platform Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) om containercode te configureren en te genereren die u op de pagina&#39;s in uw overzicht plaatst. De [!UICONTROL DTM] container werkt samen met [!UICONTROL Data Information Library (DIL)] [!DNL Audience Manager]de container om gegevens van uw site te verzamelen en naar te sturen.

## Data Integration Library (DIL) {#dil}

De DIL ( [Data Information Library](../../dil/dil-overview.md) ) is een zelfstandige API-module die gegevens van uw website verzamelt. [!UICONTROL DIL] helpt u te voorkomen dat u speciale code hoeft te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens. [!UICONTROL DIL] voert deze acties automatisch uit. Bovendien [!UICONTROL DIL] is het compact. Het is een zelfstandige codebibliotheek die helpt de hoeveelheid code verminderen die wordt vereist om informatie te verzamelen. Tot slot [!UICONTROL DIL] helpt u om [!DNL Audience Manager] met andere producten in [!DNL Adobe] Experience Cloud te integreren.

## Akamai {#akamai}

[!DNL Audience Manager] gebruikt [Akamai](https://www.akamai.com/html/about/index.html) om containercode van ons eigen platform van het markeringsbeheer te ontvangen en te leveren dat als [!UICONTROL TIM (Tag Insertion Manager)]. Codeimplementatie met [!UICONTROL TIM] is echter geleidelijk afgebouwd ten gunste van [!DNL Adobe Dynamic Tag Management] en [!DNL Adobe Experience Platform Launch].

## Besturingsdatabase {#control-database}

De besturingsdatabase:

* Verwerkt cliëntinput van het portaal (bijvoorbeeld, creërend eigenschappen en bestemmingen).
* Hiermee worden gegevens naar Akamai verzonden, die gegevens bevat die worden gebruikt om de containersjabloon en doelpublicatie-iFrame samen te stellen.
* Retourneert gegevens voor UI-rapportagesystemen.

