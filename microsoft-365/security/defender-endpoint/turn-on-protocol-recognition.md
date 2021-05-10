---
title: Включив распознавание протокола для антивирусная программа в Microsoft Defender
description: Включи распознавание протокола для антивирусная программа в Microsoft Defender.
keywords: антивирусная программа в Microsoft Defender, антивирусное программное обеспечение, безопасность, защита, распознавание протоколов
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296493"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="0b3e4-104">Включив распознавание протокола</span><span class="sxs-lookup"><span data-stu-id="0b3e4-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0b3e4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0b3e4-105">**Applies to:**</span></span>

- [<span data-ttu-id="0b3e4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0b3e4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0b3e4-107">Этот параметр политики позволяет настроить распознавание протоколов для защиты сети от эксплойтов известных уязвимостей.</span><span class="sxs-lookup"><span data-stu-id="0b3e4-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="0b3e4-108">Если включить или не настроить этот параметр, будет включено распознавание протокола.</span><span class="sxs-lookup"><span data-stu-id="0b3e4-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="0b3e4-109">Если отключить этот параметр, распознавание протокола будет отключено.</span><span class="sxs-lookup"><span data-stu-id="0b3e4-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="0b3e4-110">Использование групповой политики для настройки распознавания протоколов</span><span class="sxs-lookup"><span data-stu-id="0b3e4-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="0b3e4-111">На конечной точке управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="0b3e4-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="0b3e4-112">Перейдите **к административным** шаблонам конфигурации  >    >  **компьютера Windows компонентов**  >  **антивирусная программа в Microsoft Defender**  >  **сетевой системы проверки.**</span><span class="sxs-lookup"><span data-stu-id="0b3e4-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="0b3e4-113">Выберите **распознавание протокола.**</span><span class="sxs-lookup"><span data-stu-id="0b3e4-113">Select **protocol recognition**.</span></span> <span data-ttu-id="0b3e4-114">По умолчанию эта политика включена.</span><span class="sxs-lookup"><span data-stu-id="0b3e4-114">By default, this policy is enabled.</span></span> <span data-ttu-id="0b3e4-115">Если набор **не настроен,** включено определение выхода на пенсию.</span><span class="sxs-lookup"><span data-stu-id="0b3e4-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="0b3e4-116">Чтобы изменить политику, выберите ссылку **параметра политики** редактирования.</span><span class="sxs-lookup"><span data-stu-id="0b3e4-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="0b3e4-117">Выберите **включено,** а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0b3e4-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="0b3e4-118">Развертывание обновленного объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="0b3e4-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="0b3e4-119">См. [консоль управления групповой политикой.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="0b3e4-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="0b3e4-120">Вы используете объекты групповой политики в помещениях?</span><span class="sxs-lookup"><span data-stu-id="0b3e4-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="0b3e4-121">Узнайте, как они переводятся в облаке.</span><span class="sxs-lookup"><span data-stu-id="0b3e4-121">See how they translate in the cloud.</span></span> <span data-ttu-id="0b3e4-122">[Анализ объектов локальной групповой политики](/mem/intune/configuration/group-policy-analytics)с помощью аналитики групповой политики в Microsoft Endpoint Manager - Preview .</span><span class="sxs-lookup"><span data-stu-id="0b3e4-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="0b3e4-123">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0b3e4-123">Related articles</span></span>

- [<span data-ttu-id="0b3e4-124">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="0b3e4-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="0b3e4-125">Включение облачной защиты</span><span class="sxs-lookup"><span data-stu-id="0b3e4-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="0b3e4-126">Создание и развертывание политик противомалярийных программ: служба облачной защиты</span><span class="sxs-lookup"><span data-stu-id="0b3e4-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)