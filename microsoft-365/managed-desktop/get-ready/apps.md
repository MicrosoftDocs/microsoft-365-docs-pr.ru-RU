---
title: Приложения на компьютерах, управляемых Майкрософт
description: Объясняет, как обрабатываются приложения, включая их упаковку, развертывание и поддержку.
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 37f533f34753d66d975cb557239b2b168ac78f8e
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430772"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="16bec-104">Приложения на компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="16bec-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="16bec-105">Приложения обычно</span><span class="sxs-lookup"><span data-stu-id="16bec-105">Apps generally</span></span>

<span data-ttu-id="16bec-106">Корпорация Майкрософт включает некоторые ключевые приложения вместе с лицензией Microsoft 365 E3 E5, необходимой для участия в компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="16bec-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="16bec-107">Однако, несмотря на то, что мы предоставляем эти приложения, у вас по-прежнему есть определенные обязанности и действия, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="16bec-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="16bec-108">Вы также можете развертывать дополнительные приложения, не в microsoft, для самообслуживки через Корпоративный портал или необходимую фоновую установку, используя Microsoft Intune конвейера развертывания.</span><span class="sxs-lookup"><span data-stu-id="16bec-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="16bec-109">Приложения, предоставляемые Корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="16bec-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="16bec-110">В компьютеры, управляемые Майкрософт лицензии включены 64-битные версии приложений в Приложения Microsoft 365 для предприятий Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams и OneNote.) По умолчанию не включаются Microsoft Project и Visio, но  их можно запросить.</span><span class="sxs-lookup"><span data-stu-id="16bec-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="16bec-111">Дополнительные сведения об этих приложениях см. в [Microsoft Project или Microsoft Visio на компьютеры, управляемые Майкрософт устройствах.](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="16bec-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="16bec-112">Что корпорация Майкрософт делает для поддержки приложений, которые мы предоставляем</span><span class="sxs-lookup"><span data-stu-id="16bec-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="16bec-113">Корпорация Майкрософт предоставит полную службу для развертывания, обновления и поддержки включенных Приложения Microsoft 365 для предприятий приложений.</span><span class="sxs-lookup"><span data-stu-id="16bec-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="16bec-114">По умолчанию не включаются версии Microsoft Project и Visio,  но компьютеры, управляемые Майкрософт предоставляют группы развертывания, позволяющие ИТ-администратору управлять лицензиями и развертывать эти приложения надлежащим образом для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="16bec-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="16bec-115">Корпорация Майкрософт будет поддерживать пользователей этих приложений через компьютеры, управляемые Майкрософт каналов поддержки.</span><span class="sxs-lookup"><span data-stu-id="16bec-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="16bec-116">Что необходимо сделать для поддержки приложений, которые мы предоставляем</span><span class="sxs-lookup"><span data-stu-id="16bec-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="16bec-117">Есть еще некоторые вещи, которые необходимо сделать с этими приложениями:</span><span class="sxs-lookup"><span data-stu-id="16bec-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="16bec-118">**Назначение лицензий** . Вы несете ответственность за получение и назначение соответствующих лицензий пользователям для Приложения Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="16bec-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="16bec-119">**Добавление пользователей в** группы безопасности . Если вы используете Microsoft Project или Visio, ИТ-администратор должен добавить этих пользователей в соответствующие группы развертывания.</span><span class="sxs-lookup"><span data-stu-id="16bec-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="16bec-120">ИТ-администраторы также несут ответственность за возврат лицензий у этих пользователей, если они покидают компанию.</span><span class="sxs-lookup"><span data-stu-id="16bec-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="16bec-121">**Развертывание Microsoft 365** надстройки . Если вам нужны какие-либо надстройки для любого из Приложения Microsoft 365 для предприятий приложений, развертывайте их централизованно, как и любое другое приложение Windows 32.</span><span class="sxs-lookup"><span data-stu-id="16bec-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="16bec-122">Приложения, которые вы предоставляете</span><span class="sxs-lookup"><span data-stu-id="16bec-122">Apps you provide</span></span>

<span data-ttu-id="16bec-123">Возможно, у вас есть другие приложения, необходимые для бизнес-операций.</span><span class="sxs-lookup"><span data-stu-id="16bec-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="16bec-124">Эти приложения можно развернуть только для компьютеры, управляемые Майкрософт устройств с помощью Microsoft Intune конвейера развертывания.</span><span class="sxs-lookup"><span data-stu-id="16bec-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="16bec-125">Дополнительные сведения о развертывании приложений следуют шагам в [Развертывании приложений для компьютеры, управляемые Майкрософт устройств.](../get-started/deploy-apps.md)</span><span class="sxs-lookup"><span data-stu-id="16bec-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="16bec-126">Подготовка собственных приложений для включения в компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="16bec-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="16bec-127">Просмотрите приложения, проверив:</span><span class="sxs-lookup"><span data-stu-id="16bec-127">Review your apps, checking:</span></span>

- <span data-ttu-id="16bec-128">Ни одно из приложений не запрещено или не имеет ограниченного поведения, как описано в компьютеры, управляемые Майкрософт [приложения.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="16bec-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="16bec-129">Приложения должны быть готовы к управлению Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="16bec-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="16bec-130">Дополнительные разделы см. в Windows 10 [развертывания](/intune/apps-windows-10-app-deploy) приложений с Microsoft Intune и добавление приложений [в Microsoft Intune.](/intune/apps-add)</span><span class="sxs-lookup"><span data-stu-id="16bec-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="16bec-131">Другие требования к предварительной упаковке, такие как предоставление ключей лицензии, согласование с условиями лицензии и предварительное подключение к серверу.</span><span class="sxs-lookup"><span data-stu-id="16bec-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="16bec-132">Действия, которые необходимо сделать, чтобы быть готовыми</span><span class="sxs-lookup"><span data-stu-id="16bec-132">Steps to get ready</span></span>

1. <span data-ttu-id="16bec-133">Просмотрите [Необходимые условия для компьютеры, управляемые Майкрософт](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="16bec-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="16bec-134">Используйте [средства оценки готовности.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="16bec-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="16bec-135">Предварительные требования для гостевых учетных записей</span><span class="sxs-lookup"><span data-stu-id="16bec-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="16bec-136">Конфигурация сети для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="16bec-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="16bec-137">Подготовка сертификатов и сетевых профилей для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="16bec-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="16bec-138">Подготовка доступа к локальным ресурсам для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="16bec-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="16bec-139">[Приложения в компьютеры, управляемые Майкрософт](apps.md) (Эта статья)</span><span class="sxs-lookup"><span data-stu-id="16bec-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="16bec-140">Подготовка подключенных дисков для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="16bec-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="16bec-141">Подготовка ресурсов печати для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="16bec-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
