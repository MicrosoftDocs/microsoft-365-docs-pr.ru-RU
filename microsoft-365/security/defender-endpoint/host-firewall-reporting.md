---
title: Учет брандмауэра в Microsoft Defender для конечной точки
description: Хост и просмотр отчетов брандмауэра в Microsoft 365 центре безопасности.
keywords: защитник windows, брандмауэр
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809344"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3756a-104">Учет брандмауэра в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3756a-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3756a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3756a-105">**Applies to:**</span></span>
- [<span data-ttu-id="3756a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3756a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3756a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3756a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3756a-108">Если вы администратор, теперь вы можете принимать отчеты брандмауэра в центр Microsoft 365 [безопасности.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3756a-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="3756a-109">Эта функция позволяет просматривать отчеты Windows 10 и Windows server 2019 из централизованного расположения.</span><span class="sxs-lookup"><span data-stu-id="3756a-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3756a-110">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="3756a-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="3756a-111">Необходимо запускать Windows 10 или Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3756a-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="3756a-112">С бортовых устройств в службу Microsoft Defender для конечных точек см. [здесь.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="3756a-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="3756a-113">Чтобы Microsoft 365 центр безопасности начал получать данные, необходимо  включить события аудита для брандмауэр Защитника Windows с помощью advanced Security:</span><span class="sxs-lookup"><span data-stu-id="3756a-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="3756a-114">Падение пакетов платформы фильтрации аудита</span><span class="sxs-lookup"><span data-stu-id="3756a-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="3756a-115">Подключение платформы фильтрации аудита</span><span class="sxs-lookup"><span data-stu-id="3756a-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="3756a-116">Включить эти события с помощью редактора объектов групповой политики, локальной политики безопасности или auditpol.exe команд.</span><span class="sxs-lookup"><span data-stu-id="3756a-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="3756a-117">Дополнительные сведения см. [здесь.](/windows/win32/fwp/auditing-and-logging)</span><span class="sxs-lookup"><span data-stu-id="3756a-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="3756a-118">Две команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3756a-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="3756a-119">**auditpol /set/subcategory:"Filtering Platform Packet Drop" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="3756a-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="3756a-120">**auditpol /set/subcategory:"Filtering Platform Connection" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="3756a-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="3756a-121">Процесс</span><span class="sxs-lookup"><span data-stu-id="3756a-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="3756a-122">Обязательно следуйте инструкциям из раздела выше и правильно настройте устройства для участия в предварительном предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="3756a-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="3756a-123">После включения событий центр Microsoft 365 начнет отслеживать данные.</span><span class="sxs-lookup"><span data-stu-id="3756a-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="3756a-124">Удаленный IP-адрес, удаленный порт, локальный порт, локальный IP, имя компьютера, процесс между входящие и исходящие подключения.</span><span class="sxs-lookup"><span data-stu-id="3756a-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="3756a-125">Администраторы теперь могут видеть Windows брандмауэра [](https://security.microsoft.com/firewall)здесь .</span><span class="sxs-lookup"><span data-stu-id="3756a-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="3756a-126">Дополнительные отчеты можно упростить, скачав скрипт настраиваемой отчетности для мониторинга брандмауэр Защитника Windows с помощью Power BI. [](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)</span><span class="sxs-lookup"><span data-stu-id="3756a-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="3756a-127">До отражения данных может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="3756a-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="3756a-128">Поддерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="3756a-128">Supported scenarios</span></span>
<span data-ttu-id="3756a-129">Следующие сценарии поддерживаются во время предварительного просмотра Ring0.</span><span class="sxs-lookup"><span data-stu-id="3756a-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="3756a-130">Отчеты о брандмауэре в центре безопасности</span><span class="sxs-lookup"><span data-stu-id="3756a-130">Firewall reporting in security center</span></span>

<span data-ttu-id="3756a-131">Вот несколько примеров страниц отчета брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="3756a-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="3756a-132">Здесь вы найдете сводку действий входящие, исходящие и приложения.</span><span class="sxs-lookup"><span data-stu-id="3756a-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="3756a-133">Вы можете получить доступ к этой странице напрямую, переехав https://security.microsoft.com/firewall на .</span><span class="sxs-lookup"><span data-stu-id="3756a-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3756a-134">![Страница отчетов о брандмауэре хост](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="3756a-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="3756a-135">К этим отчетам также можно получить доступ, переехав в службу **Reports**  >  **Security Report**  >  **Devices** (section),  расположенную в нижней части карты заблокированных подключений к брандмауэру.</span><span class="sxs-lookup"><span data-stu-id="3756a-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="3756a-136">От "Компьютеры с заблокированным подключением" к устройству</span><span class="sxs-lookup"><span data-stu-id="3756a-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="3756a-137">Карты поддерживают интерактивные объекты.</span><span class="sxs-lookup"><span data-stu-id="3756a-137">Cards support interactive objects.</span></span> <span data-ttu-id="3756a-138">Вы можете сверлить активность устройства, нажав на имя устройства, которое запустится на новой вкладке, и отвести вас непосредственно на вкладку https://securitycenter.microsoft.com **Timeline** устройства.</span><span class="sxs-lookup"><span data-stu-id="3756a-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3756a-139">![Компьютеры с заблокированным подключением](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="3756a-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="3756a-140">Теперь вы можете выбрать вкладку **Timeline,** которая даст вам список событий, связанных с этим устройством.</span><span class="sxs-lookup"><span data-stu-id="3756a-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="3756a-141">После нажатия кнопки **"Фильтры"** в правом верхнем углу области просмотра выберите нужный тип события.</span><span class="sxs-lookup"><span data-stu-id="3756a-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="3756a-142">В этом случае выберите **события Брандмауэра,** и области будут фильтроваться для событий Брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="3756a-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3756a-143">![Кнопка Фильтры](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="3756a-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="3756a-144">Упражнение в продвинутую охоту (предварительное обновление)</span><span class="sxs-lookup"><span data-stu-id="3756a-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="3756a-145">Брандмауэр сообщает о поддержке бурения с карты непосредственно в **advanced Hunting,** нажав кнопку **Open Advanced hunting.**</span><span class="sxs-lookup"><span data-stu-id="3756a-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="3756a-146">Запрос будет предварительно заполнен.</span><span class="sxs-lookup"><span data-stu-id="3756a-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3756a-147">![Кнопка Open Advanced hunting](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="3756a-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="3756a-148">Теперь запрос можно выполнять, а все связанные события брандмауэра за последние 30 дней можно изучить.</span><span class="sxs-lookup"><span data-stu-id="3756a-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="3756a-149">Для дополнительных отчетов или пользовательских изменений запрос можно экспортировать в Power BI для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="3756a-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="3756a-150">Настраиваемые отчеты можно упростить, скачав сценарий настраиваемой отчетности для мониторинга брандмауэр Защитника Windows с помощью Power BI. [](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)</span><span class="sxs-lookup"><span data-stu-id="3756a-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 