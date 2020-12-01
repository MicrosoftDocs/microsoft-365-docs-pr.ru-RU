---
title: Управление учетными записями приоритетов и их отслеживание
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
description: Отслеживание сбоев и задержанных сообщений электронной почты, отправленных в или из учетных записей с высоким влиянием на бизнес.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477617"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="7f78f-103">Управление учетными записями приоритетов и их отслеживание</span><span class="sxs-lookup"><span data-stu-id="7f78f-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="7f78f-104">В каждой организации Microsoft 365 есть важные пользователи, такие как руководители, руководители, руководители и другие пользователи, имеющие доступ к конфиденциальным, особым или высокоприоритетным сведениям.</span><span class="sxs-lookup"><span data-stu-id="7f78f-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="7f78f-105">Чтобы помочь вашей организации защитить эти учетные записи, теперь вы можете назначить определенных пользователей в качестве приоритетных учетных записей и использовать функции, связанные с приложениями, которые предоставляют им дополнительную защиту.</span><span class="sxs-lookup"><span data-stu-id="7f78f-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="7f78f-106">В будущем больше приложений и функций будут поддерживать учетные записи приоритетов, и для начала мы объявили о двух возможностях: **приоритетной защите учетных записей** и **расширенному мониторингу почтовых ящиков**.</span><span class="sxs-lookup"><span data-stu-id="7f78f-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="7f78f-107">**Приоритет защиты учетных записей** — защитник Майкрософт для Office 365 (ранее Office 365 Advanced Threat protection) поддерживает учетные записи приоритетов в качестве тегов, которые можно использовать в фильтрах в оповещениях, отчетах и исследованиях.</span><span class="sxs-lookup"><span data-stu-id="7f78f-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="7f78f-108">Для получения дополнительных сведений ознакомьтесь [с тегами пользователя в защитнике Майкрософт для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="7f78f-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="7f78f-109">**Мониторинг почтовых почтовых ящиков с расширенной** почтовыми сообщениями может быть критически важным для успеха бизнеса, а задержки и сбои доставки могут негативно повлиять на работу предприятия.</span><span class="sxs-lookup"><span data-stu-id="7f78f-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="7f78f-110">Вы можете выбрать пороговое значение для неудачных или задержанных сообщений электронной почты, получать оповещения при превышении этого порога и просматривать отчет о неполадках по электронной почте для учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="7f78f-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="7f78f-111">Для получения дополнительных сведений обратитесь к [отчету о приоритетных учетных записей в современном](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="7f78f-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7f78f-112">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="7f78f-112">Before you begin</span></span>

<span data-ttu-id="7f78f-113">Функция **защиты учетной записи Priority** , описанная в этом разделе, доступна только организациям, которые отвечают следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="7f78f-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="7f78f-114">Защитник Майкрософт для Office 365 (план 2), в том числе с Office 365 E3, Office 365, Microsoft 365, или Microsoft 365, безопасность.</span><span class="sxs-lookup"><span data-stu-id="7f78f-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="7f78f-115">Функция **мониторинга почтовых сообщений Premium** , описанная в этом разделе, доступна только организациям, которые отвечают следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="7f78f-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="7f78f-116">Организация должна иметь число лицензий по крайней мере 10 000, из одного из следующих продуктов: Office 365 E3, Microsoft 365 E3, Office 365, Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f78f-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="7f78f-117">Например, у вашей организации могут быть 3000 лицензий на Office 365 E3 и 8500 Microsoft 365 "/", чтобы получить общее 11 500 количество лицензий на продукцию QLP.</span><span class="sxs-lookup"><span data-stu-id="7f78f-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="7f78f-118">Организация должна иметь по крайней мере 50 ежемесячных активных пользователей Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7f78f-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="7f78f-119">Вы можете отслеживать до 250 учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="7f78f-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="7f78f-120">Добавление учетных записей приоритетов на странице настройки</span><span class="sxs-lookup"><span data-stu-id="7f78f-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="7f78f-121">Добавьте учетные записи приоритетов на **странице Настройка**.</span><span class="sxs-lookup"><span data-stu-id="7f78f-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="7f78f-122">Перейдите в центр администрирования Microsoft 365 по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="7f78f-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="7f78f-123">Перейдите к разделу **Настройка**  >  **организационных знаний** и выберите **Просмотр** в разделе **мониторинг наиболее важных учетных записей**.</span><span class="sxs-lookup"><span data-stu-id="7f78f-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="7f78f-124">Нажмите кнопку " **начать работу** " или " **Управление**".</span><span class="sxs-lookup"><span data-stu-id="7f78f-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="7f78f-125">На странице " **Добавление учетных записей приоритетов** " в поле поиска введите имя или адрес электронной почты пользователя, которого нужно добавить в список учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="7f78f-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="7f78f-126">Вы также можете задать пороговое значение для неудачных или задержанных сообщений электронной почты, а также получить отчет о проблемах с учетными записями приоритетов.</span><span class="sxs-lookup"><span data-stu-id="7f78f-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="7f78f-127">Выберите пользователя и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f78f-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="7f78f-128">Вы также можете добавлять учетные записи приоритетов со страницы активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="7f78f-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="7f78f-129">Добавление учетных записей приоритетов на странице "активные пользователи"</span><span class="sxs-lookup"><span data-stu-id="7f78f-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="7f78f-130">Добавьте учетные записи приоритетов со страницы активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="7f78f-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="7f78f-131">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="7f78f-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="7f78f-132">Перейдите к **Users** разделу  >  **Активные пользователи** пользователей и нажмите кнопку **...** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="7f78f-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="7f78f-133">Выберите **Управление учетными записями приоритетов**.</span><span class="sxs-lookup"><span data-stu-id="7f78f-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="7f78f-134">Нажмите кнопку **Добавить учетные записи**, а затем на странице " **Добавление учетных записей приоритетов** " в поле поиска введите имя пользователя, которого вы хотите добавить в список учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="7f78f-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="7f78f-135">Выберите пользователя и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f78f-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="7f78f-136">Удаление пользователя из списка приоритетных учетных записей</span><span class="sxs-lookup"><span data-stu-id="7f78f-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="7f78f-137">Перейдите в центр администрирования Microsoft 365 по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="7f78f-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="7f78f-138">Перейдите к разделу **Настройка**  >  **организационных знаний** и выберите **Просмотр** в разделе **мониторинг наиболее важных учетных записей**.</span><span class="sxs-lookup"><span data-stu-id="7f78f-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="7f78f-139">На странице " **наблюдение за всеми учетными записями** " выберите пункт **приоритетные учетные записи** в разделе **Управление этим компонентом**.</span><span class="sxs-lookup"><span data-stu-id="7f78f-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="7f78f-140">На странице **приоритет учетных записей** выберите пользователя или пользователей, которых требуется удалить из списка, а затем выберите, **удалить учетные записи**.</span><span class="sxs-lookup"><span data-stu-id="7f78f-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7f78f-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7f78f-141">Related topics</span></span>

[<span data-ttu-id="7f78f-142">Использование учетных записей приоритетов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f78f-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)