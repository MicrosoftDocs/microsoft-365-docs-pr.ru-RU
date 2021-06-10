---
title: Настройка периода антивирусная программа в Microsoft Defender облачного блока
description: Вы можете настроить срок, антивирусная программа в Microsoft Defender будет блокировать работу файла в ожидании определения облака.
keywords: антивирусная программа в Microsoft Defender, antimalware, security, defender, cloud, timeout, block, period, seconds
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789091"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="37d00-104">Настройка времени ожидания блокировки облака</span><span class="sxs-lookup"><span data-stu-id="37d00-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="37d00-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="37d00-105">**Applies to:**</span></span>

- [<span data-ttu-id="37d00-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="37d00-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="37d00-107">Когда антивирусная программа в Microsoft Defender обнаруживает подозрительный файл, он может запретить его работу во время запроса облачной [службы антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="37d00-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="37d00-108">Период блокировки файла по умолчанию [составляет](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="37d00-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="37d00-109">Если вы администратор безопасности, вы можете указать больше времени, чтобы дождаться запуска файла.</span><span class="sxs-lookup"><span data-stu-id="37d00-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="37d00-110">Расширение периода ожидания облачного блока может помочь обеспечить достаточно времени для получения надлежащего определения от антивирусная программа в Microsoft Defender облачной службы.</span><span class="sxs-lookup"><span data-stu-id="37d00-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="37d00-111">Необходимые условия для использования растянутой облачной блокировки</span><span class="sxs-lookup"><span data-stu-id="37d00-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="37d00-112">[Блок на первый взгляд,](configure-block-at-first-sight-microsoft-defender-antivirus.md) и его необходимо включить, прежде чем указать расширенный период ожидания.</span><span class="sxs-lookup"><span data-stu-id="37d00-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="37d00-113">Укажите расширенный период ожидания с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="37d00-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="37d00-114">Вы можете указать период ожидания облачного блока с политикой безопасности [конечной](/mem/intune/protect/endpoint-security-policy)точки в Microsoft Endpoint Manager .</span><span class="sxs-lookup"><span data-stu-id="37d00-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="37d00-115">Перейдите в центр администрирования Endpoint Manager [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="37d00-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="37d00-116">Выберите **безопасность конечных точек,** а затем в **статье Управление**, выберите **антивирус**.</span><span class="sxs-lookup"><span data-stu-id="37d00-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="37d00-117">Выберите (или создайте) антивирусную политику.</span><span class="sxs-lookup"><span data-stu-id="37d00-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="37d00-118">В разделе **Параметры конфигурации** расширим **облачную защиту.**</span><span class="sxs-lookup"><span data-stu-id="37d00-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="37d00-119">Затем в поле Расширенное время в секундах **в облаке Defender** укажите больше времени, в секундах, от 1 секунды до 50 секунд.</span><span class="sxs-lookup"><span data-stu-id="37d00-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="37d00-120">Все, что вы указываете, добавляется к 10 секундам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37d00-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="37d00-121">(Этот шаг необязателен) Внести любые другие изменения в антивирусную политику.</span><span class="sxs-lookup"><span data-stu-id="37d00-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="37d00-122">(Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="37d00-122">(Need help?</span></span> <span data-ttu-id="37d00-123">См. [Параметры для антивирусная программа в Microsoft Defender политики в Microsoft Intune.)](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)</span><span class="sxs-lookup"><span data-stu-id="37d00-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="37d00-124">Выберите **Далее** и завершите настройку политики.</span><span class="sxs-lookup"><span data-stu-id="37d00-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="37d00-125">Укажите расширенный период ожидания с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="37d00-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="37d00-126">С помощью групповой политики можно указать расширенный период времени для облачных проверок.</span><span class="sxs-lookup"><span data-stu-id="37d00-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="37d00-127">На компьютере управления групповой политикой откройте консоль [управления групповой политикой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="37d00-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="37d00-128">Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="37d00-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="37d00-129">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="37d00-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="37d00-130">Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="37d00-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="37d00-131">Дважды **щелкните Настройка расширенной облачной проверки** и убедитесь, что параметр включен.</span><span class="sxs-lookup"><span data-stu-id="37d00-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="37d00-132">Укажите дополнительное время, чтобы не допустить запуска файла в ожидании определения облака.</span><span class="sxs-lookup"><span data-stu-id="37d00-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="37d00-133">Укажите дополнительное время в секундах от 1 секунды до 50 секунд.</span><span class="sxs-lookup"><span data-stu-id="37d00-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="37d00-134">Все, что вы указываете, добавляется к 10 секундам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37d00-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="37d00-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="37d00-135">Select **OK**.</span></span>

 