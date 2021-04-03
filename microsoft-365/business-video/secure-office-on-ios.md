---
title: Защита приложений Office на устройстве с iOS
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как обеспечить безопасность приложений Office на iOS с помощью Microsoft 365 Business Premium.
ms.openlocfilehash: 5a5f52f87fe63fdec6df9611a5ea44a2ecf4466b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580466"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="a8add-103">Защита приложений Office на устройстве с iOS</span><span class="sxs-lookup"><span data-stu-id="a8add-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="a8add-104">Вы можете настроить политику доступа пользователей, которая требует от мобильных пользователей ввести ПИН-код или отпечатки пальцев для входа, а также шифровать файлы работы, хранимые на их устройствах.</span><span class="sxs-lookup"><span data-stu-id="a8add-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="a8add-105">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="a8add-105">Try it!</span></span>

1. <span data-ttu-id="a8add-106">Войдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8add-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="a8add-107">В **соответствии с политиками** выберите **добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="a8add-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="a8add-108">В области **Добавить политику** введите имя под именем **Политика** и выберите тип политики, который необходимо в **типе Политики.**</span><span class="sxs-lookup"><span data-stu-id="a8add-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="a8add-109">**Включи управление доступом** пользователей к файлам Office на мобильных устройствах, а затем убедитесь, что включены следующие три параметра:</span><span class="sxs-lookup"><span data-stu-id="a8add-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="a8add-110">**Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office**</span><span class="sxs-lookup"><span data-stu-id="a8add-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="a8add-111">**Защита файлов работы при потерянии или краже устройств**</span><span class="sxs-lookup"><span data-stu-id="a8add-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="a8add-112">**Шифрование рабочих файлов**</span><span class="sxs-lookup"><span data-stu-id="a8add-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="a8add-113">В **этих приложениях файлы будут защищены,** выберите приложения Office, которые необходимо защитить на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="a8add-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="a8add-114">В **статье Кто получит эти параметры?,** все пользователи выбираются по умолчанию, но вы можете выбрать **Изменение,** чтобы выбрать все созданные группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="a8add-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="a8add-115">Чтобы завершить создание политики, выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a8add-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="a8add-116">На странице **Добавить политику** выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a8add-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="a8add-117">На домашней странице центра администрирования подтвердите,  что новая политика была добавлена путем выбора политик и просмотра политики на странице **Политики.**</span><span class="sxs-lookup"><span data-stu-id="a8add-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>