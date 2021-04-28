---
title: Получить одно действие по исправлению по ID
description: Возвращает сведения для указанного действия по исправлению.
keywords: apis, remediation, remediation api, get, remediation tasks, list
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
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061167"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="cd138-104">Получить одно действие по исправлению по ID</span><span class="sxs-lookup"><span data-stu-id="cd138-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cd138-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cd138-105">**Applies to:**</span></span>

- [<span data-ttu-id="cd138-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cd138-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cd138-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd138-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cd138-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="cd138-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cd138-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="cd138-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="cd138-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="cd138-110">API description</span></span>

<span data-ttu-id="cd138-111">Возвращает сведения для указанного действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="cd138-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="cd138-112">Представляет те же столбцы, что [и "Получить](get-remediation-all-activities.md)все действия по исправлению", но возвращает результаты только для указанного действия по исправлению. </span><span class="sxs-lookup"><span data-stu-id="cd138-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="cd138-113">[Дополнительные информацию о действиях по исправлению.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="cd138-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="cd138-114">Список указанного действия по исправлению (id)</span><span class="sxs-lookup"><span data-stu-id="cd138-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="cd138-115">**URL-адрес:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="cd138-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="cd138-116">**Сведения о свойствах**</span><span class="sxs-lookup"><span data-stu-id="cd138-116">**Properties** details</span></span>

<span data-ttu-id="cd138-117">Свойство (id)</span><span class="sxs-lookup"><span data-stu-id="cd138-117">Property (id)</span></span> | <span data-ttu-id="cd138-118">Тип данных</span><span class="sxs-lookup"><span data-stu-id="cd138-118">Data type</span></span> | <span data-ttu-id="cd138-119">Описание</span><span class="sxs-lookup"><span data-stu-id="cd138-119">Description</span></span> | <span data-ttu-id="cd138-120">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="cd138-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="cd138-121">category</span><span class="sxs-lookup"><span data-stu-id="cd138-121">category</span></span> | <span data-ttu-id="cd138-122">String</span><span class="sxs-lookup"><span data-stu-id="cd138-122">String</span></span> | <span data-ttu-id="cd138-123">Категория действия по исправлению (конфигурация программного обеспечения и безопасности)</span><span class="sxs-lookup"><span data-stu-id="cd138-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="cd138-124">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="cd138-124">Software</span></span>
<span data-ttu-id="cd138-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="cd138-125">completerEmail</span></span> | <span data-ttu-id="cd138-126">String</span><span class="sxs-lookup"><span data-stu-id="cd138-126">String</span></span> | <span data-ttu-id="cd138-127">Если действие по исправлению было выполнено вручную кем-то, в этом столбце содержится их электронная почта.</span><span class="sxs-lookup"><span data-stu-id="cd138-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="cd138-128">null</span><span class="sxs-lookup"><span data-stu-id="cd138-128">null</span></span>
<span data-ttu-id="cd138-129">completerId</span><span class="sxs-lookup"><span data-stu-id="cd138-129">completerId</span></span> | <span data-ttu-id="cd138-130">String</span><span class="sxs-lookup"><span data-stu-id="cd138-130">String</span></span> | <span data-ttu-id="cd138-131">Если действие по исправлению было выполнено вручную кем-то, этот столбец содержит их объектный id</span><span class="sxs-lookup"><span data-stu-id="cd138-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="cd138-132">null</span><span class="sxs-lookup"><span data-stu-id="cd138-132">null</span></span>
<span data-ttu-id="cd138-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="cd138-133">completionMethod</span></span> | <span data-ttu-id="cd138-134">String</span><span class="sxs-lookup"><span data-stu-id="cd138-134">String</span></span> | <span data-ttu-id="cd138-135">Действие по исправлению может быть выполнено "автоматически" (если все устройства исправлены) или "вручную" человеком, который выбирает "метку как завершенную"</span><span class="sxs-lookup"><span data-stu-id="cd138-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="cd138-136">Автоматически</span><span class="sxs-lookup"><span data-stu-id="cd138-136">Automatic</span></span>
<span data-ttu-id="cd138-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="cd138-137">createdOn</span></span> | <span data-ttu-id="cd138-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="cd138-138">DateTime</span></span> | <span data-ttu-id="cd138-139">Время создания этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd138-139">Time this remediation activity was created</span></span> | <span data-ttu-id="cd138-140">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="cd138-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="cd138-141">description</span><span class="sxs-lookup"><span data-stu-id="cd138-141">description</span></span> | <span data-ttu-id="cd138-142">String</span><span class="sxs-lookup"><span data-stu-id="cd138-142">String</span></span> | <span data-ttu-id="cd138-143">Описание этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd138-143">Description of this remediation activity</span></span> | <span data-ttu-id="cd138-144">Обновите Chrome в более поздней версии, чтобы устранить 1248 известных уязвимостей, затрагивающих устройства.</span><span class="sxs-lookup"><span data-stu-id="cd138-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="cd138-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="cd138-145">dueOn</span></span> | <span data-ttu-id="cd138-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="cd138-146">DateTime</span></span> | <span data-ttu-id="cd138-147">Дата, установленная создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd138-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="cd138-148">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="cd138-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="cd138-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="cd138-149">fixedDevices</span></span> |  | <span data-ttu-id="cd138-150">Количество исправленных устройств</span><span class="sxs-lookup"><span data-stu-id="cd138-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="cd138-151">2</span><span class="sxs-lookup"><span data-stu-id="cd138-151">2</span></span>
<span data-ttu-id="cd138-152">id</span><span class="sxs-lookup"><span data-stu-id="cd138-152">id</span></span> | <span data-ttu-id="cd138-153">String</span><span class="sxs-lookup"><span data-stu-id="cd138-153">String</span></span> | <span data-ttu-id="cd138-154">ID этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd138-154">ID of this remediation activity</span></span> | <span data-ttu-id="cd138-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="cd138-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="cd138-156">nameId</span><span class="sxs-lookup"><span data-stu-id="cd138-156">nameId</span></span> | <span data-ttu-id="cd138-157">String</span><span class="sxs-lookup"><span data-stu-id="cd138-157">String</span></span> | <span data-ttu-id="cd138-158">Связанное имя продукта</span><span class="sxs-lookup"><span data-stu-id="cd138-158">Related product name</span></span> | <span data-ttu-id="cd138-159">chrome</span><span class="sxs-lookup"><span data-stu-id="cd138-159">chrome</span></span>
<span data-ttu-id="cd138-160">priority</span><span class="sxs-lookup"><span data-stu-id="cd138-160">priority</span></span> | <span data-ttu-id="cd138-161">String</span><span class="sxs-lookup"><span data-stu-id="cd138-161">String</span></span> | <span data-ttu-id="cd138-162">Приоритет, установленный создателем для этого действия по исправлению (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="cd138-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="cd138-163">Высокая</span><span class="sxs-lookup"><span data-stu-id="cd138-163">High</span></span>
<span data-ttu-id="cd138-164">productId</span><span class="sxs-lookup"><span data-stu-id="cd138-164">productId</span></span> | <span data-ttu-id="cd138-165">String</span><span class="sxs-lookup"><span data-stu-id="cd138-165">String</span></span> | <span data-ttu-id="cd138-166">Соответствующий ID продукта</span><span class="sxs-lookup"><span data-stu-id="cd138-166">Related product ID</span></span> | <span data-ttu-id="cd138-167">Google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="cd138-167">google-_-chrome</span></span>
<span data-ttu-id="cd138-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="cd138-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="cd138-169">String</span><span class="sxs-lookup"><span data-stu-id="cd138-169">String</span></span> | <span data-ttu-id="cd138-170">Несколько изменений конфигурации можно запросить только для устройств без влияния пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd138-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="cd138-171">Это значение указывает на выбор между "всеми выставленными устройствами" или "только устройствами без влияния пользователя".</span><span class="sxs-lookup"><span data-stu-id="cd138-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="cd138-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="cd138-172">AllExposedAssets</span></span>
<span data-ttu-id="cd138-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="cd138-173">rbacGroupNames</span></span> | <span data-ttu-id="cd138-174">String</span><span class="sxs-lookup"><span data-stu-id="cd138-174">String</span></span> | <span data-ttu-id="cd138-175">Связанные имена групп устройств</span><span class="sxs-lookup"><span data-stu-id="cd138-175">Related device group names</span></span> | <span data-ttu-id="cd138-176">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="cd138-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="cd138-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="cd138-177">recommendedProgram</span></span> | <span data-ttu-id="cd138-178">String</span><span class="sxs-lookup"><span data-stu-id="cd138-178">String</span></span> | <span data-ttu-id="cd138-179">Рекомендуемая программа для обновления до</span><span class="sxs-lookup"><span data-stu-id="cd138-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="cd138-180">null</span><span class="sxs-lookup"><span data-stu-id="cd138-180">null</span></span>
<span data-ttu-id="cd138-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="cd138-181">recommendedVendor</span></span> | <span data-ttu-id="cd138-182">String</span><span class="sxs-lookup"><span data-stu-id="cd138-182">String</span></span> | <span data-ttu-id="cd138-183">Рекомендуемый поставщик для обновления до</span><span class="sxs-lookup"><span data-stu-id="cd138-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="cd138-184">null</span><span class="sxs-lookup"><span data-stu-id="cd138-184">null</span></span>
<span data-ttu-id="cd138-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="cd138-185">recommendedVersion</span></span> | <span data-ttu-id="cd138-186">String</span><span class="sxs-lookup"><span data-stu-id="cd138-186">String</span></span> | <span data-ttu-id="cd138-187">Рекомендуемая версия для обновления и обновления до</span><span class="sxs-lookup"><span data-stu-id="cd138-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="cd138-188">null</span><span class="sxs-lookup"><span data-stu-id="cd138-188">null</span></span>
<span data-ttu-id="cd138-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="cd138-189">relatedComponent</span></span> | <span data-ttu-id="cd138-190">String</span><span class="sxs-lookup"><span data-stu-id="cd138-190">String</span></span> | <span data-ttu-id="cd138-191">Связанный компонент этого действия по исправлению (аналогичный связанному компоненту для рекомендации по безопасности)</span><span class="sxs-lookup"><span data-stu-id="cd138-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="cd138-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="cd138-192">Google Chrome</span></span>
<span data-ttu-id="cd138-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="cd138-193">requesterEmail</span></span> | <span data-ttu-id="cd138-194">String</span><span class="sxs-lookup"><span data-stu-id="cd138-194">String</span></span> | <span data-ttu-id="cd138-195">Адрес электронной почты создателя</span><span class="sxs-lookup"><span data-stu-id="cd138-195">Creator email address</span></span> | <span data-ttu-id="cd138-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cd138-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="cd138-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="cd138-197">requesterId</span></span> | <span data-ttu-id="cd138-198">String</span><span class="sxs-lookup"><span data-stu-id="cd138-198">String</span></span> | <span data-ttu-id="cd138-199">ID объекта Creator</span><span class="sxs-lookup"><span data-stu-id="cd138-199">Creator object id</span></span> | <span data-ttu-id="cd138-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="cd138-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="cd138-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="cd138-201">requesterNotes</span></span> | <span data-ttu-id="cd138-202">String</span><span class="sxs-lookup"><span data-stu-id="cd138-202">String</span></span> | <span data-ttu-id="cd138-203">Заметки (бесплатный текст), добавленные создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd138-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="cd138-204">null</span><span class="sxs-lookup"><span data-stu-id="cd138-204">null</span></span>
<span data-ttu-id="cd138-205">scid</span><span class="sxs-lookup"><span data-stu-id="cd138-205">scid</span></span> | <span data-ttu-id="cd138-206">String</span><span class="sxs-lookup"><span data-stu-id="cd138-206">String</span></span> | <span data-ttu-id="cd138-207">SCID связанной рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="cd138-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="cd138-208">null</span><span class="sxs-lookup"><span data-stu-id="cd138-208">null</span></span>
<span data-ttu-id="cd138-209">status</span><span class="sxs-lookup"><span data-stu-id="cd138-209">status</span></span> | <span data-ttu-id="cd138-210">String</span><span class="sxs-lookup"><span data-stu-id="cd138-210">String</span></span> | <span data-ttu-id="cd138-211">Состояние действия по исправлению (Active/Completed)</span><span class="sxs-lookup"><span data-stu-id="cd138-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="cd138-212">Активное</span><span class="sxs-lookup"><span data-stu-id="cd138-212">Active</span></span>
<span data-ttu-id="cd138-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="cd138-213">statusLastModifiedOn</span></span> | <span data-ttu-id="cd138-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="cd138-214">DateTime</span></span> | <span data-ttu-id="cd138-215">Дата обновления поля состояния</span><span class="sxs-lookup"><span data-stu-id="cd138-215">Date when the status field was updated</span></span> | <span data-ttu-id="cd138-216">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="cd138-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="cd138-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="cd138-217">targetDevices</span></span> | <span data-ttu-id="cd138-218">Длинное целое</span><span class="sxs-lookup"><span data-stu-id="cd138-218">Long</span></span> | <span data-ttu-id="cd138-219">Количество открытых устройств, к которые применяется это исправление</span><span class="sxs-lookup"><span data-stu-id="cd138-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="cd138-220">43</span><span class="sxs-lookup"><span data-stu-id="cd138-220">43</span></span>
<span data-ttu-id="cd138-221">title</span><span class="sxs-lookup"><span data-stu-id="cd138-221">title</span></span> | <span data-ttu-id="cd138-222">String</span><span class="sxs-lookup"><span data-stu-id="cd138-222">String</span></span> | <span data-ttu-id="cd138-223">Название этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd138-223">Title of this remediation activity</span></span> | <span data-ttu-id="cd138-224">Обновление Google Chrome</span><span class="sxs-lookup"><span data-stu-id="cd138-224">Update Google Chrome</span></span>
<span data-ttu-id="cd138-225">type</span><span class="sxs-lookup"><span data-stu-id="cd138-225">type</span></span> | <span data-ttu-id="cd138-226">String</span><span class="sxs-lookup"><span data-stu-id="cd138-226">String</span></span> | <span data-ttu-id="cd138-227">Тип устранения</span><span class="sxs-lookup"><span data-stu-id="cd138-227">Remediation type</span></span> | <span data-ttu-id="cd138-228">Update</span><span class="sxs-lookup"><span data-stu-id="cd138-228">Update</span></span>
<span data-ttu-id="cd138-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="cd138-229">vendorId</span></span> | <span data-ttu-id="cd138-230">String</span><span class="sxs-lookup"><span data-stu-id="cd138-230">String</span></span> | <span data-ttu-id="cd138-231">Имя связанного поставщика</span><span class="sxs-lookup"><span data-stu-id="cd138-231">Related vendor name</span></span> | <span data-ttu-id="cd138-232">Google</span><span class="sxs-lookup"><span data-stu-id="cd138-232">google</span></span>

## <a name="example"></a><span data-ttu-id="cd138-233">Пример</span><span class="sxs-lookup"><span data-stu-id="cd138-233">Example</span></span>

<span data-ttu-id="cd138-234">**Пример запроса**</span><span class="sxs-lookup"><span data-stu-id="cd138-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="cd138-235">**Пример ответа**</span><span class="sxs-lookup"><span data-stu-id="cd138-235">**Response** example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cd138-236">См. также</span><span class="sxs-lookup"><span data-stu-id="cd138-236">See also</span></span>

- [<span data-ttu-id="cd138-237">Методы и свойства по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd138-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="cd138-238">Список всех действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd138-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="cd138-239">Список выставленных устройств одного действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd138-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="cd138-240">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="cd138-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="cd138-241">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="cd138-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
