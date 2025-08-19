---
description: Met de opties in het menu Beheer kunt u Audience Manager-gebruikers maken en deze toewijzen aan groepen. U kunt ook limieten (kenmerken, segmenten, doelen en modellen) weergeven.
keywords: rbac;RBAC;op rol gebaseerd;op rol-gebaseerd;op rol-gebaseerde toegangscontroles
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Administratie
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 0%

---

# [!UICONTROL Administration] (RBAC-controles) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> Het rekeningsbeheer van de gebruiker beweegt zich aan [ Admin Console ](https://helpx.adobe.com/nl/enterprise/using/admin-console.html). Om gebruikersmigratie te beginnen, vereisen wij alle klanten van Audience Manager om de noodzakelijke maatregelen onmiddellijk te nemen die in dit artikel worden beschreven: [ de gebruikersmigratie van Audience Manager aan Admin Console ](admin-console-migration.md).
> 
> Nadat alle klanten zijn gemigreerd, gaan de gebruikersbeheersecties van dit document weg.

>[!IMPORTANT]
>
> Voordat u [!DNL RBAC] kunt gebruiken, moet deze functie zijn ingeschakeld door Adobe voor uw organisatie. Neem contact op met uw accountteam om [!DNL RBAC] activering aan te vragen of neem contact op met de klantenservice.


Met de opties in het menu [!UICONTROL Administration] kunt u Audience Manager-gebruikers maken en deze toewijzen aan groepen. U kunt ook limieten (kenmerken, segmenten, doelen en modellen) weergeven.

Enterprise-klanten die [!DNL Audience Manager] gebruiken, hebben één platform voor gegevensbeheer nodig voor al hun gegevens, maar moeten de zichtbaarheid van de verschillende gegevenselementen voor specifieke bedrijfseenheden kunnen beheren. U kunt dit verwezenlijken gebruikend groepstoestemmingen, die ook als [!UICONTROL Role-Based Access Control] worden bedoeld ([!UICONTROL RBAC]).

[!DNL Audience Manager] gebruikt groepen om machtigingen toe te wijzen. Machtigingen worden niet op gebruikersniveau toegewezen. Groepmachtigingen zijn gekoppeld aan objecten ([!UICONTROL traits], segmenten, enzovoort) en aan handelingen die u op die objecten kunt uitvoeren (bewerken, weergeven, enz.). Deze besturingselementen zijn ook beschikbaar via de Audience Manager REST API&#39;s. Zie [ Beheer van de Gebruiker 0&rbrace;, ](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md) Beheer van de Groep [, en ](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) het Beheer van toestemmingen [ API methodes.](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md)

## Gebruikers maken {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> Het rekeningsbeheer van de gebruiker beweegt zich aan [ Admin Console ](https://helpx.adobe.com/nl/enterprise/using/admin-console.html). Om gebruikersmigratie te beginnen, vereisen wij alle klanten van Audience Manager om de noodzakelijke maatregelen onmiddellijk te nemen die in dit artikel worden beschreven: [ de gebruikersmigratie van Audience Manager aan Admin Console ](admin-console-migration.md).
> 
> Nadat alle klanten zijn gemigreerd, zal de sectie van het gebruikersbeheer van dit document weggaan.
> 
>Maak gebruikers in [!DNL Audience Manager] en geef gebruikersgegevens, aanmeldingsstatus en wijs gebruikers toe aan groepen.

1. Klik op **[!UICONTROL Administration]** > **[!UICONTROL Users]** .
1. Klik op ![](assets/icon_add.png) om de pagina [!UICONTROL Create New User] weer te geven.
1. Vul onder **[!UICONTROL User Details]** de velden in:
   * **[!UICONTROL Username]:** specificeer een unieke gebruikersbenaming voor Audience Manager.
   * **[!UICONTROL First Name]:** specificeer de voornaam van de gebruiker.
   * **[!UICONTROL Last Name]:** specificeer de achternaam van de gebruiker.
   * **[!UICONTROL Email Address]:** Geef het e-mailadres van de gebruiker op. [!DNL Audience Manager] verzendt geen regelmatig bericht naar gebruikers. [!DNL Audience Manager] -beheerders hebben toegang tot de e-mailadressen van gebruikers en kunnen gebruikers indien nodig handmatig e-mailen. Als een gebruiker bijvoorbeeld zijn wachtwoord vergeet, wordt het in dit veld opgegeven e-mailadres gebruikt om een tijdelijk wachtwoord en instructies te verzenden waarmee het wachtwoord opnieuw kan worden ingesteld.
   * **[!UICONTROL Phone Number]:** specificeer het telefoonaantal van de gebruiker.
   * **[!UICONTROL Is Admin]:** specificeer als deze gebruiker een [!DNL Audience Manager] beheerder is. Gebruikers met beheerdersrechten kunnen gebruikers (maken, bewerken, enz.) en groepen beheren (machtigingen maken, toewijzen, enz.). Gebruikers die geen beheerder zijn, kunnen alleen hun eigen gebruikersprofielen beheren, zoals het bewerken van hun e-mailadressen en het opnieuw instellen van hun eigen wachtwoorden. Voor meer informatie, zie [ Uw Montages van de Rekening ](../../features/administration/edit-account-settings.md) uitgeven.
