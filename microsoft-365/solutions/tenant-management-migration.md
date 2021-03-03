---
title: Этап 4. Миграция для microsoft 365 для корпоративных клиентов
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
description: Перенос устройств Windows, клиентских приложений Office и серверов Office для клиентов Microsoft 365.
ms.openlocfilehash: 85f1c0d927b881c4d1526ce538ae54f5954a0664
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406364"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="b731e-104">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="b731e-104">Step 4.</span></span> <span data-ttu-id="b731e-105">Миграция для microsoft 365 для корпоративных клиентов</span><span class="sxs-lookup"><span data-stu-id="b731e-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="b731e-106">Большинство корпоративных организаций имеют разнородную среду, которая включает несколько выпусков операционных систем, клиентского программного обеспечения и серверного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b731e-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="b731e-107">Microsoft 365 для предприятия включает самые безопасные версии ключевых компонентов ИТ-инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="b731e-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="b731e-108">Он также включает функции производительности, предназначенные для использования облачных технологий.</span><span class="sxs-lookup"><span data-stu-id="b731e-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="b731e-109">Чтобы максимально увеличить бизнес-значение пакета продуктов Microsoft 365 для корпоративных интегрированных продуктов, приступить к планированию и реализации стратегии переноса этих выпусков:</span><span class="sxs-lookup"><span data-stu-id="b731e-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="b731e-110">От</span><span class="sxs-lookup"><span data-stu-id="b731e-110">From</span></span> | <span data-ttu-id="b731e-111">To</span><span class="sxs-lookup"><span data-stu-id="b731e-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="b731e-112">Windows 7 и Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b731e-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="b731e-113">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="b731e-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="b731e-114">Клиентские продукты Office, установленные на устройствах вашего рабочего</span><span class="sxs-lookup"><span data-stu-id="b731e-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="b731e-115">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="b731e-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="b731e-116">Продукты office server, установленные на локальном сервере</span><span class="sxs-lookup"><span data-stu-id="b731e-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="b731e-117">Их эквивалентные облачные службы в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b731e-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="b731e-118">Перенос в Windows 10</span><span class="sxs-lookup"><span data-stu-id="b731e-118">Migrating to Windows 10</span></span>

