---
title: Настройка периода ожидания облачного блока антивирусной программы Microsoft Defender
description: Можно настроить продолжительность блокировки антивируса Microsoft Defender файла в ожидании определения облачности.
keywords: Антивирус Microsoft Defender, антивирусные программы, безопасность, защитник, облако, время ожидания, блок, период, секунд
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691064"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="49d18-104">Настройка периода ожидания облачного блока</span><span class="sxs-lookup"><span data-stu-id="49d18-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="49d18-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="49d18-105">**Applies to:**</span></span>

- [<span data-ttu-id="49d18-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="49d18-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="49d18-107">Когда антивирус Microsoft Defender находит подозрительный файл, он может запретить его работу во время запросов облачной службы [антивирусов Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="49d18-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="49d18-108">Период блокировки файла по [](configure-block-at-first-sight-microsoft-defender-antivirus.md) умолчанию составляет 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="49d18-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="49d18-109">Можно указать дополнительный период времени для ожидания запуска файла.</span><span class="sxs-lookup"><span data-stu-id="49d18-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="49d18-110">Это может помочь обеспечить достаточно времени для получения надлежащего определения от облачной службы антивирусной программы Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="49d18-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="49d18-111">Необходимые условия для использования растянутой облачной блокировки</span><span class="sxs-lookup"><span data-stu-id="49d18-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="49d18-112">[Блок на первый взгляд,](configure-block-at-first-sight-microsoft-defender-antivirus.md) и его необходимо включить, прежде чем указать расширенный период ожидания.</span><span class="sxs-lookup"><span data-stu-id="49d18-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="49d18-113">Укажите расширенный период ожидания</span><span class="sxs-lookup"><span data-stu-id="49d18-113">Specify the extended timeout period</span></span>

<span data-ttu-id="49d18-114">С помощью групповой политики можно указать расширенный период времени для облачных проверок.</span><span class="sxs-lookup"><span data-stu-id="49d18-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="49d18-115">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="49d18-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="49d18-116">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="49d18-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="49d18-117">Расширь дерево до компонентов Windows > **Microsoft Defender > MpEngine**</span><span class="sxs-lookup"><span data-stu-id="49d18-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="49d18-118">Дважды **щелкните Настройка расширенной облачной проверки** и убедитесь, что параметр включен.</span><span class="sxs-lookup"><span data-stu-id="49d18-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="49d18-119">Укажите дополнительное время, чтобы не допустить запуска файла в ожидании определения облака.</span><span class="sxs-lookup"><span data-stu-id="49d18-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="49d18-120">Вы можете указать дополнительное время в секундах от 1 секунды до 50 секунд.</span><span class="sxs-lookup"><span data-stu-id="49d18-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="49d18-121">Это время будет добавлено к 10 секундам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="49d18-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="49d18-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="49d18-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="49d18-123">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="49d18-123">Related topics</span></span>

- [<span data-ttu-id="49d18-124">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="49d18-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="49d18-125">Использование антивирусных технологий нового поколения с помощью облачной защиты</span><span class="sxs-lookup"><span data-stu-id="49d18-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="49d18-126">Настройка блока с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="49d18-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="49d18-127">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="49d18-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)