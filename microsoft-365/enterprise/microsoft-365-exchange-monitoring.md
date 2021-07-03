---
title: Мониторинг Exchange Online для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Используйте мониторинг Exchange Online для получения сведений об инцидентах или предупреждениях электронной почты в Microsoft 365.
ms.openlocfilehash: 3d88378449879d451b21ba8bf2a7b5c3032a2c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286445"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="6abb1-103">Мониторинг Exchange Online для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6abb1-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="6abb1-104">С помощью мониторинга Exchange Online в Центре администрирования Microsoft 365 вы можете отслеживать работоспособность службы Exchange в рамках подписки Microsoft 365 вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6abb1-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="6abb1-105">Мониторинг Exchange Online предоставляет информацию об инцидентах и предупреждениях, собираемых в следующих категориях:</span><span class="sxs-lookup"><span data-stu-id="6abb1-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="6abb1-106">**Инфраструктура**. Проблема обнаружена в инфраструктуре Microsoft 365, принадлежащей корпорации Майкрософт и используемой для обеспечения регулярных обновлений и устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="6abb1-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="6abb1-107">Например, пользователи не могут получить доступ к Exchange Online из-за проблем в Exchange или другой облачной инфраструктуре Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6abb1-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="6abb1-108">**Сторонняя инфраструктура**. Проблема обнаружена в сторонней инфраструктуре, от которой зависит ваша организация. Для ее устранения требуется действие от вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6abb1-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="6abb1-109">Например, операции проверки подлинности пользователей регулируются сторонним поставщиком службы маркеров безопасности (STS), который не позволяет пользователям подключаться к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6abb1-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="6abb1-110">**Пользовательская инфраструктура**. Проблема обнаружена в инфраструктуре вашей организации, и для ее устранения требуется действие от вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6abb1-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="6abb1-111">Например, пользователи не могут получить доступ к Exchange Online, так как они не могут получить маркер проверки подлинности от поставщика STS, размещенного в вашей организации, из-за просроченного сертификата.</span><span class="sxs-lookup"><span data-stu-id="6abb1-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="6abb1-112">Ниже приведен пример страницы **Работоспособность служб** в Центре администрирования Microsoft 365, доступной в разделе **Работоспособность > Работоспособность службы**.</span><span class="sxs-lookup"><span data-stu-id="6abb1-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![Страница "Работоспособность служб" в Центре администрирования Microsoft 365](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="6abb1-114">Значение столбца **Состояние** указывает, является ли служба работоспособной или с ней связаны предупреждения и инциденты на основе облачных служб, поддерживаемых корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6abb1-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="6abb1-115">Значение в столбце **Проблемы вашей организации и сторонних поставщиков** указывает, что инфраструктура вашей организации или сторонние программы влияют на работоспособность служб пользователей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6abb1-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="6abb1-116">Предупреждения и инциденты требуют *ваших* действий по устранению.</span><span class="sxs-lookup"><span data-stu-id="6abb1-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="6abb1-117">Ниже приведен пример страницы мониторинга **Exchange Online** в Центре администрирования Microsoft 365, доступной в разделе **Работоспособность > Работоспособность службы > Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="6abb1-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![Страница мониторинга Exchange Online в Центре администрирования Microsoft 365](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="6abb1-119">На странице мониторинга **Exchange Online** вы можете увидеть, работоспособна ли служба Exchange Online и связаны ли с ней какие-либо инциденты и предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6abb1-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="6abb1-120">С помощью мониторинга Exchange Online вы можете просмотреть работоспособность служб для определенных почтовых сценариев и увидеть сигналы почти в режиме реального времени для определения воздействия сценария.</span><span class="sxs-lookup"><span data-stu-id="6abb1-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="6abb1-121">Требования</span><span class="sxs-lookup"><span data-stu-id="6abb1-121">Requirements</span></span>

