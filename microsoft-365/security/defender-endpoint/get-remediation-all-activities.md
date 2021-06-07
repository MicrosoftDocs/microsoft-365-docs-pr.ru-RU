---
title: Перечисление всех действий по исправлению
description: Возвращает сведения обо всех действиях по исправлению.
keywords: apis, remediation, remediation api, get, remediation tasks, all remediation,
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
ms.openlocfilehash: b95fa2da177a3ecb93bcf3e2085be6111c2c641e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770521"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="9a353-104">Перечисление всех действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a353-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9a353-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9a353-105">**Applies to:**</span></span>

- [<span data-ttu-id="9a353-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9a353-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9a353-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a353-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9a353-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9a353-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9a353-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9a353-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="9a353-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="9a353-110">API description</span></span>

<span data-ttu-id="9a353-111">Возвращает сведения обо всех действиях по исправлению.</span><span class="sxs-lookup"><span data-stu-id="9a353-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="9a353-112">[Дополнительные информацию о действиях по исправлению.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="9a353-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="9a353-113">**URL-адрес:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="9a353-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="9a353-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="9a353-114">Permissions</span></span>

<span data-ttu-id="9a353-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="9a353-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9a353-116">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9a353-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="9a353-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="9a353-117">Permission type</span></span> | <span data-ttu-id="9a353-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="9a353-118">Permission</span></span> | <span data-ttu-id="9a353-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="9a353-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9a353-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="9a353-120">Application</span></span> | <span data-ttu-id="9a353-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="9a353-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="9a353-122">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="9a353-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="9a353-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="9a353-123">Delegated (work or school account)</span></span> | <span data-ttu-id="9a353-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="9a353-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="9a353-125">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="9a353-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="9a353-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="9a353-126">Properties</span></span>

<span data-ttu-id="9a353-127">Свойство (id)</span><span class="sxs-lookup"><span data-stu-id="9a353-127">Property (id)</span></span> | <span data-ttu-id="9a353-128">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9a353-128">Data type</span></span> | <span data-ttu-id="9a353-129">Описание</span><span class="sxs-lookup"><span data-stu-id="9a353-129">Description</span></span> | <span data-ttu-id="9a353-130">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="9a353-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="9a353-131">category</span><span class="sxs-lookup"><span data-stu-id="9a353-131">category</span></span> | <span data-ttu-id="9a353-132">String</span><span class="sxs-lookup"><span data-stu-id="9a353-132">String</span></span> | <span data-ttu-id="9a353-133">Категория действия по исправлению (конфигурация программного обеспечения и безопасности)</span><span class="sxs-lookup"><span data-stu-id="9a353-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="9a353-134">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="9a353-134">Software</span></span>
<span data-ttu-id="9a353-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="9a353-135">completerEmail</span></span> | <span data-ttu-id="9a353-136">String</span><span class="sxs-lookup"><span data-stu-id="9a353-136">String</span></span> | <span data-ttu-id="9a353-137">Если действие по исправлению было выполнено вручную кем-то, в этом столбце содержится их электронная почта.</span><span class="sxs-lookup"><span data-stu-id="9a353-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="9a353-138">null</span><span class="sxs-lookup"><span data-stu-id="9a353-138">null</span></span>
<span data-ttu-id="9a353-139">completerId</span><span class="sxs-lookup"><span data-stu-id="9a353-139">completerId</span></span> | <span data-ttu-id="9a353-140">String</span><span class="sxs-lookup"><span data-stu-id="9a353-140">String</span></span> | <span data-ttu-id="9a353-141">Если действие по исправлению было выполнено вручную кем-то, этот столбец содержит их объектный id</span><span class="sxs-lookup"><span data-stu-id="9a353-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="9a353-142">null</span><span class="sxs-lookup"><span data-stu-id="9a353-142">null</span></span>
<span data-ttu-id="9a353-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="9a353-143">completionMethod</span></span> | <span data-ttu-id="9a353-144">String</span><span class="sxs-lookup"><span data-stu-id="9a353-144">String</span></span> | <span data-ttu-id="9a353-145">Действие по исправлению может быть выполнено "автоматически" (если все устройства исправлены) или "вручную" человеком, который выбирает "метку как завершенную"</span><span class="sxs-lookup"><span data-stu-id="9a353-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="9a353-146">Автоматически</span><span class="sxs-lookup"><span data-stu-id="9a353-146">Automatic</span></span>
<span data-ttu-id="9a353-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="9a353-147">createdOn</span></span> | <span data-ttu-id="9a353-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="9a353-148">DateTime</span></span> | <span data-ttu-id="9a353-149">Время создания этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a353-149">Time this remediation activity was created</span></span> | <span data-ttu-id="9a353-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="9a353-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="9a353-151">description</span><span class="sxs-lookup"><span data-stu-id="9a353-151">description</span></span> | <span data-ttu-id="9a353-152">String</span><span class="sxs-lookup"><span data-stu-id="9a353-152">String</span></span> | <span data-ttu-id="9a353-153">Описание этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a353-153">Description of this remediation activity</span></span> | <span data-ttu-id="9a353-154">Обновите Microsoft Silverlight в более поздней версии, чтобы устранить известные уязвимости, влияющие на устройства.</span><span class="sxs-lookup"><span data-stu-id="9a353-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="9a353-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="9a353-155">dueOn</span></span> | <span data-ttu-id="9a353-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="9a353-156">DateTime</span></span> | <span data-ttu-id="9a353-157">Дата, установленная создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a353-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="9a353-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="9a353-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="9a353-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="9a353-159">fixedDevices</span></span> | <span data-ttu-id="9a353-160">.</span><span class="sxs-lookup"><span data-stu-id="9a353-160">.</span></span> | <span data-ttu-id="9a353-161">Количество исправленных устройств</span><span class="sxs-lookup"><span data-stu-id="9a353-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="9a353-162">2</span><span class="sxs-lookup"><span data-stu-id="9a353-162">2</span></span>
<span data-ttu-id="9a353-163">id</span><span class="sxs-lookup"><span data-stu-id="9a353-163">id</span></span> | <span data-ttu-id="9a353-164">String</span><span class="sxs-lookup"><span data-stu-id="9a353-164">String</span></span> | <span data-ttu-id="9a353-165">ID этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a353-165">ID of this remediation activity</span></span> | <span data-ttu-id="9a353-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="9a353-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="9a353-167">nameId</span><span class="sxs-lookup"><span data-stu-id="9a353-167">nameId</span></span> | <span data-ttu-id="9a353-168">String</span><span class="sxs-lookup"><span data-stu-id="9a353-168">String</span></span> | <span data-ttu-id="9a353-169">Связанное имя продукта</span><span class="sxs-lookup"><span data-stu-id="9a353-169">Related product name</span></span> | <span data-ttu-id="9a353-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="9a353-170">Microsoft Silverlight</span></span>
<span data-ttu-id="9a353-171">priority</span><span class="sxs-lookup"><span data-stu-id="9a353-171">priority</span></span> | <span data-ttu-id="9a353-172">String</span><span class="sxs-lookup"><span data-stu-id="9a353-172">String</span></span> | <span data-ttu-id="9a353-173">Приоритет, установленный создателем для этого действия по исправлению (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="9a353-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="9a353-174">Высокие</span><span class="sxs-lookup"><span data-stu-id="9a353-174">High</span></span>
<span data-ttu-id="9a353-175">productId</span><span class="sxs-lookup"><span data-stu-id="9a353-175">productId</span></span> | <span data-ttu-id="9a353-176">String</span><span class="sxs-lookup"><span data-stu-id="9a353-176">String</span></span> | <span data-ttu-id="9a353-177">Соответствующий ID продукта</span><span class="sxs-lookup"><span data-stu-id="9a353-177">Related product ID</span></span> | <span data-ttu-id="9a353-178">microsoft-__-silverlight</span><span class="sxs-lookup"><span data-stu-id="9a353-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="9a353-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="9a353-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="9a353-180">String</span><span class="sxs-lookup"><span data-stu-id="9a353-180">String</span></span> | <span data-ttu-id="9a353-181">Несколько изменений конфигурации можно запросить только для устройств без влияния пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a353-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="9a353-182">Это значение указывает на выбор между "всеми выставленными устройствами" или "только устройствами без влияния пользователя".</span><span class="sxs-lookup"><span data-stu-id="9a353-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="9a353-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="9a353-183">AllExposedAssets</span></span>
<span data-ttu-id="9a353-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="9a353-184">rbacGroupNames</span></span> | <span data-ttu-id="9a353-185">String</span><span class="sxs-lookup"><span data-stu-id="9a353-185">String</span></span> | <span data-ttu-id="9a353-186">Связанные имена групп устройств</span><span class="sxs-lookup"><span data-stu-id="9a353-186">Related device group names</span></span> | <span data-ttu-id="9a353-187">[ "Windows Серверы", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="9a353-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="9a353-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="9a353-188">recommendedProgram</span></span> | <span data-ttu-id="9a353-189">String</span><span class="sxs-lookup"><span data-stu-id="9a353-189">String</span></span> | <span data-ttu-id="9a353-190">Рекомендуемая программа для обновления до</span><span class="sxs-lookup"><span data-stu-id="9a353-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="9a353-191">null</span><span class="sxs-lookup"><span data-stu-id="9a353-191">null</span></span>
<span data-ttu-id="9a353-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="9a353-192">recommendedVendor</span></span> | <span data-ttu-id="9a353-193">String</span><span class="sxs-lookup"><span data-stu-id="9a353-193">String</span></span> | <span data-ttu-id="9a353-194">Рекомендуемый поставщик для обновления до</span><span class="sxs-lookup"><span data-stu-id="9a353-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="9a353-195">null</span><span class="sxs-lookup"><span data-stu-id="9a353-195">null</span></span>
<span data-ttu-id="9a353-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="9a353-196">recommendedVersion</span></span> | <span data-ttu-id="9a353-197">String</span><span class="sxs-lookup"><span data-stu-id="9a353-197">String</span></span> | <span data-ttu-id="9a353-198">Рекомендуемая версия для обновления и обновления до</span><span class="sxs-lookup"><span data-stu-id="9a353-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="9a353-199">null</span><span class="sxs-lookup"><span data-stu-id="9a353-199">null</span></span>
<span data-ttu-id="9a353-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="9a353-200">relatedComponent</span></span> | <span data-ttu-id="9a353-201">String</span><span class="sxs-lookup"><span data-stu-id="9a353-201">String</span></span> | <span data-ttu-id="9a353-202">Связанный компонент этого действия по исправлению (аналогичный связанному компоненту для рекомендации по безопасности)</span><span class="sxs-lookup"><span data-stu-id="9a353-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="9a353-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="9a353-203">Microsoft Silverlight</span></span>
<span data-ttu-id="9a353-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="9a353-204">requesterEmail</span></span> | <span data-ttu-id="9a353-205">String</span><span class="sxs-lookup"><span data-stu-id="9a353-205">String</span></span> | <span data-ttu-id="9a353-206">Адрес электронной почты создателя</span><span class="sxs-lookup"><span data-stu-id="9a353-206">Creator email address</span></span> | <span data-ttu-id="9a353-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a353-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="9a353-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="9a353-208">requesterId</span></span> | <span data-ttu-id="9a353-209">String</span><span class="sxs-lookup"><span data-stu-id="9a353-209">String</span></span> | <span data-ttu-id="9a353-210">ID объекта Creator</span><span class="sxs-lookup"><span data-stu-id="9a353-210">Creator object id</span></span> | <span data-ttu-id="9a353-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="9a353-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="9a353-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="9a353-212">requesterNotes</span></span> | <span data-ttu-id="9a353-213">String</span><span class="sxs-lookup"><span data-stu-id="9a353-213">String</span></span> | <span data-ttu-id="9a353-214">Заметки (бесплатный текст), добавленные создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a353-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="9a353-215">null</span><span class="sxs-lookup"><span data-stu-id="9a353-215">null</span></span>
<span data-ttu-id="9a353-216">scid</span><span class="sxs-lookup"><span data-stu-id="9a353-216">scid</span></span> | <span data-ttu-id="9a353-217">String</span><span class="sxs-lookup"><span data-stu-id="9a353-217">String</span></span> | <span data-ttu-id="9a353-218">SCID связанной рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="9a353-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="9a353-219">null</span><span class="sxs-lookup"><span data-stu-id="9a353-219">null</span></span>
<span data-ttu-id="9a353-220">status</span><span class="sxs-lookup"><span data-stu-id="9a353-220">status</span></span> | <span data-ttu-id="9a353-221">String</span><span class="sxs-lookup"><span data-stu-id="9a353-221">String</span></span> | <span data-ttu-id="9a353-222">Состояние действия по исправлению (Active/Completed)</span><span class="sxs-lookup"><span data-stu-id="9a353-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="9a353-223">Активна</span><span class="sxs-lookup"><span data-stu-id="9a353-223">Active</span></span>
<span data-ttu-id="9a353-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="9a353-224">statusLastModifiedOn</span></span> | <span data-ttu-id="9a353-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="9a353-225">DateTime</span></span> | <span data-ttu-id="9a353-226">Дата обновления поля состояния</span><span class="sxs-lookup"><span data-stu-id="9a353-226">Date when the status field was updated</span></span> | <span data-ttu-id="9a353-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="9a353-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="9a353-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="9a353-228">targetDevices</span></span> | <span data-ttu-id="9a353-229">Длинное целое</span><span class="sxs-lookup"><span data-stu-id="9a353-229">Long</span></span> | <span data-ttu-id="9a353-230">Количество открытых устройств, к которые применяется это исправление</span><span class="sxs-lookup"><span data-stu-id="9a353-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="9a353-231">43</span><span class="sxs-lookup"><span data-stu-id="9a353-231">43</span></span>
<span data-ttu-id="9a353-232">title</span><span class="sxs-lookup"><span data-stu-id="9a353-232">title</span></span> | <span data-ttu-id="9a353-233">String</span><span class="sxs-lookup"><span data-stu-id="9a353-233">String</span></span> | <span data-ttu-id="9a353-234">Название этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a353-234">Title of this remediation activity</span></span> | <span data-ttu-id="9a353-235">Обновление Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="9a353-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="9a353-236">type</span><span class="sxs-lookup"><span data-stu-id="9a353-236">type</span></span> | <span data-ttu-id="9a353-237">String</span><span class="sxs-lookup"><span data-stu-id="9a353-237">String</span></span> | <span data-ttu-id="9a353-238">Тип устранения</span><span class="sxs-lookup"><span data-stu-id="9a353-238">Remediation type</span></span> | <span data-ttu-id="9a353-239">Update</span><span class="sxs-lookup"><span data-stu-id="9a353-239">Update</span></span>
<span data-ttu-id="9a353-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="9a353-240">vendorId</span></span> | <span data-ttu-id="9a353-241">String</span><span class="sxs-lookup"><span data-stu-id="9a353-241">String</span></span> | <span data-ttu-id="9a353-242">Имя связанного поставщика</span><span class="sxs-lookup"><span data-stu-id="9a353-242">Related vendor name</span></span> | <span data-ttu-id="9a353-243">Корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9a353-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="9a353-244">Пример</span><span class="sxs-lookup"><span data-stu-id="9a353-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="9a353-245">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="9a353-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="9a353-246">Пример ответа</span><span class="sxs-lookup"><span data-stu-id="9a353-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9a353-247">См. также</span><span class="sxs-lookup"><span data-stu-id="9a353-247">See also</span></span>

- [<span data-ttu-id="9a353-248">Методы и свойства по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a353-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="9a353-249">Получение одного действия по исправлению по ИД</span><span class="sxs-lookup"><span data-stu-id="9a353-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="9a353-250">Перечисление устройств, затрагиваемых одним действием по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a353-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="9a353-251">Риск на основе угрозы & управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="9a353-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="9a353-252">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="9a353-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
