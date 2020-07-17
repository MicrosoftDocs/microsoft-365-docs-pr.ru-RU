---
title: Интеграция билетов с ServiceNow в центр безопасности и соответствия требованиям Microsoft 365
description: Узнайте, как создавать и отслеживать билеты в ServiceNow с помощью центра обеспечения безопасности Microsoft 365 и центра соответствия требованиям.
keywords: безопасность, Microsoft 365, M365, соответствие требованиям, центр обеспечения безопасности, ServiceNow, билеты, задачи, SNOW, подключение
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
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086671"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="86705-104">Интеграция билетов с ServiceNow в центр безопасности и соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="86705-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="86705-105">ServiceNow — это популярная платформа облачных вычислений, которая помогает компаниям управлять цифровыми рабочими процессами для корпоративных операций.</span><span class="sxs-lookup"><span data-stu-id="86705-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="86705-106">На их платформах теперь есть рабочие процессы, рабочие процессы сотрудников и рабочие процессы клиентов.</span><span class="sxs-lookup"><span data-stu-id="86705-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="86705-107">Дополнительные сведения о ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86705-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="86705-108">Корпорация Майкрософт поделилась с ServiceNow, чтобы облегчить ИТ-администраторам управлять своими билетами и задачами на обеих платформах.</span><span class="sxs-lookup"><span data-stu-id="86705-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="86705-109">[Центр безопасности microsoft 365](overview-security-center.md) и [центр соответствия требованиям корпорации майкрософт (Microsoft 365](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) ) позволяют улучшить создание и отслеживание билетов в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86705-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="86705-110">**Управление билетами ServiceNow в центре безопасности**</span><span class="sxs-lookup"><span data-stu-id="86705-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="86705-111">**Управление билетами ServiceNow в центре соответствия требованиям** (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="86705-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86705-112">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="86705-112">Prerequisites</span></span>

<span data-ttu-id="86705-113">Доступ к центру безопасности Microsoft 365 или центру соответствия требованиям и экземпляру ServiceNow с помощью следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="86705-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="86705-114">Кингстон или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="86705-114">Kingston or higher version</span></span>
* <span data-ttu-id="86705-115">Иметь учетные данные администратора HI</span><span class="sxs-lookup"><span data-stu-id="86705-115">Have admin HI credentials</span></span>
* <span data-ttu-id="86705-116">Иметь права администратора в экземпляре целевого поставщика</span><span class="sxs-lookup"><span data-stu-id="86705-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="86705-117">ServiceNow рекомендует пользователям хранить параметры по умолчанию в своем экземпляре ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86705-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="86705-118">Настройка может привести к ошибкам при завершении работы контрольного списка установки и интеграции с центром безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86705-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="86705-119">обмен данными;</span><span class="sxs-lookup"><span data-stu-id="86705-119">Data exchange</span></span>

<span data-ttu-id="86705-120">При подключении центра безопасности Microsoft 365 или центра соответствия требованиям к ServiceNow Корпорация Майкрософт получает следующие дополнительные данные:</span><span class="sxs-lookup"><span data-stu-id="86705-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="86705-121">Имя экземпляра ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86705-121">ServiceNow instance name</span></span>
* <span data-ttu-id="86705-122">ИД клиента ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86705-122">ServiceNow client ID</span></span>
* <span data-ttu-id="86705-123">Секрет клиента ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86705-123">ServiceNow client secret</span></span>
* <span data-ttu-id="86705-124">Маркеры обновления & доступа ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86705-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="86705-125">Когда вы создаете билет ServiceNow из центра безопасности Microsoft 365 или центра соответствия требованиям, в ServiceNow передаются следующие данные:</span><span class="sxs-lookup"><span data-stu-id="86705-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="86705-126">Идентификатор пользователя, инициирующий создание билета</span><span class="sxs-lookup"><span data-stu-id="86705-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="86705-127">Имя задачи</span><span class="sxs-lookup"><span data-stu-id="86705-127">Task name</span></span>
* <span data-ttu-id="86705-128">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="86705-128">Task description</span></span>
* <span data-ttu-id="86705-129">Priority</span><span class="sxs-lookup"><span data-stu-id="86705-129">Priority</span></span>
* <span data-ttu-id="86705-130">Дата выполнения</span><span class="sxs-lookup"><span data-stu-id="86705-130">Due date</span></span>
* <span data-ttu-id="86705-131">Источник рекомендаций (рекомендации по пользователю или рекомендация корпорации Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="86705-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="86705-132">Категория рекомендаций (устройства, данные, приложения, идентификация, инфраструктура)</span><span class="sxs-lookup"><span data-stu-id="86705-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="86705-133">Подключение к ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86705-133">Connect to ServiceNow</span></span>

<span data-ttu-id="86705-134">Чтобы узнать, как подключаться к ServiceNow, перейдите в раздел [Создание и отслеживание билетов servicenow в центре безопасности майкрософт 365](tickets-security-center.md) .</span><span class="sxs-lookup"><span data-stu-id="86705-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="86705-135">Скоро появится подключение из центра соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86705-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="86705-136">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="86705-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="86705-137">На первом шаге контрольного списка установки появляется сообщение об ошибке (создание OAuth)</span><span class="sxs-lookup"><span data-stu-id="86705-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="86705-138">**Сообщение об ошибке**: операция чтения для "oauth_entity" из области "x_mioms_m365ticket" была отклонена из-за политики доступа между областями таблицы</span><span class="sxs-lookup"><span data-stu-id="86705-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="86705-139">Приложение предполагает, что все администраторы в экземпляре ServiceNow могут создавать и читать сущности OAuth.</span><span class="sxs-lookup"><span data-stu-id="86705-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="86705-140">Эта ошибка может возникать из-за настроек в вашем экземпляре ServiceNow, которые ограничивают круг пользователей, которые могут создавать и читать сущности OAuth.</span><span class="sxs-lookup"><span data-stu-id="86705-140">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="86705-141">**ServiceNow рекомендует пользователям использовать стандартные функции.**</span><span class="sxs-lookup"><span data-stu-id="86705-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="86705-142">Присвойте параметру таблицы "Application реестров" значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="86705-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="86705-143">Label = регистрация приложений</span><span class="sxs-lookup"><span data-stu-id="86705-143">Label = Application Registeries</span></span>
* <span data-ttu-id="86705-144">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="86705-144">Name = oauth_entity</span></span>
* <span data-ttu-id="86705-145">Доступен из = все области применения приложений</span><span class="sxs-lookup"><span data-stu-id="86705-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="86705-146">Возможность чтения = установлен флажок</span><span class="sxs-lookup"><span data-stu-id="86705-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="86705-147">Проверка объекта OAuth, созданного для соединителя соответствия требованиям Microsoft 365 Security &</span><span class="sxs-lookup"><span data-stu-id="86705-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="86705-148">Перейдите в таблицу "реестры приложений" (**меню > реестр > приложений системы OAuth**) в ServiceNow и найдите созданную вами сущность OAuth, указав имя, которое ему назначено.</span><span class="sxs-lookup"><span data-stu-id="86705-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="86705-149">Вход в качестве пользователя интеграции</span><span class="sxs-lookup"><span data-stu-id="86705-149">Logging in as the integration user</span></span>

<span data-ttu-id="86705-150">Прежде чем выполнять авторизацию подключения между центром безопасности Microsoft 365 и ServiceNow, убедитесь, что вы используете имя входа и пароль пользователя интеграции, которые вы создали в шагах установки.</span><span class="sxs-lookup"><span data-stu-id="86705-150">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="86705-151">Не используйте свои личные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="86705-151">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="86705-152">Перейдите на страницу Авторизация в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86705-152">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="86705-153">Если вы выполнили вход с использованием личных учетных данных, выберите ссылку **нет** в верхнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="86705-153">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="86705-154">Выполните вход в ServiceNow в качестве пользователя, созданного ранее в контрольном списке установки.</span><span class="sxs-lookup"><span data-stu-id="86705-154">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="86705-155">На странице ServiceNow выберите параметр **Разрешить** подключение к учетной записи ServiceNow с помощью соединителя безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="86705-155">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="86705-156">Следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="86705-156">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="86705-157">Проверка пользователя интеграции, созданного с помощью контрольного списка установки Microsoft 365 Security & Connector</span><span class="sxs-lookup"><span data-stu-id="86705-157">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="86705-158">Перейдите в таблицу пользователи **(меню > администрирование пользователей > пользователи**) в ServiceNow и найдите созданного пользователя по интеграции, указав его имя.</span><span class="sxs-lookup"><span data-stu-id="86705-158">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="86705-159">В вашей компании включен единый вход, который не позволяет подключаться к ServiceNow через центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="86705-159">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="86705-160">Если в вашей компании включен единый вход и вы получаете сообщение об ошибке или неудачном входе, выполните одно из двух решений.</span><span class="sxs-lookup"><span data-stu-id="86705-160">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="86705-161">Вход в ServiceNow в качестве пользователя интеграции</span><span class="sxs-lookup"><span data-stu-id="86705-161">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="86705-162">Вернитесь на страницу авторизации в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86705-162">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="86705-163">Выберите ссылку **нет** в верхнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="86705-163">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="86705-164">Выполните вход в ServiceNow в качестве пользователя, созданного ранее в контрольном списке установки.</span><span class="sxs-lookup"><span data-stu-id="86705-164">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="86705-165">На странице ServiceNow выберите параметр **Разрешить** подключение к учетной записи ServiceNow с помощью соединителя безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="86705-165">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="86705-166">Следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="86705-166">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="86705-167">Создание пользователя администратора безопасности</span><span class="sxs-lookup"><span data-stu-id="86705-167">Create a security admin user</span></span>

1. <span data-ttu-id="86705-168">Создайте пользователя с правами администратора безопасности в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="86705-168">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="86705-169">Пользователю должны быть назначены те же имя и адрес электронной почты, что и у пользователя интеграции, созданного на основе контрольного списка установки.</span><span class="sxs-lookup"><span data-stu-id="86705-169">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="86705-170">Вы можете удалить роль администратора безопасности после завершения входа и подключения.</span><span class="sxs-lookup"><span data-stu-id="86705-170">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="86705-171">Войдите в центр безопасности Microsoft 365 как этот пользователь и следуйте инструкциям по установке.</span><span class="sxs-lookup"><span data-stu-id="86705-171">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="86705-172">IP-фильтрация</span><span class="sxs-lookup"><span data-stu-id="86705-172">IP filtering</span></span>

<span data-ttu-id="86705-173">Если вы включили фильтрацию IP, возможно, потребуется явно разрешить IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="86705-173">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="86705-174">Сведения о том, как разрешить диапазоны IP-адресов в ServiceNow, можно найти в разделе [Управление доступом к IP-адресу](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) .</span><span class="sxs-lookup"><span data-stu-id="86705-174">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="86705-175">Список IP-адресов и их тегов в Azure можно найти в [общедоступном облаке](https://www.microsoft.com/en-us/download/details.aspx?id=56519) .</span><span class="sxs-lookup"><span data-stu-id="86705-175">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="86705-176">Установка завершена, но не видят билеты и не может поделиться</span><span class="sxs-lookup"><span data-stu-id="86705-176">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="86705-177">Если установка и настройка выполнены, но на домашней странице не видны карточки ServiceNow, которые не могут быть предоставлены в ServiceNow из Microsoft Secure Score, проверьте состояние страницы подготовки по адресу https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="86705-177">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="86705-178">Выберите **авторизовать** и вернитесь на домашнюю страницу.</span><span class="sxs-lookup"><span data-stu-id="86705-178">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="86705-179">Отображаются карточки.</span><span class="sxs-lookup"><span data-stu-id="86705-179">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="86705-180">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="86705-180">Resources</span></span>

- [<span data-ttu-id="86705-181">Управление билетами ServiceNow в центре безопасности</span><span class="sxs-lookup"><span data-stu-id="86705-181">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)