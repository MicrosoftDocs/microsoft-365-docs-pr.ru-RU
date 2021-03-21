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
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
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
ms.openlocfilehash: c6b255f7815a5b49cd0fb5ed27da0cf642ff2ca7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928836"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="c70be-104">Получать уведомления об инцидентах по электронной почте</span><span class="sxs-lookup"><span data-stu-id="c70be-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c70be-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c70be-105">**Applies to:**</span></span>
- <span data-ttu-id="c70be-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c70be-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c70be-107">Вы можете настроить Microsoft 365 Defender, чтобы уведомлять вас по электронной почте при каждом новом инциденте или обновлении существующих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="c70be-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="c70be-108">Вы можете получать уведомления в зависимости от серьезности инцидентов или группы устройств.</span><span class="sxs-lookup"><span data-stu-id="c70be-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="c70be-109">Вы также можете получить уведомление только при первом обновлении за один инцидент.</span><span class="sxs-lookup"><span data-stu-id="c70be-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="c70be-110">Вы можете добавить или удалить получателей в уведомлениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c70be-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="c70be-111">Вновь добавленные получатели получают уведомления об инцидентах после их добавлений.</span><span class="sxs-lookup"><span data-stu-id="c70be-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="c70be-112">Уведомление электронной почты содержит важные сведения об инциденте, такие как имя инцидента, серьезность и категории, в частности.</span><span class="sxs-lookup"><span data-stu-id="c70be-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="c70be-113">Вы также можете напрямую перейти к инцидентам, чтобы можно было сразу приступить к расследованию.</span><span class="sxs-lookup"><span data-stu-id="c70be-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="c70be-114">Дополнительные новости о расследовании инцидентов см. в см. в сайте [Investigate incidents in Microsoft 365 Defender.](./investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="c70be-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](./investigate-incidents.md).</span></span>

>[!NOTE]
><span data-ttu-id="c70be-115">Для настройки параметров уведомлений электронной почты необходимы разрешения "Управление настройками параметров безопасности".</span><span class="sxs-lookup"><span data-stu-id="c70be-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="c70be-116">Если вы решили использовать управление базовыми разрешениями, пользователи с ролями администратора безопасности или глобального администратора могут настроить уведомления электронной почты для вас.</span><span class="sxs-lookup"><span data-stu-id="c70be-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="c70be-117">Кроме того, если ваша организация использует управление доступом на основе ролей (RBAC), можно создавать, изменять, удалять и получать уведомления на основе групп устройств, которые разрешены для управления.</span><span class="sxs-lookup"><span data-stu-id="c70be-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="c70be-118">Создание правил для уведомлений об инцидентах</span><span class="sxs-lookup"><span data-stu-id="c70be-118">Create rules for incident notifications</span></span>

<span data-ttu-id="c70be-119">Чтобы настроить первое уведомление по электронной почте для инцидентов, создайте новое правило и настройте параметры уведомлений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c70be-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="c70be-120">В области навигации выберите **уведомления электронной** почты Settings  >  **Incident**.</span><span class="sxs-lookup"><span data-stu-id="c70be-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="c70be-121">Выберите **элемент Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c70be-121">Select **Add item**.</span></span>
3. <span data-ttu-id="c70be-122">Дайте правилу имя **в Name** и предоставляем **описание.**</span><span class="sxs-lookup"><span data-stu-id="c70be-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Создание окна правил для сообщений электронной почты об инцидентах](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="c70be-124">Выберите **Далее,** чтобы перейти **к настройкам уведомлений.**</span><span class="sxs-lookup"><span data-stu-id="c70be-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="c70be-125">Здесь можно указать:</span><span class="sxs-lookup"><span data-stu-id="c70be-125">Here you can specify:</span></span>
    - <span data-ttu-id="c70be-126">**Предупреждение серьезности** . Выберите серьезность оповещения, которая вызовет уведомление об инциденте.</span><span class="sxs-lookup"><span data-stu-id="c70be-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="c70be-127">Например, если вы хотите быть информированы только о инцидентах с высокой степенью серьезности, выберите High.</span><span class="sxs-lookup"><span data-stu-id="c70be-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="c70be-128">**Область группы устройств** . В этом отсеве отображаются все группы устройств, к которые пользователь может получить доступ.</span><span class="sxs-lookup"><span data-stu-id="c70be-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="c70be-129">Выберите группы устройств, для которых вы создаете правила уведомления об инцидентах.</span><span class="sxs-lookup"><span data-stu-id="c70be-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="c70be-130">**Только уведомить о первом** возникновении каждого инцидента . Выбор этого параметра будет отправлять уведомление по электронной почте только в первом оповещении, которое совпадает с другими выборами.</span><span class="sxs-lookup"><span data-stu-id="c70be-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="c70be-131">Последующие обновления или оповещения, связанные с инцидентом, не вызывают уведомления.</span><span class="sxs-lookup"><span data-stu-id="c70be-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="c70be-132">**Включайте имя** организации — указывает, отображается ли имя клиента в уведомлении электронной почты или нет.</span><span class="sxs-lookup"><span data-stu-id="c70be-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="c70be-133">**Включи ссылку портала** для клиента . Добавляет ссылку с ИД клиента, чтобы разрешить доступ к конкретному клиенту.</span><span class="sxs-lookup"><span data-stu-id="c70be-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Notif settings window for incident email notifs](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="c70be-135">Выберите **Далее,** чтобы перейти **к разделу Получатели.**</span><span class="sxs-lookup"><span data-stu-id="c70be-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="c70be-136">Здесь можно указать адреса электронной почты, которые будут получать уведомления об инциденте.</span><span class="sxs-lookup"><span data-stu-id="c70be-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="c70be-137">Выберите **Добавить получателя после** ввода каждого адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c70be-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Добавление окна получателей для сообщений электронной почты об инцидентах](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="c70be-139">Наконец, выберите **Далее,** чтобы перейти к **правилу Обзор,** чтобы просмотреть все параметры, связанные с новым правилом.</span><span class="sxs-lookup"><span data-stu-id="c70be-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="c70be-140">Получатели начнут получать уведомления об инцидентах по электронной почте в зависимости от параметров.</span><span class="sxs-lookup"><span data-stu-id="c70be-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="c70be-141">См. также</span><span class="sxs-lookup"><span data-stu-id="c70be-141">See also</span></span>
- [<span data-ttu-id="c70be-142">Обзор инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c70be-142">Incidents overview in Microsoft 365 Defender</span></span>](./incidents-overview.md)
- [<span data-ttu-id="c70be-143">Приоритеты инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c70be-143">Prioritize incidents in Microsoft 365 Defender</span></span>](./incident-queue.md)
- [<span data-ttu-id="c70be-144">Расследование инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c70be-144">Investigate incidents in Microsoft 365 Defender</span></span>](./investigate-incidents.md)