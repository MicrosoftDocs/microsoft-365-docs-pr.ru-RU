---
title: Создание и отслеживание билетов с помощью ServiceNow
description: Узнайте, как создавать и отслеживать билеты в ServiceNow из центра безопасности Майкрософт 365.
keywords: безопасность, Microsoft 365, M365, Оценка безопасности, центр безопасности, ServiceNow, билеты, задачи
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 6070878d6cf0efd8a85d05ff6ef89ee49baf4144
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034192"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="78e09-104">Управление билетами с помощью ServiceNow</span><span class="sxs-lookup"><span data-stu-id="78e09-104">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="78e09-105">ServiceNow — это популярная платформа облачных вычислений, которая помогает компаниям управлять цифровыми рабочими процессами для корпоративных операций.</span><span class="sxs-lookup"><span data-stu-id="78e09-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="78e09-106">На их платформах теперь есть рабочие процессы, рабочие процессы сотрудников и рабочие процессы клиентов.</span><span class="sxs-lookup"><span data-stu-id="78e09-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> <span data-ttu-id="78e09-107">Корпорация Майкрософт поделилась с ServiceNow, чтобы облегчить ИТ-администраторам управлять своими билетами и задачами на обеих платформах.</span><span class="sxs-lookup"><span data-stu-id="78e09-107">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> [<span data-ttu-id="78e09-108">Дополнительные сведения о ServiceNow</span><span class="sxs-lookup"><span data-stu-id="78e09-108">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="78e09-109">Центр обеспечения безопасности Microsoft 365 теперь дополнен возможностью самостоятельно создавать и отслеживать билеты в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-109">Microsoft 365 security center is now enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="78e09-110">Администраторы безопасности могут отправить действие улучшения [оценки безопасности Майкрософт](microsoft-secure-score.md) непосредственно в ServiceNow и создать билет.</span><span class="sxs-lookup"><span data-stu-id="78e09-110">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="78e09-111">Могут быть созданы как управление инцидентами, так и билеты управления изменениями.</span><span class="sxs-lookup"><span data-stu-id="78e09-111">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="78e09-112">Затем их можно отслеживать на домашней странице центра безопасности Майкрософт и ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-112">They can then be tracked in the Microsoft security center home page, and ServiceNow.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="78e09-113">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="78e09-113">Prerequisites</span></span>

<span data-ttu-id="78e09-114">Получить доступ к центру безопасности Microsoft 365 и экземпляру ServiceNow с помощью следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="78e09-114">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="78e09-115">Кингстон или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="78e09-115">Kingston or higher version</span></span>
* <span data-ttu-id="78e09-116">Иметь учетные данные администратора HI</span><span class="sxs-lookup"><span data-stu-id="78e09-116">Have admin HI credentials</span></span>
* <span data-ttu-id="78e09-117">Иметь права администратора в экземпляре целевого поставщика</span><span class="sxs-lookup"><span data-stu-id="78e09-117">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="78e09-118">ServiceNow рекомендует пользователям хранить параметры по умолчанию в своем экземпляре ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-118">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="78e09-119">Настройка может привести к ошибкам при завершении работы контрольного списка установки и интеграции с центром безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78e09-119">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="78e09-120">обмен данными;</span><span class="sxs-lookup"><span data-stu-id="78e09-120">Data exchange</span></span>

