---
title: Настройка взаимодействия пользователей с microsoft Defender AV
description: Настройте, как конечные пользователи взаимодействуют с Microsoft Defender AV, какие уведомления они видят и могут ли они переопределять параметры.
keywords: конечная точка, пользователь, взаимодействие, уведомления, режим блокировки пользовательского интерфейса, режим безголовые, интерфейс скрыть
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: df9f87e725575bad2f36cf7b016d257e766e523b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765231"
---
# <a name="configure-end-user-interaction-with-microsoft-defender-antivirus"></a><span data-ttu-id="8d825-104">Настройка взаимодействия между конечными пользователями с антивирусом Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8d825-104">Configure end-user interaction with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8d825-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8d825-105">**Applies to:**</span></span>

- [<span data-ttu-id="8d825-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8d825-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8d825-107">Можно настроить взаимодействие пользователей конечных точек в сети с антивирусом Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="8d825-107">You can configure how users of the endpoints on your network can interact with Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="8d825-108">Это включает в себя, видят ли они антивирусный интерфейс Microsoft Defender, какие уведомления они видят, и могут ли они локально переопределять глобально развернутые параметры групповой политики.</span><span class="sxs-lookup"><span data-stu-id="8d825-108">This includes whether they see the Microsoft Defender Antivirus interface, what notifications they see, and if they can locally override globally-deployed Group Policy settings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8d825-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8d825-109">In this section</span></span>

<span data-ttu-id="8d825-110">Статья</span><span class="sxs-lookup"><span data-stu-id="8d825-110">Topic</span></span> | <span data-ttu-id="8d825-111">Описание</span><span class="sxs-lookup"><span data-stu-id="8d825-111">Description</span></span> 
---|---
[<span data-ttu-id="8d825-112">Настройка уведомлений, которые отображаются в конечных точках</span><span class="sxs-lookup"><span data-stu-id="8d825-112">Configure notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md) | <span data-ttu-id="8d825-113">Настройка и настройка дополнительных уведомлений, настраиваемых текстов для уведомлений и уведомлений о перезагрузке для устранения</span><span class="sxs-lookup"><span data-stu-id="8d825-113">Configure and customize additional notifications, customized text for notifications, and notifications about reboots for remediation</span></span>
[<span data-ttu-id="8d825-114">Запретить пользователям видеть и взаимодействовать с пользовательским интерфейсом антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8d825-114">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="8d825-115">Сокрытие пользовательского интерфейса от пользователей</span><span class="sxs-lookup"><span data-stu-id="8d825-115">Hide the user interface from users</span></span>
[<span data-ttu-id="8d825-116">Предотвращение локального изменения параметров политики пользователями</span><span class="sxs-lookup"><span data-stu-id="8d825-116">Prevent users from locally modifying policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) | <span data-ttu-id="8d825-117">Запретить (или разрешить) пользователям переопределять параметры политики на отдельных конечных точках</span><span class="sxs-lookup"><span data-stu-id="8d825-117">Prevent (or allow) users from overriding policy settings on their individual endpoints</span></span>