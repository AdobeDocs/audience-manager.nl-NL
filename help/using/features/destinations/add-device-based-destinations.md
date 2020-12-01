---
description: Dit artikel verklaart hoe te om nieuwe op apparaat-gebaseerde bestemmingen van het gebruikersinterface van de Audience Manager te vormen.
seo-description: Dit artikel verklaart hoe te om nieuwe op apparaat-gebaseerde bestemmingen van het gebruikersinterface van de Audience Manager te vormen.
seo-title: Nieuwe apparaatgebaseerde bestemmingen toevoegen
solution: Audience Manager
title: Nieuwe apparaatgebaseerde bestemmingen toevoegen
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '437'
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

## Stap 1. Verifiëren met een Platform {#step1} van de Bestemming

Alvorens u een nieuwe op apparaat-gebaseerde bestemming kunt tot stand brengen, moet u de integratie tussen Audience Manager en het bestemmingsplatform vormen. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!DNL Administration > Integrated Accounts]**. Als u een eerder gevormde integratie met een bestemmingsplatform hebt, zou u het in deze pagina moeten zien die. Anders is de pagina leeg.
1. Klik op **[!DNL Add Account]**.
1. Selecteer het doelplatform waarmee u wilt verifiëren en klik op **[!DNL Confirm]** om te worden omgeleid naar de verificatiepagina van het geselecteerde platform.

   ![geïntegreerde platforms](assets/dbd-integrated-platforms.png)

1. Zodra u aan uw rekening van het bestemmingsplatform voor authentiek hebt verklaard, wordt u opnieuw gericht aan Audience Manager waar u uw bijbehorende adverteerderrekeningen zou moeten zien. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!DNL Confirm]**.

## Stap 2. Een nieuwe op apparaten gebaseerde bestemming maken {#step2}

Nadat u de integratie van het bestemmingsplatform hebt gevormd, kunt u de nieuwe bestemming tot stand brengen. Dit doet u als volgt:

>[!NOTE]
>
>U kunt de naam van een bestaand op apparaat gebaseerd doel niet wijzigen. Zorg ervoor om een naam te verstrekken die u zal helpen de bestemming correct identificeren.

1. Meld u aan bij uw Audience Manager-account, ga naar **[!DNL Audience Data > Destinations]** en klik op **[!DNL Create Destination]**.
1. Voer in de sectie **[!DNL Basic Information]** een **[!DNL Name]** en **[!DNL Description]** in voor uw nieuwe bestemming en gebruik de instellingen in de onderstaande lijst:

   ![instellen](assets/dbd-new-basic.png)

   * **[!DNL Category]**:  [!DNL Integrated Platforms];
   * **[!DNL Type]**:  [!DNL Device-Based];
   * **[!DNL Platform]**: Selecteer het doelplatform waarnaar u publiekssegmenten wilt verzenden.
   * **[!DNL Account]**: Selecteer het gewenste adverteerderaccount dat aan het geselecteerde platform is gekoppeld.
1. Klik op **[!DNL Next]**.
1. Kies de [Labels voor gegevensexport](/help/using/features/data-export-controls.md#controls-labels) die u voor deze bestemming wilt instellen.
1. Klik op **[!DNL Save]**.
1. Selecteer in de sectie **[!DNL Segment Mappings]** de publiekssegmenten die u naar deze bestemming wilt verzenden.
1. Sla het doel op.
