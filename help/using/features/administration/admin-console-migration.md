---
description: Gebruikersbeheer van Audience Managers gaat over naar Adobe Admin Console. In dit artikel wordt uitgelegd wat u moet doen om de migratie van gebruikers voor te bereiden en wat er verandert als de migratie is voltooid.
keywords: rbac;RBAC;op rol gebaseerd;op rol-gebaseerd;op rol-gebaseerde toegangscontroles
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager van gebruikersmigratie naar Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 3%

---

# [!DNL Audience Manager] gebruikersmigratie naar [!DNL Admin Console] {#user-migration}

## Overzicht {#overview}

[!DNL Audience Manager] het beheer van gebruikersaccounts gaat over naar de [Adobe Admin Console](https://helpx.adobe.com/nl/enterprise/using/admin-console.html), voor een gestroomlijndere ervaring in al uw Adobe-oplossingen.

De voordelen van het gebruik van de [!DNL Admin Console] omvatten:

| Voordeel | Beschrijving |
|---|---|
| Single Sign-On voor oplossingen | [!DNL Audience Manager] gebruikers kunnen zich aanmelden bij [!DNL Experience Cloud] en alle andere oplossingen die hun [!DNL Adobe ID] of [!DNL Enterprise ID]. Met deze aanmeldingsnaam hebt u toegang tot geïntegreerde oplossingen en kernservices in de hele regio [!DNL Experience Cloud]. Na de migratie proberen gebruikers zich aan te melden via oudere logins (`bank.demdex.com`) wordt omgeleid naar `experiencecloud.adobe.com`. |
| Gebruikers en groepen beheren | Zodra de migratie is voltooid, [!DNL Audience Manager] beheerders beheren gebruikers en groepen uitsluitend in de [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Producten en services beheren | Van de [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)kunnen beheerders: <ul><li>Gebruikers maken, bijwerken en verwijderen</li><li>Toegang verlenen tot oplossingen en services</li></ul> |

Om de migratie van gebruikers te vergemakkelijken, vragen wij allen [!DNL Audience Manager] beheerders moeten beginnen met het migreren van hun gebruikersaccounts naar [Adobe Admin Console](https://helpx.adobe.com/nl/enterprise/using/admin-console.html) zo spoedig mogelijk door de in dit artikel beschreven stappen te volgen.

## Wat gebruikers moeten doen {#what-to-do-users}

Als gebruiker van de Audience Manager hoeft u alleen maar contact op te nemen met uw [!DNL Audience Manager] beheerder en vraag hen om een nieuwe gebruikersrekening voor u te creëren in [!DNL Admin Console].

## Wat beheerders moeten doen {#what-to-do-admins}

Beheerders van Audience Managers moeten de onderstaande stappen volgen om gebruikers te migreren naar [!DNL Admin Console].

1. Ga naar [https://adminconsole.adobe.com](https://adminconsole.adobe.com) en meld u aan met uw Adobe ID of Enterprise ID. Als u geen toegang hebt tot [!DNL Admin Console], neemt u contact op met de klantenservice of uw Adobe-consultant.
2. Controleer de [!DNL Adobe Admin Console] [Help-handleiding](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/users.ug.html) voor gedetailleerde instructies over het maken en beheren van gebruikersaccounts.
3. Maak nieuwe gebruikersaccounts voor al uw bestaande Audience Managers.
4. Stel uw gebruikers op de hoogte van de nieuwe gebruikersaccounts. Wanneer gebruikers zijn gemigreerd naar [!DNL Admin Console], zouden zij moeten ophouden gebruikend erfenislogins.

## Overwegingen voor gebruikersmigratie {#considerations}

Zowel moeten de gebruikers als de beheerders de volgende overwegingen voor de migratie van de gebruiker van de Audience Manager in acht nemen:

* Zodra de nieuwe gebruikersrekeningen in Admin Console worden gecreeerd, zullen hun bestaande toestemmingen van hun rekeningen van de erfenisgebruiker nog van toepassing zijn.
* Updates voor gebruikersmachtigingen worden nog steeds beheerd vanaf [!DNL Audience Manager]. De [!DNL Admin Console] alleen gebruikers- en groepsbeheer.
* Beheerders hoeven verouderde gebruikersaccounts niet uit te schakelen. Oude gebruikersaccounts worden automatisch samengevoegd met gemigreerde gebruikersaccounts.
