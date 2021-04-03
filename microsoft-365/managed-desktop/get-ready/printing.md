---
title: Подготовка ресурсов печати для компьютеров, управляемых Майкрософт
description: Важные шаги, чтобы убедиться, что печать работает гладко
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 971644aafabda733bf745fae278bdfeeed3282e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574551"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="a0063-104">Подготовка ресурсов печати для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a0063-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="a0063-105">По мере готовности к регистрации в Microsoft Managed Desktop необходимо оценить требования к печати и определить правильный подход к среде.</span><span class="sxs-lookup"><span data-stu-id="a0063-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="a0063-106">У вас есть три варианта:</span><span class="sxs-lookup"><span data-stu-id="a0063-106">You have three options:</span></span>
 
- <span data-ttu-id="a0063-107">Разместим решение Microsoft Universal Print, чтобы устройствам Microsoft Managed Desktop было проще открывать принтеры.</span><span class="sxs-lookup"><span data-stu-id="a0063-107">Deploy the Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="a0063-108">Дополнительные сведения см. в [издании What is Universal Print.](/universal-print/fundamentals/universal-print-whatis)</span><span class="sxs-lookup"><span data-stu-id="a0063-108">For more information, see [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).</span></span>
- <span data-ttu-id="a0063-109">Развертывание принтеров непосредственно с помощью настраиваемой скрипта PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0063-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="a0063-110">Выполните действия в разделе [Настройка локальных принтеров.](#set-up-local-printers)</span><span class="sxs-lookup"><span data-stu-id="a0063-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section.</span></span>
- <span data-ttu-id="a0063-111">Используйте решение облачной печати, не в microsoft, которое совместимо с устройствами Windows 10, которые присоединяются к домену Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a0063-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="a0063-112">Решение должно соответствовать требованиям программного обеспечения для Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="a0063-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="a0063-113">Дополнительные сведения см. в [приложении Microsoft Managed Desktop.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="a0063-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="a0063-114">Во всех случаях, если драйверы принтера недоступны в Microsoft Update или Microsoft Store, их необходимо получить самостоятельно и упакововать для развертывания на устройствах Microsoft Managed Desktop с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="a0063-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="a0063-115">Дополнительные см. в [приложении Intune Standalone — управление приложениями Win32](/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="a0063-115">For more, see [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="a0063-116">Настройка локальных принтеров</span><span class="sxs-lookup"><span data-stu-id="a0063-116">Set up local printers</span></span>

<span data-ttu-id="a0063-117">Если вы решили развернуть принтеры с помощью настраиваемой скрипта PowerShell и подготовили ресурсы печати, выполните следующие действия, чтобы развернуть общие принтеры:</span><span class="sxs-lookup"><span data-stu-id="a0063-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="a0063-118">Перейдите на портал Управляемый рабочий стол Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0063-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="a0063-119">Отправка запроса с меткой *Развертывание* принтера **в** разделе > поддержки на портале администрирования, в которых печатались указанные сведения:</span><span class="sxs-lookup"><span data-stu-id="a0063-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="a0063-120">Все пути UNC к общим расположениям принтеров, которые необходимо развернуть для устройств Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a0063-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="a0063-121">Группы пользователей, которые требуют доступа к этим общим принтерам</span><span class="sxs-lookup"><span data-stu-id="a0063-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="a0063-122">С помощью портала администрирования мы сообщаем вам о том, когда запрос будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="a0063-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="a0063-123">Изначально мы будем развертывать конфигурацию только на устройствах в группе развертывания Test.</span><span class="sxs-lookup"><span data-stu-id="a0063-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="a0063-124">Необходимо проверить и подтвердить, работает ли конфигурация так, как вы ожидаете.</span><span class="sxs-lookup"><span data-stu-id="a0063-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="a0063-125">Ответьте с помощью вкладки **Обсуждение** в запросе поддержки, чтобы дать нам знать, когда вы завершили тестирование.</span><span class="sxs-lookup"><span data-stu-id="a0063-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="a0063-126">Затем мы развернем конфигурацию для других групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="a0063-126">We'll then deploy the configuration to the other deployment groups.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="a0063-127">Действия, которые необходимо сделать, чтобы быть готовыми</span><span class="sxs-lookup"><span data-stu-id="a0063-127">Steps to get ready</span></span>

1. <span data-ttu-id="a0063-128">Просмотрите [необходимые условия для управляемого рабочего стола Майкрософт.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="a0063-128">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="a0063-129">Используйте [средства оценки готовности.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="a0063-129">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="a0063-130">Предварительные требования для гостевых учетных записей</span><span class="sxs-lookup"><span data-stu-id="a0063-130">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="a0063-131">Конфигурация сети для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a0063-131">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="a0063-132">Подготовка сертификатов и сетевых профилей для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a0063-132">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="a0063-133">Подготовка доступа к локальным ресурсам для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a0063-133">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="a0063-134">Приложения на компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a0063-134">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="a0063-135">Подготовка подключенных дисков для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a0063-135">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. <span data-ttu-id="a0063-136">[Подготовка ресурсов печати для microsoft Managed Desktop](printing.md) (Эта статья)</span><span class="sxs-lookup"><span data-stu-id="a0063-136">[Prepare printing resources for Microsoft Managed Desktop](printing.md) (This article)</span></span>
