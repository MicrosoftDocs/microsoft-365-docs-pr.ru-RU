---
title: Обзор уменьшения поверхности атаки
ms.reviewer: ''
description: Узнайте о возможностях по уменьшению поверхности атаки в ATP Microsoft Defender.
keywords: asr, уменьшение поверхности атаки, atp защитника Майкрософт, защитник Microsoft для конечной точки, защитник Майкрософт, антивирус, av, защитник Windows
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e4e10ba82ec344449b003c0a9cc9d27d99047005
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186249"
---
# <a name="overview-of-attack-surface-reduction"></a><span data-ttu-id="c680f-104">Обзор уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="c680f-104">Overview of attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c680f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c680f-105">**Applies to:**</span></span>
- [<span data-ttu-id="c680f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c680f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c680f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c680f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c680f-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c680f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c680f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c680f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="c680f-110">Помогите уменьшить поверхности атак, минимизируя места, в которых ваша организация уязвима для киберугроз и атак.</span><span class="sxs-lookup"><span data-stu-id="c680f-110">Help reduce your attack surfaces, by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="c680f-111">Используйте следующие ресурсы для настройки защиты устройств и приложений в организации.</span><span class="sxs-lookup"><span data-stu-id="c680f-111">Use the following resources to configure protection for the devices and applications in your organization.</span></span>


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]


<span data-ttu-id="c680f-112">Статья</span><span class="sxs-lookup"><span data-stu-id="c680f-112">Article</span></span> | <span data-ttu-id="c680f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c680f-113">Description</span></span>
-|-
[<span data-ttu-id="c680f-114">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="c680f-114">Attack surface reduction</span></span>](./attack-surface-reduction.md) | <span data-ttu-id="c680f-115">Уменьшение уязвимостей (направлений атак) в ваших приложениях с помощью интеллектуальных правил, которые помогают остановить вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="c680f-115">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="c680f-116">(Требуется антивирус Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="c680f-116">(Requires Microsoft Defender Antivirus).</span></span>
[<span data-ttu-id="c680f-117">Изолирование на основе оборудования</span><span class="sxs-lookup"><span data-stu-id="c680f-117">Hardware-based isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="c680f-118">Защита и сохранение целостности системы по мере ее запуска и работы.</span><span class="sxs-lookup"><span data-stu-id="c680f-118">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="c680f-119">Проверка целостности системы с помощью локальной и удаленной проверки.</span><span class="sxs-lookup"><span data-stu-id="c680f-119">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="c680f-120">Кроме того, используйте изоляцию контейнеров для Microsoft Edge, чтобы защититься от вредоносных веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="c680f-120">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span>
[<span data-ttu-id="c680f-121">Элемент управления приложениями</span><span class="sxs-lookup"><span data-stu-id="c680f-121">Application control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control.md) | <span data-ttu-id="c680f-122">Используйте управление приложениями, чтобы ваши приложения заработали доверие для запуска.</span><span class="sxs-lookup"><span data-stu-id="c680f-122">Use application control so that your applications must earn trust in order to run.</span></span>
[<span data-ttu-id="c680f-123">Защита от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="c680f-123">Exploit protection</span></span>](./exploit-protection.md) | <span data-ttu-id="c680f-124">Защита операционных систем и приложений, которые использует организация, от использования.</span><span class="sxs-lookup"><span data-stu-id="c680f-124">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="c680f-125">Защита от эксплойтов также работает с сторонними антивирусными решениями.</span><span class="sxs-lookup"><span data-stu-id="c680f-125">Exploit protection also works with third-party antivirus solutions.</span></span>
[<span data-ttu-id="c680f-126">Защита сети</span><span class="sxs-lookup"><span data-stu-id="c680f-126">Network protection</span></span>](./network-protection.md) | <span data-ttu-id="c680f-127">Расширение защиты сетевого трафика и подключения на устройствах организации.</span><span class="sxs-lookup"><span data-stu-id="c680f-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="c680f-128">(Требуется антивирус Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="c680f-128">(Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="c680f-129">Веб-защита</span><span class="sxs-lookup"><span data-stu-id="c680f-129">Web protection</span></span>](./web-protection-overview.md) | <span data-ttu-id="c680f-130">Защита устройств от веб-угроз и регулирование нежелательного контента.</span><span class="sxs-lookup"><span data-stu-id="c680f-130">Secure your devices against web threats and help you regulate unwanted content.</span></span>
[<span data-ttu-id="c680f-131">Управляемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="c680f-131">Controlled folder access</span></span>](./controlled-folders.md) | <span data-ttu-id="c680f-132">Помогите предотвратить внесение изменений в файлы в папках ключевой системы (требуется антивирус Microsoft Defender) для предотвращения изменения вредоносных или подозрительных приложений (в том числе вредоносных программ-вымогателей с шифрованием файлов).</span><span class="sxs-lookup"><span data-stu-id="c680f-132">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="c680f-133">Брандмауэр сети</span><span class="sxs-lookup"><span data-stu-id="c680f-133">Network firewall</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security.md) | <span data-ttu-id="c680f-134">Запретить несанкционированный трафик на устройства или с устройств организации с помощью фильтрации сетевого трафика.</span><span class="sxs-lookup"><span data-stu-id="c680f-134">Prevent unauthorized traffic from flowing to or from your organization's devices with two-way network traffic filtering.</span></span>
[<span data-ttu-id="c680f-135">FaQ уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="c680f-135">Attack surface reduction FAQ</span></span>](./attack-surface-reduction-faq.md) | <span data-ttu-id="c680f-136">Часто задают вопросы о правилах уменьшения поверхности attack, лицензировании и других.</span><span class="sxs-lookup"><span data-stu-id="c680f-136">Frequently asked questions about Attack surface reduction rules, licensing, and more.</span></span>