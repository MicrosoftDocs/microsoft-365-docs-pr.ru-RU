---
title: Директива платежных служб 2 и прочная проверка подлинности клиентов для коммерческих клиентов
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: С 14 сентября 2019 г. банкам в 31 странах Европейской зоны необходимо проверить личность человека, который делает покупку через Интернет, прежде чем платеж будет обработан".
keywords: директива платежных служб 2, прочная проверка подлинности клиентов, многофакторная проверка подлинности
ms.openlocfilehash: d6564a8c6d31bd0758f1084e7ee9b6857aed034e
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906613"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="7dcba-104">Директива платежных служб 2 и прочная проверка подлинности клиентов для коммерческих клиентов</span><span class="sxs-lookup"><span data-stu-id="7dcba-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="7dcba-105">С 14 сентября 2019 г. банкам в 31 странах Европейской зоны необходимо проверить удостоверение лица, выдающего покупку через Интернет, прежде чем платеж будет обработан.</span><span class="sxs-lookup"><span data-stu-id="7dcba-105">As of September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="7dcba-106">Для этой проверки требуется многофакторная проверка подлинности, чтобы обеспечить безопасность и защиту покупок через Интернет.</span><span class="sxs-lookup"><span data-stu-id="7dcba-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="7dcba-107">Дата для этого требования будет отложена для некоторых стран.</span><span class="sxs-lookup"><span data-stu-id="7dcba-107">The date for this verification requirement will be delayed for some countries.</span></span>

<span data-ttu-id="7dcba-108">Дополнительные сведения см. в [faq microsoft about Payment Services Directive 2 and Strong Customer Authentication.](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)</span><span class="sxs-lookup"><span data-stu-id="7dcba-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="7dcba-109">Когда требуется многофакторная проверка подлинности?</span><span class="sxs-lookup"><span data-stu-id="7dcba-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="7dcba-110">В настоящее время требования проверки для этой директивы с использованием многофакторной проверки подлинности применяются только к клиентам, использующим кредитные карты из банков в 31 странах Европейской экономической зоны.</span><span class="sxs-lookup"><span data-stu-id="7dcba-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="7dcba-111">Иногда клиентам будет предложено действие, которое они приняли, а иногда — из-за событий с существующими подписками или службами.</span><span class="sxs-lookup"><span data-stu-id="7dcba-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="7dcba-112">Действия клиента</span><span class="sxs-lookup"><span data-stu-id="7dcba-112">Customer Actions</span></span>

<span data-ttu-id="7dcba-113">Вашему банку может потребоваться проверка с помощью многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7dcba-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="7dcba-114">Вот некоторые примеры:</span><span class="sxs-lookup"><span data-stu-id="7dcba-114">Some examples include:</span></span>
- <span data-ttu-id="7dcba-115">Регистрация для новой подписки</span><span class="sxs-lookup"><span data-stu-id="7dcba-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="7dcba-116">Добавление лицензий в подписку</span><span class="sxs-lookup"><span data-stu-id="7dcba-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="7dcba-117">Добавление или замена кредитной карты, используемой для оплаты подписки или службы</span><span class="sxs-lookup"><span data-stu-id="7dcba-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="7dcba-118">Добавление или замена кредитной карты в профиле вычета</span><span class="sxs-lookup"><span data-stu-id="7dcba-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="7dcba-119">Приобретение приложений</span><span class="sxs-lookup"><span data-stu-id="7dcba-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="7dcba-120">События жизненного цикла подписки</span><span class="sxs-lookup"><span data-stu-id="7dcba-120">Subscription lifecycle events</span></span>

<span data-ttu-id="7dcba-121">Оплата за повторяющиеся платежи может привести к сбойу.</span><span class="sxs-lookup"><span data-stu-id="7dcba-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="7dcba-122">В этом случае вы получите сообщение электронной почты с инструкциями.</span><span class="sxs-lookup"><span data-stu-id="7dcba-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="7dcba-123">Вам будет предложено ответить на запрос на проверку и внести текущий платеж.</span><span class="sxs-lookup"><span data-stu-id="7dcba-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="7dcba-124">Нужна дополнительная помощь?</span><span class="sxs-lookup"><span data-stu-id="7dcba-124">Need more help?</span></span>

<span data-ttu-id="7dcba-125">Финансовое учреждение является лучшим контактом для этих сценариев:</span><span class="sxs-lookup"><span data-stu-id="7dcba-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="7dcba-126">Код проверки не был вы получите.</span><span class="sxs-lookup"><span data-stu-id="7dcba-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="7dcba-127">Процесс проверки не работал после отправки кода проверки.</span><span class="sxs-lookup"><span data-stu-id="7dcba-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="7dcba-128">Вы не знаете, правильны ли контактные данные для вашей кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="7dcba-128">You're not sure if the contact info for your credit card is correct.</span></span>