<span data-ttu-id="b731e-119">Каждый Microsoft 365 для корпоративной лицензии включает лицензию для Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b731e-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="b731e-120">Чтобы перенести устройства с Windows 7 или Windows 8.1, можно выполнить обновление на месте.</span><span class="sxs-lookup"><span data-stu-id="b731e-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="b731e-121">Поддержка windows 7 завершилась *14 января 2020 г.*</span><span class="sxs-lookup"><span data-stu-id="b731e-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="b731e-122">Дополнительные методы установки Windows 10 Enterprise после обновления на месте см. в примере сценариев [развертывания Windows 10.](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="b731e-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="b731e-123">Вы также можете [планировать развертывание Windows 10](https://aka.ms/planforwin10deployment) самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="b731e-123">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b731e-124">Перенос в Microsoft 365 Apps для предприятия</span><span class="sxs-lookup"><span data-stu-id="b731e-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="b731e-125">Microsoft 365 для предприятия включает Microsoft 365 Apps для предприятия, версию клиентских продуктов Office (Word, PowerPoint, Excel и Outlook), которая устанавливается и обновляется из облака Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b731e-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="b731e-126">Дополнительные сведения см. [в дополнительных сведениях о приложениях Microsoft 365 для предприятия.](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="b731e-126">For more information, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="b731e-127">Вместо того, чтобы поддерживать ток компьютеров для Версий Office 2019 или более старых версий, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b731e-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="b731e-128">Получите и назначьте пользователям лицензию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b731e-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="b731e-129">Удалить Office 2013 или Office 2016 на своих компьютерах.</span><span class="sxs-lookup"><span data-stu-id="b731e-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="b731e-130">Установите приложения Microsoft 365 для предприятия как индивидуально, так и во время ИТ-2018.</span><span class="sxs-lookup"><span data-stu-id="b731e-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="b731e-131">Дополнительные сведения см. в [руководстве по развертыванию приложений Microsoft 365.](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="b731e-131">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="b731e-132">Приложения Microsoft 365 для предприятия устанавливают обновления безопасности и обновления новых функций автоматически и могут использовать облачные службы в Microsoft 365 для повышения безопасности и производительности.</span><span class="sxs-lookup"><span data-stu-id="b731e-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="b731e-133">Перенос локального сервера и данных в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b731e-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="b731e-134">Microsoft 365 для предприятия включает облачные версии служб office server, которые используют одни и те же инструменты, что и локальное программное обеспечение сервера Office, например веб-браузеры и клиент Outlook.</span><span class="sxs-lookup"><span data-stu-id="b731e-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="b731e-135">Эти облачные службы автоматически обновляются для обеспечения безопасности и новых функций.</span><span class="sxs-lookup"><span data-stu-id="b731e-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="b731e-136">После переноса ИТ-отдел может сэкономить время, необходимое для обслуживания и обновления локального сервера.</span><span class="sxs-lookup"><span data-stu-id="b731e-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="b731e-137">Используйте следующие ресурсы для сведений о миграции пользователей и данных для определенных рабочих нагрузок Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="b731e-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="b731e-138">Перемещение почтовых ящиков из локального Exchange Server в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b731e-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="b731e-139">Перенос данных SharePoint с SharePoint Server на SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b731e-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="b731e-140">Перенос Skype для бизнеса в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b731e-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="b731e-141">Переход всей организации</span><span class="sxs-lookup"><span data-stu-id="b731e-141">Transition your entire organization</span></span>

<span data-ttu-id="b731e-142">Чтобы получить представление о том, как переместить всю организацию в продукты и службы в Microsoft 365 для предприятия, скачайте этот плакат перехода:</span><span class="sxs-lookup"><span data-stu-id="b731e-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="b731e-143">[![Изображение плаката Переход на Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="b731e-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="b731e-144">Этот двухстраничный плакат позволяет быстро ознакомиться с существующей инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="b731e-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="b731e-145">Используйте его для получения рекомендаций по переходу на продукт или службу в Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="b731e-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="b731e-146">В нем показаны продукты Windows и Office, а также другие элементы инфраструктуры и безопасности, такие как управление устройствами, защита от личных данных и угроз, а также защита и соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="b731e-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="b731e-147">Результаты шага 4</span><span class="sxs-lookup"><span data-stu-id="b731e-147">Results of Step 4</span></span>

<span data-ttu-id="b731e-148">Для миграции клиента Microsoft 365 вы определили:</span><span class="sxs-lookup"><span data-stu-id="b731e-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="b731e-149">На каких устройствах работает Windows 7 или Windows 8.1, и планируется обновить их до Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b731e-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="b731e-150">На каких устройствах запущены клиентские приложения Office и планируется обновить их до приложений Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="b731e-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="b731e-151">Какие локально-серверные службы Office должны быть перенесены в эквивалент Microsoft 365 и планируется перенести их и их данные.</span><span class="sxs-lookup"><span data-stu-id="b731e-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="b731e-152">Вот пример клиента с завершенной миграцией локального сервера.</span><span class="sxs-lookup"><span data-stu-id="b731e-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Пример клиента с завершенной миграцией локального сервера](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="b731e-154">На этой иллюстрации организация имеет:</span><span class="sxs-lookup"><span data-stu-id="b731e-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="b731e-155">Перенос локального почтового ящика Exchange Server в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b731e-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="b731e-156">Перенос локального сайта и данных SharePoint Server в SharePoint в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b731e-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="b731e-157">Текущее обслуживание для миграции</span><span class="sxs-lookup"><span data-stu-id="b731e-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="b731e-158">На постоянной основе может потребоваться:</span><span class="sxs-lookup"><span data-stu-id="b731e-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="b731e-159">В зависимости от состояния миграции почтовых ящиков Exchange продолжайте перенос перехода в Exchange Online в организацию.</span><span class="sxs-lookup"><span data-stu-id="b731e-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="b731e-160">В зависимости от состояния локальной миграции сайта SharePoint продолжайте переназначение перехода на SharePoint в Microsoft 365 в организацию.</span><span class="sxs-lookup"><span data-stu-id="b731e-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="b731e-161">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="b731e-161">Next step</span></span>

<span data-ttu-id="b731e-162">[![Шаг 5. Развертывание управления устройствами и приложениями](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="b731e-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="b731e-163">Продолжайте с [управлением устройствами и приложениями,](tenant-management-device-management.md) чтобы развернуть управление устройствами и приложениями.</span><span class="sxs-lookup"><span data-stu-id="b731e-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>
