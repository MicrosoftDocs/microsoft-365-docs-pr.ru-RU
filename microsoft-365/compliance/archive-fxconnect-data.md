---
title: Настройка соединителя для архивации данных FX Connect в Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: Администраторы могут настроить соединитель для импорта и архивирования данных из Глобанет FX Connect в Microsoft 365. Этот соединитель позволяет архивировать данные из сторонних источников данных в Microsoft 365, чтобы можно было использовать такие функции обеспечения соответствия, как судебное хранение, поиск контента и политики хранения для управления сторонними данными Организации.
ms.openlocfilehash: d22313ab1de1700c14ee4b35f6a0e3dbcae73ae3
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405590"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data-preview"></a><span data-ttu-id="c2d98-104">Настройка соединителя для архивации данных FX Connect (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c2d98-104">Set up a connector to archive FX Connect data (preview)</span></span>

<span data-ttu-id="c2d98-105">Используйте соединитель Глобанет в центре соответствия требованиям Microsoft 365 для импорта и архивирования данных из платформы FX Connect Collaboration для почтовых ящиков пользователей в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2d98-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the FX Connect collaboration platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="c2d98-106">Глобанет предоставляет соединитель [FX Connect](https://globanet.com/fx-connect/) , настроенный для захвата элементов FX Connect и импорта этих элементов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2d98-106">Globanet provides an [FX Connect](https://globanet.com/fx-connect/) connector that is configured to capture FX Connect items and import those items to Microsoft 365.</span></span> <span data-ttu-id="c2d98-107">Соединитель преобразует содержимое из FX Connect, например, руки, сообщения и другие сведения из учетной записи FX Connect вашей организации, в формат электронного сообщения, а затем импортирует эти элементы в почтовый ящик пользователя в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2d98-107">The connector converts the content from FX Connect, such as  trades, messages, and other details from your organization's FX Connect account, to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="c2d98-108">После хранения данных FX Connect в почтовых ящиках пользователей можно применять функции обеспечения соответствия требованиям Microsoft 365, такие как хранение для судебного разбирательства, обнаружение электронных данных, политики хранения и метки хранения, а также соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="c2d98-108">After FX Connect data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="c2d98-109">С помощью соединителя FX Connect для импорта и архивирования данных в Microsoft 365 можно обеспечить соответствие организации политикам государственных учреждений и нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="c2d98-109">Using a FX Connect connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-fx-connect-data"></a><span data-ttu-id="c2d98-110">Общие сведения о архивных данных FX Connect</span><span class="sxs-lookup"><span data-stu-id="c2d98-110">Overview of archiving FX Connect data</span></span>

<span data-ttu-id="c2d98-111">В следующем обзоре описывается процесс использования соединителя для архивации данных FX Connect в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2d98-111">The following overview explains the process of using a connector to archive the FX Connect information in Microsoft 365.</span></span>

![Рабочий процесс архивации данных для FX Connect](../media/FXConnectConnectorWorkflow.png)

1. <span data-ttu-id="c2d98-113">Ваша организация работает с FX Connect, чтобы установить и настроить сайт FX Connect.</span><span class="sxs-lookup"><span data-stu-id="c2d98-113">Your organization works with FX Connect to set up and configure an FX Connect site.</span></span>

2. <span data-ttu-id="c2d98-114">Каждые 24 часа элементы из учетных записей подключения FX копируются на сайт Глобанет Merge1.</span><span class="sxs-lookup"><span data-stu-id="c2d98-114">Once every 24 hours, items from FX Connect accounts are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="c2d98-115">Соединитель также преобразует элементы FX Connect в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c2d98-115">The connector also converts the FX Connect items to an email message format.</span></span>

3. <span data-ttu-id="c2d98-116">Соединитель FX Connect, созданный в центре соответствия требованиям Microsoft 365, подключается к сайту Глобанет Merge1 каждый день и передает элементы FX Connect в безопасное место хранения Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d98-116">The FX Connect connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the FX Connect items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="c2d98-117">Соединитель импортирует элементы в почтовые ящики определенных пользователей, используя значение свойства *Email* для автоматического сопоставления пользователей, как описано в [шаге 3](#step-3-map-users-and-complete-the-connector-setup).</span><span class="sxs-lookup"><span data-stu-id="c2d98-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="c2d98-118">Вложенная папка в папке "Входящие" с именем **FX Connect** создается в почтовых ящиках пользователей, а элементы импортируются в эту папку.</span><span class="sxs-lookup"><span data-stu-id="c2d98-118">A subfolder in the Inbox folder named **FX Connect** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="c2d98-119">Соединитель выполняет это, используя значение свойства *Email* .</span><span class="sxs-lookup"><span data-stu-id="c2d98-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="c2d98-120">Каждый элемент FX Connect содержит это свойство, которое заполняется адресом электронной почты каждого участника элемента.</span><span class="sxs-lookup"><span data-stu-id="c2d98-120">Every FX Connect item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c2d98-121">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="c2d98-121">Before you begin</span></span>

- <span data-ttu-id="c2d98-122">Создайте учетную запись Глобанет Merge1 для соединителей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d98-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span>  <span data-ttu-id="c2d98-123">Для этого обратитесь в [службу поддержки клиентов глобанет](https://globanet.com/ms-connectors-contact).</span><span class="sxs-lookup"><span data-stu-id="c2d98-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="c2d98-124">Вы должны войти в эту учетную запись, когда вы создадите соединитель на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="c2d98-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="c2d98-125">Пользователь, который создает соединитель FX Connect на этапе 1 (и выполняет его на шаге 3), должен быть назначен роли импорта для импорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c2d98-125">The user who creates the FX Connect connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c2d98-126">Эта роль необходима для добавления соединителей на странице " **соединители данных** " в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2d98-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c2d98-127">По умолчанию эта роль не назначена ни одной группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c2d98-127">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="c2d98-128">Вы можете добавить роль экспорта для импорта почтовых ящиков в группу ролей Управление организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c2d98-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c2d98-129">Вы также можете создать группу ролей, назначить роль импорта для импорта почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="c2d98-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c2d98-130">Для получения дополнительных сведений обратитесь к разделу [Создание](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение групп ролей](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) статьи "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="c2d98-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-fx-connect-connector"></a><span data-ttu-id="c2d98-131">Шаг 1: Настройка соединителя подключения FX</span><span class="sxs-lookup"><span data-stu-id="c2d98-131">Step 1: Set up the FX Connect connector</span></span>

<span data-ttu-id="c2d98-132">Первый шаг — доступ к странице " **соединители данных** " в центре соответствия требованиям Microsoft 365 и создание соединителя для данных FX Connect.</span><span class="sxs-lookup"><span data-stu-id="c2d98-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for FX Connect data.</span></span>

1. <span data-ttu-id="c2d98-133">Перейдите к [https://compliance.microsoft.com](https://compliance.microsoft.com/) пункту **Data Connectors**  >  **FX Connect**.</span><span class="sxs-lookup"><span data-stu-id="c2d98-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **FX Connect**.</span></span>

2. <span data-ttu-id="c2d98-134">На странице "Описание продукта **FX Connect** " нажмите **Добавить соединитель**.</span><span class="sxs-lookup"><span data-stu-id="c2d98-134">On the **FX Connect** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="c2d98-135">На странице **условия обслуживания** нажмите кнопку **принять**.</span><span class="sxs-lookup"><span data-stu-id="c2d98-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="c2d98-136">Введите уникальное имя, идентифицирующее соединитель, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c2d98-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="c2d98-137">Войдите в свою учетную запись Merge1, чтобы настроить соединитель.</span><span class="sxs-lookup"><span data-stu-id="c2d98-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-fx-connect-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="c2d98-138">Шаг 2: Настройте соединитель FX Connect на сайте Глобанет Merge1</span><span class="sxs-lookup"><span data-stu-id="c2d98-138">Step 2: Configure the FX Connect connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="c2d98-139">Второй шаг — настройка соединителя FX Connect на сайте Merge1.</span><span class="sxs-lookup"><span data-stu-id="c2d98-139">The second step is to configure the FX Connect connector on the Merge1 site.</span></span> <span data-ttu-id="c2d98-140">Сведения о том, как настроить соединитель FX Connect, можно найти в [руководстве пользователя Merge1 Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf).</span><span class="sxs-lookup"><span data-stu-id="c2d98-140">For information about how to configure the FX Connect connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="c2d98-141">После нажатия кнопки **сохранить & готово**вы передаетесь обратно в центр соответствия требованиям Microsoft 365 на страницу **сопоставления пользователей** в мастере соединителей.</span><span class="sxs-lookup"><span data-stu-id="c2d98-141">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="c2d98-142">Шаг 3: сопоставление пользователей и завершение установки соединителя</span><span class="sxs-lookup"><span data-stu-id="c2d98-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="c2d98-143">Чтобы сопоставить пользователей и завершить настройку соединителя в центре соответствия требованиям Microsoft 365, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c2d98-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="c2d98-144">На странице **Map FX Connect users to Microsoft 365 Users** включите автоматическое сопоставление пользователей.</span><span class="sxs-lookup"><span data-stu-id="c2d98-144">On the **Map FX Connect users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="c2d98-145">Элементы FX Connect включают в себя свойство *Email*, которое содержит адреса электронной почты для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="c2d98-145">The FX Connect items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="c2d98-146">Если соединитель может сопоставить этот адрес с пользователем Microsoft 365, элементы будут импортированы в почтовый ящик этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="c2d98-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="c2d98-147">На странице **согласия администратора** нажмите кнопку **предоставить согласие** .</span><span class="sxs-lookup"><span data-stu-id="c2d98-147">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="c2d98-148">Вы будете перенаправлены на сайт Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d98-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="c2d98-149">Нажмите кнопку **принять** , чтобы предоставить согласие.</span><span class="sxs-lookup"><span data-stu-id="c2d98-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="c2d98-150">Ваша организация должна разрешить службе импорта Office 365 доступ к данным почтовых ящиков в Организации.</span><span class="sxs-lookup"><span data-stu-id="c2d98-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="c2d98-151">Чтобы предоставить согласие администратора, необходимо войти в систему, используя учетные данные глобального администратора Microsoft 365, а затем принять запрос согласия.</span><span class="sxs-lookup"><span data-stu-id="c2d98-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="c2d98-152">Если вы не вошли в систему как глобальный администратор, вы можете перейти на [эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) и войти в систему, используя учетные данные глобального администратора, чтобы принять запрос.</span><span class="sxs-lookup"><span data-stu-id="c2d98-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="c2d98-153">Нажмите кнопку **Далее**, проверьте параметры, а затем перейдите на страницу " **соединители данных** ", чтобы просмотреть ход процесса импорта для нового соединителя.</span><span class="sxs-lookup"><span data-stu-id="c2d98-153">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-fx-connect-connector"></a><span data-ttu-id="c2d98-154">Шаг 4: мониторинг соединителя диспетчера FX</span><span class="sxs-lookup"><span data-stu-id="c2d98-154">Step 4: Monitor the FX Connect connector</span></span>

<span data-ttu-id="c2d98-155">После создания соединителя FX Connect вы можете просмотреть состояние соединителя в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2d98-155">After you create the FX Connect connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="c2d98-156">Перейдите к разделу <https://compliance.microsoft.com/> **соединители данных** в левой панели навигации и нажмите кнопку соединители данных.</span><span class="sxs-lookup"><span data-stu-id="c2d98-156">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="c2d98-157">Перейдите на вкладку **соединители** и выберите соединитель **FX Connect** , чтобы отобразить всплывающую страницу, содержащую свойства и сведения о соединителе.</span><span class="sxs-lookup"><span data-stu-id="c2d98-157">Click the **Connectors** tab and then select the **FX Connect** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="c2d98-158">В разделе **состояние соединителя с источником**выберите ссылку **журнал загрузки** , чтобы открыть (или сохранить) журнал состояний для соединителя.</span><span class="sxs-lookup"><span data-stu-id="c2d98-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="c2d98-159">Этот журнал содержит данные, которые были импортированы в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="c2d98-159">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="c2d98-160">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c2d98-160">Known issues</span></span>

- <span data-ttu-id="c2d98-161">В настоящее время мы не поддерживаем импорт вложений размером более 10 МБ, но поддержка более крупных элементов будет доступна позже.</span><span class="sxs-lookup"><span data-stu-id="c2d98-161">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>