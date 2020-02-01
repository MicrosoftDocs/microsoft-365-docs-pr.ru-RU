---
title: Управление доступом пользователей к документам Office с мобильных устройств
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Узнайте о политиках защиты, которые помогут защитить доступ к приложениям Office с мобильных устройств.
ms.openlocfilehash: 39d28a3a78fb06d0020c484b1782b544f6a8c656
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593828"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="dd286-103">Управление доступом пользователей к документам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="dd286-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="dd286-104">Параметры политики, которые определяют, каким образом пользователи получают доступ к файлам Office с мобильных устройств, **выключены** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dd286-104">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="dd286-105">Рекомендуется принять значения по умолчанию во время установки, чтобы создать политики приложений для Android, iOS и Windows 10, которые применяются ко всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="dd286-105">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="dd286-106">По завершении настройки вы сможете создать дополнительные политики.</span><span class="sxs-lookup"><span data-stu-id="dd286-106">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="dd286-107">Параметры, управляющие доступом пользователей к файлам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="dd286-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="dd286-108">Управлять доступом пользователей к рабочим файлам Office можно с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="dd286-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dd286-109">Setting</span><span class="sxs-lookup"><span data-stu-id="dd286-109">Setting</span></span>  <br/> |<span data-ttu-id="dd286-110">Описание</span><span class="sxs-lookup"><span data-stu-id="dd286-110">Description</span></span>  <br/> |
|<span data-ttu-id="dd286-111">Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="dd286-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="dd286-112">Если этот параметр включен **, пользователям**необходимо предоставить еще одну форму проверки подлинности, а также имя пользователя и пароль, прежде чем они смогут использовать приложения Office на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="dd286-112">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="dd286-113">Сбрасывать ПИН-код после указанного числа неудачных попыток входа</span><span class="sxs-lookup"><span data-stu-id="dd286-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="dd286-114">Чтобы запретить несанкционированным пользователям случайным образом подбирать ПИН-код, он будет сброшен после указанного вами числа неудачных попыток ввода.</span><span class="sxs-lookup"><span data-stu-id="dd286-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="dd286-115">Требовать от пользователей повторно выполнять вход, если приложения Office были неактивны в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="dd286-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="dd286-116">Этот параметр определяет, как долго пользователь может выйти из системы, прежде чем ему будет предложено войти снова.</span><span class="sxs-lookup"><span data-stu-id="dd286-116">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="dd286-117">Запретить доступ к рабочим файлам на устройствах со снятой защитой или с включенным привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="dd286-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="dd286-118">На устройствах технически осведомленных пользователей может быть снята защита или включен привилегированный доступ.</span><span class="sxs-lookup"><span data-stu-id="dd286-118">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="dd286-119">Это означает, что пользователь может изменять операционную систему, что может сделать устройство более уязвимым для вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="dd286-119">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="dd286-120">Когда этот параметр **включен**, такие устройства блокируются.</span><span class="sxs-lookup"><span data-stu-id="dd286-120">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="dd286-121">Не разрешать пользователям копировать содержимое из приложений Office в личные приложения</span><span class="sxs-lookup"><span data-stu-id="dd286-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="dd286-122">Если этот параметр включен **, пользователь не может**копировать данные из рабочего файла в личный файл.</span><span class="sxs-lookup"><span data-stu-id="dd286-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="dd286-123">Если этот параметр **отключен**, пользователь может копировать данные из рабочего файла в личное приложение или личную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="dd286-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

