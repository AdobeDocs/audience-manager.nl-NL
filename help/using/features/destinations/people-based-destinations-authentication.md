---
description: 'Deze pagina bevat richtlijnen voor het configureren en beheren van de integratie tussen Audience Manager- en op mensen gebaseerde platforms. '
seo-description: 'Deze pagina bevat richtlijnen voor het configureren en beheren van de integratie tussen Audience Manager- en op mensen gebaseerde platforms. '
seo-title: Verificatie met persoonsgebaseerde platforms
solution: Audience Manager
title: Verificatie met persoonsgebaseerde platforms
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# Verificatie met persoonsgebaseerde platforms {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina bevat richtlijnen over hoe u uw integratie kunt configureren en beheren
tussen Audience Manager en op mensen gebaseerde platforms.

>[!NOTE]
>Dit is een verplichte stap voor op mensen-Gebaseerde Doelen, ongeacht uw implementatiescenario.

## Verificatie van Platforms op basis van personen configureren {#configure-authentication}

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![op mensen gebaseerde integratie](assets/pbd-config.png)
2. Klik op **[!UICONTROL Add Account]**.
3. Gebruik het vervolgkeuzemenu **[!UICONTROL People-Based Platform]** om het platform te selecteren waarmee u de integratie wilt configureren.
   ![op mensen gebaseerd platform](assets/pbd-add.png)
4. Klik op **[!UICONTROL Confirm]** om te worden omgeleid naar de verificatiepagina van het geselecteerde platform.
5. Nadat u zich hebt geverifieerd op uw account voor het sociale platform, wordt u omgeleid naar de Audience Manager waar de accounts van uw adverteerders moeten worden weergegeven. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]**.
6. Audience Manager geeft boven aan de pagina een melding weer om te laten weten of de account is toegevoegd. Met de melding kunt u ook een e-mailadres voor contactpersonen toevoegen om meldingen van Adobe te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

## Verificatietokkenvervaldatum en meldingsbeheer {#token-expiration-notification}

De Audience Manager behandelt uw integratie met sociale platforms door authentificatietokens die na een bepaalde hoeveelheid tijd verlopen. De geldigheidsduur van de token is afhankelijk van de integratieregels van elk sociaal platform. Zodra het authentificatietoken verloopt, kan de Audience Manager uw publiekssegmenten naar uw bestemming niet verzenden. Om dit scenario te vermijden, adviseren wij toevoegend minstens één contact e-mailadres aan uw integratie, zodat u op de hoogte wordt gebracht zodra het authentificatietoken op het punt staat te verlopen. Wanneer dat gebeurt, kunt u opnieuw voor authentiek verklaren om de bestemming te verzekeren blijft uw publiekssegmenten ontvangen.

Hieronder wordt beschreven hoe u e-mailadressen aan bestaande integratie kunt toevoegen:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identificeer de integratie waarvoor u symbolische vervalberichten wilt ontvangen, en klik **[!UICONTROL Edit]** pictogram.
1. Voer de e-mailadressen in waarop u meldingen over het verlopen van token wilt ontvangen, gescheiden door komma&#39;s.
1. Klik op **[!UICONTROL Save]**.

## Verificatietokens vernieuwen {#token-renewal}

Wanneer een authentificatietoken verloopt, wordt de integratie tussen Audience Manager en het overeenkomstige sociale platform onderbroken, zodat kan de Audience Manager niet publiekssegmenten naar de bestemming meer verzenden. De [!UICONTROL Integrated Accounts] pagina toont u de vervalstatus van elke integratie in [!UICONTROL Expiration] kolom, en staat u toe om de authentificatie op elk ogenblik te vernieuwen.

Hieronder wordt beschreven hoe u een verlopen of bijna verlopen verificatie vernieuwt:
1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identificeer de integratie die u authentificatie voor moet vernieuwen. Verlopen authenticaties worden gemarkeerd als [!UICONTROL Expired], terwijl voor authenticaties die binnenkort verlopen, binnenkort het resterende aantal geverifieerde dagen wordt weergegeven.
1. Klik op het bijbehorende pictogram **[!UICONTROL Renew]** in de kolom [!UICONTROL Expiration]. Hierdoor wordt de **[!UICONTROL Renew Account]**-workflow geactiveerd, waardoor u weer de verificatiepagina van het sociale platform doorloopt. Zodra u voor authentiek verklaart, wordt het teken vernieuwd met de nieuwe vervaldatum.
   ![pbd-renew](assets/pbd-renew.png)
