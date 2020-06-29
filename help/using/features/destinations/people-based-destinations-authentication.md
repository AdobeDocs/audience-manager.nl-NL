---
description: 'Deze pagina bevat richtlijnen voor het configureren en beheren van de integratie tussen Audience Manager- en op mensen gebaseerde platforms. '
seo-description: 'Deze pagina bevat richtlijnen voor het configureren en beheren van de integratie tussen Audience Manager- en op mensen gebaseerde platforms. '
seo-title: Verificatie met Platforms op basis van personen
solution: Audience Manager
title: Verificatie met Platforms op basis van personen
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 0%

---


# Verificatie met Platforms op basis van personen {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina bevat richtlijnen voor het configureren en beheren van uw integratie tussen Audience Manager- en op personen gebaseerde platforms.

>[!NOTE]
>Dit is een verplichte stap voor op mensen-Gebaseerde Doelen, ongeacht uw implementatiescenario.

## Verificatie van Platforms op basis van personen configureren {#configure-authentication}

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![op mensen gebaseerde integratie](assets/pbd-config.png)
2. Klik op **[!UICONTROL Add Account]**.
3. Gebruik het **[!UICONTROL People-Based Platform]** drop-down menu om het platform te selecteren dat u de integratie met wilt vormen.
   ![op mensen gebaseerd platform](assets/pbd-add.png)
4. Klik **[!UICONTROL Confirm]** om naar de authentificatiepagina van het geselecteerde platform worden opnieuw gericht.
5. Nadat u zich hebt geverifieerd op uw account voor het sociale platform, wordt u omgeleid naar de Audience Manager waar de accounts van uw adverteerders moeten worden weergegeven. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]**.
6. Audience Manager geeft boven aan de pagina een melding weer om te laten weten of de account is toegevoegd. Met deze melding kunt u ook een contact-e-mailadres toevoegen om meldingen van Adobe te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

## Verificatietokkenvervaldatum en meldingsbeheer {#token-expiration-notification}

De Audience Manager behandelt uw integratie met sociale platforms door authentificatietokens die na een bepaalde hoeveelheid tijd verlopen. De geldigheidsduur van de token is afhankelijk van de integratieregels van elk sociaal platform. Zodra het authentificatietoken verloopt, kan de Audience Manager uw publiekssegmenten naar uw bestemming niet verzenden. Om dit scenario te vermijden, adviseren wij toevoegend minstens één contact e-mailadres aan uw integratie, zodat u op de hoogte wordt gebracht zodra het authentificatietoken op het punt staat te verlopen. Wanneer dat gebeurt, kunt u opnieuw voor authentiek verklaren om de bestemming te verzekeren blijft uw publiekssegmenten ontvangen.

Hieronder wordt beschreven hoe u e-mailadressen aan bestaande integratie kunt toevoegen:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identificeer de integratie u symbolische vervalberichten voor wilt ontvangen, en het **[!UICONTROL Edit]** pictogram klikken.
1. Voer de e-mailadressen in waarop u meldingen over het verlopen van token wilt ontvangen, gescheiden door komma&#39;s.
1. Klik op **[!UICONTROL Save]**.

## Verificatietokens vernieuwen {#token-renewal}

Wanneer een authentificatietoken verloopt, wordt de integratie tussen Audience Manager en het overeenkomstige sociale platform onderbroken, zodat kan de Audience Manager niet publiekssegmenten naar de bestemming meer verzenden. De [!UICONTROL Integrated Accounts] pagina toont u de vervalstatus van elke integratie in de [!UICONTROL Expiration] kolom, en staat u toe om de authentificatie op elk ogenblik te vernieuwen.

Hieronder wordt beschreven hoe u een verlopen of bijna verlopen verificatie vernieuwt:
1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identificeer de integratie die u authentificatie voor moet vernieuwen. Verlopen authenticaties worden gemarkeerd als [!UICONTROL Expired], terwijl voor authenticaties die binnenkort verlopen, binnenkort het resterende aantal geverifieerde dagen wordt weergegeven.
1. Klik op het bijbehorende **[!UICONTROL Renew]** pictogram in de [!UICONTROL Expiration] kolom. Dit activeert de **[!UICONTROL Renew Account]** workflow, waardoor u weer door de verificatiepagina van het sociale platform wordt geleid. Zodra u voor authentiek verklaart, wordt het teken vernieuwd met de nieuwe vervaldatum.
   ![pbd-renew](assets/pbd-renew.png)
