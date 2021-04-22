---
title: Настройка оповещений в Microsoft Defender для конечной точки
description: Вы можете использовать Microsoft Defender для конечной точки для настройки параметров уведомлений электронной почты для оповещений о безопасности в зависимости от серьезности и других критериев.
keywords: уведомления электронной почты, настройка уведомлений оповещений, Microsoft Defender для конечной точки, уведомления Microsoft Defender для конечных точек, оповещения Microsoft Defender для конечных точек, windows 10 корпоративный, windows 10 образования
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c60bed1fb2cc17c9f5dfbd1289ae5f5b5e13faec
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933953"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="98ebf-104">Настройка оповещений в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="98ebf-104">Configure alert notifications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98ebf-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="98ebf-105">**Applies to:**</span></span>
- [<span data-ttu-id="98ebf-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="98ebf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="98ebf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98ebf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="98ebf-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="98ebf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98ebf-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="98ebf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="98ebf-110">Вы можете настроить Defender для конечной точки для отправки уведомлений электронной почты указанным получателям для новых оповещений.</span><span class="sxs-lookup"><span data-stu-id="98ebf-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="98ebf-111">Эта функция позволяет определить группу лиц, которые будут немедленно проинформированы и могут действовать по оповещениям в зависимости от их серьезности.</span><span class="sxs-lookup"><span data-stu-id="98ebf-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="98ebf-112">Настраивать уведомления по электронной почте могут только пользователи с разрешениями "Управление настройками безопасности".</span><span class="sxs-lookup"><span data-stu-id="98ebf-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="98ebf-113">Если вы решили использовать управление базовыми разрешениями, пользователи с ролями администратора безопасности или глобального администратора могут настроить уведомления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="98ebf-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="98ebf-114">Можно установить уровни серьезности оповещений, которые вызывают уведомления.</span><span class="sxs-lookup"><span data-stu-id="98ebf-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="98ebf-115">Вы также можете добавить или удалить получателей уведомления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="98ebf-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="98ebf-116">Новые получатели получают уведомления о срабатывных оповещениях после их добавлений.</span><span class="sxs-lookup"><span data-stu-id="98ebf-116">New recipients get notified about alerts triggered after they're added.</span></span> <span data-ttu-id="98ebf-117">Дополнительные сведения о оповещениях см. в [обзоре и организации очереди оповещений.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="98ebf-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="98ebf-118">Если вы используете управление доступом на основе ролей (RBAC), получатели будут получать уведомления только на основе групп устройств, настроенных в правиле уведомлений.</span><span class="sxs-lookup"><span data-stu-id="98ebf-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="98ebf-119">Пользователи с надлежащим разрешением могут создавать, редактировать или удалять уведомления, ограниченные областью управления группой устройств.</span><span class="sxs-lookup"><span data-stu-id="98ebf-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="98ebf-120">Управлять правилами уведомлений, настроенными для всех групп устройств, могут только пользователи, назначенные роли глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="98ebf-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="98ebf-121">Уведомление электронной почты содержит основные сведения о оповещении и ссылку на портал, на котором можно дополнительно исследовать.</span><span class="sxs-lookup"><span data-stu-id="98ebf-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>


## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="98ebf-122">Создание правил для уведомлений об оповещении</span><span class="sxs-lookup"><span data-stu-id="98ebf-122">Create rules for alert notifications</span></span>
<span data-ttu-id="98ebf-123">Можно создавать правила, определяя серьезности устройств и оповещения для отправки уведомлений электронной почты для получателей и получателей уведомлений.</span><span class="sxs-lookup"><span data-stu-id="98ebf-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="98ebf-124">В области навигации выберите **параметры уведомлений**  >  **электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="98ebf-124">In the navigation pane, select **Settings** > **Email notifications**.</span></span>

2. <span data-ttu-id="98ebf-125">Нажмите **кнопку Добавить элемент**.</span><span class="sxs-lookup"><span data-stu-id="98ebf-125">Click **Add item**.</span></span>

3. <span data-ttu-id="98ebf-126">Укажите общие сведения:</span><span class="sxs-lookup"><span data-stu-id="98ebf-126">Specify the General information:</span></span>
    - <span data-ttu-id="98ebf-127">**Имя правила** . Укажите имя правила уведомлений.</span><span class="sxs-lookup"><span data-stu-id="98ebf-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="98ebf-128">**Включайте имя организации** — укажите имя клиента, которое отображается в уведомлении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="98ebf-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="98ebf-129">**Включи ссылку портала** для клиента . Добавляет ссылку с ИД клиента, чтобы разрешить доступ к конкретному клиенту.</span><span class="sxs-lookup"><span data-stu-id="98ebf-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="98ebf-130">**Включайте сведения об** устройстве . Включает имя устройства в тело оповещения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="98ebf-130">**Include device information** - Includes the device name in the email alert body.</span></span>
    
        >[!NOTE]
        > <span data-ttu-id="98ebf-131">Эти сведения могут обрабатываться почтовыми серверами получателей, которые не имеют географического расположения, выбранного для данных Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="98ebf-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="98ebf-132">**Устройства** — выберите, следует ли уведомлять получателей о оповещениях на всех устройствах (только роли глобального администратора) или на отдельных группах устройств.</span><span class="sxs-lookup"><span data-stu-id="98ebf-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="98ebf-133">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении группами устройств.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="98ebf-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="98ebf-134">**Степень серьезности** оповещений . Выберите уровень серьезности оповещения.</span><span class="sxs-lookup"><span data-stu-id="98ebf-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="98ebf-135">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98ebf-135">Click **Next**.</span></span>
    
5. <span data-ttu-id="98ebf-136">Введите адрес электронной почты получателя и нажмите **кнопку Добавить получателя**.</span><span class="sxs-lookup"><span data-stu-id="98ebf-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="98ebf-137">Вы можете добавить несколько адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="98ebf-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="98ebf-138">Убедитесь, что получатели электронной почты могут получать уведомления электронной почты, выбрав **отправить тестовую электронную почту.**</span><span class="sxs-lookup"><span data-stu-id="98ebf-138">Check that email recipients can receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="98ebf-139">Нажмите **кнопку Сохранить правило уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="98ebf-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="98ebf-140">Изменение правила уведомления</span><span class="sxs-lookup"><span data-stu-id="98ebf-140">Edit a notification rule</span></span>
1. <span data-ttu-id="98ebf-141">Выберите правило уведомлений, необходимое для редактирования.</span><span class="sxs-lookup"><span data-stu-id="98ebf-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="98ebf-142">Обновление сведений о вкладке "Общие" и "Получатель".</span><span class="sxs-lookup"><span data-stu-id="98ebf-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="98ebf-143">Нажмите **кнопку Сохранить правило уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="98ebf-143">Click **Save notification rule**.</span></span>


## <a name="delete-notification-rule"></a><span data-ttu-id="98ebf-144">Правило удаления уведомлений</span><span class="sxs-lookup"><span data-stu-id="98ebf-144">Delete notification rule</span></span>

1. <span data-ttu-id="98ebf-145">Выберите правило уведомления, необходимое для удаления.</span><span class="sxs-lookup"><span data-stu-id="98ebf-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="98ebf-146">Нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="98ebf-146">Click **Delete**.</span></span>


## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="98ebf-147">Устранение неполадок в уведомлениях электронной почты для оповещений</span><span class="sxs-lookup"><span data-stu-id="98ebf-147">Troubleshoot email notifications for alerts</span></span>
<span data-ttu-id="98ebf-148">В этом разделе перечислены различные проблемы, с которыми вы можете столкнуться при использовании уведомлений электронной почты для оповещения.</span><span class="sxs-lookup"><span data-stu-id="98ebf-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="98ebf-149">**Проблема:** Предполагаемые получатели сообщают, что они не получают уведомления.</span><span class="sxs-lookup"><span data-stu-id="98ebf-149">**Problem:** Intended recipients report they're not getting the notifications.</span></span>

<span data-ttu-id="98ebf-150">**Решение:** Убедитесь, что уведомления не заблокированы фильтрами электронной почты:</span><span class="sxs-lookup"><span data-stu-id="98ebf-150">**Solution:** Make sure that the notifications aren't blocked by email filters:</span></span>

1. <span data-ttu-id="98ebf-151">Убедитесь, что уведомления электронной почты Defender для конечной точки не отправляются в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="98ebf-151">Check that the Defender for Endpoint email notifications aren't sent to the Junk Email folder.</span></span> <span data-ttu-id="98ebf-152">Пометить их как Не нежелательной.</span><span class="sxs-lookup"><span data-stu-id="98ebf-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="98ebf-153">Убедитесь, что продукт безопасности электронной почты не блокирует уведомления электронной почты из Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="98ebf-153">Check that your email security product isn't blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="98ebf-154">Проверьте правила приложения электронной почты, которые могут отлавлить и перемещать уведомления электронной почты Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="98ebf-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="98ebf-155">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="98ebf-155">Related topics</span></span>
- [<span data-ttu-id="98ebf-156">Обновление параметров хранения данных</span><span class="sxs-lookup"><span data-stu-id="98ebf-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="98ebf-157">Настройка дополнительных функций</span><span class="sxs-lookup"><span data-stu-id="98ebf-157">Configure advanced features</span></span>](advanced-features.md)
