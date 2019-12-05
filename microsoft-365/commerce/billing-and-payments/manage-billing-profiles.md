---
title: Управление профилями выставления счетов
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Узнайте, как профили выставления счетов поддерживают накладные.
keywords: Профиль выставления счетов, счета, расходы, управляемые расходы
ms.openlocfilehash: 3dbdbb57b46b915891640483bde56ebc8ad1cff6
ms.sourcegitcommit: 95a07b328166f637a481c8b5c53669eaf8ff0db8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "39837393"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="a2ab0-104">Управление профилями выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-104">Manage billing profiles</span></span>
<span data-ttu-id="a2ab0-105">Для коммерческих клиентов, которые покупают продукты и услуги от Майкрософт, профили выставления счетов позволяют настраивать, какие товары включаются в счет, а также как вы оплачиваете счета.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-105">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="a2ab0-106">Профили выставления счетов включают следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a2ab0-106">Billing profiles include the following information:</span></span>

- <span data-ttu-id="a2ab0-107">Имя **учетной** &ndash; записи выставления счетов, с которой связан профиль</span><span class="sxs-lookup"><span data-stu-id="a2ab0-107">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="a2ab0-108">**Способы** &ndash; оплаты кредитные или дебетовые карты, банковские счета, проверка или перенос проводок</span><span class="sxs-lookup"><span data-stu-id="a2ab0-108">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="a2ab0-109">Адрес для выставления счетов и имя контакта **контактной информации** &ndash;</span><span class="sxs-lookup"><span data-stu-id="a2ab0-109">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="a2ab0-110">Валюта &ndash; **параметров накладных** на основе страны счета выставления счетов, дополнительного номера ЗП и варианта получения счетов в виде вложений электронной почты</span><span class="sxs-lookup"><span data-stu-id="a2ab0-110">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="a2ab0-111">Разрешения, позволяющие изменить профиль выставления счетов, счета оплаты или использовать метод оплаты в профиле выставления счетов, чтобы совершать покупки \*\*\*\* &ndash;</span><span class="sxs-lookup"><span data-stu-id="a2ab0-111">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="a2ab0-112">Использование профилей выставления счетов для управления покупками и настройки счетов.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-112">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="a2ab0-113">Для продуктов, приобретенных в профиле выставления счетов, создается ежемесячный счет.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-113">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="a2ab0-114">Вы можете настроить накладную, например, обновить номер заказа на покупку и настройку накладных по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-114">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="a2ab0-115">Профиль выставления счетов автоматически создается для счета выставления счетов при первой покупке.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-115">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="a2ab0-116">Вы можете создать профили выставления счетов на странице <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Профили выставления счетов</a> , чтобы настроить дополнительные счета.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-116">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="a2ab0-117">Например, вы можете использовать различные профили выставления счетов при совершении покупок для каждого отдела в Организации.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-117">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="a2ab0-118">На следующей дате выставления счетов вы получите счет для каждого профиля выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-118">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="a2ab0-119">Роли профиля выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-119">Billing profile roles</span></span>

<span data-ttu-id="a2ab0-120">Роли в профилях выставления счетов имеют разрешения на управление покупками и просмотр и управление накладными.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-120">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="a2ab0-121">Назначьте эти роли пользователям, которые отслеживают, упорядочивают и платят по накладным, например участникам группы закупаемой продукции в Организации.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-121">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="a2ab0-122">Role</span><span class="sxs-lookup"><span data-stu-id="a2ab0-122">Role</span></span>                          | <span data-ttu-id="a2ab0-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a2ab0-123">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="a2ab0-124">Владелец профиля выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-124">Billing profile owner</span></span>         | <span data-ttu-id="a2ab0-125">Управление всеми для профиля выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-125">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="a2ab0-126">Корреспондент профиля выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-126">Billing profile contributor</span></span>   | <span data-ttu-id="a2ab0-127">Управление всеми, кроме разрешений, в профиле выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-127">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="a2ab0-128">Средство чтения профилей выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-128">Billing profile reader</span></span>        | <span data-ttu-id="a2ab0-129">Представление "только для чтения" всего в профиле выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-129">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="a2ab0-130">Менеджер по накладным</span><span class="sxs-lookup"><span data-stu-id="a2ab0-130">Invoice manager</span></span>               | <span data-ttu-id="a2ab0-131">Просмотр и оплата ведомостей, а так же доступное только для чтения представление всех элементов в профиле выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-131">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="a2ab0-132">Просмотр профилей выставления счетов</span><span class="sxs-lookup"><span data-stu-id="a2ab0-132">View billing profiles</span></span>

1. <span data-ttu-id="a2ab0-133">В центре администрирования перейдите на страницу **выставления счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">& платежей</a> .</span><span class="sxs-lookup"><span data-stu-id="a2ab0-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="a2ab0-134">Выберите **Профили выставления счетов**, а затем выберите из списка профиль выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-134">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="a2ab0-135">На вкладке **Обзор** можно изменить сведения профиля выставления счетов, а также включить или отключить отправку счета по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-135">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="a2ab0-136">На вкладке **разрешения** можно назначить роли пользователям для оплаты счетов.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-136">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="a2ab0-137">На вкладке **Azure Credit Balance** клиенты Azure могут просматривать историю сальдо проводок для кредитов Azure, используемых этим профилем выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-137">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="a2ab0-138">На вкладке **кредиты Azure** клиенты Azure могут просматривать список кредитов Azure, связанных с этим профилем выставления счетов, и даты их истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-138">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a2ab0-139">Если у вас нет кредитов в Azure, вы не увидите вкладки **Azure кредитный баланс** или **Azure кредиты** .</span><span class="sxs-lookup"><span data-stu-id="a2ab0-139">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="a2ab0-140">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="a2ab0-140">Need help?</span></span> <span data-ttu-id="a2ab0-141">Обратитесь за поддержкой.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-141">Contact support.</span></span>

<span data-ttu-id="a2ab0-142">Если у вас возникли вопросы или вам нужна помощь по работе с платами Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Создайте запрос в службу поддержки с поддержкой Azure</a>.</span><span class="sxs-lookup"><span data-stu-id="a2ab0-142">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="a2ab0-143">Если у вас возникли вопросы или вам нужна помощь по профилю выставления счетов в центре администрирования Microsoft 365, [обратитесь в службу поддержки продуктов для бизнеса](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="a2ab0-143">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
