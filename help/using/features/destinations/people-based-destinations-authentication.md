---
description: Deze pagina bevat aanwijzingen voor het configureren en beheren van de integratie tussen Audience Manager en op personen gebaseerde platforms.
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: Verificatie met platforms op basis van personen
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# Verificatie met platforms op basis van personen {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Deze pagina bevat richtlijnen over hoe u uw integratie kunt configureren en beheren
tussen Audience Manager en op mensen gebaseerde platforms.

>[!NOTE]
>Dit is een verplichte stap voor op mensen-Gebaseerde Doelen, ongeacht uw implementatiescenario.

## Platformverificatie configureren op basis van personen {#configure-authentication}

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]** . Als u een eerder geconfigureerde integratie met een sociaal platform hebt, wordt deze in deze pagina weergegeven. Anders is de pagina leeg.
   ![ op mensen-gebaseerde-integratie ](assets/pbd-config.png)
2. Klik op **[!UICONTROL Add Account]**.
3. Gebruik het vervolgkeuzemenu **[!UICONTROL People-Based Platform]** om het platform te selecteren waarmee u de integratie wilt configureren.
   ![ op mensen-gebaseerd-platform ](assets/pbd-add.png)
4. Klik op **[!UICONTROL Confirm]** om te worden omgeleid naar de verificatiepagina van het geselecteerde platform.
5. Zodra je je hebt geverifieerd op je account bij een sociaal platform, word je doorgestuurd naar Audience Manager waar je de bijbehorende adverteerderaccounts kunt bekijken. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!UICONTROL Confirm]** .
6. Audience Manager geeft boven aan de pagina een melding weer om aan te geven of de account is toegevoegd. Met deze melding kunt u ook een e-mailadres voor contactpersonen toevoegen om berichten van Adobe te ontvangen wanneer de verificatie van het sociale platform bijna verlopen is.

## Verificatietokkenvervaldatum en meldingsbeheer {#token-expiration-notification}

Audience Manager verwerkt uw integratie met sociale platforms via verificatietokens die na een bepaalde tijd verlopen. De geldigheidsduur van de token is afhankelijk van de integratieregels van elk sociaal platform. Als het verificatietoken is verlopen, kan Audience Manager de doelsegmenten niet meer naar uw bestemming verzenden. Om dit scenario te vermijden, adviseren wij toevoegend minstens één contact e-mailadres aan uw integratie, zodat u op de hoogte wordt gebracht zodra het authentificatietoken op het punt staat te verlopen. Wanneer dat gebeurt, kunt u opnieuw voor authentiek verklaren om de bestemming te verzekeren blijft uw publiekssegmenten ontvangen.

Hieronder wordt beschreven hoe u e-mailadressen aan bestaande integratie kunt toevoegen:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]** .
1. Bepaal de integratie waarvoor u meldingen over het verlopen van token wilt ontvangen en klik op het pictogram **[!UICONTROL Edit]** .
1. Voer de e-mailadressen in waarop u meldingen over het verlopen van token wilt ontvangen, gescheiden door komma&#39;s.
1. Klik op **[!UICONTROL Save]**.

## Verificatietokens vernieuwen {#token-renewal}

Wanneer een authentificatietoken verloopt, wordt de integratie tussen Audience Manager en het overeenkomstige sociale platform onderbroken, zodat kan Audience Manager niet publiekssegmenten naar de bestemming meer verzenden. Op de pagina [!UICONTROL Integrated Accounts] ziet u de vervalstatus van elke integratie in de kolom [!UICONTROL Expiration] en kunt u de verificatie op elk gewenst moment vernieuwen.

Hieronder wordt beschreven hoe u een verlopen of bijna verlopen verificatie vernieuwt:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]** .
1. Identificeer de integratie die u authentificatie voor moet vernieuwen. Verlopen verificaties worden gemarkeerd als [!UICONTROL Expired] , terwijl voor verificaties die binnenkort verlopen, binnenkort het resterende aantal geverifieerde dagen wordt weergegeven.
1. Klik op het bijbehorende pictogram **[!UICONTROL Renew]** in de kolom [!UICONTROL Expiration] . Dit activeert de **[!UICONTROL Renew Account]** -workflow, die u weer doorloopt op de verificatiepagina van het sociale platform. Zodra u voor authentiek verklaart, wordt het teken vernieuwd met de nieuwe vervaldatum.

   ![ pbd-vernieuwt ](assets/pbd-renew.png)
