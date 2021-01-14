---
title: Получать уведомления об инцидентах в Microsoft 365 Defender
description: Узнайте, как создавать правила для получения уведомлений по электронной почте об инцидентах в Microsoft 365 Defender
keywords: инцидент, электронная почта, нотации электронной почты, настройка, пользователи, почтовый ящик, электронная почта, инциденты
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848895"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="3e5e7-104">Получать уведомления об инциденте по электронной почте</span><span class="sxs-lookup"><span data-stu-id="3e5e7-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3e5e7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3e5e7-105">**Applies to:**</span></span>
- <span data-ttu-id="3e5e7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3e5e7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3e5e7-107">Вы можете настроить Microsoft 365 Defender так, чтобы он уведомлял вас по электронной почте каждый раз, когда имеются новые инциденты или новые обновления существующих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="3e5e7-108">Вы можете получать уведомления по степени серьезности инцидента или по группе устройств.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="3e5e7-109">Вы также можете получать уведомление только при первом обновлении для каждого инцидента.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="3e5e7-110">Вы можете добавлять или удалять получателей в уведомлениях по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="3e5e7-111">Добавленные получатели получают уведомления об инцидентах после их добавления.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="3e5e7-112">Уведомление по электронной почте содержит важные сведения об инциденте, например имя, серьезность и категории инцидента.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="3e5e7-113">Вы также можете напрямую перейти к инцидентам, чтобы сразу начать исследование.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="3e5e7-114">Подробнее о расследовании инцидентов см. в теме ["Исследование инцидентов в Microsoft 365 Defender".](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)</span><span class="sxs-lookup"><span data-stu-id="3e5e7-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="3e5e7-115">Для настройки параметров уведомлений по электронной почте необходимы разрешения "Управление настройками безопасности".</span><span class="sxs-lookup"><span data-stu-id="3e5e7-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="3e5e7-116">Если вы решили использовать базовое управление разрешениями, пользователи с ролями администратора безопасности или глобального администратора могут настраивать уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="3e5e7-117">Аналогичным образом, если в организации используется управление доступом на основе ролей (RBAC), можно создавать, редактировать, удалять и получать уведомления только на основе групп устройств, которые разрешено управлять.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="3e5e7-118">Создание правил для уведомлений об инцидентах</span><span class="sxs-lookup"><span data-stu-id="3e5e7-118">Create rules for incident notifications</span></span>

<span data-ttu-id="3e5e7-119">Чтобы настроить первое уведомление по электронной почте об инцидентах, создайте новое правило и настройте параметры уведомлений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="3e5e7-120">В области навигации выберите **"Параметры"**  >  **уведомления по электронной почте об инциденте.**</span><span class="sxs-lookup"><span data-stu-id="3e5e7-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="3e5e7-121">Выберите **"Добавить элемент"**.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-121">Select **Add item**.</span></span>
3. <span data-ttu-id="3e5e7-122">Придать правилу имя в **имени** и в качестве **описания.**</span><span class="sxs-lookup"><span data-stu-id="3e5e7-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Создание окна правил для сообщений электронной почты об инциденте](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="3e5e7-124">Выберите **"Далее",** чтобы **перейти к параметрам уведомлений.**</span><span class="sxs-lookup"><span data-stu-id="3e5e7-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="3e5e7-125">Здесь можно указать:</span><span class="sxs-lookup"><span data-stu-id="3e5e7-125">Here you can specify:</span></span>
    - <span data-ttu-id="3e5e7-126">**Серьезность оповещения:** выберите степень серьезности оповещения, которая будет вызывать уведомление об инциденте.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="3e5e7-127">Например, если вы хотите получить только информацию об инцидентах с высокой степенью серьезности, выберите "Высокий".</span><span class="sxs-lookup"><span data-stu-id="3e5e7-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="3e5e7-128">**Область группы устройств** — в этом выпадающее поле отображаются все группы устройств, к которые пользователь может получить доступ.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="3e5e7-129">Выберите группы устройств, для которых вы создаете правила уведомлений об инциденте.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="3e5e7-130">**Уведомлять о первом** возникновении инцидента можно только при выборе этого параметра. При выборе этого параметра уведомление по электронной почте отправляется только при первом оповещении, соответствующем выбранным другим вариантам.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="3e5e7-131">Последующие обновления или оповещения, связанные с инцидентом, не инициирует уведомление.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="3e5e7-132">**Включайте название** организации — указывает, отображается ли имя клиента в уведомлении по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="3e5e7-133">**Включит ссылку на портал** для определенного клиента. Добавляет ссылку с ИД клиента, чтобы разрешить доступ к определенному арендатору.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Окно параметров нотифиции сообщений электронной почты об инциденте](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="3e5e7-135">Выберите **"Далее",** чтобы **перейти к разделу "Получатели".**</span><span class="sxs-lookup"><span data-stu-id="3e5e7-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="3e5e7-136">Здесь можно указать адреса электронной почты, которые будут получать уведомления по электронной почте об инциденте.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="3e5e7-137">Выберите **"Добавить получателя" после** ввода каждого адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Окно добавления получателей для сообщений электронной почты об инциденте](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="3e5e7-139">Наконец, выберите **"Далее",** чтобы перейти **к** правилу проверки, чтобы просмотреть все параметры, связанные с новым правилом.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="3e5e7-140">Получатели начнут получать уведомления об инциденте по электронной почте в зависимости от параметров.</span><span class="sxs-lookup"><span data-stu-id="3e5e7-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e5e7-141">См. также</span><span class="sxs-lookup"><span data-stu-id="3e5e7-141">See also</span></span>
- [<span data-ttu-id="3e5e7-142">Обзор инцидентов в Защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e5e7-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="3e5e7-143">Расставить приоритеты инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3e5e7-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="3e5e7-144">Исследование инцидентов в Защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e5e7-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

