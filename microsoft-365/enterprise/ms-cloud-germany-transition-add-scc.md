---
title: Сведения об опыте работы с электронными данными во время миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Сводка. Этапы миграции электронных данных для миграции из Microsoft Cloud Deutschland.
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844254"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="3200c-103">Сведения о том, как получить сведения об обнаружении электронных данных во время миграции из Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="3200c-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="3200c-104">В следующих разделах приводится дополнительная информация о том, как получить сведения об обнаружении электронных данных при переходе из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в Office 365 службы в новом немецком регионе центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="3200c-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="3200c-105">администрирование электронных открытий до 4-го этапа</span><span class="sxs-lookup"><span data-stu-id="3200c-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="3200c-106">До 4-го этапа Центр безопасности и соответствия требованиям будет полностью доступен.</span><span class="sxs-lookup"><span data-stu-id="3200c-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="3200c-107">Все содержимое по-прежнему остается в Microsoft Cloud Germany и управляется Центром безопасности и соответствия требованиям Microsoft Cloud Germany https://protection.office.de/) (.</span><span class="sxs-lookup"><span data-stu-id="3200c-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="3200c-108">опыт по обнаружению электронных обнаружений между этапом 4 и до конца 9-й фазы</span><span class="sxs-lookup"><span data-stu-id="3200c-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="3200c-109">С начала 4-го этапа и до завершения 9-го этапа поиски электронных обнаружений не будут завершены или будут возвращены 0 результатов для SharePoint Online, OneDrive для бизнеса и Exchange Online, которые были перенесены.</span><span class="sxs-lookup"><span data-stu-id="3200c-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="3200c-110">Во время миграции клиенты могут продолжать создавать случаи, удерживания, поиски и экспорты в Центре & [безопасности,](/microsoft-365/compliance/manage-legal-investigations)включая [поиск контента.](/microsoft-365/compliance/search-for-content)</span><span class="sxs-lookup"><span data-stu-id="3200c-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations), including [Content Search](/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="3200c-111">Однако поиск в SharePoint, OneDrive для бизнеса и Exchange Online, которые были перенесены, возвращает 0 результатов или создает ошибку.</span><span class="sxs-lookup"><span data-stu-id="3200c-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="3200c-112">В случае, если поиск возвращает нулевые результаты или ошибку во время миграции, примите следующие действия для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="3200c-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span>

- <span data-ttu-id="3200c-113">Скачайте сайты непосредственно с сайта SharePoint Online или OneDrive для бизнеса, следуя инструкциям по загрузке файлов и папок из OneDrive [или SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span><span class="sxs-lookup"><span data-stu-id="3200c-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="3200c-114">Этот метод потребует SharePoint разрешений администратора Online или разрешений только для чтения на сайте.</span><span class="sxs-lookup"><span data-stu-id="3200c-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="3200c-115">Если ограничения превышены, как поясняется в файле загрузки и папках из OneDrive или [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)клиенты могут использовать клиент синхронизации OneDrive для бизнеса, следуя указаниям в sync [SharePoint и Teams](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)файлах с компьютером .</span><span class="sxs-lookup"><span data-stu-id="3200c-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="3200c-116">Дополнительные сведения см. [в обнаружение электронных данных на месте в Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span><span class="sxs-lookup"><span data-stu-id="3200c-116">For more information, see  [In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="3200c-117">администрирование электронных разыскных открытий после 9-го этапа</span><span class="sxs-lookup"><span data-stu-id="3200c-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="3200c-118">**Применяется к:** Все клиенты, использующие eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3200c-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="3200c-119">На 9-м этапе будут завершены заключительные шаги по переходу в новый немецкий центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="3200c-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="3200c-120">На этом этапе все оставшиеся компоненты службы будут перенесены.</span><span class="sxs-lookup"><span data-stu-id="3200c-120">In this phase, all remaining service components will be migrated.</span></span>
<span data-ttu-id="3200c-121">После 9-го этапа использование Центра безопасности и соответствия требованиям в Microsoft Cloud Germany (protection.office.de) больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3200c-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="3200c-122">Вместо этого используйте новый [Центр безопасности](https://security.microsoft.com/) или [Центр соответствия](https://compliance.microsoft.com/) требованиям.</span><span class="sxs-lookup"><span data-stu-id="3200c-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="3200c-123">Все данные были перенесены на новые порталы администрирования.</span><span class="sxs-lookup"><span data-stu-id="3200c-123">All data have been migrated to the new admin portals.</span></span>

| <span data-ttu-id="3200c-124">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3200c-124">Step(s)</span></span> | <span data-ttu-id="3200c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="3200c-125">Description</span></span> | <span data-ttu-id="3200c-126">Влияние</span><span class="sxs-lookup"><span data-stu-id="3200c-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="3200c-127">Все SharePoint, OneDrive для бизнеса и Exchange Online были перенесены вместе с Центром безопасности и соответствия требованиям (SCC).</span><span class="sxs-lookup"><span data-stu-id="3200c-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="3200c-128">Все действия по обнаружению электронных обнаружений должны запускаться от клиента по всему миру.</span><span class="sxs-lookup"><span data-stu-id="3200c-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="3200c-129">Поиск теперь будет на 100% успешным.</span><span class="sxs-lookup"><span data-stu-id="3200c-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="3200c-130">Любые сбои или ошибки должны следовать обычным каналам поддержки.</span><span class="sxs-lookup"><span data-stu-id="3200c-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="3200c-131">Нет</span><span class="sxs-lookup"><span data-stu-id="3200c-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="3200c-132">Политика хранения электронных данных</span><span class="sxs-lookup"><span data-stu-id="3200c-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="3200c-133">**Применяется к:**  Все клиенты, применявшие политику хранения в рамках этапов предварительной миграции</span><span class="sxs-lookup"><span data-stu-id="3200c-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="3200c-134">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3200c-134">Step(s)</span></span> | <span data-ttu-id="3200c-135">Описание</span><span class="sxs-lookup"><span data-stu-id="3200c-135">Description</span></span> | <span data-ttu-id="3200c-136">Влияние</span><span class="sxs-lookup"><span data-stu-id="3200c-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3200c-137">Удаление политик хранения по всей организации, созданных во время этапов предварительной миграции</span><span class="sxs-lookup"><span data-stu-id="3200c-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="3200c-138">Клиенты могут удалить политики хранения на всей организации, созданные во время работы перед миграцией клиентов.</span><span class="sxs-lookup"><span data-stu-id="3200c-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="3200c-139">Нет</span><span class="sxs-lookup"><span data-stu-id="3200c-139">None</span></span> |
||||
