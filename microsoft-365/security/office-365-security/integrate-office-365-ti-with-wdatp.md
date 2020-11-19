---
title: Использование защитника Microsoft для Office 365 вместе с защитником Майкрософт для конечной точки
f1.keywords:
- NOCSH
keywords: интеграция, защитник Майкрософт, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Используйте защитник Майкрософт для Office 365 вместе с защитником Майкрософт для конечной точки, чтобы получить более подробные сведения о угрозах для ваших устройств и содержимого электронной почты.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f668aa1234509789dacd2b018b94f1bfbc79e2c
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357783"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="1150f-104">Использование защитника Microsoft для Office 365 вместе с защитником Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1150f-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1150f-105">[Защитник Майкрософт для Office 365](office-365-atp.md) можно настроить для работы с [защитником Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="1150f-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="1150f-106">Интеграция защитника Microsoft для Office 365 с помощью защитника Майкрософт для конечной точки может помочь вашей группе управления операциями безопасности и быстро выполнить действия в случае риска на устройствах пользователей.</span><span class="sxs-lookup"><span data-stu-id="1150f-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="1150f-107">Например, если интеграция включена, Группа операций безопасности сможет видеть устройства, на которые потенциально влияет обнаруженное сообщение электронной почты, а также количество последних оповещений, созданных для этих устройств в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1150f-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="1150f-108">На следующем рисунке показано, как выглядит эта вкладка " **устройства** " с включенным защитником Майкрософт для интеграции конечных точек:</span><span class="sxs-lookup"><span data-stu-id="1150f-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>
  
![Если защитник Майкрософт для конечной точки включен, вы можете просмотреть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="1150f-110">В этом примере видно, что получатели обнаруженного сообщения электронной почты имеют четыре устройства, а одно — оповещение.</span><span class="sxs-lookup"><span data-stu-id="1150f-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="1150f-111">Щелчок ссылки на устройство открывает его страницу в центре безопасности защитника (Майкрософт) ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="1150f-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="1150f-112">**[Узнайте больше о центре безопасности защитника Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (также называемом защитником Майкрософт для портала конечных точек).</span><span class="sxs-lookup"><span data-stu-id="1150f-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="1150f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1150f-113">Requirements</span></span>

- <span data-ttu-id="1150f-114">У вашей организации должен быть защитник Майкрософт для Office 365 (или Office 365 в ~) и защитник Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1150f-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>
    
- <span data-ttu-id="1150f-115">Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную [в &amp; центре безопасности и соответствия требованиям](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="1150f-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="1150f-116">(См. [разрешения в центре безопасности и &amp; соответствия требованиям](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="1150f-116">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="1150f-117">Необходимо иметь доступ к [проводнику (или обнаружениям в режиме реального времени)](threat-explorer.md) в центре безопасности & соответствия требованиям и центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1150f-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="1150f-118">Интеграция защитника Microsoft для Office 365 с защитником Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1150f-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="1150f-119">Интеграция защитника Microsoft для Office 365 с защитником Майкрософт для конечной точки настраивается с помощью центра безопасности & соответствия требованиям и центра безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1150f-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="1150f-120">Как глобальный администратор или администратор безопасности перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="1150f-120">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="1150f-121">(Откроется центр соответствия требованиям & безопасности Office 365.)</span><span class="sxs-lookup"><span data-stu-id="1150f-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="1150f-122">В области навигации выберите Обозреватель **управления угрозами**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="1150f-122">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="1150f-123">![Проводник в меню "Управление угрозами"](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="1150f-123">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="1150f-124">В правом верхнем углу экрана выберите пункт **защитник для параметров конечной точки**.</span><span class="sxs-lookup"><span data-stu-id="1150f-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings**.</span></span>
    
4. <span data-ttu-id="1150f-125">В диалоговом окне защитник (Майкрософт) для подключения к конечной точке включите параметр **подключиться к защитнику Майкрософт для конечной точки**.</span><span class="sxs-lookup"><span data-stu-id="1150f-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span><br><span data-ttu-id="1150f-126">![Защитник Майкрософт для подключения к конечной точке](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="1150f-126">![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="1150f-127">Перейдите в центр безопасности защитника (Майкрософт [https://securitycenter.windows.com](https://securitycenter.windows.com) ) ().</span><span class="sxs-lookup"><span data-stu-id="1150f-127">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="1150f-128">В панели навигации выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="1150f-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="1150f-129">Затем в разделе **Общие** выберите **Дополнительные функции**.</span><span class="sxs-lookup"><span data-stu-id="1150f-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="1150f-130">Прокрутите список вниз до раздела **Office 365 Threat Intelligence Connection** и включите подключение.</span><span class="sxs-lookup"><span data-stu-id="1150f-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="1150f-131">![Подключение к бизнес-аналитике Office 365](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="1150f-131">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="1150f-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1150f-132">Related articles</span></span>

[<span data-ttu-id="1150f-133">Исследование угроз и возможности реагирования в Office 365</span><span class="sxs-lookup"><span data-stu-id="1150f-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="1150f-134">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="1150f-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
  
[<span data-ttu-id="1150f-135">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1150f-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
