---
title: Включить Защитник Microsoft 365 в Центре безопасности Microsoft 365
description: Узнайте, как включить Microsoft 365 Defender и начать интеграцию инцидентов безопасности и реагирования на них.
keywords: начало работы, включить MTP, Защиту от угроз (Майкрософт), M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страница параметров
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
ms.openlocfilehash: b052f70c1b618adef12c4f70c2b3fe55741697d5
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760510"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="1a7d9-104">Включить Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a7d9-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1a7d9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1a7d9-105">**Applies to:**</span></span>
- <span data-ttu-id="1a7d9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a7d9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1a7d9-107">[Microsoft 365 Defender](microsoft-threat-protection.md) объединяет процесс реагирования на инциденты, интегрируя ключевые возможности в Microsoft Defender для endpoint, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="1a7d9-108">В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="1a7d9-109">Защитник Microsoft 365 автоматически включается, когда подходящие клиенты с требуемой разрешением могут посетить Центр безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="1a7d9-110">Ознакомьтесь с этой статьей, чтобы ознакомиться с различными предварительными условиями и тем, как работает Защитник Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="1a7d9-111">Проверка прав на получение лицензии и необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="1a7d9-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="1a7d9-112">Лицензия на продукт безопасности Microsoft 365 обычно дает вам право использовать Microsoft 365 Defender в Центре безопасности Microsoft 365 без дополнительных затрат на лицензирование.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="1a7d9-113">Рекомендуем получить лицензию на Microsoft 365 E5, E5 Security, A5 или A5 Security или допустимое сочетание лицензий, которое предоставляет доступ ко всем поддерживаемым службам.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="1a7d9-114">Подробные сведения о лицензировании можно узнать [в требованиях к лицензированию.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="1a7d9-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="1a7d9-115">Проверка роли</span><span class="sxs-lookup"><span data-stu-id="1a7d9-115">Check your role</span></span>

<span data-ttu-id="1a7d9-116">Чтобы включить Microsoft 365 **Defender,** необходимо быть глобальным администратором или администратором безопасности в Azure Active Directory. </span><span class="sxs-lookup"><span data-stu-id="1a7d9-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="1a7d9-117">Просмотр ролей в Azure AD</span><span class="sxs-lookup"><span data-stu-id="1a7d9-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="1a7d9-118">Поддерживаемые службы</span><span class="sxs-lookup"><span data-stu-id="1a7d9-118">Supported services</span></span>

