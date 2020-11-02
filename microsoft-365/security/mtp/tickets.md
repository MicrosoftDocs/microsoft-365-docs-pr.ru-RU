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
ms.openlocfilehash: a2650efbac0966b84e6fbfd6ce78cb732f4933b3
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769657"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="08290-104">Интеграция билетов с ServiceNow в центр безопасности и соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="08290-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="08290-105">**Завершен период предварительной версии для соединителя ServiceNow**</span><span class="sxs-lookup"><span data-stu-id="08290-105">**The preview period for the ServiceNow connector is ending**</span></span><br>
><span data-ttu-id="08290-106">Эта возможность больше не будет доступна в конце ноября 2020.</span><span class="sxs-lookup"><span data-stu-id="08290-106">This capability will no longer available by the end of November 2020.</span></span> <span data-ttu-id="08290-107">Благодарим вас за отзыв и продолжение поддержки, пока мы определим дальнейшие действия.</span><span class="sxs-lookup"><span data-stu-id="08290-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="08290-108">ServiceNow — это популярная платформа облачных вычислений, которая помогает компаниям управлять цифровыми рабочими процессами для корпоративных операций.</span><span class="sxs-lookup"><span data-stu-id="08290-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="08290-109">На их платформах теперь есть рабочие процессы, рабочие процессы сотрудников и рабочие процессы клиентов.</span><span class="sxs-lookup"><span data-stu-id="08290-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="08290-110">Дополнительные сведения о ServiceNow</span><span class="sxs-lookup"><span data-stu-id="08290-110">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="08290-111">Корпорация Майкрософт поделилась с ServiceNow, чтобы облегчить ИТ-администраторам управлять своими билетами и задачами на обеих платформах.</span><span class="sxs-lookup"><span data-stu-id="08290-111">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="08290-112">[Центр безопасности microsoft 365](overview-security-center.md) и [центр соответствия требованиям корпорации майкрософт (Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) ) позволяют улучшить создание и отслеживание билетов в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="08290-112">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="08290-113">**Управление билетами ServiceNow в центре безопасности**</span><span class="sxs-lookup"><span data-stu-id="08290-113">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="08290-114">**Управление билетами ServiceNow в центре соответствия требованиям** (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="08290-114">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08290-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="08290-115">Prerequisites</span></span>

<span data-ttu-id="08290-116">Доступ к центру безопасности Microsoft 365 или центру соответствия требованиям и экземпляру ServiceNow с помощью следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="08290-116">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="08290-117">Кингстон или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="08290-117">Kingston or higher version</span></span>
* <span data-ttu-id="08290-118">Иметь учетные данные администратора HI</span><span class="sxs-lookup"><span data-stu-id="08290-118">Have admin HI credentials</span></span>
* <span data-ttu-id="08290-119">Иметь права администратора в экземпляре целевого поставщика</span><span class="sxs-lookup"><span data-stu-id="08290-119">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="08290-120">ServiceNow рекомендует пользователям хранить параметры по умолчанию в своем экземпляре ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="08290-120">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="08290-121">Настройка может привести к ошибкам при завершении работы контрольного списка установки и интеграции с центром безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08290-121">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="08290-122">обмен данными;</span><span class="sxs-lookup"><span data-stu-id="08290-122">Data exchange</span></span>

