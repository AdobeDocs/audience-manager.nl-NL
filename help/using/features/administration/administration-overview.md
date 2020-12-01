---
description: Met de opties in het menu Beheer kunt u gebruikers van Audience Managers maken en deze toewijzen aan groepen. U kunt ook limieten (kenmerken, segmenten, doelen en modellen) weergeven.
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: Met de opties in het menu Beheer kunt u gebruikers van Audience Managers maken en deze toewijzen aan groepen. U kunt ook limieten (kenmerken, segmenten, doelen en modellen) weergeven.
seo-title: Beheer
solution: Audience Manager
title: Beheer
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---


# [!UICONTROL Administration] (RBAC-controles)  {#administration}

![](assets/rbac-controls.png)

Met de opties in het menu [!UICONTROL Administration] kunt u gebruikers van Audience Managers maken en deze toewijzen aan groepen. U kunt ook limieten (kenmerken, segmenten, doelen en modellen) weergeven.

Enterprise-klanten die [!DNL Audience Manager] gebruiken, hebben één platform voor gegevensbeheer nodig voor al hun gegevens, maar moeten de zichtbaarheid van de verschillende gegevenselementen voor specifieke bedrijfseenheden kunnen beheren. U kunt dit verwezenlijken gebruikend groepstoestemmingen, die ook als [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC] worden bedoeld).

[!DNL Audience Manager] gebruikt groepen om machtigingen toe te wijzen. Machtigingen worden niet op gebruikersniveau toegewezen. Groepmachtigingen zijn gekoppeld aan objecten ([!UICONTROL traits], segmenten, enz.) en op handelingen die u op die objecten kunt uitvoeren (bewerken, weergeven, enz.). Deze besturingselementen zijn ook beschikbaar via de Audience Manager REST API&#39;s. Zie [Gebruikersbeheer](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Groepsbeheer](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) en [Machtigingenbeheer](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API-methoden.

## Gebruikers {#create-users} maken

<!-- t_create_users.xml -->

Maak gebruikers in [!DNL Audience Manager] en geef gebruikersgegevens, aanmeldingsstatus op en wijs gebruikers aan groepen toe.

1. Klik op **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Klik op ![](assets/icon_add.png) om de pagina [!UICONTROL Create New User] weer te geven.
1. Vul onder **[!UICONTROL User Details]** de velden in:
   * **[!UICONTROL Username]:** Geef een unieke gebruikersnaam op voor de Audience Manager.
   * **[!UICONTROL First Name]:** Geef de voornaam van de gebruiker op.
   * **[!UICONTROL Last Name]:** Geef de achternaam van de gebruiker op.
   * **[!UICONTROL Email Address]:** Geef het e-mailadres van de gebruiker op. [!DNL Audience Manager] verzendt geen regelmatig bericht naar gebruikers. [!DNL Audience Manager] beheerders hebben toegang tot de e-mailadressen van gebruikers en kunnen gebruikers indien nodig handmatig e-mailen. Als een gebruiker bijvoorbeeld zijn wachtwoord vergeet, wordt het in dit veld opgegeven e-mailadres gebruikt om een tijdelijk wachtwoord en instructies te verzenden waarmee het wachtwoord opnieuw kan worden ingesteld.
   * **[!UICONTROL Phone Number]:** Geef het telefoonnummer van de gebruiker op.
   * **[!UICONTROL Is Admin]:** Geef op of deze gebruiker een  [!DNL Audience Manager] beheerder is. Gebruikers met beheerdersrechten kunnen gebruikers beheren (maken, bewerken, enz.) en groepen (maken, toewijzen van machtigingen enz.). Gebruikers die geen beheerder zijn, kunnen alleen hun eigen gebruikersprofielen beheren, zoals het bewerken van hun e-mailadressen en het opnieuw instellen van hun eigen wachtwoorden. Zie [Uw accountinstellingen bewerken](../../features/administration/edit-account-settings.md) voor meer informatie.
