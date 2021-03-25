---
title: Создание индикаторов для файлов
ms.reviewer: ''
description: Создание индикаторов для файла, определяющих обнаружение, предотвращение и исключение сущностями.
keywords: файл, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, URL-адрес, домен
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075750"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="b0ea0-104">Создание индикаторов для файлов</span><span class="sxs-lookup"><span data-stu-id="b0ea0-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b0ea0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b0ea0-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0ea0-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b0ea0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b0ea0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0ea0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="b0ea0-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b0ea0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b0ea0-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="b0ea0-110">Вы можете предотвратить дальнейшее распространение атаки в организации, запретив потенциально вредоносные файлы или подозрительные вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="b0ea0-111">Если вы знаете потенциально вредоносный переносной файл(PE), его можно заблокировать.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="b0ea0-112">Эта операция предотвратит чтение, написание или выполнение ее на компьютерах в организации.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="b0ea0-113">Существует два способа создания индикаторов для файлов:</span><span class="sxs-lookup"><span data-stu-id="b0ea0-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="b0ea0-114">Создание индикатора на странице параметры</span><span class="sxs-lookup"><span data-stu-id="b0ea0-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="b0ea0-115">Создание контекстного индикатора с помощью кнопки добавить индикатор со страницы сведений о файле</span><span class="sxs-lookup"><span data-stu-id="b0ea0-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="b0ea0-116">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b0ea0-116">Before you begin</span></span>
<span data-ttu-id="b0ea0-117">Важно понимать следующие предпосылки перед созданием индикаторов для файлов:</span><span class="sxs-lookup"><span data-stu-id="b0ea0-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="b0ea0-118">Эта функция доступна, если в организации Защитник Windows включена антивирусная и облачная защита.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="b0ea0-119">Дополнительные сведения см. в дополнительных сведениях: Использование технологий следующего поколения в [антивирусе Microsoft Defender с помощью облачной защиты.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="b0ea0-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="b0ea0-120">Клиентская версия antimalware должна быть 4.18.1901.x или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="b0ea0-121">Поддерживается на компьютерах в Windows 10, версии 1703 или более поздней версии, Windows server 2016 и 2019.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="b0ea0-122">Чтобы начать блокировать файлы, сначала необходимо включить блок или включить функцию [в  ](advanced-features.md) Параметры.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="b0ea0-123">Эта функция предназначена для предотвращения скачивания из Интернета подозрительных вредоносных программ (или потенциально вредоносных файлов).</span><span class="sxs-lookup"><span data-stu-id="b0ea0-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="b0ea0-124">В настоящее время он поддерживает переносные исполняемые (PE) файлы, включая _файлы .exe_ и _.dll._</span><span class="sxs-lookup"><span data-stu-id="b0ea0-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="b0ea0-125">Со временем охват будет расширен.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-125">The coverage will be extended over time.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="b0ea0-126">Функция разрешить или заблокировать не может быть сделана в файлах, если классификация файла существует в кэше устройства до действия разрешить или заблокировать</span><span class="sxs-lookup"><span data-stu-id="b0ea0-126">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
>- <span data-ttu-id="b0ea0-127">Доверенные подписанные файлы будут рассматриваться по-разному.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-127">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="b0ea0-128">Defender for Endpoint оптимизирован для обработки вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-128">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="b0ea0-129">Попытка заблокировать доверенные подписанные файлы в некоторых случаях может иметь последствия для производительности.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-129">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>

 
>[!NOTE]
><span data-ttu-id="b0ea0-130">Обычно блоки файлов применяются в течение нескольких минут, но могут занять более 30 минут.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-130">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="b0ea0-131">Создание индикатора для файлов со страницы параметры</span><span class="sxs-lookup"><span data-stu-id="b0ea0-131">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="b0ea0-132">В области навигации выберите **Параметры**  >  **Индикаторы**.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-132">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="b0ea0-133">Выберите **вкладку "Hash** File".</span><span class="sxs-lookup"><span data-stu-id="b0ea0-133">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="b0ea0-134">Выберите **индикатор Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-134">Select **Add indicator**.</span></span>

4. <span data-ttu-id="b0ea0-135">Укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b0ea0-135">Specify the following details:</span></span>
   - <span data-ttu-id="b0ea0-136">Индикатор . Укажите сведения об объекте и определите срок действия индикатора.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-136">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="b0ea0-137">Действие . Укажите действия, которые необходимо принять, и укажите описание.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-137">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="b0ea0-138">Область — определите область действия группы машин.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-138">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="b0ea0-139">Просмотрите сведения в вкладке Сводка, а затем нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-139">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="b0ea0-140">Создание контекстного индикатора на странице сведения о файле</span><span class="sxs-lookup"><span data-stu-id="b0ea0-140">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="b0ea0-141">Одним из вариантов при принятии ответных [действий в файле](respond-file-alerts.md) является добавление индикатора для файла.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-141">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="b0ea0-142">При добавлении hash индикатора для файла можно поднять оповещение и заблокировать файл всякий раз, когда компьютер в организации пытается запустить его.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-142">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="b0ea0-143">Файлы, автоматически заблокированные индикатором, не будут показываться в центре действий файла, но оповещения по-прежнему будут видны в очереди Оповещения.</span><span class="sxs-lookup"><span data-stu-id="b0ea0-143">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b0ea0-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b0ea0-144">Related topics</span></span>
- [<span data-ttu-id="b0ea0-145">Создание индикаторов</span><span class="sxs-lookup"><span data-stu-id="b0ea0-145">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="b0ea0-146">Создание индикаторов для IPs и URL-адресов/доменов</span><span class="sxs-lookup"><span data-stu-id="b0ea0-146">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="b0ea0-147">Создание индикаторов на основе сертификатов</span><span class="sxs-lookup"><span data-stu-id="b0ea0-147">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="b0ea0-148">Управление индикаторами</span><span class="sxs-lookup"><span data-stu-id="b0ea0-148">Manage indicators</span></span>](indicator-manage.md)
