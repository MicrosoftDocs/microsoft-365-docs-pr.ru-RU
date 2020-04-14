---
title: Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
ms.openlocfilehash: a2634a70bdbdd21efe2c59721e5532500eb4e4cc
ms.sourcegitcommit: 4c6af6530b4997055b8e60bf532e75cbc72fb6c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "43284231"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="41a4c-103">Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="41a4c-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="41a4c-104">Если вы участвуете в группе безопасности Организации, вы можете интегрировать [Office 365 Advanced Threat protection](office-365-atp.md) и соответствующие функции расследования и ответа с помощью [Advanced Threat Protection в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="41a4c-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="41a4c-105">Это поможет быстро выяснить, подвержены ли компьютеры пользователям риску при изучении угроз в Office 365.</span><span class="sxs-lookup"><span data-stu-id="41a4c-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="41a4c-106">Например, после включения интеграции вы сможете просмотреть список компьютеров, используемых получателями обнаруженного сообщения электронной почты, а также о том, сколько последних оповещений у этих компьютеров у них есть в Advanced Threat Protection в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="41a4c-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="41a4c-107">На следующем рисунке показана вкладка " **устройства** ", которая будет отображаться при включенной интеграции защитника Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="41a4c-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![Когда включен пакет ATP для защитника, вы можете просмотреть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="41a4c-109">В этом примере видно, что получатели сообщения электронной почты имеют четыре устройства, а одно — оповещение.</span><span class="sxs-lookup"><span data-stu-id="41a4c-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="41a4c-110">Щелчок ссылки на устройство открывает его страницу в центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="41a4c-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="41a4c-111">Requirements</span><span class="sxs-lookup"><span data-stu-id="41a4c-111">Requirements</span></span>

- <span data-ttu-id="41a4c-112">В вашей организации должен быть Office 365 ATP (план 2) (или Office 365 в) и пакет ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="41a4c-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="41a4c-113">Необходимо быть глобальным администратором Office 365 или иметь роль администратора безопасности (например, администратора безопасности), назначенную в [центре &amp; безопасности и соответствия требованиям](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="41a4c-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="41a4c-114">(См. [разрешения в центре безопасности &amp; и соответствия требованиям Office 365](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="41a4c-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="41a4c-115">Необходимо иметь доступ к [проводнику (или обнаружениям в режиме реального времени)](threat-explorer.md) в центре безопасности & соответствия требованиям и центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="41a4c-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="41a4c-116">Интеграция Office 365 ATP с защитником Microsoft для пакета ATP</span><span class="sxs-lookup"><span data-stu-id="41a4c-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="41a4c-117">Интеграция Office 365 ATP с защитником Microsoft для пакета ATP настроена с помощью центра безопасности & Office 365 и центра безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="41a4c-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Office 365 Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="41a4c-118">Как глобальный администратор Office 365 или администратор безопасности перейдите на [https://protection.office.com](https://protection.office.com) страницу и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="41a4c-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>
    
2. <span data-ttu-id="41a4c-119">Выберите \> **Обозреватель** **управления угрозами** .</span><span class="sxs-lookup"><span data-stu-id="41a4c-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="41a4c-120">![Проводник в меню "Управление угрозами"](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="41a4c-120">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="41a4c-121">В правом верхнем углу экрана выберите **Параметры вдатп**.</span><span class="sxs-lookup"><span data-stu-id="41a4c-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="41a4c-122">В диалоговом окне Подключение к Защитнику (Майкрософт) ATP включите параметр **подключиться к Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="41a4c-122">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="41a4c-123">![Подключение к Microsoft Defender ATP](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="41a4c-123">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="41a4c-124">Включите подключение в центре безопасности защитника (Майкрософт)[https://securitycenter.windows.com](https://securitycenter.windows.com)().</span><span class="sxs-lookup"><span data-stu-id="41a4c-124">Enable the connection in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="41a4c-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="41a4c-125">Related topics</span></span>

[<span data-ttu-id="41a4c-126">Исследование угроз и возможности реагирования в Office 365</span><span class="sxs-lookup"><span data-stu-id="41a4c-126">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="41a4c-127">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="41a4c-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

