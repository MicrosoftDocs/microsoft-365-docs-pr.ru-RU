---
title: Список всех действий по исправлению
description: Возвращает сведения обо всех действиях по исправлению.
keywords: apis, remediation, remediation api, get, remediation tasks,
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
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061161"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="0fd23-104">Список всех действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="0fd23-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0fd23-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0fd23-105">**Applies to:**</span></span>

- [<span data-ttu-id="0fd23-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0fd23-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0fd23-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0fd23-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0fd23-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0fd23-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0fd23-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0fd23-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="0fd23-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="0fd23-110">API description</span></span>

<span data-ttu-id="0fd23-111">Возвращает сведения обо всех действиях по исправлению.</span><span class="sxs-lookup"><span data-stu-id="0fd23-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="0fd23-112">[Дополнительные информацию о действиях по исправлению.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="0fd23-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="0fd23-113">**URL-адрес:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="0fd23-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="0fd23-114">**Сведения о свойствах**</span><span class="sxs-lookup"><span data-stu-id="0fd23-114">**Properties** details</span></span>

<span data-ttu-id="0fd23-115">Свойство (id)</span><span class="sxs-lookup"><span data-stu-id="0fd23-115">Property (id)</span></span> | <span data-ttu-id="0fd23-116">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0fd23-116">Data type</span></span> | <span data-ttu-id="0fd23-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd23-117">Description</span></span> | <span data-ttu-id="0fd23-118">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="0fd23-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="0fd23-119">category</span><span class="sxs-lookup"><span data-stu-id="0fd23-119">category</span></span> | <span data-ttu-id="0fd23-120">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-120">String</span></span> | <span data-ttu-id="0fd23-121">Категория действия по исправлению (конфигурация программного обеспечения и безопасности)</span><span class="sxs-lookup"><span data-stu-id="0fd23-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="0fd23-122">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="0fd23-122">Software</span></span>
<span data-ttu-id="0fd23-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="0fd23-123">completerEmail</span></span> | <span data-ttu-id="0fd23-124">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-124">String</span></span> | <span data-ttu-id="0fd23-125">Если действие по исправлению было выполнено вручную кем-то, в этом столбце содержится их электронная почта.</span><span class="sxs-lookup"><span data-stu-id="0fd23-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="0fd23-126">null</span><span class="sxs-lookup"><span data-stu-id="0fd23-126">null</span></span>
<span data-ttu-id="0fd23-127">completerId</span><span class="sxs-lookup"><span data-stu-id="0fd23-127">completerId</span></span> | <span data-ttu-id="0fd23-128">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-128">String</span></span> | <span data-ttu-id="0fd23-129">Если действие по исправлению было выполнено вручную кем-то, этот столбец содержит их объектный id</span><span class="sxs-lookup"><span data-stu-id="0fd23-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="0fd23-130">null</span><span class="sxs-lookup"><span data-stu-id="0fd23-130">null</span></span>
<span data-ttu-id="0fd23-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="0fd23-131">completionMethod</span></span> | <span data-ttu-id="0fd23-132">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-132">String</span></span> | <span data-ttu-id="0fd23-133">Действие по исправлению может быть выполнено "автоматически" (если все устройства исправлены) или "вручную" человеком, который выбирает "метку как завершенную"</span><span class="sxs-lookup"><span data-stu-id="0fd23-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="0fd23-134">Автоматически</span><span class="sxs-lookup"><span data-stu-id="0fd23-134">Automatic</span></span>
<span data-ttu-id="0fd23-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="0fd23-135">createdOn</span></span> | <span data-ttu-id="0fd23-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="0fd23-136">DateTime</span></span> | <span data-ttu-id="0fd23-137">Время создания этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="0fd23-137">Time this remediation activity was created</span></span> | <span data-ttu-id="0fd23-138">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="0fd23-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="0fd23-139">description</span><span class="sxs-lookup"><span data-stu-id="0fd23-139">description</span></span> | <span data-ttu-id="0fd23-140">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-140">String</span></span> | <span data-ttu-id="0fd23-141">Описание этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="0fd23-141">Description of this remediation activity</span></span> | <span data-ttu-id="0fd23-142">Обновите Chrome в более поздней версии, чтобы устранить 1248 известных уязвимостей, затрагивающих устройства.</span><span class="sxs-lookup"><span data-stu-id="0fd23-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="0fd23-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="0fd23-143">dueOn</span></span> | <span data-ttu-id="0fd23-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="0fd23-144">DateTime</span></span> | <span data-ttu-id="0fd23-145">Дата, установленная создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="0fd23-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="0fd23-146">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="0fd23-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="0fd23-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="0fd23-147">fixedDevices</span></span> | <span data-ttu-id="0fd23-148">.</span><span class="sxs-lookup"><span data-stu-id="0fd23-148">.</span></span> | <span data-ttu-id="0fd23-149">Количество исправленных устройств</span><span class="sxs-lookup"><span data-stu-id="0fd23-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="0fd23-150">2</span><span class="sxs-lookup"><span data-stu-id="0fd23-150">2</span></span>
<span data-ttu-id="0fd23-151">id</span><span class="sxs-lookup"><span data-stu-id="0fd23-151">id</span></span> | <span data-ttu-id="0fd23-152">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-152">String</span></span> | <span data-ttu-id="0fd23-153">ID этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="0fd23-153">ID of this remediation activity</span></span> | <span data-ttu-id="0fd23-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="0fd23-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="0fd23-155">nameId</span><span class="sxs-lookup"><span data-stu-id="0fd23-155">nameId</span></span> | <span data-ttu-id="0fd23-156">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-156">String</span></span> | <span data-ttu-id="0fd23-157">Связанное имя продукта</span><span class="sxs-lookup"><span data-stu-id="0fd23-157">Related product name</span></span> | <span data-ttu-id="0fd23-158">chrome</span><span class="sxs-lookup"><span data-stu-id="0fd23-158">chrome</span></span>
<span data-ttu-id="0fd23-159">priority</span><span class="sxs-lookup"><span data-stu-id="0fd23-159">priority</span></span> | <span data-ttu-id="0fd23-160">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-160">String</span></span> | <span data-ttu-id="0fd23-161">Приоритет, установленный создателем для этого действия по исправлению (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="0fd23-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="0fd23-162">Высокая</span><span class="sxs-lookup"><span data-stu-id="0fd23-162">High</span></span>
<span data-ttu-id="0fd23-163">productId</span><span class="sxs-lookup"><span data-stu-id="0fd23-163">productId</span></span> | <span data-ttu-id="0fd23-164">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-164">String</span></span> | <span data-ttu-id="0fd23-165">Соответствующий ID продукта</span><span class="sxs-lookup"><span data-stu-id="0fd23-165">Related product ID</span></span> | <span data-ttu-id="0fd23-166">Google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="0fd23-166">google-_-chrome</span></span>
<span data-ttu-id="0fd23-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="0fd23-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="0fd23-168">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-168">String</span></span> | <span data-ttu-id="0fd23-169">Несколько изменений конфигурации можно запросить только для устройств без влияния пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fd23-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="0fd23-170">Это значение указывает на выбор между "всеми выставленными устройствами" или "только устройствами без влияния пользователя".</span><span class="sxs-lookup"><span data-stu-id="0fd23-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="0fd23-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="0fd23-171">AllExposedAssets</span></span>
<span data-ttu-id="0fd23-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="0fd23-172">rbacGroupNames</span></span> | <span data-ttu-id="0fd23-173">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-173">String</span></span> | <span data-ttu-id="0fd23-174">Связанные имена групп устройств</span><span class="sxs-lookup"><span data-stu-id="0fd23-174">Related device group names</span></span> | <span data-ttu-id="0fd23-175">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="0fd23-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="0fd23-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="0fd23-176">recommendedProgram</span></span> | <span data-ttu-id="0fd23-177">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-177">String</span></span> | <span data-ttu-id="0fd23-178">Рекомендуемая программа для обновления до</span><span class="sxs-lookup"><span data-stu-id="0fd23-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="0fd23-179">null</span><span class="sxs-lookup"><span data-stu-id="0fd23-179">null</span></span>
<span data-ttu-id="0fd23-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="0fd23-180">recommendedVendor</span></span> | <span data-ttu-id="0fd23-181">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-181">String</span></span> | <span data-ttu-id="0fd23-182">Рекомендуемый поставщик для обновления до</span><span class="sxs-lookup"><span data-stu-id="0fd23-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="0fd23-183">null</span><span class="sxs-lookup"><span data-stu-id="0fd23-183">null</span></span>
<span data-ttu-id="0fd23-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="0fd23-184">recommendedVersion</span></span> | <span data-ttu-id="0fd23-185">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-185">String</span></span> | <span data-ttu-id="0fd23-186">Рекомендуемая версия для обновления и обновления до</span><span class="sxs-lookup"><span data-stu-id="0fd23-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="0fd23-187">null</span><span class="sxs-lookup"><span data-stu-id="0fd23-187">null</span></span>
<span data-ttu-id="0fd23-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="0fd23-188">relatedComponent</span></span> | <span data-ttu-id="0fd23-189">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-189">String</span></span> | <span data-ttu-id="0fd23-190">Связанный компонент этого действия по исправлению (аналогичный связанному компоненту для рекомендации по безопасности)</span><span class="sxs-lookup"><span data-stu-id="0fd23-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="0fd23-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="0fd23-191">Google Chrome</span></span>
<span data-ttu-id="0fd23-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="0fd23-192">requesterEmail</span></span> | <span data-ttu-id="0fd23-193">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-193">String</span></span> | <span data-ttu-id="0fd23-194">Адрес электронной почты создателя</span><span class="sxs-lookup"><span data-stu-id="0fd23-194">Creator email address</span></span> | <span data-ttu-id="0fd23-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fd23-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="0fd23-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="0fd23-196">requesterId</span></span> | <span data-ttu-id="0fd23-197">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-197">String</span></span> | <span data-ttu-id="0fd23-198">ID объекта Creator</span><span class="sxs-lookup"><span data-stu-id="0fd23-198">Creator object id</span></span> | <span data-ttu-id="0fd23-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="0fd23-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="0fd23-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="0fd23-200">requesterNotes</span></span> | <span data-ttu-id="0fd23-201">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-201">String</span></span> | <span data-ttu-id="0fd23-202">Заметки (бесплатный текст), добавленные создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="0fd23-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="0fd23-203">null</span><span class="sxs-lookup"><span data-stu-id="0fd23-203">null</span></span>
<span data-ttu-id="0fd23-204">scid</span><span class="sxs-lookup"><span data-stu-id="0fd23-204">scid</span></span> | <span data-ttu-id="0fd23-205">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-205">String</span></span> | <span data-ttu-id="0fd23-206">SCID связанной рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="0fd23-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="0fd23-207">null</span><span class="sxs-lookup"><span data-stu-id="0fd23-207">null</span></span>
<span data-ttu-id="0fd23-208">status</span><span class="sxs-lookup"><span data-stu-id="0fd23-208">status</span></span> | <span data-ttu-id="0fd23-209">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-209">String</span></span> | <span data-ttu-id="0fd23-210">Состояние действия по исправлению (Active/Completed)</span><span class="sxs-lookup"><span data-stu-id="0fd23-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="0fd23-211">Активное</span><span class="sxs-lookup"><span data-stu-id="0fd23-211">Active</span></span>
<span data-ttu-id="0fd23-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="0fd23-212">statusLastModifiedOn</span></span> | <span data-ttu-id="0fd23-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="0fd23-213">DateTime</span></span> | <span data-ttu-id="0fd23-214">Дата обновления поля состояния</span><span class="sxs-lookup"><span data-stu-id="0fd23-214">Date when the status field was updated</span></span> | <span data-ttu-id="0fd23-215">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="0fd23-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="0fd23-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="0fd23-216">targetDevices</span></span> | <span data-ttu-id="0fd23-217">Длинное целое</span><span class="sxs-lookup"><span data-stu-id="0fd23-217">Long</span></span> | <span data-ttu-id="0fd23-218">Количество открытых устройств, к которые применяется это исправление</span><span class="sxs-lookup"><span data-stu-id="0fd23-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="0fd23-219">43</span><span class="sxs-lookup"><span data-stu-id="0fd23-219">43</span></span>
<span data-ttu-id="0fd23-220">title</span><span class="sxs-lookup"><span data-stu-id="0fd23-220">title</span></span> | <span data-ttu-id="0fd23-221">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-221">String</span></span> | <span data-ttu-id="0fd23-222">Название этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="0fd23-222">Title of this remediation activity</span></span> | <span data-ttu-id="0fd23-223">Обновление Google Chrome</span><span class="sxs-lookup"><span data-stu-id="0fd23-223">Update Google Chrome</span></span>
<span data-ttu-id="0fd23-224">type</span><span class="sxs-lookup"><span data-stu-id="0fd23-224">type</span></span> | <span data-ttu-id="0fd23-225">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-225">String</span></span> | <span data-ttu-id="0fd23-226">Тип устранения</span><span class="sxs-lookup"><span data-stu-id="0fd23-226">Remediation type</span></span> | <span data-ttu-id="0fd23-227">Update</span><span class="sxs-lookup"><span data-stu-id="0fd23-227">Update</span></span>
<span data-ttu-id="0fd23-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="0fd23-228">vendorId</span></span> | <span data-ttu-id="0fd23-229">String</span><span class="sxs-lookup"><span data-stu-id="0fd23-229">String</span></span> | <span data-ttu-id="0fd23-230">Имя связанного поставщика</span><span class="sxs-lookup"><span data-stu-id="0fd23-230">Related vendor name</span></span> | <span data-ttu-id="0fd23-231">Google</span><span class="sxs-lookup"><span data-stu-id="0fd23-231">google</span></span>

## <a name="example"></a><span data-ttu-id="0fd23-232">Пример</span><span class="sxs-lookup"><span data-stu-id="0fd23-232">Example</span></span>

<span data-ttu-id="0fd23-233">**Пример запроса**</span><span class="sxs-lookup"><span data-stu-id="0fd23-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="0fd23-234">**Пример ответа**</span><span class="sxs-lookup"><span data-stu-id="0fd23-234">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
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
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="0fd23-235">См. также</span><span class="sxs-lookup"><span data-stu-id="0fd23-235">See also</span></span>

- [<span data-ttu-id="0fd23-236">Методы и свойства по исправлению</span><span class="sxs-lookup"><span data-stu-id="0fd23-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="0fd23-237">Получить одно действие по исправлению по ID</span><span class="sxs-lookup"><span data-stu-id="0fd23-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="0fd23-238">Список выставленных устройств одного действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="0fd23-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="0fd23-239">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="0fd23-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="0fd23-240">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="0fd23-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
