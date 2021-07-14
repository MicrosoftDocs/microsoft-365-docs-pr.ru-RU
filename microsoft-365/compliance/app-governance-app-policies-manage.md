---
title: Управление политиками приложений
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Управление политиками управления приложениями.
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420402"
---
# <a name="manage-app-policies"></a><span data-ttu-id="768c4-103">Управление политиками приложений</span><span class="sxs-lookup"><span data-stu-id="768c4-103">Manage app policies</span></span>

><span data-ttu-id="768c4-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="768c4-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="768c4-105">Чтобы следить за новыми приложениями, которые использует ваша организация, реагировать на новые атаки через приложения и постоянно вносить изменения в задачи обеспечения соответствия приложений требованиям, вам может потребоваться управлять политиками приложений следующими способами.</span><span class="sxs-lookup"><span data-stu-id="768c4-105">To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:</span></span>

- <span data-ttu-id="768c4-106">Создание новых политик, нацеленных на новые приложения</span><span class="sxs-lookup"><span data-stu-id="768c4-106">Create new policies targeted at new apps</span></span>
- <span data-ttu-id="768c4-107">Изменение состояния существующей политики (активная, неактивная, режим аудита)</span><span class="sxs-lookup"><span data-stu-id="768c4-107">Change the status of an existing policy (active, inactive, audit mode)</span></span>
- <span data-ttu-id="768c4-108">Изменение условий существующей политики</span><span class="sxs-lookup"><span data-stu-id="768c4-108">Change the conditions of an existing policy</span></span>
- <span data-ttu-id="768c4-109">Изменение действий существующей политики для автоматического исправления в связи с оповещениями</span><span class="sxs-lookup"><span data-stu-id="768c4-109">Change the actions of an existing policy for auto-remediation of alerts</span></span>

<span data-ttu-id="768c4-110">Вот пример процесса управления существующей политикой:</span><span class="sxs-lookup"><span data-stu-id="768c4-110">Here's an example of a process for managing an existing policy:</span></span>

1. <span data-ttu-id="768c4-111">Изменение политики:</span><span class="sxs-lookup"><span data-stu-id="768c4-111">Edit the policy:</span></span>

  - <span data-ttu-id="768c4-112">изменение параметров политики.</span><span class="sxs-lookup"><span data-stu-id="768c4-112">Change the settings of the policy.</span></span>
  - <span data-ttu-id="768c4-113">При необходимости измените состояние на **Режим аудита** для тестирования.</span><span class="sxs-lookup"><span data-stu-id="768c4-113">If needed, change the status to **Audit mode** for testing.</span></span>

