---
title: Управление доступом пользователей к документам Office с мобильных устройств
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Сведения о политиках защиты, которые могут помочь безопасный доступ к приложениям Office с помощью мобильных устройств.
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870754"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="08e30-103">Управление доступом пользователей к документам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="08e30-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="08e30-p101">Параметры политики, которые определяют, каким образом пользователи получают доступ к файлам Office с мобильных устройств, **выключены** по умолчанию. Советуем во время настройки принять значения по умолчанию, чтобы создать политики приложений для устройств с Windows 10, iOS и Android, которые будут применяться ко всем пользователям. По завершении настройки вы сможете создать дополнительные политики.</span><span class="sxs-lookup"><span data-stu-id="08e30-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="08e30-107">Параметры, управляющие доступом пользователей к файлам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="08e30-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="08e30-108">Управлять доступом пользователей к рабочим файлам Office можно с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="08e30-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="08e30-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="08e30-109">Setting</span></span>  <br/> |<span data-ttu-id="08e30-110">Описание</span><span class="sxs-lookup"><span data-stu-id="08e30-110">Description</span></span>  <br/> |
|<span data-ttu-id="08e30-111">Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="08e30-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="08e30-112">Если этот параметр **включен**, пользователям необходимо настроить дополнительный способ проверки подлинности, помимо ввода имени и пароля, чтобы открыть приложения Office на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="08e30-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="08e30-113">Сбрасывать ПИН-код после указанного числа неудачных попыток входа</span><span class="sxs-lookup"><span data-stu-id="08e30-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="08e30-114">ПИН-код будет сбрасываться после указанного вами числа неудачных попыток ввода, чтобы несанкционированные пользователи не могли подобрать его случайным образом.</span><span class="sxs-lookup"><span data-stu-id="08e30-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="08e30-115">Требовать от пользователей повторно выполнять вход, если приложения Office были неактивны в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="08e30-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="08e30-116">Этот параметр определяет, сколько времени пользователь может оставаться неактивным, прежде чем ему будет предложено выполнить вход повторно.</span><span class="sxs-lookup"><span data-stu-id="08e30-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="08e30-117">Запретить доступ к рабочим файлам на устройствах со снятой защитой или с включенным привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="08e30-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="08e30-p102">На устройствах технически осведомленных пользователей может быть снята защита или включен привилегированный доступ. Это означает, что пользователь может изменять операционную систему, из-за чего устройство может стать более уязвимым к вредоносным программам. Когда этот параметр **включен**, такие устройства блокируются.  </span><span class="sxs-lookup"><span data-stu-id="08e30-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="08e30-121">Разрешить пользователям копировать содержимое из приложений Office в личные приложения</span><span class="sxs-lookup"><span data-stu-id="08e30-121">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="08e30-p103">Такая возможность предоставляется по умолчанию, но когда данный параметр **включен**, пользователь может копировать сведения из рабочих файлов в личные. Если параметр **отключен**, пользователь не сможет копировать сведения из рабочих файлов в личные приложения или учетные записи.  </span><span class="sxs-lookup"><span data-stu-id="08e30-p103">We allow this by default, but when the setting is **On**, the user can copy information in a work file to a personal file. If the setting is **Off**, the user can't copy information from a work file to a personal app or personal account.  </span></span><br/> |
   