1. Selecteer onder **[!UICONTROL Login]** de gewenste status:
   * **[!UICONTROL Active]:** Actieve gebruikers hebben toegang tot [!DNL Audience Manager] en beschikken over de machtigingen die door het groepslidmaatschap zijn verleend.
   * **[!UICONTROL Deactivated]:** gedeactiveerde gebruikers hebben geen toegang tot [!DNL Audience Manager] en hebben geen machtigingen. Als u gebruikers deactiveert, blijven hun gebruikersgegevens in [!DNL Audience Manager] en kunt u ze eenvoudig opnieuw activeren, indien nodig. Als u gebruikers verwijdert, moet u ze opnieuw maken als ze [!DNL Audience Manager] in de toekomst opnieuw moeten gebruiken.
   * **[!UICONTROL Expired]:** Het wachtwoord van een gebruiker is ouder dan 90 dagen.
   * **[!UICONTROL Pending]:** de gebruiker heeft een tijdelijk wachtwoord, of na een wachtwoordteruggestelde of als gloednieuwe rekening, en zij hebben nog geen permanent wachtwoord geplaatst.
   * **[!UICONTROL Locked Out]:** 5 onjuiste aanmeldingspogingen zullen een gebruiker uitsluiten.
1. Selecteer onder **[!UICONTROL Assigned Groups]** in de vervolgkeuzelijst de gewenste groepen waaraan u deze gebruiker wilt toewijzen.
Voor meer informatie over groepen en toestemmingen, zie [ een Groep ](../../features/administration/administration-overview.md#create-group) creëren.
1. Klik op **[!UICONTROL Save]**.

## Een [!UICONTROL Group] maken {#create-group}

>[!IMPORTANT]
>
> Het rekeningsbeheer van de gebruiker beweegt zich aan [ Admin Console ](https://helpx.adobe.com/nl/enterprise/using/admin-console.html). Om gebruikersmigratie te beginnen, adviseren wij alle klanten van Audience Manager om de noodzakelijke maatregelen onmiddellijk te nemen die in dit artikel worden beschreven: [ de gebruikersmigratie van Audience Manager aan Admin Console ](admin-console-migration.md).
> 
> Nadat alle klanten zijn gemigreerd, gaat deze sectie weg.

A *groep* is een inzameling van gebruikers die toegangsrechten aan [!UICONTROL destination] delen, [!UICONTROL segment], en [!UICONTROL trait] voorwerpen. U kunt groepen beperken tot alleen enkele objecten of ze brede toegang geven tot combinaties van verschillende objecten.

<!-- t_create_groups.xml -->

Een groep maken:

1. Klik op **[!UICONTROL Administration]** > **[!UICONTROL Groups]** .
2. Klik op ![](assets/icon_add.png) om de pagina van [!UICONTROL Group Settings] te openen.
3. In [!UICONTROL Group Details]:
   * Geef de groep een naam.
   * Geef een korte groepbeschrijving op.
4. Klik in [!UICONTROL Group Members] op een gebruiker uit **[!UICONTROL Add Users]** -opties om deze aan de groep toe te voegen.
5. In [!UICONTROL Group Permissions], selecteer a [ spoor ](../../features/traits/trait-details-page.md), [ segment ](../../features/segments/segments-purpose.md), of [ bestemming ](../../features/destinations/destinations.md) van **[!UICONTROL Add Object]**.
Hiermee opent u een venster met machtigingen voor het geselecteerde object.
6. Schakel het selectievakje in voor de machtigingen die groepsleden moeten hebben.
7. *(Facultatief)* wijs [ de Toestemmingen van de Kaart ](../../features/administration/administration-overview.md#wild-card-permissions) aan de groep toe.
8. Klik op **[!UICONTROL Save Group]**.

## Werken met [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> Het rekeningsbeheer van de gebruiker beweegt zich aan [ Admin Console ](https://helpx.adobe.com/nl/enterprise/using/admin-console.html). Om gebruikersmigratie te beginnen, adviseren wij alle klanten van Audience Manager om de noodzakelijke maatregelen onmiddellijk te nemen die in dit artikel worden beschreven: [ de gebruikersmigratie van Audience Manager aan Admin Console ](admin-console-migration.md).
> 
> Nadat alle klanten zijn gemigreerd, gaat deze sectie weg.

Vereenvoudig het beheer van groepsrechten met [!UICONTROL Wild Card Permissions] .

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] geeft groepsleden automatisch toegang tot elke gegevensbron die is gekoppeld aan een [!UICONTROL segment] , [!UICONTROL destination] of [!UICONTROL trait] . Met standaardmachtigingen kunt u alleen specifieke [!UICONTROL data sources] toewijzen aan een van deze objecten. En als u nieuwe [!UICONTROL data sources] toevoegt, krijgen groepsleden geen toegang tot die nieuwe bronnen.

U moet de machtigingen voor de groep openen en die nieuwe [!UICONTROL data sources] toewijzen aan de groep. Met [!UICONTROL Wild Card Permissions] voorkomt u dit handmatige [!UICONTROL data source] updateproces. Groepen met [!UICONTROL Wild Card Permissions] krijgen zonder expliciete toestemming toegang tot nieuwe [!UICONTROL data sources] .

![](assets/wild-card.png)

Lees hieronder voor een beschrijving van wat elke [!UICONTROL wildcard permission] betekent:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Gebruikers kunnen [!UICONTROL traits] selecteren als basislijn voor [!UICONTROL models] .
* `EDIT_ALL_TRAITS` - Gebruikers kunnen alle [!UICONTROL traits] -instellingen in hun bedrijfsaccount bewerken.
* `VIEW_ALL_TRAITS` - Gebruikers kunnen alle [!UICONTROL traits] -instellingen in hun bedrijfsaccount bekijken.
* `DELETE_ALL_TRAITS` - Gebruikers kunnen alle [!UICONTROL traits] -instellingen in hun bedrijfsaccount verwijderen.
* `CREATE_ALL_ALGO_TRAITS` - Gebruikers kunnen [!UICONTROL algorithmic traits] maken.
* `MAP_ALL_TO_SEGMENTS` - Gebruikers kunnen [!UICONTROL traits] die deel uitmaken van hun bedrijf, toevoegen aan [!UICONTROL segments] .
* `CREATE_ALL_TRAITS` - Gebruikers kunnen [!UICONTROL traits] maken.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Gebruikers hebben toestemming om [!UICONTROL models] te bekijken die bij hun bedrijf hoort.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Gebruikers kunnen alle [!UICONTROL derived signals] van hun bedrijf weergeven.
* `CREATE_DERIVED_SIGNALS` - Gebruikers kunnen [!UICONTROL derived signals] maken.
* `EDIT_DERIVED_SIGNALS` - Gebruikers kunnen alle [!UICONTROL derived signals] die bij hun bedrijf horen, bewerken.
* `DELETE_DERIVED_SIGNALS` - Gebruikers kunnen alle [!UICONTROL derived signals] die bij hun bedrijf horen, verwijderen.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Gebruikers kunnen alle [!UICONTROL destinations] -instellingen in hun bedrijfsaccount bewerken.
* `CREATE_DESTINATIONS` - Gebruikers kunnen [!UICONTROL destinations] maken.
* `VIEW_ALL_DESTINATIONS` - Gebruikers kunnen alle [!UICONTROL destinations] -instellingen in hun bedrijfsaccount bekijken.
* `DELETE_ALL_DESTINATIONS` - Gebruikers kunnen alle [!UICONTROL destinations] -instellingen in hun bedrijfsaccount verwijderen.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Gebruikers kunnen alles doen (weergeven, maken, bewerken, verwijderen) op hun [!UICONTROL Tag Containers] .

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gebruikers kunnen alles (weergeven, maken, bewerken, verwijderen) in hun [!UICONTROL Audience Lab] -testgroepen uitvoeren.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Gebruikers kunnen segmenten maken.
* `DELETE_ALL_SEGMENTS` - Gebruikers kunnen alle segmenten verwijderen die in hun bedrijfsaccount zijn ingesteld.
* `MAP_ALL_TO_DESTINATIONS` - Gebruikers kunnen alle segmenten van hun bedrijf toewijzen aan doelen.
* `EDIT_ALL_SEGMENTS` - Gebruikers kunnen alle segmenten bewerken die in hun bedrijfsaccount zijn ingesteld.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Gebruikers kunnen segmenten selecteren als basislijn voor modellen.
* `VIEW_ALL_SEGMENTS` - Gebruikers kunnen alle segmenten weergeven die in hun bedrijfsaccount zijn ingesteld.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - de gebruikers kunnen alle signalen bekijken die in [ Data Explorer ](/help/using/features/data-explorer/data-explorer-overview.md) worden gevangen.

## Gevallen gebruiken {#use-cases}

### Gebruikerstoegang controleren {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] kan u helpen bij het controleren van de aanmeldingsstatus van de gebruiker, zodat u een duidelijk beeld krijgt van wie toegang heeft tot uw Audience Manager-instantie.

Afhankelijk van uw bedrijfsvereisten, kunt u gebruikersrekeningen toelaten en onbruikbaar maken zoals nodig.

![ monitor-gebruiker-toegang ](assets/monitor-user-access.png)

### Toegangsbeveiliging voor gevoelig [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

U kunt [!UICONTROL Role-Based Access Control] op [!UICONTROL trait] , segment, en [!UICONTROL destination] niveau, voor elke gebruikersgroep vormen.

Met deze functie kunt u beheren hoe uw gebruikers specifieke gegevenssets weergeven, maken, lezen, schrijven en bewerken en kunt u zelfs voorkomen dat gebruikers toegang krijgen tot gegevenssets die niet voor hen beschikbaar zouden moeten zijn.

![ toegang-bescherming ](assets/access-protection.png)
