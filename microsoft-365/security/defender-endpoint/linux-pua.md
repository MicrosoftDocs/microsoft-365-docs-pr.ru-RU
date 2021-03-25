---
title: Обнаружение и блокировка потенциально нежелательных приложений с помощью ATP Microsoft Defender для Linux
description: Обнаружение и блокировка потенциально нежелательных приложений (PUA) с помощью ATP Microsoft Defender для Linux.
keywords: Microsoft, defender, atp, linux, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 40e6099349ff6c62c5e0b6c35fd9940cb9200f05
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187773"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="e00ef-104">Обнаружение и блокировка потенциально нежелательных приложений с помощью Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="e00ef-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e00ef-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e00ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="e00ef-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e00ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e00ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e00ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e00ef-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e00ef-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e00ef-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e00ef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="e00ef-110">Функция защиты потенциально нежелательного приложения (PUA) в Defender for Endpoint для Linux может обнаруживать и блокировать файлы PUA в конечных точках сети.</span><span class="sxs-lookup"><span data-stu-id="e00ef-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint for Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="e00ef-111">Эти приложения не считаются вирусами, вредоносными программами или другими типами угроз, но могут выполнять действия в конечных точках, которые отрицательно влияют на их производительность или использование.</span><span class="sxs-lookup"><span data-stu-id="e00ef-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="e00ef-112">PUA также может относиться к приложениям, которые считаются плохой репутацией.</span><span class="sxs-lookup"><span data-stu-id="e00ef-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="e00ef-113">Эти приложения могут повысить риск заражения сети вредоносными программами, привести к тому, что выявить вредоносные программы будет сложнее, и могут тратить ИТ-ресурсы на очистку приложений.</span><span class="sxs-lookup"><span data-stu-id="e00ef-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="e00ef-114">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="e00ef-114">How it works</span></span>

<span data-ttu-id="e00ef-115">Защитник для конечной точки для Linux может обнаруживать и сообщать о файлах PUA.</span><span class="sxs-lookup"><span data-stu-id="e00ef-115">Defender for Endpoint for Linux can detect and report PUA files.</span></span> <span data-ttu-id="e00ef-116">При настройке в режиме блокировки файлы PUA перемещаются в карантин.</span><span class="sxs-lookup"><span data-stu-id="e00ef-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="e00ef-117">Когда puA обнаруживается на конечной точке, Defender for Endpoint для Linux ведет запись инфекции в истории угроз.</span><span class="sxs-lookup"><span data-stu-id="e00ef-117">When a PUA is detected on an endpoint, Defender for Endpoint for Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="e00ef-118">Историю можно визуализировать на портале Центра безопасности Защитника Майкрософт или с помощью средства `mdatp` командной строки.</span><span class="sxs-lookup"><span data-stu-id="e00ef-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="e00ef-119">Имя угрозы будет содержать слово "Application".</span><span class="sxs-lookup"><span data-stu-id="e00ef-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="e00ef-120">Настройка защиты PUA</span><span class="sxs-lookup"><span data-stu-id="e00ef-120">Configure PUA protection</span></span>

<span data-ttu-id="e00ef-121">Защита PUA в Defender for Endpoint для Linux может быть настроена одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="e00ef-121">PUA protection in Defender for Endpoint for Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="e00ef-122">**Отключено:** защита PUA отключена.</span><span class="sxs-lookup"><span data-stu-id="e00ef-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="e00ef-123">**Аудит:** файлы PUA сообщаются в журналах продуктов, но не в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e00ef-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="e00ef-124">Запись о заражении не хранится в истории угроз и продукт не будет принимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="e00ef-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="e00ef-125">**Блок**: файлы PUA регистрируются в журналах продуктов и в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e00ef-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="e00ef-126">Запись инфекции хранится в истории угроз, и продуктом принимаются меры.</span><span class="sxs-lookup"><span data-stu-id="e00ef-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="e00ef-127">По умолчанию защита PUA настраивается в **режиме аудита.**</span><span class="sxs-lookup"><span data-stu-id="e00ef-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="e00ef-128">Можно настроить обработку файлов PUA из командной строки или консоли управления.</span><span class="sxs-lookup"><span data-stu-id="e00ef-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="e00ef-129">Используйте средство командной строки для настройки защиты PUA:</span><span class="sxs-lookup"><span data-stu-id="e00ef-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="e00ef-130">В Терминале выполните следующую команду, чтобы настроить защиту PUA:</span><span class="sxs-lookup"><span data-stu-id="e00ef-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="e00ef-131">Используйте консоль управления для настройки защиты PUA:</span><span class="sxs-lookup"><span data-stu-id="e00ef-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="e00ef-132">На предприятии можно настроить защиту PUA с консоли управления, например Puppet или Ansible, аналогично настройке других параметров продукта.</span><span class="sxs-lookup"><span data-stu-id="e00ef-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="e00ef-133">Дополнительные сведения см. в разделе [Параметры](linux-preferences.md#threat-type-settings) типа угрозы в статье [Set preferences for Defender for Endpoint for Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="e00ef-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint for Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e00ef-134">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e00ef-134">Related articles</span></span>

- [<span data-ttu-id="e00ef-135">Настройка предпочтений для Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="e00ef-135">Set preferences for Defender for Endpoint for Linux</span></span>](linux-preferences.md)