<span data-ttu-id="6abb1-122">Эта предварительная версия включена для пользователей, отвечающих следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="6abb1-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="6abb1-123">У вашей организации должно быть не менее 5 000 лицензий на один или несколько следующих продуктов: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6abb1-123">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="6abb1-124">Например, у вашей организации может быть 3 000 лицензий Office 365 E3 и 2 500 лицензий Microsoft 365 E5, что в итоге составляет 5 500 лицензий на соответствующие продукты.</span><span class="sxs-lookup"><span data-stu-id="6abb1-124">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="6abb1-125">У вашей организации должно быть как минимум 50 активных пользователей Exchange Online ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="6abb1-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="6abb1-126">С помощью мониторинга Exchange Online вы можете просматривать сведения о работоспособности следующих почтовых клиентов на основе действий по чтению писем:</span><span class="sxs-lookup"><span data-stu-id="6abb1-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="6abb1-127">Классическое приложение Outlook</span><span class="sxs-lookup"><span data-stu-id="6abb1-127">Outlook Desktop</span></span>
- <span data-ttu-id="6abb1-128">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="6abb1-128">Outlook on the Web</span></span>
- <span data-ttu-id="6abb1-129">Собственные почтовые клиенты iOS и Android</span><span class="sxs-lookup"><span data-stu-id="6abb1-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="6abb1-130">Приложение Outlook Mobile в iOS и Android</span><span class="sxs-lookup"><span data-stu-id="6abb1-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="6abb1-131">Клиент Outlook Mac</span><span class="sxs-lookup"><span data-stu-id="6abb1-131">Outlook Mac client</span></span>

<span data-ttu-id="6abb1-132">В этих клиентах вы можете просматривать количество активных пользователей за последние 30 минут на основе чтения писем пользователями, а также количество инцидентов и предупреждений в панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="6abb1-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="6abb1-133">Эти данные сравниваются с тем же интервалом прошлой недели, чтобы проверить, имеется ли проблема.</span><span class="sxs-lookup"><span data-stu-id="6abb1-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="6abb1-134">Количество активных пользователей измеряется по одному действию, например при чтении пользователем письма.</span><span class="sxs-lookup"><span data-stu-id="6abb1-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="6abb1-135">В это показателе учитываются действия только за последние 30 минут.</span><span class="sxs-lookup"><span data-stu-id="6abb1-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="6abb1-136">Кроме того, вы можете отслеживать работоспособность Exchange Online в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="6abb1-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="6abb1-137">**Поток обработки почты**. Количество сообщений, успешно доставленных в почтовый ящик без задержек после того, как сообщение достигло сети Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6abb1-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="6abb1-138">**Обычная проверка подлинности и современная проверка подлинности**. Количество пользователей, успешно прошедших проверку в службе Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6abb1-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![Пример мониторинга работоспособности Exchange для доставки почты](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="6abb1-140">Во всех этих сценариях ключевые показатели указываются в основной панели мониторинга за последние 30 минут.</span><span class="sxs-lookup"><span data-stu-id="6abb1-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="6abb1-141">В подробных представлениях для каждого из этих сценариев демонстрируется тренд почти в режиме реального времени за последние семь дней с 30-минутным агрегированием в сравнении с прошлой неделей.</span><span class="sxs-lookup"><span data-stu-id="6abb1-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="6abb1-142">Отправка отзывов и предложений</span><span class="sxs-lookup"><span data-stu-id="6abb1-142">Send us feedback</span></span>

