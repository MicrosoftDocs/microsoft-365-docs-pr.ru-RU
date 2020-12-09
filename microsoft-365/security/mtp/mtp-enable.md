---
title: Включение защитника Microsoft 365 в центре безопасности Майкрософт 365
description: Сведения о том, как включить защитник Microsoft 365 и приступить к интеграции инцидента безопасности и ответа.
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
ms.openlocfilehash: fbe98b814b253551432ea35102f2bd6eeba921f8
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602095"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="92b95-104">Включение защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="92b95-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="92b95-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="92b95-105">**Applies to:**</span></span>
- <span data-ttu-id="92b95-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92b95-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="92b95-107">[Защитник microsoft 365](microsoft-threat-protection.md) объединяет в себе процесс реагирования на инциденты, интегрируя основные возможности в защитнике Майкрософт для конечной точки, защитник Майкрософт для Office 365, Microsoft Cloud App Security и защитник Майкрософт для удостоверения.</span><span class="sxs-lookup"><span data-stu-id="92b95-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="92b95-108">В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="92b95-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="92b95-109">Защитник Microsoft 365 автоматически включается, когда пользователи с необходимыми разрешениями могут посетить центр безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="92b95-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="92b95-110">В этой статье приводятся сведения о различных предварительных требованиях и способах подготовки защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="92b95-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="92b95-111">Проверка допустимости лицензий и необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="92b95-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="92b95-112">Лицензия на продукт Microsoft 365 Security обычно дает вам право использовать защитник Microsoft 365 в центре безопасности Майкрософт 365 без дополнительной стоимости лицензирования.</span><span class="sxs-lookup"><span data-stu-id="92b95-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="92b95-113">Мы рекомендуем получить лицензию безопасности Microsoft 365, а также лицензию, A5 или A5 или действительную комбинацию лицензий, предоставляющую доступ ко всем поддерживаемым службам.</span><span class="sxs-lookup"><span data-stu-id="92b95-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="92b95-114">Для получения подробных сведений о лицензировании [Прочтите требования к лицензированию](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="92b95-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="92b95-115">Проверка роли</span><span class="sxs-lookup"><span data-stu-id="92b95-115">Check your role</span></span>
<span data-ttu-id="92b95-116">Чтобы включить защитник Microsoft 365, необходимо быть **глобальным администратором** или **администратором безопасности** в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="92b95-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="92b95-117">Просмотр ролей в Azure AD</span><span class="sxs-lookup"><span data-stu-id="92b95-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="92b95-118">Поддерживаемые службы</span><span class="sxs-lookup"><span data-stu-id="92b95-118">Supported services</span></span>
<span data-ttu-id="92b95-119">Защитник Microsoft 365 собирает данные из различных поддерживаемых служб, которые вы уже развернули.</span><span class="sxs-lookup"><span data-stu-id="92b95-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="92b95-120">Он будет обрабатывать и хранить данные централизованно, чтобы определять новые аналитики и создавать централизованные рабочие процессы ответа.</span><span class="sxs-lookup"><span data-stu-id="92b95-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="92b95-121">Это происходит, не затрагивая существующие развертывания, параметры или данные, связанные со встроенными службами.</span><span class="sxs-lookup"><span data-stu-id="92b95-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="92b95-122">Чтобы получить лучшую защиту и оптимизировать защитник Microsoft 365, рекомендуем развернуть все поддерживаемые службы в сети.</span><span class="sxs-lookup"><span data-stu-id="92b95-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="92b95-123">Для получения дополнительных сведений [Ознакомьтесь с разворачиванием поддерживаемых служб](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="92b95-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="92b95-124">Перед запуском службы</span><span class="sxs-lookup"><span data-stu-id="92b95-124">Before starting the service</span></span>
<span data-ttu-id="92b95-125">Перед включением службы центр безопасности Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) отображает страницу параметров защитника Microsoft 365, когда вы выбираете **инциденты**, **Центр уведомлений** **или поиск** в области навигации.</span><span class="sxs-lookup"><span data-stu-id="92b95-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="92b95-126">Эти элементы навигации не отображаются, если вы не можете использовать защитник Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="92b95-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="92b95-127">![Изображение страницы параметров защитника Microsoft 365, которая отображается, если защитник Microsoft 365 не включен в ](../../media/mtp-enable/mtp-settings.png)
 *параметрах защитника Microsoft 365 в центре безопасности Майкрософт 365*</span><span class="sxs-lookup"><span data-stu-id="92b95-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="92b95-128">Запуск службы</span><span class="sxs-lookup"><span data-stu-id="92b95-128">Starting the service</span></span>
<span data-ttu-id="92b95-129">Чтобы включить защитник Microsoft 365, просто выберите **включить защитник microsoft 365** и примените изменение.</span><span class="sxs-lookup"><span data-stu-id="92b95-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="92b95-130">Вы также можете получить доступ к этому параметру, выбрав **Параметры** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) в области навигации, а затем выбрав **Microsoft 365 защитник**.</span><span class="sxs-lookup"><span data-stu-id="92b95-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

>[!NOTE]
><span data-ttu-id="92b95-131">Если вы не видите **Параметры** в области навигации или не смогли получить доступ к странице, проверьте свои разрешения и лицензии.</span><span class="sxs-lookup"><span data-stu-id="92b95-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="92b95-132">Расположение центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="92b95-132">Data center location</span></span>
<span data-ttu-id="92b95-133">Защитник Microsoft 365 будет хранить и обрабатывать данные в [одном и том же расположении, используемом защитником Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="92b95-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="92b95-134">Если у вас нет защитника Майкрософт для конечной точки, новое расположение центра обработки данных автоматически выбирается на основе расположения активных служб безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="92b95-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="92b95-135">Выбранное расположение центра обработки данных отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="92b95-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="92b95-136">Выберите пункт **нужна помощь?** в центре безопасности Майкрософт 365, чтобы обратиться в службу поддержки Майкрософт о подготовке защитника Microsoft 365 в другое расположение центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="92b95-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="92b95-137">Защитник Майкрософт для конечных точек автоматически подготавливается в центрах обработки данных Европейского союза (ЕС) при включенном защитнике Azure.</span><span class="sxs-lookup"><span data-stu-id="92b95-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="92b95-138">Защитник Microsoft 365 автоматически подготавливается к работе с тем же центром обработки данных ЕС для клиентов, у которых в такой манере подготовлен защитник для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="92b95-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="92b95-139">Подтверждение включения службы</span><span class="sxs-lookup"><span data-stu-id="92b95-139">Confirm that the service is on</span></span>
<span data-ttu-id="92b95-140">После подготовки службы в нее добавляются:</span><span class="sxs-lookup"><span data-stu-id="92b95-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="92b95-141">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="92b95-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="92b95-142">Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="92b95-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="92b95-143">[Расширенные](advanced-hunting-overview.md) возможности поисковых</span><span class="sxs-lookup"><span data-stu-id="92b95-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="92b95-144">![Изображение области навигации центра безопасности Microsoft 365 с помощью функции защитника Microsoft 365 ](../../media/mtp-enable/mtp-on.png)
 *Центр безопасности Microsoft 365 с функцией управления происшествиями и другими возможностями защитника Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="92b95-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="92b95-145">Сбор данных об удостоверении для защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="92b95-145">Getting Microsoft Defender for Identity data</span></span>
<span data-ttu-id="92b95-146">Чтобы предоставить доступ к защитнику Майкрософт для данных удостоверений с помощью защитника Microsoft 365, убедитесь, что Microsoft Cloud App Security и защитник Майкрософт для интеграции удостоверений включены.</span><span class="sxs-lookup"><span data-stu-id="92b95-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> [<span data-ttu-id="92b95-147">Подробнее об этой интеграции</span><span class="sxs-lookup"><span data-stu-id="92b95-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="get-assistance"></a><span data-ttu-id="92b95-148">Получение помощи</span><span class="sxs-lookup"><span data-stu-id="92b95-148">Get assistance</span></span>

<span data-ttu-id="92b95-149">Чтобы получить ответы на часто задаваемые вопросы о включении защитника Microsoft 365, [прочитайте вопросы и ответы](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="92b95-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="92b95-150">Сотрудники службы поддержки Майкрософт могут помочь подготовить или отменить подготовку службы и связанных ресурсов в клиенте.</span><span class="sxs-lookup"><span data-stu-id="92b95-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="92b95-151">Для получения помощи выберите **нужна помощь?** в центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="92b95-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="92b95-152">При обращении в службу поддержки следует упомянуть о защитнике Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="92b95-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="92b95-153">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="92b95-153">Related topics</span></span>

- [<span data-ttu-id="92b95-154">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="92b95-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="92b95-155">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="92b95-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="92b95-156">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="92b95-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="92b95-157">Обзор защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="92b95-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="92b95-158">Обзор защитника Майкрософт для конечных точек</span><span class="sxs-lookup"><span data-stu-id="92b95-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="92b95-159">Обзор защитника для Office 365</span><span class="sxs-lookup"><span data-stu-id="92b95-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="92b95-160">Обзор Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="92b95-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="92b95-161">Обзор защитника Майкрософт для удостоверения</span><span class="sxs-lookup"><span data-stu-id="92b95-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="92b95-162">Защитник Майкрософт для хранения данных конечной точки</span><span class="sxs-lookup"><span data-stu-id="92b95-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
