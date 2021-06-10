---
title: Этап 4. Миграция для Microsoft 365 для корпоративных клиентов
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Перенос устройств Windows, Office клиентских приложений и Office серверов для Microsoft 365 клиентов.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929148"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="3f5d8-104">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-104">Step 4.</span></span> <span data-ttu-id="3f5d8-105">Миграция для Microsoft 365 для корпоративных клиентов</span><span class="sxs-lookup"><span data-stu-id="3f5d8-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="3f5d8-106">Большинство корпоративных организаций имеют разнородную среду, которая включает несколько выпусков операционных систем, клиентского программного обеспечения и серверного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="3f5d8-107">Microsoft 365 для предприятия включает самые безопасные версии ключевых компонентов ИТ-инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="3f5d8-108">Он также включает функции производительности, предназначенные для использования облачных технологий.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="3f5d8-109">Чтобы максимально увеличить бизнес-значение пакета Microsoft 365 корпоративных интегрированных продуктов, приступить к планированию и реализации стратегии переноса этих выпусков:</span><span class="sxs-lookup"><span data-stu-id="3f5d8-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="3f5d8-110">From</span><span class="sxs-lookup"><span data-stu-id="3f5d8-110">From</span></span> | <span data-ttu-id="3f5d8-111">To</span><span class="sxs-lookup"><span data-stu-id="3f5d8-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="3f5d8-112">Windows 7 и Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3f5d8-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="3f5d8-113">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="3f5d8-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="3f5d8-114">Office клиентские продукты, установленные на устройствах вашего рабочего</span><span class="sxs-lookup"><span data-stu-id="3f5d8-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="3f5d8-115">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3f5d8-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="3f5d8-116">Office серверных продуктов, установленных на локальном сервере</span><span class="sxs-lookup"><span data-stu-id="3f5d8-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="3f5d8-117">Их эквивалентные облачные службы в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f5d8-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="3f5d8-118">Перенос в Windows 10</span><span class="sxs-lookup"><span data-stu-id="3f5d8-118">Migrating to Windows 10</span></span>

