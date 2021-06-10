---
title: Директива 2 по службам оплаты и сильная проверка подлинности клиентов для коммерческих клиентов
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: По данным на 14 сентября 2019 г., банки в 31 стране Европейской экономической зоны должны проверить личность лица, сделавного онлайн-покупку, до обработки платежа".
keywords: директива 2 служб оплаты, сильная проверка подлинности клиентов, многофакторная проверка подлинности
ms.date: 11/03/2020
ms.openlocfilehash: bbbbe9f53c11fcae9c35cda1fd4e7d4b51a9c767
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331950"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="185e8-104">Директива 2 по службам оплаты и сильная проверка подлинности клиентов для коммерческих клиентов</span><span class="sxs-lookup"><span data-stu-id="185e8-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="185e8-105">По данным на 14 сентября 2019 г., банки в 31 стране Европейской экономической зоны обязаны проверить личность лица, сделав купли-продажи в Интернете до обработки платежа.</span><span class="sxs-lookup"><span data-stu-id="185e8-105">As of September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="185e8-106">Эта проверка требует многофакторной проверки подлинности, чтобы обеспечить безопасность и защиту покупок в Интернете.</span><span class="sxs-lookup"><span data-stu-id="185e8-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="185e8-107">Дата этого требования проверки для некоторых стран будет отложена.</span><span class="sxs-lookup"><span data-stu-id="185e8-107">The date for this verification requirement will be delayed for some countries.</span></span>

<span data-ttu-id="185e8-108">Дополнительные сведения см. в [faq Microsoft о Директиве 2](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)по платежным службам и проверке подлинности клиентов.</span><span class="sxs-lookup"><span data-stu-id="185e8-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="185e8-109">Когда требуется многофакторная проверка подлинности?</span><span class="sxs-lookup"><span data-stu-id="185e8-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="185e8-110">В настоящее время требования к проверке для этой директивы с помощью многофакторной проверки подлинности применяются только к клиентам, использующим кредитные карты из банков в 31 стране Европейской экономической зоны.</span><span class="sxs-lookup"><span data-stu-id="185e8-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="185e8-111">Иногда клиенты будут вызваны из-за действий, которые они приняли, а иногда они вызваны из-за событий с существующими подписками или службами.</span><span class="sxs-lookup"><span data-stu-id="185e8-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="185e8-112">Действия клиента</span><span class="sxs-lookup"><span data-stu-id="185e8-112">Customer Actions</span></span>

<span data-ttu-id="185e8-113">Вашему банку может потребоваться проверка с помощью многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="185e8-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="185e8-114">Вот некоторые примеры:</span><span class="sxs-lookup"><span data-stu-id="185e8-114">Some examples include:</span></span>

- <span data-ttu-id="185e8-115">Регистрация на новую подписку</span><span class="sxs-lookup"><span data-stu-id="185e8-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="185e8-116">Добавление лицензий в подписку</span><span class="sxs-lookup"><span data-stu-id="185e8-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="185e8-117">Добавление или замена кредитной карты, используемой для оплаты подписки или службы</span><span class="sxs-lookup"><span data-stu-id="185e8-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="185e8-118">Добавление или замена кредитной карты в профиле вы выставления счета</span><span class="sxs-lookup"><span data-stu-id="185e8-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="185e8-119">Покупка приложений</span><span class="sxs-lookup"><span data-stu-id="185e8-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="185e8-120">События жизненного цикла подписки</span><span class="sxs-lookup"><span data-stu-id="185e8-120">Subscription lifecycle events</span></span>

<span data-ttu-id="185e8-121">Сборы за повторяющиеся платежи могут привести к сбойу.</span><span class="sxs-lookup"><span data-stu-id="185e8-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="185e8-122">В этом случае вы получите сообщение электронной почты с инструкциями.</span><span class="sxs-lookup"><span data-stu-id="185e8-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="185e8-123">Вам будет предложено ответить на запрос проверки и внести текущий платеж.</span><span class="sxs-lookup"><span data-stu-id="185e8-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="185e8-124">Нужна дополнительная помощь?</span><span class="sxs-lookup"><span data-stu-id="185e8-124">Need more help?</span></span>

<span data-ttu-id="185e8-125">Ваше финансовое учреждение является лучшим контактом для этих сценариев:</span><span class="sxs-lookup"><span data-stu-id="185e8-125">Your financial institution is the best contact for these scenarios:</span></span>

- <span data-ttu-id="185e8-126">Вы не получили код проверки.</span><span class="sxs-lookup"><span data-stu-id="185e8-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="185e8-127">Процесс проверки не работал после отправки кода проверки.</span><span class="sxs-lookup"><span data-stu-id="185e8-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="185e8-128">Вы не уверены, является ли контактная информация для вашей кредитной карты правильной.</span><span class="sxs-lookup"><span data-stu-id="185e8-128">You're not sure if the contact info for your credit card is correct.</span></span>
