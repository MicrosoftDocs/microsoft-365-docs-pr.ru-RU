---
title: Управление политиками устройств Windows 10 Pro с помощью Microsoft 365 Business Premium
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
description: Узнайте, как управлять политиками устройств Windows 10 Pro с помощью Microsoft 365 Business Premium.
ms.openlocfilehash: 0f7cfff227e1ab4ea992414b513e341adbd9ef22
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578691"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="d2766-103">Управление политиками устройств Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="d2766-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="d2766-104">Вы можете использовать Microsoft 365 Бизнес, чтобы убедиться, что Защитник Windows антивирус активируется на устройствах Windows 10, а обновления Microsoft автоматически загружаются на устройства пользователей.</span><span class="sxs-lookup"><span data-stu-id="d2766-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="d2766-105">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="d2766-105">Try it!</span></span>

1. <span data-ttu-id="d2766-106">Войдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2766-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="d2766-107">В **статье Политики** выберите добавить политику.</span><span class="sxs-lookup"><span data-stu-id="d2766-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="d2766-108">В области **Добавить политику** введите имя под именем **Политика,** а затем выберите **конфигурацию устройств Windows 10** под **типом Политики.**</span><span class="sxs-lookup"><span data-stu-id="d2766-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="d2766-109">Выберите **устройства Secure Windows 10,** чтобы увидеть параметры.</span><span class="sxs-lookup"><span data-stu-id="d2766-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="d2766-110">Убедитесь, что помогите защитить компьютеры от вирусов и других угроз с помощью **Защитник Windows** антивируса и автоматически включите устройства **Windows 10** в соответствии с обновлениями.</span><span class="sxs-lookup"><span data-stu-id="d2766-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="d2766-111">В **статье Кто получит эти параметры?,** все пользователи выбираются по умолчанию, но вы можете выбрать **Изменение,** чтобы выбрать все созданные группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="d2766-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="d2766-112">Чтобы завершить создание политики, выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d2766-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="d2766-113">На странице **Добавить политику** выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d2766-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="d2766-114">На домашней странице центра администрирования подтвердите,  что новая политика была добавлена путем выбора политик и просмотра политики на странице **Политики.**</span><span class="sxs-lookup"><span data-stu-id="d2766-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="d2766-115">Чтобы убедиться, что политика вступила в силу, на устройстве windows 10 пользователя перейдите в Windows Update, выберите дополнительные параметры и убедитесь, что параметры серые. </span><span class="sxs-lookup"><span data-stu-id="d2766-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="d2766-116">Затем нажмите кнопку **Выберите,** как доставляются обновления, и подтвердите, что параметры серые и появится следующее сообщение: Некоторые параметры скрыты или **управляются вашей организацией.**</span><span class="sxs-lookup"><span data-stu-id="d2766-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

