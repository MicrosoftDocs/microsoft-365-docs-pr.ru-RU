---
title: Используйте Microsoft Defender для Office 365 вместе с Microsoft Defender для конечной точки
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
description: Используйте Microsoft Defender для Office 365 вместе с Microsoft Defender для конечной точки, чтобы получить более подробные сведения об угрозах в отношении устройств и контента электронной почты.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bac2414419d673f261d0d0162d8ae742385fd4eb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073278"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="b7b60-104">Используйте Microsoft Defender для Office 365 вместе с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b7b60-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b7b60-105">[Microsoft Defender для Office 365](defender-for-office-365.md) можно настроить для работы с [Microsoft Defender для конечной точки.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="b7b60-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="b7b60-106">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки может помочь группе безопасности отслеживать и быстро принимать меры, если устройства пользователей находятся под угрозой.</span><span class="sxs-lookup"><span data-stu-id="b7b60-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="b7b60-107">Например, после включения интеграции группа операций безопасности сможет видеть устройства, которые потенциально затронуты обнаруженным сообщением электронной почты, а также количество последних оповещений для этих устройств в Microsoft Defender для Endpoint.</span><span class="sxs-lookup"><span data-stu-id="b7b60-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="b7b60-108">На следующем изображении изображено, как выглядит вкладка **Devices** при включенной интеграции Microsoft Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="b7b60-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Когда включен Microsoft Defender для конечной точки, вы можете увидеть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="b7b60-110">В этом примере можно увидеть, что получатели обнаруженного сообщения электронной почты имеют четыре устройства и одно имеет оповещение.</span><span class="sxs-lookup"><span data-stu-id="b7b60-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="b7b60-111">Щелкнув ссылку для устройства, откроет свою страницу в центре безопасности Microsoft Defender <https://securitycenter.windows.com> ().</span><span class="sxs-lookup"><span data-stu-id="b7b60-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="b7b60-112">**[Дополнительные информацию о Центре безопасности защитника](/windows/security/threat-protection/microsoft-defender-atp/use)** Майкрософт (также именуемом порталом Microsoft Defender для конечных точек).)</span><span class="sxs-lookup"><span data-stu-id="b7b60-112">**[Learn more about the Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="b7b60-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b7b60-113">Requirements</span></span>

- <span data-ttu-id="b7b60-114">В организации должны быть Microsoft Defender для Office 365 (или Office 365 E5) и Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b7b60-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="b7b60-115">Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную в Центре & [безопасности.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="b7b60-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="b7b60-116">(См. разрешения в центре [& безопасности)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="b7b60-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="b7b60-117">Вы должны иметь доступ как [к Explorer (так](threat-explorer.md) и к обнаружениям в режиме реального времени) в Центре & безопасности и Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b7b60-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="b7b60-118">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b7b60-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="b7b60-119">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки создана с помощью Центра & безопасности и Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b7b60-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="b7b60-120">В качестве глобального администратора или администратора безопасности <https://protection.office.com> войдите и войдите.</span><span class="sxs-lookup"><span data-stu-id="b7b60-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="b7b60-121">(Это делает вас в Центре безопасности Office 365 & соответствия требованиям.)</span><span class="sxs-lookup"><span data-stu-id="b7b60-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="b7b60-122">В области навигации выберите **Обозреватель управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="b7b60-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Обозреватель в меню Управления угрозами](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="b7b60-124">В правом верхнем углу экрана выберите Параметры защитника для конечных точек **(параметры MDE).**</span><span class="sxs-lookup"><span data-stu-id="b7b60-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="b7b60-125">В диалоговом окне Microsoft Defender для подключения к конечной точке включите подключение к **Microsoft Defender для конечной точки.**</span><span class="sxs-lookup"><span data-stu-id="b7b60-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender для подключения к конечной точке](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="b7b60-127">Перейдите в Центр безопасности защитника Майкрософт <https://securitycenter.windows.com> ().</span><span class="sxs-lookup"><span data-stu-id="b7b60-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="b7b60-128">В панели навигации выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="b7b60-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="b7b60-129">Затем в **статье General** выберите **расширенные функции**.</span><span class="sxs-lookup"><span data-stu-id="b7b60-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="b7b60-130">Прокрутите **вниз до подключения к Office 365 Threat Intelligence** и включите подключение.</span><span class="sxs-lookup"><span data-stu-id="b7b60-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Подключение к сведениям об угрозах Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="b7b60-132">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b7b60-132">Related articles</span></span>

[<span data-ttu-id="b7b60-133">Возможности расследования и реагирования на угрозы в Office 365</span><span class="sxs-lookup"><span data-stu-id="b7b60-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="b7b60-134">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b7b60-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="b7b60-135">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b7b60-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)