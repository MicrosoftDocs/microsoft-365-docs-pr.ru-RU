---
title: Настройка соединителю для архива данных взрывателя в Microsoft 365
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
description: Узнайте, как настроить и использовать соединителю fuze DataParser 17a-4 для импорта и архива данных взрывателя в Microsoft 365.
ms.openlocfilehash: 9f3c7590a033c2c19d9b588167d67c24f917ec5f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454509"
---
# <a name="set-up-a-connector-to-archive-fuze-data"></a><span data-ttu-id="fb950-103">Настройка соединителю для архива данных взрывателя</span><span class="sxs-lookup"><span data-stu-id="fb950-103">Set up a connector to archive Fuze data</span></span>

<span data-ttu-id="fb950-104">Используйте [fuze DataParser](https://www.17a-4.com/fuze-dataparser/) от 17a-4 LLC для импорта и архива данных из fuze в почтовые ящики пользователей в Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="fb950-104">Use the [Fuze DataParser](https://www.17a-4.com/fuze-dataparser/) from 17a-4 LLC to import and archive data from Fuze to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="fb950-105">DataParser включает соединителю fuze, который настроен для захвата элементов из стороннего источника данных и импорта этих элементов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb950-105">The DataParser includes a Fuze connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="fb950-106">Соединиттель Fuze DataParser преобразует данные взрывателя в формат сообщений электронной почты, а затем импортирует эти элементы в почтовые ящики пользователей в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb950-106">The Fuze DataParser connector converts Fuze data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="fb950-107">После хранения данных взрывания в почтовых ящиках пользователей можно применить Microsoft 365, такие как хранение судебного разбирательства, электронные сведения, политики хранения и метки хранения, а также соответствие требованиям связи.</span><span class="sxs-lookup"><span data-stu-id="fb950-107">After Fuze data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="fb950-108">Использование соединиттеля взрывателя для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.</span><span class="sxs-lookup"><span data-stu-id="fb950-108">Using a Fuze connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-fuze-data"></a><span data-ttu-id="fb950-109">Обзор архива данных взрывания</span><span class="sxs-lookup"><span data-stu-id="fb950-109">Overview of archiving Fuze data</span></span>

<span data-ttu-id="fb950-110">В следующем обзоре объясняется процесс использования соединителю данных для архивации данных fuze в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb950-110">The following overview explains the process of using a data connector to archive Fuze data in Microsoft 365.</span></span>

![Архивативная работа для данных взрывания с 17a-4](../media/FuzeDataParserConnectorWorkflow.png)

1. <span data-ttu-id="fb950-112">Ваша организация работает с 17a-4 для настройки и настройки fuze DataParser.</span><span class="sxs-lookup"><span data-stu-id="fb950-112">Your organization works with 17a-4 to set up and configure the Fuze DataParser.</span></span>

2. <span data-ttu-id="fb950-113">На регулярной основе элементы взрыватель собираются dataParser.</span><span class="sxs-lookup"><span data-stu-id="fb950-113">On a regular basis, Fuze items are collected by the DataParser.</span></span> <span data-ttu-id="fb950-114">DataParser также преобразует содержимое сообщения в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fb950-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="fb950-115">Соединителю Fuze DataParser, который вы создаете в Центр соответствия требованиям Microsoft 365, подключается к DataParser и передает сообщения в безопасное служба хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fb950-115">The Fuze DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="fb950-116">В почтовых ящиках пользователей создается подмостки в папке "Входящие" с именем **Fuze DataParser,** и элементы взрыватель импортируется в эту папку.</span><span class="sxs-lookup"><span data-stu-id="fb950-116">A subfolder in the Inbox folder named **Fuze DataParser** is created in the user mailboxes, and the Fuze items are imported to that folder.</span></span> <span data-ttu-id="fb950-117">Соединитатель определяет, в какой почтовый ящик импортировать элементы, используя значение свойства *Email.*</span><span class="sxs-lookup"><span data-stu-id="fb950-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="fb950-118">Каждый элемент fuze содержит это свойство, которое заполняется адресом электронной почты каждого участника.</span><span class="sxs-lookup"><span data-stu-id="fb950-118">Every Fuze item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="fb950-119">Перед настройками соединитетеля</span><span class="sxs-lookup"><span data-stu-id="fb950-119">Before you set up a connector</span></span>

- <span data-ttu-id="fb950-120">Создайте учетную запись DataParser для соединители Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb950-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="fb950-121">Для этого обратитесь в [ООО "17a-4".](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="fb950-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="fb950-122">При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="fb950-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="fb950-123">Пользователь, создавший соединителю Fuze DataParser в шаге 1 (и завершавший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb950-123">The user who creates the Fuze DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fb950-124">Эта роль требуется для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb950-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fb950-125">По умолчанию эта роль не назначена группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb950-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="fb950-126">Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb950-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fb950-127">Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="fb950-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fb950-128">Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="fb950-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-fuze-dataparser-connector"></a><span data-ttu-id="fb950-129">Шаг 1. Настройка соединиттеля Fuze DataParser</span><span class="sxs-lookup"><span data-stu-id="fb950-129">Step 1: Set up a Fuze DataParser connector</span></span>

<span data-ttu-id="fb950-130">Первым шагом является доступ к странице соединители данных в Центр соответствия требованиям Microsoft 365 и создание соединителя 17a-4 для данных Fuze.</span><span class="sxs-lookup"><span data-stu-id="fb950-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Fuze data.</span></span>

1. <span data-ttu-id="fb950-131">Перейдите к соединителю данных и нажмите кнопку <https://compliance.microsoft.com>   >  **Fuze DataParser**.</span><span class="sxs-lookup"><span data-stu-id="fb950-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Fuze DataParser**.</span></span>

2. <span data-ttu-id="fb950-132">На странице **описания продукта Fuze DataParser** нажмите **кнопку Добавить соединителю**.</span><span class="sxs-lookup"><span data-stu-id="fb950-132">On the **Fuze DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="fb950-133">На странице **Условия службы нажмите** кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="fb950-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fb950-134">Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="fb950-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="fb950-135">Вопишите в свою учетную запись 17a-4 и выполните действия в мастере подключения Fuze DataParser.</span><span class="sxs-lookup"><span data-stu-id="fb950-135">Sign in to your 17a-4 account and complete the steps in the Fuze DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-fuze-dataparser-connector"></a><span data-ttu-id="fb950-136">Шаг 2. Настройка соединиттеля Fuze DataParser</span><span class="sxs-lookup"><span data-stu-id="fb950-136">Step 2: Configure the Fuze DataParser connector</span></span>

<span data-ttu-id="fb950-137">Работа с поддержкой 17a-4 для настройки соединиттеля Fuze DataParser.</span><span class="sxs-lookup"><span data-stu-id="fb950-137">Work with 17a-4 Support to configure the Fuze DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="fb950-138">Шаг 3. Пользователи карт</span><span class="sxs-lookup"><span data-stu-id="fb950-138">Step 3: Map users</span></span>

<span data-ttu-id="fb950-139">Соединиттель Fuze DataParser автоматически соединит пользователей с Microsoft 365 адресами электронной почты перед импортом данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb950-139">The Fuze DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-fuze-dataparser-connector"></a><span data-ttu-id="fb950-140">Шаг 4. Мониторинг соединиттеля Fuze DataParser</span><span class="sxs-lookup"><span data-stu-id="fb950-140">Step 4: Monitor the Fuze DataParser connector</span></span>

<span data-ttu-id="fb950-141">После создания соединиттеля Fuze DataParser можно просмотреть состояние соединителю в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb950-141">After you create a Fuze DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="fb950-142">Перейдите <https://compliance.microsoft.com> и щелкните **соединители данных** в левом nav.</span><span class="sxs-lookup"><span data-stu-id="fb950-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="fb950-143">Щелкните  вкладку Соединители, а затем выберите соединителю Fuze DataParser, созданный для отображения страницы вылетов, которая содержит свойства и сведения о соединителе.</span><span class="sxs-lookup"><span data-stu-id="fb950-143">Click the **Connectors** tab and then select the Fuze DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="fb950-144">В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="fb950-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="fb950-145">В этом журнале содержатся данные, импортируемые в облако Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fb950-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fb950-146">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="fb950-146">Known issues</span></span>

<span data-ttu-id="fb950-147">В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="fb950-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="fb950-148">Поддержка более крупных элементов будет доступна позднее.</span><span class="sxs-lookup"><span data-stu-id="fb950-148">Support for larger items will be available at a later date.</span></span>
