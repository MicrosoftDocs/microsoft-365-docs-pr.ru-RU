---
title: Поддержка нескольких регионов в OneDrive и SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Расширьте свою географию присутствия Microsoft 365 с поддержкой нескольких регионов в OneDrive Online.
ms.openlocfilehash: 8f42b071abef0602304f1a468190c33700fe3e82
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995913"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="4e97d-103">Поддержка нескольких регионов в OneDrive и SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4e97d-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="4e97d-104">Возможности поддержки нескольких регионов в OneDrive и SharePoint Online позволяют управлять общими ресурсами, например сайтами групп SharePoint и почтовыми ящиками групп Microsoft 365, хранимых в стране или регионе.</span><span class="sxs-lookup"><span data-stu-id="4e97d-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a country or region.</span></span>

<span data-ttu-id="4e97d-105">У каждого пользователя, почтового ящика группы и сайта SharePoint есть предпочтительное расположение данных (PDL), обозначающее географическое расположение для хранения соответствующих данных.</span><span class="sxs-lookup"><span data-stu-id="4e97d-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="4e97d-106">Персональные данные пользователей (почтовый ящик Exchange и OneDrive), а также любые созданные им группы Microsoft 365 или сайты SharePoint могут храниться в указанном географическом расположении для соблюдения требований к месту расположения данных.</span><span class="sxs-lookup"><span data-stu-id="4e97d-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="4e97d-107">Можно [указывать разных администраторов для каждого географического расположения](add-a-sharepoint-geo-admin.md).</span><span class="sxs-lookup"><span data-stu-id="4e97d-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="4e97d-108">Для пользователей обеспечивается удобство взаимодействия при использовании служб Microsoft 365, включая приложения Office, OneDrive и поиск.</span><span class="sxs-lookup"><span data-stu-id="4e97d-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="4e97d-109">Подробные сведения см. в статье [Взаимодействие с пользователем в среде с поддержкой нескольких регионов](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="4e97d-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="4e97d-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4e97d-110">OneDrive</span></span>

<span data-ttu-id="4e97d-111">Хранилище OneDrive каждого пользователя может быть подготовлено или [перемещено администратором](move-onedrive-between-geo-locations.md) в периферийное расположение в соответствии с предпочтительным расположением данных (PDL) пользователя.</span><span class="sxs-lookup"><span data-stu-id="4e97d-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="4e97d-112">После этого личные файлы хранятся в этом географическом расположении, но ими можно делиться с пользователями из других географических расположений.</span><span class="sxs-lookup"><span data-stu-id="4e97d-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="4e97d-113">Сайты и группы SharePoint</span><span class="sxs-lookup"><span data-stu-id="4e97d-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="4e97d-114">Функцией поддержки нескольких регионов можно управлять в Центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4e97d-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="4e97d-115">Подробные сведения см. в [соответствующей записи блога](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span><span class="sxs-lookup"><span data-stu-id="4e97d-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="4e97d-116">Когда пользователь создает подключенный к группе сайт SharePoint в среде с поддержкой нескольких регионов, его значение PDL используется для определения географического расположения, в котором создается сайт и почтовый ящик связанной группы.</span><span class="sxs-lookup"><span data-stu-id="4e97d-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="4e97d-117">(Если значение PDL пользователя не задано или присвоено географическое расположение, не настроенное в качестве периферийного расположения, сайт и почтовый ящик создаются в центральном расположении.)</span><span class="sxs-lookup"><span data-stu-id="4e97d-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="4e97d-118">В службах Microsoft 365, кроме Exchange, OneDrive и SharePoint, отсутствует поддержка нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="4e97d-118">Microsoft 365 services other than Exchange, OneDrive, and SharePoint are not Multi-Geo.</span></span> <span data-ttu-id="4e97d-119">Однако группы Microsoft 365, созданные с помощью этих служб, помечаются значением PDL создавшего их пользователя, а почтовый ящик Exchange группы и сайт группы SharePoint Office 365 подготавливаются в соответствующем географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="4e97d-119">However, Microsoft 365 Groups that are created by these services will be stamped with the PDL of the creator and their Exchange Group mailbox and SharePoint O365 Group Site provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="4e97d-120">Управление средой с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="4e97d-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="4e97d-121">Настройка и управление средой с поддержкой нескольких регионов осуществляется через Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4e97d-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![Снимок экрана: страница географических расположений в Центре администрирования SharePoint](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="4e97d-123">(Некоторые действия, например перемещение сайта SharePoint или сайта OneDrive, требуют использования Microsoft PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="4e97d-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="4e97d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4e97d-124">See also</span></span>

[<span data-ttu-id="4e97d-125">Поддержка нескольких регионов в SharePoint и группах Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e97d-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="4e97d-126">Администрирование среды с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="4e97d-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="4e97d-127">Квоты хранилища SharePoint в средах с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="4e97d-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="4e97d-128">Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="4e97d-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
