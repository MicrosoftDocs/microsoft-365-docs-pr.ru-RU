---
title: Начало работы с политиками приложений
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
description: 'Начало работы: сведения о политиках приложений.'
ms.openlocfilehash: 3f80048835388e740ba64ac36d1aa19594bf7a9d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420407"
---
# <a name="get-started-with-app-policies"></a><span data-ttu-id="4f948-103">Начало работы с политиками приложений</span><span class="sxs-lookup"><span data-stu-id="4f948-103">Get started with app policies</span></span>

><span data-ttu-id="4f948-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4f948-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4f948-105">Политики приложений для управления приложениями Майкрософт — это способ применения как упреждающих, так и реактивных условий создания оповещений или автоматического исправления, отвечающих вашим конкретным задачам в области соответствия приложений требованиям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4f948-105">App policies for Microsoft app governance are the way that you can implement more proactive or reactive conditions to create alerts or automatic remediation for your specific needs for app compliance in your organization.</span></span>

<span data-ttu-id="4f948-106">Чтобы просмотреть список текущих политик приложений, перейдите в раздел **Центр соответствия требованиям Microsoft 365 > Защита приложений и управление ими > Политики**.</span><span class="sxs-lookup"><span data-stu-id="4f948-106">To see the list of current app policies, go to **Microsoft 365 Compliance Center > App protection & governance > Policies**.</span></span>

