---
title: Настройка соединитетеля для архива данных связи Telegram в Microsoft 365
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
description: Администраторы могут настроить соединители TeleMessage для импорта и архива данных связи Telegram в Microsoft 365. Это позволяет архивировать данные из сторонних источников данных в Microsoft 365, чтобы управлять сторонними данными с помощью функций соответствия требованиям, таких как юридические удержания, поиск контента и политики хранения.
ms.openlocfilehash: d3fbe02dce56bec01d66351aa69500a3d5d93a37
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054883"
---
# <a name="set-up-a-connector-to-archive-telegram-communications-data-preview"></a><span data-ttu-id="5de83-104">Настройка соединитетеля для архива данных связи Telegram (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="5de83-104">Set up a connector to archive Telegram communications data (preview)</span></span>

<span data-ttu-id="5de83-105">Используйте соединители TeleMessage в Центр соответствия требованиям Microsoft 365 для импорта и архива чатов, вложений, файлов и удаленных сообщений и вызовов.</span><span class="sxs-lookup"><span data-stu-id="5de83-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive Telegram chats, attachments, files, and deleted messages and calls.</span></span> <span data-ttu-id="5de83-106">После настройки соединители он подключается к учетной записи TeleMessage вашей организации и импортирует мобильную связь сотрудников с помощью архива Telegram в почтовые ящики в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5de83-106">After you set up and configure a connector, it connects to your organization's TeleMessage account, and imports the mobile communication of employees using the Telegram Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="5de83-107">После хранения данных соединиттеля архива Telegram в почтовых ящиках пользователей к данным связи Telegram можно применить Microsoft 365 таких функций соответствия требованиям, как хранение судебного разбирательства, поиск контента и Microsoft 365 хранения.</span><span class="sxs-lookup"><span data-stu-id="5de83-107">After Telegram Archiver connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content search, and Microsoft 365 retention policies to Telegram communication data.</span></span> <span data-ttu-id="5de83-108">Например, вы можете искать сообщения Telegram с помощью поиска контента или связывать почтовый ящик, содержащий данные соединителя архива Telegram, с хранителями в Advanced eDiscovery случае.</span><span class="sxs-lookup"><span data-stu-id="5de83-108">For example, you can search Telegram communication using Content Search or associate the mailbox that contains the Telegram Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="5de83-109">Использование соединиттеля архива Telegram для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать правила корпоративного управления и нормативные политики.</span><span class="sxs-lookup"><span data-stu-id="5de83-109">Using a Telegram Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with corporate governance regulations and regulatory policies.</span></span>

## <a name="overview-of-archiving-telegram-communications-data"></a><span data-ttu-id="5de83-110">Обзор архива данных связи Telegram</span><span class="sxs-lookup"><span data-stu-id="5de83-110">Overview of archiving Telegram communications data</span></span>

<span data-ttu-id="5de83-111">В следующем обзоре рассказывается о процессе использования соединитетеля для архивации данных связи Telegram в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5de83-111">The following overview explains the process of using a connector to archive  Telegram communications data in Microsoft 365.</span></span>

![Рабочий процесс архива сообщений Telegram](../media/TelegramConnectorWorkflow.png)

1. <span data-ttu-id="5de83-113">Ваша организация работает с TeleMessage, чтобы настроить соединители архиватора Telegram.</span><span class="sxs-lookup"><span data-stu-id="5de83-113">Your organization works with TeleMessage to set up a Telegram Archiver connector.</span></span> <span data-ttu-id="5de83-114">Дополнительные сведения см. в [странице Активация архива teleMessage Telegram для Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/).</span><span class="sxs-lookup"><span data-stu-id="5de83-114">For more information, see [Activating the TeleMessage Telegram Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/).</span></span>

2. <span data-ttu-id="5de83-115">В режиме реального времени данные Telegram вашей организации копируется на сайт TeleMessage.</span><span class="sxs-lookup"><span data-stu-id="5de83-115">In real time, your organization's Telegram data is copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="5de83-116">Соединитатель архива Telegram, который вы создаете в Центр соответствия требованиям Microsoft 365 подключается к сайту TeleMessage каждый день и передает сообщения электронной почты из предыдущих 24 часов в безопасную служба хранилища Azure область в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="5de83-116">The Telegram Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

4. <span data-ttu-id="5de83-117">Соединитатель импортирует элементы мобильной связи в почтовый ящик определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="5de83-117">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="5de83-118">В почтовом ящике конкретного пользователя будет создана новая папка с именем Архивер Telegram, в который будут импортироваться элементы.</span><span class="sxs-lookup"><span data-stu-id="5de83-118">A new folder named Telegram Archiver will be created in the specific user's mailbox and the items will be imported to it.</span></span> <span data-ttu-id="5de83-119">Соединитатель делает это сопоставление, используя значение свойства адреса *электронной почты* пользователя.</span><span class="sxs-lookup"><span data-stu-id="5de83-119">The connector does this mapping by using the value of the *User's Email address* property.</span></span> <span data-ttu-id="5de83-120">Каждое сообщение электронной почты содержит это свойство, которое заполняется адресом электронной почты каждого участника сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="5de83-120">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span>

