---
title: Управление доступом пользователей к документам Office с мобильных устройств
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Узнайте о политиках защиты, которые позволяют управлять доступом пользователей к приложениям и Office с мобильных устройств.
ms.openlocfilehash: 7602b712f2dfc3ba369fd76979baaaa8d5da5c5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925286"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="b0de9-103">Управление доступом пользователей к документам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="b0de9-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="b0de9-104">Эта статья применима к Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="b0de9-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="b0de9-105">Параметры политики, которые определяют, каким образом пользователи получают доступ к файлам Office с мобильных устройств, **выключены** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b0de9-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="b0de9-106">Рекомендуется принимать значения по умолчанию во время установки для создания политик приложений для Android, iOS и Windows 10, которые применяются ко всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="b0de9-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="b0de9-107">По завершении настройки вы сможете создать дополнительные политики.</span><span class="sxs-lookup"><span data-stu-id="b0de9-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="b0de9-108">Параметры, управляющие доступом пользователей к файлам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="b0de9-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="b0de9-109">Управлять доступом пользователей к рабочим файлам Office можно с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="b0de9-109">The following settings are available to manage how users access Office work files:</span></span>

|<span data-ttu-id="b0de9-110">Setting</span><span class="sxs-lookup"><span data-stu-id="b0de9-110">Setting</span></span>  <br/> |<span data-ttu-id="b0de9-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b0de9-111">Description</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="b0de9-112">Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="b0de9-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="b0de9-113">Если этот параметр **работает,** пользователи должны предоставить другую форму проверки подлинности, помимо имени пользователя и пароля, прежде чем они смогут использовать Office приложения на своем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="b0de9-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="b0de9-114">Сбрасывать ПИН-код после указанного числа неудачных попыток входа</span><span class="sxs-lookup"><span data-stu-id="b0de9-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="b0de9-115">Чтобы запретить несанкционированным пользователям случайным образом подбирать ПИН-код, он будет сброшен после указанного вами числа неудачных попыток ввода.</span><span class="sxs-lookup"><span data-stu-id="b0de9-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="b0de9-116">Требовать от пользователей повторно выполнять вход, если приложения Office были неактивны в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="b0de9-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="b0de9-117">Этот параметр определяет, как долго пользователь может простаивать до того, как им будет предложено войти снова.</span><span class="sxs-lookup"><span data-stu-id="b0de9-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="b0de9-118">Запретить доступ к рабочим файлам на устройствах со снятой защитой или с включенным привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="b0de9-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="b0de9-119">На устройствах технически осведомленных пользователей может быть снята защита или включен привилегированный доступ.</span><span class="sxs-lookup"><span data-stu-id="b0de9-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="b0de9-120">Это означает, что пользователь может изменять операционную систему, что может сделать устройство более восприимчивым к вредоносным программам.</span><span class="sxs-lookup"><span data-stu-id="b0de9-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="b0de9-121">Когда этот параметр **включен**, такие устройства блокируются.</span><span class="sxs-lookup"><span data-stu-id="b0de9-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="b0de9-122">Не позволяйте пользователям копировать контент из Office в личные приложения</span><span class="sxs-lookup"><span data-stu-id="b0de9-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="b0de9-123">Когда параметр в **работе,** пользователь не может копировать сведения в файле работы в личный файл.</span><span class="sxs-lookup"><span data-stu-id="b0de9-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="b0de9-124">Если параметр **отключен,** пользователь может скопировать сведения из файла работы в личное приложение или личную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="b0de9-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

