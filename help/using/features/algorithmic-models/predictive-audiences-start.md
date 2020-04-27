---
description: Met voorspellende doelgroepen kunt u een onbekend publiek in real-time in verschillende personen indelen met behulp van gegevenswetenschap.
seo-description: Met voorspellende doelgroepen kunt u een onbekend publiek in real-time in verschillende personen indelen met behulp van gegevenswetenschap.
seo-title: Voorspelend publiek beheren
solution: Audience Manager
title: Voorspelend publiek van Auditiebeheer
translation-type: tm+mt
source-git-commit: 8259f07c91efa0efd88e8f7c87cb1829ffadd77d

---


# Aan de slag met voorspellend publiek {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

## Een voorspellend model voor soorten publiek maken {#create-predictive-audiences}

Alvorens u een [!UICONTROL Predictive Audiences] model creeert, moet u beslissen welke bron van eerste-partijgegevens u uw [!UICONTROL Predictive Audiences] eigenschappen en segmenten aan wilt toewijzen. U kunt een bestaande bron van eerste-partijgegevens gebruiken, of nieuwe creëren. Zie Gegevensbronnen [](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) beheren voor meer informatie over het maken van een nieuwe gegevensbron van de eerste partij.

Volg de onderstaande stappen als u weet welke gegevensbron u wilt gebruiken.

1. Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Klik in de [!UICONTROL Predictive Audiences] sectie op **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Definieer vervolgens de personen waarop u de doelgroep wilt classificeren. U kunt dit doen door of eigenschappen of segmenten te kiezen om persona&#39;s van te bouwen. Gebruik de tabbladen [!UICONTROL Traits] en [!UICONTROL Segments] tabbladen in de linkerbovenhoek van het scherm om te schakelen tussen de catalogus met kenmerken en segmenten. Nadat u de kenmerken of segmenten hebt geïdentificeerd die u als personen wilt gebruiken, klikt u op het bijbehorende **[!UICONTROL Add]** pictogram in de [!UICONTROL Action] kolom.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >U moet een minimum van of twee eigenschappen of twee segmenten voor uw basislijnpersona&#39;s kiezen. U kunt geen combinatie van zowel kenmerken als segmenten gebruiken.
1. Klik **[!UICONTROL Next]** nadat u uw persona&#39;s hebt bepaald.
1. Selecteer vervolgens het publiek van de eerste partij dat u wilt classificeren door een eersteklas kenmerk of segment voor dit publiek te kiezen. Gebruik de tabbladen [!UICONTROL Traits] en [!UICONTROL Segments] tabbladen in de linkerbovenhoek van het scherm om te schakelen tussen de catalogus met kenmerken en segmenten. Selecteer de eigenschap of het segment van de eerste partij die u als uw publiek wilt gebruiken, om het aan het model toe te voegen.
   ![smart-persona-select-publiek](assets/predictive-audiences-audience.png)
1. Klik **[!UICONTROL Next]** nadat u uw publiek hebt gekozen.
1. Vul de modelgegevens in:
   1. **[!UICONTROL Model Name]**: Voer een beschrijvende naam in voor het model, zodat u het later kunt herkennen. De namen van de segmenten die door het model worden gegenereerd, beginnen met de naam van het model.
   2. **[!UICONTROL Description]**: Voer een beschrijving in van het model dat u helpt bij het identificeren van het gebruikte hoofdlettergebruik.
   3. **[!UICONTROL Data Source]**: Selecteer de eerste gegevensbron waaraan u de [!UICONTROL Predictive Audiences] segmenten van dit model wilt toewijzen.
      ![voorspellend publiek-sparen](assets/predictive-audiences-save.png)
1. Klik op **[!UICONTROL Save]**.

## Voorspelend publiek bewerken {#edit-predictive-audiences}

Audience Manager biedt geen ondersteuning voor het bewerken van bestaande [!UICONTROL Predictive Audiences] modellen. Als u de configuratie van een model wilt wijzigen, moet u een nieuw model maken. Als u de limiet van 10 [!UICONTROL Predictive Audiences] modellen hebt bereikt en een van uw modellen moet bewerken, moet u een model verwijderen en een nieuw model maken.

## Voorspelend publiek verwijderen {#delete-predictive-audiences}

Als u een [!UICONTROL Predictive Audiences] model wilt verwijderen, gaat u naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, zoekt u het model dat u wilt verwijderen en klikt u op het **[!UICONTROL Delete]** pictogram.
