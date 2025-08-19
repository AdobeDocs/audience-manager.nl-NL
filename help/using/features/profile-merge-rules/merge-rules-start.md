---
description: Als u de revisie Regels voor samenvoegen van profielen wilt maken, voert u de stappen uit in elk van de procedures die in deze sectie worden beschreven.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Aan de slag met regels voor het samenvoegen van profielen
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 0%

---

# Aan de slag met regels voor het samenvoegen van profielen {#getting-started-with-profile-merge-rules}

Als u [!UICONTROL Profile Merge Rules] wilt maken, controleert en voltooit u de stappen in elk van de procedures die in deze sectie worden beschreven.

<!-- merge-rules-start.xml -->

## Een Source voor apparaatoverschrijdende gegevens maken {#create-data-source}

Als u een apparaatgegevensbron wilt maken, gaat u naar **[!UICONTROL Audience Data > Data Sources > Add New]** en voert u de stappen uit voor elke sectie die hier wordt beschreven. Beheerdersmachtigingen zijn vereist voor het maken of bewerken van een apparaatgegevensbron.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Zie {de Montages van Source van 0} Gegevens en de Opties van het Menu [ voor beschrijvingen van deze verschillende controles.](../datasources-list-and-settings.md#settings-menu-options)

## Gegevens Source {#details}

De sectie [!UICONTROL Data Source Details] voltooien:

1. Geef de gegevensbron een naam.
2. *(Facultatief)* beschrijf de gegevensbron. Met een beknopte beschrijving kunt u de rol of het doel van de gegevensbron definiëren.
3. Geef een integratiecode op. Een integratiecode is uw eigen unieke id voor deze gegevensbron.
4. Selecteer **[!UICONTROL ID Type]** in de lijst **[!UICONTROL Cross Device]** .
5. Selecteer in de lijst **[!UICONTROL ID Definition]** een optie die het type gegevensbron definieert. U kunt onder andere de volgende opties kiezen:
   * **[!UICONTROL Person]**: Een id die één persoon definieert. Deze id kan aan meerdere [!DNL Audience Manager] id&#39;s worden toegewezen.
   * **[!UICONTROL Household]**: Een id die een groep personen definieert. Deze id kan aan meerdere [!DNL Audience Manager] id&#39;s worden toegewezen.

## Besturingselementen voor gegevensexport {#export-controls}

[ de Controles van de Uitvoer van Gegevens ](../data-export-controls.md) zijn facultatieve classificatieregels u op een gegevensbron en een bestemming kunt toepassen. Ze verhinderen dat u gegevens naar een bestemming verzendt wanneer die handeling een inbreuk vormt op de privacy van gegevens of een gebruiksovereenkomst. Sla deze sectie over als u [!UICONTROL Data Export Controls] niet gebruikt.

## Source-instellingen voor gegevens {#settings}

[!UICONTROL Data Source Settings] biedt meerdere opties, maar deze 2 zijn belangrijk voor het maken van een gegevensbron voor verschillende apparaten:

* **[!UICONTROL Use as Authenticated Profile]**: Deze instelling is standaard geselecteerd. Hiermee kunt u een [!UICONTROL Profile Merge Rule] met uw eigen, geverifieerde gegevens maken.

* **[!UICONTROL Use as a Device Graph]**: Dit besturingselement is alleen beschikbaar voor accounts die zijn opgenomen als gegevensaanbieder. Als u dit selectievakje inschakelt, wordt uw gegevensbron gemaakt als een apparaatgrafiek en kunt u deze delen met andere klanten van [!DNL Audience Manager] . Werk samen met uw [!DNL Audience Manager] -consultant om een gegevensaanbieder op te zetten en op te geven met welke klanten deze [!UICONTROL Data Source] moet worden gedeeld. Uw consultant zal uw account en apparaatgrafiek delen via een intern inrichtingsproces.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Met dit besturingselement kunt u de bewaarperiode voor inactieve id&#39;s van de klant instellen. Dit bepaalt hoe lang Audience Manager de id&#39;s van de Klant in onze database bewaart nadat ze voor het laatst op het Audience Manager-platform zijn gezien. De standaardwaarde is 24 maanden (720 dagen). De minimumwaarde die u kunt instellen is 1 maand en de maximumwaarde is 5 jaar. We tellen alle maanden als 30 dagen. Audience Manager voert een proces uit dat inactieve klant-id&#39;s één keer per week verwijdert, in overeenstemming met de gegevensopslag die u hebt ingesteld voor niet-actieve klant-id&#39;s.

De tekstgebieden verbonden aan deze montages laten u [!UICONTROL Data Source] met een alias anders noemen die in de [ opties van de Regel van de Fusie van het Profiel ](merge-rule-definitions.md) verschijnt. Als u bijvoorbeeld een alias toevoegt aan **[!UICONTROL Use as Authenticated Profile]** , wordt die naam weergegeven in de lijst [!UICONTROL Authenticated Profile Options] . Als u een alias aan **[!UICONTROL Use as a Device Graph]** toevoegt, verschijnt die naam in de [!UICONTROL Device Options] lijst.

## Een regel voor het samenvoegen van profielen maken {#create-profile-merge-rule}

Als u een [!UICONTROL Profile Merge Rule] wilt maken, gaat u naar **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** en voert u de stappen uit voor elke sectie die hier wordt beschreven.

U kunt maximaal drie samenvoegregels maken nadat u een gegevensbron voor meerdere apparaten hebt ingesteld. U krijgt toegang tot een 4de Regel van de Fusie van het Profiel ([!UICONTROL All Cross-Device Profiles]) als u omhoog voor [ Op mensen-Gebaseerde Doelen ](../destinations/people-based-destinations-overview.md) ondertekent.

Beheerdersmachtigingen zijn vereist voor het maken, bewerken of verwijderen van een regel. Alle gebruikers kunnen bestaande [!UICONTROL Profile Merge Rules] weergeven en gebruiken.

<!-- create-profile-merge-rule.xml -->

**Vereisten:** Een dwars-apparatengegevensbron wordt vereist om a [!UICONTROL Profile Merge Rule] te bouwen. Zie [ een Gegevens Source ](../manage-datasources.md#create-data-source) creëren.

>[!TIP]
>
>Zie {de Opties van de Regel van de Samenvoeging van 0} Gedefinieerd [ voor beschrijvingen van deze verschillende controles.](merge-rule-definitions.md)

## Basisinformatie {#basic-info}

De sectie [!UICONTROL Basic Information] voltooien:

1. Geef de [!UICONTROL Profile Merge Rule] een naam.
2. *(Facultatief)* beschrijf [!UICONTROL Profile Merge Rule]. Een beknopte beschrijving helpt u de rol of het doel van uw regel bepalen.
3. *(Optioneel)* Selecteer **[!UICONTROL Set as default]** als u dit als de standaardinstelling wilt instellen [!UICONTROL Profile Merge Rule] . Nieuwe segmenten worden automatisch gekoppeld aan de standaardregel.

## Besturingselementen voor gegevensexport {#data-export-controls}

[ de Controles van de Uitvoer van Gegevens ](../data-export-controls.md) zijn facultatieve classificatieregels u op uw [!UICONTROL Profile Merge Rule] kunt toepassen. Ze verhinderen dat u gegevens naar een bestemming verzendt wanneer die handeling een inbreuk vormt op de privacy van gegevens of een gebruiksovereenkomst. Sla deze sectie over als u [!UICONTROL Data Export Controls] niet gebruikt.

## Opstelling van regel voor samenvoegen van profielen {#profile-merge-rule-setup}

De sectie [!UICONTROL Proflie Merge Rule Setup] voltooien:

1. Selecteer een **[!UICONTROL Authenticated Option]** . U kunt onder andere de volgende opties kiezen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selecteer een **[!UICONTROL Authenticated Profile Option]** (maximaal 3). Dit zijn de [ bronnen van dwars-apparatengegevens ](merge-rules-start.md) u eerder hebt gecreeerd.
3. Selecteer een **[!UICONTROL Device Option]** . U kunt onder andere de volgende opties kiezen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Klik op **[!UICONTROL Save]**.

### Overwegingen bij Adobe Campaign-doelen die ID&#39;s voor andere apparaten gebruiken als gebruikersidentificatietoetsen {#considerations}

Eind 2019 hebben we een aantal verbeteringen in de regels voor het samenvoegen van profielen gepubliceerd om de nauwkeurigheid van batchbestanden die met id&#39;s voor meerdere apparaten zijn gegenereerd, te verbeteren. Deze verbeteringen worden strikt nageleefd in uw Audience Manager-exemplaar vanaf maandag 16 maart 2020. Dientengevolge, zullen de segmenten die aan een bestemming worden in kaart gebracht gebruikend cross-device IDs ophouden producerend de uitvoer in sommige configuraties van de Regels van de Fusie van het Profiel.

Om de correcte integratie tussen uw Audience Manager-instantie en bestemmingen te verzekeren die gebruik maken van apparaat-id&#39;s, zoals Adobe Campaign, moet u aan de volgende vereisten voldoen:

1. Controleer de regel voor het samenvoegen van profielen die wordt gebruikt door de segmenten die zijn toegewezen aan de bestemming van de door Adobe Campaign aangegeven id. De regel voor het samenvoegen van profielen moet de optie [!UICONTROL Last Authenticated Profile] gebruiken, zodat alle geverifieerde profielen kunnen worden opgenomen in de exportbewerking. Als de regel voor het samenvoegen van profielen een andere optie gebruikt, schakelt u deze over naar [!UICONTROL Last Authenticated Profile] .
2. Selecteer de gegevensbron voor de Adobe Campaign-declaratie-id in de instellingen voor de regel voor het samenvoegen van profielen.

>[!NOTE]
>
> Als u uw maximumaantal [!UICONTROL Profile Merge Rules] hebt bereikt en hulp nodig hebt bij het configureren van deze op basis van de bovenstaande instructies, neemt u contact op met de klantenservice.

## Code samenvoegregel configureren {#configure-merge-rule-code}

Volg deze instructies om de code [!UICONTROL Adobe Experience Platform Identity Service] , [!UICONTROL DIL] en mobile [!DNL SDK] zo in te stellen dat deze met de samenvoegregels werken.

<!-- merge-rules-configure-code.xml -->

### Vereisten

U moet opstelling a [ dwars-apparatengegevensbron ](#create-data-source) en [ de regels van de profielfusie ](#create-profile-merge-rule) *alvorens* voltooit deze procedures.

## Voor klanten van Adobe Experience Platform Identity Service {#id-service-customers}

[!UICONTROL Adobe Experience Platform Identity Service] en de recentste versie van [ DIL ](../../dil/dil-overview.md) worden geadviseerd wanneer het werken met [!UICONTROL Profile Merge Rules]. U hoeft de [!UICONTROL Adobe Experience Platform Identity Service] echter niet te gebruiken om met deze functie te werken. Als u enkel [!UICONTROL DIL] gebruikt, zie de [ sectie van erfenisDIL ](#legacy-dil) hieronder.

### De functie Customer ID instellen configureren

Wanneer de functie [!UICONTROL Adobe Experience Platform Identity Service] gebruikt, geeft de functie `setCustomerIDs` gedeclareerde id&#39;s door aan [!DNL Audience Manager] . Als u een regel voor het samenvoegen van profielen wilt gebruiken, moet u `setCustomerIDs` wijzigen om de integratiecode te gebruiken die is opgegeven bij het maken van een apparaatgegevensbron. Stel dat u een gegevensbron voor meerdere apparaten hebt gemaakt met de integratiecode `my_datasource_ic` . Als u een gedeclareerde id wilt doorgeven, voegt u de integratiecode toe aan de functie bezoekersidentiteitskaart, zoals in het onderstaande gewijzigde codevoorbeeld wordt getoond.

#### Generic code sample

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Voorbeeld van gewijzigde code

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Voor meer informatie, zie [ een Gegevens van het Apparaat Source ](#create-data-source) en [ Klantidentiteitskaarts en de Staten van de Authentificatie ](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=nl-NL) creëren.

### Functie `DIL.create` configureren

De recentste versies van [!UICONTROL DIL] nemen nu automatisch [!UICONTROL declared ID] van de `visitorService` functie in `DIL.create` op (zie [ Verklaarde Variabelen van identiteitskaart ](../declared-ids.md#declared-id-variables)). Controleer of de functie `DIL.create` correct is ingesteld, zoals in het onderstaande codevoorbeeld wordt getoond.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

In het namespace zeer belangrijk-waardepaar, is de `*` MCORG `*` variabele uw [!DNL Experience Cloud] identiteitskaart van de Organisatie. Als u deze id niet hebt, vindt u deze in de sectie [!UICONTROL Administration] van het dashboard van [!DNL Experience Cloud] . U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie [ Beleid: De Diensten van de Kern ](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=nl-NL).

### SDK&#39;s configureren

Zie [ vormen SDKs ](#configure-sdks-legacy-dil) hieronder sectie.

## Legacy DIL {#legacy-dil}

Als u [!DNL Adobe Experience Platform Identity Service] nog niet gebruikt, moet u dat echt doen. Maar we begrijpen dat de overgang naar nieuwe code zorgvuldig moet worden overwogen en getest. Controleer in deze gevallen de functie `DIL.create` om te controleren of deze op de juiste wijze is ingesteld, zoals in het onderstaande codevoorbeeld wordt getoond.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Voor meer informatie, zie de erfenis [!UICONTROL DIL] sectie in [ Gedeclareerde Variabelen van identiteitskaart ](../declared-ids.md#declared-id-variables).

### SDK&#39;s configureren {#configure-sdks-legacy-dil}

Controleer de methoden in uw [!DNL SDK] -code waarmee u [!UICONTROL declared IDs] van [!DNL Android] - en [!DNL iOS] mobiele apparaten kunt doorgeven. De variabelenamen voor de codebibliotheken [!DNL Android] en [!DNL iOS] zijn hetzelfde:

* `dpid`: De bron-id voor alle apparaten.
* `dpuuid`: De [!UICONTROL declared ID] (de gebruikers-id).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Apparaattype </th> 
   <th colname="col2" class="entry"> Methode </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b> Syntaxis:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b> Voorbeeld:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b> Syntaxis:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b> Voorbeeld:</b> </p><p>
    <code class="javascript">
      &lbrack;ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"&rbrack;;
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Zie ook, [ Methoden van Audience Manager voor Android ](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html?lang=nl-NL) en [ methodes van Audience Manager voor iOS ](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html?lang=nl-NL).

>[!MORELIKETHIS]
>
>* [Een databron maken](../manage-datasources.md#create-data-source)
