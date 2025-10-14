---
description: Dit artikel verklaart hoe te om nieuwe op apparaat-gebaseerde bestemmingen van het gebruikersinterface van Audience Manager te vormen.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Nieuwe apparaatgebaseerde doelen toevoegen
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Nieuwe apparaatgebaseerde doelen toevoegen {#add-new-device-based-destinations}

Dit artikel verklaart hoe te om nieuwe op apparaat-gebaseerde bestemmingen van het gebruikersinterface van Audience Manager te vormen.

>[!IMPORTANT]
>
>Momenteel, zijn de meeste op apparaat-gebaseerde bestemmingen niet verkiesbaar voor het werkschema van de zelfbediening configuratie. Als het apparaat-gebaseerde doel dat u moet toevoegen niet in de lijst van bestemmingen wordt getoond, contacteer uw consultant van Adobe of Klantenondersteuning voor hulp.

## Overzicht {#overview}

Het proces om een nieuwe op apparaat-gebaseerde bestemming toe te voegen bestaat uit twee belangrijkste stappen. Eerst, moet u de integratie tussen Audience Manager en de bestemmingspartner vormen. Als u dat doet, kunt u een nieuwe, op apparaten gebaseerde bestemming maken.

## Vereisten {#prerequisites}

Neem bij het maken van de eerste apparaatgebaseerde bestemming met een geïntegreerd platform contact op met Adobe Consulting of de klantenservice om id-synchronisatie tussen Audience Manager en het geïntegreerde platform voor uw account in te schakelen. Dit is vereist voor de juiste synchronisatie tussen Audience Manager en het doelplatform.

## Stap 1. Verifiëren met een Platform van de Bestemming {#step1}

Voordat u een nieuwe, op apparaten gebaseerde bestemming kunt maken, moet u de integratie tussen Audience Manager en het doelplatform configureren. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!DNL Administration > Integrated Accounts]** . Als u een eerder gevormde integratie met een bestemmingsplatform hebt, zou u het in deze pagina moeten zien die. Anders is de pagina leeg.
1. Klik op **[!DNL Add Account]**.
1. Selecteer het doelplatform waarmee u wilt verifiëren en klik op **[!DNL Confirm]** om te worden omgeleid naar de verificatiepagina van het geselecteerde platform.

   ![&#x200B; geïntegreerd-platforms &#x200B;](assets/dbd-integrated-platforms.png)

1. Zodra je je hebt geverifieerd op je doelplatformaccount, word je doorgestuurd naar Audience Manager waar je de bijbehorende adverteerderaccounts kunt bekijken. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!DNL Confirm]** .

## Stap 2. Een nieuwe op apparaten gebaseerde bestemming maken {#step2}

Nadat u de integratie van het bestemmingsplatform hebt gevormd, kunt u de nieuwe bestemming tot stand brengen. Dit doet u als volgt:

>[!NOTE]
>
>U kunt de naam van een bestaand op apparaat gebaseerd doel niet wijzigen. Zorg ervoor om een naam te verstrekken die u zal helpen de bestemming correct identificeren.

1. Meld u aan bij uw Audience Manager-account, ga naar **[!DNL Audience Data > Destinations]** en klik op **[!DNL Create Destination]** .
1. Voer in de sectie **[!DNL Basic Information]** een **[!DNL Name]** en **[!DNL Description]** in voor uw nieuwe doel en gebruik de instellingen in de onderstaande lijst:

   ![&#x200B; opstelling &#x200B;](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: selecteer het doelplatform waarnaar u publiekssegmenten wilt verzenden.
   * **[!DNL Account]** : selecteer het gewenste adverteerderaccount dat aan het geselecteerde platform is gekoppeld.
1. Klik op **[!DNL Next]**.
1. Kies de [&#x200B; Etiketten van de Uitvoer van Gegevens &#x200B;](/help/using/features/data-export-controls.md#controls-labels) die u voor deze bestemming wilt plaatsen.
1. Klik op **[!DNL Save]**.
1. Selecteer in de sectie **[!DNL Segment Mappings]** de publiekssegmenten die u naar deze bestemming wilt verzenden.
1. Sla het doel op.
