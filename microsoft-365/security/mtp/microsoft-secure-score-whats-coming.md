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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541111"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="63742-104">Что поступает в показателях безопасности Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="63742-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="63742-105">Чтобы сделать Microsoft Secure рейтинг более подходящим для вашей безопасности и улучшить удобство использования, мы будем вносить некоторые изменения в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="63742-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="63742-106">Ваш рейтинг и максимально возможный показатель будут меняться.</span><span class="sxs-lookup"><span data-stu-id="63742-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="63742-107">Однако это не подразумевает изменения в безопасности.</span><span class="sxs-lookup"><span data-stu-id="63742-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="63742-108">Чтобы узнать о последних изменениях, ознакомьтесь со статьей " [новые возможности оценки безопасности Майкрософт".](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="63742-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="63742-109">21 апреля 2020 г.</span><span class="sxs-lookup"><span data-stu-id="63742-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="63742-110">Удаление действий улучшения, которые не отвечают ожиданиям для надежного измерения, или не предоставляют удобного представления безопасности</span><span class="sxs-lookup"><span data-stu-id="63742-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="63742-111">Чтобы обеспечить осмысленность оценки безопасности Майкрософт и обеспечить надежность и надежность каждого действия по улучшению, мы удаляем следующие действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="63742-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="63742-112">Применение защиты IRM к документам</span><span class="sxs-lookup"><span data-stu-id="63742-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="63742-113">Применение политик защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="63742-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a><span data-ttu-id="63742-114">Добавление действия по улучшению Azure AD в предварительной версии</span><span class="sxs-lookup"><span data-stu-id="63742-114">Adding Azure AD improvement action in the preview version</span></span>

- <span data-ttu-id="63742-115">Не разрешать пользователям предоставлять согласие на неуправляемые приложения (в настоящее время доступно в выпущенной версии)</span><span class="sxs-lookup"><span data-stu-id="63742-115">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a><span data-ttu-id="63742-116">Добавление действий по улучшению Azure ATP в предварительной версии</span><span class="sxs-lookup"><span data-stu-id="63742-116">Adding Azure ATP improvement actions in the preview version</span></span>

- <span data-ttu-id="63742-117">Отключение службы диспетчера очереди печати на контроллерах домена</span><span class="sxs-lookup"><span data-stu-id="63742-117">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="63742-118">Изменение небезопасного делегирования Kerberos для предотвращения олицетворения</span><span class="sxs-lookup"><span data-stu-id="63742-118">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="63742-119">Защита и управление паролями локального администратора с помощью Microsoft ЛАПС</span><span class="sxs-lookup"><span data-stu-id="63742-119">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="63742-120">Снижение риска для пути перемещения Латерал к конфиденциальным объектам</span><span class="sxs-lookup"><span data-stu-id="63742-120">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="63742-121">Удаление неактивных учетных записей из конфиденциальных групп</span><span class="sxs-lookup"><span data-stu-id="63742-121">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="63742-122">Удаление атрибутов небезопасного журнала SID из сущностей</span><span class="sxs-lookup"><span data-stu-id="63742-122">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="63742-123">Разрешение небезопасных атрибутов учетной записи</span><span class="sxs-lookup"><span data-stu-id="63742-123">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="63742-124">Stop — неясное воздействие на текстовые учетные данные</span><span class="sxs-lookup"><span data-stu-id="63742-124">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="63742-125">Остановка связи устаревших протоколов</span><span class="sxs-lookup"><span data-stu-id="63742-125">Stop legacy protocols communication</span></span>
- <span data-ttu-id="63742-126">Остановка использования слабого шифра</span><span class="sxs-lookup"><span data-stu-id="63742-126">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a><span data-ttu-id="63742-127">Рекомендации по обеспечению безопасности & угрозам безопасности для защитника Майкрософт (ТВМ) в предварительной версии</span><span class="sxs-lookup"><span data-stu-id="63742-127">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in the preview version</span></span>

- <span data-ttu-id="63742-128">Все Рекомендуемые рекомендации по обеспечению безопасности, предоставляемые ТВМ, будут также доступны в показателях безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="63742-128">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
