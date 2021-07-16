---
title: Настройка соединитетеля для архива данных FactSet в Microsoft 365
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
description: Узнайте, как настроить и использовать соединителя dataParser 17a-4 FactSet для импорта и архива данных FactSet в Microsoft 365.
ms.openlocfilehash: 26beead657618dc3b33a11d8b6202c914a9c49bc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454521"
---
# <a name="set-up-a-connector-to-archive-factset-data"></a><span data-ttu-id="a3a92-103">Настройка соединитетеля для архива данных FactSet</span><span class="sxs-lookup"><span data-stu-id="a3a92-103">Set up a connector to archive FactSet data</span></span>

<span data-ttu-id="a3a92-104">Используйте [DataParser FactSet](https://www.17a-4.com/factset-dataparser/) из 17a-4 LLC для импорта и архива данных с платформы FactSet в почтовые ящики пользователей в Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="a3a92-104">Use the [FactSet DataParser](https://www.17a-4.com/factset-dataparser/) from 17a-4 LLC to import and archive data from the FactSet platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="a3a92-105">В dataParser включен соединиттель FactSet, настроенный для захвата элементов из стороннего источника данных и импорта этих элементов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3a92-105">The DataParser includes a FactSet connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="a3a92-106">Соединиттель FactSet DataParser преобразует данные FactSet в формат сообщений электронной почты, а затем импортирует эти элементы в почтовые ящики пользователей в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3a92-106">The FactSet DataParser connector converts FactSet data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="a3a92-107">После хранения данных FactSet в почтовых ящиках пользователей можно применить Microsoft 365, такие как хранение судебного разбирательства, электронные сведения, политики хранения и метки хранения, а также соответствие требованиям связи.</span><span class="sxs-lookup"><span data-stu-id="a3a92-107">After FactSet data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="a3a92-108">Использование соединиттеля FactSet для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.</span><span class="sxs-lookup"><span data-stu-id="a3a92-108">Using a FactSet connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-factset-data"></a><span data-ttu-id="a3a92-109">Обзор архива данных FactSet</span><span class="sxs-lookup"><span data-stu-id="a3a92-109">Overview of archiving FactSet data</span></span>

<span data-ttu-id="a3a92-110">В следующем обзоре объясняется процесс использования соединиттеля данных для архивации данных FactSet в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3a92-110">The following overview explains the process of using a data connector to archive FactSet data in Microsoft 365.</span></span>

![Процесс архива данных FactSet с 17a-4](../media/FactSetDataParserConnectorWorkflow.png)

1. <span data-ttu-id="a3a92-112">Ваша организация работает с 17a-4 для настройки и настройки dataParser FactSet.</span><span class="sxs-lookup"><span data-stu-id="a3a92-112">Your organization works with 17a-4 to set up and configure the FactSet DataParser.</span></span>

2. <span data-ttu-id="a3a92-113">Регулярно элементы FactSet собираются в DataParser.</span><span class="sxs-lookup"><span data-stu-id="a3a92-113">On a regular basis, FactSet items are collected by the DataParser.</span></span> <span data-ttu-id="a3a92-114">DataParser также преобразует содержимое сообщения в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a3a92-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="a3a92-115">Соединитетель DataParser FactSet, который вы создаете в Центр соответствия требованиям Microsoft 365, подключается к DataParser и передает сообщения в безопасное служба хранилища Azure в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3a92-115">The FactSet DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="a3a92-116">В почтовых ящиках пользователей создается подмножество в папке "Входящие" с именем **FactSet DataParser,** и элементы FactSet импортируется в эту папку.</span><span class="sxs-lookup"><span data-stu-id="a3a92-116">A subfolder in the Inbox folder named **FactSet DataParser** is created in the user mailboxes, and the FactSet items are imported to that folder.</span></span> <span data-ttu-id="a3a92-117">Соединитатель определяет, в какой почтовый ящик импортировать элементы, используя значение свойства *Email.*</span><span class="sxs-lookup"><span data-stu-id="a3a92-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="a3a92-118">Каждый элемент FactSet содержит это свойство, которое заполняется адресом электронной почты каждого участника.</span><span class="sxs-lookup"><span data-stu-id="a3a92-118">Every FactSet item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="a3a92-119">Перед настройками соединитетеля</span><span class="sxs-lookup"><span data-stu-id="a3a92-119">Before you set up a connector</span></span>

- <span data-ttu-id="a3a92-120">Создайте учетную запись DataParser для соединители Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3a92-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="a3a92-121">Для этого обратитесь в [ООО "17a-4".](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="a3a92-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="a3a92-122">При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="a3a92-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="a3a92-123">Пользователь, создававший соединиттель FactSet DataParser в шаге 1 (и завершавший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3a92-123">The user who creates the FactSet DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a3a92-124">Эта роль требуется для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3a92-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a3a92-125">По умолчанию эта роль не назначена группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3a92-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="a3a92-126">Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3a92-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a3a92-127">Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="a3a92-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a3a92-128">Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="a3a92-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-factset-dataparser-connector"></a><span data-ttu-id="a3a92-129">Шаг 1. Настройка соединиттеля DataParser FactSet</span><span class="sxs-lookup"><span data-stu-id="a3a92-129">Step 1: Set up a FactSet DataParser connector</span></span>

<span data-ttu-id="a3a92-130">Первым шагом является доступ к странице соединители данных в Центр соответствия требованиям Microsoft 365 и создание соединителя 17a-4 для данных FactSet.</span><span class="sxs-lookup"><span data-stu-id="a3a92-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for FactSet data.</span></span>

1. <span data-ttu-id="a3a92-131">Перейдите <https://compliance.microsoft.com> и нажмите **кнопку Соединители данных**  >  **FactSet DataParser**.</span><span class="sxs-lookup"><span data-stu-id="a3a92-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **FactSet DataParser**.</span></span>

2. <span data-ttu-id="a3a92-132">На странице **описания продукта FactSet DataParser** нажмите **кнопку Добавить соединителю**.</span><span class="sxs-lookup"><span data-stu-id="a3a92-132">On the **FactSet DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="a3a92-133">На странице **Условия службы нажмите** кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="a3a92-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="a3a92-134">Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="a3a92-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="a3a92-135">Вопишите в свою учетную запись 17a-4 и выполните действия мастера подключения FactSet DataParser.</span><span class="sxs-lookup"><span data-stu-id="a3a92-135">Sign in to your 17a-4 account and complete the steps in the FactSet DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-factset-dataparser-connector"></a><span data-ttu-id="a3a92-136">Шаг 2. Настройка соединиттеля DataParser FactSet</span><span class="sxs-lookup"><span data-stu-id="a3a92-136">Step 2: Configure the FactSet DataParser connector</span></span>

<span data-ttu-id="a3a92-137">Работа с поддержкой 17a-4 для настройки соединителя DataParser FactSet.</span><span class="sxs-lookup"><span data-stu-id="a3a92-137">Work with 17a-4 Support to configure the FactSet DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="a3a92-138">Шаг 3. Пользователи карт</span><span class="sxs-lookup"><span data-stu-id="a3a92-138">Step 3: Map users</span></span>

<span data-ttu-id="a3a92-139">Соединиттель FactSet DataParser автоматически соединит пользователей с их Microsoft 365 адресами электронной почты перед импортом данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3a92-139">The FactSet DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-factset-dataparser-connector"></a><span data-ttu-id="a3a92-140">Шаг 4. Мониторинг соединиттеля DataParser FactSet</span><span class="sxs-lookup"><span data-stu-id="a3a92-140">Step 4: Monitor the FactSet DataParser connector</span></span>

<span data-ttu-id="a3a92-141">После создания соединиттеля DataParser FactSet можно просмотреть состояние соединитетеля в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3a92-141">After you create a FactSet DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="a3a92-142">Перейдите <https://compliance.microsoft.com> и щелкните **соединители данных** в левом nav.</span><span class="sxs-lookup"><span data-stu-id="a3a92-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a3a92-143">Щелкните  вкладку Соединители, а затем выберите соединиттель FactSet DataParser, созданный для отображения страницы вылетов, которая содержит свойства и сведения о соединителе.</span><span class="sxs-lookup"><span data-stu-id="a3a92-143">Click the **Connectors** tab and then select the FactSet DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="a3a92-144">В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="a3a92-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="a3a92-145">В этом журнале содержатся данные, импортируемые в облако Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3a92-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a3a92-146">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3a92-146">Known issues</span></span>

<span data-ttu-id="a3a92-147">В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="a3a92-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="a3a92-148">Поддержка более крупных элементов будет доступна позднее.</span><span class="sxs-lookup"><span data-stu-id="a3a92-148">Support for larger items will be available at a later date.</span></span>
