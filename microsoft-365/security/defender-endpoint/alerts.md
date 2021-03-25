---
title: Получить API оповещений
description: Узнайте о методах и свойствах типа ресурса Alert в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4997d7118b139d993ed94ed917137ca107940e46
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199625"
---
# <a name="alert-resource-type"></a><span data-ttu-id="0fe64-104">Тип ресурса оповещений</span><span class="sxs-lookup"><span data-stu-id="0fe64-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0fe64-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0fe64-105">**Applies to:**</span></span>
- [<span data-ttu-id="0fe64-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0fe64-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="0fe64-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0fe64-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0fe64-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0fe64-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="0fe64-109">Методы</span><span class="sxs-lookup"><span data-stu-id="0fe64-109">Methods</span></span>

<span data-ttu-id="0fe64-110">Метод</span><span class="sxs-lookup"><span data-stu-id="0fe64-110">Method</span></span> |<span data-ttu-id="0fe64-111">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="0fe64-111">Return Type</span></span> |<span data-ttu-id="0fe64-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0fe64-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="0fe64-113">Получение оповещения</span><span class="sxs-lookup"><span data-stu-id="0fe64-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="0fe64-114">Оповещение</span><span class="sxs-lookup"><span data-stu-id="0fe64-114">Alert</span></span>](alerts.md) | <span data-ttu-id="0fe64-115">Получите один объект [оповещения.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0fe64-115">Get a single [alert](alerts.md) object.</span></span>
<span data-ttu-id="0fe64-116">[перечисление оповещений](get-alerts.md);</span><span class="sxs-lookup"><span data-stu-id="0fe64-116">[List alerts](get-alerts.md)</span></span> | <span data-ttu-id="0fe64-117">[Коллекция оповещений](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0fe64-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="0fe64-118">Список [оповещений.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0fe64-118">List [alert](alerts.md) collection.</span></span>
<span data-ttu-id="0fe64-119">[обновление оповещения](update-alert.md).</span><span class="sxs-lookup"><span data-stu-id="0fe64-119">[Update alert](update-alert.md)</span></span> | [<span data-ttu-id="0fe64-120">Оповещение</span><span class="sxs-lookup"><span data-stu-id="0fe64-120">Alert</span></span>](alerts.md) | <span data-ttu-id="0fe64-121">Обновление определенного [оповещения](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="0fe64-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="0fe64-122">Пакетные оповещения об обновлении</span><span class="sxs-lookup"><span data-stu-id="0fe64-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="0fe64-123">Обновление пакета [оповещений.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0fe64-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="0fe64-124">Создание оповещений</span><span class="sxs-lookup"><span data-stu-id="0fe64-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="0fe64-125">Оповещение</span><span class="sxs-lookup"><span data-stu-id="0fe64-125">Alert</span></span>](alerts.md)|<span data-ttu-id="0fe64-126">Создание оповещений на основе данных событий, полученных из [Advanced Hunting.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="0fe64-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="0fe64-127">Списки связанных доменов</span><span class="sxs-lookup"><span data-stu-id="0fe64-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="0fe64-128">Коллекция доменов</span><span class="sxs-lookup"><span data-stu-id="0fe64-128">Domain collection</span></span>| <span data-ttu-id="0fe64-129">Список URL-адресов, связанных с оповещением.</span><span class="sxs-lookup"><span data-stu-id="0fe64-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="0fe64-130">Файлы, связанные со списком</span><span class="sxs-lookup"><span data-stu-id="0fe64-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="0fe64-131">[Коллекция](files.md) файлов</span><span class="sxs-lookup"><span data-stu-id="0fe64-131">[File](files.md) collection</span></span> |  <span data-ttu-id="0fe64-132">Список [сущностями](files.md) файлов, связанных с [оповещением.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0fe64-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="0fe64-133">IPs, связанные со списком</span><span class="sxs-lookup"><span data-stu-id="0fe64-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="0fe64-134">Коллекция IP</span><span class="sxs-lookup"><span data-stu-id="0fe64-134">IP collection</span></span> | <span data-ttu-id="0fe64-135">Список IPs, связанных с оповещением.</span><span class="sxs-lookup"><span data-stu-id="0fe64-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="0fe64-136">Получить связанные машины</span><span class="sxs-lookup"><span data-stu-id="0fe64-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="0fe64-137">Компьютер</span><span class="sxs-lookup"><span data-stu-id="0fe64-137">Machine</span></span>](machine.md) | <span data-ttu-id="0fe64-138">[Машина,](machine.md) связанная с оповещением. [](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0fe64-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="0fe64-139">Получить связанных пользователей</span><span class="sxs-lookup"><span data-stu-id="0fe64-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="0fe64-140">Пользователь</span><span class="sxs-lookup"><span data-stu-id="0fe64-140">User</span></span>](user.md) | <span data-ttu-id="0fe64-141">[Пользователь,](user.md) связанный с оповещением. [](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0fe64-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>


## <a name="properties"></a><span data-ttu-id="0fe64-142">Свойства</span><span class="sxs-lookup"><span data-stu-id="0fe64-142">Properties</span></span>

<span data-ttu-id="0fe64-143">Свойство</span><span class="sxs-lookup"><span data-stu-id="0fe64-143">Property</span></span> |    <span data-ttu-id="0fe64-144">Тип</span><span class="sxs-lookup"><span data-stu-id="0fe64-144">Type</span></span>    |    <span data-ttu-id="0fe64-145">Описание</span><span class="sxs-lookup"><span data-stu-id="0fe64-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="0fe64-146">id</span><span class="sxs-lookup"><span data-stu-id="0fe64-146">id</span></span> | <span data-ttu-id="0fe64-147">Строка</span><span class="sxs-lookup"><span data-stu-id="0fe64-147">String</span></span> | <span data-ttu-id="0fe64-148">ИД оповещения.</span><span class="sxs-lookup"><span data-stu-id="0fe64-148">Alert ID.</span></span>
<span data-ttu-id="0fe64-149">title</span><span class="sxs-lookup"><span data-stu-id="0fe64-149">title</span></span> | <span data-ttu-id="0fe64-150">String</span><span class="sxs-lookup"><span data-stu-id="0fe64-150">String</span></span> | <span data-ttu-id="0fe64-151">Заголовок оповещения.</span><span class="sxs-lookup"><span data-stu-id="0fe64-151">Alert title.</span></span>
<span data-ttu-id="0fe64-152">description</span><span class="sxs-lookup"><span data-stu-id="0fe64-152">description</span></span> | <span data-ttu-id="0fe64-153">String</span><span class="sxs-lookup"><span data-stu-id="0fe64-153">String</span></span> | <span data-ttu-id="0fe64-154">Описание оповещения.</span><span class="sxs-lookup"><span data-stu-id="0fe64-154">Alert description.</span></span>
<span data-ttu-id="0fe64-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="0fe64-155">alertCreationTime</span></span> | <span data-ttu-id="0fe64-156">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0fe64-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0fe64-157">Дата и время (в UTC) было создано оповещение.</span><span class="sxs-lookup"><span data-stu-id="0fe64-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="0fe64-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="0fe64-158">lastEventTime</span></span> | <span data-ttu-id="0fe64-159">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0fe64-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0fe64-160">Последнее событие, срабатывающее оповещением на том же устройстве.</span><span class="sxs-lookup"><span data-stu-id="0fe64-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="0fe64-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="0fe64-161">firstEventTime</span></span> | <span data-ttu-id="0fe64-162">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0fe64-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0fe64-163">Первое появление события, срабатывающее оповещением на этом устройстве.</span><span class="sxs-lookup"><span data-stu-id="0fe64-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="0fe64-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="0fe64-164">lastUpdateTime</span></span> | <span data-ttu-id="0fe64-165">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0fe64-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0fe64-166">Дата и время (в UTC) последнее обновление оповещений.</span><span class="sxs-lookup"><span data-stu-id="0fe64-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="0fe64-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="0fe64-167">resolvedTime</span></span> | <span data-ttu-id="0fe64-168">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0fe64-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0fe64-169">Дата и время, в течение которых состояние оповещений было изменено на "Разрешено".</span><span class="sxs-lookup"><span data-stu-id="0fe64-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="0fe64-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="0fe64-170">incidentId</span></span> | <span data-ttu-id="0fe64-171">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="0fe64-171">Nullable Long</span></span> | <span data-ttu-id="0fe64-172">[ИД](view-incidents-queue.md) оповещений об инциденте.</span><span class="sxs-lookup"><span data-stu-id="0fe64-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="0fe64-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="0fe64-173">investigationId</span></span> | <span data-ttu-id="0fe64-174">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="0fe64-174">Nullable Long</span></span> | <span data-ttu-id="0fe64-175">ID [исследования,](automated-investigations.md) связанный с оповещением.</span><span class="sxs-lookup"><span data-stu-id="0fe64-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="0fe64-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="0fe64-176">investigationState</span></span> | <span data-ttu-id="0fe64-177">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="0fe64-177">Nullable Enum</span></span> | <span data-ttu-id="0fe64-178">Текущее состояние [расследования](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="0fe64-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="0fe64-179">Возможные значения: "Unknown", "Terminated", "SuccessfullyRemediated", 'Benign', 'Failed', 'PartiallyRemediated', "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedAlert", "SuppressedAlert".</span><span class="sxs-lookup"><span data-stu-id="0fe64-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="0fe64-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="0fe64-180">assignedTo</span></span> | <span data-ttu-id="0fe64-181">String</span><span class="sxs-lookup"><span data-stu-id="0fe64-181">String</span></span> | <span data-ttu-id="0fe64-182">Владелец оповещений.</span><span class="sxs-lookup"><span data-stu-id="0fe64-182">Owner of the alert.</span></span>
<span data-ttu-id="0fe64-183">severity</span><span class="sxs-lookup"><span data-stu-id="0fe64-183">severity</span></span> | <span data-ttu-id="0fe64-184">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0fe64-184">Enum</span></span> | <span data-ttu-id="0fe64-185">Степень серьезности оповещения.</span><span class="sxs-lookup"><span data-stu-id="0fe64-185">Severity of the alert.</span></span> <span data-ttu-id="0fe64-186">Возможные значения: "UnSpecified", "Informational", "Low", "Medium" и "High".</span><span class="sxs-lookup"><span data-stu-id="0fe64-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="0fe64-187">status</span><span class="sxs-lookup"><span data-stu-id="0fe64-187">status</span></span> | <span data-ttu-id="0fe64-188">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0fe64-188">Enum</span></span> | <span data-ttu-id="0fe64-189">Указывает текущее состояние оповещений.</span><span class="sxs-lookup"><span data-stu-id="0fe64-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="0fe64-190">Возможные значения: "Unknown", "New", "InProgress" и "Resolved".</span><span class="sxs-lookup"><span data-stu-id="0fe64-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="0fe64-191">classification</span><span class="sxs-lookup"><span data-stu-id="0fe64-191">classification</span></span> | <span data-ttu-id="0fe64-192">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="0fe64-192">Nullable Enum</span></span> | <span data-ttu-id="0fe64-193">Спецификация оповещений.</span><span class="sxs-lookup"><span data-stu-id="0fe64-193">Specification of the alert.</span></span> <span data-ttu-id="0fe64-194">Возможные значения: "Неизвестный", "FalsePositive", "TruePositive".</span><span class="sxs-lookup"><span data-stu-id="0fe64-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="0fe64-195">определение</span><span class="sxs-lookup"><span data-stu-id="0fe64-195">determination</span></span> | <span data-ttu-id="0fe64-196">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="0fe64-196">Nullable Enum</span></span> | <span data-ttu-id="0fe64-197">Указывает определение оповещений.</span><span class="sxs-lookup"><span data-stu-id="0fe64-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="0fe64-198">Возможные значения: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other".</span><span class="sxs-lookup"><span data-stu-id="0fe64-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="0fe64-199">category</span><span class="sxs-lookup"><span data-stu-id="0fe64-199">category</span></span>| <span data-ttu-id="0fe64-200">String</span><span class="sxs-lookup"><span data-stu-id="0fe64-200">String</span></span> | <span data-ttu-id="0fe64-201">Категория оповещения.</span><span class="sxs-lookup"><span data-stu-id="0fe64-201">Category of the alert.</span></span>
<span data-ttu-id="0fe64-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="0fe64-202">detectionSource</span></span> | <span data-ttu-id="0fe64-203">Строка</span><span class="sxs-lookup"><span data-stu-id="0fe64-203">String</span></span> | <span data-ttu-id="0fe64-204">Источник обнаружения.</span><span class="sxs-lookup"><span data-stu-id="0fe64-204">Detection source.</span></span>
<span data-ttu-id="0fe64-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="0fe64-205">threatFamilyName</span></span> | <span data-ttu-id="0fe64-206">Строка</span><span class="sxs-lookup"><span data-stu-id="0fe64-206">String</span></span> | <span data-ttu-id="0fe64-207">Семейство угроз.</span><span class="sxs-lookup"><span data-stu-id="0fe64-207">Threat family.</span></span>
<span data-ttu-id="0fe64-208">threatName</span><span class="sxs-lookup"><span data-stu-id="0fe64-208">threatName</span></span> | <span data-ttu-id="0fe64-209">Строка</span><span class="sxs-lookup"><span data-stu-id="0fe64-209">String</span></span> | <span data-ttu-id="0fe64-210">Имя угрозы.</span><span class="sxs-lookup"><span data-stu-id="0fe64-210">Threat name.</span></span>
<span data-ttu-id="0fe64-211">machineId</span><span class="sxs-lookup"><span data-stu-id="0fe64-211">machineId</span></span> | <span data-ttu-id="0fe64-212">Строка</span><span class="sxs-lookup"><span data-stu-id="0fe64-212">String</span></span> | <span data-ttu-id="0fe64-213">ID объекта [машины,](machine.md) связанного с оповещением.</span><span class="sxs-lookup"><span data-stu-id="0fe64-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="0fe64-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="0fe64-214">computerDnsName</span></span> | <span data-ttu-id="0fe64-215">Строка</span><span class="sxs-lookup"><span data-stu-id="0fe64-215">String</span></span> | <span data-ttu-id="0fe64-216">[полное](machine.md) имя машины.</span><span class="sxs-lookup"><span data-stu-id="0fe64-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="0fe64-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="0fe64-217">aadTenantId</span></span> | <span data-ttu-id="0fe64-218">Строка</span><span class="sxs-lookup"><span data-stu-id="0fe64-218">String</span></span> | <span data-ttu-id="0fe64-219">ID Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0fe64-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="0fe64-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="0fe64-220">detectorId</span></span> | <span data-ttu-id="0fe64-221">Строка</span><span class="sxs-lookup"><span data-stu-id="0fe64-221">String</span></span> | <span data-ttu-id="0fe64-222">ID детектора, который вызвал оповещение.</span><span class="sxs-lookup"><span data-stu-id="0fe64-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="0fe64-223">comments</span><span class="sxs-lookup"><span data-stu-id="0fe64-223">comments</span></span> | <span data-ttu-id="0fe64-224">Список замечаний оповещений</span><span class="sxs-lookup"><span data-stu-id="0fe64-224">List of Alert comments</span></span> | <span data-ttu-id="0fe64-225">Объект Alert Comment содержит строку комментариев, createdBy string и createTime date time.</span><span class="sxs-lookup"><span data-stu-id="0fe64-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="0fe64-226">Свидетельство</span><span class="sxs-lookup"><span data-stu-id="0fe64-226">Evidence</span></span> | <span data-ttu-id="0fe64-227">Список доказательств оповещений</span><span class="sxs-lookup"><span data-stu-id="0fe64-227">List of Alert evidence</span></span> | <span data-ttu-id="0fe64-228">Доказательства, относящиеся к оповещению.</span><span class="sxs-lookup"><span data-stu-id="0fe64-228">Evidence related to the alert.</span></span> <span data-ttu-id="0fe64-229">См. приведенный ниже пример.</span><span class="sxs-lookup"><span data-stu-id="0fe64-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="0fe64-230">Пример ответа для получения единого оповещения:</span><span class="sxs-lookup"><span data-stu-id="0fe64-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
