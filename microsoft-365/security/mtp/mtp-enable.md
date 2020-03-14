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
ms.openlocfilehash: fa970b28939ad43bf6a2717e603013277bc9130f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633907"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="5c793-104">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="5c793-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="5c793-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5c793-105">**Applies to:**</span></span>
- <span data-ttu-id="5c793-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="5c793-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5c793-107">Защита от угроз (Майкрософт) объединяет процесс реагирования на инциденты, интегрируя основные возможности Advanced Threat Protection (ATP) в Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="5c793-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="5c793-108">В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="5c793-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="5c793-109">Чтобы получить лучшую защиту и оптимизировать защиту от угроз Майкрософт, мы рекомендуем развернуть все поддерживаемые службы в сети.</span><span class="sxs-lookup"><span data-stu-id="5c793-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="5c793-110">Для получения дополнительных сведений [Ознакомьтесь с разворачиванием поддерживаемых служб](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="5c793-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="5c793-111">Проверка допустимости лицензий и необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="5c793-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="5c793-112">Лицензия Microsoft 365, в том действиях, в том, чтобы получить доступ к поддерживаемым службам, и предоставляет доступ к поддерживаемым службам и предоставляет Вам возможность использовать защиту от угроз Майкрософт в центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="5c793-112">A Microsoft 365 E5, E5 Security, or A5 license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="5c793-113">Для получения подробных сведений о лицензировании [Прочтите требования к лицензированию](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="5c793-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="5c793-114">Проверка роли</span><span class="sxs-lookup"><span data-stu-id="5c793-114">Check your role</span></span>
<span data-ttu-id="5c793-115">Чтобы включить защиту от угроз Майкрософт, необходимо быть **глобальным администратором** или **администратором безопасности** в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5c793-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="5c793-116">Просмотр ролей в Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c793-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="5c793-117">Начало работы со службой</span><span class="sxs-lookup"><span data-stu-id="5c793-117">Start using the service</span></span>
<span data-ttu-id="5c793-118">Защита от угроз Майкрософт собирает данные из различных интегрированных служб.</span><span class="sxs-lookup"><span data-stu-id="5c793-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="5c793-119">Он будет обрабатывать и хранить данные централизованно, чтобы определять новые аналитики и создавать централизованные рабочие процессы ответа.</span><span class="sxs-lookup"><span data-stu-id="5c793-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="5c793-120">Перед включением службы центр безопасности Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) отображает страницу приветствия Microsoft Threat Protection, когда вы выбираете **инциденты**, **Центр уведомлений** **или поиск** в области навигации.</span><span class="sxs-lookup"><span data-stu-id="5c793-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="5c793-121">Эти параметры навигации не отображаются, если вы не можете использовать защиту от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5c793-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="5c793-122">![Изображение страницы приветствия Microsoft Threat Protection, показанной в том случае, если защита от угроз](../../media/mtp-welcome.png)
Майкрософт не включена на*странице приветствия Microsoft Threat Protection в центре безопасности Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="5c793-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="5c793-123">Чтобы включить защиту от угроз Майкрософт, просто завершите процесс на странице приветствия.</span><span class="sxs-lookup"><span data-stu-id="5c793-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="5c793-124">Вы также можете включить защиту от угроз Майкрософт, закрыв **Параметры** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) в области навигации и выбрав **защиту от угроз Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="5c793-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="5c793-125">Если вы не видите **Параметры** в области навигации или не смогли получить доступ к странице, проверьте свои разрешения и лицензии.</span><span class="sxs-lookup"><span data-stu-id="5c793-125">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="5c793-126">Выбор расположения центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="5c793-126">Select data center location</span></span>
<span data-ttu-id="5c793-127">Если для вашей организации подготовлена служба ATP в Microsoft Defender, данные будут храниться и обрабатываться в том же расположении центра обработки данных, которое вы выбрали для [данных ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="5c793-127">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="5c793-128">В противном случае вам будет предложено выбрать новое расположение центра обработки данных для Защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="5c793-128">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="5c793-129">Необходимо предоставить согласие, прежде чем данные будут совместно использоваться службами и объединены.</span><span class="sxs-lookup"><span data-stu-id="5c793-129">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="5c793-130">Подтверждение включения службы</span><span class="sxs-lookup"><span data-stu-id="5c793-130">Confirm that the service is on</span></span>
<span data-ttu-id="5c793-131">После подготовки службы в нее добавляются:</span><span class="sxs-lookup"><span data-stu-id="5c793-131">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="5c793-132">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="5c793-132">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="5c793-133">Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="5c793-133">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="5c793-134">[Расширенные](advanced-hunting-overview.md) возможности поисковых</span><span class="sxs-lookup"><span data-stu-id="5c793-134">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="5c793-135">![Изображение области навигации центра безопасности Microsoft 365 с помощью функций](../../media/mtp-on.png)
защиты от угроз Майкрософт*Центр безопасности Microsoft 365 с возможностью управления происшествиями и другими возможностями защиты от угроз Майкрософт*</span><span class="sxs-lookup"><span data-stu-id="5c793-135">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="5c793-136">Получение данных Azure ATP</span><span class="sxs-lookup"><span data-stu-id="5c793-136">Getting Azure ATP data</span></span>
<span data-ttu-id="5c793-137">Чтобы предоставить доступ к данным Azure ATP службе Защиты от угроз (Майкрософт), убедитесь в том, что включена интеграция Microsoft Cloud App Security с Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="5c793-137">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="5c793-138">Подробнее об этой интеграции</span><span class="sxs-lookup"><span data-stu-id="5c793-138">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="5c793-139">Выключение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="5c793-139">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="5c793-140">Чтобы прекратить использование службы Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**.</span><span class="sxs-lookup"><span data-stu-id="5c793-140">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="5c793-141">Снимите флажок **Включение Защиты от угроз (Майкрософт)** и сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="5c793-141">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="5c793-142">Соответствующие функции будут удалены из центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c793-142">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="5c793-143">Получение помощи</span><span class="sxs-lookup"><span data-stu-id="5c793-143">Get assistance</span></span>

<span data-ttu-id="5c793-144">Сотрудники службы поддержки Майкрософт могут помочь подготовить или отменить подготовку службы и связанных ресурсов в клиенте.</span><span class="sxs-lookup"><span data-stu-id="5c793-144">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="5c793-145">Для получения помощи выберите **нужна помощь?** в центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="5c793-145">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="5c793-146">При обращении в службу поддержки следует упомянуть о защите от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5c793-146">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c793-147">См. также</span><span class="sxs-lookup"><span data-stu-id="5c793-147">Related topics</span></span>

- [<span data-ttu-id="5c793-148">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="5c793-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="5c793-149">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5c793-149">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="5c793-150">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="5c793-150">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="5c793-151">Обзор ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5c793-151">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="5c793-152">Обзор Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="5c793-152">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="5c793-153">Обзор Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5c793-153">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="5c793-154">Обзор Azure ATP</span><span class="sxs-lookup"><span data-stu-id="5c793-154">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="5c793-155">Хранение данных в службе ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5c793-155">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
