---
description: Tot de Audience Manager-componenten voor tagbeheer behoren het clientportaal, Adobe Tag Manager (afgekeurd ten gunste van Adobe Experience Platform Launch), DIL, Akamai en de controledatabase.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management-componenten
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Tag Management-componenten{#tag-management-components}

Tot de Audience Manager-componenten voor tagbeheer behoren het clientportaal, Adobe Tag Manager (afgekeurd ten gunste van Adobe Experience Platform Tags), DIL, Akamai en de database voor besturingselementen.

<!-- 

c_comptag.xml

 -->

Audience Manager bevat de volgende componenten:

* [ Portaal van de Cliënt ](../../reference/system-components/components-tag-management.md#client-portal)
* [ DIL/TIM Container ](../../reference/system-components/components-tag-management.md#dil-tim)
* [ de Bibliotheek van de Informatie van Gegevens (DIL) ](../../reference/system-components/components-tag-management.md#dil)
* [ Akamai ](../../reference/system-components/components-tag-management.md#akamai)
* [Besturingsdatabase](../../reference/system-components/components-tag-management.md#control-database)

## Clientportal {#client-portal}

Het clientportaal is de primaire gebruikersinterface (UI) voor tag- en gegevensbeheer. De klanten gebruiken het portaal om met markeringen te werken, eigenschappen en segmenten te bouwen, opstellingsbestemmingen, en campagneprestaties met rapporten te controleren.

## DIL/TIM-container {#dil-tim}

Met de [!UICONTROL DIL] -container kunt u [!DNL Audience Manager] -code voor gegevensverzameling op uw website implementeren. [!UICONTROL TIM] is het afgekeurde beheer voor het invoegen van tags. Deze wordt niet meer gebruikt door [!DNL Audience Manager] . In plaats daarvan, gebruikt u de [!DNL Audience Manager] uitbreiding in [ de Markeringen van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=nl-NL) om containercode te vormen en te produceren die u op pagina&#39;s in uw inventaris plaatst.

## Data Integration Library (DIL) {#dil}

De [ Bibliotheek van de Informatie van Gegevens ](../../dil/dil-overview.md) (DIL) is een op zichzelf staande API module die gegevens van uw website verzamelt. Met [!UICONTROL DIL] voorkomt u de noodzaak om speciale code te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens. [!UICONTROL DIL] voert deze handelingen automatisch uit. Bovendien is [!UICONTROL DIL] compact. Het is een zelfstandige codebibliotheek die helpt de hoeveelheid code verminderen die wordt vereist om informatie te verzamelen. Tot slot kunt u met [!UICONTROL DIL] [!DNL Audience Manager] integreren met andere producten in de Experience Cloud van [!DNL Adobe] .

## Akamai {#akamai}

[!DNL Audience Manager] gebruikt [ Akamai ](https://www.akamai.com/us/en/about/) om containercode van ons eigen platform van het markeringsbeheer te ontvangen en te leveren dat als [!UICONTROL TIM (Tag Insertion Manager)] wordt bekend. Codeimplementatie met [!UICONTROL TIM] is echter geleidelijk afgebouwd ten gunste van [!DNL Adobe Experience Platform Tags] .

## Besturingsdatabase {#control-database}

De besturingsdatabase:

* Verwerkt cliëntinput van het portaal (bijvoorbeeld, creërend eigenschappen en bestemmingen).
* Hiermee worden gegevens naar Akamai verzonden, die gegevens bevat die worden gebruikt om de containersjabloon en doelpublicatie-iFrame samen te stellen.
* Retourneert gegevens voor UI-rapportagesystemen.
