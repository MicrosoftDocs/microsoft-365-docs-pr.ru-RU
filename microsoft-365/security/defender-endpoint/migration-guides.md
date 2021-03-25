---
title: Руководство по миграции, чтобы перейти на Microsoft Defender для конечной точки
description: Узнайте, как перейти от решения защиты от угроз, не от Microsoft, к Microsoft Defender для endpoint
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
ms.date: 09/24/2020
ms.technology: mde
ms.openlocfilehash: a56153a9c4076b1072f6d3fc5296f9e12dc0cc4d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186597"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint-and-microsoft-defender-antivirus"></a><span data-ttu-id="288d7-103">Переключение на Microsoft Defender для конечной точки и антивирус Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="288d7-103">Make the switch to Microsoft Defender for Endpoint and Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="288d7-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="288d7-104">**Applies to:**</span></span>
- [<span data-ttu-id="288d7-105">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="288d7-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="288d7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="288d7-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="288d7-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="288d7-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="288d7-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="288d7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="288d7-109">Руководство по миграции</span><span class="sxs-lookup"><span data-stu-id="288d7-109">Migration guides</span></span>

<span data-ttu-id="288d7-110">Если вы рассматриваете возможность перехода от решения защиты от угроз, не от Microsoft, к Microsoft Defender для конечной точки с антивирусной программой Microsoft Defender, ознакомьтесь с нашими рекомендациями по миграции.</span><span class="sxs-lookup"><span data-stu-id="288d7-110">If you're considering switching from a non-Microsoft threat protection solution to Microsoft Defender for Endpoint with Microsoft Defender Antivirus, check out our migration guidance.</span></span> <span data-ttu-id="288d7-111">Выберите сценарий, который лучше всего представляет, где вы находитесь в процессе развертывания, и см. инструкции.</span><span class="sxs-lookup"><span data-stu-id="288d7-111">Select the scenario that best represents where you are in your deployment process, and see the guidance.</span></span>

|<span data-ttu-id="288d7-112">Сценарий</span><span class="sxs-lookup"><span data-stu-id="288d7-112">Scenario</span></span> |<span data-ttu-id="288d7-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="288d7-113">Guidance</span></span> |
|:--|:--|
|<span data-ttu-id="288d7-114">Решение для защиты конечной точки еще не найдено, и вы хотите узнать больше о том, как работает антивирус Microsoft Defender для endpoint & Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="288d7-114">You do not have an endpoint protection solution yet, and you want to know more about how Microsoft Defender for Endpoint & Microsoft Defender Antivirus work.</span></span>  |[<span data-ttu-id="288d7-115">Лаборатория оценки Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="288d7-115">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
|<span data-ttu-id="288d7-116">У вас есть microsoft Defender для endpoint & Антивирус Microsoft Defender и нужна помощь в настройке и настройке всего.</span><span class="sxs-lookup"><span data-stu-id="288d7-116">You have Microsoft Defender for Endpoint & Microsoft Defender Antivirus and need some help getting everything set up and configured.</span></span>  |[<span data-ttu-id="288d7-117">Руководство по развертыванию Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="288d7-117">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
|<span data-ttu-id="288d7-118">Планируется перейти из McAfee Endpoint Security (McAfee) в Microsoft Defender для конечной точки & антивирус Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="288d7-118">You're planning to migrate from McAfee Endpoint Security (McAfee) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="288d7-119">Переключиться с McAfee на Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="288d7-119">Switch from McAfee to Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-migration.md) |
|<span data-ttu-id="288d7-120">Планируется перейти из Symantec Endpoint Protection (Symantec) в Microsoft Defender для конечной точки & антивирус Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="288d7-120">You're planning to migrate from Symantec Endpoint Protection (Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="288d7-121">Переход от Symantec к Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="288d7-121">Switch from Symantec to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-migration.md) |
|<span data-ttu-id="288d7-122">Планируется перейти из решения по защите конечных точек, не в microsoft (кроме McAfee или Symantec) в антивирус Microsoft Defender для endpoint & Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="288d7-122">You're planning to migrate from a non-Microsoft endpoint protection solution (other than McAfee or Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="288d7-123">Переключение на Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="288d7-123">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
|<span data-ttu-id="288d7-124">Вы мигрировали в Microsoft Defender для endpoint & антивирус Microsoft Defender, и вам нужна помощь в следующих действиях, таких как настройка дополнительных функций или настройка параметров безопасности.</span><span class="sxs-lookup"><span data-stu-id="288d7-124">You've migrated to Microsoft Defender for Endpoint & Microsoft Defender Antivirus, and you need help with next steps, such as configuring additional features or fine-tuning your security settings.</span></span> | [<span data-ttu-id="288d7-125">Управление защитником Майкрософт для конечной точки после миграции</span><span class="sxs-lookup"><span data-stu-id="288d7-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="got-feedback"></a><span data-ttu-id="288d7-126">Есть отзывы?</span><span class="sxs-lookup"><span data-stu-id="288d7-126">Got feedback?</span></span>

<span data-ttu-id="288d7-127">Дайте нам знать, что вы думаете!</span><span class="sxs-lookup"><span data-stu-id="288d7-127">Let us know what you think!</span></span> <span data-ttu-id="288d7-128">Отправка отзывов в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="288d7-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="288d7-129">Мы будем учитывать ваши отзывы, продолжая улучшать и добавлять в наши рекомендации по миграции.</span><span class="sxs-lookup"><span data-stu-id="288d7-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="288d7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="288d7-130">See also</span></span>

- [<span data-ttu-id="288d7-131">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="288d7-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
- [<span data-ttu-id="288d7-132">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="288d7-132">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [<span data-ttu-id="288d7-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="288d7-133">Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection?) 
