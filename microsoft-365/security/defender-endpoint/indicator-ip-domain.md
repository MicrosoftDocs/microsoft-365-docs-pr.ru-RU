---
title: Создание индикаторов для IPs и URL-адресов/доменов
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
ms.openlocfilehash: 3cfdc226ec5b476a37d15b67ca6158313e508adf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075749"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="cbb28-104">Создание индикаторов для IPs и URL-адресов/доменов</span><span class="sxs-lookup"><span data-stu-id="cbb28-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cbb28-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cbb28-105">**Applies to:**</span></span>
- [<span data-ttu-id="cbb28-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cbb28-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="cbb28-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cbb28-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="cbb28-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="cbb28-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cbb28-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="cbb28-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="cbb28-110">Защитник для конечной точки может блокировать то, что Корпорация Майкрософт считает вредоносными IPs/URL-адресами, с помощью Защитник Windows SmartScreen для браузеров Майкрософт и с помощью сетевой защиты для браузеров или вызовов, не влиянных на microsoft.</span><span class="sxs-lookup"><span data-stu-id="cbb28-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="cbb28-111">Набор данных разведки угроз для этого управляется корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cbb28-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="cbb28-112">Создав индикаторы для IPs и URL-адресов или доменов, теперь можно разрешить или заблокировать IPs, URL-адреса или домены на основе собственной разведки угроз.</span><span class="sxs-lookup"><span data-stu-id="cbb28-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="cbb28-113">Это можно сделать через страницу параметров или группами машин, если вы считаете, что некоторые группы более или менее рискуют, чем другие.</span><span class="sxs-lookup"><span data-stu-id="cbb28-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="cbb28-114">Не поддерживается Inter-Domain маршрутизации (CIDR) для IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="cbb28-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="cbb28-115">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="cbb28-115">Before you begin</span></span>
<span data-ttu-id="cbb28-116">Важно понимать следующие предпосылки перед созданием показателей для IPS, URL-адресов или доменов:</span><span class="sxs-lookup"><span data-stu-id="cbb28-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="cbb28-117">URL-адрес и IP-адрес позволяют и блокируют защиту сетевого компонента Defender для конечной точки, которая будет включена в режиме блокировки.</span><span class="sxs-lookup"><span data-stu-id="cbb28-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="cbb28-118">Дополнительные сведения о инструкциях по защите сети и конфигурации см. в инструкции [enable network protection.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="cbb28-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="cbb28-119">Клиентская версия antimalware должна быть 4.18.1906.x или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="cbb28-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="cbb28-120">Поддерживается на машинах в Windows 10 версии 1709 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="cbb28-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="cbb28-121">**Убедитесь, что настраиваемые** сетевые индикаторы включены в центре безопасности **Microsoft Defender > параметры > расширенных функций.**</span><span class="sxs-lookup"><span data-stu-id="cbb28-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="cbb28-122">Дополнительные сведения см. в [дополнительных сведениях.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="cbb28-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="cbb28-123">Для поддержки индикаторов на iOS см. в [руб. Настройка настраиваемых индикаторов.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)</span><span class="sxs-lookup"><span data-stu-id="cbb28-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="cbb28-124">В список индикаторов могут быть добавлены только внешние ИП.</span><span class="sxs-lookup"><span data-stu-id="cbb28-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="cbb28-125">Индикаторы не могут быть созданы для внутренних ИП.</span><span class="sxs-lookup"><span data-stu-id="cbb28-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="cbb28-126">Для сценариев веб-защиты рекомендуется использовать встроенные возможности в Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="cbb28-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="cbb28-127">Microsoft Edge использует [network Protection](network-protection.md) для проверки сетевого трафика и позволяет блоки для TCP, HTTP и HTTPS (TLS).</span><span class="sxs-lookup"><span data-stu-id="cbb28-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="cbb28-128">Для всех остальных процессов сценарии веб-защиты используют network Protection для проверки и обеспечения соблюдения:</span><span class="sxs-lookup"><span data-stu-id="cbb28-128">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> <br>
> <span data-ttu-id="cbb28-129">ПРИМЕЧАНИЕ:</span><span class="sxs-lookup"><span data-stu-id="cbb28-129">NOTE:</span></span>
> - <span data-ttu-id="cbb28-130">IP поддерживается для всех трех протоколов</span><span class="sxs-lookup"><span data-stu-id="cbb28-130">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="cbb28-131">Поддерживаются только отдельные IP-адреса (без блоков CIDR или диапазонов IP-адресов)</span><span class="sxs-lookup"><span data-stu-id="cbb28-131">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="cbb28-132">Зашифрованные URL-адреса (полный путь) могут быть заблокированы только в первых браузерах сторон (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="cbb28-132">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="cbb28-133">Зашифрованные URL-адреса (только для FQDN) могут быть заблокированы за пределами первых браузеров сторон (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="cbb28-133">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="cbb28-134">На уровне домена и всех незашифрованных URL-адресов можно применять полные блоки путей URL-адресов</span><span class="sxs-lookup"><span data-stu-id="cbb28-134">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="cbb28-135">Между временем действия и блокировкой URL-адреса и IP может быть до 2 часов задержки (как правило, меньше).</span><span class="sxs-lookup"><span data-stu-id="cbb28-135">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="cbb28-136">Создание индикатора для IPs, URL-адресов или доменов на странице параметры</span><span class="sxs-lookup"><span data-stu-id="cbb28-136">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="cbb28-137">В области навигации выберите **Параметры**  >  **Индикаторы**.</span><span class="sxs-lookup"><span data-stu-id="cbb28-137">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="cbb28-138">Выберите **IP-адреса или вкладку URL-адресов и доменов.**</span><span class="sxs-lookup"><span data-stu-id="cbb28-138">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="cbb28-139">Выберите **элемент Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cbb28-139">Select **Add item**.</span></span>

4. <span data-ttu-id="cbb28-140">Укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="cbb28-140">Specify the following details:</span></span>
   - <span data-ttu-id="cbb28-141">Индикатор . Укажите сведения об объекте и определите срок действия индикатора.</span><span class="sxs-lookup"><span data-stu-id="cbb28-141">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="cbb28-142">Действие . Укажите действия, которые необходимо принять, и укажите описание.</span><span class="sxs-lookup"><span data-stu-id="cbb28-142">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="cbb28-143">Область — определите область действия группы машин.</span><span class="sxs-lookup"><span data-stu-id="cbb28-143">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="cbb28-144">Просмотрите сведения в вкладке Сводка, а затем нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cbb28-144">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cbb28-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cbb28-145">Related topics</span></span>
- [<span data-ttu-id="cbb28-146">Создание индикаторов</span><span class="sxs-lookup"><span data-stu-id="cbb28-146">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="cbb28-147">Создание индикаторов для файлов</span><span class="sxs-lookup"><span data-stu-id="cbb28-147">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="cbb28-148">Создание индикаторов на основе сертификатов</span><span class="sxs-lookup"><span data-stu-id="cbb28-148">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="cbb28-149">Управление индикаторами</span><span class="sxs-lookup"><span data-stu-id="cbb28-149">Manage indicators</span></span>](indicator-manage.md)
