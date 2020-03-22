---
title: Что поступает в показателях безопасности Майкрософт?
description: В этой статье описывается оценка безопасности Майкрософт в центре безопасности Майкрософт 365, вычисление сведений и возможные Администраторы безопасности.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, Оценка безопасности, центр безопасности, действия по улучшению
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895445"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="93d87-104">Что поступает в показателях безопасности Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="93d87-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="93d87-105">Чтобы сделать Microsoft Secure рейтинг более подходящим для вашей безопасности и улучшить удобство использования, мы будем вносить некоторые изменения в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="93d87-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="93d87-106">Ваш рейтинг и максимально возможный показатель будут меняться.</span><span class="sxs-lookup"><span data-stu-id="93d87-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="93d87-107">Однако это не подразумевает изменения в безопасности.</span><span class="sxs-lookup"><span data-stu-id="93d87-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="93d87-108">Чтобы узнать о последних изменениях, ознакомьтесь со статьей " [новые возможности оценки безопасности Майкрософт".](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="93d87-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="93d87-109">21 апреля 2020 г.</span><span class="sxs-lookup"><span data-stu-id="93d87-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="93d87-110">Удаление действий улучшения, которые не отвечают ожиданиям для надежного измерения, или не предоставляют удобного представления безопасности</span><span class="sxs-lookup"><span data-stu-id="93d87-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="93d87-111">Чтобы обеспечить осмысленность оценки безопасности Майкрософт и обеспечить надежность и надежность каждого действия по улучшению, мы удаляем следующие действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="93d87-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="93d87-112">Удаление и блокировка учетных записей, не использованных за последние 30 дней</span><span class="sxs-lookup"><span data-stu-id="93d87-112">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="93d87-113">Назначение меньше 5 глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="93d87-113">Designate fewer than 5 global admins</span></span>
- <span data-ttu-id="93d87-114">Применение защиты IRM к документам</span><span class="sxs-lookup"><span data-stu-id="93d87-114">Apply IRM protections to documents</span></span>
- <span data-ttu-id="93d87-115">Применение политик защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="93d87-115">Apply Data Loss Prevention policies</span></span>

### <a name="adding-additional-control-support-in-the-preview-version"></a><span data-ttu-id="93d87-116">Добавление поддержки дополнительных элементов управления в предварительной версии</span><span class="sxs-lookup"><span data-stu-id="93d87-116">Adding additional control support in the preview version</span></span>
- <span data-ttu-id="93d87-117">Не разрешать пользователям предоставлять согласие на неуправляемые приложения (в настоящее время доступно в выпущенной версии)</span><span class="sxs-lookup"><span data-stu-id="93d87-117">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a><span data-ttu-id="93d87-118">Поддержка дополнительных действий по улучшению безопасности облачного приложения Майкрософт</span><span class="sxs-lookup"><span data-stu-id="93d87-118">Support for additional Microsoft Cloud App Security improvement actions</span></span>
- <span data-ttu-id="93d87-119">Отключение службы диспетчера очереди печати на контроллерах домена</span><span class="sxs-lookup"><span data-stu-id="93d87-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="93d87-120">Изменение небезопасного делегирования Kerberos для предотвращения олицетворения</span><span class="sxs-lookup"><span data-stu-id="93d87-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="93d87-121">Защита и управление паролями локального администратора с помощью Microsoft ЛАПС</span><span class="sxs-lookup"><span data-stu-id="93d87-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="93d87-122">Снижение риска для пути перемещения Латерал к конфиденциальным объектам</span><span class="sxs-lookup"><span data-stu-id="93d87-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="93d87-123">Удаление неактивных учетных записей из конфиденциальных групп</span><span class="sxs-lookup"><span data-stu-id="93d87-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="93d87-124">Удаление атрибутов небезопасного журнала SID из сущностей</span><span class="sxs-lookup"><span data-stu-id="93d87-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="93d87-125">Разрешение небезопасных атрибутов учетной записи</span><span class="sxs-lookup"><span data-stu-id="93d87-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="93d87-126">Stop — неясное воздействие на текстовые учетные данные</span><span class="sxs-lookup"><span data-stu-id="93d87-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="93d87-127">Остановка связи устаревших протоколов</span><span class="sxs-lookup"><span data-stu-id="93d87-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="93d87-128">Остановка использования слабого шифра</span><span class="sxs-lookup"><span data-stu-id="93d87-128">Stop weak cipher usage</span></span>

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a><span data-ttu-id="93d87-129">Рекомендации по обеспечению безопасности системы безопасности & угрозам для защитника Майкрософт (ТВМ)</span><span class="sxs-lookup"><span data-stu-id="93d87-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations</span></span>
- <span data-ttu-id="93d87-130">Все Рекомендуемые рекомендации по обеспечению безопасности, предоставляемые ТВМ, будут также доступны в показателях безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="93d87-130">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
