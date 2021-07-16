---
title: Настройка соединитетеля для архива данных Quip в Microsoft 365
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
description: Узнайте, как настроить и использовать соединителя 17a-4 Quip DataParser для импорта и архива данных Quip в Microsoft 365.
ms.openlocfilehash: e3379e238b0142522d4161149fd38892843e6eae
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454449"
---
# <a name="set-up-a-connector-to-archive-quip-data"></a><span data-ttu-id="0c14c-103">Настройка соединитетеля для архива данных Quip</span><span class="sxs-lookup"><span data-stu-id="0c14c-103">Set up a connector to archive Quip data</span></span>

<span data-ttu-id="0c14c-104">Используйте [quip DataParser](https://www.17a-4.com/quip-dataparser/) от 17a-4 LLC для импорта и архива данных из Quip в почтовые ящики пользователей в Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="0c14c-104">Use the [Quip DataParser](https://www.17a-4.com/quip-dataparser/) from 17a-4 LLC to import and archive data from Quip to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="0c14c-105">DataParser включает соединители Quip, настроенные для захвата элементов из стороннего источника данных и импорта этих элементов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c14c-105">The DataParser includes a Quip connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="0c14c-106">Соединиттель Quip DataParser преобразует данные Quip в формат сообщений электронной почты, а затем импортирует эти элементы в почтовые ящики пользователей в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c14c-106">The Quip DataParser connector converts Quip data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="0c14c-107">После хранения данных Quip в почтовых ящиках пользователей можно применить Microsoft 365, такие как хранение судебного разбирательства, открытие электронных данных, политики хранения и метки хранения, а также соответствие требованиям к связи.</span><span class="sxs-lookup"><span data-stu-id="0c14c-107">After Quip data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="0c14c-108">Использование соединиттеля Quip для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.</span><span class="sxs-lookup"><span data-stu-id="0c14c-108">Using a Quip connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-quip-data"></a><span data-ttu-id="0c14c-109">Обзор архива данных Quip</span><span class="sxs-lookup"><span data-stu-id="0c14c-109">Overview of archiving Quip data</span></span>

<span data-ttu-id="0c14c-110">В следующем обзоре объясняется процесс использования соединиттеля данных для архивации данных Quip в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c14c-110">The following overview explains the process of using a data connector to archive Quip data in Microsoft 365.</span></span>

![Архивативная работа для данных Quip с 17a-4](../media/QuipDataParserConnectorWorkflow.png)

1. <span data-ttu-id="0c14c-112">Ваша организация работает с 17a-4 для настройки и настройки quip DataParser.</span><span class="sxs-lookup"><span data-stu-id="0c14c-112">Your organization works with 17a-4 to set up and configure the Quip DataParser.</span></span>

2. <span data-ttu-id="0c14c-113">Регулярно элементы Quip собираются в DataParser.</span><span class="sxs-lookup"><span data-stu-id="0c14c-113">On a regular basis, Quip items are collected by the DataParser.</span></span> <span data-ttu-id="0c14c-114">DataParser также преобразует содержимое сообщения в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c14c-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="0c14c-115">Соединитетель Quip DataParser, который вы создаете в Центр соответствия требованиям Microsoft 365, подключается к DataParser и передает сообщения в безопасное служба хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0c14c-115">The Quip DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="0c14c-116">Подмостки в папке "Входящие" с именем **Quip DataParser** создаются в почтовых ящиках пользователей, и элементы Quip импортируется в эту папку.</span><span class="sxs-lookup"><span data-stu-id="0c14c-116">A subfolder in the Inbox folder named **Quip DataParser** is created in the user mailboxes, and the Quip items are imported to that folder.</span></span> <span data-ttu-id="0c14c-117">Соединитатель определяет, в какой почтовый ящик импортировать элементы, используя значение свойства *Email.*</span><span class="sxs-lookup"><span data-stu-id="0c14c-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="0c14c-118">Каждый элемент Quip содержит это свойство, заполненное адресом электронной почты каждого участника.</span><span class="sxs-lookup"><span data-stu-id="0c14c-118">Every Quip item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="0c14c-119">Перед настройками соединитетеля</span><span class="sxs-lookup"><span data-stu-id="0c14c-119">Before you set up a connector</span></span>

- <span data-ttu-id="0c14c-120">Создайте учетную запись DataParser для соединители Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c14c-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="0c14c-121">Для этого обратитесь в [ООО "17a-4".](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="0c14c-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="0c14c-122">При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="0c14c-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="0c14c-123">Пользователь, создававший соединиттель Quip DataParser в шаге 1 (и завершавший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c14c-123">The user who creates the Quip DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="0c14c-124">Эта роль требуется для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c14c-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0c14c-125">По умолчанию эта роль не назначена группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c14c-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="0c14c-126">Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c14c-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="0c14c-127">Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="0c14c-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="0c14c-128">Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="0c14c-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-quip-dataparser-connector"></a><span data-ttu-id="0c14c-129">Шаг 1. Настройка соединиттеля Quip DataParser</span><span class="sxs-lookup"><span data-stu-id="0c14c-129">Step 1: Set up a Quip DataParser connector</span></span>

<span data-ttu-id="0c14c-130">Первым шагом является доступ к странице соединители данных в Центр соответствия требованиям Microsoft 365 и создание соединителя 17a-4 для данных Quip.</span><span class="sxs-lookup"><span data-stu-id="0c14c-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Quip data.</span></span>

1. <span data-ttu-id="0c14c-131">Перейдите <https://compliance.microsoft.com> и нажмите **кнопку Соединители данные**  >  **Quip DataParser**.</span><span class="sxs-lookup"><span data-stu-id="0c14c-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Quip DataParser**.</span></span>

2. <span data-ttu-id="0c14c-132">На странице **описания продукта Quip DataParser** нажмите **кнопку Добавить соединителю**.</span><span class="sxs-lookup"><span data-stu-id="0c14c-132">On the **Quip DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="0c14c-133">На странице **Условия службы нажмите** кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="0c14c-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="0c14c-134">Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="0c14c-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="0c14c-135">Вопишите в свою учетную запись 17a-4 и выполните действия мастера подключения Quip DataParser.</span><span class="sxs-lookup"><span data-stu-id="0c14c-135">Sign in to your 17a-4 account and complete the steps in the Quip DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-quip-dataparser-connector"></a><span data-ttu-id="0c14c-136">Шаг 2. Настройка соединиттеля Quip DataParser</span><span class="sxs-lookup"><span data-stu-id="0c14c-136">Step 2: Configure the Quip DataParser connector</span></span>

<span data-ttu-id="0c14c-137">Работа с поддержкой 17a-4 для настройки соединиттеля Quip DataParser.</span><span class="sxs-lookup"><span data-stu-id="0c14c-137">Work with 17a-4 Support to configure the Quip DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="0c14c-138">Шаг 3. Пользователи карт</span><span class="sxs-lookup"><span data-stu-id="0c14c-138">Step 3: Map users</span></span>

<span data-ttu-id="0c14c-139">Соединиттель Quip DataParser автоматически сопопоает пользователей с Microsoft 365 адресами электронной почты перед импортом данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c14c-139">The Quip DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-quip-dataparser-connector"></a><span data-ttu-id="0c14c-140">Шаг 4. Мониторинг соединиттеля Quip DataParser</span><span class="sxs-lookup"><span data-stu-id="0c14c-140">Step 4: Monitor the Quip DataParser connector</span></span>

<span data-ttu-id="0c14c-141">После создания соединиттеля Quip DataParser можно просмотреть состояние соединитетеля в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c14c-141">After you create a Quip DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="0c14c-142">Перейдите <https://compliance.microsoft.com> и щелкните **соединители данных** в левом nav.</span><span class="sxs-lookup"><span data-stu-id="0c14c-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="0c14c-143">Щелкните  вкладку Соединители, а затем выберите соединиттель Quip DataParser, созданный для отображения страницы вылетов, которая содержит свойства и сведения о соединителе.</span><span class="sxs-lookup"><span data-stu-id="0c14c-143">Click the **Connectors** tab and then select the Quip DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="0c14c-144">В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="0c14c-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="0c14c-145">В этом журнале содержатся данные, импортируемые в облако Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0c14c-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0c14c-146">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="0c14c-146">Known issues</span></span>

<span data-ttu-id="0c14c-147">В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="0c14c-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="0c14c-148">Поддержка более крупных элементов будет доступна позднее.</span><span class="sxs-lookup"><span data-stu-id="0c14c-148">Support for larger items will be available at a later date.</span></span>
