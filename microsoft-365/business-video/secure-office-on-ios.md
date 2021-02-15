---
title: Защита приложений Office на устройстве с iOS
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как защитить приложения Office в iOS с помощью Microsoft 365 бизнес премиум.
ms.openlocfilehash: fd7fdd32500f9a2362ac29059abe9424d045c206
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928034"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="f3a4e-103">Защита приложений Office на устройстве с iOS</span><span class="sxs-lookup"><span data-stu-id="f3a4e-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="f3a4e-104">Можно настроить политику доступа пользователей, которая требует от мобильных пользователей ввода ПИН-кода или отпечатка пальца для входа, а также шифровать файлы, хранимые на их устройствах.</span><span class="sxs-lookup"><span data-stu-id="f3a4e-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="f3a4e-105">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="f3a4e-105">Try it!</span></span>

1. <span data-ttu-id="f3a4e-106">Войдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3a4e-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="f3a4e-107">В **области "Политики"** выберите **"Добавить политику".**</span><span class="sxs-lookup"><span data-stu-id="f3a4e-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="f3a4e-108">В области **"Добавление** политики" введите имя под именем политики и выберите тип политики, который необходимо в  **типе политики.**</span><span class="sxs-lookup"><span data-stu-id="f3a4e-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="f3a4e-109">**Включив управление доступом пользователей к** файлам Office на мобильных устройствах, убедитесь, что включены следующие три параметра:</span><span class="sxs-lookup"><span data-stu-id="f3a4e-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="f3a4e-110">**Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office**</span><span class="sxs-lookup"><span data-stu-id="f3a4e-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="f3a4e-111">**Защита файлов в случае потери или кражи устройств**</span><span class="sxs-lookup"><span data-stu-id="f3a4e-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="f3a4e-112">**Шифрование рабочих файлов**</span><span class="sxs-lookup"><span data-stu-id="f3a4e-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="f3a4e-113">Under **Files in these apps will be protected,** select the Office apps you want to protect on mobile devices.</span><span class="sxs-lookup"><span data-stu-id="f3a4e-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="f3a4e-114">В **области "Кто получит эти параметры?",** по умолчанию выбраны все пользователи, но вы можете выбрать "Изменить", чтобы выбрать все созданные группы безопасности. </span><span class="sxs-lookup"><span data-stu-id="f3a4e-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="f3a4e-115">Чтобы завершить создание политики, выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="f3a4e-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="f3a4e-116">На странице **"Добавление политики"** выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="f3a4e-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="f3a4e-117">На домашней странице Центра администрирования подтвердите,  что новая политика добавлена, выбрав "Политики" и просмотрев политику на **странице "Политики".**</span><span class="sxs-lookup"><span data-stu-id="f3a4e-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>