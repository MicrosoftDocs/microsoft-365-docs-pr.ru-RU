---
title: Интеграция ATP Office 365 с ATP в Microsoft Defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт для просмотра подробных сведений об управлении угрозами.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086712"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="4cff0-103">Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4cff0-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="4cff0-104">[Office 365 Advanced Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) можно настроить для работы с [Advanced Threat Protection в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection) (Майкрософт Defender ATP).</span><span class="sxs-lookup"><span data-stu-id="4cff0-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="4cff0-105">Интеграция Office 365 ATP с помощью защитника Microsoft Defender может помочь вам в обеспечении безопасности групп и быстро предпринимать действия в случае, если устройства пользователей подвержены риску.</span><span class="sxs-lookup"><span data-stu-id="4cff0-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="4cff0-106">Например, если интеграция включена, Группа операций безопасности сможет просматривать устройства, на которые потенциально влияет обнаруженное сообщение электронной почты, а также количество последних оповещений, которые эти устройства имеют в пакет ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4cff0-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="4cff0-107">На следующем рисунке показано, как выглядит вкладка " **устройства** " с включенной интеграцией Microsoft Defender ATP:</span><span class="sxs-lookup"><span data-stu-id="4cff0-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![Когда включен пакет ATP для защитника, вы можете просмотреть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="4cff0-109">В этом примере видно, что получатели обнаруженного сообщения электронной почты имеют четыре устройства, а одно — оповещение.</span><span class="sxs-lookup"><span data-stu-id="4cff0-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="4cff0-110">Щелчок ссылки на устройство открывает его страницу в центре безопасности защитника (Майкрософт) ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="4cff0-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="4cff0-111">**[Узнайте больше о центре безопасности защитника](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (Майкрософт), также называемом порталом ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4cff0-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4cff0-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="4cff0-112">Requirements</span></span>

- <span data-ttu-id="4cff0-113">В вашей организации должен быть Office 365 ATP (план 2) (или Office 365 в) и пакет ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4cff0-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="4cff0-114">Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную [в &amp; центре безопасности и соответствия требованиям](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="4cff0-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="4cff0-115">(См. [разрешения в центре безопасности и &amp; соответствия требованиям](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="4cff0-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="4cff0-116">Необходимо иметь доступ к [проводнику (или обнаружениям в режиме реального времени)](threat-explorer.md) в центре безопасности & соответствия требованиям и центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4cff0-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="4cff0-117">Интеграция Office 365 ATP с защитником Microsoft для пакета ATP</span><span class="sxs-lookup"><span data-stu-id="4cff0-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="4cff0-118">Интеграция Office 365 ATP с защитником Microsoft для пакета ATP настроена с помощью центра безопасности & соответствия требованиям и центра безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4cff0-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="4cff0-119">Как глобальный администратор или администратор безопасности перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="4cff0-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="4cff0-120">(Откроется центр соответствия требованиям & безопасности Office 365.)</span><span class="sxs-lookup"><span data-stu-id="4cff0-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="4cff0-121">В области навигации выберите Обозреватель **управления угрозами**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4cff0-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="4cff0-122">![Проводник в меню "Управление угрозами"](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="4cff0-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="4cff0-123">В правом верхнем углу экрана выберите **Параметры вдатп**.</span><span class="sxs-lookup"><span data-stu-id="4cff0-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="4cff0-124">В диалоговом окне Подключение к Защитнику (Майкрософт) ATP включите параметр **подключиться к Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="4cff0-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="4cff0-125">![Подключение к Microsoft Defender ATP](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="4cff0-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="4cff0-126">Перейдите в центр безопасности защитника (Майкрософт [https://securitycenter.windows.com](https://securitycenter.windows.com) ) ().</span><span class="sxs-lookup"><span data-stu-id="4cff0-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="4cff0-127">В панели навигации выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="4cff0-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="4cff0-128">Затем в разделе **Общие**выберите **Дополнительные функции**.</span><span class="sxs-lookup"><span data-stu-id="4cff0-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="4cff0-129">Прокрутите список вниз до раздела **Office 365 Threat Intelligence Connection**и включите подключение.</span><span class="sxs-lookup"><span data-stu-id="4cff0-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="4cff0-130">![Подключение к бизнес-аналитике Office 365](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="4cff0-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="4cff0-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4cff0-131">Related articles</span></span>

[<span data-ttu-id="4cff0-132">Исследование угроз и возможности реагирования в Office 365</span><span class="sxs-lookup"><span data-stu-id="4cff0-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="4cff0-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4cff0-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="4cff0-134">ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4cff0-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
