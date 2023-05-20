---
description: Deze procedure begeleidt u door de stappen nodig om, een testgroep in het Laboratorium van de Auditie tot stand te brengen uit te geven of te schrappen
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Testgroepen beheren
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# Testgroepen beheren {#manage-test-groups}

Deze procedure begeleidt u door de stappen nodig om, een testgroep binnen tot stand te brengen uit te geven of te schrappen [!UICONTROL Audience Lab].

## Segmenttestgroepen maken {#create-test-groups}

### Vereisten

<!-- create-test-group.xml -->

* U moet minstens één **conversietaak** ingesteld. U kunt omzettingskenmerken instellen in het dialoogvenster [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md)door **conversie** als het gebeurtenistype. We hebben een [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) voor jou.

   >[!IMPORTANT]
   >
   >[Mapkenmerken](../../features/traits/about-folder-traits.md) zijn **niet ondersteund** door [!UICONTROL Audience Lab]. De instelling [Type gebeurtenis](../../features/traits/create-onboarded-rule-based-traits.md) van een mapkenmerk naar **conversie** geen gegevens genereren in [!UICONTROL Audience Lab] voor die specifieke mapkenmerken.

* Voor bedrijven die [Op rollen gebaseerd toegangsbeheer](../../features/administration/administration-overview.md): Wijs het [!UICONTROL Audience Lab] [jokerteken, machtiging](../../features/administration/administration-overview.md#wild-card-permissions) tot **[!UICONTROL User Groups]** om toegang te verlenen. Met deze machtiging kan de gebruiker de resultaten van een test maken en bekijken. Een gebruiker zal segmenten van een gegevensbron slechts kunnen gebruiken zij hebben **lezen** en **toewijzen aan bestemming** rechten voor. De gebruiker zal omzettingseigenschappen van een gegevensbron slechts kunnen gebruiken waarvoor zij hebben **&quot;read&quot;** machtigingen. Een gebruiker zal slechts bestemmingen kunnen zien zij tot ook toegang hebben. Dus voordat u de [!DNL Audience Lab] jokerteken toestemming aan een groep, zorg ervoor de groep heeft:
   * toegang tot leesbare relevante omzettingskenmerken;
   * toegang tot lees- en kaartrelevante segmenten voor tests;
   * toegang tot relevante bestemmingen.

Een nieuwe [!UICONTROL Segment Test Group]:

1. Selecteren **[!UICONTROL Create New Test Group]** in de [!UICONTROL Audience Lab] dashboard om de wizard te starten.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Een **[!UICONTROL Test Group Name]** en **[!UICONTROL Description]**.
   * Kies de optie **[!UICONTROL Base Segment]** door in de bestandsbrowser te navigeren of door in de zoekbalk te typen, bevestigt u dit door op **[!UICONTROL Choose Segment.]**
   * U kunt de testgroep opslaan als een concept en er later opnieuw aan werken.
   * Er verschijnt een waarschuwing als het geselecteerde basissegment al in andere testgroepen wordt gebruikt. Het tweemaal gebruiken van het basissegment kan de omzettingsresultaten voor beide tests vervormen.

1. **[!UICONTROL Allocate Test Segments]**

   * U kunt **tot 15 testsegmenten** en verdeel het percentage apparaten zoals u wenst.
   * U kunt de naam van de testsegmenten bewerken door erop te klikken.
   * De percentages worden automatisch gelijkmatig verdeeld naar 100% wanneer nieuwe testsegmenten worden toegewezen. U kunt de percentages vervolgens handmatig bewerken. Klik op het selectievakje nadat u de percentages hebt bewerkt en zorg ervoor dat ze optellen tot 100%. Als dit niet het geval is, kunt u niet verder gaan naar de volgende stap.

1. **[!UICONTROL Set a Control Segment]**

   * Selecteer een controlesegment als u een bepaald deel van het segment wilt opzij zetten dat als controlegroep moet worden gebruikt. Met controlegroepen kunt u de impact zien van de testsegmenten die u hebt gemaakt in vergelijking met een benchmark.
   * U kunt een testsegment selecteren als controlesegment in de drop-down lijst, of u kunt kiezen **[!UICONTROL None]** zonder controle.
   * Klikken **[!UICONTROL Next]** als je klaar bent.

1. **[!UICONTROL Select Conversion Traits]**

   * Conversietekenmerken toevoegen door deze te typen in het venster Conversietekenmerken. Dit is een **verplicht** stap en u kunt niet verder gaan naar de volgende stap, tenzij u ten minste één omzettingskenmerk toevoegt.
   * U kunt maximaal vijf conversietekenmerken desgewenst toevoegen.
   * Er verschijnt een waarschuwing voor het geval u een conversietekenmerk selecteert die al voor andere testgroepen wordt gebruikt.
   * Audience Manager ondersteunt het gebruik van [mapkenmerken](/help/using/features/traits/about-folder-traits.md) als omzettingskenmerken. Als u een mapkenmerk selecteert als conversietekenmerk, resulteert dit in 0 aggregaat- en trendrapporten die tijdens de test worden weergegeven.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Typ de gewenste doelen in het zoekveld of gebruik de vervolgkeuzepijl. [!UICONTROL Audience Lab] testsegmenten kunnen naar URL-, cookie- of server-naar-server doelen worden verzonden.
   * Segmenten naar bestemmingen slepen en neerzetten.
   * Nadat u een segment in een doel hebt neergezet, vult u de **[!UICONTROL Destination Mapping Value]** in de blinde.
   * U kunt het zelfde testsegment naar veelvoudige bestemmingen verzenden en u kunt veelvoudige testsegmenten aan één enkele bestemming toevoegen.
   * Doelen worden grijs weergegeven als ze niet beschikbaar zijn voor een bepaald testsegment op basis van [Besturingselementen voor gegevensexport](../../features/data-export-controls.md).
   * De gebruikers zullen slechts de bestemmingen zien die zij hebben tot gebaseerd op [RBAC-gebruikersgroep](../../features/administration/administration-overview.md) ze horen tot.
   * Tot slot moet u een begindatum voor uw testgroep selecteren. Deze datum geeft het begin aan van de periode waarin uw testgroep wordt gepubliceerd naar bestemmingen. Selecteren **Geen einddatum** voor een onbeperkte vergelijking van de testsegmenten.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] met een geverifieerd profiel alleen worden ondersteund in realtime-doelen. Als een testsegment met een regel van de profielfusie van die configuratie naar een op dossier-gebaseerde server-aan-server bestemming wordt verzonden, zou het publiek niet kunnen bevolken.

   Klikken **[!UICONTROL Next]** om uw testgroep te bekijken en te voltooien.

