---
description: Gebruikersbeheer van Audience Managers gaat over naar Adobe Admin Console. In dit artikel wordt uitgelegd wat u moet doen om de migratie van gebruikers voor te bereiden en wat er verandert als de migratie is voltooid.
keywords: rbac;RBAC;op rol gebaseerd;op rol-gebaseerd;op rol-gebaseerde toegangscontroles
seo-description: Gebruikersbeheer van Audience Managers gaat over naar Adobe Admin Console. In dit artikel wordt uitgelegd wat u moet doen om de migratie van gebruikers voor te bereiden en wat er verandert als de migratie is voltooid.
seo-title: Audience Manager van gebruikersmigratie naar Admin Console
solution: Audience Manager
title: Audience Manager van gebruikersmigratie naar Admin Console
feature: Administration
translation-type: tm+mt
source-git-commit: 2e01abab2616daccd7581cdaa18417650951d139
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 2%

---


# [!DNL Audience Manager] gebruikersmigratie naar  [!DNL Admin Console] {#user-migration}

## Overzicht {#overview}

[!DNL Audience Manager] Het beheer van gebruikersaccounts gaat over naar de  [Adobe Admin Console](https://helpx.adobe.com/nl/enterprise/using/admin-console.html) voor een gestroomlijnde ervaring in al uw Adobe-oplossingen.

De voordelen van het gebruik van [!DNL Admin Console] zijn onder andere:

| Voordeel | Beschrijving |
|---|---|
| Single Sign-On voor oplossingen | [!DNL Audience Manager] gebruikers kunnen zich aanmelden bij  [!DNL Experience Cloud] en alle andere oplossingen met hun  [!DNL Adobe ID] of  [!DNL Enterprise ID]. Met deze aanmelding hebt u toegang tot geïntegreerde oplossingen en kernservices in [!DNL Experience Cloud]. Na de migratie worden gebruikers die proberen zich aan te melden via oudere logins (`bank.demdex.com`) omgeleid naar `experiencecloud.adobe.com`. |
| Gebruikers en groepen beheren | Als de migratie is voltooid, beheren [!DNL Audience Manager] beheerders gebruikers en groepen uitsluitend in [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/). |
| Producten en services beheren | Vanuit [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/) kunnen beheerders: <ul><li>Gebruikers maken, bijwerken en verwijderen</li><li>Toegang verlenen tot oplossingen en services</li></ul> |

Om de migratie van gebruikers te vergemakkelijken, vragen we alle [!DNL Audience Manager]-beheerders zo snel mogelijk te beginnen met het migreren van hun gebruikersaccounts naar [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) door de in dit artikel beschreven stappen uit te voeren.

## Wat gebruikers moeten doen {#what-to-do-users}

Als gebruiker van de Audience Manager hoeft u alleen maar contact op te nemen met uw [!DNL Audience Manager]-beheerder en deze te vragen om een nieuwe gebruikersaccount voor u te maken in [!DNL Admin Console].

## Wat beheerders moeten doen {#what-to-do-admins}

Beheerders van Audience Managers moeten de onderstaande stappen volgen om gebruikers te migreren naar [!DNL Admin Console].

1. Ga naar [https://adminconsole.adobe.com](https://adminconsole.adobe.com) en meld u aan met uw Adobe ID of Enterprise ID. Als u geen toegang hebt tot [!DNL Admin Console], neemt u contact op met de klantenservice of uw Adobe-consultant.
2. Raadpleeg de [!DNL Adobe Admin Console] [help guide](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) voor gedetailleerde instructies over het maken en beheren van gebruikersaccounts.
3. Maak nieuwe gebruikersaccounts voor al uw bestaande Audience Managers.
4. Stel uw gebruikers op de hoogte van de nieuwe gebruikersaccounts. Wanneer gebruikers zijn gemigreerd naar [!DNL Admin Console], moeten ze geen oude logins meer gebruiken.

## Overwegingen voor gebruikersmigratie {#considerations}

Zowel moeten de gebruikers als de beheerders de volgende overwegingen voor de migratie van de gebruiker van de Audience Manager in acht nemen:

* Zodra de nieuwe gebruikersrekeningen in Admin Console worden gecreeerd, zullen hun bestaande toestemmingen van hun rekeningen van de erfenisgebruiker nog van toepassing zijn.
* Updates voor gebruikersmachtigingen worden nog steeds beheerd vanaf [!DNL Audience Manager]. Het [!DNL Admin Console] heeft alleen betrekking op gebruikers- en groepsbeheer.
* Beheerders hoeven verouderde gebruikersaccounts niet uit te schakelen. Oude gebruikersaccounts worden automatisch samengevoegd met gemigreerde gebruikersaccounts.
