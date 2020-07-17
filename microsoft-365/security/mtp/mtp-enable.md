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
ms.openlocfilehash: b6ac30f7e32bbec80952ad4f2104032886b11503
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016347"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="821a1-104">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="821a1-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="821a1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="821a1-105">**Applies to:**</span></span>
- <span data-ttu-id="821a1-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="821a1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="821a1-107">[Защита от угроз Майкрософт](microsoft-threat-protection.md) объединяет ваш процесс реагирования на инциденты за счет интеграции основных возможностей в Advanced Threat protection (ATP), Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="821a1-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="821a1-108">В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="821a1-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="821a1-109">Защита от угроз Майкрософт автоматически включается, когда пользователи с необходимыми разрешениями могут посетить центр безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="821a1-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="821a1-110">В этой статье приводятся сведения о различных предварительных требованиях и способах подготовки системы защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="821a1-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="821a1-111">Проверка допустимости лицензий и необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="821a1-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="821a1-112">Лицензия на продукт Microsoft 365 Security обычно дает вам возможность использовать защиту от угроз Майкрософт в центре безопасности Майкрософт 365 без дополнительной стоимости лицензирования.</span><span class="sxs-lookup"><span data-stu-id="821a1-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="821a1-113">Мы рекомендуем получить лицензию безопасности Microsoft 365, а также лицензию, A5 или A5 или действительную комбинацию лицензий, предоставляющую доступ ко всем поддерживаемым службам.</span><span class="sxs-lookup"><span data-stu-id="821a1-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="821a1-114">Для получения подробных сведений о лицензировании [Прочтите требования к лицензированию](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="821a1-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="821a1-115">Проверка роли</span><span class="sxs-lookup"><span data-stu-id="821a1-115">Check your role</span></span>
<span data-ttu-id="821a1-116">Чтобы включить защиту от угроз Майкрософт, необходимо быть **глобальным администратором** или **администратором безопасности** в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="821a1-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="821a1-117">Просмотр ролей в Azure AD</span><span class="sxs-lookup"><span data-stu-id="821a1-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="821a1-118">Поддерживаемые службы</span><span class="sxs-lookup"><span data-stu-id="821a1-118">Supported services</span></span>
<span data-ttu-id="821a1-119">Защита от угроз Майкрософт собирает данные из различных поддерживаемых служб, которые вы уже развернули.</span><span class="sxs-lookup"><span data-stu-id="821a1-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="821a1-120">Он будет обрабатывать и хранить данные централизованно, чтобы определять новые аналитики и создавать централизованные рабочие процессы ответа.</span><span class="sxs-lookup"><span data-stu-id="821a1-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="821a1-121">Это происходит, не затрагивая существующие развертывания, параметры или данные, связанные со встроенными службами.</span><span class="sxs-lookup"><span data-stu-id="821a1-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="821a1-122">Чтобы получить лучшую защиту и оптимизировать защиту от угроз Майкрософт, мы рекомендуем развернуть все поддерживаемые службы в сети.</span><span class="sxs-lookup"><span data-stu-id="821a1-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="821a1-123">Для получения дополнительных сведений [Ознакомьтесь с разворачиванием поддерживаемых служб](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="821a1-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="821a1-124">Перед запуском службы</span><span class="sxs-lookup"><span data-stu-id="821a1-124">Before starting the service</span></span>
<span data-ttu-id="821a1-125">Перед включением службы центр безопасности Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) отображает страницу параметров защиты от угроз Майкрософт при выборе **инцидентов**, **центра уведомлений** **или поиска** в области навигации.</span><span class="sxs-lookup"><span data-stu-id="821a1-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="821a1-126">Эти элементы навигации не отображаются, если вы не можете использовать защиту от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="821a1-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="821a1-127">![Изображение страницы параметров защиты от Майкрософт, отображаемой, если защита от угроз Майкрософт не включена ](../../media/mtp-enable/mtp-settings.png)
 *в центре безопасности Microsoft 365* .</span><span class="sxs-lookup"><span data-stu-id="821a1-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="821a1-128">Запуск службы</span><span class="sxs-lookup"><span data-stu-id="821a1-128">Starting the service</span></span>
