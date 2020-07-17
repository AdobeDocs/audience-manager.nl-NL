---
description: Deze procedure begeleidt u door de stappen nodig om, een testgroep in het Laboratorium van de Auditie tot stand te brengen uit te geven of te schrappen
seo-description: Deze procedure begeleidt u door de stappen nodig om, een testgroep in het Laboratorium van de Auditie tot stand te brengen uit te geven of te schrappen
seo-title: Testgroepen beheren
solution: Audience Manager
title: Testgroepen beheren
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 0%

---


# Testgroepen beheren {#manage-test-groups}

Deze procedure begeleidt u door de stappen nodig om, een testgroep binnen tot stand te brengen uit te geven of te schrappen [!UICONTROL Audience Lab].

## Segmenttestgroepen maken {#create-test-groups}

### Vereisten

<!-- create-test-group.xml -->

* Er moet ten minste één **conversietraject** zijn ingesteld. U kunt omzettingskenmerken instellen in de [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md)door **conversie** als gebeurtenistype te selecteren. Voor meer informatie over welke omzettingskenmerken zijn en hoe te om hen te vestigen, hebben wij een [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) voor u voorbereid.

   >[!IMPORTANT]
   >
   >[Mapkenmerken](../../features/traits/about-folder-traits.md) worden **niet ondersteund** door [!UICONTROL Audience Lab]. Als u het [gebeurtenistype](../../features/traits/create-onboarded-rule-based-traits.md) van een mapkenmerk instelt op **conversie** , worden er geen gegevens gegenereerd [!UICONTROL Audience Lab] voor die specifieke mapeigenschap.

* Voor bedrijven die [Op rol-Gebaseerd Toegangsbeheer](../../features/administration/administration-overview.md)gebruiken: Wijs de [!UICONTROL Audience Lab] vervangingstoestemming [toe om toegang](../../features/administration/administration-overview.md#wild-card-permissions) **[!UICONTROL User Groups]** te verlenen. Met deze machtiging kan de gebruiker de resultaten van een test maken en bekijken. Een gebruiker zal segmenten van een gegevensbron slechts kunnen gebruiken zij **lezen** en **kaart aan bestemmingsvoorrechten** hebben. De gebruiker zal omzettingseigenschappen van een gegevensbron slechts kunnen gebruiken waarvoor zij **&quot;lees&quot;** toestemmingen hebben. Een gebruiker zal slechts bestemmingen kunnen zien zij tot ook toegang hebben. Zo, alvorens de [!DNL Audience Lab] vervangingstoestemming aan een groep toe te voegen, zorg ervoor de groep heeft:
   * toegang tot leesbare relevante omzettingskenmerken;
   * toegang tot lees- en kaartrelevante segmenten voor tests;
   * toegang tot relevante bestemmingen.

To create a new [!UICONTROL Segment Test Group]:

1. Selecteer **[!UICONTROL Create New Test Group]** in het [!UICONTROL Audience Lab] dashboard om de wizard te starten.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Vul een **[!UICONTROL Test Group Name]** en een **[!UICONTROL Description]**.
   * Kies de optie **[!UICONTROL Base Segment]** door in de bestandsbrowser te navigeren of door in de zoekbalk te typen, bevestig door op **[!UICONTROL Choose Segment.]**
   * U kunt de testgroep opslaan als een concept en er later opnieuw aan werken.
   * Er verschijnt een waarschuwing als het geselecteerde basissegment al in andere testgroepen wordt gebruikt. Het tweemaal gebruiken van het basissegment kan de omzettingsresultaten voor beide tests vervormen.

1. **[!UICONTROL Allocate Test Segments]**

   * U kunt **tot 15 testsegmenten** tot stand brengen en het percentage apparaten verdelen zoals u wenst.
   * U kunt de naam van de testsegmenten bewerken door erop te klikken.
   * De percentages worden automatisch gelijkmatig verdeeld naar 100% wanneer nieuwe testsegmenten worden toegewezen. U kunt de percentages vervolgens handmatig bewerken. Klik op het selectievakje nadat u de percentages hebt bewerkt en zorg ervoor dat ze optellen tot 100%. Als dit niet het geval is, kunt u niet verder gaan naar de volgende stap.

1. **[!UICONTROL Set a Control Segment]**

   * Selecteer een controlesegment als u een bepaald deel van het segment wilt opzij zetten dat als controlegroep moet worden gebruikt. Met controlegroepen kunt u de impact zien van de testsegmenten die u hebt gemaakt in vergelijking met een benchmark.
   * U kunt een testsegment als controlesegment in de drop-down lijst selecteren, of u kunt **[!UICONTROL None]** voor geen controle kiezen.
   * Klik **[!UICONTROL Next]** wanneer u klaar bent.

1. **[!UICONTROL Select Conversion Traits]**

   * Conversietekenmerken toevoegen door deze te typen in het venster Conversietekenmerken. Dit is een **verplichte** stap en u kunt alleen verdergaan met de volgende stap als u ten minste één conversietekenmerk toevoegt.
   * U kunt maximaal vijf conversietekenmerken desgewenst toevoegen.
   * Er verschijnt een waarschuwing voor het geval u een conversietekenmerk selecteert die al voor andere testgroepen wordt gebruikt.
   * Audience Manager biedt geen ondersteuning voor het gebruik van [mapkenmerken](/help/using/features/traits/about-folder-traits.md) als conversietekenmerken. Als u een mapkenmerk selecteert als conversietekenmerk, resulteert dit in 0 aggregaat- en trendrapporten die tijdens de test worden weergegeven.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Typ de gewenste doelen in het zoekveld of gebruik de vervolgkeuzepijl. [!UICONTROL Audience Lab] testsegmenten kunnen naar URL-, cookie- of server-naar-server doelen worden verzonden.
   * Segmenten naar bestemmingen slepen en neerzetten.
   * Nadat u een segment op een bestemming hebt neergezet, vult u het segment **[!UICONTROL Destination Mapping Value]** in de blinde.
   * U kunt het zelfde testsegment naar veelvoudige bestemmingen verzenden en u kunt veelvoudige testsegmenten aan één enkele bestemming toevoegen.
   * Doelen worden grijs weergegeven als ze niet beschikbaar zijn voor een bepaald testsegment op basis van [gegevensexportbesturingselementen](../../features/data-export-controls.md).
   * De gebruikers zullen slechts de bestemmingen zien zij tot gebaseerd op de [RBAC Gebruikersgroep](../../features/administration/administration-overview.md) hebben zij tot behoren.
   * Tot slot moet u een begindatum voor uw testgroep selecteren. Deze datum geeft het begin aan van de periode waarin uw testgroep wordt gepubliceerd naar bestemmingen. Selecteer **Geen einddatum** voor een onbepaalde vergelijking van de testsegmenten.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] met een geverifieerd profiel alleen worden ondersteund in realtime-doelen. Als een testsegment met een regel van de profielfusie van die configuratie naar een op dossier-gebaseerde server-aan-server bestemming wordt verzonden, zou het publiek niet kunnen bevolken.

   Klik **[!UICONTROL Next]** om uw testgroep te bekijken en te voltooien.