> <span data-ttu-id="5de83-121">Помимо автоматического сопоставления пользователей с  использованием значения свойства адресов электронной почты пользователя, вы также можете определить настраиваемую сопоставление, загрузив файл сопоставления CSV.</span><span class="sxs-lookup"><span data-stu-id="5de83-121">In addition to automatic user mapping using the value of the *User's Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="5de83-122">Этот файл сопоставления должен содержать мобильный номер пользователя и соответствующий Microsoft 365 почтового ящика для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="5de83-122">This mapping file should contain User's mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="5de83-123">Если вы включаете автоматическое сопоставление пользователей и предоставляете настраиваемый сопоставление, для каждого элемента электронной почты соединитатель сначала будет искать настраиваемый файл сопоставления.</span><span class="sxs-lookup"><span data-stu-id="5de83-123">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="5de83-124">Если он не найдет допустимого пользователя Microsoft 365, соответствующего мобильному номеру пользователя, соединиттель будет использовать свойство адресов электронной почты пользователя элемента электронной почты.</span><span class="sxs-lookup"><span data-stu-id="5de83-124">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="5de83-125">Если соединиттель не находит допустимого пользователя Microsoft 365 в настраиваемом  файле сопоставления или свойстве адреса электронной почты элемента электронной почты, элемент не будет импортирован.</span><span class="sxs-lookup"><span data-stu-id="5de83-125">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user's email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="5de83-126">Перед настройками соединитетеля</span><span class="sxs-lookup"><span data-stu-id="5de83-126">Before you set up a connector</span></span>

- <span data-ttu-id="5de83-127">Заказать [службу архивации Telegram в TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) и получить допустимую учетную запись администрирования для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5de83-127">Order the [Telegram archiving service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization.</span></span> <span data-ttu-id="5de83-128">Вам потребуется войти в эту учетную запись при создании соединитетеля в центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5de83-128">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="5de83-129">Регистрация всех пользователей, которые требуют архива Telegram в учетной записи TeleMessage.</span><span class="sxs-lookup"><span data-stu-id="5de83-129">Register all users that require Telegram archiving in the TeleMessage account.</span></span> <span data-ttu-id="5de83-130">При регистрации пользователей обязательно используйте тот же адрес электронной почты, который используется для Microsoft 365 учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5de83-130">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="5de83-131">Установите приложение Архивер Telegram на мобильные телефоны сотрудников и активируйте его.</span><span class="sxs-lookup"><span data-stu-id="5de83-131">Install the Telegram Archiver app on the mobile phones of your employees and activate it.</span></span> <span data-ttu-id="5de83-132">Приложение Архивер Telegram позволяет им общаться и общаться с другими пользователями Telegram.</span><span class="sxs-lookup"><span data-stu-id="5de83-132">The Telegram Archiver app allows them to communicate and chat with other Telegram users.</span></span>

- <span data-ttu-id="5de83-133">Пользователю, создававшего соединители архива Telegram в шаге 3, должна быть назначена роль экспорта импорта почтовых ящиков в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5de83-133">The user who creates a Telegram Archiver connector in Step 3 must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="5de83-134">Это необходимо для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5de83-134">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5de83-135">По умолчанию эта роль не назначена ни одной группе ролей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5de83-135">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="5de83-136">Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5de83-136">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="5de83-137">Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="5de83-137">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="5de83-138">Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="5de83-138">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-telegram-archiver-connector"></a><span data-ttu-id="5de83-139">Создание соединитетеля архива Telegram</span><span class="sxs-lookup"><span data-stu-id="5de83-139">Create a Telegram Archiver connector</span></span>

<span data-ttu-id="5de83-140">После завершения необходимых условий, описанных в предыдущем разделе, можно создать соединители архиватора Telegram в Центр соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5de83-140">After you've completed the prerequisites described in the previous section, you can create the Telegram Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5de83-141">Соединитатель использует сведения, которые вы предоставляете, для подключения к сайту TeleMessage и передачи данных телеграммы в соответствующие ящики почтовых ящиков пользователей в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5de83-141">The connector uses the information you provide to connect to the TeleMessage site and transfers Telegram communications data to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="5de83-142">Перейдите <https://compliance.microsoft.com> к и нажмите **соединителей** данных > T **elegram Archiver**.</span><span class="sxs-lookup"><span data-stu-id="5de83-142">Go to <https://compliance.microsoft.com> and then click **Data connectors** > T **elegram Archiver**.</span></span>

2. <span data-ttu-id="5de83-143">На странице **описания продукта архиватора Telegram** нажмите **кнопку Добавить соединителю**.</span><span class="sxs-lookup"><span data-stu-id="5de83-143">On the **Telegram Archiver** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="5de83-144">На странице **Условия службы нажмите** кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="5de83-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="5de83-145">На странице **Входа в TeleMessage** в шаге 3 введите необходимые сведения в следующих полях и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de83-145">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

    - <span data-ttu-id="5de83-146">**Имя пользователя:** Имя пользователя TeleMessage.</span><span class="sxs-lookup"><span data-stu-id="5de83-146">**Username:** Your TeleMessage username.</span></span>

    - <span data-ttu-id="5de83-147">**Пароль:** Пароль TeleMessage.</span><span class="sxs-lookup"><span data-stu-id="5de83-147">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="5de83-148">После создания соединитетеля можно закрыть всплывающее окно и перейти на следующую страницу.</span><span class="sxs-lookup"><span data-stu-id="5de83-148">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="5de83-149">На странице **Сопоставление пользователей** включаем автоматическое сопоставление пользователей.</span><span class="sxs-lookup"><span data-stu-id="5de83-149">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="5de83-150">Чтобы включить настраиваемую сопоставление, загрузите CSV-файл, содержащий сведения о сопоставлении пользователей, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="5de83-150">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="5de83-151">Просмотрите параметры и нажмите **кнопку Готово** для создания соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="5de83-151">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="5de83-152">Перейдите на вкладку Соединители на странице **Соединители** данных, чтобы увидеть ход процесса импорта для нового соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="5de83-152">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="5de83-153">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="5de83-153">Known issues</span></span>

- <span data-ttu-id="5de83-154">В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="5de83-154">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="5de83-155">Поддержка более крупных элементов будет доступна позднее.</span><span class="sxs-lookup"><span data-stu-id="5de83-155">Support for larger items will be available at a later date.</span></span>