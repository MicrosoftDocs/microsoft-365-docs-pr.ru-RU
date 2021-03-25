---
title: Настройка оповещений в Microsoft Defender для конечной точки
description: Вы можете использовать Microsoft Defender для конечной точки для настройки параметров уведомлений электронной почты для оповещений о безопасности в зависимости от серьезности и других критериев.
keywords: уведомления электронной почты, настройка уведомлений оповещений, уведомления atp защитника Майкрософт, оповещения atp защитника Майкрософт, windows 10 корпоративный, windows 10 education
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
ms.openlocfilehash: d8b68e6b6dc42de5730aa634386406d4762b1fa2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163687"
---
# <a name="configure-alert-notifications-in-microsoft-defender-atp"></a><span data-ttu-id="d76ae-104">Настройка оповещений в ATP Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d76ae-104">Configure alert notifications in Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d76ae-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d76ae-105">**Applies to:**</span></span>
- [<span data-ttu-id="d76ae-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d76ae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d76ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d76ae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d76ae-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d76ae-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d76ae-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d76ae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="d76ae-110">Вы можете настроить Defender для конечной точки для отправки уведомлений электронной почты указанным получателям для новых оповещений.</span><span class="sxs-lookup"><span data-stu-id="d76ae-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="d76ae-111">Эта функция позволяет определить группу лиц, которые будут немедленно проинформированы и могут действовать по оповещениям в зависимости от их серьезности.</span><span class="sxs-lookup"><span data-stu-id="d76ae-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="d76ae-112">Настраивать уведомления по электронной почте могут только пользователи с разрешениями "Управление настройками безопасности".</span><span class="sxs-lookup"><span data-stu-id="d76ae-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="d76ae-113">Если вы решили использовать управление базовыми разрешениями, пользователи с ролями администратора безопасности или глобального администратора могут настроить уведомления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d76ae-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="d76ae-114">Можно установить уровни серьезности оповещений, которые вызывают уведомления.</span><span class="sxs-lookup"><span data-stu-id="d76ae-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="d76ae-115">Вы также можете добавить или удалить получателей уведомления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d76ae-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="d76ae-116">Новые получатели получают уведомления о оповещениях, с которыми сталкиваются после их добавлений.</span><span class="sxs-lookup"><span data-stu-id="d76ae-116">New recipients get notified about alerts encountered after they are added.</span></span> <span data-ttu-id="d76ae-117">Дополнительные сведения о оповещениях см. в [обзоре и организации очереди оповещений.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="d76ae-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="d76ae-118">Если вы используете управление доступом на основе ролей (RBAC), получатели будут получать уведомления только на основе групп устройств, настроенных в правиле уведомлений.</span><span class="sxs-lookup"><span data-stu-id="d76ae-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="d76ae-119">Пользователи с надлежащим разрешением могут создавать, редактировать или удалять уведомления, ограниченные областью управления группой устройств.</span><span class="sxs-lookup"><span data-stu-id="d76ae-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="d76ae-120">Управлять правилами уведомлений, настроенными для всех групп устройств, могут только пользователи, назначенные роли глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="d76ae-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="d76ae-121">Уведомление электронной почты содержит основные сведения о оповещении и ссылку на портал, на котором можно дополнительно исследовать.</span><span class="sxs-lookup"><span data-stu-id="d76ae-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>


## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="d76ae-122">Создание правил для уведомлений об оповещении</span><span class="sxs-lookup"><span data-stu-id="d76ae-122">Create rules for alert notifications</span></span>
<span data-ttu-id="d76ae-123">Можно создавать правила, определяя серьезности устройств и оповещения для отправки уведомлений электронной почты для получателей и получателей уведомлений.</span><span class="sxs-lookup"><span data-stu-id="d76ae-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="d76ae-124">В области навигации выберите **уведомления "Параметры**  >  **оповещений".**</span><span class="sxs-lookup"><span data-stu-id="d76ae-124">In the navigation pane, select **Settings** > **Alert notifications**.</span></span>

2. <span data-ttu-id="d76ae-125">Нажмите **кнопку Добавить правило уведомления**.</span><span class="sxs-lookup"><span data-stu-id="d76ae-125">Click **Add notification rule**.</span></span>

3. <span data-ttu-id="d76ae-126">Укажите общие сведения:</span><span class="sxs-lookup"><span data-stu-id="d76ae-126">Specify the General information:</span></span>
    - <span data-ttu-id="d76ae-127">**Имя правила** . Укажите имя правила уведомлений.</span><span class="sxs-lookup"><span data-stu-id="d76ae-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="d76ae-128">**Включайте имя организации** — укажите имя клиента, которое отображается в уведомлении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d76ae-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="d76ae-129">**Включи ссылку портала** для клиента . Добавляет ссылку с ИД клиента, чтобы разрешить доступ к конкретному клиенту.</span><span class="sxs-lookup"><span data-stu-id="d76ae-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="d76ae-130">**Включайте сведения об** устройстве . Включает имя устройства в тело оповещения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d76ae-130">**Include device information** - Includes the device name in the email alert body.</span></span>
    
        >[!NOTE]
        > <span data-ttu-id="d76ae-131">Эти сведения могут обрабатываться почтовыми серверами получателей, которые не имеют географического расположения, выбранного для данных Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d76ae-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="d76ae-132">**Устройства** — выберите, следует ли уведомлять получателей о оповещениях на всех устройствах (только роли глобального администратора) или на отдельных группах устройств.</span><span class="sxs-lookup"><span data-stu-id="d76ae-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="d76ae-133">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении группами устройств.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="d76ae-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="d76ae-134">**Степень серьезности** оповещений . Выберите уровень серьезности оповещения.</span><span class="sxs-lookup"><span data-stu-id="d76ae-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="d76ae-135">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d76ae-135">Click **Next**.</span></span>
    
5. <span data-ttu-id="d76ae-136">Введите адрес электронной почты получателя и нажмите **кнопку Добавить получателя**.</span><span class="sxs-lookup"><span data-stu-id="d76ae-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="d76ae-137">Вы можете добавить несколько адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d76ae-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="d76ae-138">Убедитесь, что получатели электронной почты могут получать уведомления электронной почты, выбрав **отправку тестовой электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="d76ae-138">Check that email recipients are able to receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="d76ae-139">Нажмите **кнопку Сохранить правило уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="d76ae-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="d76ae-140">Изменение правила уведомления</span><span class="sxs-lookup"><span data-stu-id="d76ae-140">Edit a notification rule</span></span>
1. <span data-ttu-id="d76ae-141">Выберите правило уведомлений, необходимое для редактирования.</span><span class="sxs-lookup"><span data-stu-id="d76ae-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="d76ae-142">Обновление сведений о вкладке "Общие" и "Получатель".</span><span class="sxs-lookup"><span data-stu-id="d76ae-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="d76ae-143">Нажмите **кнопку Сохранить правило уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="d76ae-143">Click **Save notification rule**.</span></span>


## <a name="delete-notification-rule"></a><span data-ttu-id="d76ae-144">Правило удаления уведомлений</span><span class="sxs-lookup"><span data-stu-id="d76ae-144">Delete notification rule</span></span>

1. <span data-ttu-id="d76ae-145">Выберите правило уведомления, необходимое для удаления.</span><span class="sxs-lookup"><span data-stu-id="d76ae-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="d76ae-146">Нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d76ae-146">Click **Delete**.</span></span>


## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="d76ae-147">Устранение неполадок в уведомлениях электронной почты для оповещений</span><span class="sxs-lookup"><span data-stu-id="d76ae-147">Troubleshoot email notifications for alerts</span></span>
<span data-ttu-id="d76ae-148">В этом разделе перечислены различные проблемы, с которыми вы можете столкнуться при использовании уведомлений электронной почты для оповещения.</span><span class="sxs-lookup"><span data-stu-id="d76ae-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="d76ae-149">**Проблема:** Предполагаемые получатели сообщают, что они не получают уведомления.</span><span class="sxs-lookup"><span data-stu-id="d76ae-149">**Problem:** Intended recipients report they are not getting the notifications.</span></span>

<span data-ttu-id="d76ae-150">**Решение:** Убедитесь, что уведомления не заблокированы фильтрами электронной почты:</span><span class="sxs-lookup"><span data-stu-id="d76ae-150">**Solution:** Make sure that the notifications are not blocked by email filters:</span></span>

1. <span data-ttu-id="d76ae-151">Убедитесь, что уведомления электронной почты Defender для конечной точки не отправляются в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d76ae-151">Check that the Defender for Endpoint email notifications are not sent to the Junk Email folder.</span></span> <span data-ttu-id="d76ae-152">Пометить их как Не нежелательной.</span><span class="sxs-lookup"><span data-stu-id="d76ae-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="d76ae-153">Убедитесь, что продукт безопасности электронной почты не блокирует уведомления электронной почты из Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d76ae-153">Check that your email security product is not blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="d76ae-154">Проверьте правила приложения электронной почты, которые могут отлавлить и перемещать уведомления электронной почты Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d76ae-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d76ae-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d76ae-155">Related topics</span></span>
- [<span data-ttu-id="d76ae-156">Обновление параметров хранения данных</span><span class="sxs-lookup"><span data-stu-id="d76ae-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="d76ae-157">Настройка расширенных функций</span><span class="sxs-lookup"><span data-stu-id="d76ae-157">Configure advanced features</span></span>](advanced-features.md)
