---
title: Скрыть антивирусный интерфейс Microsoft Defender
description: В приложении Windows Security можно скрыть плитку защиты от вирусов и угроз.
keywords: Блокировка пользовательского интерфейса, режим без головы, скрыть приложение, скрыть параметры, скрыть интерфейс
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274920"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="2d0e8-104">Запретить пользователям видеть и взаимодействовать с пользовательским интерфейсом антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2d0e8-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2d0e8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2d0e8-105">**Applies to:**</span></span>

- [<span data-ttu-id="2d0e8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2d0e8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2d0e8-107">Можно использовать групповую политику, чтобы запретить пользователям конечных точек видеть антивирусный интерфейс Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="2d0e8-108">Вы также можете запретить им прио паузу в проверке.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="2d0e8-109">Скрыть антивирусный интерфейс Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2d0e8-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="2d0e8-110">В Windows 10 версии 1703 скрытие интерфейса скроет уведомления о антивирусе Microsoft Defender и предотвратит & защиты от угрозы в приложении Windows Security.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="2d0e8-111">С набором параметров **включен:**</span><span class="sxs-lookup"><span data-stu-id="2d0e8-111">With the setting set to **Enabled**:</span></span>

![Снимок экрана Windows Security без значка щита и раздела защиты от вирусов и угроз](images/defender/wdav-headless-mode-1703.png)

<span data-ttu-id="2d0e8-113">С набором параметра **Отключено или** не настроено:</span><span class="sxs-lookup"><span data-stu-id="2d0e8-113">With the setting set to **Disabled** or not configured:</span></span>

![Снимок экрана Windows Security, показывающий значок щита и раздел защиты от вирусов и угроз](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
><span data-ttu-id="2d0e8-115">Сокрытие интерфейса также предотвратит появления антивирусных уведомлений Microsoft Defender на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="2d0e8-116">Уведомления Microsoft Defender для конечной точки по-прежнему будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="2d0e8-117">Кроме того, можно настроить уведомления, которые отображаются [в конечных точках.](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="2d0e8-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="2d0e8-118">В более ранних версиях Windows 10 параметр будет скрывать Защитник Windows клиентского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="2d0e8-119">Если пользователь по пытается открыть его, ему будет объявлено предупреждение: "Администратор системы имеет ограниченный доступ к этому приложению".</span><span class="sxs-lookup"><span data-stu-id="2d0e8-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

![Предупреждение при включенном безголовом режиме в Windows 10, версии более ранних версий 1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="2d0e8-121">Использование групповой политики для сокрытия интерфейса av-интерфейса Microsoft Defender от пользователей</span><span class="sxs-lookup"><span data-stu-id="2d0e8-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="2d0e8-122">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2d0e8-123">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="2d0e8-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="2d0e8-124">Щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="2d0e8-125">Расширь дерево до **компонентов Windows и > антивируса Microsoft Defender > клиентского интерфейса.**</span><span class="sxs-lookup"><span data-stu-id="2d0e8-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="2d0e8-126">Дважды щелкните **параметр Включить безголевую настройку пользовательского интерфейса** и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="2d0e8-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="2d0e8-127">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-127">Click **OK**.</span></span> 

<span data-ttu-id="2d0e8-128">Подробнее [о том,](configure-local-policy-overrides-microsoft-defender-antivirus.md) как запретить пользователям изменять параметры политики на локальном уровне, см. в руб. Предотвращение изменения защиты пользователей на пк.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="2d0e8-129">Запретить пользователям прио паузу в проверке</span><span class="sxs-lookup"><span data-stu-id="2d0e8-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="2d0e8-130">Вы можете запретить пользователям прерывать проверки, которые могут быть полезны для обеспечения того, чтобы запланированные или по требованию проверки не прерывались пользователями.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="2d0e8-131">Этот параметр не поддерживается в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="2d0e8-132">Использование групповой политики, чтобы запретить пользователям прио паузу в проверке</span><span class="sxs-lookup"><span data-stu-id="2d0e8-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="2d0e8-133">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2d0e8-134">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="2d0e8-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="2d0e8-135">Щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="2d0e8-136">Расширь дерево до **компонентов**  >  **Антивирусной проверки Microsoft Defender**  >  **Microsoft** Defender.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="2d0e8-137">Дважды щелкните **кнопку Разрешить пользователям приостанавлить** параметр сканирования и установить параметр **Отключен.**</span><span class="sxs-lookup"><span data-stu-id="2d0e8-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="2d0e8-138">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2d0e8-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="2d0e8-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2d0e8-139">Related articles</span></span>

- [<span data-ttu-id="2d0e8-140">Настройка уведомлений, которые отображаются в конечных точках</span><span class="sxs-lookup"><span data-stu-id="2d0e8-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="2d0e8-141">Настройка взаимодействия между конечными пользователями с антивирусом Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2d0e8-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="2d0e8-142">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="2d0e8-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)