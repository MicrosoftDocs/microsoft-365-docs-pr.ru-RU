---
title: Обзор сокращения направлений атак
ms.reviewer: ''
description: Узнайте о возможностях уменьшения поверхности атаки в Microsoft Defender для конечной точки.
keywords: asr, уменьшение поверхности атаки, Microsoft Defender для endpoint, защитник Майкрософт, антивирус, av, защитник Windows
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
ms.date: 06/02/2021
ms.openlocfilehash: 6b3c88f23d3ceffbca588c80b05266d12147ca39
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985028"
---
# <a name="overview-of-attack-surface-reduction-capabilities"></a><span data-ttu-id="ab795-104">Обзор возможностей уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="ab795-104">Overview of attack surface reduction capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ab795-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ab795-105">**Applies to:**</span></span>

- [<span data-ttu-id="ab795-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ab795-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab795-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab795-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="ab795-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ab795-108">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="ab795-109">[Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="ab795-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink).</span></span>

<span data-ttu-id="ab795-110">Поверхности атак — это все места, в которых ваша организация уязвима перед киберугрозами и атаками.</span><span class="sxs-lookup"><span data-stu-id="ab795-110">Attack surfaces are all the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="ab795-111">Defender for Endpoint включает несколько возможностей, которые помогут уменьшить количество поверхностей атак.</span><span class="sxs-lookup"><span data-stu-id="ab795-111">Defender for Endpoint includes several capabilities to help reduce your attack surfaces.</span></span> <span data-ttu-id="ab795-112">Просмотрите следующее видео, чтобы узнать больше о сокращении поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="ab795-112">Watch the following video to learn more about attack surface reduction.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a><span data-ttu-id="ab795-113">Ресурсы, чтобы узнать больше о снижении поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="ab795-113">Resources to learn more about attack surface reduction</span></span>

<span data-ttu-id="ab795-114">Как упоминалось в видео, Defender for Endpoint включает несколько возможностей уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="ab795-114">As mentioned in the video, Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="ab795-115">Дополнительные возможности использования следующих ресурсов:</span><span class="sxs-lookup"><span data-stu-id="ab795-115">Use the following resources to learn more:</span></span>

| <span data-ttu-id="ab795-116">Статья</span><span class="sxs-lookup"><span data-stu-id="ab795-116">Article</span></span> | <span data-ttu-id="ab795-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ab795-117">Description</span></span> |
|:---|:---|
| [<span data-ttu-id="ab795-118">Аппаратная изоляция</span><span class="sxs-lookup"><span data-stu-id="ab795-118">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="ab795-119">Защита и сохранение целостности системы по мере ее запуска и работы.</span><span class="sxs-lookup"><span data-stu-id="ab795-119">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="ab795-120">Проверка целостности системы с помощью локальной и удаленной проверки.</span><span class="sxs-lookup"><span data-stu-id="ab795-120">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="ab795-121">Использование изоляции контейнеров для Microsoft Edge защиты от вредоносных веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="ab795-121">Use container isolation for Microsoft Edge to help guard against malicious websites.</span></span> |
| [<span data-ttu-id="ab795-122">Элемент управления приложениями</span><span class="sxs-lookup"><span data-stu-id="ab795-122">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="ab795-123">Используйте управление приложениями, чтобы ваши приложения заработали доверие для запуска.</span><span class="sxs-lookup"><span data-stu-id="ab795-123">Use application control so that your applications must earn trust in order to run.</span></span> |
| [<span data-ttu-id="ab795-124">Контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="ab795-124">Controlled folder access</span></span>](controlled-folders.md) | <span data-ttu-id="ab795-125">Помогите предотвратить внесение изменений в файлы в папках ключевой системы (требуется антивирусная программа в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="ab795-125">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="ab795-126">Защита сети</span><span class="sxs-lookup"><span data-stu-id="ab795-126">Network protection</span></span>](network-protection.md) | <span data-ttu-id="ab795-127">Расширение защиты сетевого трафика и подключения на устройствах организации.</span><span class="sxs-lookup"><span data-stu-id="ab795-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="ab795-128">(Требуется антивирусная программа в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="ab795-128">(Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="ab795-129">Защита от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="ab795-129">Exploit protection</span></span>](exploit-protection.md) | <span data-ttu-id="ab795-130">Помогите защитить операционные системы и приложения, которые использует ваша организация, от использования.</span><span class="sxs-lookup"><span data-stu-id="ab795-130">Help protect the operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="ab795-131">Защита от эксплойтов также работает с сторонними антивирусными решениями.</span><span class="sxs-lookup"><span data-stu-id="ab795-131">Exploit protection also works with third-party antivirus solutions.</span></span> |
| [<span data-ttu-id="ab795-132">Правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="ab795-132">Attack surface reduction rules</span></span>](attack-surface-reduction.md) | <span data-ttu-id="ab795-133">Уменьшение уязвимостей (направлений атак) в ваших приложениях с помощью интеллектуальных правил, которые помогают остановить вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="ab795-133">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="ab795-134">(Требуется антивирусная программа в Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="ab795-134">(Requires Microsoft Defender Antivirus).</span></span> |
| [<span data-ttu-id="ab795-135">Управление устройством</span><span class="sxs-lookup"><span data-stu-id="ab795-135">Device control</span></span>](device-control-report.md) | <span data-ttu-id="ab795-136">Защищает от потери данных, отслеживая и контролируя средства массовой информации, используемые на устройствах, таких как съемные накопители и USB-накопители, в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ab795-136">Protects against data loss by monitoring and controlling media used on devices, such as removable storage and USB drives, in your organization.</span></span> |
