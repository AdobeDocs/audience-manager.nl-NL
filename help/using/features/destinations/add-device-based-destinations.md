---
description: Dit artikel verklaart hoe te om nieuwe op apparaat-gebaseerde bestemmingen van het gebruikersinterface van de Audience Manager te vormen.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Nieuwe apparaatgebaseerde bestemmingen toevoegen
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 3%

---

# Nieuwe apparaatgebaseerde bestemmingen toevoegen {#add-new-device-based-destinations}

Dit artikel verklaart hoe te om nieuwe op apparaat-gebaseerde bestemmingen van het gebruikersinterface van de Audience Manager te vormen.

>[!IMPORTANT]
>
>Momenteel, zijn de meeste op apparaat-gebaseerde bestemmingen niet verkiesbaar voor het werkschema van de zelfbediening configuratie. Als het apparaat-gebaseerde doel dat u moet toevoegen niet in de lijst van bestemmingen wordt getoond, contacteer uw consultant van de Adobe of Klantenondersteuning voor hulp.

## Overzicht {#overview}

Het proces om een nieuwe op apparaat-gebaseerde bestemming toe te voegen bestaat uit twee belangrijkste stappen. Eerst, moet u de integratie tussen Audience Manager en de bestemmingspartner vormen. Als u dat doet, kunt u een nieuwe, op apparaten gebaseerde bestemming maken.

## Vereisten {#prerequisites}

Neem bij het maken van de eerste apparaatgebaseerde bestemming met een geïntegreerd platform contact op met Adobe Consulting of de klantenservice om id-synchronisatie tussen Audience Manager en het geïntegreerde platform voor uw account in te schakelen. Dit wordt vereist voor de correcte synchronisatie tussen Audience Manager en het bestemmingsplatform.

## Stap 1. Verifiëren met een Platform van de Bestemming {#step1}

Alvorens u een nieuwe op apparaat-gebaseerde bestemming kunt tot stand brengen, moet u de integratie tussen Audience Manager en het bestemmingsplatform vormen. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!DNL Administration > Integrated Accounts]**. Als u een eerder gevormde integratie met een bestemmingsplatform hebt, zou u het in deze pagina moeten zien die. Anders is de pagina leeg.
1. Klik op **[!DNL Add Account]**.
1. Selecteer het doelplatform waarmee u wilt verifiëren en klik op **[!DNL Confirm]** om te worden omgeleid naar de authentificatiepagina van het geselecteerde platform.

   ![geïntegreerde platforms](assets/dbd-integrated-platforms.png)

1. Zodra u aan uw rekening van het bestemmingsplatform voor authentiek hebt verklaard, wordt u opnieuw gericht aan Audience Manager waar u uw bijbehorende adverteerderrekeningen zou moeten zien. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!DNL Confirm]**.

## Stap 2. Een nieuwe op apparaten gebaseerde bestemming maken {#step2}

Nadat u de integratie van het bestemmingsplatform hebt gevormd, kunt u de nieuwe bestemming tot stand brengen. Dit doet u als volgt:

>[!NOTE]
>
>U kunt de naam van een bestaand op apparaat gebaseerd doel niet wijzigen. Zorg ervoor om een naam te verstrekken die u zal helpen de bestemming correct identificeren.

1. Meld u aan bij uw Audience Manager-account, ga naar **[!DNL Audience Data > Destinations]** en klik op **[!DNL Create Destination]**.
1. In de **[!DNL Basic Information]** in, voert u een **[!DNL Name]** en **[!DNL Description]** voor uw nieuwe bestemming, en gebruik de montages in de hieronder lijst:

   ![instellen](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: Selecteer het doelplatform waarnaar u publiekssegmenten wilt verzenden.
   * **[!DNL Account]**: Selecteer het gewenste adverteerderaccount dat aan het geselecteerde platform is gekoppeld.
1. Klik op **[!DNL Next]**.
1. Kies de optie [Labels voor gegevensexport](/help/using/features/data-export-controls.md#controls-labels) die u voor dit doel wilt instellen.
1. Klik op **[!DNL Save]**.
1. In de **[!DNL Segment Mappings]** selecteert u de publiekssegmenten die u naar deze bestemming wilt verzenden.
1. Sla het doel op.
