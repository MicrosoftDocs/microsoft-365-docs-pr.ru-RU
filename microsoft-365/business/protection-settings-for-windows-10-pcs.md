---
title: Настройка параметров защиты устройств для компьютеров с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Узнайте о том, как использовать по умолчанию и другие параметры, доступные в Microsoft 365 Business для защиты устройств с Windows 10.
ms.openlocfilehash: 5dc6ede8f31f5837d59c200e0b76083dcf419e05
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660402"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="f4dc8-103">Настройка параметров защиты устройств для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="f4dc8-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="f4dc8-104">Защита устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="f4dc8-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="f4dc8-105">Просмотрите видео о том, как защитить устройства с Windows 10 с помощью Office 365 бизнес:</span><span class="sxs-lookup"><span data-stu-id="f4dc8-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="f4dc8-106">СГО в центр администрирования по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-106">SGo to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="f4dc8-107">В левой панели навигации выберите пункт \*\*\*\* \> **политики** \> устройств **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="f4dc8-108">На панели **Добавить политику** введите уникальное имя политики.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="f4dc8-109">В поле **Тип политики** выберите **Конфигурация устройства с Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="f4dc8-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information.</span></span> 
    
    <span data-ttu-id="f4dc8-112">Вы всегда можете вернуться к значениям по умолчанию с помощью ссылки **Восстановление параметров по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-112">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="f4dc8-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="f4dc8-116">Нажмите кнопку **Готово**, чтобы сохранить политику и назначить ее устройствам.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="f4dc8-117">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="f4dc8-117">Available settings</span></span>

<span data-ttu-id="f4dc8-p103">Все параметры **включены** по умолчанию. Доступные параметры перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="f4dc8-120">Дополнительные сведения см. в статье [Как функции защиты в Microsoft 365 бизнес соотносятся с параметрами Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f4dc8-120">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f4dc8-121">Setting</span><span class="sxs-lookup"><span data-stu-id="f4dc8-121">Setting</span></span>  <br/> |<span data-ttu-id="f4dc8-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f4dc8-122">Description</span></span>  <br/> |
|<span data-ttu-id="f4dc8-123">Использование антивирусной программы "Защитник Windows"</span><span class="sxs-lookup"><span data-stu-id="f4dc8-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="f4dc8-124">Требует включения антивирусной программы "Защитник Windows" для защиты компьютеров, подключенных к Интернету.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="f4dc8-125">Защитите компьютеры от угроз из Интернета в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f4dc8-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="f4dc8-126">Включает параметры в Microsoft Edge, которые помогают защитить пользователей от вредоносных сайтов и скачиваний.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="f4dc8-127">Использовать правила для ограничения направлений атак на устройства</span><span class="sxs-lookup"><span data-stu-id="f4dc8-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="f4dc8-p104">Если этот параметр включен, ограничение направлений атак позволяет блокировать действия и приложения, которые вредоносные программы обычно используют для заражения устройств. Этот параметр доступен, только если включена антивирусная программа "Защитник Windows". Дополнительные сведения см. в статье [Уменьшение уязвимой зоны](https://go.microsoft.com/fwlink/?linkid=870417).  </span><span class="sxs-lookup"><span data-stu-id="f4dc8-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="f4dc8-131">Защитить папки от угроз, таких как программы-шантажисты</span><span class="sxs-lookup"><span data-stu-id="f4dc8-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="f4dc8-p105">Этот параметр использует управляемый доступ к папкам для защиты корпоративных данных от внесения изменений подозрительными или вредоносными приложениями, такими как программы-шантажисты. Таким приложениям запрещается внесение изменений в защищенных папках. Этот параметр доступен, только если включена антивирусная программа "Защитник Windows". Дополнительные сведения см. в статье [Защита важных папок с помощью управляемого доступа к папкам](https://go.microsoft.com/fwlink/?linkid=870418).  </span><span class="sxs-lookup"><span data-stu-id="f4dc8-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="f4dc8-136">Запретить доступ из сети к потенциально вредоносному содержимому в Интернете</span><span class="sxs-lookup"><span data-stu-id="f4dc8-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="f4dc8-p106">Этот параметр используется для блокировки исходящих подключений пользователей к интернет-расположениям с низкой репутацией, в которых могут размещается фишинговые сообщения, эксплойты и другое вредоносное содержимое. Этот параметр доступен, только если включена антивирусная программа "Защитник Windows". Дополнительные сведения см. в статье [Защитите свою сеть](https://go.microsoft.com/fwlink/?linkid=870419).  </span><span class="sxs-lookup"><span data-stu-id="f4dc8-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="f4dc8-140">Защитить файлы и папки на компьютерах от несанкционированного доступа с помощью BitLocker</span><span class="sxs-lookup"><span data-stu-id="f4dc8-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="f4dc8-p107">BitLocker защищает данные от раскрытия в случае потери или кражи компьютера путем шифрования его жестких дисков. Дополнительные сведения см. в статье [Вопросы и ответы по BitLocker](https://go.microsoft.com/fwlink/?linkid=871000).  </span><span class="sxs-lookup"><span data-stu-id="f4dc8-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="f4dc8-143">Разрешить пользователям скачивать приложения из Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f4dc8-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="f4dc8-p108">Позволяет пользователям скачивать и устанавливать приложения из Microsoft Store. Это касается любых приложений, от инструментов для повышения производительности до игр, поэтому этот параметр **включен**, но его можно отключить, чтобы обеспечить дополнительную защиту.  </span><span class="sxs-lookup"><span data-stu-id="f4dc8-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="f4dc8-146">Разрешить пользователям доступ к Кортане</span><span class="sxs-lookup"><span data-stu-id="f4dc8-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="f4dc8-p109">Кортана может быть очень полезной. Она умеет включать и отключать для вас параметры, давать рекомендации или следить, чтобы вы не пропустили назначенные встречи, поэтому этот параметр **включен** по умолчанию.  </span><span class="sxs-lookup"><span data-stu-id="f4dc8-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="f4dc8-149">Разрешить пользователям получать советы и объявления для Windows от Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f4dc8-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="f4dc8-150">Советы для Windows могут оказаться очень кстати. Они помогают пользователям сориентироваться, когда выпускаются новые возможности.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="f4dc8-151">Автоматически обновлять устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="f4dc8-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="f4dc8-152">Обеспечивает автоматическую установку последних обновлений на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="f4dc8-153">Выключать экран устройства, если оно неактивно в течение указанного периода времени</span><span class="sxs-lookup"><span data-stu-id="f4dc8-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="f4dc8-p110">Обеспечивает защиту корпоративных данных, когда пользователь неактивен. Пользователь может работать в общественном месте, например кафе, и на короткое время отойти или отвлечься. При этом посторонние могут случайно увидеть сведения на экране. Этот параметр управляет временем, на протяжении которого пользователь может оставаться неактивным, прежде чем экран выключится.</span><span class="sxs-lookup"><span data-stu-id="f4dc8-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

