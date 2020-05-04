---
title: Включение Защиты от угроз (Майкрософт) в Центре безопасности Microsoft 365
description: Узнайте, как включить Защиту от угроз (Майкрософт) и начать интеграцию инцидентов безопасности и реагирования на них.
keywords: Начало работы, включение MTP, защита от угроз Майкрософт, M365, безопасность, расположение данных, необходимые разрешения, права на лицензирование, страница параметров
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 0bb91f226a29fe6b175cf1ca4866316d1457291e
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011867"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="4ec3e-104">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="4ec3e-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="4ec3e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4ec3e-105">**Applies to:**</span></span>
- <span data-ttu-id="4ec3e-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="4ec3e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4ec3e-107">Защита от угроз (Майкрософт) объединяет процесс реагирования на инциденты, интегрируя основные возможности Advanced Threat Protection (ATP) в Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="4ec3e-108">В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="4ec3e-109">Чтобы получить лучшую защиту и оптимизировать защиту от угроз Майкрософт, мы рекомендуем развернуть все поддерживаемые службы в сети.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="4ec3e-110">Для получения дополнительных сведений [Ознакомьтесь с разворачиванием поддерживаемых служб](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="4ec3e-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="4ec3e-111">Проверка допустимости лицензий и необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="4ec3e-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="4ec3e-112">Лицензия Microsoft 365, в том действиях безопасности, A5 или A5, а также действующая комбинация лицензий предоставляет доступ к поддерживаемым службам и предоставляет Вам возможность использовать защиту от угроз Майкрософт в центре безопасности Майкрософт 365 без дополнительной стоимости лицензирования.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span>

