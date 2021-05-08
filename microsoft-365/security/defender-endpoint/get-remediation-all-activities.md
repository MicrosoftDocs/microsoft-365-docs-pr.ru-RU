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
ms.technology: mde
ms.openlocfilehash: cf7c79cb6cc76af88ce0293a013ba6edbf435d8c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245496"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="87cb4-104">Перечисление всех действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="87cb4-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="87cb4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="87cb4-105">**Applies to:**</span></span>

- [<span data-ttu-id="87cb4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="87cb4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="87cb4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87cb4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="87cb4-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="87cb4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="87cb4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="87cb4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="87cb4-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="87cb4-110">API description</span></span>

<span data-ttu-id="87cb4-111">Возвращает сведения обо всех действиях по исправлению.</span><span class="sxs-lookup"><span data-stu-id="87cb4-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="87cb4-112">[Дополнительные информацию о действиях по исправлению.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="87cb4-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="87cb4-113">**URL-адрес:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="87cb4-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="87cb4-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="87cb4-114">Permissions</span></span>

<span data-ttu-id="87cb4-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="87cb4-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="87cb4-116">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="87cb4-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="87cb4-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="87cb4-117">Permission type</span></span> | <span data-ttu-id="87cb4-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="87cb4-118">Permission</span></span> | <span data-ttu-id="87cb4-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="87cb4-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="87cb4-120">Для приложений</span><span class="sxs-lookup"><span data-stu-id="87cb4-120">Application</span></span> | <span data-ttu-id="87cb4-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="87cb4-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="87cb4-122">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="87cb4-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="87cb4-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="87cb4-123">Delegated (work or school account)</span></span> | <span data-ttu-id="87cb4-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="87cb4-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="87cb4-125">\'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'</span><span class="sxs-lookup"><span data-stu-id="87cb4-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="87cb4-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="87cb4-126">Properties</span></span>

<span data-ttu-id="87cb4-127">Свойство (id)</span><span class="sxs-lookup"><span data-stu-id="87cb4-127">Property (id)</span></span> | <span data-ttu-id="87cb4-128">Тип данных</span><span class="sxs-lookup"><span data-stu-id="87cb4-128">Data type</span></span> | <span data-ttu-id="87cb4-129">Описание</span><span class="sxs-lookup"><span data-stu-id="87cb4-129">Description</span></span> | <span data-ttu-id="87cb4-130">Пример возвращенного значения</span><span class="sxs-lookup"><span data-stu-id="87cb4-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="87cb4-131">category</span><span class="sxs-lookup"><span data-stu-id="87cb4-131">category</span></span> | <span data-ttu-id="87cb4-132">String</span><span class="sxs-lookup"><span data-stu-id="87cb4-132">String</span></span> | <span data-ttu-id="87cb4-133">Категория действия по исправлению (конфигурация программного обеспечения и безопасности)</span><span class="sxs-lookup"><span data-stu-id="87cb4-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="87cb4-134">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="87cb4-134">Software</span></span>
<span data-ttu-id="87cb4-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="87cb4-135">completerEmail</span></span> | <span data-ttu-id="87cb4-136">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-136">String</span></span> | <span data-ttu-id="87cb4-137">Если действие по исправлению было выполнено вручную кем-то, в этом столбце содержится их электронная почта.</span><span class="sxs-lookup"><span data-stu-id="87cb4-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="87cb4-138">null</span><span class="sxs-lookup"><span data-stu-id="87cb4-138">null</span></span>
<span data-ttu-id="87cb4-139">completerId</span><span class="sxs-lookup"><span data-stu-id="87cb4-139">completerId</span></span> | <span data-ttu-id="87cb4-140">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-140">String</span></span> | <span data-ttu-id="87cb4-141">Если действие по исправлению было выполнено вручную кем-то, этот столбец содержит их объектный id</span><span class="sxs-lookup"><span data-stu-id="87cb4-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="87cb4-142">null</span><span class="sxs-lookup"><span data-stu-id="87cb4-142">null</span></span>
<span data-ttu-id="87cb4-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="87cb4-143">completionMethod</span></span> | <span data-ttu-id="87cb4-144">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-144">String</span></span> | <span data-ttu-id="87cb4-145">Действие по исправлению может быть выполнено "автоматически" (если все устройства исправлены) или "вручную" человеком, который выбирает "метку как завершенную"</span><span class="sxs-lookup"><span data-stu-id="87cb4-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="87cb4-146">Автоматически</span><span class="sxs-lookup"><span data-stu-id="87cb4-146">Automatic</span></span>
<span data-ttu-id="87cb4-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="87cb4-147">createdOn</span></span> | <span data-ttu-id="87cb4-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="87cb4-148">DateTime</span></span> | <span data-ttu-id="87cb4-149">Время создания этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="87cb4-149">Time this remediation activity was created</span></span> | <span data-ttu-id="87cb4-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="87cb4-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="87cb4-151">description</span><span class="sxs-lookup"><span data-stu-id="87cb4-151">description</span></span> | <span data-ttu-id="87cb4-152">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-152">String</span></span> | <span data-ttu-id="87cb4-153">Описание этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="87cb4-153">Description of this remediation activity</span></span> | <span data-ttu-id="87cb4-154">Обновите Microsoft Silverlight в более поздней версии, чтобы устранить известные уязвимости, влияющие на устройства.</span><span class="sxs-lookup"><span data-stu-id="87cb4-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="87cb4-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="87cb4-155">dueOn</span></span> | <span data-ttu-id="87cb4-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="87cb4-156">DateTime</span></span> | <span data-ttu-id="87cb4-157">Дата, установленная создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="87cb4-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="87cb4-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="87cb4-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="87cb4-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="87cb4-159">fixedDevices</span></span> | <span data-ttu-id="87cb4-160">.</span><span class="sxs-lookup"><span data-stu-id="87cb4-160">.</span></span> | <span data-ttu-id="87cb4-161">Количество исправленных устройств</span><span class="sxs-lookup"><span data-stu-id="87cb4-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="87cb4-162">2</span><span class="sxs-lookup"><span data-stu-id="87cb4-162">2</span></span>
<span data-ttu-id="87cb4-163">id</span><span class="sxs-lookup"><span data-stu-id="87cb4-163">id</span></span> | <span data-ttu-id="87cb4-164">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-164">String</span></span> | <span data-ttu-id="87cb4-165">ID этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="87cb4-165">ID of this remediation activity</span></span> | <span data-ttu-id="87cb4-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="87cb4-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="87cb4-167">nameId</span><span class="sxs-lookup"><span data-stu-id="87cb4-167">nameId</span></span> | <span data-ttu-id="87cb4-168">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-168">String</span></span> | <span data-ttu-id="87cb4-169">Связанное имя продукта</span><span class="sxs-lookup"><span data-stu-id="87cb4-169">Related product name</span></span> | <span data-ttu-id="87cb4-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="87cb4-170">Microsoft Silverlight</span></span>
<span data-ttu-id="87cb4-171">priority</span><span class="sxs-lookup"><span data-stu-id="87cb4-171">priority</span></span> | <span data-ttu-id="87cb4-172">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-172">String</span></span> | <span data-ttu-id="87cb4-173">Приоритет, установленный создателем для этого действия по исправлению (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="87cb4-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="87cb4-174">Высокий</span><span class="sxs-lookup"><span data-stu-id="87cb4-174">High</span></span>
<span data-ttu-id="87cb4-175">productId</span><span class="sxs-lookup"><span data-stu-id="87cb4-175">productId</span></span> | <span data-ttu-id="87cb4-176">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-176">String</span></span> | <span data-ttu-id="87cb4-177">Соответствующий ID продукта</span><span class="sxs-lookup"><span data-stu-id="87cb4-177">Related product ID</span></span> | <span data-ttu-id="87cb4-178">microsoft-__-silverlight</span><span class="sxs-lookup"><span data-stu-id="87cb4-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="87cb4-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="87cb4-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="87cb4-180">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-180">String</span></span> | <span data-ttu-id="87cb4-181">Несколько изменений конфигурации можно запросить только для устройств без влияния пользователя.</span><span class="sxs-lookup"><span data-stu-id="87cb4-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="87cb4-182">Это значение указывает на выбор между "всеми выставленными устройствами" или "только устройствами без влияния пользователя".</span><span class="sxs-lookup"><span data-stu-id="87cb4-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="87cb4-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="87cb4-183">AllExposedAssets</span></span>
<span data-ttu-id="87cb4-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="87cb4-184">rbacGroupNames</span></span> | <span data-ttu-id="87cb4-185">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-185">String</span></span> | <span data-ttu-id="87cb4-186">Связанные имена групп устройств</span><span class="sxs-lookup"><span data-stu-id="87cb4-186">Related device group names</span></span> | <span data-ttu-id="87cb4-187">[ "Windows Серверы", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="87cb4-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="87cb4-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="87cb4-188">recommendedProgram</span></span> | <span data-ttu-id="87cb4-189">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-189">String</span></span> | <span data-ttu-id="87cb4-190">Рекомендуемая программа для обновления до</span><span class="sxs-lookup"><span data-stu-id="87cb4-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="87cb4-191">null</span><span class="sxs-lookup"><span data-stu-id="87cb4-191">null</span></span>
<span data-ttu-id="87cb4-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="87cb4-192">recommendedVendor</span></span> | <span data-ttu-id="87cb4-193">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-193">String</span></span> | <span data-ttu-id="87cb4-194">Рекомендуемый поставщик для обновления до</span><span class="sxs-lookup"><span data-stu-id="87cb4-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="87cb4-195">null</span><span class="sxs-lookup"><span data-stu-id="87cb4-195">null</span></span>
<span data-ttu-id="87cb4-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="87cb4-196">recommendedVersion</span></span> | <span data-ttu-id="87cb4-197">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-197">String</span></span> | <span data-ttu-id="87cb4-198">Рекомендуемая версия для обновления и обновления до</span><span class="sxs-lookup"><span data-stu-id="87cb4-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="87cb4-199">null</span><span class="sxs-lookup"><span data-stu-id="87cb4-199">null</span></span>
<span data-ttu-id="87cb4-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="87cb4-200">relatedComponent</span></span> | <span data-ttu-id="87cb4-201">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-201">String</span></span> | <span data-ttu-id="87cb4-202">Связанный компонент этого действия по исправлению (аналогичный связанному компоненту для рекомендации по безопасности)</span><span class="sxs-lookup"><span data-stu-id="87cb4-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="87cb4-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="87cb4-203">Microsoft Silverlight</span></span>
<span data-ttu-id="87cb4-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="87cb4-204">requesterEmail</span></span> | <span data-ttu-id="87cb4-205">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-205">String</span></span> | <span data-ttu-id="87cb4-206">Адрес электронной почты создателя</span><span class="sxs-lookup"><span data-stu-id="87cb4-206">Creator email address</span></span> | <span data-ttu-id="87cb4-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="87cb4-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="87cb4-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="87cb4-208">requesterId</span></span> | <span data-ttu-id="87cb4-209">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-209">String</span></span> | <span data-ttu-id="87cb4-210">ID объекта Creator</span><span class="sxs-lookup"><span data-stu-id="87cb4-210">Creator object id</span></span> | <span data-ttu-id="87cb4-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="87cb4-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="87cb4-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="87cb4-212">requesterNotes</span></span> | <span data-ttu-id="87cb4-213">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-213">String</span></span> | <span data-ttu-id="87cb4-214">Заметки (бесплатный текст), добавленные создателем для этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="87cb4-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="87cb4-215">null</span><span class="sxs-lookup"><span data-stu-id="87cb4-215">null</span></span>
<span data-ttu-id="87cb4-216">scid</span><span class="sxs-lookup"><span data-stu-id="87cb4-216">scid</span></span> | <span data-ttu-id="87cb4-217">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-217">String</span></span> | <span data-ttu-id="87cb4-218">SCID связанной рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="87cb4-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="87cb4-219">null</span><span class="sxs-lookup"><span data-stu-id="87cb4-219">null</span></span>
<span data-ttu-id="87cb4-220">status</span><span class="sxs-lookup"><span data-stu-id="87cb4-220">status</span></span> | <span data-ttu-id="87cb4-221">String</span><span class="sxs-lookup"><span data-stu-id="87cb4-221">String</span></span> | <span data-ttu-id="87cb4-222">Состояние действия по исправлению (Active/Completed)</span><span class="sxs-lookup"><span data-stu-id="87cb4-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="87cb4-223">Активное</span><span class="sxs-lookup"><span data-stu-id="87cb4-223">Active</span></span>
<span data-ttu-id="87cb4-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="87cb4-224">statusLastModifiedOn</span></span> | <span data-ttu-id="87cb4-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="87cb4-225">DateTime</span></span> | <span data-ttu-id="87cb4-226">Дата обновления поля состояния</span><span class="sxs-lookup"><span data-stu-id="87cb4-226">Date when the status field was updated</span></span> | <span data-ttu-id="87cb4-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="87cb4-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="87cb4-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="87cb4-228">targetDevices</span></span> | <span data-ttu-id="87cb4-229">Длинное целое</span><span class="sxs-lookup"><span data-stu-id="87cb4-229">Long</span></span> | <span data-ttu-id="87cb4-230">Количество открытых устройств, к которые применяется это исправление</span><span class="sxs-lookup"><span data-stu-id="87cb4-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="87cb4-231">43</span><span class="sxs-lookup"><span data-stu-id="87cb4-231">43</span></span>
<span data-ttu-id="87cb4-232">title</span><span class="sxs-lookup"><span data-stu-id="87cb4-232">title</span></span> | <span data-ttu-id="87cb4-233">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-233">String</span></span> | <span data-ttu-id="87cb4-234">Название этого действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="87cb4-234">Title of this remediation activity</span></span> | <span data-ttu-id="87cb4-235">Обновление Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="87cb4-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="87cb4-236">type</span><span class="sxs-lookup"><span data-stu-id="87cb4-236">type</span></span> | <span data-ttu-id="87cb4-237">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-237">String</span></span> | <span data-ttu-id="87cb4-238">Тип устранения</span><span class="sxs-lookup"><span data-stu-id="87cb4-238">Remediation type</span></span> | <span data-ttu-id="87cb4-239">Update</span><span class="sxs-lookup"><span data-stu-id="87cb4-239">Update</span></span>
<span data-ttu-id="87cb4-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="87cb4-240">vendorId</span></span> | <span data-ttu-id="87cb4-241">Строка</span><span class="sxs-lookup"><span data-stu-id="87cb4-241">String</span></span> | <span data-ttu-id="87cb4-242">Имя связанного поставщика</span><span class="sxs-lookup"><span data-stu-id="87cb4-242">Related vendor name</span></span> | <span data-ttu-id="87cb4-243">Корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="87cb4-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="87cb4-244">Пример</span><span class="sxs-lookup"><span data-stu-id="87cb4-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="87cb4-245">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="87cb4-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="87cb4-246">Пример ответа</span><span class="sxs-lookup"><span data-stu-id="87cb4-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="87cb4-247">См. также</span><span class="sxs-lookup"><span data-stu-id="87cb4-247">See also</span></span>

- [<span data-ttu-id="87cb4-248">Методы и свойства по исправлению</span><span class="sxs-lookup"><span data-stu-id="87cb4-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="87cb4-249">Получение одного действия по исправлению по ИД</span><span class="sxs-lookup"><span data-stu-id="87cb4-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="87cb4-250">Перечисление устройств, затрагиваемых одним действием по исправлению</span><span class="sxs-lookup"><span data-stu-id="87cb4-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="87cb4-251">Риск на основе угрозы & управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="87cb4-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="87cb4-252">Уязвимости в организации</span><span class="sxs-lookup"><span data-stu-id="87cb4-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
