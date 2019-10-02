---
title: Создание и отслеживание билетов с помощью ServiceNow
description: Microsoft 365 Security Center обеспечивает возможность самостоятельно создавать и отслеживать билеты в ServiceNow. Это позволяет администраторам безопасности отправлять рекомендацию по оценке безопасности непосредственно в ServiceNow и создавать билет.
keywords: безопасность, Microsoft 365, M365, Оценка безопасности, центр безопасности, ServiceNow, билеты, задачи
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350338"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="d97db-105">Управление билетами с помощью ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d97db-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="d97db-106">Microsoft 365 Security Center обеспечивает возможность самостоятельно создавать и отслеживать билеты в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d97db-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="d97db-107">Это позволяет администраторам безопасности отправлять действия по улучшению [оценки безопасности Майкрософт](microsoft-secure-score.md) непосредственно в ServiceNow и создавать билет.</span><span class="sxs-lookup"><span data-stu-id="d97db-107">This allows security administrators to send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="d97db-108">Могут быть созданы как управление инцидентами, так и билеты управления изменениями.</span><span class="sxs-lookup"><span data-stu-id="d97db-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d97db-109">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="d97db-109">Prerequisites</span></span>

<span data-ttu-id="d97db-110">Получить доступ к центру безопасности Microsoft 365 и экземпляру ServiceNow с помощью следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="d97db-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="d97db-111">Кингстон или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="d97db-111">Kingston or higher version</span></span>
* <span data-ttu-id="d97db-112">Иметь учетные данные администратора HI</span><span class="sxs-lookup"><span data-stu-id="d97db-112">Have admin HI credentials</span></span>
* <span data-ttu-id="d97db-113">Иметь права администратора в экземпляре целевого поставщика</span><span class="sxs-lookup"><span data-stu-id="d97db-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="d97db-114">ServiceNow рекомендует пользователям оставить параметры Box (по умолчанию) в своем экземпляре ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d97db-114">ServiceNow recommends users keep out of the box settings (default) in your ServiceNow instance.</span></span>  <span data-ttu-id="d97db-115">Настройка может привести к ошибкам при выполнении контрольного списка установки и интеграции с центром безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d97db-115">Having customizations could cause errors in completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="d97db-116">обмен данными;</span><span class="sxs-lookup"><span data-stu-id="d97db-116">Data exchange</span></span>

<span data-ttu-id="d97db-117">При подключении центра безопасности Microsoft 365 к ServiceNow Корпорация Майкрософт будет получать следующие дополнительные данные:</span><span class="sxs-lookup"><span data-stu-id="d97db-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft will be receiving the following additional data:</span></span>

