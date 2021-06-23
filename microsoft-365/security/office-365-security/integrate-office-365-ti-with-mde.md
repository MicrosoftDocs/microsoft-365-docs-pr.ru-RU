---
title: Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки
f1.keywords:
- NOCSH
keywords: интеграция, Microsoft Defender, Microsoft Defender для конечной точки
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки, чтобы получить более подробные сведения об угрозах в отношении устройств и контента электронной почты.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083384"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="8f9d9-104">Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8f9d9-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8f9d9-105">[Microsoft Defender для Office 365](defender-for-office-365.md) можно настроить для работы с [Microsoft Defender для конечной точки](/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="8f9d9-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="8f9d9-106">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки может помочь группе безопасности отслеживать и быстро принимать меры, если устройства пользователей находятся под угрозой.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="8f9d9-107">Например, после включения интеграции группа операций безопасности сможет видеть устройства, которые потенциально затронуты обнаруженным сообщением электронной почты, а также количество последних оповещений для этих устройств в Microsoft Defender для Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="8f9d9-108">На следующем изображении изображено, как выглядит вкладка **Devices** при включенной интеграции Microsoft Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="8f9d9-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Когда включен Microsoft Defender для конечной точки, вы можете увидеть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="8f9d9-110">В этом примере можно увидеть, что получатели обнаруженного сообщения электронной почты имеют четыре устройства и одно имеет оповещение.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="8f9d9-111">Щелкнув ссылку для устройства, откроет свою страницу на портале Microsoft 365 Defender [(ранее](../defender-endpoint/microsoft-defender-security-center.md) центр безопасности Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="8f9d9-111">Clicking the link for a device opens its page in [the Microsoft 365 Defender portal](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender security center).</span></span>

> [!TIP]
> <span data-ttu-id="8f9d9-112">Портал Microsoft 365 Defender заменяет Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="8f9d9-113">См. [в Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="8f9d9-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="8f9d9-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="8f9d9-114">Requirements</span></span>

- <span data-ttu-id="8f9d9-115">Ваша организация должна иметь Microsoft Defender для Office 365 (или Office 365 E5) и Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="8f9d9-116">Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="8f9d9-117">Дополнительные сведения см. в статье [Разрешения на портале Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="8f9d9-117">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="8f9d9-118">Вы должны иметь доступ к Explorer (или обнаружения [в режиме реального времени).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="8f9d9-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="8f9d9-119">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8f9d9-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="8f9d9-120">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки настроена как в Defender для конечной точки, так и в Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="8f9d9-121">В качестве глобального администратора или администратора безопасности откройте портал Microsoft 365 Defender () и перейдите в обозреватель <https://security.microsoft.com> **&** \> **электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="8f9d9-121">As a global administrator or a security administrator, open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Email & collaboration** \> **Explorer**.</span></span> <span data-ttu-id="8f9d9-122">Чтобы перейти непосредственно на **страницу Explorer,** используйте <https://security.microsoft.com/threatexplorer> .</span><span class="sxs-lookup"><span data-stu-id="8f9d9-122">To go directly to the **Explorer** page, use <https://security.microsoft.com/threatexplorer>.</span></span>

2. <span data-ttu-id="8f9d9-123">На странице **Explorer** в правом верхнем углу экрана нажмите **кнопку MDE Параметры**.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-123">On the **Explorer** page, in the upper right corner of the screen, click **MDE Settings**.</span></span>

3. <span data-ttu-id="8f9d9-124">В **вылете подключения к** конечной точке Microsoft **Defender для конечной** точки включите Подключение microsoft Defender для конечной точки ![ (Toggle on), а затем нажмите кнопку Закрыть значок ](../../media/scc-toggle-on.png) ![ ](../../media/m365-cc-sc-close-icon.png) **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-124">In the **Microsoft Defender for Endpoint connection** flyout that appears, turn on **Connect to Microsoft Defender for Endpoint** (![Toggle on](../../media/scc-toggle-on.png)) and then click ![Close icon](../../media/m365-cc-sc-close-icon.png) **Close**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Подключение к MDE":::

4. <span data-ttu-id="8f9d9-126">Возвращаясь в области навигации, выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="8f9d9-126">Back in the navigation pane, choose **Settings**.</span></span> <span data-ttu-id="8f9d9-127">На странице **Параметры** выберите **конечные точки**</span><span class="sxs-lookup"><span data-stu-id="8f9d9-127">On the **Settings** page, choose **Endpoints**</span></span>

5. <span data-ttu-id="8f9d9-128">На **открываемой странице Конечные** точки выберите **расширенные функции.**</span><span class="sxs-lookup"><span data-stu-id="8f9d9-128">On the **Endpoints** page that opens, choose **Advanced features**.</span></span>

6. <span data-ttu-id="8f9d9-129">Прокрутите **вниз Office 365 подключения к службе сведении** об угрозах и включите его ![ (чтобы ](../../media/scc-toggle-on.png) включить).</span><span class="sxs-lookup"><span data-stu-id="8f9d9-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn it on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="8f9d9-130">По завершению нажмите кнопку **Сохранить предпочтения.**</span><span class="sxs-lookup"><span data-stu-id="8f9d9-130">When you're finished, click **Save preferences**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8f9d9-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8f9d9-131">Related articles</span></span>

[<span data-ttu-id="8f9d9-132">Возможности расследования и реагирования на угрозы в Office 365</span><span class="sxs-lookup"><span data-stu-id="8f9d9-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="8f9d9-133">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="8f9d9-133">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="8f9d9-134">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8f9d9-134">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
