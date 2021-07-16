---
title: Настройка соединитетеля для архива данных Подключение чата в Microsoft 365
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
description: Узнайте, как настроить и использовать соединителя 17a-4 ICE Подключение Chat DataParser для импорта и архива данных чата ICE Подключение в Microsoft 365.
ms.openlocfilehash: 0aac5c701f122eaf99497635281ebc07d835fc2e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454485"
---
# <a name="set-up-a-connector-to-archive-ice-connect-chat-data"></a><span data-ttu-id="1bf44-103">Настройка соединитетеля для архива данных Подключение чата</span><span class="sxs-lookup"><span data-stu-id="1bf44-103">Set up a connector to archive ICE Connect Chat data</span></span>

<span data-ttu-id="1bf44-104">Используйте [ICE DataParser](https://www.17a-4.com/ice-dataparser/) от 17a-4 LLC для импорта и архива данных из ICE Подключение Chat в почтовые ящики пользователей в Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="1bf44-104">Use the [ICE DataParser](https://www.17a-4.com/ice-dataparser/) from 17a-4 LLC to import and archive data from ICE Connect Chat to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="1bf44-105">DataParser включает соединители ICE Chat, настроенные для захвата элементов из стороннего источника данных и импорта этих элементов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bf44-105">The DataParser includes an ICE Chat connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="1bf44-106">Соединиттель ICE DataParser преобразует данные ice Подключение чата в формат сообщений электронной почты, а затем импортирует эти элементы в почтовые ящики пользователей в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bf44-106">The ICE DataParser connector converts ICE Connect Chat data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="1bf44-107">После хранения данных Подключение чата в почтовых ящиках пользователей можно применить такие Microsoft 365, как хранение судебного разбирательства, электронные сведения, политики хранения и метки хранения, а также соответствие требованиям к связи.</span><span class="sxs-lookup"><span data-stu-id="1bf44-107">After ICE Connect Chat data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="1bf44-108">Использование соединиттеля ICE DataParser для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.</span><span class="sxs-lookup"><span data-stu-id="1bf44-108">Using an ICE DataParser connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ice-chat-data"></a><span data-ttu-id="1bf44-109">Обзор архива данных ICE Chat</span><span class="sxs-lookup"><span data-stu-id="1bf44-109">Overview of archiving ICE Chat data</span></span>

<span data-ttu-id="1bf44-110">В следующем обзоре объясняется процесс использования соединиттеля данных для архивации данных ICE Подключение чата в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bf44-110">The following overview explains the process of using a data connector to archive ICE Connect Chat data in Microsoft 365.</span></span>

![Архивативная работа для данных чата Подключение ICE с 17a-4](../media/ICEChatDataParserConnectorWorkflow.png)

1. <span data-ttu-id="1bf44-112">Ваша организация работает с 17a-4 для настройки и настройки ICE DataParser.</span><span class="sxs-lookup"><span data-stu-id="1bf44-112">Your organization works with 17a-4 to set up and configure the ICE DataParser.</span></span>

2. <span data-ttu-id="1bf44-113">Регулярно элементы чата ICE Подключение собираются в DataParser.</span><span class="sxs-lookup"><span data-stu-id="1bf44-113">On a regular basis, ICE Connect Chat items are collected by the DataParser.</span></span> <span data-ttu-id="1bf44-114">DataParser также преобразует содержимое сообщения в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1bf44-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="1bf44-115">Соединитетель ICE DataParser, который вы создаете в Центр соответствия требованиям Microsoft 365, подключается к DataParser и передает сообщения в безопасное служба хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1bf44-115">The ICE DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="1bf44-116">В почтовых ящиках пользователей создается подмостка в папке Входящие с именем **ICE DataParser,** и элементы чата ICE Подключение в эту папку импортируется.</span><span class="sxs-lookup"><span data-stu-id="1bf44-116">A subfolder in the Inbox folder named **ICE DataParser** is created in the user mailboxes, and the ICE Connect Chat items are imported to that folder.</span></span> <span data-ttu-id="1bf44-117">Соединитатель определяет, в какой почтовый ящик импортировать элементы, используя значение свойства *Email.*</span><span class="sxs-lookup"><span data-stu-id="1bf44-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="1bf44-118">Каждый элемент Подключение chat содержит это свойство, которое заполняется адресом электронной почты каждого участника.</span><span class="sxs-lookup"><span data-stu-id="1bf44-118">Every ICE Connect Chat item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="1bf44-119">Перед настройками соединитетеля</span><span class="sxs-lookup"><span data-stu-id="1bf44-119">Before you set up a connector</span></span>

- <span data-ttu-id="1bf44-120">Создайте учетную запись DataParser для соединители Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1bf44-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="1bf44-121">Для этого обратитесь в [ООО "17a-4".](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="1bf44-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="1bf44-122">При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="1bf44-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="1bf44-123">Пользователь, создававший соединиттель ICE DataParser в шаге 1 (и завершавший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1bf44-123">The user who creates the ICE DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="1bf44-124">Эта роль требуется для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bf44-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1bf44-125">По умолчанию эта роль не назначена группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1bf44-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="1bf44-126">Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1bf44-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="1bf44-127">Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="1bf44-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="1bf44-128">Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="1bf44-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-ice-dataparser-connector"></a><span data-ttu-id="1bf44-129">Шаг 1. Настройка соединиттеля ICE DataParser</span><span class="sxs-lookup"><span data-stu-id="1bf44-129">Step 1: Set up an ICE DataParser connector</span></span>

<span data-ttu-id="1bf44-130">Первым шагом является доступ к странице соединители данных в Центр соответствия требованиям Microsoft 365 и создание соединителя 17a-4 для данных Подключение чата.</span><span class="sxs-lookup"><span data-stu-id="1bf44-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for ICE Connect Chat data.</span></span>

1. <span data-ttu-id="1bf44-131">Перейдите <https://compliance.microsoft.com> к и нажмите **соединители**  >  **данных ICE DataParser**.</span><span class="sxs-lookup"><span data-stu-id="1bf44-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **ICE DataParser**.</span></span>

2. <span data-ttu-id="1bf44-132">На странице **описания продукта ICE DataParser** нажмите **кнопку Добавить соединителю**.</span><span class="sxs-lookup"><span data-stu-id="1bf44-132">On the **ICE DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="1bf44-133">На странице **Условия службы нажмите** кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="1bf44-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="1bf44-134">Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="1bf44-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="1bf44-135">Вопишите в свою учетную запись 17a-4 и выполните действия мастера подключения ICE DataParser.</span><span class="sxs-lookup"><span data-stu-id="1bf44-135">Sign in to your 17a-4 account and complete the steps in the ICE DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-ice-dataparser-connector"></a><span data-ttu-id="1bf44-136">Шаг 2. Настройка соединиттеля ICE DataParser</span><span class="sxs-lookup"><span data-stu-id="1bf44-136">Step 2: Configure the ICE DataParser connector</span></span>

<span data-ttu-id="1bf44-137">Работа с поддержкой 17a-4 для настройки соединителя ICE DataParser.</span><span class="sxs-lookup"><span data-stu-id="1bf44-137">Work with 17a-4 Support to configure the ICE DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="1bf44-138">Шаг 3. Пользователи карт</span><span class="sxs-lookup"><span data-stu-id="1bf44-138">Step 3: Map users</span></span>

<span data-ttu-id="1bf44-139">Соединителю ICE DataParser перед импортом данных в Microsoft 365 будут автоматически соединять пользователей с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bf44-139">The ICE DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-ice-dataparser-connector"></a><span data-ttu-id="1bf44-140">Шаг 4. Мониторинг соединиттеля ICE DataParser</span><span class="sxs-lookup"><span data-stu-id="1bf44-140">Step 4: Monitor the ICE DataParser connector</span></span>

<span data-ttu-id="1bf44-141">После создания соединиттеля ICE DataParser можно просмотреть состояние соединитетеля в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bf44-141">After you create an ICE DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="1bf44-142">Перейдите <https://compliance.microsoft.com> и щелкните **соединители данных** в левом nav.</span><span class="sxs-lookup"><span data-stu-id="1bf44-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="1bf44-143">Щелкните  вкладку Соединители, а затем выберите разъем ICE DataParser, созданный для отображения страницы вылетов, которая содержит свойства и сведения о соединителе.</span><span class="sxs-lookup"><span data-stu-id="1bf44-143">Click the **Connectors** tab and then select the ICE DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="1bf44-144">В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="1bf44-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="1bf44-145">В этом журнале содержатся данные, импортируемые в облако Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1bf44-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="1bf44-146">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="1bf44-146">Known issues</span></span>

<span data-ttu-id="1bf44-147">В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="1bf44-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="1bf44-148">Поддержка более крупных элементов будет доступна позднее.</span><span class="sxs-lookup"><span data-stu-id="1bf44-148">Support for larger items will be available at a later date.</span></span>
