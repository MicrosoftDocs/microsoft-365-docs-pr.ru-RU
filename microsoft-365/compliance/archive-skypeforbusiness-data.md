---
title: Настройка соединитетеля для архива Skype для бизнеса данных в Microsoft 365
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
description: Узнайте, как настроить и использовать соединители в Центр соответствия требованиям Microsoft 365 для импорта и архива данных с Skype для бизнеса до Microsoft 365.
ms.openlocfilehash: 93128af0c7f305cb2bef55efd5520de77555a222
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054868"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data-preview"></a><span data-ttu-id="05629-103">Настройка соединитетеля для архива Skype для бизнеса данных (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="05629-103">Set up a connector to archive Skype for Business data (preview)</span></span>

<span data-ttu-id="05629-104">Используйте соединитель Veritas в Центр соответствия требованиям Microsoft 365 для импорта и архива данных с платформы Skype для бизнеса для почтовых ящиков пользователей в Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="05629-104">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Skype for Business platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="05629-105">Veritas предоставляет [](https://www.veritas.com/en/au/insights/merge1/skype-for-business) Skype для бизнеса, настроенный для захвата элементов из стороннего источника данных (на регулярной основе) и импорта этих элементов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05629-105">Veritas provides a [Skype for Business](https://www.veritas.com/en/au/insights/merge1/skype-for-business) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="05629-106">Соединитатель преобразует содержимое, например сообщения между пользователями, постоянные чаты и конференц-сообщения из Skype для бизнеса в формат электронной почты, а затем импортирует эти элементы в почтовый ящик пользователя в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05629-106">The connector converts the content such as messages between users, persistent chats, and conference messages from Skype for Business to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="05629-107">После Skype для бизнеса данных, хранимых в почтовых ящиках пользователей, можно применить Microsoft 365, такие как хранение судебного разбирательства, открытие электронных данных, политики хранения и метки хранения.</span><span class="sxs-lookup"><span data-stu-id="05629-107">After Skype for Business data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="05629-108">Использование соединиттеля Skype для бизнеса для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.</span><span class="sxs-lookup"><span data-stu-id="05629-108">Using a Skype for Business connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-skype-for-business-data"></a><span data-ttu-id="05629-109">Обзор архива Skype для бизнеса данных</span><span class="sxs-lookup"><span data-stu-id="05629-109">Overview of archiving Skype for Business data</span></span>

<span data-ttu-id="05629-110">В следующем обзоре объясняется процесс использования соединитетеля для архивации Skype для бизнеса данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05629-110">The following overview explains the process of using a connector to archive the Skype for Business data in Microsoft 365.</span></span>

![Архивавка рабочего процесса для Skype для бизнеса данных](../media/SkypeforBusinessConnectorWorkflow.png)

1. <span data-ttu-id="05629-112">Организация работает с Skype для бизнеса для настройки и настройки Skype для бизнеса сайта.</span><span class="sxs-lookup"><span data-stu-id="05629-112">Your organization works with Skype for Business to set up and configure a Skype for Business site.</span></span>

2. <span data-ttu-id="05629-113">Каждые 24 часа Skype для бизнеса элементы копируется на сайте Veritas Merge1.</span><span class="sxs-lookup"><span data-stu-id="05629-113">Once every 24 hours, Skype for Business items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="05629-114">Соединитатель также преобразует элементы Skype для бизнеса в формат сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="05629-114">The connector also converts Skype for Business items to an email message format.</span></span>

3. <span data-ttu-id="05629-115">Соединитель Skype для бизнеса, который вы создаете в Центр соответствия требованиям Microsoft 365, подключается к сайту Veritas Merge1 каждый день и передает содержимое Skype для бизнеса в безопасное служба хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="05629-115">The Skype for Business connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the Skype for Business content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="05629-116">Соединитатель импортирует преобразованные элементы в почтовые ящики определенных пользователей, используя значение свойства *Email* автоматического сопоставления пользователей, как описано в [шаге 3](#step-3-map-users-and-complete-the-connector-setup).</span><span class="sxs-lookup"><span data-stu-id="05629-116">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="05629-117">В почтовых ящиках **пользователей создается Skype для бизнеса** папка в папке "Входящие", и элементы импортируется в эту папку.</span><span class="sxs-lookup"><span data-stu-id="05629-117">A subfolder in the Inbox folder named **Skype for Business** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="05629-118">Соединитатель делает это, используя значение свойства *Email.*</span><span class="sxs-lookup"><span data-stu-id="05629-118">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="05629-119">Каждый Skype для бизнеса содержит это свойство, которое заполняется адресом электронной почты каждого участника элемента.</span><span class="sxs-lookup"><span data-stu-id="05629-119">Every Skype for Business item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="05629-120">Перед настройками соединитетеля</span><span class="sxs-lookup"><span data-stu-id="05629-120">Before you set up a connector</span></span>

- <span data-ttu-id="05629-121">Создание учетной записи Merge1 для соединители Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05629-121">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="05629-122">Для этого обратитесь в службу поддержки клиентов [Veritas.](https://www.veritas.com/form/requestacall/ms-connectors-contact.html)</span><span class="sxs-lookup"><span data-stu-id="05629-122">To do this, contact [Veritas Customer Support](https://www.veritas.com/form/requestacall/ms-connectors-contact.html).</span></span> <span data-ttu-id="05629-123">При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="05629-123">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="05629-124">Пользователю, создававшего Skype для бизнеса в шаге 1 (и завершающую его в шаге 3), необходимо приступить к роли экспорта импорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05629-124">The user who creates the Skype for Business connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="05629-125">Эта роль требуется для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05629-125">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="05629-126">По умолчанию эта роль не назначена какой-либо группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05629-126">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="05629-127">Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05629-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="05629-128">Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="05629-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="05629-129">Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="05629-129">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-skype-for-business-connector"></a><span data-ttu-id="05629-130">Шаг 1. Настройка соединиттеля Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="05629-130">Step 1: Set up the Skype for Business connector</span></span>

<span data-ttu-id="05629-131">Первым шагом является доступ  к странице Соединители данных в Центр соответствия требованиям Microsoft 365 и создание соединитетеля для Skype для бизнеса данных.</span><span class="sxs-lookup"><span data-stu-id="05629-131">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Skype for Business data.</span></span>

1. <span data-ttu-id="05629-132">Перейдите <https://compliance.microsoft.com> к и нажмите **соединители**  >  **данных Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="05629-132">Go to <https://compliance.microsoft.com> and click **Data connectors** > **Skype for Business**.</span></span>

2. <span data-ttu-id="05629-133">На странице **Skype для бизнеса** описание продукта нажмите **кнопку Добавить соединителю**.</span><span class="sxs-lookup"><span data-stu-id="05629-133">On the **Skype for Business** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="05629-134">На странице **Условия службы нажмите** кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="05629-134">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="05629-135">Введите уникальное имя, идентифицируемое соединитетелем, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="05629-135">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="05629-136">Впишитесь в свою учетную запись Merge1, чтобы настроить соединители.</span><span class="sxs-lookup"><span data-stu-id="05629-136">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a><span data-ttu-id="05629-137">Шаг 2. Настройка Skype для бизнеса на сайте Veritas Merge1</span><span class="sxs-lookup"><span data-stu-id="05629-137">Step 2: Configure the Skype for Business on the Veritas Merge1 site</span></span>

<span data-ttu-id="05629-138">Второй шаг — настройка соединителя Skype для бизнеса на сайте Veritas Merge1.</span><span class="sxs-lookup"><span data-stu-id="05629-138">The second step is to configure the Skype for Business connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="05629-139">Сведения о настройке соединители Skype для бизнеса см. в руководстве по пользователю [Merge1 Сторонние соединители.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="05629-139">For information about how to configure the Skype for Business connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf).</span></span>

<span data-ttu-id="05629-140">После нажатия **кнопки Сохранить &**  finish отображается страница сопоставления пользователя в мастере соединители в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05629-140">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="05629-141">Шаг 3. Карта пользователей и завершение установки соединитетеля</span><span class="sxs-lookup"><span data-stu-id="05629-141">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="05629-142">Чтобы соединять пользователей и выполнить установку соединитетеля в Центр соответствия требованиям Microsoft 365, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="05629-142">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="05629-143">На странице **Map Skype для бизнеса пользователям Microsoft 365** пользователям включить автоматическое сопоставление пользователей.</span><span class="sxs-lookup"><span data-stu-id="05629-143">On the **Map Skype for Business users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="05629-144">В Skype для бизнеса элементов содержится свойство *Email,* которое содержит адреса электронной почты для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="05629-144">The Skype for Business items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="05629-145">Если соединитатель может связать этот адрес с Microsoft 365 пользователем, элементы импортируется в почтовый ящик этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="05629-145">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="05629-146">Нажмите **кнопку Далее,** просмотрите параметры и перейдите на страницу соединители данных, чтобы просмотреть ход процесса импорта для нового соединитетеля. </span><span class="sxs-lookup"><span data-stu-id="05629-146">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-skype-for-business-connector"></a><span data-ttu-id="05629-147">Шаг 4. Мониторинг Skype для бизнеса соединители</span><span class="sxs-lookup"><span data-stu-id="05629-147">Step 4: Monitor the Skype for Business connector</span></span>

<span data-ttu-id="05629-148">После создания соединитетеля Skype для бизнеса можно просмотреть состояние соединитетеля в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05629-148">After you create the Skype for Business connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="05629-149">Перейдите <https://compliance.microsoft.com/> и щелкните **соединители данных** в левом nav.</span><span class="sxs-lookup"><span data-stu-id="05629-149">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="05629-150">Щелкните **вкладку** Соединители, а затем **выберите Skype для бизнеса,** чтобы отобразить страницу вылетов, которая содержит свойства и сведения о соединителе.</span><span class="sxs-lookup"><span data-stu-id="05629-150">Click the **Connectors** tab and then select the **Skype for Business** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="05629-151">В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="05629-151">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="05629-152">В этом журнале содержатся данные, импортируемые в облако Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="05629-152">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="05629-153">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="05629-153">Known issues</span></span>

- <span data-ttu-id="05629-154">В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="05629-154">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="05629-155">Поддержка более крупных элементов будет доступна позднее.</span><span class="sxs-lookup"><span data-stu-id="05629-155">Support for larger items will be available at a later date.</span></span>