1. **[!UICONTROL Summary & Finalize]**

   * Controleer de gegevens die u in de vorige stappen hebt toegevoegd en selecteer **[!UICONTROL Finalize Group]**.
   * Vergeet niet dat een testgroep na het voltooien ervan kan worden gedupliceerd of verwijderd, maar niet kan worden bewerkt.

   >[!NOTE]
   >* U kunt de testgroepen op elk gewenst moment in het ontwerpproces opslaan en later terugkeren naar de wizard. De status van de testgroep zal zijn **[!UICONTROL Draft]** en de testgroep zal geen gegevens naar bestemmingen verzenden tot u de groep van de segmenttest voltooit.
   >* Voor ontwerp tests, kunt u terug gaan en de testgroepen uitgeven door in de kaart van de testgroep in de belangrijkste **[!UICONTROL Edit]** [!UICONTROL Audience Lab] mening te klikken.


## Testgroepen segment bewerken {#edit-test-groups}

In kunt [!UICONTROL Audience Lab]u alleen concepttestgroepen bewerken. In de [!UICONTROL Create Segment Test Group] tovenaar, kunt u uw testgroep als ontwerp opslaan en het werken aan het later hervatten.

1. Navigeer naar de [!UICONTROL Audience Lab] hoofdweergave.
1. Zoek naar uw ontwerp testgroepen en selecteer de **[!UICONTROL Edit]** controle in de kaart van de testgroep.
1. Hervat de [Create tovenaar van de Groep](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) van de Test van het Segment en selecteer **[!UICONTROL Finalize Group]** wanneer u wordt gedaan.

## Segmenttestgroepen verwijderen {#delete-test-groups}

1. Navigeer naar de [!UICONTROL Audience Lab] hoofdweergave.
1. Zoek de testgroep die u wilt verwijderen. U kunt:

   * de **[!UICONTROL Delete]** controle in de testgroepkaart drukken, of
   * Druk de titel van de testgroep in de kaart van de testgroep om naar de mening van de Informatie [van de Groep van de](../../features/audience-lab/audience-lab-information-view.md) Test te gaan en de **[!UICONTROL Delete]** controle in de titelbar te drukken.

1. Voor [voltooide testsegmenten](../../features/audience-lab/audience-lab.md#status), zal een alarm u ertoe aanzetten om het Csv- dossier te downloaden om het melden te bewaren als u wenst.
