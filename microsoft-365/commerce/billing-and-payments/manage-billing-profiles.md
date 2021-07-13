---
title: Общие сведения о профилях выставления счетов
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- AdminTemplateSet
search.appverid: MET150
description: Узнайте, как профили выставления счетов поддерживают счета-фактуры.
ms.date: 04/02/2021
ms.openlocfilehash: ecea09a9ceea12fa92b92eac3e5a7595b2510042
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394633"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="09ef8-103">Общие сведения о профилях выставления счетов</span><span class="sxs-lookup"><span data-stu-id="09ef8-103">Understand billing profiles</span></span>

<span data-ttu-id="09ef8-104">Профиль выставления счетов содержит метод оплаты, сведения о счете и другие параметры счетов, такие как номер заказа на покупку и предпочтение счета-фактуры электронной почты.</span><span class="sxs-lookup"><span data-stu-id="09ef8-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="09ef8-105">Для оплаты продуктов, которые вы покупаете в Корпорации Майкрософт, используется профиль выплаты.</span><span class="sxs-lookup"><span data-stu-id="09ef8-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="09ef8-106">При покупке самообслуживаемого пользователя автоматически создается профиль выписывающих счета.</span><span class="sxs-lookup"><span data-stu-id="09ef8-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="09ef8-107">Каждый профиль выставления счетов выставляется отдельно.</span><span class="sxs-lookup"><span data-stu-id="09ef8-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="09ef8-108">Профили биллинга недоступны клиентам, которые покупают продукты и Microsoft.com или  на странице Службы покупки Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09ef8-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="09ef8-109">Что такое роли профилей для вы выставления счета?</span><span class="sxs-lookup"><span data-stu-id="09ef8-109">What are billing profile roles?</span></span>

<span data-ttu-id="09ef8-110">Роли в профилях выставления счетов имеют разрешения на управление покупками, просмотр и управление счет-фактурами.</span><span class="sxs-lookup"><span data-stu-id="09ef8-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="09ef8-111">Назначьте эти роли пользователям, которые отслеживают, организуют и платят счета-фактуры.</span><span class="sxs-lookup"><span data-stu-id="09ef8-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="09ef8-112">Например, члены группы закупок в организации.</span><span class="sxs-lookup"><span data-stu-id="09ef8-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="09ef8-113">Role</span><span class="sxs-lookup"><span data-stu-id="09ef8-113">Role</span></span>                         | <span data-ttu-id="09ef8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="09ef8-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="09ef8-115">Владелец профилей биллинга</span><span class="sxs-lookup"><span data-stu-id="09ef8-115">Billing profile owner</span></span>        | <span data-ttu-id="09ef8-116">Управление всем для профиля вы выставления счета</span><span class="sxs-lookup"><span data-stu-id="09ef8-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="09ef8-117">Вкладчик профилей биллинга</span><span class="sxs-lookup"><span data-stu-id="09ef8-117">Billing profile contributor</span></span>  | <span data-ttu-id="09ef8-118">Управление всем, кроме разрешений в профиле биллинга</span><span class="sxs-lookup"><span data-stu-id="09ef8-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="09ef8-119">Считыватель профилей биллинга</span><span class="sxs-lookup"><span data-stu-id="09ef8-119">Billing profile reader</span></span>       | <span data-ttu-id="09ef8-120">Просмотр только для чтения всего в профиле вы выставления счета</span><span class="sxs-lookup"><span data-stu-id="09ef8-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="09ef8-121">Менеджер по счетам</span><span class="sxs-lookup"><span data-stu-id="09ef8-121">Invoice manager</span></span>              | <span data-ttu-id="09ef8-122">Просмотр и оплата счетов, а также просмотр только для чтения всего в профиле вы выставления счетов</span><span class="sxs-lookup"><span data-stu-id="09ef8-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="09ef8-123">Просмотр профилей биллинга</span><span class="sxs-lookup"><span data-stu-id="09ef8-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="09ef8-124">Если вы выполните эти действия, и список профилей вы выставления счета будет пустым, это означает, что у вас нет профиля вы выставления счета и вы не можете использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="09ef8-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="09ef8-125">В центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Счета и платежи</a>.</span><span class="sxs-lookup"><span data-stu-id="09ef8-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="09ef8-126">Выберите **вкладку профилей Биллинга,** а затем выберите профиль выкладки из списка.</span><span class="sxs-lookup"><span data-stu-id="09ef8-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="09ef8-127">Каждый профиль вы выставления счета содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="09ef8-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="09ef8-128">**Имя и состояние профиля биллинга** &ndash; Уникальное имя профиля вы выставления счета и активен ли он или отключен для покупки.</span><span class="sxs-lookup"><span data-stu-id="09ef8-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="09ef8-129">**Параметры счета** &ndash; Валюта в зависимости от страны счета-выставления счетов, сведений о частоте и дате счета, возможности получения счетов в виде вложений электронной почты и дополнительного поля номеров PO</span><span class="sxs-lookup"><span data-stu-id="09ef8-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="09ef8-130">**Методы оплаты** &ndash; Показывает метод первичной и резервной оплаты, если таково, для профиля</span><span class="sxs-lookup"><span data-stu-id="09ef8-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="09ef8-131">**Учетная запись биллинга** &ndash; Имя учетной записи вы выставления счетов, с чем связан профиль.</span><span class="sxs-lookup"><span data-stu-id="09ef8-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="09ef8-132">Дополнительные сведения об учетных записях с выставлением счетов см. в [см. в руб. Сведения об учетных записях для биллинга.](../manage-billing-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="09ef8-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="09ef8-133">**Контактные данные** &ndash; Адрес и имя контакта и адрес электронной почты</span><span class="sxs-lookup"><span data-stu-id="09ef8-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="09ef8-134">**Роли профилей биллинга** &ndash; Список людей, которым назначена одна из ролей профилей биллинга для работы с этим профилем.</span><span class="sxs-lookup"><span data-stu-id="09ef8-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="09ef8-135">Например, оплата счетов, добавление номера PO или замена метода оплаты, который используется для покупки.</span><span class="sxs-lookup"><span data-stu-id="09ef8-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="09ef8-136">Вы можете назначать только роли профилей для вы выставления счета пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="09ef8-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="09ef8-137">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="09ef8-137">Need help?</span></span> <span data-ttu-id="09ef8-138">Обратитесь в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="09ef8-138">Contact support</span></span>

<span data-ttu-id="09ef8-139">Если у вас есть вопросы или вам нужна помощь с зарядами Azure, создайте запрос на поддержку <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">с помощью службы поддержки Azure.</a></span><span class="sxs-lookup"><span data-stu-id="09ef8-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="09ef8-140">Если у вас есть вопросы или вам нужна помощь в профиле Центр администрирования Microsoft 365, обратитесь [в службу поддержки.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="09ef8-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="09ef8-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="09ef8-141">Related content</span></span>

<span data-ttu-id="09ef8-142">[Оплата подписки с помощью профиля](pay-for-subscription-billing-profile.md) вы выставления счета (статья)</span><span class="sxs-lookup"><span data-stu-id="09ef8-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="09ef8-143">[Понимание учетных записей биллинга](../manage-billing-accounts.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="09ef8-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="09ef8-144">[Управление методами оплаты](manage-payment-methods.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="09ef8-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