<span data-ttu-id="1a7d9-119">Microsoft 365 Defender собирает данные из различных поддерживаемых служб, которые вы уже развернули.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="1a7d9-120">Централизованная обработка и хранение данных будут определять новые сведения и делать возможными централизованные процессы ответа.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="1a7d9-121">Это делается без влияния на существующие развертывания, параметры или данные, связанные с интегрированными службами.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="1a7d9-122">Чтобы получить лучшую защиту и оптимизировать Microsoft 365 Defender, рекомендуем развернуть в вашей сети все поддерживаемые службы.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="1a7d9-123">Дополнительные сведения о [развертывании поддерживаемых служб.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="1a7d9-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="1a7d9-124">Перед запуском службы</span><span class="sxs-lookup"><span data-stu-id="1a7d9-124">Before starting the service</span></span>

<span data-ttu-id="1a7d9-125">Перед тем как включить службу, Центр безопасности Microsoft 365[(security.microsoft.com)](https://security.microsoft.com)отображает страницу параметров Защитника Microsoft 365, когда вы выбираете "Инциденты", "Центр действий" или "Охота" в области навигации. </span><span class="sxs-lookup"><span data-stu-id="1a7d9-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="1a7d9-126">Эти элементы навигации не показываются, если вы не можете использовать Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="1a7d9-127">![Изображение страницы параметров Защитника Microsoft 365, если Защитник Microsoft 365 не включен в параметрах Защитника Microsoft 365 в Центре безопасности ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="1a7d9-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="1a7d9-128">Запуск службы</span><span class="sxs-lookup"><span data-stu-id="1a7d9-128">Starting the service</span></span>

<span data-ttu-id="1a7d9-129">Чтобы включить Microsoft 365 Defender, просто выберите "Включить **Защитник Microsoft 365"** и применить изменение.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="1a7d9-130">Вы также можете получить доступ  к этому параметру, выбрав параметры [(security.microsoft.com/settings)](https://security.microsoft.com/settings)в области навигации, а затем выбрав **Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="1a7d9-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="1a7d9-131">Если вы не видите **параметры** в области навигации или не можете получить доступ к странице, проверьте свои разрешения и лицензии.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="1a7d9-132">Расположение центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="1a7d9-132">Data center location</span></span>

<span data-ttu-id="1a7d9-133">Защитник Microsoft 365 будет хранить и обрабатывать данные в том же расположении, что и [Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="1a7d9-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="1a7d9-134">Если у вас нет Microsoft Defender для конечной точки, новое расположение центра обработки данных автоматически выбирается в зависимости от расположения активных служб безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="1a7d9-135">Выбранное расположение центра обработки данных отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="1a7d9-136">Выберите **"Нужна помощь"?** В Центре безопасности Microsoft 365 обратитесь в службу поддержки Майкрософт по поводу предоставления Microsoft 365 Defender в другом расположении центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="1a7d9-137">Microsoft Defender для конечной точки автоматически подготовка в центрах обработки данных Европейского Союза (ЕС) при включаемом в Защитнике Azure.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="1a7d9-138">Защитник Microsoft 365 автоматически будет в том же центре обработки данных ЕС работать с клиентами, которые таким образом назначили Защитник для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="1a7d9-139">Подтверждение включения службы</span><span class="sxs-lookup"><span data-stu-id="1a7d9-139">Confirm that the service is on</span></span>

<span data-ttu-id="1a7d9-140">После подготовки службы в нее добавляются:</span><span class="sxs-lookup"><span data-stu-id="1a7d9-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="1a7d9-141">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="1a7d9-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="1a7d9-142">Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="1a7d9-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="1a7d9-143">[Расширенные возможности охоты](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1a7d9-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="1a7d9-144">![Изображение области навигации Центра безопасности Microsoft 365 с функциями Центра безопасности Microsoft 365 с управлением инцидентами и другими возможностями ](../../media/mtp-enable/mtp-on.png)
 *Защитника Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="1a7d9-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="1a7d9-145">Получение данных удостоверений в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1a7d9-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="1a7d9-146">Чтобы поделиться данными Microsoft Defender для удостоверений с Microsoft 365 Defender, убедитесь, что интеграция Microsoft Cloud App Security и Microsoft Defender для удостоверений включена.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="1a7d9-147">[Узнайте больше об этой интеграции.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="1a7d9-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="1a7d9-148">Получение помощи</span><span class="sxs-lookup"><span data-stu-id="1a7d9-148">Get assistance</span></span>

<span data-ttu-id="1a7d9-149">Чтобы получить ответы на наиболее часто задаваемые вопросы о включаемом Защитнике Microsoft 365, ознакомьтесь [с часто задаваемой проблемой.](mtp-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="1a7d9-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="1a7d9-150">Сотрудники службы поддержки Майкрософт могут помочь в предоставлении или отофровке службы и связанных ресурсов в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="1a7d9-151">Для помощи выберите **"Нужна помощь"** в Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="1a7d9-152">Обратитесь в службу поддержки и обратитесь в Службу поддержки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a7d9-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1a7d9-153">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1a7d9-153">Related topics</span></span>

- [<span data-ttu-id="1a7d9-154">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="1a7d9-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="1a7d9-155">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1a7d9-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="1a7d9-156">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="1a7d9-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="1a7d9-157">Обзор Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a7d9-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1a7d9-158">Обзор Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1a7d9-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="1a7d9-159">Обзор Защитника для Office 365</span><span class="sxs-lookup"><span data-stu-id="1a7d9-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="1a7d9-160">Обзор Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1a7d9-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="1a7d9-161">Обзор Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="1a7d9-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="1a7d9-162">Microsoft Defender для хранения данных конечной точки</span><span class="sxs-lookup"><span data-stu-id="1a7d9-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
