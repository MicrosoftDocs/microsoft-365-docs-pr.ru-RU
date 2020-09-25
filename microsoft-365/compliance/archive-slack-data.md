---
title: Настройка соединителя для архивации данных резервного времени в Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Администраторы могут настроить соединитель для импорта и архивирования данных из резервного Глобанет в Microsoft 365. Этот соединитель данных позволяет архивировать данные из сторонних источников данных в Microsoft 365, чтобы можно было использовать такие функции обеспечения соответствия, как судебное хранение, поиск контента и политики хранения, для управления данными сторонних организаций.
ms.openlocfilehash: 7c796c16b5a4b305c5d4b5259337ca28d9bfde9a
ms.sourcegitcommit: 96b4593becc9450af136c528844e858c6e88b5a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269461"
---
# <a name="set-up-a-connector-to-archive-slack-data"></a><span data-ttu-id="7cbfc-104">Настройка соединителя для архивации данных резервного времени</span><span class="sxs-lookup"><span data-stu-id="7cbfc-104">Set up a connector to archive Slack data</span></span>

<span data-ttu-id="7cbfc-105">Используйте соединитель Глобанет в центре соответствия требованиям Microsoft 365, чтобы импортировать и архивировать сторонние данные из социальных сетей, обмена мгновенными сообщениями и платформы совместной работы с документами в почтовые ящики в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive third-party data from social media, instant messaging, and document collaboration platforms to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="7cbfc-106">Глобанет предоставляет соединитель временной резерв, настроенный для сбора элементов из стороннего источника данных (на регулярной основе), а затем импортируйте эти элементы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-106">Globanet provides a Slack connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="7cbfc-107">Временной резерв извлекает сообщения и файлы из API резервного времени и преобразует их в формат сообщений электронной почты, а затем импортирует их в почтовые ящики пользователей.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-107">Slack pulls messages and files from the Slack API and converts them to an email message format and then imports the item to user mailboxes.</span></span>

<span data-ttu-id="7cbfc-108">После хранения резервных данных в почтовых ящиках пользователей можно применять функции обеспечения соответствия требованиям Microsoft 365, такие как хранение для судебного разбирательства, обнаружение электронных данных, политики хранения и метки хранения, а также соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-108">After Slack data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="7cbfc-109">Использование соединителя временного резерва для импорта и архивирования данных в Microsoft 365 может помочь организации соответствовать государственным и нормативным политикам.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-109">Using a Slack connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-slack-data"></a><span data-ttu-id="7cbfc-110">Обзор резервных копий данных резервных копий</span><span class="sxs-lookup"><span data-stu-id="7cbfc-110">Overview of archiving Slack data</span></span>

<span data-ttu-id="7cbfc-111">В следующем обзоре описывается процесс использования соединителя для архивации данных резервного времени в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-111">The following overview explains the process of using a connector to archive the Slack information in Microsoft 365.</span></span>

![Рабочий процесс архивации](../media/SlackConnectorWorkflow.png)

1. <span data-ttu-id="7cbfc-113">Организация работает с резервным копированием и настройкой резервного сайта.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-113">Your organization works with Slack to set up and configure a Slack site.</span></span>

2. <span data-ttu-id="7cbfc-114">Каждые 24 часа сообщения чата копируются на сайт Глобанет Merge1.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-114">Once every 24 hours, chat messages from Slack are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="7cbfc-115">Соединитель также Преобразовывает содержимое сообщения чата в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-115">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="7cbfc-116">Временной интервал, который вы создаете в центре соответствия требованиям Microsoft 365, подключается к сайту Глобанет Merge1 каждый день и передает сообщения чата в безопасное место хранения Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-116">The Slack connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the chat messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="7cbfc-117">Соединитель импортирует преобразованные элементы сообщений чата в почтовые ящики определенных пользователей, используя значение свойства *электронной почты* и автоматическое сопоставление пользователей, как описано в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-117">The connector imports the converted chat message items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="7cbfc-118">В почтовых ящиках пользователей создается новая подпапка в папке "Входящие" с именем **временной резерв** , а элементы сообщений чата будут импортированы в эту папку.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-118">A new subfolder in the Inbox folder named **Slack** is created in the user mailboxes, and the chat message items will be imported to that folder.</span></span> <span data-ttu-id="7cbfc-119">Соединитель выполняет это, используя значение свойства *Email* .</span><span class="sxs-lookup"><span data-stu-id="7cbfc-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="7cbfc-120">Каждое сообщение разговора содержит это свойство, которое заполняется адресом электронной почты каждого участника сообщения разговора.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-120">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7cbfc-121">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="7cbfc-121">Before you begin</span></span>

