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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Узнайте о политиках защиты, которые позволяют управлять доступом пользователей к приложениям Office и файлам с мобильных устройств.
ms.openlocfilehash: b2b828cf2e201360f12b8fadcb395e72958230f6
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471074"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="c3ee2-103">Управление доступом пользователей к документам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="c3ee2-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="c3ee2-104">Эта статья относится к Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c3ee2-105">Параметры политики, которые определяют, каким образом пользователи получают доступ к файлам Office с мобильных устройств, **выключены** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="c3ee2-106">Мы рекомендуем принять значения по умолчанию во время настройки, чтобы создать политики приложений для Android, iOS и Windows 10, которые применяются ко всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="c3ee2-107">По завершении настройки вы сможете создать дополнительные политики.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="c3ee2-108">Параметры, управляющие доступом пользователей к файлам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="c3ee2-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="c3ee2-109">Управлять доступом пользователей к рабочим файлам Office можно с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c3ee2-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c3ee2-110">Setting</span><span class="sxs-lookup"><span data-stu-id="c3ee2-110">Setting</span></span>  <br/> |<span data-ttu-id="c3ee2-111">Описание</span><span class="sxs-lookup"><span data-stu-id="c3ee2-111">Description</span></span>  <br/> |
|<span data-ttu-id="c3ee2-112">Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="c3ee2-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="c3ee2-113">Если этот параметр **в** сети, пользователи должны предоставить еще одну форму проверки подлинности в дополнение к имени пользователя и паролям, прежде чем они смогут использовать приложения Office на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="c3ee2-114">Сбрасывать ПИН-код после указанного числа неудачных попыток входа</span><span class="sxs-lookup"><span data-stu-id="c3ee2-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="c3ee2-115">Чтобы запретить несанкционированным пользователям случайным образом подбирать ПИН-код, он будет сброшен после указанного вами числа неудачных попыток ввода.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="c3ee2-116">Требовать от пользователей повторно выполнять вход, если приложения Office были неактивны в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="c3ee2-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="c3ee2-117">Этот параметр определяет, сколько времени пользователь может бездействовать, прежде чем им будет предложено повторно войти.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="c3ee2-118">Запретить доступ к рабочим файлам на устройствах со снятой защитой или с включенным привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="c3ee2-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="c3ee2-119">На устройствах технически осведомленных пользователей может быть снята защита или включен привилегированный доступ.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="c3ee2-120">Это означает, что пользователь может изменить операционную систему, что может сделать устройство более уязвимым к вредоносным программам.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="c3ee2-121">Когда этот параметр **включен**, такие устройства блокируются.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="c3ee2-122">Не разрешайте пользователям копировать содержимое из приложений Office в личные приложения</span><span class="sxs-lookup"><span data-stu-id="c3ee2-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="c3ee2-123">Если этот параметр **в сети,** пользователь не может копировать сведения в рабочий файл в личный файл.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="c3ee2-124">Если параметр **отключен,** пользователь может скопировать данные из файла в личное приложение или личную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="c3ee2-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

