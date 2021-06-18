---
title: Включи Microsoft 365 Defender в центре Microsoft 365 безопасности
description: Узнайте, как включить Microsoft 365 Defender и приступить к интеграции инцидентов и ответных действий в области безопасности.
keywords: начать работу, включить Microsoft 365 Defender, Microsoft 365 Defender, M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страницу параметров
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 102666834562d0576920c746842582c2870b3738
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007613"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="6b7ea-104">Включение Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b7ea-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6b7ea-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6b7ea-105">**Applies to:**</span></span>
- <span data-ttu-id="6b7ea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b7ea-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6b7ea-107">[Microsoft 365 Defender](microsoft-365-defender.md) объединяет процесс реагирования на инциденты, интегрируя ключевые возможности в Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="6b7ea-108">В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="6b7ea-109">Microsoft 365 Defender автоматически включается, когда подходящие клиенты с нужными разрешениями посещают Microsoft 365 центр безопасности.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="6b7ea-110">Ознакомьтесь с этой статьей, чтобы понять различные предпосылки и Microsoft 365 Defender подготовка.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="6b7ea-111">Проверка прав на лицензию и необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="6b7ea-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="6b7ea-112">Лицензия на продукт Microsoft 365 безопасности обычно дает право на использование Microsoft 365 Defender в центре Microsoft 365 безопасности без дополнительных затрат на лицензирование.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="6b7ea-113">Мы рекомендуем получить лицензию Microsoft 365 E5, E5 Security, A5 или A5 Security или допустимое сочетание лицензий, которые предоставляют доступ ко всем поддерживаемым службам.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="6b7ea-114">Подробные сведения о лицензировании [читайте в публикации "Ъ" "Требования к лицензированию".](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="6b7ea-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="6b7ea-115">Проверка роли</span><span class="sxs-lookup"><span data-stu-id="6b7ea-115">Check your role</span></span>

<span data-ttu-id="6b7ea-116">Вы должны быть глобальным **администратором** или **администратором** безопасности в Azure Active Directory, чтобы включить Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="6b7ea-117">Просмотр ролей в Azure AD</span><span class="sxs-lookup"><span data-stu-id="6b7ea-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="6b7ea-118">Поддерживаемые службы</span><span class="sxs-lookup"><span data-stu-id="6b7ea-118">Supported services</span></span>

<span data-ttu-id="6b7ea-119">Microsoft 365 Defender собирает данные из различных поддерживаемых служб, которые вы уже развернули.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="6b7ea-120">Централизованная обработка и хранение данных будут определять новые сведения и делать возможными процессы централизованного реагирования.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="6b7ea-121">Это делается без влияния на существующие развертывания, параметры или данные, связанные с интегрированными службами.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="6b7ea-122">Чтобы получить лучшую защиту и оптимизировать Microsoft 365 Defender, рекомендуется развернуть все применимые поддерживаемые службы в вашей сети.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="6b7ea-123">Дополнительные сведения читайте [в публикации "Ъ" "Развертывание поддерживаемых служб".](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="6b7ea-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="6b7ea-124">На борту службы</span><span class="sxs-lookup"><span data-stu-id="6b7ea-124">Onboard to the service</span></span>
<span data-ttu-id="6b7ea-125">В Microsoft 365 Defender просто.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="6b7ea-126">В меню навигации выберите любой элемент, **например**& оповещений,  **охоты,** центра действий или аналитики угроз, чтобы инициировать процесс взбора.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-126">From the navigation menu, select any item, such as **Incidents & alerts**, **Hunting**, **Action center**, or **Threat analytics** to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="6b7ea-127">Расположение центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="6b7ea-127">Data center location</span></span>

<span data-ttu-id="6b7ea-128">Microsoft 365 Defender будет хранить и обрабатывать данные в том же расположении, что и [Microsoft Defender для конечной точки.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="6b7ea-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="6b7ea-129">Если у вас нет Microsoft Defender для конечной точки, новое расположение центра обработки данных автоматически выбирается в зависимости от расположения активных служб Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="6b7ea-130">Выбранное расположение центра обработки данных отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="6b7ea-131">Выберите **Необходимую помощь?** в центре Microsoft 365, чтобы связаться с службой поддержки Майкрософт по Microsoft 365 Defender в другом расположении центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="6b7ea-132">В прошлом Центр обработки данных Microsoft Defender для конечной точки автоматически был включен в центрах обработки данных Европейского союза (ЕС) при включенном в Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-132">In the past, Microsoft Defender for Endpoint automatically provisioned in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="6b7ea-133">Microsoft 365 Defender автоматическое предоставление в том же центре обработки данных ЕС для клиентов, которые в прошлом таким образом обуяли Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner in the past.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="6b7ea-134">Подтверждение включения службы</span><span class="sxs-lookup"><span data-stu-id="6b7ea-134">Confirm that the service is on</span></span>

<span data-ttu-id="6b7ea-135">После подготовки службы в нее добавляются:</span><span class="sxs-lookup"><span data-stu-id="6b7ea-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="6b7ea-136">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="6b7ea-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="6b7ea-137">Очередь оповещений</span><span class="sxs-lookup"><span data-stu-id="6b7ea-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="6b7ea-138">Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="6b7ea-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="6b7ea-139">[Расширенные возможности](advanced-hunting-overview.md) охоты</span><span class="sxs-lookup"><span data-stu-id="6b7ea-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="6b7ea-140">Аналитика угроз</span><span class="sxs-lookup"><span data-stu-id="6b7ea-140">Threat analytics</span></span>

<span data-ttu-id="6b7ea-141">![Изображение области навигации Microsoft 365 центра безопасности с Microsoft 365 Defender функциями Microsoft 365 безопасности с управлением инцидентами и другими ](../../media/overview-incident.png)
 *Microsoft 365 Defender возможностями*</span><span class="sxs-lookup"><span data-stu-id="6b7ea-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="6b7ea-142">Получение данных Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="6b7ea-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="6b7ea-143">Чтобы включить интеграцию Microsoft Cloud App Security, необходимо хотя бы один раз войти в Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="6b7ea-144">Получение помощи</span><span class="sxs-lookup"><span data-stu-id="6b7ea-144">Get assistance</span></span>

<span data-ttu-id="6b7ea-145">Чтобы получить ответы на наиболее часто задаваемые вопросы о включаемой Microsoft 365 Defender, ознакомьтесь [с часто задаваемой проблемой.](m365d-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="6b7ea-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="6b7ea-146">Сотрудники службы поддержки Майкрософт могут помочь в предоставлении или откормке службы и связанных с ней ресурсов на клиенте.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="6b7ea-147">Для оказания помощи выберите **"Нужна помощь"?** в центре Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="6b7ea-148">При контакте с поддержкой упоминают Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6b7ea-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b7ea-149">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6b7ea-149">Related topics</span></span>

- [<span data-ttu-id="6b7ea-150">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="6b7ea-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="6b7ea-151">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6b7ea-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="6b7ea-152">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="6b7ea-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="6b7ea-153">Microsoft 365 Defender обзор</span><span class="sxs-lookup"><span data-stu-id="6b7ea-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="6b7ea-154">Обзор Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6b7ea-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="6b7ea-155">Обзор defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="6b7ea-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="6b7ea-156">Обзор Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6b7ea-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="6b7ea-157">Обзор Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="6b7ea-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="6b7ea-158">Microsoft Defender для хранения данных конечной точки</span><span class="sxs-lookup"><span data-stu-id="6b7ea-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
