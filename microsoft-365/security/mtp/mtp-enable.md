---
title: Включи microsoft 365 Defender в центре безопасности Microsoft 365
description: Узнайте, как включить Microsoft 365 Defender и приступить к интеграции инцидентов и ответных действий в области безопасности.
keywords: начать работу, включить MTP, Microsoft Threat Protection, M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страницу параметров
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e7910866c494cf599022c17c29e3577e55cdba51
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928656"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="7ebcf-104">Включив защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7ebcf-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7ebcf-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7ebcf-105">**Applies to:**</span></span>
- <span data-ttu-id="7ebcf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ebcf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7ebcf-107">[Microsoft 365 Defender](microsoft-threat-protection.md) объединяет процесс реагирования на инциденты, интегрируя ключевые возможности в Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="7ebcf-108">В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="7ebcf-109">Microsoft 365 Defender автоматически включается при посещении центра безопасности Microsoft 365 подходящими клиентами с нужными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="7ebcf-110">Ознакомьтесь с этой статьей, чтобы разобраться в различных необходимых предпосылках и о том, как подготовка Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="7ebcf-111">Проверка прав на лицензию и необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="7ebcf-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="7ebcf-112">Лицензия на продукт безопасности Microsoft 365 обычно дает вам право использовать Microsoft 365 Defender в центре безопасности Microsoft 365 без дополнительных затрат на лицензирование.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="7ebcf-113">Мы рекомендуем получить лицензию Microsoft 365 E5, E5 Security, A5 или A5 Security или допустимое сочетание лицензий, которые предоставляют доступ ко всем поддерживаемым службам.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="7ebcf-114">Подробные сведения о лицензировании [читайте в публикации "Ъ" "Требования к лицензированию".](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="7ebcf-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="7ebcf-115">Проверка роли</span><span class="sxs-lookup"><span data-stu-id="7ebcf-115">Check your role</span></span>

<span data-ttu-id="7ebcf-116">Вы должны быть глобальным **администратором** или **администратором** безопасности в Azure Active Directory, чтобы включить Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="7ebcf-117">Просмотр ролей в Azure AD</span><span class="sxs-lookup"><span data-stu-id="7ebcf-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="7ebcf-118">Поддерживаемые службы</span><span class="sxs-lookup"><span data-stu-id="7ebcf-118">Supported services</span></span>

<span data-ttu-id="7ebcf-119">Microsoft 365 Defender собирает данные из различных поддерживаемых служб, которые вы уже развернули.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="7ebcf-120">Централизованная обработка и хранение данных будут определять новые сведения и делать возможными процессы централизованного реагирования.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="7ebcf-121">Это делается без влияния на существующие развертывания, параметры или данные, связанные с интегрированными службами.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="7ebcf-122">Чтобы получить лучшую защиту и оптимизировать Microsoft 365 Defender, рекомендуется развернуть все применимые поддерживаемые службы в сети.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="7ebcf-123">Дополнительные сведения читайте [в публикации "Ъ" "Развертывание поддерживаемых служб".](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="7ebcf-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="7ebcf-124">На борту службы</span><span class="sxs-lookup"><span data-stu-id="7ebcf-124">Onboard to the service</span></span>
<span data-ttu-id="7ebcf-125">Простота в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="7ebcf-126">В меню навигации выберите любой элемент в разделе Конечные точки, например Инциденты, Охота, Центр действий или аналитика угроз, чтобы инициировать процесс взбора.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-126">From the navigation menu, select any item under the Endpoints section, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="7ebcf-127">Расположение центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="7ebcf-127">Data center location</span></span>

<span data-ttu-id="7ebcf-128">Microsoft 365 Defender будет хранить и обрабатывать данные в том же расположении, что и [Microsoft Defender для конечной точки.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="7ebcf-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="7ebcf-129">Если у вас нет Microsoft Defender для конечной точки, новое расположение центра обработки данных автоматически выбирается в зависимости от расположения активных служб безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="7ebcf-130">Выбранное расположение центра обработки данных отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="7ebcf-131">Выберите **Необходимую помощь?** в центре безопасности Microsoft 365 связаться с службой поддержки Майкрософт по поводу обеспечения Microsoft 365 Defender в другом расположении центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="7ebcf-132">Microsoft Defender для конечной точки автоматически содержит положения в центрах обработки данных Европейского союза (ЕС) при включении через Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="7ebcf-133">Microsoft 365 Defender автоматически будет в том же центре обработки данных ЕС для клиентов, которые таким образом закапировали Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="7ebcf-134">Подтверждение включения службы</span><span class="sxs-lookup"><span data-stu-id="7ebcf-134">Confirm that the service is on</span></span>

<span data-ttu-id="7ebcf-135">После подготовки службы в нее добавляются:</span><span class="sxs-lookup"><span data-stu-id="7ebcf-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="7ebcf-136">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="7ebcf-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="7ebcf-137">Очередь оповещений</span><span class="sxs-lookup"><span data-stu-id="7ebcf-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="7ebcf-138">Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="7ebcf-138">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="7ebcf-139">[Расширенные возможности](advanced-hunting-overview.md) охоты</span><span class="sxs-lookup"><span data-stu-id="7ebcf-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="7ebcf-140">Аналитика угроз</span><span class="sxs-lookup"><span data-stu-id="7ebcf-140">Threat analytics</span></span>

<span data-ttu-id="7ebcf-141">![Изображение области навигации центра безопасности Microsoft 365 с Microsoft 365 Defender имеет центр безопасности Microsoft 365 с управлением инцидентами и другими возможностями ](../../media/mtp-enable/mtp-on.png)
 *Защитника Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="7ebcf-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="7ebcf-142">Получение данных Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="7ebcf-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="7ebcf-143">Чтобы включить интеграцию с microsoft Cloud App Security, необходимо хотя бы один раз войти в службу безопасности облачных приложений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="7ebcf-144">Получение помощи</span><span class="sxs-lookup"><span data-stu-id="7ebcf-144">Get assistance</span></span>

<span data-ttu-id="7ebcf-145">Чтобы получить ответы на наиболее часто задаваемые вопросы о включив Microsoft 365 Defender, ознакомьтесь с часто задаваемой [проблемой.](mtp-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="7ebcf-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="7ebcf-146">Сотрудники службы поддержки Майкрософт могут помочь в предоставлении или откормке службы и связанных с ней ресурсов на клиенте.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="7ebcf-147">Для оказания помощи выберите **Need Help?** в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="7ebcf-148">При контакте с поддержкой упоминают Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7ebcf-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7ebcf-149">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="7ebcf-149">Related topics</span></span>

- [<span data-ttu-id="7ebcf-150">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="7ebcf-150">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="7ebcf-151">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7ebcf-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="7ebcf-152">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="7ebcf-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="7ebcf-153">Обзор Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7ebcf-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="7ebcf-154">Обзор Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7ebcf-154">Microsoft Defender for Endpoint overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="7ebcf-155">Обзор Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="7ebcf-155">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="7ebcf-156">Обзор Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7ebcf-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="7ebcf-157">Обзор Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="7ebcf-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="7ebcf-158">Microsoft Defender для хранения данных конечной точки</span><span class="sxs-lookup"><span data-stu-id="7ebcf-158">Microsoft Defender for Endpoint data storage</span></span>](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)