<span data-ttu-id="4ec3e-113">Для получения подробных сведений о лицензировании [Прочтите требования к лицензированию](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="4ec3e-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="4ec3e-114">Проверка роли</span><span class="sxs-lookup"><span data-stu-id="4ec3e-114">Check your role</span></span>
<span data-ttu-id="4ec3e-115">Чтобы включить защиту от угроз Майкрософт, необходимо быть **глобальным администратором** или **администратором безопасности** в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="4ec3e-116">Просмотр ролей в Azure AD</span><span class="sxs-lookup"><span data-stu-id="4ec3e-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="4ec3e-117">Начало работы со службой</span><span class="sxs-lookup"><span data-stu-id="4ec3e-117">Start using the service</span></span>

>[!IMPORTANT]
><span data-ttu-id="4ec3e-118">Начиная с 3 мая 2020 г. Корпорация Майкрософт постепенно выполнит развертывание новых, оптимизированных возможностей [лицензирования](prerequisites.md#licensing-requirements) и включения защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-118">Starting May 3, 2020, Microsoft will gradually roll out new, optimized experiences around [licensing requirements](prerequisites.md#licensing-requirements) and turning on Microsoft Threat Protection.</span></span> <span data-ttu-id="4ec3e-119">В течение нескольких недель в течение этого периода некоторые клиенты начнут видеть изменения в интерфейсах портала.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-119">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="4ec3e-120">Сведения о новых возможностях помечаются **новым интерфейсом** в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-120">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="4ec3e-121">Защита от угроз Майкрософт собирает данные из различных интегрированных служб.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-121">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="4ec3e-122">Он будет обрабатывать и хранить данные централизованно, чтобы определять новые аналитики и создавать централизованные рабочие процессы ответа.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-122">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="4ec3e-123">Это происходит, не затрагивая существующие развертывания, параметры или данные, связанные со встроенными службами.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-123">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="4ec3e-124">Перед включением службы центр безопасности Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) отображает страницу приветствия Microsoft Threat Protection, когда вы выбираете **инциденты**, **Центр уведомлений** **или поиск** в области навигации.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-124">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="4ec3e-125">Эти параметры навигации не отображаются, если вы не можете использовать защиту от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-125">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="4ec3e-126">![Изображение страницы приветствия Microsoft Threat Protection, показанной в том случае, если защита от угроз](../../media/mtp-welcome.png)
Майкрософт не включена на*странице приветствия Microsoft Threat Protection в центре безопасности Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="4ec3e-126">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="4ec3e-127">Чтобы включить защиту от угроз Майкрософт, просто завершите процесс на странице приветствия.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-127">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="4ec3e-128">Вы также можете включить защиту от угроз Майкрософт, закрыв **Параметры** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) в области навигации и выбрав **защиту от угроз Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-128">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="4ec3e-129">Если вы не видите **Параметры** в области навигации или не смогли получить доступ к странице, проверьте свои разрешения и лицензии.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-129">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>       

### <a name="select-data-center-location"></a><span data-ttu-id="4ec3e-130">Выбор расположения центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="4ec3e-130">Select data center location</span></span>
<span data-ttu-id="4ec3e-131">Если для вашей организации подготовлена служба ATP в Microsoft Defender, данные будут храниться и обрабатываться в том же расположении центра обработки данных, которое вы выбрали для [данных ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="4ec3e-131">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="4ec3e-132">В противном случае вам будет предложено выбрать новое расположение центра обработки данных для Защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="4ec3e-132">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 
 
<span data-ttu-id="4ec3e-133">Необходимо предоставить согласие, прежде чем данные будут совместно использоваться службами и объединены.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-133">You need to provide consent before data is shared between services and aggregated.</span></span>

<span data-ttu-id="4ec3e-134">**Новые возможности:** Начиная с 3 мая 2020 клиенты постепенно перестанут получать изменения этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-134">**New experience:** Starting May 3, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="4ec3e-135">При новом интерфейсе служба автоматически выбирает оптимальное расположение центра обработки данных для собранных данных на основе существующих служб безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-135">For those with the new experience, the service automatically selects the optimal data center location for your aggregated data based on your existing Microsoft 365 security services.</span></span> <span data-ttu-id="4ec3e-136">Выбранное расположение центра обработки данных отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-136">The selected data center location is shown in the screen.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="4ec3e-137">Подтверждение включения службы</span><span class="sxs-lookup"><span data-stu-id="4ec3e-137">Confirm that the service is on</span></span>
<span data-ttu-id="4ec3e-138">После подготовки службы в нее добавляются:</span><span class="sxs-lookup"><span data-stu-id="4ec3e-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="4ec3e-139">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="4ec3e-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="4ec3e-140">Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="4ec3e-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="4ec3e-141">[Расширенные](advanced-hunting-overview.md) возможности поисковых</span><span class="sxs-lookup"><span data-stu-id="4ec3e-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="4ec3e-142">![Изображение области навигации центра безопасности Microsoft 365 с помощью функций](../../media/mtp-on.png)
защиты от угроз Майкрософт*Центр безопасности Microsoft 365 с возможностью управления происшествиями и другими возможностями защиты от угроз Майкрософт*</span><span class="sxs-lookup"><span data-stu-id="4ec3e-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="4ec3e-143">Получение данных Azure ATP</span><span class="sxs-lookup"><span data-stu-id="4ec3e-143">Getting Azure ATP data</span></span>
<span data-ttu-id="4ec3e-144">Чтобы предоставить доступ к данным Azure ATP службе Защиты от угроз (Майкрософт), убедитесь в том, что включена интеграция Microsoft Cloud App Security с Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="4ec3e-145">Подробнее об этой интеграции</span><span class="sxs-lookup"><span data-stu-id="4ec3e-145">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="4ec3e-146">Выключение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="4ec3e-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="4ec3e-147">Чтобы прекратить использование службы Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="4ec3e-148">Снимите флажок **Включение Защиты от угроз (Майкрософт)** и сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-148">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="4ec3e-149">Соответствующие функции будут удалены из центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="4ec3e-150">Получение помощи</span><span class="sxs-lookup"><span data-stu-id="4ec3e-150">Get assistance</span></span>

<span data-ttu-id="4ec3e-151">Сотрудники службы поддержки Майкрософт могут помочь подготовить или отменить подготовку службы и связанных ресурсов в клиенте.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-151">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="4ec3e-152">Для получения помощи выберите **нужна помощь?** в центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-152">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="4ec3e-153">При обращении в службу поддержки следует упомянуть о защите от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4ec3e-153">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4ec3e-154">См. также</span><span class="sxs-lookup"><span data-stu-id="4ec3e-154">Related topics</span></span>

- [<span data-ttu-id="4ec3e-155">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="4ec3e-155">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="4ec3e-156">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4ec3e-156">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="4ec3e-157">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="4ec3e-157">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="4ec3e-158">Обзор ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4ec3e-158">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="4ec3e-159">Обзор Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="4ec3e-159">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="4ec3e-160">Обзор Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4ec3e-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="4ec3e-161">Обзор Azure ATP</span><span class="sxs-lookup"><span data-stu-id="4ec3e-161">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="4ec3e-162">Хранение данных в службе ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4ec3e-162">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
