---
title: Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/22/2019
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
ms.openlocfilehash: fc2db4c1a3e5b32206ee91cae9f5adbeae4875d4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599136"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="0ac60-103">Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0ac60-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="0ac60-104">Если вы участвуете в группе безопасности Организации, вы можете интегрировать [Office 365 Advanced Threat protection](office-365-atp.md) и соответствующие функции расследования и ответа с помощью [Advanced Threat Protection в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="0ac60-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="0ac60-105">Это поможет быстро выяснить, подвержены ли компьютеры пользователям риску при изучении угроз в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0ac60-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="0ac60-106">Например, после включения интеграции вы сможете просмотреть список компьютеров, используемых получателями обнаруженного сообщения электронной почты, а также о том, сколько последних оповещений у этих компьютеров у них есть в Advanced Threat Protection в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0ac60-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="0ac60-107">На следующем рисунке показана вкладка " **устройства** ", которая будет отображаться при включенной интеграции защитника Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="0ac60-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![Когда включен пакет ATP для защитника, вы можете просмотреть список компьютеров с оповещениями.](../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="0ac60-109">В этом примере видно, что получатели сообщения электронной почты имеют четыре устройства, а одно — оповещение.</span><span class="sxs-lookup"><span data-stu-id="0ac60-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="0ac60-110">Щелчок ссылки на устройство открывает его страницу в центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0ac60-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="0ac60-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0ac60-111">Requirements</span></span>

- <span data-ttu-id="0ac60-112">В вашей организации должен быть Office 365 ATP (план 2) (или Office 365 в) и пакет ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0ac60-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="0ac60-113">Необходимо быть глобальным администратором Office 365 или иметь роль администратора безопасности (например, администратора безопасности), назначенную в [центре &amp; безопасности и соответствия требованиям](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="0ac60-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="0ac60-114">(См. [разрешения в центре безопасности &amp; и соответствия требованиям Office 365](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="0ac60-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="0ac60-115">Необходимо иметь доступ к [проводнику (или обнаружениям в режиме реального времени)](threat-explorer.md) в центре безопасности & соответствия требованиям и центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0ac60-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="0ac60-116">Интеграция Office 365 ATP с защитником Microsoft для пакета ATP</span><span class="sxs-lookup"><span data-stu-id="0ac60-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="0ac60-117">Интеграция Office 365 ATP с защитником Microsoft для пакета ATP настроена с помощью центра безопасности & соответствия требованиям и центра безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0ac60-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="0ac60-118">Как глобальный администратор Office 365 или администратор безопасности перейдите к [https://protection.office.com](https://protection.office.com) рабочей или учебной учетной записи для Office 365 с помощью рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="0ac60-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span>
    
2. <span data-ttu-id="0ac60-119">Выберите \> **Обозреватель** **управления угрозами** .</span><span class="sxs-lookup"><span data-stu-id="0ac60-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="0ac60-120">![Проводник в меню "Управление угрозами"](../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="0ac60-120">![Explorer in Threat Management menu](../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="0ac60-121">В правом верхнем углу экрана выберите **Параметры вдатп**.</span><span class="sxs-lookup"><span data-stu-id="0ac60-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="0ac60-122">В диалоговом окне Подключение ATP для защитника Windows включите параметр подключиться к Windows ATP.</span><span class="sxs-lookup"><span data-stu-id="0ac60-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Подключение к Microsoft Defender ATP](../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="0ac60-124">Включите подключение в центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0ac60-124">Enable the connection in the Microsoft Defender Security Center.</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="0ac60-125">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="0ac60-125">Related topics</span></span>

[<span data-ttu-id="0ac60-126">Исследование угроз для Office 365 и ответ на них</span><span class="sxs-lookup"><span data-stu-id="0ac60-126">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="0ac60-127">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0ac60-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