<span data-ttu-id="821a1-129">Чтобы включить защиту от угроз Майкрософт, просто выберите **включить защиту от угроз Майкрософт** и примените изменение.</span><span class="sxs-lookup"><span data-stu-id="821a1-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="821a1-130">Вы также можете получить доступ к этому параметру, выбрав **Параметры** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) в области навигации, а затем выбрав **защиту от угроз Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="821a1-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="821a1-131">Если вы не видите **Параметры** в области навигации или не смогли получить доступ к странице, проверьте свои разрешения и лицензии.</span><span class="sxs-lookup"><span data-stu-id="821a1-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="821a1-132">Расположение центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="821a1-132">Data center location</span></span>
<span data-ttu-id="821a1-133">Защита от угроз Майкрософт будет хранить и обрабатывать данные в том [же расположении, что и пакет ATP для защитника Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="821a1-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="821a1-134">Если у вас нет пакета ATP для защитника Майкрософт, автоматически выбирается новое расположение центра обработки данных на основе расположения активных служб безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="821a1-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="821a1-135">Выбранное расположение центра обработки данных отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="821a1-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="821a1-136">Выберите пункт **нужна помощь?** в центре безопасности Майкрософт 365, чтобы обратиться в службу поддержки Майкрософт о подготовке защиты от угроз Майкрософт в другое расположение центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="821a1-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft Threat Protection in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="821a1-137">Защитник Майкрософт автоматически подготавливается к центрам обработки данных Европейского союза (ЕС) при включении в центре безопасности Azure.</span><span class="sxs-lookup"><span data-stu-id="821a1-137">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="821a1-138">Защита от угроз Майкрософт автоматически подготавливается к работе с одним и тем же центром обработки данных ЕС для клиентов, у которых такой способ настроен с помощью пакета ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="821a1-138">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="821a1-139">Подтверждение включения службы</span><span class="sxs-lookup"><span data-stu-id="821a1-139">Confirm that the service is on</span></span>
<span data-ttu-id="821a1-140">После подготовки службы в нее добавляются:</span><span class="sxs-lookup"><span data-stu-id="821a1-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="821a1-141">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="821a1-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="821a1-142">Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="821a1-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="821a1-143">[Расширенные](advanced-hunting-overview.md) возможности поисковых</span><span class="sxs-lookup"><span data-stu-id="821a1-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="821a1-144">![Изображение области навигации центра безопасности Microsoft 365 с помощью функций защиты от угроз Майкрософт ](../../media/mtp-enable/mtp-on.png)
 *Центр безопасности Microsoft 365 с возможностью управления происшествиями и другими возможностями защиты от угроз Майкрософт*</span><span class="sxs-lookup"><span data-stu-id="821a1-144">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="821a1-145">Получение данных Azure ATP</span><span class="sxs-lookup"><span data-stu-id="821a1-145">Getting Azure ATP data</span></span>
<span data-ttu-id="821a1-146">Чтобы предоставить доступ к данным Azure ATP службе Защиты от угроз (Майкрософт), убедитесь в том, что включена интеграция Microsoft Cloud App Security с Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="821a1-146">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="821a1-147">Подробнее об этой интеграции</span><span class="sxs-lookup"><span data-stu-id="821a1-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="821a1-148">Выключение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="821a1-148">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="821a1-149">Чтобы прекратить использование службы Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**.</span><span class="sxs-lookup"><span data-stu-id="821a1-149">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="821a1-150">Снимите флажок **включить защиту от угроз Майкрософт** и примените изменения.</span><span class="sxs-lookup"><span data-stu-id="821a1-150">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="821a1-151">Соответствующие функции будут удалены из центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="821a1-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="821a1-152">Получение помощи</span><span class="sxs-lookup"><span data-stu-id="821a1-152">Get assistance</span></span>

<span data-ttu-id="821a1-153">Чтобы получить ответы на часто задаваемые вопросы о включении защиты от угроз Майкрософт, [прочитайте вопросы и ответы](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="821a1-153">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="821a1-154">Сотрудники службы поддержки Майкрософт могут помочь подготовить или отменить подготовку службы и связанных ресурсов в клиенте.</span><span class="sxs-lookup"><span data-stu-id="821a1-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="821a1-155">Для получения помощи выберите **нужна помощь?** в центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="821a1-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="821a1-156">При обращении в службу поддержки следует упомянуть о защите от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="821a1-156">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="821a1-157">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="821a1-157">Related topics</span></span>

- [<span data-ttu-id="821a1-158">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="821a1-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="821a1-159">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="821a1-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="821a1-160">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="821a1-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="821a1-161">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="821a1-161">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="821a1-162">Обзор ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="821a1-162">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="821a1-163">Обзор Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="821a1-163">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="821a1-164">Обзор Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="821a1-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="821a1-165">Обзор Azure ATP</span><span class="sxs-lookup"><span data-stu-id="821a1-165">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="821a1-166">Хранение данных в службе ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="821a1-166">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)