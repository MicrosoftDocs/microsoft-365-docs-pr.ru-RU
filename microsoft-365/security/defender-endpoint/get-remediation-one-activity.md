---
title: Получить одно действие по исправлению по ID
description: Возвращает сведения для указанного действия по исправлению.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation by ID,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2b7afef2c090df709f9209f450d8d3aab0424bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772153"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="3c7fd-104">Получить одно действие по исправлению по ID</span><span class="sxs-lookup"><span data-stu-id="3c7fd-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3c7fd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3c7fd-105">**Applies to:**</span></span>

- [<span data-ttu-id="3c7fd-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c7fd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3c7fd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c7fd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3c7fd-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3c7fd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3c7fd-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="3c7fd-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="3c7fd-110">API description</span></span>

<span data-ttu-id="3c7fd-111">Возвращает сведения для указанного действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="3c7fd-112">Представляет те же столбцы, что [и "Получить](get-remediation-all-activities.md)все действия по исправлению", но возвращает результаты только для указанного действия по исправлению. </span><span class="sxs-lookup"><span data-stu-id="3c7fd-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="3c7fd-113">[Дополнительные информацию о действиях по исправлению.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="3c7fd-114">Список указанного действия по исправлению (id)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="3c7fd-115">**URL-адрес:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="3c7fd-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="3c7fd-116">Разрешения</span><span class="sxs-lookup"><span data-stu-id="3c7fd-116">Permissions</span></span>

<span data-ttu-id="3c7fd-117">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3c7fd-118">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="3c7fd-119">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="3c7fd-119">Permission type</span></span> | <span data-ttu-id="3c7fd-120">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3c7fd-120">Permission</span></span> | <span data-ttu-id="3c7fd-121">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="3c7fd-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3c7fd-122">Приложение</span><span class="sxs-lookup"><span data-stu-id="3c7fd-122">Application</span></span> | <span data-ttu-id="3c7fd-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="3c7fd-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="3c7fd-124">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="3c7fd-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="3c7fd-125">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-125">Delegated (work or school account)</span></span> | <span data-ttu-id="3c7fd-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="3c7fd-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="3c7fd-127">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="3c7fd-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="3c7fd-128">Свойства</span><span class="sxs-lookup"><span data-stu-id="3c7fd-128">Properties</span></span>

<span data-ttu-id="3c7fd-129">Свойство (id)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-129">Property (id)</span></span> | <span data-ttu-id="3c7fd-130">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3c7fd-130">Data type</span></span> | <span data-ttu-id="3c7fd-131">Описание</span><span class="sxs-lookup"><span data-stu-id="3c7fd-131">Description</span></span> | <span data-ttu-id="3c7fd-132">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="3c7fd-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="3c7fd-133">category</span><span class="sxs-lookup"><span data-stu-id="3c7fd-133">category</span></span> | <span data-ttu-id="3c7fd-134">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-134">String</span></span> | <span data-ttu-id="3c7fd-135">Категория действия по исправлению (конфигурация программного обеспечения и безопасности)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="3c7fd-136">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="3c7fd-136">Software</span></span>
<span data-ttu-id="3c7fd-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="3c7fd-137">completerEmail</span></span> | <span data-ttu-id="3c7fd-138">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-138">String</span></span> | <span data-ttu-id="3c7fd-139">Если действие по исправлению было выполнено вручную кем-то, в этом столбце содержится их электронная почта.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="3c7fd-140">null</span><span class="sxs-lookup"><span data-stu-id="3c7fd-140">null</span></span>
<span data-ttu-id="3c7fd-141">completerId</span><span class="sxs-lookup"><span data-stu-id="3c7fd-141">completerId</span></span> | <span data-ttu-id="3c7fd-142">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-142">String</span></span> | <span data-ttu-id="3c7fd-143">Если действие по исправлению было выполнено вручную кем-то, этот столбец содержит их объектный id</span><span class="sxs-lookup"><span data-stu-id="3c7fd-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="3c7fd-144">null</span><span class="sxs-lookup"><span data-stu-id="3c7fd-144">null</span></span>
<span data-ttu-id="3c7fd-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="3c7fd-145">completionMethod</span></span> | <span data-ttu-id="3c7fd-146">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-146">String</span></span> | <span data-ttu-id="3c7fd-147">Действие по исправлению может быть выполнено "автоматически" (если все устройства исправлены) или "вручную" человеком, который выбирает "метку как завершенную"</span><span class="sxs-lookup"><span data-stu-id="3c7fd-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="3c7fd-148">Автоматически</span><span class="sxs-lookup"><span data-stu-id="3c7fd-148">Automatic</span></span>
<span data-ttu-id="3c7fd-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="3c7fd-149">createdOn</span></span> | <span data-ttu-id="3c7fd-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="3c7fd-150">DateTime</span></span> | <span data-ttu-id="3c7fd-151">Время создания этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c7fd-151">Time this remediation activity was created</span></span> | <span data-ttu-id="3c7fd-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="3c7fd-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="3c7fd-153">description</span><span class="sxs-lookup"><span data-stu-id="3c7fd-153">description</span></span> | <span data-ttu-id="3c7fd-154">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-154">String</span></span> | <span data-ttu-id="3c7fd-155">Описание этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c7fd-155">Description of this remediation activity</span></span> | <span data-ttu-id="3c7fd-156">Обновите Microsoft Silverlight в более поздней версии, чтобы устранить известные уязвимости, влияющие на устройства.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="3c7fd-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="3c7fd-157">dueOn</span></span> | <span data-ttu-id="3c7fd-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="3c7fd-158">DateTime</span></span> | <span data-ttu-id="3c7fd-159">Дата, установленная создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c7fd-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="3c7fd-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="3c7fd-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="3c7fd-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="3c7fd-161">fixedDevices</span></span> |  | <span data-ttu-id="3c7fd-162">Количество исправленных устройств</span><span class="sxs-lookup"><span data-stu-id="3c7fd-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="3c7fd-163">2</span><span class="sxs-lookup"><span data-stu-id="3c7fd-163">2</span></span>
<span data-ttu-id="3c7fd-164">id</span><span class="sxs-lookup"><span data-stu-id="3c7fd-164">id</span></span> | <span data-ttu-id="3c7fd-165">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-165">String</span></span> | <span data-ttu-id="3c7fd-166">ID этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c7fd-166">ID of this remediation activity</span></span> | <span data-ttu-id="3c7fd-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="3c7fd-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="3c7fd-168">nameId</span><span class="sxs-lookup"><span data-stu-id="3c7fd-168">nameId</span></span> | <span data-ttu-id="3c7fd-169">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-169">String</span></span> | <span data-ttu-id="3c7fd-170">Связанное имя продукта</span><span class="sxs-lookup"><span data-stu-id="3c7fd-170">Related product name</span></span> | <span data-ttu-id="3c7fd-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="3c7fd-171">Microsoft Silverlight</span></span>
<span data-ttu-id="3c7fd-172">priority</span><span class="sxs-lookup"><span data-stu-id="3c7fd-172">priority</span></span> | <span data-ttu-id="3c7fd-173">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-173">String</span></span> | <span data-ttu-id="3c7fd-174">Приоритет, установленный создателем для этого действия по исправлению (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="3c7fd-175">Фишинговое сообщение с</span><span class="sxs-lookup"><span data-stu-id="3c7fd-175">High</span></span>
<span data-ttu-id="3c7fd-176">productId</span><span class="sxs-lookup"><span data-stu-id="3c7fd-176">productId</span></span> | <span data-ttu-id="3c7fd-177">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-177">String</span></span> | <span data-ttu-id="3c7fd-178">Соответствующий ID продукта</span><span class="sxs-lookup"><span data-stu-id="3c7fd-178">Related product ID</span></span> | <span data-ttu-id="3c7fd-179">microsoft-__-silverlight</span><span class="sxs-lookup"><span data-stu-id="3c7fd-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="3c7fd-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="3c7fd-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="3c7fd-181">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-181">String</span></span> | <span data-ttu-id="3c7fd-182">Несколько изменений конфигурации можно запросить только для устройств без влияния пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="3c7fd-183">Это значение указывает на выбор между "всеми выставленными устройствами" или "только устройствами без влияния пользователя".</span><span class="sxs-lookup"><span data-stu-id="3c7fd-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="3c7fd-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="3c7fd-184">AllExposedAssets</span></span>
<span data-ttu-id="3c7fd-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="3c7fd-185">rbacGroupNames</span></span> | <span data-ttu-id="3c7fd-186">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-186">String</span></span> | <span data-ttu-id="3c7fd-187">Связанные имена групп устройств</span><span class="sxs-lookup"><span data-stu-id="3c7fd-187">Related device group names</span></span> | <span data-ttu-id="3c7fd-188">[ "Windows Серверы", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="3c7fd-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="3c7fd-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="3c7fd-189">recommendedProgram</span></span> | <span data-ttu-id="3c7fd-190">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-190">String</span></span> | <span data-ttu-id="3c7fd-191">Рекомендуемая программа для обновления до</span><span class="sxs-lookup"><span data-stu-id="3c7fd-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="3c7fd-192">null</span><span class="sxs-lookup"><span data-stu-id="3c7fd-192">null</span></span>
<span data-ttu-id="3c7fd-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="3c7fd-193">recommendedVendor</span></span> | <span data-ttu-id="3c7fd-194">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-194">String</span></span> | <span data-ttu-id="3c7fd-195">Рекомендуемый поставщик для обновления до</span><span class="sxs-lookup"><span data-stu-id="3c7fd-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="3c7fd-196">null</span><span class="sxs-lookup"><span data-stu-id="3c7fd-196">null</span></span>
<span data-ttu-id="3c7fd-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="3c7fd-197">recommendedVersion</span></span> | <span data-ttu-id="3c7fd-198">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-198">String</span></span> | <span data-ttu-id="3c7fd-199">Рекомендуемая версия для обновления и обновления до</span><span class="sxs-lookup"><span data-stu-id="3c7fd-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="3c7fd-200">null</span><span class="sxs-lookup"><span data-stu-id="3c7fd-200">null</span></span>
<span data-ttu-id="3c7fd-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="3c7fd-201">relatedComponent</span></span> | <span data-ttu-id="3c7fd-202">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-202">String</span></span> | <span data-ttu-id="3c7fd-203">Связанный компонент этого действия по исправлению (аналогичный связанному компоненту для рекомендации по безопасности)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="3c7fd-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="3c7fd-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="3c7fd-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="3c7fd-205">requesterEmail</span></span> | <span data-ttu-id="3c7fd-206">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-206">String</span></span> | <span data-ttu-id="3c7fd-207">Адрес электронной почты создателя</span><span class="sxs-lookup"><span data-stu-id="3c7fd-207">Creator email address</span></span> | <span data-ttu-id="3c7fd-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3c7fd-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="3c7fd-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="3c7fd-209">requesterId</span></span> | <span data-ttu-id="3c7fd-210">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-210">String</span></span> | <span data-ttu-id="3c7fd-211">ID объекта Creator</span><span class="sxs-lookup"><span data-stu-id="3c7fd-211">Creator object id</span></span> | <span data-ttu-id="3c7fd-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="3c7fd-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="3c7fd-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="3c7fd-213">requesterNotes</span></span> | <span data-ttu-id="3c7fd-214">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-214">String</span></span> | <span data-ttu-id="3c7fd-215">Заметки (бесплатный текст), добавленные создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c7fd-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="3c7fd-216">null</span><span class="sxs-lookup"><span data-stu-id="3c7fd-216">null</span></span>
<span data-ttu-id="3c7fd-217">scid</span><span class="sxs-lookup"><span data-stu-id="3c7fd-217">scid</span></span> | <span data-ttu-id="3c7fd-218">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-218">String</span></span> | <span data-ttu-id="3c7fd-219">SCID связанной рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="3c7fd-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="3c7fd-220">null</span><span class="sxs-lookup"><span data-stu-id="3c7fd-220">null</span></span>
<span data-ttu-id="3c7fd-221">status</span><span class="sxs-lookup"><span data-stu-id="3c7fd-221">status</span></span> | <span data-ttu-id="3c7fd-222">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-222">String</span></span> | <span data-ttu-id="3c7fd-223">Состояние действия по исправлению (Active/Completed)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="3c7fd-224">Активация</span><span class="sxs-lookup"><span data-stu-id="3c7fd-224">Active</span></span>
<span data-ttu-id="3c7fd-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="3c7fd-225">statusLastModifiedOn</span></span> | <span data-ttu-id="3c7fd-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="3c7fd-226">DateTime</span></span> | <span data-ttu-id="3c7fd-227">Дата обновления поля состояния</span><span class="sxs-lookup"><span data-stu-id="3c7fd-227">Date when the status field was updated</span></span> | <span data-ttu-id="3c7fd-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="3c7fd-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="3c7fd-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="3c7fd-229">targetDevices</span></span> | <span data-ttu-id="3c7fd-230">Длинное целое</span><span class="sxs-lookup"><span data-stu-id="3c7fd-230">Long</span></span> | <span data-ttu-id="3c7fd-231">Количество открытых устройств, к которые применяется это исправление</span><span class="sxs-lookup"><span data-stu-id="3c7fd-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="3c7fd-232">43</span><span class="sxs-lookup"><span data-stu-id="3c7fd-232">43</span></span>
<span data-ttu-id="3c7fd-233">title</span><span class="sxs-lookup"><span data-stu-id="3c7fd-233">title</span></span> | <span data-ttu-id="3c7fd-234">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-234">String</span></span> | <span data-ttu-id="3c7fd-235">Название этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c7fd-235">Title of this remediation activity</span></span> | <span data-ttu-id="3c7fd-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="3c7fd-236">Microsoft Silverlight</span></span>
<span data-ttu-id="3c7fd-237">type</span><span class="sxs-lookup"><span data-stu-id="3c7fd-237">type</span></span> | <span data-ttu-id="3c7fd-238">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-238">String</span></span> | <span data-ttu-id="3c7fd-239">Тип устранения</span><span class="sxs-lookup"><span data-stu-id="3c7fd-239">Remediation type</span></span> | <span data-ttu-id="3c7fd-240">Update</span><span class="sxs-lookup"><span data-stu-id="3c7fd-240">Update</span></span>
<span data-ttu-id="3c7fd-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="3c7fd-241">vendorId</span></span> | <span data-ttu-id="3c7fd-242">String</span><span class="sxs-lookup"><span data-stu-id="3c7fd-242">String</span></span> | <span data-ttu-id="3c7fd-243">Имя связанного поставщика</span><span class="sxs-lookup"><span data-stu-id="3c7fd-243">Related vendor name</span></span> | <span data-ttu-id="3c7fd-244">Корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3c7fd-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="3c7fd-245">Пример</span><span class="sxs-lookup"><span data-stu-id="3c7fd-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="3c7fd-246">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="3c7fd-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="3c7fd-247">Пример ответа</span><span class="sxs-lookup"><span data-stu-id="3c7fd-247">Response example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a><span data-ttu-id="3c7fd-248">См. также</span><span class="sxs-lookup"><span data-stu-id="3c7fd-248">See also</span></span>

- [<span data-ttu-id="3c7fd-249">Методы и свойства по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c7fd-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="3c7fd-250">Перечисление всех действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c7fd-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="3c7fd-251">Перечисление устройств, затрагиваемых одним действием по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c7fd-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="3c7fd-252">Риск на основе угрозы & управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="3c7fd-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="3c7fd-253">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="3c7fd-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
