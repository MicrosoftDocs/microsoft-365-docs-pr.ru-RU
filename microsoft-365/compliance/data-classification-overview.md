---
title: Начало работы с классификацией данных (предварительная версия)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Панель мониторинга классификации данных дает вам наглядное представление о количестве найденных и классифицированных конфиденциальных данных в вашей организации.
ms.openlocfilehash: 76c1199fa3842428900db197f15728c116f778b9
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076412"
---
# <a name="data-classification-overview-preview"></a><span data-ttu-id="2240c-103">Общие сведения о классификации данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="2240c-103">Data classification overview (preview)</span></span>

<span data-ttu-id="2240c-104">В качестве администратора Microsoft 365 или администратора соответствия вы можете оценивать и затем маркировать содержимое в своей организации, чтобы контролировать путь его направления, защищать вне зависимости от расположения, а также гарантировать его сохранность и удаление в соответствии с потребностями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2240c-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according your your organizations needs.</span></span> <span data-ttu-id="2240c-105">Это можно сделать посредством применения [меток конфиденциальности](sensitivity-labels.md), [меток хранения](labels.md)и классификации типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="2240c-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](labels.md), and sensitive information type classification.</span></span> <span data-ttu-id="2240c-106">Существуют различные способы обнаружения, оценки и маркировки, но в результате у вас может быть очень большое количество документов и электронных писем, которые помечены и классифицированы одной или обеими этими метками.</span><span class="sxs-lookup"><span data-stu-id="2240c-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large numbers of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="2240c-107">После применения своих меток хранения и меток конфиденциальности вы захотите увидеть, каким образом метки используются вашим клиентом и что происходит с этими элементами.</span><span class="sxs-lookup"><span data-stu-id="2240c-107">After you apply  your retention labels and sensitivity labels, you’ll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="2240c-108">На странице классификации данных можно увидеть этот текст содержимого, а именно:</span><span class="sxs-lookup"><span data-stu-id="2240c-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="2240c-109">количество элементов, которые были классифицированы как тип конфиденциальной информации, и характер этих классификаций</span><span class="sxs-lookup"><span data-stu-id="2240c-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="2240c-110">наиболее часто используемые метки конфиденциальности, применяемые в Microsoft 365 и Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="2240c-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="2240c-111">наиболее часто используемые метки хранения</span><span class="sxs-lookup"><span data-stu-id="2240c-111">the top applied retention labels</span></span>
- <span data-ttu-id="2240c-112">сводка действий, выполняемых пользователями с вашим конфиденциальным содержимым</span><span class="sxs-lookup"><span data-stu-id="2240c-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="2240c-113">расположение ваших конфиденциальных и сохраненных данных</span><span class="sxs-lookup"><span data-stu-id="2240c-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="2240c-114">Классификация данных приведена в **Центре соответствия требованиям Microsoft 365** или **Центре безопасности Microsoft 365** > **Классификация** > **Классификация данных**.</span><span class="sxs-lookup"><span data-stu-id="2240c-114">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="2240c-115">Типы конфиденциальных данных, которые наиболее часто используются в вашем содержимом</span><span class="sxs-lookup"><span data-stu-id="2240c-115">Sensitive information types used most in your content</span></span>

