---
title: Настройка периода ожидания облачного блока антивирусной программы Microsoft Defender
description: Можно настроить продолжительность блокировки антивируса Microsoft Defender файла в ожидании определения облачности.
keywords: Антивирус Microsoft Defender, антивирусные программы, безопасность, защитник, облако, время ожидания, блок, период, секунд
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 372d679f45d6f87392b612f757e6bdf1c6c6b9ad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765807"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="cf5df-104">Настройка времени ожидания блокировки облака</span><span class="sxs-lookup"><span data-stu-id="cf5df-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cf5df-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cf5df-105">**Applies to:**</span></span>

- [<span data-ttu-id="cf5df-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cf5df-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cf5df-107">Когда антивирус Microsoft Defender находит подозрительный файл, он может запретить его работу во время запросов облачной службы [антивирусов Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="cf5df-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="cf5df-108">Период блокировки файла по [](configure-block-at-first-sight-microsoft-defender-antivirus.md) умолчанию составляет 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="cf5df-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="cf5df-109">Можно указать дополнительный период времени для ожидания запуска файла.</span><span class="sxs-lookup"><span data-stu-id="cf5df-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="cf5df-110">Это может помочь обеспечить достаточно времени для получения надлежащего определения от облачной службы антивирусной программы Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="cf5df-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="cf5df-111">Необходимые условия для использования растянутой облачной блокировки</span><span class="sxs-lookup"><span data-stu-id="cf5df-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="cf5df-112">[Блок на первый взгляд,](configure-block-at-first-sight-microsoft-defender-antivirus.md) и его необходимо включить, прежде чем указать расширенный период ожидания.</span><span class="sxs-lookup"><span data-stu-id="cf5df-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="cf5df-113">Укажите расширенный период ожидания</span><span class="sxs-lookup"><span data-stu-id="cf5df-113">Specify the extended timeout period</span></span>

<span data-ttu-id="cf5df-114">С помощью групповой политики можно указать расширенный период времени для облачных проверок.</span><span class="sxs-lookup"><span data-stu-id="cf5df-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="cf5df-115">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cf5df-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="cf5df-116">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="cf5df-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="cf5df-117">Расширь дерево до компонентов Windows > **Microsoft Defender > MpEngine**</span><span class="sxs-lookup"><span data-stu-id="cf5df-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="cf5df-118">Дважды **щелкните Настройка расширенной облачной проверки** и убедитесь, что параметр включен.</span><span class="sxs-lookup"><span data-stu-id="cf5df-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="cf5df-119">Укажите дополнительное время, чтобы не допустить запуска файла в ожидании определения облака.</span><span class="sxs-lookup"><span data-stu-id="cf5df-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="cf5df-120">Вы можете указать дополнительное время в секундах от 1 секунды до 50 секунд.</span><span class="sxs-lookup"><span data-stu-id="cf5df-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="cf5df-121">Это время будет добавлено к 10 секундам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf5df-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="cf5df-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cf5df-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf5df-123">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="cf5df-123">Related topics</span></span>

- [<span data-ttu-id="cf5df-124">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="cf5df-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="cf5df-125">Использование антивирусных технологий нового поколения с помощью облачной защиты</span><span class="sxs-lookup"><span data-stu-id="cf5df-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cf5df-126">Настройка блока с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="cf5df-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cf5df-127">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="cf5df-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)