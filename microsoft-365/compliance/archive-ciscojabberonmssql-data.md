---
title: Настройка соединителя для архивации данных Cisco Jabber для данных MS SQL в Microsoft 365
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
description: Администраторы могут настроить соединитель для импорта и архивации данных Cisco Jabber из Глобанет в Microsoft 365. Этот соединитель позволяет архивировать данные из сторонних источников данных в Microsoft 365, чтобы можно было использовать такие функции обеспечения соответствия, как судебное хранение, поиск контента и политики хранения для управления сторонними данными Организации.
ms.openlocfilehash: c87449c35d588fd886d9d108f136eea0a4799ccf
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409219"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data-preview"></a><span data-ttu-id="8f041-104">Настройка соединителя для архивации данных Cisco Jabber (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="8f041-104">Set up a connector to archive Cisco Jabber data (preview)</span></span>

<span data-ttu-id="8f041-105">Используйте соединитель Глобанет в центре соответствия требованиям Microsoft 365 для импорта и архивирования данных из платформы Cisco Jabber в почтовые ящики пользователей в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f041-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="8f041-106">Глобанет предоставляет соединитель [Cisco Jabber](https://globanet.com/jabber/) , настроенный для захвата элементов из базы данных MS SQL Jabber, таких как сообщения чатов 1:1 чата и беседы групп, а затем импортировать эти элементы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f041-106">Globanet provides you with a [Cisco Jabber](https://globanet.com/jabber/) connector that is configured to capture items from the Jabber’s MS SQL database, such as 1:1 chat messages and group chats and then import those items to Microsoft 365.</span></span> <span data-ttu-id="8f041-107">Соединитель извлекает данные из базы данных MS SQL Cisco Jabber, обрабатывает их и преобразует содержимое из учетной записи Cisco Jabber в формат сообщения электронной почты, а затем импортирует эти элементы в почтовый ящик пользователя в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f041-107">The connector retrieves data from the Cisco Jabber’s MS SQL database, processes it, and the converts the content from a user's Cisco Jabber account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="8f041-108">После хранения данных Cisco Jabber в почтовых ящиках пользователей можно применять функции обеспечения соответствия требованиям Microsoft 365, такие как хранение для судебного разбирательства, обнаружение электронных данных, политики хранения и метки хранения, а также соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="8f041-108">After Cisco Jabber data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="8f041-109">Использование соединителя Cisco Jabber для импорта и архивирования данных в Microsoft 365 поможет обеспечить соответствие организации требованиям государственных и законодательных политик.</span><span class="sxs-lookup"><span data-stu-id="8f041-109">Using a Cisco Jabber connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-data"></a><span data-ttu-id="8f041-110">Общие сведения о архивации данных Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="8f041-110">Overview of archiving Cisco Jabber data</span></span>

<span data-ttu-id="8f041-111">В следующем обзоре описывается процесс использования соединителя для архивации данных Cisco Jabber в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f041-111">The following overview explains the process of using a connector to archive Cisco Jabber data in Microsoft 365.</span></span>

![Рабочий процесс архивации данных Cisco Jabber](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. <span data-ttu-id="8f041-113">Ваша организация работает с компанией Cisco для установки и настройки базы данных Cisco Jabber on MS SQL.</span><span class="sxs-lookup"><span data-stu-id="8f041-113">Your organization works with Cisco to set up and configure a Cisco Jabber on MS SQL database.</span></span>

2. <span data-ttu-id="8f041-114">Каждые 24 часа элементы Cisco Jabber копируются из базы данных MS SQL на сайт Глобанет Merge1.</span><span class="sxs-lookup"><span data-stu-id="8f041-114">Once every 24 hours, Cisco Jabber items are copied from the MS SQL database to the Globanet Merge1 site.</span></span> <span data-ttu-id="8f041-115">Соединитель также Преобразовывает содержимое сообщений чата в формат сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8f041-115">The connector also converts the content of chat messages to an email message format.</span></span>

3. <span data-ttu-id="8f041-116">Соединитель Cisco Jabber, созданный в центре соответствия требованиям Microsoft 365, подключается к сайту Глобанет Merge1 каждый день и передает элементы в безопасное место хранения Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f041-116">The Cisco Jabber connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="8f041-117">Автоматическое сопоставление пользователей как соединитель импортирует элементы в почтовые ящики определенных пользователей, используя значение свойства *Email* , описанное в [шаге 3](#step-3-map-users-and-complete-the-connector-setup).</span><span class="sxs-lookup"><span data-stu-id="8f041-117">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="8f041-118">Вложенная папка в папке "Входящие" с именем **Cisco Jabber on MS SQL** создается в почтовых ящиках пользователей, а элементы сообщения импортируются в эту папку.</span><span class="sxs-lookup"><span data-stu-id="8f041-118">A subfolder in the Inbox folder named **Cisco Jabber on MS SQL** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="8f041-119">Соединитель выполняет это, используя значение свойства *Email* .</span><span class="sxs-lookup"><span data-stu-id="8f041-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="8f041-120">Каждый элемент Cisco Jabber содержит это свойство, которое заполняется электронным адресом каждого участника сообщения.</span><span class="sxs-lookup"><span data-stu-id="8f041-120">Every Cisco Jabber item contains this property, which is populated with the email address of every participant of the messages.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8f041-121">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="8f041-121">Before you begin</span></span>

- <span data-ttu-id="8f041-122">Создайте учетную запись Глобанет Merge1 для соединителей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f041-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="8f041-123">Для этого обратитесь в [службу поддержки клиентов глобанет](https://globanet.com/ms-connectors-contact/).</span><span class="sxs-lookup"><span data-stu-id="8f041-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="8f041-124">Вы должны войти в эту учетную запись, когда вы создадите соединитель на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="8f041-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="8f041-125">Необходимо настроить базу данных MS SQL для извлечения элементов Jabber, прежде чем создавать соединитель в действии 1.</span><span class="sxs-lookup"><span data-stu-id="8f041-125">You must set up an MS SQL database to retrieve Jabber items from before creating the connector in Step 1.</span></span> <span data-ttu-id="8f041-126">Вы укажете параметры подключения для базы данных MS SQL при настройке соединителя Cisco Jabber в действии 2.</span><span class="sxs-lookup"><span data-stu-id="8f041-126">You will specify the connection settings for the MS SQL database when configuring the Cisco Jabber connector in Step 2.</span></span> <span data-ttu-id="8f041-127">Дополнительные сведения можно найти в [руководстве пользователя Merge1 сторонних соединителей](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span><span class="sxs-lookup"><span data-stu-id="8f041-127">For more information, see the [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="8f041-128">Пользователь, который создает соединитель Cisco Jabber в действии 1 (и выполняет его на шаге 3), должен быть назначен роли импорта и экспорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8f041-128">The user who creates the Cisco Jabber connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="8f041-129">Эта роль необходима для добавления соединителей на странице " **соединители данных** " в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f041-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8f041-130">По умолчанию эта роль не назначена ни одной группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8f041-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="8f041-131">Вы можете добавить роль экспорта для импорта почтовых ящиков в группу ролей Управление организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8f041-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="8f041-132">Вы также можете создать группу ролей, назначить роль импорта для импорта почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="8f041-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="8f041-133">Для получения дополнительных сведений обратитесь к разделу [Создание](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение групп ролей](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) статьи "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="8f041-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-connector"></a><span data-ttu-id="8f041-134">Шаг 1: Настройка соединителя Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="8f041-134">Step 1: Set up the Cisco Jabber connector</span></span>

<span data-ttu-id="8f041-135">Первый шаг — доступ к **соединителям данных** в центре соответствия требованиям Microsoft 365 и создание соединителя для данных Cisco Jabber в данных MS SQL.</span><span class="sxs-lookup"><span data-stu-id="8f041-135">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for Cisco Jabber on MS SQL data.</span></span>

1. <span data-ttu-id="8f041-136">Перейдите в раздел [https://compliance.microsoft.com](https://compliance.microsoft.com/) **соединители данных**  >  **Cisco Jabber для MS SQL**и нажмите кнопку соединители данных.</span><span class="sxs-lookup"><span data-stu-id="8f041-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/)and then click **Data connectors** > **Cisco Jabber on MS SQL**.</span></span>

2. <span data-ttu-id="8f041-137">На странице "Описание продукта" **Cisco Jabber on MS SQL** нажмите **Добавить соединитель**.</span><span class="sxs-lookup"><span data-stu-id="8f041-137">On the **Cisco Jabber on MS SQL** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="8f041-138">На странице **условия обслуживания** нажмите кнопку **принять**.</span><span class="sxs-lookup"><span data-stu-id="8f041-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="8f041-139">Введите уникальное имя, идентифицирующее соединитель, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8f041-139">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="8f041-140">Войдите в свою учетную запись Merge1, чтобы настроить соединитель.</span><span class="sxs-lookup"><span data-stu-id="8f041-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="8f041-141">Шаг 2: Настройте соединитель Cisco Jabber на сайте Глобанет Merge1</span><span class="sxs-lookup"><span data-stu-id="8f041-141">Step 2: Configure the Cisco Jabber connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="8f041-142">Второй шаг — настройка соединителя Cisco Jabber on MS SQL на сайте Глобанет Merge1.</span><span class="sxs-lookup"><span data-stu-id="8f041-142">The second step is to configure the Cisco Jabber on MS SQL connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="8f041-143">Сведения о настройке соединителя Cisco Jabber on MS SQL можно найти в [руководстве пользователя Merge1 Connectors Guide (сторонние Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)).</span><span class="sxs-lookup"><span data-stu-id="8f041-143">For information about how to configure the Cisco Jabber on MS SQL connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="8f041-144">После нажатия кнопки **сохранить & готово**вы переходите к центру соответствия требованиям Microsoft 365 к странице **сопоставления пользователей** в мастере соединителей.</span><span class="sxs-lookup"><span data-stu-id="8f041-144">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance centre, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="8f041-145">Шаг 3: сопоставление пользователей и завершение установки соединителя</span><span class="sxs-lookup"><span data-stu-id="8f041-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="8f041-146">Чтобы сопоставить пользователей и завершить настройку соединителя в центре соответствия требованиям Microsoft 365, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8f041-146">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="8f041-147">На странице **сопоставить Cisco Jabber on MS SQL users to Microsoft 365 Users** включите автоматическое сопоставление пользователей.</span><span class="sxs-lookup"><span data-stu-id="8f041-147">On the **Map Cisco Jabber on MS SQL users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="8f041-148">Элементы Cisco Jabber on MS SQL включают в себя свойство *Email*, которое содержит адреса электронной почты для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="8f041-148">The Cisco Jabber on MS SQL items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="8f041-149">Если соединитель может сопоставить этот адрес с пользователем Microsoft 365, элементы будут импортированы в почтовый ящик этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f041-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="8f041-150">На странице **"согласие администратора** " щелкните **предоставить согласие**.</span><span class="sxs-lookup"><span data-stu-id="8f041-150">On the **Admin Consent** page, click **Provide Consent**.</span></span> <span data-ttu-id="8f041-151">Вы будете перенаправлены на сайт Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f041-151">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="8f041-152">Нажмите кнопку **принять** , чтобы предоставить согласие.</span><span class="sxs-lookup"><span data-stu-id="8f041-152">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="8f041-153">Ваша организация должна разрешить службе импорта Office 365 доступ к данным почтовых ящиков в Организации.</span><span class="sxs-lookup"><span data-stu-id="8f041-153">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="8f041-154">Чтобы предоставить согласие администратора, необходимо войти в систему, используя учетные данные глобального администратора Microsoft 365, а затем принять запрос согласия.</span><span class="sxs-lookup"><span data-stu-id="8f041-154">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="8f041-155">Если вы не вошли в систему как глобальный администратор, вы можете перейти на [эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) и войти в систему, используя учетные данные глобального администратора, чтобы принять запрос.</span><span class="sxs-lookup"><span data-stu-id="8f041-155">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="8f041-156">Нажмите кнопку **Далее**, проверьте параметры и перейдите на страницу " **соединители данных** ", чтобы просмотреть ход процесса импорта для нового соединителя.</span><span class="sxs-lookup"><span data-stu-id="8f041-156">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-connector"></a><span data-ttu-id="8f041-157">Шаг 4: мониторинг соединителя Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="8f041-157">Step 4: Monitor the Cisco Jabber connector</span></span>

<span data-ttu-id="8f041-158">После создания соединителя Cisco Jabber on MS SQL можно просмотреть состояние соединителя в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f041-158">After you create the Cisco Jabber on MS SQL connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="8f041-159">Перейдите к разделу [https://compliance.microsoft.com](https://compliance.microsoft.com) **соединители данных** в левой панели навигации и нажмите кнопку соединители данных.</span><span class="sxs-lookup"><span data-stu-id="8f041-159">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8f041-160">Перейдите на вкладку **соединители** и выберите параметр **Cisco Jabber on MS SQL** Connector, чтобы отобразить всплывающую страницу, содержащую свойства и информацию о соединителе.</span><span class="sxs-lookup"><span data-stu-id="8f041-160">Click the **Connectors** tab and then select the **Cisco Jabber on MS SQL** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="8f041-161">В разделе **состояние соединителя с источником**выберите ссылку **журнал загрузки** , чтобы открыть (или сохранить) журнал состояний для соединителя.</span><span class="sxs-lookup"><span data-stu-id="8f041-161">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="8f041-162">Этот журнал содержит данные, которые были импортированы в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="8f041-162">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8f041-163">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="8f041-163">Known issues</span></span>

- <span data-ttu-id="8f041-164">В настоящее время импорт вложений или элементов, размер которых превышает 10 МБ, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8f041-164">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="8f041-165">Поддержка элементов с большим сроком действия будет доступна позже.</span><span class="sxs-lookup"><span data-stu-id="8f041-165">Support for larger items will be available at a later date.</span></span>