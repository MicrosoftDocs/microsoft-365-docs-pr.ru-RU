---
title: Создание индикаторов для протоколов IP и URL-адресов или доменов
ms.reviewer: ''
description: Создание индикаторов для IPs и URL-адресов/доменов, определяющих обнаружение, предотвращение и исключение сущностями.
keywords: IP, URL-адрес, домен, управление, разрешено, заблокировано, блокируется, блокируется, очищается, вредоносный, файл, IP-адрес, URL-адреса, домен
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
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841070"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="47c71-104">Создание индикаторов для протоколов IP и URL-адресов или доменов</span><span class="sxs-lookup"><span data-stu-id="47c71-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47c71-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="47c71-105">**Applies to:**</span></span>
- [<span data-ttu-id="47c71-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="47c71-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="47c71-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47c71-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="47c71-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="47c71-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="47c71-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="47c71-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="47c71-110">Защитник для конечной точки может блокировать вредоносные IPs/URL-адреса Майкрософт с помощью Защитник Windows SmartScreen для браузеров Майкрософт, а также с помощью сетевой защиты для браузеров или вызовов, не влиянных на microsoft.</span><span class="sxs-lookup"><span data-stu-id="47c71-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="47c71-111">Набор данных разведки угроз для этого управляется корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="47c71-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="47c71-112">Создав индикаторы для IPs и URL-адресов или доменов, теперь можно разрешить или заблокировать IPs, URL-адреса или домены на основе собственной разведки угроз.</span><span class="sxs-lookup"><span data-stu-id="47c71-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="47c71-113">Это можно сделать через страницу параметров или группами машин, если вы считаете, что некоторые группы более или менее рискуют, чем другие.</span><span class="sxs-lookup"><span data-stu-id="47c71-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="47c71-114">Не поддерживается Inter-Domain маршрутизации (CIDR) для IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="47c71-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="47c71-115">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="47c71-115">Before you begin</span></span>
<span data-ttu-id="47c71-116">Важно понимать следующие предпосылки перед созданием показателей для IPS, URL-адресов или доменов:</span><span class="sxs-lookup"><span data-stu-id="47c71-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="47c71-117">URL-адрес и IP-адрес позволяют и блокируют защиту сетевого компонента Defender для конечной точки, которая будет включена в режиме блокировки.</span><span class="sxs-lookup"><span data-stu-id="47c71-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="47c71-118">Дополнительные сведения о инструкциях по защите сети и конфигурации см. в инструкции [enable network protection.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="47c71-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="47c71-119">Клиентская версия antimalware должна быть 4.18.1906.x или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="47c71-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="47c71-120">Поддерживается на машинах Windows 10 версии 1709 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="47c71-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="47c71-121">**Убедитесь, что настраиваемые** сетевые индикаторы включены **в Центр безопасности в Microsoft Defender > Параметры > расширенных функций.**</span><span class="sxs-lookup"><span data-stu-id="47c71-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="47c71-122">Дополнительные сведения см. в [дополнительных сведениях.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="47c71-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="47c71-123">Для поддержки индикаторов на iOS см. в [руб. Настройка настраиваемых индикаторов.](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)</span><span class="sxs-lookup"><span data-stu-id="47c71-123">For support of indicators on iOS, see [Configure custom indicators](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="47c71-124">В список индикаторов могут быть добавлены только внешние ИП.</span><span class="sxs-lookup"><span data-stu-id="47c71-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="47c71-125">Индикаторы не могут быть созданы для внутренних ИП.</span><span class="sxs-lookup"><span data-stu-id="47c71-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="47c71-126">Для сценариев веб-защиты рекомендуется использовать встроенные возможности в Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="47c71-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="47c71-127">Microsoft Edge network [Protection](network-protection.md) для проверки сетевого трафика и позволяет блоки для TCP, HTTP и HTTPS (TLS).</span><span class="sxs-lookup"><span data-stu-id="47c71-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="47c71-128">Если существуют противоречивые политики индикатора URL-адресов, применяется более длительный путь.</span><span class="sxs-lookup"><span data-stu-id="47c71-128">If there are conflicting URL indicator policies, the longer path is applied.</span></span> <span data-ttu-id="47c71-129">Например, политика индикатора URL-адресов имеет приоритет над `https:\\support.microsoft.com/en-us/office` политикой индикатора `https:\\support.microsoft.com` URL.</span><span class="sxs-lookup"><span data-stu-id="47c71-129">For example, the URL indicator policy `https:\\support.microsoft.com/en-us/office` takes precedence over the URL indicator policy `https:\\support.microsoft.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="47c71-130">Для всех остальных процессов сценарии веб-защиты используют network Protection для проверки и обеспечения соблюдения:</span><span class="sxs-lookup"><span data-stu-id="47c71-130">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> 
> - <span data-ttu-id="47c71-131">IP поддерживается для всех трех протоколов</span><span class="sxs-lookup"><span data-stu-id="47c71-131">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="47c71-132">Поддерживаются только отдельные IP-адреса (без блоков CIDR или диапазонов IP-адресов)</span><span class="sxs-lookup"><span data-stu-id="47c71-132">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="47c71-133">Зашифрованные URL-адреса (полный путь) могут быть заблокированы только в первых браузерах сторон (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="47c71-133">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="47c71-134">Зашифрованные URL-адреса (только для FQDN) могут быть заблокированы за пределами первых браузеров сторон (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="47c71-134">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="47c71-135">На уровне домена и всех незашифрованных URL-адресов можно применять полные блоки путей URL-адресов</span><span class="sxs-lookup"><span data-stu-id="47c71-135">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="47c71-136">Между временем действия и блокировкой URL-адреса и IP может быть до 2 часов задержки (как правило, меньше).</span><span class="sxs-lookup"><span data-stu-id="47c71-136">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="47c71-137">Создание индикатора для IPs, URL-адресов или доменов на странице параметры</span><span class="sxs-lookup"><span data-stu-id="47c71-137">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="47c71-138">В области навигации выберите **Параметры**  >  **Индикаторы**.</span><span class="sxs-lookup"><span data-stu-id="47c71-138">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="47c71-139">Выберите **IP-адреса или вкладку URL-адресов и доменов.**</span><span class="sxs-lookup"><span data-stu-id="47c71-139">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="47c71-140">Выберите **элемент Добавить**.</span><span class="sxs-lookup"><span data-stu-id="47c71-140">Select **Add item**.</span></span>

4. <span data-ttu-id="47c71-141">Укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="47c71-141">Specify the following details:</span></span>
   - <span data-ttu-id="47c71-142">Индикатор . Укажите сведения об объекте и определите срок действия индикатора.</span><span class="sxs-lookup"><span data-stu-id="47c71-142">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="47c71-143">Действие . Укажите действия, которые необходимо принять, и укажите описание.</span><span class="sxs-lookup"><span data-stu-id="47c71-143">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="47c71-144">Область — определите область действия группы машин.</span><span class="sxs-lookup"><span data-stu-id="47c71-144">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="47c71-145">Просмотрите сведения в вкладке Сводка, а затем нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="47c71-145">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="47c71-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="47c71-146">Related topics</span></span>
- [<span data-ttu-id="47c71-147">Создание индикаторов</span><span class="sxs-lookup"><span data-stu-id="47c71-147">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="47c71-148">Создание индикаторов для файлов</span><span class="sxs-lookup"><span data-stu-id="47c71-148">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="47c71-149">Создание индикаторов на основе сертификатов</span><span class="sxs-lookup"><span data-stu-id="47c71-149">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="47c71-150">Управление индикаторами</span><span class="sxs-lookup"><span data-stu-id="47c71-150">Manage indicators</span></span>](indicator-manage.md)
