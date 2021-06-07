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
ms.openlocfilehash: b6fb9bb327816b7e166a443a0d07932d30421a19
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771697"
---
# <a name="overview-of-attack-surface-reduction-capabilities"></a><span data-ttu-id="a892b-104">Обзор возможностей уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="a892b-104">Overview of attack surface reduction capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a892b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a892b-105">**Applies to:**</span></span>
- [<span data-ttu-id="a892b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a892b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a892b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a892b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="a892b-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a892b-108">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="a892b-109">[Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="a892b-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink).</span></span>

<span data-ttu-id="a892b-110">Поверхности атак — это все места, в которых ваша организация уязвима для киберугроз и атак.</span><span class="sxs-lookup"><span data-stu-id="a892b-110">Your attack surfaces are all the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="a892b-111">Defender for Endpoint включает несколько возможностей, которые помогут уменьшить количество поверхностей атак.</span><span class="sxs-lookup"><span data-stu-id="a892b-111">Defender for Endpoint includes several capabilities to help reduce your attack surfaces.</span></span> <span data-ttu-id="a892b-112">Просмотрите следующее видео, чтобы узнать больше о сокращении поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="a892b-112">Watch the following video to learn more about attack surface reduction.</span></span><p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a><span data-ttu-id="a892b-113">Ресурсы, чтобы узнать больше о снижении поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="a892b-113">Resources to learn more about attack surface reduction</span></span>

<span data-ttu-id="a892b-114">Как упоминалось в видео, Defender for Endpoint включает несколько возможностей уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="a892b-114">As mentioned in the video, Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="a892b-115">Дополнительные возможности использования следующих ресурсов:</span><span class="sxs-lookup"><span data-stu-id="a892b-115">Use the following resources to learn more:</span></span>

| <span data-ttu-id="a892b-116">Статья</span><span class="sxs-lookup"><span data-stu-id="a892b-116">Article</span></span> | <span data-ttu-id="a892b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a892b-117">Description</span></span> |
|:---|:---|
| [<span data-ttu-id="a892b-118">Аппаратная изоляция</span><span class="sxs-lookup"><span data-stu-id="a892b-118">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="a892b-119">Защита и сохранение целостности системы по мере ее запуска и работы.</span><span class="sxs-lookup"><span data-stu-id="a892b-119">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="a892b-120">Проверка целостности системы с помощью локальной и удаленной проверки.</span><span class="sxs-lookup"><span data-stu-id="a892b-120">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="a892b-121">И используйте изоляцию контейнеров для Microsoft Edge защиты от вредоносных веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="a892b-121">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span> |
| [<span data-ttu-id="a892b-122">Элемент управления приложениями</span><span class="sxs-lookup"><span data-stu-id="a892b-122">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="a892b-123">Используйте управление приложениями, чтобы ваши приложения заработали доверие для запуска.</span><span class="sxs-lookup"><span data-stu-id="a892b-123">Use application control so that your applications must earn trust in order to run.</span></span> |
| [<span data-ttu-id="a892b-124">Контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="a892b-124">Controlled folder access</span></span>](controlled-folders.md) | <span data-ttu-id="a892b-125">Помогите предотвратить внесение изменений в файлы в папках ключевой системы (требуется антивирусная программа в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="a892b-125">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="a892b-126">Защита сети</span><span class="sxs-lookup"><span data-stu-id="a892b-126">Network protection</span></span>](network-protection.md) | <span data-ttu-id="a892b-127">Расширение защиты сетевого трафика и подключения на устройствах организации.</span><span class="sxs-lookup"><span data-stu-id="a892b-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="a892b-128">(Требуется антивирусная программа в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="a892b-128">(Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="a892b-129">Защита от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="a892b-129">Exploit protection</span></span>](exploit-protection.md) | <span data-ttu-id="a892b-130">Защита операционных систем и приложений, которые использует организация, от использования.</span><span class="sxs-lookup"><span data-stu-id="a892b-130">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="a892b-131">Защита от эксплойтов также работает с сторонними антивирусными решениями.</span><span class="sxs-lookup"><span data-stu-id="a892b-131">Exploit protection also works with third-party antivirus solutions.</span></span> |
| [<span data-ttu-id="a892b-132">Правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="a892b-132">Attack surface reduction rules</span></span>](attack-surface-reduction.md) | <span data-ttu-id="a892b-133">Уменьшение уязвимостей (направлений атак) в ваших приложениях с помощью интеллектуальных правил, которые помогают остановить вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="a892b-133">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="a892b-134">(Требуется антивирусная программа в Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="a892b-134">(Requires Microsoft Defender Antivirus).</span></span> |
| [<span data-ttu-id="a892b-135">Управление устройством</span><span class="sxs-lookup"><span data-stu-id="a892b-135">Device control</span></span>](device-control-report.md) | <span data-ttu-id="a892b-136">Защищает от потери данных, отслеживая и контролируя средства массовой информации, используемые на устройствах, таких как съемные накопители и USB-накопители, в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a892b-136">Protects against data loss by monitoring and controlling media used on devices, such as removable storage and USB drives, in your organization.</span></span> |