![Страница сводки политик MAPG в Центре соответствия требованиям Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a><span data-ttu-id="4f948-108">Что имеется на панели мониторинга политик приложений</span><span class="sxs-lookup"><span data-stu-id="4f948-108">What’s available on the app policies dashboard</span></span>

<span data-ttu-id="4f948-109">Вы можете увидеть количество активных, неактивных и тестируемых политик, а также следующие сведения для каждой политики:</span><span class="sxs-lookup"><span data-stu-id="4f948-109">You can see the number of active, inactive, and test policies, and the following information for each policy:</span></span>

- <span data-ttu-id="4f948-110">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="4f948-110">**Policy name**</span></span>
- <span data-ttu-id="4f948-111">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="4f948-111">**Status**</span></span>

  - <span data-ttu-id="4f948-112">**Активные**: все действия и оценка политики активны.</span><span class="sxs-lookup"><span data-stu-id="4f948-112">**Active**:  All policy evaluation and actions are active.</span></span>
  - <span data-ttu-id="4f948-113">**Неактивные**: все действия и оценка политики отключены.</span><span class="sxs-lookup"><span data-stu-id="4f948-113">**Inactive**: All policy evaluation and actions are disabled.</span></span>
  - <span data-ttu-id="4f948-114">**Режим аудита**: оценка политики находится в режиме аудита.</span><span class="sxs-lookup"><span data-stu-id="4f948-114">**Audit mode**: Policy evaluation is in audit mode.</span></span> <span data-ttu-id="4f948-115">Политика активна, но ее действия отключены.</span><span class="sxs-lookup"><span data-stu-id="4f948-115">The policy is active but policy actions are disabled.</span></span>

- <span data-ttu-id="4f948-116">**Серьезность**: уровень серьезности, установленный для всех оповещений, инициированных по причине оценки этой политики как true, что является частью конфигурации политики.</span><span class="sxs-lookup"><span data-stu-id="4f948-116">**Severity**: Severity level set on any alerts triggered because of this policy being evaluated as true, which is part of the configuration of the policy.</span></span>
- <span data-ttu-id="4f948-117">**Количество активных оповещений**: созданные политикой оповещения, имеющие состояние **Выполняется** или **Новое**.</span><span class="sxs-lookup"><span data-stu-id="4f948-117">**Number of active alerts**: Alerts generated by the policy that have an **In Progress** or **New** status.</span></span>
- <span data-ttu-id="4f948-118">**Общее количество оповещений**: активные и завершенные оповещения для этой политики.</span><span class="sxs-lookup"><span data-stu-id="4f948-118">**Number of total alerts**: Both active alerts and resolved alerts for this policy.</span></span>
- <span data-ttu-id="4f948-119">**Дата последнего оповещения**: дата последнего оповещения, созданного в связи с этой политикой.</span><span class="sxs-lookup"><span data-stu-id="4f948-119">**Last Alert Date**: Date of last generated alert due to this policy.</span></span>
- <span data-ttu-id="4f948-120">**Последнее изменение**: дата последнего изменения политики.</span><span class="sxs-lookup"><span data-stu-id="4f948-120">**Last Modified**: Date when this policy was last changed.</span></span>

<span data-ttu-id="4f948-121">По умолчанию список политик сортируется по атрибуту **Последнее изменение**.</span><span class="sxs-lookup"><span data-stu-id="4f948-121">The policy list is sorted by **Last modified** by default.</span></span> <span data-ttu-id="4f948-122">Чтобы отсортировать список по другому атрибуту, выберите его имя.</span><span class="sxs-lookup"><span data-stu-id="4f948-122">To sort the list by another attribute, select the attribute name.</span></span>

<span data-ttu-id="4f948-123">При выборе политики откроется подробная панель политики со следующими дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="4f948-123">When you select a policy, you get a detailed policy pane with these additional details:</span></span>

- <span data-ttu-id="4f948-124">**Описание**: более подробное объяснение назначения политики.</span><span class="sxs-lookup"><span data-stu-id="4f948-124">**Description**: A more detailed explanation of the purpose of the policy.</span></span>
- <span data-ttu-id="4f948-125">**Кем создана**: имя субъекта-пользователя (UPN) учетной записи, создавшей политику.</span><span class="sxs-lookup"><span data-stu-id="4f948-125">**Created by**: user principal name (UPN) of the account that created the policy.</span></span>
- <span data-ttu-id="4f948-126">Список активных оповещений, созданных этой политикой.</span><span class="sxs-lookup"><span data-stu-id="4f948-126">A list of the active alerts generated by this policy.</span></span>

<span data-ttu-id="4f948-127">Вы можете изменить или удалить политику приложений, щелкнув **Изменить** или **Удалить** на подробной панели политики или нажав вертикальное многоточие, относящееся к данной политике, в списке политик.</span><span class="sxs-lookup"><span data-stu-id="4f948-127">You can edit or delete an app policy by selecting **Edit** or **Delete** in the detailed policy pane or by selecting the vertical ellipses of the policy in the policy list.</span></span>

<span data-ttu-id="4f948-128">Кроме того, у вас есть следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="4f948-128">You can also:</span></span>

- <span data-ttu-id="4f948-129">Создание новой политики.</span><span class="sxs-lookup"><span data-stu-id="4f948-129">Create a new policy.</span></span> <span data-ttu-id="4f948-130">Вы можете начать с политики использования приложений или политики разрешений.</span><span class="sxs-lookup"><span data-stu-id="4f948-130">You can start with an app usage policy or a permissions policy.</span></span>
- <span data-ttu-id="4f948-131">Экспорт списка политик в файл данных с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="4f948-131">Export the policy list to a comma-separated value (CSV) file.</span></span> <span data-ttu-id="4f948-132">Например, можно открыть этот CVS-файл в Microsoft Excel и отсортировать политики по атрибуту **Серьезность**, а затем по атрибуту **Общее количество оповещений**.</span><span class="sxs-lookup"><span data-stu-id="4f948-132">For example, you could open the CVS file in Microsoft Excel and sort the policies by **Severity** and then **Number of Total Alerts**.</span></span>
- <span data-ttu-id="4f948-133">Поиск в списке политик.</span><span class="sxs-lookup"><span data-stu-id="4f948-133">Search the policy list.</span></span>

## <a name="next-step"></a><span data-ttu-id="4f948-134">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="4f948-134">Next step</span></span>

[<span data-ttu-id="4f948-135">Создание политики приложений.</span><span class="sxs-lookup"><span data-stu-id="4f948-135">Create an app policy.</span></span>](app-governance-app-policies-create.md)