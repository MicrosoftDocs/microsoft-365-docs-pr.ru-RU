---
title: Оценка защиты сети
description: Узнайте, как работает защита сети, протестуя распространенные сценарии, от которые она защищает.
keywords: Защита сети, эксплойтов, вредоносный веб-сайт, IP, домен, домены, оценка, тестирование, демонстрация
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ade50e85dbfcf5f59921a65d5b97bb47d21e5b12
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570928"
---
# <a name="evaluate-network-protection"></a><span data-ttu-id="b7078-104">Оценка защиты сети</span><span class="sxs-lookup"><span data-stu-id="b7078-104">Evaluate network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7078-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b7078-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7078-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b7078-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [<span data-ttu-id="b7078-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7078-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b7078-108">[Защита сети](network-protection.md) позволяет сотрудникам не использовать любое приложение для доступа к опасным доменам, в которые могут быть организованы фишинговые атаки, эксплойты и другой вредоносный контент в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b7078-108">[Network protection](network-protection.md) helps prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the Internet.</span></span>

<span data-ttu-id="b7078-109">В этой статье вы можете оценить защиту сети, включив функцию и направляя ее на сайт тестирования.</span><span class="sxs-lookup"><span data-stu-id="b7078-109">This article helps you evaluate network protection by enabling the feature and guiding you to a testing site.</span></span> <span data-ttu-id="b7078-110">Сайты в этой статье оценки не являются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="b7078-110">The sites in this evaluation article aren't malicious.</span></span> <span data-ttu-id="b7078-111">Это специально созданные веб-сайты, которые притворяются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="b7078-111">They're specially created websites that pretend to be malicious.</span></span> <span data-ttu-id="b7078-112">Сайт будет реплицировать поведение, которое произойдет, если пользователь посетил вредоносный сайт или домен.</span><span class="sxs-lookup"><span data-stu-id="b7078-112">The site will replicate the behavior that would happen if a user visited a malicious site or domain.</span></span>

> [!TIP]
> <span data-ttu-id="b7078-113">Вы также можете посетить веб-сайт тестового поля Защитника Майкрософт demo.wd.microsoft.com, чтобы узнать, как работают другие функции защиты. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="b7078-113">You can also visit the Microsoft Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how other protection features work.</span></span>

## <a name="enable-network-protection-in-audit-mode"></a><span data-ttu-id="b7078-114">Включить защиту сети в режиме аудита</span><span class="sxs-lookup"><span data-stu-id="b7078-114">Enable network protection in audit mode</span></span>

<span data-ttu-id="b7078-115">Включить защиту сети в режиме аудита, чтобы узнать, какие IP-адреса и домены были бы заблокированы.</span><span class="sxs-lookup"><span data-stu-id="b7078-115">Enable network protection in audit mode to see which IP addresses and domains would have been blocked.</span></span> <span data-ttu-id="b7078-116">Вы можете убедиться, что это не влияет на бизнес-приложения, или получить представление о том, как часто возникают блоки.</span><span class="sxs-lookup"><span data-stu-id="b7078-116">You can make sure it doesn't affect line-of-business apps, or get an idea of how often blocks occur.</span></span>

1. <span data-ttu-id="b7078-117">Введите **powershell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="b7078-117">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="b7078-118">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b7078-118">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a><span data-ttu-id="b7078-119">Посетите (поддельный) вредоносный домен</span><span class="sxs-lookup"><span data-stu-id="b7078-119">Visit a (fake) malicious domain</span></span>

1. <span data-ttu-id="b7078-120">Откройте Internet Explorer, Google Chrome или любой другой браузер по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="b7078-120">Open Internet Explorer, Google Chrome, or any other browser of your choice.</span></span>

1. <span data-ttu-id="b7078-121">Перейдите по ссылке [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span><span class="sxs-lookup"><span data-stu-id="b7078-121">Go to [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span></span>

<span data-ttu-id="b7078-122">Подключение к сети будет разрешено, и будет отображаться тестовая сообщение.</span><span class="sxs-lookup"><span data-stu-id="b7078-122">The network connection will be allowed and a test message will be displayed.</span></span>

![Например, уведомление о том, что подключение заблокировано: ИТ-администратор заставил Windows Security заблокировать это сетевое подключение.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="b7078-125">Просмотр событий защиты сети в Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="b7078-125">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="b7078-126">Чтобы просмотреть заблокированные приложения, откройте viewer событий и фильтр для event ID 1125 в журнале Microsoft-Windows-Windows-Defender/Operational.</span><span class="sxs-lookup"><span data-stu-id="b7078-126">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1125 in the Microsoft-Windows-Windows-Defender/Operational log.</span></span> <span data-ttu-id="b7078-127">В следующей таблице перечислены все события защиты сети.</span><span class="sxs-lookup"><span data-stu-id="b7078-127">The following table lists all network protection events.</span></span>

| <span data-ttu-id="b7078-128">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b7078-128">Event ID</span></span> | <span data-ttu-id="b7078-129">Provide/Source</span><span class="sxs-lookup"><span data-stu-id="b7078-129">Provide/Source</span></span> | <span data-ttu-id="b7078-130">Описание</span><span class="sxs-lookup"><span data-stu-id="b7078-130">Description</span></span> |
|-|-|-|
|<span data-ttu-id="b7078-131">5007</span><span class="sxs-lookup"><span data-stu-id="b7078-131">5007</span></span> | <span data-ttu-id="b7078-132">Защитник Windows (операционная)</span><span class="sxs-lookup"><span data-stu-id="b7078-132">Windows Defender (Operational)</span></span> | <span data-ttu-id="b7078-133">Событие при смене параметров</span><span class="sxs-lookup"><span data-stu-id="b7078-133">Event when settings are changed</span></span> |
|<span data-ttu-id="b7078-134">1125</span><span class="sxs-lookup"><span data-stu-id="b7078-134">1125</span></span> | <span data-ttu-id="b7078-135">Защитник Windows (операционная)</span><span class="sxs-lookup"><span data-stu-id="b7078-135">Windows Defender (Operational)</span></span> | <span data-ttu-id="b7078-136">Событие при аудите сетевого подключения</span><span class="sxs-lookup"><span data-stu-id="b7078-136">Event when a network connection is audited</span></span> |
|<span data-ttu-id="b7078-137">1126</span><span class="sxs-lookup"><span data-stu-id="b7078-137">1126</span></span> | <span data-ttu-id="b7078-138">Защитник Windows (операционная)</span><span class="sxs-lookup"><span data-stu-id="b7078-138">Windows Defender (Operational)</span></span> | <span data-ttu-id="b7078-139">Событие, когда сетевое подключение заблокировано</span><span class="sxs-lookup"><span data-stu-id="b7078-139">Event when a network connection is blocked</span></span> |

## <a name="see-also"></a><span data-ttu-id="b7078-140">См. также</span><span class="sxs-lookup"><span data-stu-id="b7078-140">See also</span></span>

* [<span data-ttu-id="b7078-141">Защита сети</span><span class="sxs-lookup"><span data-stu-id="b7078-141">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="b7078-142">Включить защиту сети</span><span class="sxs-lookup"><span data-stu-id="b7078-142">Enable network protection</span></span>](enable-network-protection.md)
* [<span data-ttu-id="b7078-143">Защита сети от неполадок</span><span class="sxs-lookup"><span data-stu-id="b7078-143">Troubleshoot network protection</span></span>](troubleshoot-np.md)