<span data-ttu-id="6abb1-143">Существует два способа обратной связи:</span><span class="sxs-lookup"><span data-stu-id="6abb1-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="6abb1-144">Использование параметра **Оставить отзыв**, доступного на каждой странице Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6abb1-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="6abb1-145">Отправка отзыва с помощью ссылки **Эта запись полезна?** для определенного инцидента или предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6abb1-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![Ссылка "Эта запись полезна?"](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="6abb1-148">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="6abb1-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6abb1-149">1. Почему я не вижу элемент "Мониторинг Exchange Online" в разделе "Работоспособность" Центра администрирования Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="6abb1-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="6abb1-150">Сначала включите новый Центр администрирования на **главной** странице Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6abb1-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="6abb1-151">Затем убедитесь, что вы отвечаете обоим следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="6abb1-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="6abb1-152">У вашей организации должно быть не менее 5 000 лицензий на один или несколько следующих продуктов: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6abb1-152">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="6abb1-153">У вашей организации должно быть как минимум 50 активных пользователей Exchange Online ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="6abb1-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="6abb1-154">Если количество лицензий в вашей организации ниже 5 000, а число активных пользователей — менее 50 в месяц, мониторинг Exchange Online не будет включен, пока не будут выполнены эти требования.</span><span class="sxs-lookup"><span data-stu-id="6abb1-154">If the license count for your organization goes below 5,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="6abb1-155">2. На панели мониторинга для каждого клиента отображается малое количество активных пользователей.</span><span class="sxs-lookup"><span data-stu-id="6abb1-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="6abb1-156">У нас есть много активных лицензий, назначенных пользователям.</span><span class="sxs-lookup"><span data-stu-id="6abb1-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="6abb1-157">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="6abb1-157">What does this mean?</span></span> 

<span data-ttu-id="6abb1-158">Количество активных пользователей, отображаемое при мониторинге, основано на 30-минутном промежутке, в котором пользователи выполняли действия, указанные в функции.</span><span class="sxs-lookup"><span data-stu-id="6abb1-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="6abb1-159">Это не следует путать с количеством использований.</span><span class="sxs-lookup"><span data-stu-id="6abb1-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="6abb1-160">Чтобы просмотреть количество использований, воспользуйтесь отчетами о действиях в Центре администрирования Microsoft 365 (**Отчеты > Использование**).</span><span class="sxs-lookup"><span data-stu-id="6abb1-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="6abb1-161">3. Будут ли доступны другие сценарии мониторинга для других служб, таких как Teams и SharePoint?</span><span class="sxs-lookup"><span data-stu-id="6abb1-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="6abb1-162">Майкрософт интегрирует эту функцию непосредственно в панель мониторинга работоспособности служб в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6abb1-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6abb1-163">Это позволит корпорации Майкрософт расширить сценарии мониторинга для других служб, о чем будет объявлено при появлении соответствующих новостей.</span><span class="sxs-lookup"><span data-stu-id="6abb1-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="6abb1-164">4. Каков план в отношении общей доступности этой функции?</span><span class="sxs-lookup"><span data-stu-id="6abb1-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="6abb1-165">Корпорация Майкрософт интегрировала мониторинг Exchange Online непосредственно в панель мониторинга **Работоспособность служб** в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6abb1-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="6abb1-166">С помощью этой новой интегрированной функции корпорация Майкрософт планирует собрать ваши отзывы, а затем определить план в отношении общей доступности.</span><span class="sxs-lookup"><span data-stu-id="6abb1-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="6abb1-167">5. Это бесплатная (включенная) или платная (дополнительная) функция?</span><span class="sxs-lookup"><span data-stu-id="6abb1-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="6abb1-168">Эта функция выпущена в общедоступной предварительной версии и доступна только для пользователей, удовлетворяющих требованиям из вопроса 1.</span><span class="sxs-lookup"><span data-stu-id="6abb1-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="6abb1-169">6. Как оставить отзыв?</span><span class="sxs-lookup"><span data-stu-id="6abb1-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="6abb1-170">Для общего отзыва используйте значок **Оставить отзыв** в правом нижнем углу страницы мониторинга **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="6abb1-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="6abb1-171">Для отзыва об инцидентах или предупреждениях используйте ссылку **Эта запись полезна?**</span><span class="sxs-lookup"><span data-stu-id="6abb1-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="6abb1-172">7. Где обрабатываются данные для сценариев, демонстрирующих тренды действий?</span><span class="sxs-lookup"><span data-stu-id="6abb1-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="6abb1-p114">Данные обрабатываются в службе Exchange Online. Если возникнет сбой, прежде чем запрос достигнет службы Exchange Online, или возникнет сбой в Exchange Online, вы увидите падение сигнала активности.</span><span class="sxs-lookup"><span data-stu-id="6abb1-p114">The data is instrumented in the Exchange Online service. If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>