1. Selecteer onder **[!UICONTROL Login]** de gewenste status:
   * **[!UICONTROL Active]:**  Actieve gebruikers hebben toegang tot  [!DNL Audience Manager] en hebben de toestemmingen die door groepslidmaatschap worden verleend.
   * **[!UICONTROL Deactivated]:**  Gedetailleerde gebruikers hebben geen toegang  [!DNL Audience Manager] en hebben geen machtigingen. Als u gebruikers deactiveert, blijven hun gebruikersgegevens in [!DNL Audience Manager] en kunt u hen eenvoudig, indien nodig, opnieuw activeren. Als u gebruikers verwijdert, moet u hen opnieuw creëren als zij [!DNL Audience Manager] in de toekomst opnieuw moeten gebruiken.
   * **[!UICONTROL Expired]:** Het wachtwoord van een gebruiker is ouder dan 90 dagen.
   * **[!UICONTROL Pending]:** De gebruiker heeft een tijdelijk wachtwoord, hetzij na het opnieuw instellen van het wachtwoord of als een gloednieuwe account, en zij hebben nog geen permanent wachtwoord ingesteld.
   * **[!UICONTROL Locked Out]:** 5 onjuiste aanmeldingspogingen sluiten een gebruiker uit.
1. Selecteer onder **[!UICONTROL Assigned Groups]** in de vervolgkeuzelijst de gewenste groepen waaraan u deze gebruiker wilt toewijzen.
Zie [Een groep maken](../../features/administration/administration-overview.md#create-group) voor meer informatie over groepen en machtigingen.
1. Klik op **[!UICONTROL Save]**.

## Een [!UICONTROL Group] {#create-group} maken

Een *groep* is een inzameling van gebruikers die toegangsrechten aan [!UICONTROL destination], [!UICONTROL segment], en [!UICONTROL trait] voorwerpen delen. U kunt groepen beperken tot alleen enkele objecten of ze brede toegang geven tot combinaties van verschillende objecten.

<!-- t_create_groups.xml -->

Een groep maken:

1. Klik op **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. Klik op ![](assets/icon_add.png) om de pagina [!UICONTROL Group Settings] te openen.
1. In [!UICONTROL Group Details]:
   * Geef de groep een naam.
   * Geef een korte beschrijving van de groep op.
1. Klik in [!UICONTROL Group Members] op een gebruiker uit de opties **[!UICONTROL Add Users]** om deze aan de groep toe te voegen.
1. Selecteer in [!UICONTROL Group Permissions] een [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md) of [destination](../../features/destinations/destinations.md) van **[!UICONTROL Add Object]**.
Hiermee opent u een venster met machtigingen voor het geselecteerde object.
1. Schakel het selectievakje in voor de machtigingen die groepsleden moeten hebben.
1. *(Optioneel)* Wijs  [jokertekens ](../../features/administration/administration-overview.md#wild-card-permissions) toe aan de groep.
1. Klik op **[!UICONTROL Save Group]**.

## [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

Vereenvoudig het beheer van groepsrechten met [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] groepsleden automatische toegang geven tot elke gegevensbron die aan een  [!UICONTROL segment],  [!UICONTROL destination]of  [!UICONTROL trait]. Door vergelijking, laten de regelmatige toestemmingen slechts u specifieke [!UICONTROL data sources] aan één van deze voorwerpen toewijzen. En, wanneer u nieuwe [!UICONTROL data sources] toevoegt, krijgen de groepsleden geen toegang tot die nieuwe bronnen.

U moet de groepstoestemmingen openen en die nieuwe [!UICONTROL data sources] aan de groep toewijzen. [!UICONTROL Wild Card Permissions] Hiermee voorkomt u dit handmatige  [!UICONTROL data source] updateproces. Groepen met [!UICONTROL Wild Card Permissions] krijgen toegang tot nieuwe [!UICONTROL data sources] zonder expliciete toestemming.

![](assets/wild-card.png)

Lees hieronder voor een beschrijving van wat elke [!UICONTROL wildcard permission] betekent:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Gebruikers kunnen selecteren  [!UICONTROL traits] als basislijn voor  [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Gebruikers kunnen alle  [!UICONTROL traits] instellingen in hun bedrijfsaccount bewerken.
* `VIEW_ALL_TRAITS` - Gebruikers kunnen alle  [!UICONTROL traits] instellingen in hun bedrijfsaccount bekijken.
* `DELETE_ALL_TRAITS` - Gebruikers kunnen alle  [!UICONTROL traits] instellingen in hun bedrijfsaccount verwijderen.
* `CREATE_ALL_ALGO_TRAITS` - Gebruikers kunnen  [!UICONTROL algorithmic traits]een document maken.
* `MAP_ALL_TO_SEGMENTS` - Gebruikers kunnen alle  [!UICONTROL traits] toebehorende bedrijven toevoegen aan  [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Gebruikers kunnen  [!UICONTROL traits]een document maken.

**[!UICONTROL Reports]**

* `PTRREPORTS` - Dit  [!UICONTROL wildcard permission] verwijst naar verouderde functionaliteit en wordt binnenkort verwijderd uit de gebruikersinterface van de Audience Manager.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Gebruikers hebben toestemming om  [!UICONTROL models] eigendom van hun bedrijf te bekijken.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Gebruikers kunnen alle  [!UICONTROL derived signals] personen van hun bedrijf bekijken.
* `CREATE_DERIVED_SIGNALS` - Gebruikers kunnen  [!UICONTROL derived signals]een document maken.
* `EDIT_DERIVED_SIGNALS` - Gebruikers kunnen alle  [!UICONTROL derived signals] toebehoren van hun bedrijf bewerken.
* `DELETE_DERIVED_SIGNALS` - De gebruikers kunnen om het even welk van  [!UICONTROL derived signals] hun bedrijf schrappen.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Gebruikers kunnen alle  [!UICONTROL destinations] instellingen in hun bedrijfsaccount bewerken.
* `CREATE_DESTINATIONS` - Gebruikers kunnen  [!UICONTROL destinations]een document maken.
* `VIEW_ALL_DESTINATIONS` - Gebruikers kunnen alle  [!UICONTROL destinations] instellingen in hun bedrijfsaccount bekijken.
* `DELETE_ALL_DESTINATIONS` - Gebruikers kunnen alle  [!UICONTROL destinations] instellingen in hun bedrijfsaccount verwijderen.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Gebruikers kunnen alles (weergeven, maken, bewerken, verwijderen) op hun  [!UICONTROL Tag Containers]computer doen.

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gebruikers kunnen alles doen (weergeven, maken, bewerken, verwijderen) in hun  [!UICONTROL Audience Lab] testgroepen.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Gebruikers kunnen segmenten maken.
* `DELETE_ALL_SEGMENTS` - Gebruikers kunnen alle segmenten verwijderen die in hun bedrijfsaccount zijn ingesteld.
* `MAP_ALL_TO_DESTINATIONS` - De gebruikers kunnen om het even welke segmenten in kaart brengen die tot hun bedrijf behoren aan bestemmingen.
* `EDIT_ALL_SEGMENTS` - Gebruikers kunnen alle segmenten bewerken die in hun bedrijfsaccount zijn ingesteld.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Gebruikers kunnen segmenten selecteren als basislijn voor modellen.
* `VIEW_ALL_SEGMENTS` - Gebruikers kunnen alle segmenten weergeven die in hun bedrijfsaccount zijn ingesteld.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Gebruikers kunnen alle signalen weergeven die in de  [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md) zijn vastgelegd.

## Gevallen {#use-cases} gebruiken

### Gebruikerstoegang {#monitoring-user-access} controleren

[!UICONTROL Role-Based Access Control] kan u helpen de status van uw gebruikerslogin controleren, die u een duidelijk beeld van geeft wie tot uw instantie van de Audience Manager kan toegang hebben.

Afhankelijk van uw bedrijfsvereisten, kunt u gebruikersrekeningen toelaten en onbruikbaar maken zoals nodig.

![monitor-gebruiker-toegang](assets/monitor-user-access.png)

### Zorg voor toegangsbeveiliging voor gevoelige [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

U kunt [!UICONTROL Role-Based Access Control] op [!UICONTROL trait], segment, en [!UICONTROL destination] niveau, voor elke gebruikersgroep vormen.

Met deze functie kunt u beheren hoe uw gebruikers specifieke gegevenssets weergeven, maken, lezen, schrijven en bewerken en kunt u zelfs voorkomen dat gebruikers toegang krijgen tot gegevenssets die niet voor hen beschikbaar zouden moeten zijn.

![toegangsbescherming](assets/access-protection.png)