2. <span data-ttu-id="768c4-114">Проверьте ожидаемое поведение, например созданные оповещения.</span><span class="sxs-lookup"><span data-stu-id="768c4-114">Check for expected behavior, such as alerts generated.</span></span>
1. <span data-ttu-id="768c4-115">Если поведение не соответствует ожидаемому, перейдите к шагу 1.</span><span class="sxs-lookup"><span data-stu-id="768c4-115">If the behavior is not expected, go back to step 1.</span></span>
1. <span data-ttu-id="768c4-116">Если поведение соответствует ожидаемому, измените политику и переведите ее в активное состояние (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="768c4-116">If the behavior is expected, edit the policy and change its status to active (if needed).</span></span>

![Рабочий процесс управления политиками приложений](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a><span data-ttu-id="768c4-118">Изменение конфигурации политики приложения</span><span class="sxs-lookup"><span data-stu-id="768c4-118">Editing an app policy configuration</span></span>

<span data-ttu-id="768c4-119">Чтобы изменить конфигурацию существующей политики приложений, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="768c4-119">To change the configuration of an existing app policy:</span></span>

- <span data-ttu-id="768c4-120">Выберите политику в списке политик, а затем нажмите **Изменить** на панели политики приложений.</span><span class="sxs-lookup"><span data-stu-id="768c4-120">Select the policy in the policy list, and then select **Edit** on the app policy pane.</span></span>
- <span data-ttu-id="768c4-121">Щелкните вертикальное многоточие возле политики в списке и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="768c4-121">Select the vertical ellipses for the policy in the list, and then select **Edit**.</span></span>

<span data-ttu-id="768c4-122">Для страницы **Изменение политики** пролистайте страницы и внесите необходимые изменения:</span><span class="sxs-lookup"><span data-stu-id="768c4-122">For the **Edit policy** page, step through the pages and make the appropriate changes:</span></span>

- <span data-ttu-id="768c4-123">**Описание**. Изменение описания для упрощения понимания назначения политики.</span><span class="sxs-lookup"><span data-stu-id="768c4-123">**Description**: Change the description to make it easier to understand the policy's purpose.</span></span>
- <span data-ttu-id="768c4-124">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="768c4-124">**Severity**</span></span>
- <span data-ttu-id="768c4-125">**Параметры политики**. Изменение набора приложений, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="768c4-125">**Policy settings**: Change the set of apps to which the policy applies.</span></span> <span data-ttu-id="768c4-126">Вы также можете использовать существующие условия или изменить их</span><span class="sxs-lookup"><span data-stu-id="768c4-126">You can also choose to use the existing conditions or modify the conditions</span></span>
- <span data-ttu-id="768c4-127">**Действия**. Изменение действия автоматического исправления для оповещений, создаваемых политикой.</span><span class="sxs-lookup"><span data-stu-id="768c4-127">**Actions**: Change the auto-remediation action for alerts generated by the policy.</span></span>
- <span data-ttu-id="768c4-128">**Состояние**. Изменение состояния политики.</span><span class="sxs-lookup"><span data-stu-id="768c4-128">**Status**: Change the policy status.</span></span>

## <a name="deleting-an-app-policy"></a><span data-ttu-id="768c4-129">Удаление политики приложений</span><span class="sxs-lookup"><span data-stu-id="768c4-129">Deleting an app policy</span></span>

<span data-ttu-id="768c4-130">Чтобы удалить политику приложений, вы можете сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="768c4-130">To delete an app policy, you can:</span></span>

- <span data-ttu-id="768c4-131">Выберите политику в списке политик, а затем щелкните **Удалить** на панели политики приложений.</span><span class="sxs-lookup"><span data-stu-id="768c4-131">Select the policy in the policy list, and then select **Delete** on the app policy pane.</span></span>
- <span data-ttu-id="768c4-132">Щелкните вертикальное многоточие возле политики в списке, а затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="768c4-132">Select the vertical ellipses for the policy in the list, and then select **Delete**.</span></span>

<span data-ttu-id="768c4-133">Альтернативным вариантом для удаления политики приложения является изменение ее состояния на неактивное.</span><span class="sxs-lookup"><span data-stu-id="768c4-133">An alternative to deleting an app policy is to change its status to inactive.</span></span> <span data-ttu-id="768c4-134">Находясь в неактивном состоянии, она не будет создавать оповещения.</span><span class="sxs-lookup"><span data-stu-id="768c4-134">Once inactive, it will not generate alerts.</span></span> <span data-ttu-id="768c4-135">Например, вместо удаления политики приложений с определенным набором условий, которые будут полезны для будущей политики, можно переименовать политику, указав, что она полезна, и перевести ее в неактивное состояние.</span><span class="sxs-lookup"><span data-stu-id="768c4-135">For example, rather than deleting an app policy for an app with a specific set of conditions that are useful for a future policy, rename the app policy to indicate its usefulness and set its status to inactive.</span></span> <span data-ttu-id="768c4-136">Позже вы можете вернуться к этой политике и изменить ее для аналогичного приложения, а также установить для нее состояние "режим аудита" или "неактивна".</span><span class="sxs-lookup"><span data-stu-id="768c4-136">You can later return to the policy and modify it for a similar app and set its status to audit mode or inactive.</span></span>
