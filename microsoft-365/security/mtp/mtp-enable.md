---
title: Включение Защиты от угроз (Майкрософт) в Центре безопасности Microsoft 365
description: Узнайте, как включить Защиту от угроз (Майкрософт) и начать интеграцию инцидентов безопасности и реагирования на них.
keywords: начало работы, MTP, Защита от угроз (Майкрософт), Microsoft 365, безопасность, расположение данных
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7790e079d4b39b5d41961a26bb17009adb1bec1d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808454"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="387cf-104">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="387cf-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="387cf-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="387cf-105">**Applies to:**</span></span>
- <span data-ttu-id="387cf-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="387cf-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="387cf-107">Защита от угроз (Майкрософт) объединяет процесс реагирования на инциденты, интегрируя основные возможности Advanced Threat Protection (ATP) в Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="387cf-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="387cf-108">В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="387cf-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-your-eligibility"></a><span data-ttu-id="387cf-109">Проверка правомочности</span><span class="sxs-lookup"><span data-stu-id="387cf-109">Check your eligibility</span></span>
<span data-ttu-id="387cf-110">Защиту от угроз (Майкрософт) могут использовать клиенты, у которых есть лицензия Microsoft 365 E5 или аналогичная лицензия. </span><span class="sxs-lookup"><span data-stu-id="387cf-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="387cf-111">Дополнительные сведения см. в статье [Требования к лицензированию](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="387cf-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="387cf-112">Начало работы со службой</span><span class="sxs-lookup"><span data-stu-id="387cf-112">Start using the service</span></span>
<span data-ttu-id="387cf-113">Включение службы Защиты от угроз (Майкрософт) объединяет данные из различных интегрированных служб.</span><span class="sxs-lookup"><span data-stu-id="387cf-113">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="387cf-114">Данные будут обрабатываться и храниться централизованно, чтобы предоставить новые рекомендации и сделать возможными централизованные рабочие процессы реагирования.</span><span class="sxs-lookup"><span data-stu-id="387cf-114">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="387cf-115">До включения службы параметры **Инциденты** и **Центр уведомлений** не отображаются в меню Центра безопасности Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="387cf-115">Before you turn the service on, Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="387cf-116">![Изображение меню Центра безопасности Microsoft 365 без функций Защиты от угроз (Майкрософт)](../images/mtp-off.png)
*Центр безопасности Microsoft 365 с отключенной службой Защиты от угроз (Майкрософт)*</span><span class="sxs-lookup"><span data-stu-id="387cf-116">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="387cf-117">Чтобы включить службу Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**.</span><span class="sxs-lookup"><span data-stu-id="387cf-117">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="387cf-118">Для выполнения этой задачи вам нужны права глобального администратора или администратора безопасности в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span><span class="sxs-lookup"><span data-stu-id="387cf-118">You will need to be a global administrator or a security administrator in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to perform this task.</span></span>

<span data-ttu-id="387cf-119">Если для вашей организации подготовлена служба ATP в Microsoft Defender, данные будут храниться и обрабатываться в том же расположении центра обработки данных, которое вы выбрали для [данных ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="387cf-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="387cf-120">В противном случае вам будет предложено выбрать новое расположение центра обработки данных для Защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="387cf-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="387cf-121">Согласие необходимо дать до предоставления службам общего доступа к данным и их агрегации.</span><span class="sxs-lookup"><span data-stu-id="387cf-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="387cf-122">Подтверждение включения службы</span><span class="sxs-lookup"><span data-stu-id="387cf-122">Confirm that the service is on</span></span>
<span data-ttu-id="387cf-123">После подготовки службы в нее добавляются:</span><span class="sxs-lookup"><span data-stu-id="387cf-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="387cf-124">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="387cf-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="387cf-125">Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="387cf-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="387cf-126">Возможности [расширенного поиска](advanced-hunting-overview.md) на существующей странице **Поиск**</span><span class="sxs-lookup"><span data-stu-id="387cf-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="387cf-127">![Изображение меню Центра безопасности Microsoft 365 с функциями Защиты от угроз (Майкрософт)](../images/mtp-on.png)
*Центр безопасности Microsoft 365 с возможностью управления инцидентами и другими функциями Защиты от угроз (Майкрософт)*</span><span class="sxs-lookup"><span data-stu-id="387cf-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="387cf-128">Получение данных Azure ATP</span><span class="sxs-lookup"><span data-stu-id="387cf-128">Getting Azure ATP data</span></span>
<span data-ttu-id="387cf-129">Чтобы предоставить доступ к данным Azure ATP службе Защиты от угроз (Майкрософт), убедитесь в том, что включена интеграция Microsoft Cloud App Security с Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="387cf-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="387cf-130">Подробнее об этой интеграции</span><span class="sxs-lookup"><span data-stu-id="387cf-130">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="387cf-131">Выключение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="387cf-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="387cf-132">Чтобы прекратить использование службы Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**.</span><span class="sxs-lookup"><span data-stu-id="387cf-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="387cf-133">Снимите флажок **Включение Защиты от угроз (Майкрософт)** и сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="387cf-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="387cf-134">Данные будут удалены без возможности восстановления, и соответствующие функции будут удалены из Центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="387cf-134">Data will be permanently deleted and corresponding features will be removed from Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="387cf-135">Получение помощи</span><span class="sxs-lookup"><span data-stu-id="387cf-135">Get assistance</span></span>

<span data-ttu-id="387cf-136">Сотрудники Майкрософт могут помочь в подготовке или отмене подготовки службы и связанных ресурсов в клиенте.</span><span class="sxs-lookup"><span data-stu-id="387cf-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="387cf-137">Чтобы получить помощь, [обратитесь в службу поддержки Premier](https://go.microsoft.com/fwlink/?LinkID=733758).</span><span class="sxs-lookup"><span data-stu-id="387cf-137">For assistance, [contact premier support](https://go.microsoft.com/fwlink/?LinkID=733758).</span></span>

## <a name="related-topics"></a><span data-ttu-id="387cf-138">См. также</span><span class="sxs-lookup"><span data-stu-id="387cf-138">Related topics</span></span>

- [<span data-ttu-id="387cf-139">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="387cf-139">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="387cf-140">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="387cf-140">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="387cf-141">Обзор ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="387cf-141">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="387cf-142">Обзор Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="387cf-142">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="387cf-143">Обзор Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="387cf-143">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="387cf-144">Обзор Azure ATP</span><span class="sxs-lookup"><span data-stu-id="387cf-144">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="387cf-145">Хранение данных в службе ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="387cf-145">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
