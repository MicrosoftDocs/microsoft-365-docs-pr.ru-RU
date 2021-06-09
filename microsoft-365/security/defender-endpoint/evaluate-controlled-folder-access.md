---
title: Оценка контролируемого доступа к папкам
description: Узнайте, как управляемый доступ к папкам помогает защитить файлы от изменения вредоносными приложениями.
keywords: Защита от эксплойтов, Windows 10, защитник Windows, вымогателей, защита, оценка, тестирование, демонстрация, попытка
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 15ea4696052a6c987314e3c7b0dd282a49ed4df8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842918"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="5f5e9-104">Оценка контролируемого доступа к папкам</span><span class="sxs-lookup"><span data-stu-id="5f5e9-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f5e9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5f5e9-105">**Applies to:**</span></span>
- [<span data-ttu-id="5f5e9-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5f5e9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5f5e9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f5e9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5f5e9-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5f5e9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5f5e9-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="5f5e9-110">[Управляемый доступ к папкам](controlled-folders.md) — это функция, которая помогает защитить документы и файлы от изменений подозрительными или вредоносными приложениями.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="5f5e9-111">Управляемый доступ к папкам поддерживается на Windows Server 2019 и Windows 10 клиентах.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="5f5e9-112">Это особенно полезно для защиты от [программ-вымогателей,](https://www.microsoft.com/wdsi/threats/ransomware) которые пытаются шифровать файлы и удерживать их в заложниках.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="5f5e9-113">В этой статье вы можете оценить доступ к управляемой папке.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="5f5e9-114">В нем объясняется, как включить режим аудита, чтобы можно было протестировать функцию непосредственно в организации.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="5f5e9-115">Вы также можете посетить веб-сайт демонстрационных сценариев Microsoft Defender for Endpoint в demo.wd.microsoft.com, чтобы подтвердить, что функция работает, и посмотреть, как она работает. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="5f5e9-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="5f5e9-116">Использование режима аудита для измерения воздействия</span><span class="sxs-lookup"><span data-stu-id="5f5e9-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="5f5e9-117">Включить доступ к управляемой папке в режиме  аудита, чтобы увидеть запись о том, что произошло бы, если бы она была полностью включена.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="5f5e9-118">Проверьте, как эта функция будет работать в организации, чтобы убедиться, что она не влияет на ваши бизнес-приложения.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="5f5e9-119">Вы также можете получить представление о том, сколько попыток изменения подозрительных файлов обычно происходит в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="5f5e9-120">Чтобы включить режим аудита, используйте следующий комдлет PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5f5e9-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="5f5e9-121">Если вы хотите полностью проверять, как будет работать управляемый доступ к папкам в организации, вам потребуется использовать средство управления для развертывания этого параметра на устройствах в сети (s).</span><span class="sxs-lookup"><span data-stu-id="5f5e9-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="5f5e9-122">Вы также можете использовать групповую политику, intune, управление мобильными устройствами (MDM) или Microsoft Endpoint Manager для настройки и развертывания параметра, как описано в основной теме доступа к управляемым [папкам](controlled-folders.md).</span><span class="sxs-lookup"><span data-stu-id="5f5e9-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="5f5e9-123">Просмотр событий управляемого доступа к папкам в Windows просмотра событий</span><span class="sxs-lookup"><span data-stu-id="5f5e9-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="5f5e9-124">Следующие события управляемого доступа к папке отображаются в Windows в папке Microsoft/Windows/Защитник Windows/Operational.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="5f5e9-125">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5f5e9-125">Event ID</span></span> | <span data-ttu-id="5f5e9-126">Описание</span><span class="sxs-lookup"><span data-stu-id="5f5e9-126">Description</span></span>
-|-
 <span data-ttu-id="5f5e9-127">5007</span><span class="sxs-lookup"><span data-stu-id="5f5e9-127">5007</span></span> | <span data-ttu-id="5f5e9-128">Событие при смене параметров</span><span class="sxs-lookup"><span data-stu-id="5f5e9-128">Event when settings are changed</span></span>
 <span data-ttu-id="5f5e9-129">1124</span><span class="sxs-lookup"><span data-stu-id="5f5e9-129">1124</span></span> | <span data-ttu-id="5f5e9-130">Событие доступа к контролируемой управляемой папке</span><span class="sxs-lookup"><span data-stu-id="5f5e9-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="5f5e9-131">1123</span><span class="sxs-lookup"><span data-stu-id="5f5e9-131">1123</span></span> | <span data-ttu-id="5f5e9-132">Событие доступа к заблокированной управляемой папке</span><span class="sxs-lookup"><span data-stu-id="5f5e9-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="5f5e9-133">Вы можете настроить подписку [Windows для](/windows/win32/wec/setting-up-a-source-initiated-subscription) централизованного сбора журналов.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-133">You can configure a [Windows Event Forwarding subscription](/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="5f5e9-134">Настройка защищенных папок и приложений</span><span class="sxs-lookup"><span data-stu-id="5f5e9-134">Customize protected folders and apps</span></span>

<span data-ttu-id="5f5e9-135">Во время оценки вы можете добавить в список защищенных папок или разрешить некоторым приложениям изменять файлы.</span><span class="sxs-lookup"><span data-stu-id="5f5e9-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="5f5e9-136">См. в обзоре Protect important [folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span><span class="sxs-lookup"><span data-stu-id="5f5e9-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f5e9-137">См. также</span><span class="sxs-lookup"><span data-stu-id="5f5e9-137">See also</span></span>

* [<span data-ttu-id="5f5e9-138">Защита важных папок с управляемым доступом к папкам</span><span class="sxs-lookup"><span data-stu-id="5f5e9-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="5f5e9-139">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5f5e9-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="5f5e9-140">Использовать режим аудита</span><span class="sxs-lookup"><span data-stu-id="5f5e9-140">Use audit mode</span></span>](audit-windows-defender.md)
