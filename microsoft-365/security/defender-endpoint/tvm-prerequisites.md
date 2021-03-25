---
title: Необходимые & разрешения — управление угрозами и уязвимостью
description: Прежде чем приступить к использованию управления угрозами и уязвимостями, убедитесь, что у вас есть соответствующие конфигурации и разрешения.
keywords: Необходимые & управления уязвимостями, необходимые для управления разрешениями на угрозы и уязвимости, предварительные условия разрешений MDATP TVM, управление уязвимостями
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca095a7a65a114182d736176840fdd4e651a8646
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074845"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="7d677-104">Необходимые & разрешения — управление угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="7d677-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d677-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7d677-105">**Applies to:**</span></span>

- [<span data-ttu-id="7d677-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7d677-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7d677-107">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="7d677-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="7d677-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d677-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7d677-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7d677-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7d677-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7d677-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="7d677-111">Убедитесь, что ваши устройства:</span><span class="sxs-lookup"><span data-stu-id="7d677-111">Ensure that your devices:</span></span>

- <span data-ttu-id="7d677-112">Находятся на борту в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7d677-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="7d677-113">Запуск [поддерживаемых операционных систем и платформ](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="7d677-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="7d677-114">Установить и развернуть в сети следующие обязательные обновления, чтобы повысить уровень обнаружения уязвимостей:</span><span class="sxs-lookup"><span data-stu-id="7d677-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="7d677-115">Выпуск</span><span class="sxs-lookup"><span data-stu-id="7d677-115">Release</span></span> | <span data-ttu-id="7d677-116">Номер и ссылка обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="7d677-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="7d677-117">Windows 10 Версия 1709</span><span class="sxs-lookup"><span data-stu-id="7d677-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="7d677-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) и [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="7d677-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="7d677-119">Windows 10 Версия 1803</span><span class="sxs-lookup"><span data-stu-id="7d677-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="7d677-120">[KB4493464](https://support.microsoft.com/help/4493464) и [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="7d677-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="7d677-121">Windows 10 Версия 1809</span><span class="sxs-lookup"><span data-stu-id="7d677-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="7d677-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="7d677-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="7d677-123">Windows 10 Версия 1903</span><span class="sxs-lookup"><span data-stu-id="7d677-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="7d677-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="7d677-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="7d677-125">Вы можете воспользоваться службами [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) и  [Microsoft Endpoint Configuration Manager,](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) чтобы помочь устранять угрозы, найденные в управлении угрозами и уязвимостями.</span><span class="sxs-lookup"><span data-stu-id="7d677-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="7d677-126">Если используется диспетчер конфигурации, обновите консоль до последней версии.</span><span class="sxs-lookup"><span data-stu-id="7d677-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="7d677-127">**Примечание.** Если включено подключение Intune, можно создать задачу безопасности Intune при создании запроса на исправление.</span><span class="sxs-lookup"><span data-stu-id="7d677-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="7d677-128">Этот параметр не появится, если подключение не установлено.</span><span class="sxs-lookup"><span data-stu-id="7d677-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="7d677-129">Есть по крайней мере одна рекомендация по безопасности, которую можно просмотреть на странице устройства</span><span class="sxs-lookup"><span data-stu-id="7d677-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="7d677-130">Помечены или помечены как совместно управляемые</span><span class="sxs-lookup"><span data-stu-id="7d677-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="7d677-131">Соответствующие параметры разрешений</span><span class="sxs-lookup"><span data-stu-id="7d677-131">Relevant permission options</span></span>

1. <span data-ttu-id="7d677-132">Войдите в Центр безопасности Microsoft Defender с помощью учетной записи с администратором безопасности или ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="7d677-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="7d677-133">В области навигации выберите **Параметры > ролей**.</span><span class="sxs-lookup"><span data-stu-id="7d677-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="7d677-134">Дополнительные сведения см. в дополнительных сведениях о создании и [управлении ролями для](user-roles.md) управления доступом на основе ролей</span><span class="sxs-lookup"><span data-stu-id="7d677-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="7d677-135">Просмотр данных</span><span class="sxs-lookup"><span data-stu-id="7d677-135">View data</span></span>

- <span data-ttu-id="7d677-136">**Операции безопасности** — просмотр всех данных операций безопасности на портале</span><span class="sxs-lookup"><span data-stu-id="7d677-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="7d677-137">**Управление угрозами и уязвимостью** — просмотр данных управления угрозами и уязвимостей на портале</span><span class="sxs-lookup"><span data-stu-id="7d677-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="7d677-138">Активные действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="7d677-138">Active remediation actions</span></span>

- <span data-ttu-id="7d677-139">**Операции безопасности** . Принятие ответных действий, утверждение или отклонение в ожидании действий по исправлению, управление разрешенными и заблокированными списками для автоматизации и индикаторов</span><span class="sxs-lookup"><span data-stu-id="7d677-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="7d677-140">**Управление угрозами и уязвимостями — обработка исключений** — создание новых исключений и управление активными исключениями</span><span class="sxs-lookup"><span data-stu-id="7d677-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="7d677-141">**Управление угрозами** и уязвимостью — обработка исправлений — отправка новых запросов на исправление, создание билетов и управление существующими действиями по исправлению.</span><span class="sxs-lookup"><span data-stu-id="7d677-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="7d677-142">Дополнительные сведения см. в [параметрах разрешений RBAC](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="7d677-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="7d677-143">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="7d677-143">Related articles</span></span>

- [<span data-ttu-id="7d677-144">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="7d677-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="7d677-145">Поддерживаемые операционные системы и платформы</span><span class="sxs-lookup"><span data-stu-id="7d677-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="7d677-146">Назначение значения устройства</span><span class="sxs-lookup"><span data-stu-id="7d677-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="7d677-147">Панель мониторинга управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="7d677-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

