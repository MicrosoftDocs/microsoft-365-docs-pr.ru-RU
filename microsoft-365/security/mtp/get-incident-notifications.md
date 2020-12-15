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
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668319"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="46567-104">Получать уведомления об инциденте по электронной почте</span><span class="sxs-lookup"><span data-stu-id="46567-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> <span data-ttu-id="46567-105">Уведомления по электронной почте об инцидентах в настоящее время находятся в режиме предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="46567-105">The email notifications for incidents feature is currently in public preview.</span></span> <span data-ttu-id="46567-106">Некоторые сведения об этой функции могут измениться до коммерческой доступности.</span><span class="sxs-lookup"><span data-stu-id="46567-106">Some information about this feature may change before commercial availability.</span></span> <span data-ttu-id="46567-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="46567-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="46567-108">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="46567-108">**Applies to:**</span></span>
- <span data-ttu-id="46567-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46567-109">Microsoft 365 Defender</span></span>

<span data-ttu-id="46567-110">Вы можете настроить Microsoft 365 Defender так, чтобы он уведомлял вас по электронной почте каждый раз, когда имеются новые инциденты или новые обновления существующих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="46567-110">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="46567-111">Вы можете получать уведомления по степени серьезности инцидента или по группе устройств.</span><span class="sxs-lookup"><span data-stu-id="46567-111">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="46567-112">Вы также можете получать уведомление только при первом обновлении для каждого инцидента.</span><span class="sxs-lookup"><span data-stu-id="46567-112">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="46567-113">Вы можете добавлять или удалять получателей в уведомлениях по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="46567-113">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="46567-114">Добавленные получатели получают уведомления об инцидентах после их добавления.</span><span class="sxs-lookup"><span data-stu-id="46567-114">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="46567-115">Уведомление по электронной почте содержит важные сведения об инциденте, например имя, серьезность и категории инцидента.</span><span class="sxs-lookup"><span data-stu-id="46567-115">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="46567-116">Вы также можете напрямую перейти к инцидентам, чтобы сразу начать исследование.</span><span class="sxs-lookup"><span data-stu-id="46567-116">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="46567-117">Дополнительные узнать об исследованиях инцидентов см. в этой [теме.](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)</span><span class="sxs-lookup"><span data-stu-id="46567-117">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="46567-118">Для настройки параметров уведомлений по электронной почте необходимы разрешения "Управление настройками безопасности".</span><span class="sxs-lookup"><span data-stu-id="46567-118">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="46567-119">Если вы решили использовать базовое управление разрешениями, пользователи с ролями администратора безопасности или глобального администратора могут настраивать уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="46567-119">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="46567-120">Аналогично, если в организации используется управление доступом на основе ролей (RBAC), можно создавать, редактировать, удалять и получать уведомления только на основе групп устройств, которые разрешено управлять.</span><span class="sxs-lookup"><span data-stu-id="46567-120">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="46567-121">Создание правил для уведомлений об инциденте</span><span class="sxs-lookup"><span data-stu-id="46567-121">Create rules for incident notifications</span></span>

<span data-ttu-id="46567-122">Чтобы настроить первое уведомление по электронной почте об инцидентах, создайте новое правило и настройте параметры уведомлений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="46567-122">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="46567-123">В области навигации выберите **"Параметры"** уведомления по электронной почте об  >  **инциденте.**</span><span class="sxs-lookup"><span data-stu-id="46567-123">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="46567-124">Выберите **"Добавить элемент"**.</span><span class="sxs-lookup"><span data-stu-id="46567-124">Select **Add item**.</span></span>
3. <span data-ttu-id="46567-125">Придать правилу имя в **имени** и в качестве **описания.**</span><span class="sxs-lookup"><span data-stu-id="46567-125">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Создание окна правила для сообщений электронной почты об инциденте](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="46567-127">Выберите **"Далее",** чтобы **перейти к параметрам уведомлений.**</span><span class="sxs-lookup"><span data-stu-id="46567-127">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="46567-128">Здесь можно указать:</span><span class="sxs-lookup"><span data-stu-id="46567-128">Here you can specify:</span></span>
    - <span data-ttu-id="46567-129">**Серьезность оповещения:** выберите степень серьезности оповещения, которая вызывает уведомление об инциденте.</span><span class="sxs-lookup"><span data-stu-id="46567-129">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="46567-130">Например, если вы хотите получить только информацию об инцидентах с высокой степенью серьезности, выберите "Высокий".</span><span class="sxs-lookup"><span data-stu-id="46567-130">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="46567-131">**Область группы устройств** — в этом выпадающее поле отображаются все группы устройств, к которые пользователь может получить доступ.</span><span class="sxs-lookup"><span data-stu-id="46567-131">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="46567-132">Выберите группы устройств, для которых вы создаете правила уведомлений об инциденте.</span><span class="sxs-lookup"><span data-stu-id="46567-132">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="46567-133">**Уведомлять только о первом** возникновении инцидента . При выборе этого параметра уведомление по электронной почте отправляется только при первом оповещении, которое соответствует другим выбранным вариантам.</span><span class="sxs-lookup"><span data-stu-id="46567-133">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="46567-134">Последующие обновления или оповещения, связанные с инцидентом, не инициирует уведомление.</span><span class="sxs-lookup"><span data-stu-id="46567-134">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="46567-135">**Включайте название** организации — указывает, отображается ли имя клиента в уведомлении по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="46567-135">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="46567-136">**Включит ссылку на портал** для определенного клиента. Добавляет ссылку с ИД клиента, чтобы разрешить доступ к определенному арендатору.</span><span class="sxs-lookup"><span data-stu-id="46567-136">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Окно параметров нотифиции сообщений электронной почты об инциденте](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="46567-138">Выберите **"Далее",** чтобы перейти **к разделу "Получатели".**</span><span class="sxs-lookup"><span data-stu-id="46567-138">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="46567-139">Здесь можно указать адреса электронной почты, которые будут получать уведомления по электронной почте об инциденте.</span><span class="sxs-lookup"><span data-stu-id="46567-139">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="46567-140">Выберите **"Добавить получателя" после** ввода каждого адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="46567-140">Select **Add a recipient** after typing every email address.</span></span>

    ![Окно добавления получателей для сообщений электронной почты об инциденте](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="46567-142">Наконец, выберите **"Далее",** чтобы перейти **к** правилу проверки, чтобы просмотреть все параметры, связанные с новым правилом.</span><span class="sxs-lookup"><span data-stu-id="46567-142">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="46567-143">Получатели начнут получать уведомления об инциденте по электронной почте в зависимости от параметров.</span><span class="sxs-lookup"><span data-stu-id="46567-143">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="46567-144">См. также</span><span class="sxs-lookup"><span data-stu-id="46567-144">See also</span></span>
- [<span data-ttu-id="46567-145">Обзор инцидентов в Защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46567-145">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="46567-146">Расставить приоритеты инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46567-146">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="46567-147">Исследование инцидентов в Защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46567-147">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