<span data-ttu-id="78e09-121">При подключении центра безопасности Microsoft 365 к ServiceNow Корпорация Майкрософт получает следующие дополнительные данные:</span><span class="sxs-lookup"><span data-stu-id="78e09-121">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="78e09-122">Имя экземпляра ServiceNow</span><span class="sxs-lookup"><span data-stu-id="78e09-122">ServiceNow instance name</span></span>
* <span data-ttu-id="78e09-123">ИД клиента ServiceNow</span><span class="sxs-lookup"><span data-stu-id="78e09-123">ServiceNow client ID</span></span>
* <span data-ttu-id="78e09-124">Секрет клиента ServiceNow</span><span class="sxs-lookup"><span data-stu-id="78e09-124">ServiceNow client secret</span></span>
* <span data-ttu-id="78e09-125">Маркеры обновления & доступа ServiceNow</span><span class="sxs-lookup"><span data-stu-id="78e09-125">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="78e09-126">Когда вы создаете билет ServiceNow из центра безопасности Microsoft 365, в ServiceNow отправляются следующие данные:</span><span class="sxs-lookup"><span data-stu-id="78e09-126">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="78e09-127">Идентификатор пользователя, инициирующий создание билета</span><span class="sxs-lookup"><span data-stu-id="78e09-127">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="78e09-128">Имя задачи</span><span class="sxs-lookup"><span data-stu-id="78e09-128">Task name</span></span>
* <span data-ttu-id="78e09-129">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="78e09-129">Task description</span></span>
* <span data-ttu-id="78e09-130">Priority</span><span class="sxs-lookup"><span data-stu-id="78e09-130">Priority</span></span>
* <span data-ttu-id="78e09-131">Дата выполнения</span><span class="sxs-lookup"><span data-stu-id="78e09-131">Due date</span></span>
* <span data-ttu-id="78e09-132">Источник рекомендаций (рекомендации по пользователю или рекомендация корпорации Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="78e09-132">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="78e09-133">Категория рекомендаций (устройства, данные, приложения, идентификация, инфраструктура)</span><span class="sxs-lookup"><span data-stu-id="78e09-133">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="78e09-134">Подключение центра безопасности Microsoft 365 к ServiceNow</span><span class="sxs-lookup"><span data-stu-id="78e09-134">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="78e09-135">Перейдите на домашнюю страницу центра безопасности Microsoft 365, чтобы просмотреть карточку подключения ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-135">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Использование ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="78e09-137">Выберите "подключиться к ServiceNow", чтобы перейти на страницу установки ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-137">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="78e09-138">Следуйте инструкциям для авторизации приложения Microsoft 365 Connector.</span><span class="sxs-lookup"><span data-stu-id="78e09-138">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="78e09-139">Прежде чем выполнять авторизацию подключения между центром безопасности Microsoft 365 и ServiceNow, убедитесь, что вы используете имя входа и пароль пользователя интеграции, которые вы создали в шагах установки.</span><span class="sxs-lookup"><span data-stu-id="78e09-139">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="78e09-140">Не используйте свои личные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="78e09-140">Do not use your personal credentials.</span></span>

<span data-ttu-id="78e09-141">После выполнения инструкций и авторизации подключения просмотрите состояние подключения на странице Подключение к центру безопасности Microsoft 365 и в интерфейсе приложения ServiceNow Microsoft 365 с помощью соединителя.</span><span class="sxs-lookup"><span data-stu-id="78e09-141">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="78e09-142">Теперь все готово для начала создания задач.</span><span class="sxs-lookup"><span data-stu-id="78e09-142">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="78e09-143">Создание задачи и общий доступ к ней в ServiceNow</span><span class="sxs-lookup"><span data-stu-id="78e09-143">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="78e09-144">После настройки интеграции Создайте задачи ServiceNow на основе определенных действий по улучшению оценки безопасности Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="78e09-144">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="78e09-145">Перейдите к любому действию улучшения в поле Оценка безопасности на портале Центра безопасности Microsoft 365 и выберите значок "общий доступ".</span><span class="sxs-lookup"><span data-stu-id="78e09-145">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="78e09-146">Один из вариантов раскрывающегося списка — ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-146">One of the dropdown options is ServiceNow.</span></span>

![Общий доступ к файлам ServiceNow в безопасной оценке](../../media/servicenow-share.png)

<span data-ttu-id="78e09-148">Создается задача, в которой можно задать приоритет и изменить имя, описание или срок выполнения.</span><span class="sxs-lookup"><span data-stu-id="78e09-148">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="78e09-149">После заполнения всех обязательных полей отправьте задачу в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-149">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="78e09-150">Эта задача отображается в ServiceNow как запрос на изменение безопасности и конфигурации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78e09-150">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="78e09-151">Отслеживание билетов</span><span class="sxs-lookup"><span data-stu-id="78e09-151">Track tickets</span></span>

<span data-ttu-id="78e09-152">После создания билетов управления изменениями и управления инцидентами, они отображаются в карточках на домашней странице центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78e09-152">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="78e09-153">Из этих карточек вы можете создать билет, просмотреть все билеты или управлять конфигурацией ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-153">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Билеты управления изменениями ServiceNow](../../media/change-management-375.png)  ![Билеты управления инцидентами ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="78e09-156">Чтобы повторно подготовить или управлять интеграцией ServiceNow в центре безопасности Майкрософт 365, выберите **Управление конфигурацией servicenow** на любой из карточек.</span><span class="sxs-lookup"><span data-stu-id="78e09-156">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="78e09-157">После этого удалите текущие подключения ServiceNow и настройте имена состояний билетов.</span><span class="sxs-lookup"><span data-stu-id="78e09-157">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="78e09-158">С билетами ServiceNow, которые отображаются в центре безопасности Майкрософт 365, ваши задачи находятся в том месте, где они могут отслеживаться и обрабатываться вместе с другими элементами панели мониторинга безопасности.</span><span class="sxs-lookup"><span data-stu-id="78e09-158">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="78e09-159">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="78e09-159">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="78e09-160">На первом шаге контрольного списка установки появляется сообщение об ошибке (создание OAuth)</span><span class="sxs-lookup"><span data-stu-id="78e09-160">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="78e09-161">**Сообщение об ошибке**: операция чтения для "oauth_entity" из области "x_mioms_m365ticket" была отклонена из-за политики доступа между областями таблицы</span><span class="sxs-lookup"><span data-stu-id="78e09-161">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="78e09-162">Приложение предполагает, что все администраторы в экземпляре ServiceNow могут создавать и читать сущности OAuth.</span><span class="sxs-lookup"><span data-stu-id="78e09-162">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="78e09-163">Эта ошибка может возникать из-за настроек в вашем экземпляре ServiceNow, которые ограничивают круг пользователей, которые могут создавать и читать сущности OAuth.</span><span class="sxs-lookup"><span data-stu-id="78e09-163">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="78e09-164">**ServiceNow рекомендует пользователям использовать стандартные функции.**</span><span class="sxs-lookup"><span data-stu-id="78e09-164">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="78e09-165">Присвойте параметру таблицы "Application реестров" значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="78e09-165">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="78e09-166">Label = регистрация приложений</span><span class="sxs-lookup"><span data-stu-id="78e09-166">Label = Application Registeries</span></span>
* <span data-ttu-id="78e09-167">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="78e09-167">Name = oauth_entity</span></span>
* <span data-ttu-id="78e09-168">Доступен из = все области применения приложений</span><span class="sxs-lookup"><span data-stu-id="78e09-168">Accessible from = All application scopes</span></span>
* <span data-ttu-id="78e09-169">Возможность чтения = установлен флажок</span><span class="sxs-lookup"><span data-stu-id="78e09-169">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="78e09-170">Проверка объекта OAuth, созданного для соединителя соответствия требованиям Microsoft 365 Security &</span><span class="sxs-lookup"><span data-stu-id="78e09-170">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="78e09-171">Перейдите в таблицу "реестры приложений" (**меню > реестр > приложений системы OAuth**) в ServiceNow и найдите созданную вами сущность OAuth, указав имя, которое ему назначено.</span><span class="sxs-lookup"><span data-stu-id="78e09-171">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="78e09-172">Вход в качестве пользователя интеграции</span><span class="sxs-lookup"><span data-stu-id="78e09-172">Logging in as the integration user</span></span>

<span data-ttu-id="78e09-173">Прежде чем выполнять авторизацию подключения между центром безопасности Microsoft 365 и ServiceNow, убедитесь, что вы используете имя входа и пароль пользователя интеграции, которые вы создали в шагах установки.</span><span class="sxs-lookup"><span data-stu-id="78e09-173">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="78e09-174">Не используйте свои личные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="78e09-174">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="78e09-175">Перейдите на страницу Авторизация в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-175">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="78e09-176">Если вы выполнили вход с использованием личных учетных данных, выберите ссылку **нет** в верхнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="78e09-176">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="78e09-177">Выполните вход в ServiceNow в качестве пользователя, созданного ранее в контрольном списке установки.</span><span class="sxs-lookup"><span data-stu-id="78e09-177">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="78e09-178">На странице ServiceNow выберите параметр **Разрешить** подключение к учетной записи ServiceNow с помощью соединителя безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="78e09-178">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="78e09-179">Следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="78e09-179">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="78e09-180">Проверка пользователя интеграции, созданного с помощью контрольного списка установки Microsoft 365 Security & Connector</span><span class="sxs-lookup"><span data-stu-id="78e09-180">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="78e09-181">Перейдите в таблицу пользователи **(меню > администрирование пользователей > пользователи**) в ServiceNow и найдите созданного пользователя по интеграции, указав его имя.</span><span class="sxs-lookup"><span data-stu-id="78e09-181">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="78e09-182">В вашей компании включен единый вход, который не позволяет подключаться к ServiceNow через центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="78e09-182">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="78e09-183">Если в вашей компании включен единый вход и вы получаете сообщение об ошибке или неудачном входе, выполните одно из двух решений.</span><span class="sxs-lookup"><span data-stu-id="78e09-183">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="78e09-184">Вход в ServiceNow в качестве пользователя интеграции</span><span class="sxs-lookup"><span data-stu-id="78e09-184">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="78e09-185">Вернитесь на страницу авторизации в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="78e09-185">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="78e09-186">Выберите ссылку **нет** в верхнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="78e09-186">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="78e09-187">Выполните вход в ServiceNow в качестве пользователя, созданного ранее в контрольном списке установки.</span><span class="sxs-lookup"><span data-stu-id="78e09-187">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="78e09-188">На странице ServiceNow выберите параметр **Разрешить** подключение к учетной записи ServiceNow с помощью соединителя безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="78e09-188">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="78e09-189">Следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="78e09-189">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="78e09-190">Создание пользователя администратора безопасности</span><span class="sxs-lookup"><span data-stu-id="78e09-190">Create a security admin user</span></span>

1. <span data-ttu-id="78e09-191">Создайте пользователя с правами администратора безопасности в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78e09-191">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="78e09-192">Пользователю должны быть назначены те же имя и адрес электронной почты, что и у пользователя интеграции, созданного на основе контрольного списка установки.</span><span class="sxs-lookup"><span data-stu-id="78e09-192">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="78e09-193">Вы можете удалить роль администратора безопасности после завершения входа и подключения.</span><span class="sxs-lookup"><span data-stu-id="78e09-193">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="78e09-194">Войдите в центр безопасности Microsoft 365 как этот пользователь и следуйте инструкциям по установке.</span><span class="sxs-lookup"><span data-stu-id="78e09-194">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="78e09-195">IP-фильтрация</span><span class="sxs-lookup"><span data-stu-id="78e09-195">IP filtering</span></span>

<span data-ttu-id="78e09-196">Если вы включили фильтрацию IP, возможно, потребуется явно разрешить IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="78e09-196">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="78e09-197">Сведения о том, как разрешить диапазоны IP-адресов в ServiceNow, можно найти в разделе [Управление доступом к IP-адресу](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) .</span><span class="sxs-lookup"><span data-stu-id="78e09-197">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="78e09-198">Список IP-адресов и их тегов в Azure можно найти в [общедоступном облаке](https://www.microsoft.com/en-us/download/details.aspx?id=56519) .</span><span class="sxs-lookup"><span data-stu-id="78e09-198">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="78e09-199">Установка завершена, но не видят билеты и не может поделиться</span><span class="sxs-lookup"><span data-stu-id="78e09-199">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="78e09-200">Если установка и настройка выполнены, но на домашней странице не видны карточки ServiceNow, которые не могут быть предоставлены в ServiceNow из Microsoft Secure Score, проверьте состояние страницы подготовки по адресу https://security.microsoft.com/ticketProvisioning.</span><span class="sxs-lookup"><span data-stu-id="78e09-200">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="78e09-201">Выберите **авторизовать** и вернитесь на домашнюю страницу.</span><span class="sxs-lookup"><span data-stu-id="78e09-201">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="78e09-202">Отображаются карточки.</span><span class="sxs-lookup"><span data-stu-id="78e09-202">The cards should appear.</span></span>