<span data-ttu-id="2240c-116">Microsoft 365 поставляется со многими определениями типов конфиденциальной информации, такими как элемент, содержащий номер социального страхования или номер кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="2240c-116">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="2240c-117">Дополнительные сведения о типах конфиденциальной информации см. в статье [Что позволяют искать типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2240c-117">For more information on sensitive information types, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="2240c-118">На карточке типа конфиденциальной информации отображаются наиболее часто используемые типы конфиденциальной информации, которые были найдены и помечены в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2240c-118">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![наиболее часто используемые типы конфиденциальной информации](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="2240c-120">Чтобы узнать количество элементов в той или иной категории классификации, наведите указатель мыши на панель этой категории.</span><span class="sxs-lookup"><span data-stu-id="2240c-120">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![наиболее часто используемые типы конфиденциальной информации, сведения при наведении](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="2240c-122">Если на карточке отображается сообщение «Данные с конфиденциальной информацией не найдены»,</span><span class="sxs-lookup"><span data-stu-id="2240c-122">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="2240c-123">то это означает, что в вашей организации отсутствуют элементы, классифицированные как тип конфиденциальной информации, или отсутствуют обойденные элементы.</span><span class="sxs-lookup"><span data-stu-id="2240c-123">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="2240c-124">Чтобы приступить к работе с метками, см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="2240c-124">To get started with labels, see:</span></span>
>- [<span data-ttu-id="2240c-125">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="2240c-125">Sensitivity labels</span></span>](sensitivity-labels.md)
>- [<span data-ttu-id="2240c-126">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="2240c-126">Retention labels</span></span>](labels.md)
>- [<span data-ttu-id="2240c-127">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="2240c-127">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="2240c-128">Наиболее часто используемые метки конфиденциальности, применяемые для содержимого</span><span class="sxs-lookup"><span data-stu-id="2240c-128">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="2240c-129">Когда вы применяете метку конфиденциальности к элементу с использованием Microsoft 365 или Azure Information Protection (AIP), то происходят две вещи:</span><span class="sxs-lookup"><span data-stu-id="2240c-129">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="2240c-130">тег, который обозначает значение элемента для вашей организации, встраивается в документ и будет повсюду следовать за ним</span><span class="sxs-lookup"><span data-stu-id="2240c-130">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="2240c-131">наличие тега включает различные защитные действия, такие как обязательные водяные знаки или шифрование.</span><span class="sxs-lookup"><span data-stu-id="2240c-131">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="2240c-132">С включенной защитой конечной точки вы можете даже не позволить элементу выйти из под управления вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2240c-132">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="2240c-133">Дополнительные сведения о метках конфиденциальности см. в статье [Сведения о метках конфиденциальности](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="2240c-133">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="2240c-134">Для файлов SharePoint и OneDrive должны быть включены метки конфиденциальности, чтобы соответствующие данные отображались на странице классификации данных.</span><span class="sxs-lookup"><span data-stu-id="2240c-134">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="2240c-135">Дополнительные сведения см. в статье [Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная предварительная версия)](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="2240c-135">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="2240c-136">На карточке с меткой конфиденциальности отображается количество элементов (электронная почта или документ) по уровню конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="2240c-136">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![разбивка содержимого по снимку замещающего текста классификации метки конфиденциальности](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="2240c-138">Если вы не создали или не опубликовали какие-либо метки конфиденциальности или к содержимому не применена метка конфиденциальности, то на этой карточке будет отображаться сообщение «Метки конфиденциальности не обнаружены».</span><span class="sxs-lookup"><span data-stu-id="2240c-138">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="2240c-139">Чтобы приступить к работе с метками, см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="2240c-139">To get started with labels, see:</span></span>
>- <span data-ttu-id="2240c-140">[метки конфиденциальности](sensitivity-labels.md) или для AIP [Настройка политики защиты данных Azure](https://docs.microsoft.com/azure/information-protection/configure-policy)</span><span class="sxs-lookup"><span data-stu-id="2240c-140">[sensitivity labels](sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="2240c-141">Наиболее часто используемые метки хранения, применяемые для содержимого</span><span class="sxs-lookup"><span data-stu-id="2240c-141">Top retention labels applied to content</span></span>

<span data-ttu-id="2240c-142">Метки хранения используются для управления ликвидацией содержимого в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2240c-142">Retention labels are used to manage the disposition of content in your organization.</span></span> <span data-ttu-id="2240c-143">В случае применения их можно использовать для контроля следующего: время хранения документа до удаления, необходимость просмотра до удаления, завершение срока хранения и должен ли документ быть помечен в качестве записи, которую никогда нельзя удалять.</span><span class="sxs-lookup"><span data-stu-id="2240c-143">When applied, they can be used to control how long a document will be kept before deletion, whether it should be reviewed prior to deletion, when it's retention period expires, or whether it should be marked as a record which can never be deleted.</span></span> <span data-ttu-id="2240c-144">Дополнительную информацию см. в разделе [Обзор меток хранения](labels.md).</span><span class="sxs-lookup"><span data-stu-id="2240c-144">For more information see, [Overview of retention labels](labels.md).</span></span>

<span data-ttu-id="2240c-145">Карточка наиболее часто используемых меток хранения показывает количество элементов, которым была присвоена метка хранения.</span><span class="sxs-lookup"><span data-stu-id="2240c-145">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![снимок экрана замещающего текста наиболее часто используемых меток хранения](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="2240c-147">Если в этой карточке отображается сообщение: «Метки хранения не обнаружены», то это обозначает, что вы не создали или не опубликовали какие-либо метки хранения или к содержимому не была применена метка хранения.</span><span class="sxs-lookup"><span data-stu-id="2240c-147">If this card displays the message, "No retention labels detected, it means you haven't created or published any retention  labels or no content has had a retention label applied.</span></span> <span data-ttu-id="2240c-148">Чтобы приступить к работе с метками хранения, см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="2240c-148">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="2240c-149">Обзор меток хранения</span><span class="sxs-lookup"><span data-stu-id="2240c-149">Overview of retention labels</span></span>](labels.md)

## <a name="top-activities-detected"></a><span data-ttu-id="2240c-150">Основные обнаруженные действия</span><span class="sxs-lookup"><span data-stu-id="2240c-150">Top activities detected</span></span>

<span data-ttu-id="2240c-151">В этой карточке представлен краткий обзор основных действий, которые пользователи выполняют с элементами, отмеченными в качестве конфиденциальных.</span><span class="sxs-lookup"><span data-stu-id="2240c-151">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="2240c-152">Используйте [Обозреватель действий](data-classification-activity-explorer.md), чтобы углубленно изучить восемь различных действий, которые Microsoft 365 отслеживает по отмеченному содержимому и содержимому, размещенному в конечных точках Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2240c-152">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="2240c-153">Если в этой карточке отображается сообщение «Действие не обнаружено», то это означает отсутствие действий с файлом или то, что аудит пользователя и администратора не включен.</span><span class="sxs-lookup"><span data-stu-id="2240c-153">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="2240c-154">Для включения журналов аудита см. сведения в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="2240c-154">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="2240c-155">Поиск журнала аудита в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="2240c-155">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="2240c-156">Данные с метками конфиденциальности и хранения по расположению</span><span class="sxs-lookup"><span data-stu-id="2240c-156">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="2240c-157">Суть отчетов о классификации данных заключается в обеспечении наглядного представления о количестве элементов с меткой, а также об их расположении.</span><span class="sxs-lookup"><span data-stu-id="2240c-157">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="2240c-158">Эти карточки дадут вам представление о количестве отмеченных элементов в Exchange, SharePoint, OneDrive и т. д.</span><span class="sxs-lookup"><span data-stu-id="2240c-158">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="2240c-159">Если в этой карточке отображается сообщение: «Расположения не обнаружены», то это обозначает, что вы не создали или не опубликовали какие-либо метки конфиденциальности или к содержимому не была применена метка хранения.</span><span class="sxs-lookup"><span data-stu-id="2240c-159">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="2240c-160">Чтобы приступить к работе с метками конфиденциальности, см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="2240c-160">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="2240c-161">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="2240c-161">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="2240c-162">См. также</span><span class="sxs-lookup"><span data-stu-id="2240c-162">See also</span></span>

- [<span data-ttu-id="2240c-163">Просмотр действий с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="2240c-163">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="2240c-164">Просмотр содержимого с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="2240c-164">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="2240c-165">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="2240c-165">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="2240c-166">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="2240c-166">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="2240c-167">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="2240c-167">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="2240c-168">Обзор политик хранения</span><span class="sxs-lookup"><span data-stu-id="2240c-168">Overview of retention policies</span></span>](retention-policies.md)
