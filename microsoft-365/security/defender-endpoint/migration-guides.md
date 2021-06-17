---
title: Руководство по миграции, чтобы перейти на Microsoft Defender для конечной точки
description: Узнайте, как перейти из решения, не Microsoft 365 Defender в Microsoft Defender для конечной точки
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.custom: migrationguides
ms.reviewer: chriggs, depicker, yongrhee
f1.keywords: NOCSH
ms.date: 06/14/2021
ms.technology: mde
ms.openlocfilehash: 010cea14bebd4e29822b1826c0ec4577d53baca7
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964865"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="3c2c1-103">Переключение на Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c2c1-103">Make the switch to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="3c2c1-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3c2c1-104">**Applies to:**</span></span>
- [<span data-ttu-id="3c2c1-105">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c2c1-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3c2c1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c2c1-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3c2c1-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3c2c1-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3c2c1-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="3c2c1-109">Руководства по миграции</span><span class="sxs-lookup"><span data-stu-id="3c2c1-109">Migration guides</span></span>

<span data-ttu-id="3c2c1-110">Если вы рассматриваете возможность перехода в Defender для конечной точки, у нас есть рекомендации.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-110">If you're considering moving to Defender for Endpoint, we have guidance to help.</span></span> <span data-ttu-id="3c2c1-111">В следующей таблице просмотрите сценарии.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-111">In the following table, review the scenarios.</span></span> <span data-ttu-id="3c2c1-112">Выберите сценарий, который лучше всего представляет вашу ситуацию, и см. рекомендуемые рекомендации.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-112">Select the scenario that best represents your situation, and see the recommended guidance.</span></span>

| <span data-ttu-id="3c2c1-113">Сценарий</span><span class="sxs-lookup"><span data-stu-id="3c2c1-113">Scenario</span></span> | <span data-ttu-id="3c2c1-114">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="3c2c1-114">Guidance</span></span> |
|:----|:----|
| <span data-ttu-id="3c2c1-115">Решение для защиты конечной точки еще не установлено, и вы хотите узнать больше о Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-115">You don't have an endpoint protection solution in place yet, and you want to know more about Defender for Endpoint.</span></span> <span data-ttu-id="3c2c1-116">Перед развертыванием в среде необходимо узнать, как работает Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-116">You want to see how Defender for Endpoint works before rolling it out in your environment.</span></span>  | [<span data-ttu-id="3c2c1-117">Лаборатория оценки Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c2c1-117">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
| <span data-ttu-id="3c2c1-118">У вас уже есть Защитник для конечной точки, и вам нужна помощь в настройке и настройке всего.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-118">You already have Defender for Endpoint, and you want some help getting everything set up and configured.</span></span>  | [<span data-ttu-id="3c2c1-119">Руководство по развертыванию Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c2c1-119">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
| <span data-ttu-id="3c2c1-120">Планируется перейти от решения защиты конечных точек, не от Microsoft, к Defender for Endpoint и антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-120">You're planning to switch from a non-Microsoft endpoint protection solution to Defender for Endpoint and Microsoft Defender Antivirus.</span></span> <span data-ttu-id="3c2c1-121">Вы хотите получить обзор процесса миграции и как сделать переключатель.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-121">You want to get an overview of the migration process and how to make the switch.</span></span> |[<span data-ttu-id="3c2c1-122">Переключение на Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c2c1-122">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
| <span data-ttu-id="3c2c1-123">Вы уже мигрировали или перенаселились в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-123">You've already migrated or onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="3c2c1-124">Вам нужна помощь в следующих действиях, таких как управление настройками безопасности, настройка дополнительных функций или настройка политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-124">You want some help with next steps, such as managing your security settings, configuring more features, or fine-tuning your security policies.</span></span> | [<span data-ttu-id="3c2c1-125">Управление защитником Майкрософт для конечной точки после миграции</span><span class="sxs-lookup"><span data-stu-id="3c2c1-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="do-you-have-feedback-for-us"></a><span data-ttu-id="3c2c1-126">У вас есть отзывы для нас?</span><span class="sxs-lookup"><span data-stu-id="3c2c1-126">Do you have feedback for us?</span></span>

<span data-ttu-id="3c2c1-127">Дайте нам знать, что вы думаете!</span><span class="sxs-lookup"><span data-stu-id="3c2c1-127">Let us know what you think!</span></span> <span data-ttu-id="3c2c1-128">Отправка отзывов в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="3c2c1-129">Мы будем учитывать ваши отзывы, продолжая улучшать и добавлять в наши рекомендации по миграции.</span><span class="sxs-lookup"><span data-stu-id="3c2c1-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c2c1-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3c2c1-130">See also</span></span>

- [<span data-ttu-id="3c2c1-131">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c2c1-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="3c2c1-132">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c2c1-132">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="3c2c1-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c2c1-133">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
