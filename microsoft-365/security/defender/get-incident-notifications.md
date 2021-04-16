---
title: Получать уведомления об инцидентах в Microsoft 365 Defender
description: Узнайте, как создать правила получения уведомлений электронной почты об инцидентах в Microsoft 365 Defender
keywords: incident, email, email notfications, configure, users, mailbox, email, incidents
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 72a1f8fe71efcfa7f4f73671611576a454b508e6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861321"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="60b14-104">Получать уведомления об инцидентах по электронной почте</span><span class="sxs-lookup"><span data-stu-id="60b14-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="60b14-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="60b14-105">**Applies to:**</span></span>
- <span data-ttu-id="60b14-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60b14-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="60b14-107">Вы можете настроить Microsoft 365 Defender, чтобы уведомить сотрудников по электронной почте о новых инцидентах или обновлениях существующих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="60b14-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="60b14-108">Вы можете выбрать для получения уведомлений на основе:</span><span class="sxs-lookup"><span data-stu-id="60b14-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="60b14-109">Серьезность инцидента.</span><span class="sxs-lookup"><span data-stu-id="60b14-109">Incident severity.</span></span>
- <span data-ttu-id="60b14-110">Группа устройств.</span><span class="sxs-lookup"><span data-stu-id="60b14-110">Device group.</span></span>
- <span data-ttu-id="60b14-111">Только при первом обновлении за один инцидент.</span><span class="sxs-lookup"><span data-stu-id="60b14-111">Only on the first update per incident.</span></span>

<span data-ttu-id="60b14-112">Уведомление электронной почты содержит важные сведения об инциденте, такие как имя инцидента, серьезность и категории, в частности.</span><span class="sxs-lookup"><span data-stu-id="60b14-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="60b14-113">Вы также можете перейти непосредственно к инциденту и сразу же начать расследование.</span><span class="sxs-lookup"><span data-stu-id="60b14-113">You can also go directly to the incident and start your investigation right away.</span></span> <span data-ttu-id="60b14-114">Дополнительные сведения см. в [дополнительных сведениях.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="60b14-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="60b14-115">Вы можете добавить или удалить получателей в уведомлениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="60b14-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="60b14-116">Новые получатели получают уведомления об инцидентах после их добавления.</span><span class="sxs-lookup"><span data-stu-id="60b14-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="60b14-117">Для настройки параметров уведомлений электронной почты необходимо разрешение "Управление настройками параметров безопасности".</span><span class="sxs-lookup"><span data-stu-id="60b14-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="60b14-118">Если вы решили использовать управление базовыми разрешениями, пользователи с ролями администратора безопасности или глобального администратора могут настроить уведомления электронной почты для вас.</span><span class="sxs-lookup"><span data-stu-id="60b14-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="60b14-119">Кроме того, если ваша организация использует управление доступом на основе ролей (RBAC), можно создавать, изменять, удалять и получать уведомления на основе групп устройств, которые разрешены для управления.</span><span class="sxs-lookup"><span data-stu-id="60b14-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="60b14-120">Создание правила для уведомлений электронной почты</span><span class="sxs-lookup"><span data-stu-id="60b14-120">Create a rule for email notifications</span></span>

<span data-ttu-id="60b14-121">Выполните следующие действия, чтобы создать новое правило и настроить параметры уведомлений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="60b14-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="60b14-122">В области навигации выберите **параметры > microsoft 365 Defender > сообщений** электронной почты.</span><span class="sxs-lookup"><span data-stu-id="60b14-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="60b14-123">Выберите **элемент Добавить**.</span><span class="sxs-lookup"><span data-stu-id="60b14-123">Select **Add item**.</span></span>
3. <span data-ttu-id="60b14-124">На странице **Basics** введите имя правила и описание, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60b14-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="60b14-125">На странице **Параметры уведомлений** настройте:</span><span class="sxs-lookup"><span data-stu-id="60b14-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="60b14-126">**Предупреждение серьезности** . Выберите серьезность оповещения, которая вызовет уведомление об инциденте.</span><span class="sxs-lookup"><span data-stu-id="60b14-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="60b14-127">Например, если вы хотите быть информированы только об инцидентах с высокой степенью серьезности, выберите **High**.</span><span class="sxs-lookup"><span data-stu-id="60b14-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="60b14-128">**Область группы устройств** — вы можете указать все группы устройств или выбрать из списка групп устройств в клиенте.</span><span class="sxs-lookup"><span data-stu-id="60b14-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="60b14-129">**Только уведомить о первом** возникновении каждого инцидента . Выберите, если вы хотите уведомление только в первом оповещении, которое соответствует другим выборам.</span><span class="sxs-lookup"><span data-stu-id="60b14-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="60b14-130">Последующие обновления или оповещения, связанные с инцидентом, не будут отправлять дополнительные уведомления.</span><span class="sxs-lookup"><span data-stu-id="60b14-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="60b14-131">**Включите имя организации в сообщение электронной** почты . Выберите, если вы хотите, чтобы имя организации было отображаться в уведомлении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="60b14-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="60b14-132">**Включайте** ссылку портала, определенной для клиента. Выберите, если вы хотите добавить ссылку с ИД клиента в уведомлении электронной почты для доступа к конкретному клиенту Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60b14-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Параметры уведомлений об инцидентах для уведомлений электронной почты об инциденте":::

5. <span data-ttu-id="60b14-134">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60b14-134">Select **Next**.</span></span> <span data-ttu-id="60b14-135">На странице **Получатели добавьте** адреса электронной почты, которые будут получать уведомления об инциденте.</span><span class="sxs-lookup"><span data-stu-id="60b14-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="60b14-136">Выберите **Добавить** после ввода каждого нового адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="60b14-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="60b14-137">Чтобы проверить уведомления и убедиться, что получатели получают их в почтовых ящиках, выберите **отправить тестовую электронную почту.**</span><span class="sxs-lookup"><span data-stu-id="60b14-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="60b14-138">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60b14-138">Select **Next**.</span></span> <span data-ttu-id="60b14-139">На странице **Правила обзора** просмотрите параметры правила и выберите **правило Create**.</span><span class="sxs-lookup"><span data-stu-id="60b14-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="60b14-140">Получатели начнут получать уведомления об инцидентах по электронной почте в зависимости от параметров.</span><span class="sxs-lookup"><span data-stu-id="60b14-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="60b14-141">Чтобы изменить существующее правило, выберите его из списка правил.</span><span class="sxs-lookup"><span data-stu-id="60b14-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="60b14-142">На области с именем правила выберите правило **Изменить** и внести изменения на страницах **Basics,** **Notification и** **Recipients.**</span><span class="sxs-lookup"><span data-stu-id="60b14-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="60b14-143">Чтобы изменить существующее правило, выберите его из списка правил.</span><span class="sxs-lookup"><span data-stu-id="60b14-143">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="60b14-144">На области с именем правила выберите **Удаление**.</span><span class="sxs-lookup"><span data-stu-id="60b14-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="60b14-145">См. также</span><span class="sxs-lookup"><span data-stu-id="60b14-145">See also</span></span>
- [<span data-ttu-id="60b14-146">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="60b14-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="60b14-147">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="60b14-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="60b14-148">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="60b14-148">Investigate incidents</span></span>](investigate-incidents.md)