<span data-ttu-id="08290-123">При подключении центра безопасности Microsoft 365 или центра соответствия требованиям к ServiceNow Корпорация Майкрософт получает следующие дополнительные данные:</span><span class="sxs-lookup"><span data-stu-id="08290-123">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="08290-124">Имя экземпляра ServiceNow</span><span class="sxs-lookup"><span data-stu-id="08290-124">ServiceNow instance name</span></span>
* <span data-ttu-id="08290-125">ИД клиента ServiceNow</span><span class="sxs-lookup"><span data-stu-id="08290-125">ServiceNow client ID</span></span>
* <span data-ttu-id="08290-126">Секрет клиента ServiceNow</span><span class="sxs-lookup"><span data-stu-id="08290-126">ServiceNow client secret</span></span>
* <span data-ttu-id="08290-127">Маркеры обновления & доступа ServiceNow</span><span class="sxs-lookup"><span data-stu-id="08290-127">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="08290-128">Когда вы создаете билет ServiceNow из центра безопасности Microsoft 365 или центра соответствия требованиям, в ServiceNow передаются следующие данные:</span><span class="sxs-lookup"><span data-stu-id="08290-128">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="08290-129">Идентификатор пользователя, инициирующий создание билета</span><span class="sxs-lookup"><span data-stu-id="08290-129">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="08290-130">Имя задачи</span><span class="sxs-lookup"><span data-stu-id="08290-130">Task name</span></span>
* <span data-ttu-id="08290-131">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="08290-131">Task description</span></span>
* <span data-ttu-id="08290-132">Priority</span><span class="sxs-lookup"><span data-stu-id="08290-132">Priority</span></span>
* <span data-ttu-id="08290-133">Дата выполнения</span><span class="sxs-lookup"><span data-stu-id="08290-133">Due date</span></span>
* <span data-ttu-id="08290-134">Источник рекомендаций (рекомендации по пользователю или рекомендация корпорации Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="08290-134">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="08290-135">Категория рекомендаций (устройства, данные, приложения, идентификация, инфраструктура)</span><span class="sxs-lookup"><span data-stu-id="08290-135">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="08290-136">Подключение к ServiceNow</span><span class="sxs-lookup"><span data-stu-id="08290-136">Connect to ServiceNow</span></span>

<span data-ttu-id="08290-137">Чтобы узнать, как подключаться к ServiceNow, перейдите в раздел [Создание и отслеживание билетов servicenow в центре безопасности майкрософт 365](tickets-security-center.md) .</span><span class="sxs-lookup"><span data-stu-id="08290-137">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="08290-138">Скоро появится подключение из центра соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08290-138">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="08290-139">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="08290-139">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="08290-140">На первом шаге контрольного списка установки появляется сообщение об ошибке (создание OAuth)</span><span class="sxs-lookup"><span data-stu-id="08290-140">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="08290-141">**Сообщение об ошибке** : операция чтения для "oauth_entity" из области "x_mioms_m365ticket" была отклонена из-за политики доступа между областями таблицы</span><span class="sxs-lookup"><span data-stu-id="08290-141">**Error Message** : Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="08290-142">Приложение предполагает, что все администраторы в экземпляре ServiceNow могут создавать и читать сущности OAuth.</span><span class="sxs-lookup"><span data-stu-id="08290-142">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="08290-143">Эта ошибка может быть вызвана настройками в вашем экземпляре ServiceNow, которые ограничивают круг пользователей, которые могут создавать или читать сущности OAuth.</span><span class="sxs-lookup"><span data-stu-id="08290-143">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="08290-144">**ServiceNow рекомендует пользователям использовать стандартные функции.**</span><span class="sxs-lookup"><span data-stu-id="08290-144">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="08290-145">Присвойте параметру таблицы "Application реестров" значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="08290-145">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="08290-146">Label = регистрация приложений</span><span class="sxs-lookup"><span data-stu-id="08290-146">Label = Application Registeries</span></span>
* <span data-ttu-id="08290-147">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="08290-147">Name = oauth_entity</span></span>
* <span data-ttu-id="08290-148">Доступен из = все области применения приложений</span><span class="sxs-lookup"><span data-stu-id="08290-148">Accessible from = All application scopes</span></span>
* <span data-ttu-id="08290-149">Возможность чтения = установлен флажок</span><span class="sxs-lookup"><span data-stu-id="08290-149">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="08290-150">Проверка объекта OAuth, созданного для соединителя соответствия требованиям Microsoft 365 Security &</span><span class="sxs-lookup"><span data-stu-id="08290-150">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="08290-151">Перейдите в таблицу реестров приложений ( **меню > реестр > приложений системы OAuth** ) в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="08290-151">Go to application registries table ( **Menu > System OAuth > Application Registry** ) in ServiceNow.</span></span> <span data-ttu-id="08290-152">Найдите созданную вами сущность OAuth с назначенным ему именем.</span><span class="sxs-lookup"><span data-stu-id="08290-152">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="08290-153">Вход в качестве пользователя интеграции</span><span class="sxs-lookup"><span data-stu-id="08290-153">Signing in as the integration user</span></span>

<span data-ttu-id="08290-154">Прежде чем выполнять авторизацию подключения между центром безопасности Microsoft 365 и ServiceNow, убедитесь, что вы используете вход пользователя и пароль, которые вы создали в шагах установки.</span><span class="sxs-lookup"><span data-stu-id="08290-154">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="08290-155">Не используйте свои личные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="08290-155">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="08290-156">Перейдите на страницу Авторизация в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="08290-156">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="08290-157">Если вы выполнили вход с использованием личных учетных данных, выберите ссылку **нет** в верхнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="08290-157">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="08290-158">Войдите в ServiceNow как пользователь интеграции, созданный ранее из контрольного списка установки.</span><span class="sxs-lookup"><span data-stu-id="08290-158">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="08290-159">На странице ServiceNow выберите параметр **Разрешить** подключение к учетной записи ServiceNow с помощью соединителя безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="08290-159">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="08290-160">Следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="08290-160">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="08290-161">Проверка пользователя интеграции, созданного с помощью контрольного списка установки Microsoft 365 Security & Connector</span><span class="sxs-lookup"><span data-stu-id="08290-161">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="08290-162">Перейдите в таблицу пользователи **(меню > администрирование пользователей > пользователи** ) в ServiceNow и найдите созданного пользователя по интеграции, указав его имя.</span><span class="sxs-lookup"><span data-stu-id="08290-162">Go to Users Table **(Menu > User Administration > Users** ) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="08290-163">В вашей компании включен единый вход, который не позволяет подключаться к ServiceNow через центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="08290-163">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="08290-164">Если в вашей компании включен единый вход, а вы получили сообщение об ошибке или войти не удалось, выполните одно из двух решений.</span><span class="sxs-lookup"><span data-stu-id="08290-164">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="08290-165">Вход в ServiceNow в качестве пользователя интеграции</span><span class="sxs-lookup"><span data-stu-id="08290-165">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="08290-166">Вернитесь на страницу авторизации в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="08290-166">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="08290-167">Выберите ссылку **нет** в верхнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="08290-167">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="08290-168">Войдите в ServiceNow как пользователь интеграции, созданный ранее из контрольного списка установки.</span><span class="sxs-lookup"><span data-stu-id="08290-168">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="08290-169">На странице ServiceNow выберите параметр **Разрешить** подключение к учетной записи ServiceNow с помощью соединителя безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="08290-169">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="08290-170">Следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="08290-170">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="08290-171">Создание пользователя администратора безопасности</span><span class="sxs-lookup"><span data-stu-id="08290-171">Create a security admin user</span></span>

1. <span data-ttu-id="08290-172">Создайте пользователя с правами администратора безопасности в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="08290-172">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="08290-173">Пользователю должны быть назначены те же имя и адрес электронной почты, что и у пользователя интеграции, созданного на основе контрольного списка установки.</span><span class="sxs-lookup"><span data-stu-id="08290-173">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="08290-174">Вы можете удалить роль администратора безопасности после входа в систему и подключения.</span><span class="sxs-lookup"><span data-stu-id="08290-174">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="08290-175">Войдите в центр безопасности Microsoft 365 как этот пользователь и следуйте инструкциям по установке.</span><span class="sxs-lookup"><span data-stu-id="08290-175">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="08290-176">IP-фильтрация</span><span class="sxs-lookup"><span data-stu-id="08290-176">IP filtering</span></span>

<span data-ttu-id="08290-177">Если вы включили фильтрацию IP, возможно, потребуется явно разрешить IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="08290-177">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="08290-178">Сведения о том, как разрешить диапазоны IP-адресов в ServiceNow, можно найти в разделе [Управление доступом к IP-адресу](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) .</span><span class="sxs-lookup"><span data-stu-id="08290-178">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="08290-179">Список IP-адресов и их тегов в Azure можно найти в [общедоступном облаке](https://www.microsoft.com/en-us/download/details.aspx?id=56519) .</span><span class="sxs-lookup"><span data-stu-id="08290-179">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="08290-180">Установка завершена, но не видят билеты и не может поделиться</span><span class="sxs-lookup"><span data-stu-id="08290-180">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="08290-181">Если установка и настройка выполнены, но на домашней странице не видны карточки ServiceNow, которые не могут быть предоставлены в ServiceNow из Microsoft Secure Score, проверьте состояние страницы подготовки по адресу https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="08290-181">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="08290-182">Выберите **авторизовать** и вернитесь на домашнюю страницу.</span><span class="sxs-lookup"><span data-stu-id="08290-182">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="08290-183">Отображаются карточки.</span><span class="sxs-lookup"><span data-stu-id="08290-183">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="08290-184">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="08290-184">Resources</span></span>

- [<span data-ttu-id="08290-185">Управление билетами ServiceNow в центре безопасности</span><span class="sxs-lookup"><span data-stu-id="08290-185">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)
