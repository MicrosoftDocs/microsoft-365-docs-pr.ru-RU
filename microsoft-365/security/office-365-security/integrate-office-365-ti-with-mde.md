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
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028885"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="44f12-104">Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="44f12-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="44f12-105">[Microsoft Defender для Office 365](defender-for-office-365.md) можно настроить для работы с [Microsoft Defender для конечной точки](/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="44f12-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="44f12-106">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки может помочь группе безопасности отслеживать и быстро принимать меры, если устройства пользователей находятся под угрозой.</span><span class="sxs-lookup"><span data-stu-id="44f12-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="44f12-107">Например, после включения интеграции группа операций безопасности сможет видеть устройства, которые потенциально затронуты обнаруженным сообщением электронной почты, а также количество последних оповещений для этих устройств в Microsoft Defender для Endpoint.</span><span class="sxs-lookup"><span data-stu-id="44f12-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="44f12-108">На следующем изображении изображено, как выглядит вкладка **Devices** при включенной интеграции Microsoft Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="44f12-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Когда включен Microsoft Defender для конечной точки, вы можете увидеть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="44f12-110">В этом примере можно увидеть, что получатели обнаруженного сообщения электронной почты имеют четыре устройства и одно имеет оповещение.</span><span class="sxs-lookup"><span data-stu-id="44f12-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="44f12-111">Щелкнув ссылку для устройства, откроет свою страницу [в Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (ранее Центр безопасности в Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="44f12-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="44f12-112">Портал Microsoft 365 Defender заменяет Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="44f12-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="44f12-113">См. [в Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="44f12-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="44f12-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="44f12-114">Requirements</span></span>

- <span data-ttu-id="44f12-115">Ваша организация должна иметь Microsoft Defender для Office 365 (или Office 365 E5) и Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="44f12-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="44f12-116">Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44f12-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="44f12-117">[(См. разрешения в Microsoft 365 Defender)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="44f12-117">(See [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="44f12-118">Вы должны иметь доступ к Explorer (или обнаружения [в режиме реального времени).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="44f12-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="44f12-119">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="44f12-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="44f12-120">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки настроена как в Defender для конечной точки, так и в Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="44f12-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="44f12-121">В качестве глобального администратора или администратора безопасности [https://security.microsoft.com](https://security.microsoft.com) войдите и войдите.</span><span class="sxs-lookup"><span data-stu-id="44f12-121">As a global administrator or a security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> <span data-ttu-id="44f12-122">(Это передает вас на Microsoft 365 Defender портала.)</span><span class="sxs-lookup"><span data-stu-id="44f12-122">(This takes you to the Microsoft 365 Defender portal.)</span></span>

2. <span data-ttu-id="44f12-123">В области навигации выберите **обозреватель &** \> **электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="44f12-123">In the navigation pane, choose **Email & collaboration** \> **Explorer**.</span></span>

3. <span data-ttu-id="44f12-124">В правом верхнем углу экрана нажмите **кнопку MDE Параметры**.</span><span class="sxs-lookup"><span data-stu-id="44f12-124">In the upper right corner of the screen, click **MDE Settings**.</span></span>

4. <span data-ttu-id="44f12-125">В диалоговом окне Microsoft Defender для подключения к конечной точке включите Подключение **в Microsoft Defender для конечной точки.**</span><span class="sxs-lookup"><span data-stu-id="44f12-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Подключение к MDE":::

5. <span data-ttu-id="44f12-127">Перейдите на Microsoft 365 Defender портал ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="44f12-127">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="44f12-128">В панели навигации выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="44f12-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="44f12-129">Затем в **статье General** выберите **расширенные функции**.</span><span class="sxs-lookup"><span data-stu-id="44f12-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="44f12-130">Прокрутите **Office 365 для подключения к службе сведении** об угрозах и включите подключение.</span><span class="sxs-lookup"><span data-stu-id="44f12-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 связи с данными об угрозах](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="44f12-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="44f12-132">Related articles</span></span>

[<span data-ttu-id="44f12-133">Возможности расследования и реагирования на угрозы в Office 365</span><span class="sxs-lookup"><span data-stu-id="44f12-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="44f12-134">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="44f12-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="44f12-135">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="44f12-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
