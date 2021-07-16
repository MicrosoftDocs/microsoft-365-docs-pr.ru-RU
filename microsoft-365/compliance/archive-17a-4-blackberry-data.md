---
title: Настройка соединителю для архива данных BlackBerry в Microsoft 365
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
description: Узнайте, как настроить и использовать соединитель 17a-4 BlackBerry DataParser для импорта и архива данных BlackBerry в Microsoft 365.
ms.openlocfilehash: 565b51c4575324bfe1c80299adf82d391a8d14e1
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454557"
---
# <a name="set-up-a-connector-to-archive-blackberry-data"></a><span data-ttu-id="4cf81-103">Настройка соединителю для архива данных BlackBerry</span><span class="sxs-lookup"><span data-stu-id="4cf81-103">Set up a connector to archive BlackBerry data</span></span>

<span data-ttu-id="4cf81-104">Используйте [BlackBerry DataParser](https://www.17a-4.com/BlackBerry-dataparser/) от 17a-4 LLC для импорта и архива корпоративных данных BlackBerry в почтовые ящики пользователей в Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="4cf81-104">Use the [BlackBerry DataParser](https://www.17a-4.com/BlackBerry-dataparser/) from 17a-4 LLC to import and archive BlackBerry enterprise data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="4cf81-105">DataParser включает соединителю BlackBerry, который настроен для захвата элементов из стороннего источника данных и импорта этих элементов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cf81-105">The DataParser includes a BlackBerry connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="4cf81-106">Соединиттель BlackBerry DataParser преобразует данные BlackBerry в формат сообщений электронной почты, а затем импортирует эти элементы в почтовые ящики пользователей в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cf81-106">The BlackBerry DataParser connector converts BlackBerry data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="4cf81-107">После хранения данных BlackBerry в почтовых ящиках пользователей можно применить Microsoft 365, такие как хранение судебного разбирательства, электронные сведения, политики хранения и метки хранения, а также соответствие требованиям связи.</span><span class="sxs-lookup"><span data-stu-id="4cf81-107">After BlackBerry data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="4cf81-108">Использование соединиттеля BlackBerry для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.</span><span class="sxs-lookup"><span data-stu-id="4cf81-108">Using a BlackBerry connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-blackberry-data"></a><span data-ttu-id="4cf81-109">Обзор архива данных BlackBerry</span><span class="sxs-lookup"><span data-stu-id="4cf81-109">Overview of archiving BlackBerry data</span></span>

<span data-ttu-id="4cf81-110">В следующем обзоре объясняется процесс использования соединиттеля данных для архивации данных BlackBerry в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cf81-110">The following overview explains the process of using a data connector to archive BlackBerry data in Microsoft 365.</span></span>

![Архивавка рабочего процесса для данных BlackBerry с 17a-4](../media/BlackBerryDataParserConnectorWorkflow.png)

1. <span data-ttu-id="4cf81-112">Ваша организация работает с 17a-4 для настройки и настройки BlackBerry DataParser.</span><span class="sxs-lookup"><span data-stu-id="4cf81-112">Your organization works with 17a-4 to set up and configure the BlackBerry DataParser.</span></span>

2. <span data-ttu-id="4cf81-113">Регулярно элементы BlackBerry собираются в DataParser.</span><span class="sxs-lookup"><span data-stu-id="4cf81-113">On a regular basis, BlackBerry items are collected by the DataParser.</span></span> <span data-ttu-id="4cf81-114">DataParser также преобразует содержимое сообщения в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4cf81-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="4cf81-115">Соединителю BlackBerry DataParser, который вы создаете в Центр соответствия требованиям Microsoft 365, подключается к DataParser и передает сообщения в безопасное служба хранилища Azure в облаке Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4cf81-115">The BlackBerry DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="4cf81-116">В почтовых ящиках пользователей создается подмостки в папке "Входящие" с именем **BlackBerry DataParser,** и элементы BlackBerry импортируется в эту папку.</span><span class="sxs-lookup"><span data-stu-id="4cf81-116">A subfolder in the Inbox folder named **BlackBerry DataParser** is created in the user mailboxes, and the BlackBerry items are imported to that folder.</span></span> <span data-ttu-id="4cf81-117">Соединитатель определяет, в какой почтовый ящик импортировать элементы, используя значение свойства *Email.*</span><span class="sxs-lookup"><span data-stu-id="4cf81-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="4cf81-118">Каждый элемент BlackBerry содержит это свойство, которое заполняется адресом электронной почты каждого участника.</span><span class="sxs-lookup"><span data-stu-id="4cf81-118">Every BlackBerry item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="4cf81-119">Перед настройками соединитетеля</span><span class="sxs-lookup"><span data-stu-id="4cf81-119">Before you set up a connector</span></span>

- <span data-ttu-id="4cf81-120">Создайте учетную запись DataParser для соединители Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4cf81-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="4cf81-121">Для этого обратитесь в [ООО "17a-4".](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="4cf81-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="4cf81-122">При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="4cf81-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="4cf81-123">Пользователь, создавший соединителю BlackBerry DataParser в шаге 1 (и завершивший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4cf81-123">The user who creates the BlackBerry DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="4cf81-124">Эта роль требуется для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cf81-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4cf81-125">По умолчанию эта роль не назначена группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4cf81-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="4cf81-126">Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4cf81-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="4cf81-127">Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="4cf81-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="4cf81-128">Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="4cf81-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-blackberry-dataparser-connector"></a><span data-ttu-id="4cf81-129">Шаг 1. Настройка соединиттеля BlackBerry DataParser</span><span class="sxs-lookup"><span data-stu-id="4cf81-129">Step 1: Set up a BlackBerry DataParser connector</span></span>

<span data-ttu-id="4cf81-130">Первым шагом является доступ к странице соединители данных в Центр соответствия требованиям Microsoft 365 и создание соединителя 17a-4 для данных BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="4cf81-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for BlackBerry data.</span></span>

1. <span data-ttu-id="4cf81-131">Перейдите <https://compliance.microsoft.com> к и нажмите **кнопку Соединители**  >  **данных BlackBerry DataParser**.</span><span class="sxs-lookup"><span data-stu-id="4cf81-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **BlackBerry DataParser**.</span></span>

2. <span data-ttu-id="4cf81-132">На странице **описания продукта BlackBerry DataParser** нажмите **кнопку Добавить соединителю**.</span><span class="sxs-lookup"><span data-stu-id="4cf81-132">On the **BlackBerry DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="4cf81-133">На странице **Условия службы нажмите** кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="4cf81-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="4cf81-134">Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="4cf81-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="4cf81-135">Вопишите в свою учетную запись 17a-4 и выполните действия мастера подключения BlackBerry DataParser.</span><span class="sxs-lookup"><span data-stu-id="4cf81-135">Sign in to your 17a-4 account and complete the steps in the BlackBerry DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-blackberry-dataparser-connector"></a><span data-ttu-id="4cf81-136">Шаг 2. Настройка соединителю BlackBerry DataParser</span><span class="sxs-lookup"><span data-stu-id="4cf81-136">Step 2: Configure the BlackBerry DataParser connector</span></span>

<span data-ttu-id="4cf81-137">Работа с поддержкой 17a-4 для настройки соединиттеля BlackBerry DataParser.</span><span class="sxs-lookup"><span data-stu-id="4cf81-137">Work with 17a-4 Support to configure the BlackBerry DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="4cf81-138">Шаг 3. Пользователи карт</span><span class="sxs-lookup"><span data-stu-id="4cf81-138">Step 3: Map users</span></span>

<span data-ttu-id="4cf81-139">Соединиттель BlackBerry DataParser автоматически соберет пользователей с Microsoft 365 адресами электронной почты перед импортом данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cf81-139">The BlackBerry DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-blackberry-dataparser-connector"></a><span data-ttu-id="4cf81-140">Шаг 4. Мониторинг соединиттеля BlackBerry DataParser</span><span class="sxs-lookup"><span data-stu-id="4cf81-140">Step 4: Monitor the BlackBerry DataParser connector</span></span>

<span data-ttu-id="4cf81-141">После создания соединиттеля BlackBerry DataParser можно просмотреть состояние соединителю в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cf81-141">After you create a BlackBerry DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="4cf81-142">Перейдите <https://compliance.microsoft.com> и щелкните **соединители данных** в левом nav.</span><span class="sxs-lookup"><span data-stu-id="4cf81-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="4cf81-143">Щелкните  вкладку Соединители, а затем выберите соединитель BlackBerry DataParser, созданный для отображения страницы вылетов, которая содержит свойства и сведения о соединителе.</span><span class="sxs-lookup"><span data-stu-id="4cf81-143">Click the **Connectors** tab and then select the BlackBerry DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="4cf81-144">В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="4cf81-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="4cf81-145">В этом журнале содержатся данные, импортируемые в облако Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4cf81-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="4cf81-146">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="4cf81-146">Known issues</span></span>

<span data-ttu-id="4cf81-147">В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="4cf81-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="4cf81-148">Поддержка более крупных элементов будет доступна позднее.</span><span class="sxs-lookup"><span data-stu-id="4cf81-148">Support for larger items will be available at a later date.</span></span>