<span data-ttu-id="3f5d8-119">Каждый Microsoft 365 для корпоративной лицензии включает лицензию на Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="3f5d8-120">Чтобы перенести устройства, Windows 7 или Windows 8.1, можно выполнить обновление на месте.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="3f5d8-121">Поддержка завершилась Windows 7 *января 14 2020 г.*</span><span class="sxs-lookup"><span data-stu-id="3f5d8-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="3f5d8-122">Дополнительные методы установки Windows 10 Корпоративная после обновления на месте см. в Windows 10 [сценариях развертывания.](/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="3f5d8-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="3f5d8-123">Вы также можете [планировать развертывание Windows 10](/windows/deployment/planning/) самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="3f5d8-124">Миграция в Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3f5d8-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="3f5d8-125">Microsoft 365 для предприятия включает Приложения Microsoft 365 для предприятий версию клиентских продуктов Office (Word, PowerPoint, Excel и Outlook), которая устанавливается и обновляется из облака Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="3f5d8-126">Дополнительные сведения см. [в Приложения Microsoft 365 для предприятий.](/deployoffice/about-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="3f5d8-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="3f5d8-127">Вместо того, чтобы поддерживать ток компьютеров для Office 2019 или более старых версий, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3f5d8-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="3f5d8-128">Получите и назначьте Microsoft 365 лицензию для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="3f5d8-129">Удалить Office 2013 или Office 2016 на своих компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="3f5d8-130">Установите Приложения Microsoft 365 для предприятий, как индивидуально, так и во время ИТ-установки.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="3f5d8-131">Дополнительные сведения см. в [руководстве по развертыванию для Приложений Microsoft 365](/deployoffice/deployment-guide-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="3f5d8-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="3f5d8-132">Приложения Microsoft 365 для предприятий устанавливает как обновления безопасности, так и новые обновления функций автоматически и может использовать облачные службы в Microsoft 365 для повышения безопасности и производительности.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="3f5d8-133">Перенос локального сервера и данных в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f5d8-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="3f5d8-134">Microsoft 365 для предприятия включает облачные версии служб Office серверов, которые используют одни и те же инструменты, что и локальное программное обеспечение Office сервера, например веб-браузеры и клиент Outlook.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="3f5d8-135">Эти облачные службы автоматически обновляются для обеспечения безопасности и новых функций.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="3f5d8-136">После переноса ИТ-отдел может сэкономить время, необходимое для обслуживания и обновления локального сервера.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="3f5d8-137">Используйте следующие ресурсы для сведений о миграции пользователей и данных для определенных Microsoft 365 рабочих нагрузок:</span><span class="sxs-lookup"><span data-stu-id="3f5d8-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="3f5d8-138">Перемещение почтовых ящиков из локального Exchange Server в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3f5d8-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="3f5d8-139">Перенос SharePoint данных с SharePoint Server на SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3f5d8-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="3f5d8-140">Перенос Skype для бизнеса в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f5d8-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="3f5d8-141">Переход всей организации</span><span class="sxs-lookup"><span data-stu-id="3f5d8-141">Transition your entire organization</span></span>

<span data-ttu-id="3f5d8-142">Чтобы получить представление о том, как переместить всю организацию в продукты и службы в Microsoft 365 для предприятия, скачайте этот плакат перехода:</span><span class="sxs-lookup"><span data-stu-id="3f5d8-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="3f5d8-143">[![Изображение, показывающая переход на Microsoft 365 плаката.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="3f5d8-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="3f5d8-144">Этот двухстраничный плакат позволяет быстро ознакомиться с существующей инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="3f5d8-145">Используйте его для получения рекомендаций по переходу на продукт или службу в Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="3f5d8-146">В нем Windows и Office и другие элементы инфраструктуры и безопасности, такие как управление устройствами, защита удостоверений и угроз, защита информации и соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="3f5d8-147">Результаты шага 4</span><span class="sxs-lookup"><span data-stu-id="3f5d8-147">Results of Step 4</span></span>

<span data-ttu-id="3f5d8-148">Для миграции Microsoft 365 клиента вы определили:</span><span class="sxs-lookup"><span data-stu-id="3f5d8-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="3f5d8-149">Какие устройства работают Windows 7 или Windows 8.1 и план обновления их до Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="3f5d8-150">Какие устройства запускают Office клиентские приложения и планируют обновить их до Microsoft 365 приложений для предприятия.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="3f5d8-151">Какие локально Office серверные службы должны быть перенесены в Microsoft 365 эквивалент и план их миграции и их данных.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="3f5d8-152">Вот пример клиента с завершенной миграцией локального сервера.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Пример клиента с завершенной миграцией локального сервера](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="3f5d8-154">На этой иллюстрации организация имеет:</span><span class="sxs-lookup"><span data-stu-id="3f5d8-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="3f5d8-155">Перенос локального почтового ящика Exchange Server в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="3f5d8-156">Перенос локального сайта SharePoint серверов и данных в SharePoint в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="3f5d8-157">Текущее обслуживание для миграции</span><span class="sxs-lookup"><span data-stu-id="3f5d8-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="3f5d8-158">На постоянной основе может потребоваться:</span><span class="sxs-lookup"><span data-stu-id="3f5d8-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="3f5d8-159">В зависимости от состояния переноса Exchange почтовых ящиков продолжайте перетаповку Exchange Online в организацию.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="3f5d8-160">В зависимости от состояния локальной миграции SharePoint, продолжайте перенакрутку перехода на SharePoint в Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="3f5d8-161">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="3f5d8-161">Next step</span></span>

<span data-ttu-id="3f5d8-162">[![Шаг 5. Развертывание управления устройствами и приложениями](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="3f5d8-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="3f5d8-163">Продолжайте с [управлением устройствами и приложениями,](tenant-management-device-management.md) чтобы развернуть управление устройствами и приложениями.</span><span class="sxs-lookup"><span data-stu-id="3f5d8-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>