* <span data-ttu-id="d97db-118">Имя экземпляра ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d97db-118">ServiceNow instance name</span></span>
* <span data-ttu-id="d97db-119">ИД клиента ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d97db-119">ServiceNow client ID</span></span>
* <span data-ttu-id="d97db-120">Секрет клиента ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d97db-120">ServiceNow client secret</span></span>
* <span data-ttu-id="d97db-121">Маркеры обновления & доступа ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d97db-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="d97db-122">Когда вы создаете билет ServiceNow из центра безопасности Microsoft 365, в ServiceNow отправляются следующие данные:</span><span class="sxs-lookup"><span data-stu-id="d97db-122">When you create a ServiceNow ticket from the Microsoft 365 security center the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="d97db-123">Идентификатор пользователя, инициирующий создание билета</span><span class="sxs-lookup"><span data-stu-id="d97db-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="d97db-124">Имя задачи</span><span class="sxs-lookup"><span data-stu-id="d97db-124">Task name</span></span>
* <span data-ttu-id="d97db-125">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="d97db-125">Task description</span></span>
* <span data-ttu-id="d97db-126">Priority</span><span class="sxs-lookup"><span data-stu-id="d97db-126">Priority</span></span>
* <span data-ttu-id="d97db-127">Дата выполнения</span><span class="sxs-lookup"><span data-stu-id="d97db-127">Due date</span></span>
* <span data-ttu-id="d97db-128">Источник рекомендаций (рекомендации по пользователю или рекомендация корпорации Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d97db-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="d97db-129">Категория рекомендаций (устройства, данные, приложения, идентификация, инфраструктура)</span><span class="sxs-lookup"><span data-stu-id="d97db-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="d97db-130">Подключение центра безопасности Microsoft 365 к ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d97db-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="d97db-131">Перейдите на домашнюю страницу центра безопасности Microsoft 365, на которой вы увидите карточку с запросом на использование ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d97db-131">Navigate to the Microsoft 365 security center home page, where you will see a card asking if you use ServiceNow.</span></span>

![Использование ServiceNow](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="d97db-133">После этого вы будете отправлены на страницу Настройка ServiceNow, на которой вы будете следовать инструкциям для авторизации приложения Microsoft 365 Connector.</span><span class="sxs-lookup"><span data-stu-id="d97db-133">From there you will be sent to the ServiceNow set up page where you'll follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

<span data-ttu-id="d97db-134">При авторизации подключения между центром безопасности Microsoft 365 и ServiceNow убедитесь, что вы используете имя входа и пароль пользователя интеграции, которые вы создали в шагах установки, а не в личных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d97db-134">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

<span data-ttu-id="d97db-135">После выполнения инструкций и авторизации подключения вы можете просмотреть состояние подключения на странице Подключение к центру безопасности Microsoft 365 и в интерфейсе приложения ServiceNow Microsoft 365 с помощью соединителя.</span><span class="sxs-lookup"><span data-stu-id="d97db-135">After following the directions and authorizing the connection, you can view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="d97db-136">Теперь все готово для начала создания задач.</span><span class="sxs-lookup"><span data-stu-id="d97db-136">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="d97db-137">Создание задачи и общий доступ к ней в ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d97db-137">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="d97db-138">После настройки интеграции можно создавать задачи ServiceNow на основе определенных действий по улучшению оценки безопасности Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d97db-138">Once the integration is set up, you can create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="d97db-139">Перейдите к любому действию улучшения в поле Оценка безопасности на портале Центра безопасности Microsoft 365 и выберите значок "общий доступ".</span><span class="sxs-lookup"><span data-stu-id="d97db-139">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="d97db-140">Один из вариантов раскрывающегося списка — ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d97db-140">One of the dropdown options is ServiceNow.</span></span>

![Общий доступ к файлам ServiceNow в безопасной оценке](../images/servicenow-share.png)

<span data-ttu-id="d97db-142">После этого будет создана задача, в которой можно задать приоритет и изменить имя, описание или срок выполнения.</span><span class="sxs-lookup"><span data-stu-id="d97db-142">A task will then be generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="d97db-143">После заполнения всех обязательных полей можно отправить задачу в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d97db-143">Once all the required fields are filled in, you can send the task to ServiceNow.</span></span>

<span data-ttu-id="d97db-144">Эта задача будет отображаться в ServiceNow как запрос на изменение параметров безопасности и изменений в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d97db-144">The task will be visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="d97db-145">Отслеживание билетов</span><span class="sxs-lookup"><span data-stu-id="d97db-145">Track tickets</span></span>

<span data-ttu-id="d97db-146">После создания билетов управления изменениями и управления инцидентами, они будут отображаться на карточках на домашней странице центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d97db-146">Once ServiceNow change management and incident management tickets have been created, they will be displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="d97db-147">Из этих карточек вы можете создать билет, просмотреть все билеты или управлять конфигурацией ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d97db-147">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Билеты управления изменениями ServiceNow](../images/change-management-375.png)  ![Билеты управления инцидентами ServiceNow](../images/incident-management-375.png)

<span data-ttu-id="d97db-150">Чтобы повторно подготовить или управлять интеграцией ServiceNow в центре безопасности Майкрософт 365, выберите **Управление конфигурацией servicenow** на любой из карточек.</span><span class="sxs-lookup"><span data-stu-id="d97db-150">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="d97db-151">После этого вы можете удалить текущие подключения ServiceNow и настроить имена состояний билетов.</span><span class="sxs-lookup"><span data-stu-id="d97db-151">From there you can  remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="d97db-152">С помощью билетов ServiceNow, отображаемых в центре безопасности Майкрософт 365, ваши задачи будут действовать в том месте, где они могут отслеживаться и обрабатываться вместе с другими элементами панели мониторинга безопасности.</span><span class="sxs-lookup"><span data-stu-id="d97db-152">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks will live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d97db-153">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="d97db-153">Frequently asked questions</span></span>

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="d97db-154">При получении сообщения об ошибке на первом шаге контрольного списка установки (OAuth "создание")</span><span class="sxs-lookup"><span data-stu-id="d97db-154">I am receiving an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="d97db-155">**Сообщение об ошибке**: операция чтения для "oauth_entity" из области "x_mioms_m365ticket" была отклонена из-за политики доступа между областями таблицы</span><span class="sxs-lookup"><span data-stu-id="d97db-155">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="d97db-156">Приложение предполагает, что все администраторы в экземпляре ServiceNow могут создавать и читать сущности OAuth.</span><span class="sxs-lookup"><span data-stu-id="d97db-156">Our app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="d97db-157">Эта ошибка может возникать из-за настроек в вашем экземпляре ServiceNow, которые ограничивают круг пользователей, которые могут создавать и читать сущности OAuth.</span><span class="sxs-lookup"><span data-stu-id="d97db-157">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span> <span data-ttu-id="d97db-158">ServiceNow рекомендует пользователям использовать функции Box (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d97db-158">ServiceNow recommends users keep out of the box functionality (default).</span></span>

<span data-ttu-id="d97db-159">Присвойте параметру таблицы "Application реестров" значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="d97db-159">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="d97db-160">Label = регистрация приложений</span><span class="sxs-lookup"><span data-stu-id="d97db-160">Label = Application Registeries</span></span>
* <span data-ttu-id="d97db-161">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="d97db-161">Name = oauth_entity</span></span>
* <span data-ttu-id="d97db-162">Доступен из = все области применения приложений</span><span class="sxs-lookup"><span data-stu-id="d97db-162">Accessible from = All application scopes</span></span>
* <span data-ttu-id="d97db-163">Возможность чтения = установлен флажок</span><span class="sxs-lookup"><span data-stu-id="d97db-163">Can read = check box selected</span></span>

<span data-ttu-id="d97db-164">**ServiceNow рекомендует пользователям использовать функции Box (по умолчанию).**</span><span class="sxs-lookup"><span data-stu-id="d97db-164">**ServiceNow recommends users keep out of the box functionality (default).**</span></span>

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="d97db-165">Как проверить сущность OAuth, созданную для соединителя соответствия требованиям Microsoft 365 Security &?</span><span class="sxs-lookup"><span data-stu-id="d97db-165">How do I validate the OAuth entity created for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="d97db-166">Перейдите в таблицу реестры приложений (меню > реестр > приложений системы OAuth) в ServiceNow и найдите созданную вами сущность OAuth (назначенное имя).</span><span class="sxs-lookup"><span data-stu-id="d97db-166">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="d97db-167">Как проверить пользователя интеграции, созданного в шаге 2 контрольного списка установки для Microsoft 365 Security & Connector?</span><span class="sxs-lookup"><span data-stu-id="d97db-167">How do I validate the Integration User created in step two of installation checklist for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="d97db-168">Перейдите в таблицу пользователи (меню > администрирование пользователей > пользователи) в ServiceNow и найдите созданного пользователя по интеграции (присвоенное ему имя).</span><span class="sxs-lookup"><span data-stu-id="d97db-168">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="d97db-169">При авторизации подключения между центром безопасности Microsoft 365 и ServiceNow убедитесь, что вы используете имя входа и пароль пользователя интеграции, которые вы создали в шагах установки, а не в личных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d97db-169">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a><span data-ttu-id="d97db-170">Установка и настройка шагов завершены, но на домашней странице не отображаются карточки ServiceNow и значок "общий доступ" не отображается в Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="d97db-170">I have completed the installation and set up steps, but I am unable to see the ServiceNow cards on the home page and cannot see the Share icon in Microsoft Secure Score</span></span>

<span data-ttu-id="d97db-171">Проверьте состояние страницы подготовки, перейдя по адресу https://security.microsoft.com/ticketProvisioning.</span><span class="sxs-lookup"><span data-stu-id="d97db-171">Check the status of the provisioning page by going to https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="d97db-172">Нажмите кнопку **сохранить** и вернитесь на домашнюю страницу.</span><span class="sxs-lookup"><span data-stu-id="d97db-172">Select **Save** and return to the home page.</span></span> <span data-ttu-id="d97db-173">Отображаются карточки.</span><span class="sxs-lookup"><span data-stu-id="d97db-173">The cards should appear.</span></span>