1. **[!UICONTROL Summary & Finalize]**

   * Controleer de gegevens die u in de vorige stappen hebt toegevoegd en selecteer **[!UICONTROL Finalize Group]**.
   * Vergeet niet dat een testgroep na het voltooien ervan kan worden gedupliceerd of verwijderd, maar niet kan worden bewerkt.

   >[!NOTE]
   >* U kunt de testgroepen op elk gewenst moment in het ontwerpproces opslaan en later terugkeren naar de wizard. De status van de testgroep wordt **[!UICONTROL Draft]** en de testgroep zal geen gegevens naar bestemmingen verzenden tot u de groep van de segmenttest voltooit.
   >* Voor concepttests kunt u teruggaan en de testgroepen bewerken door op **[!UICONTROL Edit]** in de testgroepkaart in het hoofdgedeelte [!UICONTROL Audience Lab] weergeven.


## Testgroepen segment bewerken {#edit-test-groups}

In [!UICONTROL Audience Lab]U kunt alleen concepttestgroepen bewerken. In de [!UICONTROL Create Segment Test Group] kunt u de testgroep opslaan als een concept en er later opnieuw aan werken.

1. Ga naar de [!UICONTROL Audience Lab] hoofdweergave.
1. Zoek uw concept testgroepen en selecteer de **[!UICONTROL Edit]** controle in de testgroepkaart.
1. De [Testgroep segment maken](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) wizard en selecteert u **[!UICONTROL Finalize Group]** als je klaar bent.

## Segmenttestgroepen verwijderen {#delete-test-groups}

1. Ga naar de [!UICONTROL Audience Lab] hoofdweergave.
1. Zoek de testgroep die u wilt verwijderen. U kunt:

   * de **[!UICONTROL Delete]** controle in de testgroepkaart, of
   * druk de titel van de testgroep in de kaart van de testgroep om naar [Gegevens testgroep](../../features/audience-lab/audience-lab-information-view.md) de mening en drukt **[!UICONTROL Delete]** in de titelbalk.

1. Voor [voltooide testsegmenten](../../features/audience-lab/audience-lab.md#status), wordt u in een waarschuwing gevraagd het CSV-bestand te downloaden om de melding indien gewenst op te slaan.
