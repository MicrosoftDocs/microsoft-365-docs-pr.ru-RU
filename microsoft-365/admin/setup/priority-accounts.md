---
title: Управление приоритетными учетными записями и их отслеживание
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
description: Отслеживание сбойных и отложенных сообщений по электронной почте, отправленных в учетные записи с высокими последствиями для бизнеса или из них.
ms.openlocfilehash: f67b9c6f0eaa229b650026670cf1b2adf88ab3c0
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632184"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="18b3c-103">Управление приоритетными учетными записями и их отслеживание</span><span class="sxs-lookup"><span data-stu-id="18b3c-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="18b3c-104">В каждой организации Microsoft 365 есть люди, которые необходимы, например руководители, руководители, руководители или другие пользователи, которые имеют доступ к конфиденциальной, несвободной или высокоприоритетной информации.</span><span class="sxs-lookup"><span data-stu-id="18b3c-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="18b3c-105">Чтобы помочь организации защитить эти учетные записи, вы можете назначить конкретных пользователей в качестве приоритетных учетных записей и использовать специальные функции, которые обеспечивают им дополнительную защиту.</span><span class="sxs-lookup"><span data-stu-id="18b3c-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="18b3c-106">В будущем дополнительные приложения и функции будут поддерживать учетные записи приоритетов, и для начала мы анонсировали две **возможности:** приоритетную защиту учетных записей и мониторинг потока почты **премиум-класса.**</span><span class="sxs-lookup"><span data-stu-id="18b3c-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="18b3c-107">Защита учетных записей приоритета **—** Microsoft Defender для Office 365 (ранее — Office 365 Advanced Threat Protection) поддерживает учетные записи приоритетов в качестве тегов, которые можно использовать в фильтрах оповещений, отчетов и расследований.</span><span class="sxs-lookup"><span data-stu-id="18b3c-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="18b3c-108">Дополнительные сведения можно получить в [тегах пользователей в Microsoft Defender для Office 365.](../../security/office-365-security/user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="18b3c-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="18b3c-109">Естественный вопрос: "Не являются ли все пользователи приоритетом?</span><span class="sxs-lookup"><span data-stu-id="18b3c-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="18b3c-110">Почему бы не назначить всех пользователей в качестве приоритетных учетных записей?</span><span class="sxs-lookup"><span data-stu-id="18b3c-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="18b3c-111">Да, все пользователи являются приоритетом, но защита учетных записей приоритета предоставляет следующие дополнительные преимущества:</span><span class="sxs-lookup"><span data-stu-id="18b3c-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="18b3c-112">**Дополнительные показатели.** Наш анализ потока почты в центрах обработки данных Майкрософт показывает, что шаблоны потока почты для руководителей компаний отличаются от обычного сотрудника.</span><span class="sxs-lookup"><span data-stu-id="18b3c-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="18b3c-113">Защита учетной записи приоритета предоставляет дополнительные возможности, специально разработанные для руководителей компаний, которые не повлияют на пользу обычному сотруднику.</span><span class="sxs-lookup"><span data-stu-id="18b3c-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="18b3c-114">**Дополнительная видимость** в отчетах. Фактически сведения для всех пользователей (или всех затронутых пользователей) уже доступны в оповещении, отчетах и расследованиях.</span><span class="sxs-lookup"><span data-stu-id="18b3c-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="18b3c-115">Тег учетных записей приоритетов в качестве фильтра позволяет конкретно нацелить свои исследования.</span><span class="sxs-lookup"><span data-stu-id="18b3c-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="18b3c-116">**Мониторинг потока почты** премиум-класса . Здоровый поток почты может иметь решающее значение для успешного ведения бизнеса, а задержки или сбои доставки могут отрицательно повлиять на бизнес.</span><span class="sxs-lookup"><span data-stu-id="18b3c-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="18b3c-117">Вы можете выбрать пороговое значение для сбойных или отложенных сообщений электронной почты, получать оповещения при превышении этого порогового значения и просматривать отчет о проблемах электронной почты для учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="18b3c-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="18b3c-118">Дополнительные сведения вы можете узнать о проблемах [электронной почты](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) для отчета о приоритетных учетных записях в современном EAC</span><span class="sxs-lookup"><span data-stu-id="18b3c-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="18b3c-119">Рекомендации по безопасности для приоритетных учетных записей см. в рекомендациях по безопасности [для учетных записей приоритетов.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="18b3c-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="18b3c-120">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="18b3c-120">Before you begin</span></span>

<span data-ttu-id="18b3c-121">Функция **защиты учетных записей Priority,** описанная в этом разделе, доступна только организациям, которые соответствуют следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="18b3c-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="18b3c-122">Microsoft Defender для Office 365 Plan 2, в том числе с Office 365 E3, Office 365 E5, Microsoft 365 E5 или Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="18b3c-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="18b3c-123">Функция **мониторинга потока почты** Премиум, описанная в этом разделе, доступна только организациям, которые соответствуют следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="18b3c-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="18b3c-124">Ваша организация должна иметь количество лицензий не менее 10 000 из одного из следующих продуктов: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="18b3c-124">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="18b3c-125">Например, ваша организация может иметь 3000 лицензий Office 365 E3 и 8500 Лицензий Microsoft 365 E5 на общую сумму 11 500 лицензий из продуктов, подав их.</span><span class="sxs-lookup"><span data-stu-id="18b3c-125">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="18b3c-126">У вашей организации должно быть как минимум 50 активных пользователей Exchange Online ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="18b3c-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="18b3c-127">Вы можете отслеживать до 250 учетных записей приоритетов.</span><span class="sxs-lookup"><span data-stu-id="18b3c-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="18b3c-128">При применении приоритетной защиты учетных записей к почтовому ящику следует также применять защиту учетных записей приоритетов к пользователям, которые имеют доступ к почтовому ящику (например, к генеральному директору и исполнительному помощнику генерального директора, который управляет календарем генерального директора).</span><span class="sxs-lookup"><span data-stu-id="18b3c-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="18b3c-129">Добавление учетных записей приоритета со страницы Установки</span><span class="sxs-lookup"><span data-stu-id="18b3c-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="18b3c-130">Добавление учетных записей приоритетов со страницы **Установки.**</span><span class="sxs-lookup"><span data-stu-id="18b3c-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="18b3c-131">Перейдите в центр администрирования Microsoft 365 по <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> крайней .</span><span class="sxs-lookup"><span data-stu-id="18b3c-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="18b3c-132">Перейдите к  >  **организационным знаниям установки** и выберите **Просмотр** в **режиме Monitor ваших наиболее важных учетных записей.**</span><span class="sxs-lookup"><span data-stu-id="18b3c-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="18b3c-133">Выберите **Начало работы** или **управление**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="18b3c-134">На странице **Добавить учетные записи** приоритета в поле поиска введите имя или адрес электронной почты человека, которого вы хотите добавить в список учетных записей приоритета.</span><span class="sxs-lookup"><span data-stu-id="18b3c-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="18b3c-135">Вы также можете установить пороговое значение электронной почты для сбойных или отложенных сообщений электронной почты и получить еженедельный отчет о проблемах для учетных записей приоритетов.</span><span class="sxs-lookup"><span data-stu-id="18b3c-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="18b3c-136">Выберите пользователя и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="18b3c-137">Кроме того, можно добавить учетные записи приоритетов со страницы Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="18b3c-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="18b3c-138">Добавление учетных записей приоритетов со страницы Активные пользователи</span><span class="sxs-lookup"><span data-stu-id="18b3c-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="18b3c-139">Добавление учетных записей приоритетов со страницы Активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="18b3c-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="18b3c-140">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="18b3c-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="18b3c-141">Перейдите **к пользователям Active**  >  **и** выберите **...** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="18b3c-141">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="18b3c-142">Выберите **Управление учетной записью приоритета**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="18b3c-143">Выберите **Добавить учетные** записи и на странице **Добавить** учетные записи приоритета в поле поиска введите имя человека, которого вы хотите добавить в список приоритетных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="18b3c-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="18b3c-144">Выберите пользователя и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="18b3c-145">Удаление пользователя из списка приоритетных учетных записей</span><span class="sxs-lookup"><span data-stu-id="18b3c-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="18b3c-146">Перейдите в центр администрирования Microsoft 365 по <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> крайней .</span><span class="sxs-lookup"><span data-stu-id="18b3c-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="18b3c-147">Перейдите к  >  **организационным знаниям установки** и выберите **Просмотр** в **режиме Monitor ваших наиболее важных учетных записей.**</span><span class="sxs-lookup"><span data-stu-id="18b3c-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="18b3c-148">На странице **Monitor большинство учетных записей** выберите учетные записи **Priority в** статье Управление этой **функцией.**</span><span class="sxs-lookup"><span data-stu-id="18b3c-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="18b3c-149">На странице **Учетные записи приоритета** выберите пользователя или пользователей, которые необходимо удалить из списка, и выберите Удалить **учетные записи.**</span><span class="sxs-lookup"><span data-stu-id="18b3c-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="18b3c-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="18b3c-150">Related topics</span></span>

[<span data-ttu-id="18b3c-151">Использование учетных записей приоритета в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="18b3c-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
