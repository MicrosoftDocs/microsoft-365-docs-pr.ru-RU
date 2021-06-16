---
title: Включить ограниченную функцию антивирусная программа в Microsoft Defender проверки
description: Ограниченное периодическое сканирование позволяет использовать антивирусная программа в Microsoft Defender в дополнение к другим установленным поставщикам av
keywords: LPS, ограниченное, периодическое, сканирование, сканирование, совместимость, 3-я сторона, другое av, отключение
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad49b08e687f4ba389616542bd607d4140e91132
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926695"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="93b19-104">Использование ограниченного периодического сканирования в антивирусной программе в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="93b19-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="93b19-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="93b19-105">**Applies to:**</span></span>

- [<span data-ttu-id="93b19-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="93b19-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="93b19-107">Ограниченное периодическое сканирование — это особый тип обнаружения и устранения угроз, который можно включить при установке другого антивирусного продукта на Windows 10 устройстве.</span><span class="sxs-lookup"><span data-stu-id="93b19-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="93b19-108">Его можно включить только в определенных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="93b19-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="93b19-109">Дополнительные сведения о ограниченном периодичное сканирование и антивирусная программа в Microsoft Defender других антивирусных продуктов см. в антивирусная программа в Microsoft Defender [совместимости.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="93b19-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="93b19-110">**Корпорация Майкрософт не рекомендует использовать эту функцию в корпоративных средах. Это функция, предназначенная в первую очередь для потребителей.**</span><span class="sxs-lookup"><span data-stu-id="93b19-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="93b19-111">Эта функция использует только ограниченный подмножество возможностей антивирусная программа в Microsoft Defender для обнаружения вредоносных программ, и не сможет обнаружить большинство вредоносных программ и потенциально нежелательного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="93b19-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="93b19-112">Кроме того, возможности управления и отчетности будут ограничены.</span><span class="sxs-lookup"><span data-stu-id="93b19-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="93b19-113">Корпорация Майкрософт рекомендует предприятиям выбирать основное антивирусное решение и использовать его исключительно.</span><span class="sxs-lookup"><span data-stu-id="93b19-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="93b19-114">Как включить ограниченное периодическое сканирование</span><span class="sxs-lookup"><span data-stu-id="93b19-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="93b19-115">По умолчанию антивирусная программа в Microsoft Defender включить себя на устройстве Windows 10, если не установлен другой антивирусный продукт, или если другой продукт устарел, истек или не работает правильно.</span><span class="sxs-lookup"><span data-stu-id="93b19-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="93b19-116">Если антивирусная программа в Microsoft Defender включена, будут отображаться обычные параметры для настройки на этом устройстве:</span><span class="sxs-lookup"><span data-stu-id="93b19-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![Безопасность Windows приложение, показывающая параметры av Microsoft Defender, включая параметры сканирования, параметры и параметры обновления](images/vtp-wdav.png)

<span data-ttu-id="93b19-118">Если другой антивирусный продукт установлен и работает правильно, антивирусная программа в Microsoft Defender отключится.</span><span class="sxs-lookup"><span data-stu-id="93b19-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="93b19-119">Приложение Безопасность Windows изменит раздел защиты  & вирусов, чтобы показать состояние продукта AV и укажите ссылку на параметры конфигурации продукта.</span><span class="sxs-lookup"><span data-stu-id="93b19-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="93b19-120">Под любыми сторонними продуктами AV появится новая ссылка в **антивирусная программа в Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="93b19-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="93b19-121">Щелкните эту ссылку, чтобы показать перегной, который позволяет ограниченное периодическое сканирование.</span><span class="sxs-lookup"><span data-stu-id="93b19-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="93b19-122">Обратите внимание, что ограниченный периодический параметр — это переключеть, чтобы включить или отключить периодическое сканирование.</span><span class="sxs-lookup"><span data-stu-id="93b19-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="93b19-123">При сдвижном переходе **на Включен** будет покажите стандартные параметры AV Microsoft Defender под сторонним продуктом AV.</span><span class="sxs-lookup"><span data-stu-id="93b19-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="93b19-124">Ограниченный вариант периодического сканирования появится в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="93b19-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="93b19-125">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="93b19-125">Related articles</span></span>

- [<span data-ttu-id="93b19-126">Настройка поведенческой, эвристической защиты и защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="93b19-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="93b19-127">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="93b19-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)