---
title: Обнаружение и блокировка потенциально нежелательных приложений с помощью ATP Microsoft Defender для Mac
description: Обнаружение и блокировка потенциально нежелательных приложений (PUA) с помощью ATP Microsoft Defender для Mac.
keywords: Microsoft, defender, atp, mac, pua, pus
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
ms.openlocfilehash: d52b8db069a2e1988cee9c19656116bf49ad9d60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070278"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="1fc58-104">Обнаружение и блокировка потенциально нежелательных приложений с помощью Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="1fc58-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1fc58-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1fc58-105">**Applies to:**</span></span>
- [<span data-ttu-id="1fc58-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1fc58-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="1fc58-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fc58-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1fc58-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1fc58-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1fc58-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1fc58-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="1fc58-110">Функция защиты потенциально нежелательного приложения (PUA) в Microsoft Defender для конечной точки для Mac может обнаруживать и блокировать файлы PUA в конечных точках сети.</span><span class="sxs-lookup"><span data-stu-id="1fc58-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint for Mac can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="1fc58-111">Эти приложения не считаются вирусами, вредоносными программами или другими типами угроз, но могут выполнять действия в конечных точках, которые отрицательно влияют на их производительность или использование.</span><span class="sxs-lookup"><span data-stu-id="1fc58-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="1fc58-112">PUA также может относиться к приложениям, которые считаются плохой репутацией.</span><span class="sxs-lookup"><span data-stu-id="1fc58-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="1fc58-113">Эти приложения могут повысить риск заражения сети вредоносными программами, привести к тому, что выявить вредоносные программы будет сложнее, и могут тратить ИТ-ресурсы на очистку приложений.</span><span class="sxs-lookup"><span data-stu-id="1fc58-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="1fc58-114">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="1fc58-114">How it works</span></span>

<span data-ttu-id="1fc58-115">Microsoft Defender для конечной точки для Mac может обнаруживать и сообщать о файлах PUA.</span><span class="sxs-lookup"><span data-stu-id="1fc58-115">Microsoft Defender for Endpoint for Mac can detect and report PUA files.</span></span> <span data-ttu-id="1fc58-116">При настройке в режиме блокировки файлы PUA перемещаются в карантин.</span><span class="sxs-lookup"><span data-stu-id="1fc58-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="1fc58-117">Когда puA обнаруживается на конечной точке, Microsoft Defender для конечной точки для Mac представляет пользователю уведомление, если уведомления не отключены.</span><span class="sxs-lookup"><span data-stu-id="1fc58-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint for Mac presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="1fc58-118">Имя угрозы будет содержать слово "Application".</span><span class="sxs-lookup"><span data-stu-id="1fc58-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="1fc58-119">Настройка защиты PUA</span><span class="sxs-lookup"><span data-stu-id="1fc58-119">Configure PUA protection</span></span>

<span data-ttu-id="1fc58-120">Защита PUA в Microsoft Defender для конечной точки для Mac может быть настроена одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="1fc58-120">PUA protection in Microsoft Defender for Endpoint for Mac can be configured in one of the following ways:</span></span>

- <span data-ttu-id="1fc58-121">**Отключено:** защита PUA отключена.</span><span class="sxs-lookup"><span data-stu-id="1fc58-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="1fc58-122">**Аудит:** файлы PUA сообщаются в журналах продуктов, но не в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1fc58-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="1fc58-123">Пользователю не будет представлено уведомление и продукт не будет принимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="1fc58-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="1fc58-124">**Блок**: файлы PUA регистрируются в журналах продуктов и в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1fc58-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="1fc58-125">Пользователю представлено уведомление, и продуктом принимаются действия.</span><span class="sxs-lookup"><span data-stu-id="1fc58-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="1fc58-126">По умолчанию защита PUA настраивается в **режиме аудита.**</span><span class="sxs-lookup"><span data-stu-id="1fc58-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="1fc58-127">Можно настроить обработку файлов PUA из командной строки или консоли управления.</span><span class="sxs-lookup"><span data-stu-id="1fc58-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="1fc58-128">Используйте средство командной строки для настройки защиты PUA:</span><span class="sxs-lookup"><span data-stu-id="1fc58-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="1fc58-129">В Терминале выполните следующую команду, чтобы настроить защиту PUA:</span><span class="sxs-lookup"><span data-stu-id="1fc58-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="1fc58-130">Используйте консоль управления для настройки защиты PUA:</span><span class="sxs-lookup"><span data-stu-id="1fc58-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="1fc58-131">В вашем предприятии можно настроить защиту PUA с консоли управления, например JAMF или Intune, аналогично настройке других параметров продукта.</span><span class="sxs-lookup"><span data-stu-id="1fc58-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="1fc58-132">Дополнительные сведения см. в разделе [Параметры](mac-preferences.md#threat-type-settings) типа угрозы в разделе Настройка предпочтений [для Microsoft Defender для конечной](mac-preferences.md) точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="1fc58-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1fc58-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1fc58-133">Related topics</span></span>

- [<span data-ttu-id="1fc58-134">Настройка предпочтений для Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="1fc58-134">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>](mac-preferences.md)
