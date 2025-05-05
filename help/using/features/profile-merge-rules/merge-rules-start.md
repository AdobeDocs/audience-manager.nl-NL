---
description: Als u de revisie Regels voor samenvoegen van profielen wilt maken, voert u de stappen uit in elk van de procedures die in deze sectie worden beschreven.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Aan de slag met de regels voor profielsamenvoeging
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 2%

---

# Aan de slag met de regels voor profielsamenvoeging {#getting-started-with-profile-merge-rules}

Om te creëren [!UICONTROL Profile Merge Rules]de stappen in elk van de in deze paragraaf beschreven procedures te evalueren en te voltooien.

<!-- merge-rules-start.xml -->

## Een apparaatgegevensbron maken {#create-data-source}

Ga naar **[!UICONTROL Audience Data > Data Sources > Add New]** en voltooi de stappen voor elke hier beschreven sectie. Beheerdersmachtigingen zijn vereist voor het maken of bewerken van een apparaatgegevensbron.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Zie [Instellingen gegevensbron en menuopties](../datasources-list-and-settings.md#settings-menu-options) voor beschrijvingen van deze verschillende besturingselementen.

## Gegevens gegevensbron {#details}

Als u het dialoogvenster [!UICONTROL Data Source Details] sectie:

1. Geef de gegevensbron een naam.
2. *(Optioneel)* Beschrijf de gegevensbron. Met een beknopte beschrijving kunt u de rol of het doel van de gegevensbron definiëren.
3. Geef een integratiecode op. Een integratiecode is uw eigen unieke id voor deze gegevensbron.
4. In de **[!UICONTROL ID Type]** list, selecteer **[!UICONTROL Cross Device]**.
5. In de **[!UICONTROL ID Definition]** selecteert u een optie die het type gegevensbron definieert. De volgende opties zijn beschikbaar:
   * **[!UICONTROL Person]**: Een id die één persoon definieert. Deze id kan worden toegewezen aan meerdere [!DNL Audience Manager] ID&#39;s.
   * **[!UICONTROL Household]**: Een id die een groep personen definieert. Deze id kan worden toegewezen aan meerdere [!DNL Audience Manager] ID&#39;s.

## Besturingselementen voor data-export {#export-controls}

[Besturingselementen voor gegevensexport](../data-export-controls.md) Dit zijn optionele classificatieregels die u kunt toepassen op een gegevensbron en een bestemming. Ze verhinderen dat u gegevens naar een bestemming verzendt wanneer die handeling een inbreuk vormt op de privacy van gegevens of een gebruiksovereenkomst. Deze sectie overslaan als u deze niet gebruikt [!UICONTROL Data Export Controls].

## Instellingen gegevensbron {#settings}

[!UICONTROL Data Source Settings] biedt meerdere opties, maar deze 2 zijn belangrijk voor het maken van een gegevensbron voor verschillende apparaten:

* **[!UICONTROL Use as Authenticated Profile]**: Deze instelling is standaard geselecteerd, zodat u een [!UICONTROL Profile Merge Rule] met uw eigen geverifieerde gegevens.

* **[!UICONTROL Use as a Device Graph]**: Deze controle is beschikbaar slechts aan rekeningen die als gegevensleverancier worden vermeld. Als u dit selectievakje inschakelt, wordt uw gegevensbron gemaakt als apparaatgrafiek en kunt u deze delen met andere gebruikers [!DNL Audience Manager] klanten. Werk met uw [!DNL Audience Manager] consultant om als gegevensaanbieder op te zetten en te specificeren welke klanten deze [!UICONTROL Data Source] moeten worden gedeeld met. Uw consultant zal uw account en apparaatgrafiek delen via een intern inrichtingsproces.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Met dit besturingselement kunt u de bewaarperiode voor inactieve id&#39;s van de klant instellen. Dit bepaalt hoe lang de Audience Manager identiteitskaart van de Klant in ons gegevensbestand houdt nadat zij het laatst op het platform van de Audience Manager werden gezien. De standaardwaarde is 24 maanden (720 dagen). De minimumwaarde die u kunt instellen is 1 maand en de maximumwaarde is 5 jaar. We tellen alle maanden als 30 dagen. Audience Manager voert een proces uit dat inactieve identiteitskaart van de Klant één keer per week schrapt, overeenkomstig het gegevensbehoud u voor inactieve identiteitskaart van de Klant plaatst.

Met de tekstvelden die aan deze instellingen zijn gekoppeld, kunt u de naam van de [!UICONTROL Data Source] met een alias die wordt weergegeven in het dialoogvenster [Opties voor regel voor samenvoegen van profiel](merge-rule-definitions.md). Als u bijvoorbeeld een alias toevoegt aan **[!UICONTROL Use as Authenticated Profile]**, wordt die naam weergegeven in het dialoogvenster [!UICONTROL Authenticated Profile Options] lijst. Als u een alias toevoegt aan **[!UICONTROL Use as a Device Graph]**, wordt die naam weergegeven in het dialoogvenster [!UICONTROL Device Options] lijst.

## Een regel voor het samenvoegen van profielen maken {#create-profile-merge-rule}

Als u een [!UICONTROL Profile Merge Rule], ga naar **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** en voltooi de stappen voor elke hier beschreven sectie.

U kunt maximaal drie samenvoegregels maken nadat u een gegevensbron voor meerdere apparaten hebt ingesteld. U krijgt toegang tot een vierde regel voor het samenvoegen van profielen ([!UICONTROL All Cross-Device Profiles]) als u zich aanmeldt voor [Bestemmingen op basis van personen](../destinations/people-based-destinations-overview.md).

Beheerdersmachtigingen zijn vereist voor het maken, bewerken of verwijderen van een regel. Alle gebruikers kunnen bestaande [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Vereisten:** Voor het samenstellen van een [!UICONTROL Profile Merge Rule]. Zie [Een gegevensbron maken](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Zie [Opties voor regel voor samenvoegen van profiel gedefinieerd](merge-rule-definitions.md) voor beschrijvingen van deze verschillende besturingselementen.

## Basisinformatie {#basic-info}

Als u het dialoogvenster [!UICONTROL Basic Information] sectie:

1. Geef de naam [!UICONTROL Profile Merge Rule].
2. *(Optioneel)* Beschrijf het [!UICONTROL Profile Merge Rule]. Een beknopte beschrijving helpt u de rol of het doel van uw regel bepalen.
3. *(Optioneel)* Selecteren **[!UICONTROL Set as default]** als u van dit het gebrek wilt maken [!UICONTROL Profile Merge Rule]. Nieuwe segmenten worden automatisch gekoppeld aan de standaardregel.

## Besturingselementen voor data-export {#data-export-controls}

[Besturingselementen voor gegevensexport](../data-export-controls.md) zijn optionele classificatieregels die u op uw [!UICONTROL Profile Merge Rule]. Ze verhinderen dat u gegevens naar een bestemming verzendt wanneer die handeling een inbreuk vormt op de privacy van gegevens of een gebruiksovereenkomst. Deze sectie overslaan als u deze niet gebruikt [!UICONTROL Data Export Controls].

## Opstelling van regel voor samenvoegen van profielen {#profile-merge-rule-setup}

Als u het dialoogvenster [!UICONTROL Proflie Merge Rule Setup] sectie:

1. Selecteer een **[!UICONTROL Authenticated Option]**. De volgende opties zijn beschikbaar:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selecteer een **[!UICONTROL Authenticated Profile Option]** (maximaal 3). Dit zijn de [apparaatgegevensbronnen](merge-rules-start.md) u eerder hebt gemaakt.
3. Selecteer een **[!UICONTROL Device Option]**. De volgende opties zijn beschikbaar:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Klik op **[!UICONTROL Save]**.

### Overwegingen bij Adobe Campaign-doelen die ID&#39;s voor andere apparaten gebruiken als gebruikersidentificatietoetsen {#considerations}

Eind 2019 hebben we een aantal verbeteringen in de regels voor het samenvoegen van profielen gepubliceerd om de nauwkeurigheid van batchbestanden die met id&#39;s voor meerdere apparaten zijn gegenereerd, te verbeteren. Deze verbeteringen worden strikt nageleefd in uw Audience Manager-instantie die op maandag 16 maart 2020 wordt gestart. Dientengevolge, zullen de segmenten die aan een bestemming worden in kaart gebracht gebruikend cross-device IDs ophouden producerend de uitvoer in sommige configuraties van de Regels van de Fusie van het Profiel.

Om de correcte integratie tussen uw instantie van de Audience Manager en bestemmingen te verzekeren gebruikend dwars-apparaat IDs, zoals Adobe Campaign, zorg ervoor u aan de volgende vereisten voldoet:

1. Controleer de regel voor het samenvoegen van profielen die wordt gebruikt door de segmenten die zijn toegewezen aan de bestemming van de door Adobe Campaign aangegeven id. De regel voor het samenvoegen van profielen moet de opdracht [!UICONTROL Last Authenticated Profile] zodat alle geverifieerde profielen in de exportbewerking kunnen worden opgenomen. Als de regel voor het samenvoegen van profielen een andere optie gebruikt, schakelt u deze over naar [!UICONTROL Last Authenticated Profile].
2. Selecteer de gegevensbron voor de Adobe Campaign-declaratie-id in de instellingen voor de regel voor het samenvoegen van profielen.

>[!NOTE]
>
> Als je het maximumaantal van [!UICONTROL Profile Merge Rules] en hebt hulp nodig bij het configureren van deze services op basis van de bovenstaande instructies. Neem contact op met de klantenservice.

## Code samenvoegregel configureren {#configure-merge-rule-code}

Volg deze instructies om [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL]en mobiele apparaten [!DNL SDK] code om met uw fusieregels te werken.

<!-- merge-rules-configure-code.xml -->

### Vereisten

U moet een [apparaatgegevensbron](#create-data-source) en [profielsamenvoegregels](#create-profile-merge-rule) *voor* de voltooiing van deze procedures.

## Voor klanten van Adobe Experience Platform Identity Service {#id-service-customers}

De [!UICONTROL Adobe Experience Platform Identity Service] en de meest recente versie van [DIL](../../dil/dil-overview.md) worden aanbevolen wanneer u werkt met [!UICONTROL Profile Merge Rules]. U hoeft echter niet de opdracht [!UICONTROL Adobe Experience Platform Identity Service] om met deze functie te werken. Als je gewoon [!UICONTROL DIL], zie de [verouderde DIL-sectie](#legacy-dil) hieronder.

### De functie Customer ID instellen configureren

Als u werkt met de [!UICONTROL Adobe Experience Platform Identity Service]de `setCustomerIDs` functie geeft gedeclareerde id&#39;s door aan [!DNL Audience Manager]. Als u een regel voor het samenvoegen van profielen wilt gebruiken, moet u `setCustomerIDs` om de integratiecode te gebruiken die is opgegeven toen u een apparaatgegevensbron maakte. Bijvoorbeeld, zeg u een dwars-apparatengegevensbron met de integratiecode hebt gecreeerd `my_datasource_ic`. Als u een gedeclareerde id wilt doorgeven, voegt u de integratiecode toe aan de functie bezoekersidentiteitskaart, zoals in het onderstaande gewijzigde codevoorbeeld wordt getoond.

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

Zie voor meer informatie [Een apparaatgegevensbron maken](#create-data-source) en [Klant-id&#39;s en verificatiestatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### Configureren `DIL.create` function

De meest recente versies van [!UICONTROL DIL] neemt nu automatisch de [!UICONTROL declared ID] van de `visitorService` functie in `DIL.create` (zie [Opgegeven id-variabelen](../declared-ids.md#declared-id-variables)). Controleer uw `DIL.create` om ervoor te zorgen dat deze op de juiste wijze is ingesteld, zoals in het onderstaande codevoorbeeld wordt getoond.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

In het naamruimte-sleutelwaardepaar `*`MCORG`*` variable is your [!DNL Experience Cloud] Organisatie-id. Als u deze id niet hebt, kunt u deze vinden in het dialoogvenster [!UICONTROL Administration] van de [!DNL Experience Cloud] dashboard. U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie [Beheer: Core Services](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### SDK&#39;s configureren

Zie de [SDK&#39;s configureren](#configure-sdks-legacy-dil) hieronder.

## Legacy DIL {#legacy-dil}

Als u dit niet gebruikt [!DNL Adobe Experience Platform Identity Service] toch moet je dat echt doen . Maar we begrijpen dat de overgang naar nieuwe code zorgvuldig moet worden overwogen en getest. Controleer in deze gevallen uw `DIL.create` om ervoor te zorgen dat deze op de juiste wijze is ingesteld, zoals in het onderstaande codevoorbeeld wordt getoond.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Zie de oudere versie voor meer informatie [!UICONTROL DIL] sectie in [Opgegeven id-variabelen](../declared-ids.md#declared-id-variables).

### SDK&#39;s configureren {#configure-sdks-legacy-dil}

Controleer de methoden in uw [!DNL SDK] code die u laat doorgeven [!UICONTROL declared IDs] van [!DNL Android] en [!DNL iOS] mobiele apparaten. De variabelenamen voor de [!DNL Android] en [!DNL iOS] codebibliotheken zijn hetzelfde:

* `dpid`: De bron-id voor het hele apparaat.
* `dpuuid`: De [!UICONTROL declared ID] (d.w.z. de gebruikersnaam).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type apparaat </th> 
   <th colname="col2" class="entry"> Methode </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntaxis:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Voorbeeld:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Syntaxis:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Voorbeeld:</b> </p><p>
    <code class="javascript">
      &lbrack;ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"&rbrack;;
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Zie ook: [Methoden voor Audience Manager voor Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) en [Methoden voor Audience Manager voor iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Een databron maken](../manage-datasources.md#create-data-source)

