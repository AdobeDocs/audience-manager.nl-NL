---
description: Audience Manager-gebruikersbeheer gaat naar Adobe Admin Console. In dit artikel wordt uitgelegd wat u moet doen om de migratie van gebruikers voor te bereiden en wat er verandert als de migratie is voltooid.
keywords: rbac;RBAC;op rol gebaseerd;op rol-gebaseerd;op rol-gebaseerde toegangscontroles
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager-gebruikersmigratie naar Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 1%

---

# [!DNL Audience Manager] gebruikersmigratie naar [!DNL Admin Console] {#user-migration}

## Overzicht {#overview}

[!DNL Audience Manager] het beheer van de gebruikersrekening beweegt zich aan [&#x200B; Adobe Admin Console &#x200B;](https://helpx.adobe.com/nl/enterprise/using/admin-console.html), voor een meer gestroomlijnde ervaring over uw oplossingen van Adobe.

De voordelen van het gebruik van [!DNL Admin Console] zijn onder andere:

| Voordeel | Beschrijving |
|---|---|
| Single Sign-On voor oplossingen | [!DNL Audience Manager] -gebruikers kunnen zich aanmelden bij [!DNL Experience Cloud] en alle andere oplossingen met hun [!DNL Adobe ID] of [!DNL Enterprise ID] . Met deze aanmelding hebt u toegang tot geïntegreerde oplossingen en kernservices in [!DNL Experience Cloud] . Na de migratie worden gebruikers die proberen zich aan te melden via oude logins (`bank.demdex.com`), omgeleid naar `experiencecloud.adobe.com` . |
| Gebruikers en groepen beheren | Zodra de migratie volledig is, [!DNL Audience Manager] zullen de beheerders gebruikers en groepen uitsluitend in [[!DNL Admin Console] beheren &#x200B;](https://adminconsole.adobe.com/enterprise/). |
| Producten en services beheren | Vanuit [[!DNL Admin Console] &#x200B;](https://adminconsole.adobe.com/enterprise/), kunnen de beheerders: <ul><li>Gebruikers maken, bijwerken en verwijderen</li><li>Toegang verlenen tot oplossingen en services</li></ul> |

Om gebruikersmigratie te vergemakkelijken, vragen wij alle [!DNL Audience Manager] beheerders beginnen hun gebruikersrekeningen aan [&#x200B; Adobe Admin Console &#x200B;](https://helpx.adobe.com/nl/enterprise/using/admin-console.html) zo spoedig mogelijk te migreren, door de stappen te volgen die in dit artikel worden beschreven.

## Wat gebruikers moeten doen {#what-to-do-users}

Als Audience Manager-gebruiker hoeft u alleen maar contact op te nemen met uw [!DNL Audience Manager] -beheerder en deze te vragen een nieuwe gebruikersaccount voor u te maken in [!DNL Admin Console] .

## Wat beheerders moeten doen {#what-to-do-admins}

Audience Manager-beheerders moeten de onderstaande stappen volgen om gebruikers te migreren naar [!DNL Admin Console] .

1. Ga naar [&#x200B; https://adminconsole.adobe.com &#x200B;](https://adminconsole.adobe.com) en login gebruikend uw Adobe ID of Enterprise ID. Als u geen toegang hebt tot de [!DNL Admin Console] , neemt u contact op met de klantenservice of uw Adobe-consultant.
2. Controleer de [!DNL Adobe Admin Console] [&#x200B; hulpgids &#x200B;](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/users.ug.html) voor gedetailleerde instructies op hoe te om gebruikersrekeningen tot stand te brengen en te beheren.
3. Maak nieuwe gebruikersaccounts voor al je bestaande Audience Manager-gebruikers.
4. Stel uw gebruikers op de hoogte van de nieuwe gebruikersaccounts. Wanneer gebruikers naar [!DNL Admin Console] zijn gemigreerd, moeten ze geen oude logins meer gebruiken.

## Overwegingen voor gebruikersmigratie {#considerations}

Zowel gebruikers als beheerders dienen rekening te houden met de volgende aspecten bij het migreren van Audience Manager-gebruikers:

* Zodra nieuwe gebruikersrekeningen in Admin Console worden gecreeerd, zullen hun bestaande toestemmingen van hun erfenisgebruikersrekeningen nog van toepassing zijn.
* Updates voor gebruikersmachtigingen worden nog steeds beheerd vanuit [!DNL Audience Manager] . De instructie [!DNL Admin Console] heeft alleen betrekking op gebruikers- en groepsbeheer.
* Beheerders hoeven verouderde gebruikersaccounts niet uit te schakelen. Oude gebruikersaccounts worden automatisch samengevoegd met gemigreerde gebruikersaccounts.