- <span data-ttu-id="7cbfc-122">Создайте учетную запись Глобанет Merge1 для соединителей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="7cbfc-123">Для этого обратитесь в [службу поддержки клиентов глобанет](https://globanet.com/ms-connectors-contact).</span><span class="sxs-lookup"><span data-stu-id="7cbfc-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="7cbfc-124">Вы должны войти в эту учетную запись, когда вы создадите соединитель на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="7cbfc-125">Получите имя пользователя и пароль для учетной записи, имеющей резервную корпоративную организацию.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-125">Obtain the username and password for your organization's Slack enterprise account.</span></span> <span data-ttu-id="7cbfc-126">При настройке резервного времени необходимо войти в эту учетную запись на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-126">You'll need to sign into this account in Step 2 when you configure Slack.</span></span>

- <span data-ttu-id="7cbfc-127">Пользователь, который создает соединитель временного резерва в действии 1 (и завершает его на шаге 3), должен быть назначен роли импорта для импорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-127">The user who creates the Slack connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="7cbfc-128">Эта роль необходима для добавления соединителей на странице " **соединители данных** " в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7cbfc-129">По умолчанию эта роль не назначена ни одной группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-129">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="7cbfc-130">Вы можете добавить роль экспорта для импорта почтовых ящиков в группу ролей Управление организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="7cbfc-131">Вы также можете создать группу ролей, назначить роль импорта для импорта почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="7cbfc-132">Для получения дополнительных сведений обратитесь к разделу [Создание](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение групп ролей](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) статьи "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="7cbfc-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-slack-connector"></a><span data-ttu-id="7cbfc-133">Шаг 1: Настройка соединителя временного резерва</span><span class="sxs-lookup"><span data-stu-id="7cbfc-133">Step 1: Set up the Slack connector</span></span>

<span data-ttu-id="7cbfc-134">Первый шаг — доступ к странице " **соединители данных** " в центре соответствия требованиям Microsoft 365 и создание соединителя для резервных данных.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Slack data.</span></span>

1. <span data-ttu-id="7cbfc-135">Перейдите в раздел [https://compliance.microsoft.com](https://compliance.microsoft.com/) , а затем выберите временной резерв **соединители данных**  >  **Slack**.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Slack**.</span></span>

2. <span data-ttu-id="7cbfc-136">На странице Описание **резервного временного резерва** нажмите **Добавить соединитель**.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-136">On the **Slack** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="7cbfc-137">На странице **условия обслуживания** нажмите кнопку **принять**.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="7cbfc-138">Введите уникальное имя, идентифицирующее соединитель, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="7cbfc-139">Войдите в свою учетную запись Merge1, чтобы настроить соединитель.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-slack"></a><span data-ttu-id="7cbfc-140">Шаг 2: Настройка резервного времени</span><span class="sxs-lookup"><span data-stu-id="7cbfc-140">Step 2: Configure Slack</span></span>

<span data-ttu-id="7cbfc-141">Второй шаг — настройка соединителя временного резерва на сайте Merge1.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-141">The second step is to configure the Slack connector on the Merge1 site.</span></span> <span data-ttu-id="7cbfc-142">Дополнительные сведения о настройке соединителя временного резерва на сайте Глобанет Merge1 можно найти в [руководстве пользователя Merge1 Connectors сторонних Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="7cbfc-142">For more information about how to configure the Slack connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span></span>

<span data-ttu-id="7cbfc-143">После нажатия кнопки **сохранить & готово**вы передаетесь обратно в центр соответствия требованиям Microsoft 365 на страницу **сопоставления пользователей** в мастере соединителей.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-143">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="7cbfc-144">Шаг 3: сопоставление пользователей и завершение установки соединителя</span><span class="sxs-lookup"><span data-stu-id="7cbfc-144">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="7cbfc-145">На странице " **сопоставление внешних пользователей с Microsoft 365 пользователей** " Включите автоматическое сопоставление пользователей.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="7cbfc-146">Резервные элементы включают в себя свойство *Email*, которое содержит адреса электронной почты для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-146">Slack items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="7cbfc-147">Если соединитель может сопоставить этот адрес с пользователем Microsoft 365, элементы будут импортированы в почтовый ящик этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="7cbfc-148">На странице **согласия администратора** нажмите кнопку **предоставить согласие** .</span><span class="sxs-lookup"><span data-stu-id="7cbfc-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="7cbfc-149">Вы будете перенаправлены на сайт Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="7cbfc-150">Нажмите кнопку **принять** , чтобы предоставить согласие.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="7cbfc-151">Ваша организация должна разрешить службе импорта Office 365 доступ к данным почтовых ящиков в Организации.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="7cbfc-152">Чтобы предоставить согласие администратора, необходимо войти в систему, используя учетные данные глобального администратора Microsoft 365, а затем принять запрос согласия.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="7cbfc-153">Если вы не вошли в систему как глобальный администратор, вы можете перейти на [эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) и войти в систему, используя учетные данные глобального администратора, чтобы принять запрос.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="7cbfc-154">Нажмите кнопку **Далее**, проверьте параметры и перейдите на страницу " **соединители данных** ", чтобы просмотреть ход процесса импорта для нового соединителя.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-154">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-slack-connector"></a><span data-ttu-id="7cbfc-155">Шаг 4: мониторинг временного соединителя</span><span class="sxs-lookup"><span data-stu-id="7cbfc-155">Step 4: Monitor the Slack connector</span></span>

<span data-ttu-id="7cbfc-156">После создания соединителя временной резерв можно просмотреть состояние соединителя в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-156">After you create the Slack connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="7cbfc-157">Перейдите к разделу [https://compliance.microsoft.com](https://compliance.microsoft.com) **соединители данных** в левой панели навигации и нажмите кнопку соединители данных.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="7cbfc-158">Перейдите на вкладку **соединители** и выберите **временной временной** соединитель, чтобы отобразить всплывающую страницу, содержащую свойства и сведения о соединителе.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-158">Click the **Connectors** tab and then select the **Slack** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="7cbfc-159">В разделе **состояние соединителя с источником**выберите ссылку **журнал загрузки** , чтобы открыть (или сохранить) журнал состояний для соединителя.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-159">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="7cbfc-160">Этот журнал содержит сведения о данных, импортированных в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="7cbfc-161">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="7cbfc-161">Known issues</span></span>

- <span data-ttu-id="7cbfc-162">В настоящее время импорт вложений или элементов, размер которых превышает 10 МБ, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-162">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="7cbfc-163">Поддержка элементов с большим сроком действия будет доступна позже.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-163">Support for larger items will be available at a later date.</span></span>