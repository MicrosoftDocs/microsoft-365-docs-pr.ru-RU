---
title: Управление учетной записью приоритета и наблюдение за нею
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Отслеживание сбойных и отложенных сообщений электронной почты, отложенных от учетных записей, которые имеют большое влияние на бизнес.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477617"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="c0749-103">Управление учетной записью приоритета и наблюдение за нею</span><span class="sxs-lookup"><span data-stu-id="c0749-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="c0749-104">В каждой организации Microsoft 365 есть люди, которые необходимы, например руководители, руководители, руководители или другие пользователи, которые имеют доступ к конфиденциальной, конфиденциальной или высокоприоритетной информации.</span><span class="sxs-lookup"><span data-stu-id="c0749-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="c0749-105">Чтобы помочь вашей организации защитить эти учетные записи, вы можете назначить определенных пользователей в качестве учетных записей приоритета и использовать специальные функции для приложений, которые обеспечивают им дополнительную защиту.</span><span class="sxs-lookup"><span data-stu-id="c0749-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="c0749-106">В будущем дополнительные приложения и функции будут поддерживать учетные записи с приоритетами, и для начала мы объявили две **возможности:** приоритетную защиту учетных записей и мониторинг потока почты **премиум-класса.**</span><span class="sxs-lookup"><span data-stu-id="c0749-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="c0749-107">Защита учетных записей приоритетов **—** Microsoft Defender для Office 365 (ранее Office 365 Advanced Threat Protection) поддерживает учетные записи приоритетов в качестве тегов, которые можно использовать в фильтрах оповещений, отчетов и расследований.</span><span class="sxs-lookup"><span data-stu-id="c0749-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="c0749-108">Дополнительные сведения можно узнать о [тегах пользователей в Microsoft Defender для Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="c0749-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="c0749-109">**Мониторинг потока почты** premium : для успешного бизнеса может быть важен поток почты, а задержки или сбои доставки могут отрицательно повлиять на бизнес.</span><span class="sxs-lookup"><span data-stu-id="c0749-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="c0749-110">Можно выбрать пороговое значение для неудачных или отложенных сообщений электронной почты, получать оповещения при превышении этого порога и просматривать отчет о проблемах с электронной почтой для учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="c0749-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="c0749-111">Дополнительные сведения о проблемах с электронной почтой для отчетов о приоритетах учетных записей можно узнать [в современном EAC.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="c0749-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c0749-112">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="c0749-112">Before you begin</span></span>

<span data-ttu-id="c0749-113">Функция **защиты учетных записей** приоритетов, описанная в этом разделе, доступна только организациям, которые соответствуют следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="c0749-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="c0749-114">Microsoft Defender для Office 365 (план 2), включая office 365 E3, Office 365 E5, Microsoft 365 E5 или Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="c0749-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="c0749-115">Функция **мониторинга потока почты** Premium, описанная в этом разделе, доступна только организациям, которые соответствуют следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="c0749-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="c0749-116">В вашей организации должно быть по крайней мере 10 000 лицензий из одного или нескольких продуктов: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c0749-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="c0749-117">Например, у вашей организации может быть 3000 лицензий Office 365 E3 и 8500 Microsoft 365 E5 для 11 500 лицензий из продуктов, подавных требованиям.</span><span class="sxs-lookup"><span data-stu-id="c0749-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="c0749-118">У вашей организации должно быть как минимум 50 активных пользователей Exchange Online ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="c0749-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="c0749-119">Вы можете отслеживать до 250 учетных записей с приоритетами.</span><span class="sxs-lookup"><span data-stu-id="c0749-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="c0749-120">Добавление учетных записей приоритета со страницы установки</span><span class="sxs-lookup"><span data-stu-id="c0749-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="c0749-121">Добавьте учетные записи приоритета со страницы **установки.**</span><span class="sxs-lookup"><span data-stu-id="c0749-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="c0749-122">Перейдите в Центр администрирования Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> по</span><span class="sxs-lookup"><span data-stu-id="c0749-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c0749-123">Перейдите **к сведениям о** настройке организации и выберите "Просмотр" в области  >    **"Мониторинг самых важных учетных записей".**</span><span class="sxs-lookup"><span data-stu-id="c0749-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="c0749-124">Выберите **"Начало работы"** или **"Управление".**</span><span class="sxs-lookup"><span data-stu-id="c0749-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="c0749-125">На странице **"Добавление** учетных записей приоритета" в поле поиска введите имя или адрес электронной почты пользователя, которого вы хотите добавить в список учетных записей приоритетов.</span><span class="sxs-lookup"><span data-stu-id="c0749-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="c0749-126">Вы также можете установить пороговое значение для сообщений электронной почты, которые не удалось отправить или отложить, и получить еженедельный отчет о проблемах для учетных записей с приоритетом.</span><span class="sxs-lookup"><span data-stu-id="c0749-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="c0749-127">Выберите пользователя и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="c0749-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="c0749-128">Вы также можете добавить учетные записи с учетной записью приоритета на странице "Активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="c0749-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="c0749-129">Добавление учетных записей приоритета со страницы "Активные пользователи"</span><span class="sxs-lookup"><span data-stu-id="c0749-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="c0749-130">Добавьте учетные записи приоритета со страницы "Активные пользователи".</span><span class="sxs-lookup"><span data-stu-id="c0749-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="c0749-131">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="c0749-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c0749-132">Перейдите **к пользователям**  >  **"Активные пользователи"** и выберите **...в** верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="c0749-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="c0749-133">Выберите **"Управление учетной записью с учетной записью приоритета".**</span><span class="sxs-lookup"><span data-stu-id="c0749-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="c0749-134">Выберите **"Добавить** учетные  записи" и на странице "Добавление учетных записей приоритета" в поле поиска введите имя пользователя, которого нужно добавить в список учетных записей приоритетов.</span><span class="sxs-lookup"><span data-stu-id="c0749-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="c0749-135">Выберите пользователя и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="c0749-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="c0749-136">Удаление пользователя из списка учетных записей приоритетов</span><span class="sxs-lookup"><span data-stu-id="c0749-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="c0749-137">Перейдите в Центр администрирования Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> по</span><span class="sxs-lookup"><span data-stu-id="c0749-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c0749-138">Перейдите **к сведениям о** настройке организации и выберите "Просмотр" в области  >    **"Мониторинг самых важных учетных записей".**</span><span class="sxs-lookup"><span data-stu-id="c0749-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="c0749-139">На странице **"Мониторинг большинства учетных** записей" выберите **"Учетные записи** приоритетов" в области **"Управление этой функцией".**</span><span class="sxs-lookup"><span data-stu-id="c0749-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="c0749-140">На странице **"Учетные записи приоритета"** выберите пользователя или пользователей, которые нужно удалить из списка, и выберите "Удалить **учетные записи".**</span><span class="sxs-lookup"><span data-stu-id="c0749-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0749-141">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c0749-141">Related topics</span></span>

[<span data-ttu-id="c0749-142">Использование учетных записей приоритетов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c0749-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)