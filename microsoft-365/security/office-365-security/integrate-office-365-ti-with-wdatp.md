---
title: Использование Microsoft Defender для Office 365 вместе с Microsoft Defender для конечной точки
f1.keywords:
- NOCSH
keywords: интеграция, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Используйте Microsoft Defender для Office 365 вместе с Microsoft Defender for Endpoint, чтобы получить более подробные сведения об угрозах для устройств и содержимого электронной почты.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166091"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="6f186-104">Использование Microsoft Defender для Office 365 вместе с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6f186-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6f186-105">[Microsoft Defender для Office 365](office-365-atp.md) можно настроить для работы с [Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="6f186-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="6f186-106">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки может помочь группе безопасности отслеживать и быстро действовать, если устройства пользователей находятся под угрозой.</span><span class="sxs-lookup"><span data-stu-id="6f186-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="6f186-107">Например, после включения интеграции группа операций безопасности сможет увидеть устройства, на которые может повлиять обнаруженное сообщение электронной почты, а также количество последних оповещений для этих устройств в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6f186-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="6f186-108">На следующем рисунке по изображена вкладка **"Устройства"** при включенной интеграции с Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="6f186-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Когда Microsoft Defender для конечной точки включен, вы можете увидеть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="6f186-110">В этом примере видно, что у получателей обнаруженного сообщения электронной почты четыре устройства, а на одном из них есть оповещение.</span><span class="sxs-lookup"><span data-stu-id="6f186-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="6f186-111">Щелкнув ссылку для устройства, вы откроете свою страницу в Центре безопасности Microsoft Defender ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="6f186-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="6f186-112">**[Узнайте больше о Центре](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** безопасности Microsoft Defender (также называется порталом Microsoft Defender для конечных точек).)</span><span class="sxs-lookup"><span data-stu-id="6f186-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="6f186-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6f186-113">Requirements</span></span>

- <span data-ttu-id="6f186-114">Ваша организация должна иметь Microsoft Defender для Office 365 (или Office 365 E5) и Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6f186-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="6f186-115">Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную в Центре безопасности [& соответствия требованиям.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="6f186-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="6f186-116">[(См. "Разрешения" в Центре безопасности & соответствия требованиям)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="6f186-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="6f186-117">У вас должен быть доступ к [проводнику (или](threat-explorer.md) обнаружению в режиме реального времени) в Центре безопасности & соответствия требованиям и Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6f186-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="6f186-118">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6f186-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="6f186-119">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки настроена с помощью Центра безопасности & соответствия требованиям и Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6f186-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="6f186-120">В качестве глобального администратора или администратора безопасности войдите <https://protection.office.com> и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="6f186-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="6f186-121">(Вы можете ться в Центре безопасности и соответствия & Office 365.)</span><span class="sxs-lookup"><span data-stu-id="6f186-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="6f186-122">В области навигации выберите **обозреватель управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="6f186-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Проводник в меню "Управление угрозами"](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="6f186-124">В правом верхнем углу экрана выберите "Защитник для параметров конечных точек **(параметры MDE)**".</span><span class="sxs-lookup"><span data-stu-id="6f186-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="6f186-125">В диалоговом окне подключения Microsoft Defender для конечной точки включите подключение к **Microsoft Defender для конечной точки.**</span><span class="sxs-lookup"><span data-stu-id="6f186-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender для подключения к конечной точке](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="6f186-127">Перейдите в Центр безопасности Microsoft Defender ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="6f186-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="6f186-128">На панели навигации выберите **"Параметры".**</span><span class="sxs-lookup"><span data-stu-id="6f186-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="6f186-129">Затем в области **"Общие"** выберите **дополнительные функции.**</span><span class="sxs-lookup"><span data-stu-id="6f186-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="6f186-130">Прокрутите вниз до **подключения Office 365 Threat Intelligence** и включите подключение.</span><span class="sxs-lookup"><span data-stu-id="6f186-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Подключение аналитики угроз Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="6f186-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6f186-132">Related articles</span></span>

[<span data-ttu-id="6f186-133">Возможности исследования угроз и реагирования на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="6f186-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="6f186-134">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="6f186-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="6f186-135">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6f186-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
