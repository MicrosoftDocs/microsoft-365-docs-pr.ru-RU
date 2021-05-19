---
title: Действия с метками, указываемые в обозревателе действий
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: перечисление действий по маркировке, доступных в проводнике действий.
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532258"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="218f7-103">Действия по маркировке, доступные в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="218f7-104">Метка "Чувствительность", примененная</span><span class="sxs-lookup"><span data-stu-id="218f7-104">Sensitivity label applied</span></span>

<span data-ttu-id="218f7-105">Это событие создается каждый раз, когда не помечен документ или отправляется сообщение электронной почты с меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="218f7-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="218f7-106">Оно фиксируется во время сохранения в Office и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="218f7-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="218f7-107">Она фиксируется во время появления в надстройки для защиты информации Azure.</span><span class="sxs-lookup"><span data-stu-id="218f7-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="218f7-108">Действия по обновлению и понижению меток также можно отслеживать с помощью поля типа событий *Label* и фильтра.</span><span class="sxs-lookup"><span data-stu-id="218f7-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="218f7-109">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-109">Source</span></span>  |<span data-ttu-id="218f7-110">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-110">Reported in activity explorer</span></span> | <span data-ttu-id="218f7-111">Примечание</span><span class="sxs-lookup"><span data-stu-id="218f7-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="218f7-112">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="218f7-113">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-113">yes</span></span> |
|<span data-ttu-id="218f7-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-114">Outlook</span></span>| <span data-ttu-id="218f7-115">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-115">yes</span></span> |<span data-ttu-id="218f7-116">из Win 32</span><span class="sxs-lookup"><span data-stu-id="218f7-116">from Win 32</span></span> |
|<span data-ttu-id="218f7-117">SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="218f7-118">да</span><span class="sxs-lookup"><span data-stu-id="218f7-118">yes</span></span> | |
|<span data-ttu-id="218f7-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-119">Exchange</span></span>        |<span data-ttu-id="218f7-120">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-120">yes</span></span>         | |
|<span data-ttu-id="218f7-121">Унифицированный клиент Azure Information Protection (AIP) и единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="218f7-122">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-122">yes</span></span> |<span data-ttu-id="218f7-123">действие новой *метки* AIP сопоположено с *меткой, примененной* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="218f7-124">Microsoft information protection (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="218f7-125">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-125">yes</span></span>|<span data-ttu-id="218f7-126">действие новой *метки* AIP сопоположено с *меткой, примененной* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="218f7-127">Служба управления правами (RMS)</span><span class="sxs-lookup"><span data-stu-id="218f7-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="218f7-128">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-128">not applicable</span></span>         | |
|<span data-ttu-id="218f7-129">Power BI и веб</span><span class="sxs-lookup"><span data-stu-id="218f7-129">Power BI desktop and web</span></span>        | <span data-ttu-id="218f7-130">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-130">no</span></span>| <span data-ttu-id="218f7-131">доступны в журналах Microsoft 365 аудита</span><span class="sxs-lookup"><span data-stu-id="218f7-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="218f7-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="218f7-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="218f7-133">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="218f7-134">Метка "Чувствительность" изменена</span><span class="sxs-lookup"><span data-stu-id="218f7-134">Sensitivity label changed</span></span>

<span data-ttu-id="218f7-135">Это событие создается каждый раз, когда метка конфиденциальности обновляется в документе или электронной почте.</span><span class="sxs-lookup"><span data-stu-id="218f7-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="218f7-136">Для единого клиента AIP, источников единого сканера и SDK  *MIP* метка обновления AIP и карты действий метки понижения до метки обозревателя *действий изменены.*</span><span class="sxs-lookup"><span data-stu-id="218f7-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="218f7-137">Он фиксируется в точке сохранения в Office приложениях и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="218f7-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="218f7-138">Он фиксируется во время появления в Azure Information Protection унифицированных клиентских надстройок и правоохранительных органов сканера.</span><span class="sxs-lookup"><span data-stu-id="218f7-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="218f7-139">Действия по обновлению и понижению меток также можно отслеживать с помощью поля типа событий *Label* и фильтра.</span><span class="sxs-lookup"><span data-stu-id="218f7-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="218f7-140">Текст *обоснования* также захвачен, за исключением SharePoint Online и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="218f7-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="218f7-141">Маркировка конфиденциальности, Office в Outlook, собирает последнее действие, которое было сгенерировано до сохранения файлов или действий отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="218f7-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="218f7-142">Например, если перед отправкой пользователь несколько раз меняет метку на электронной почте, последняя метка, найденная в электронной почте при отправке, запечатлена в журнале аудита и затем сообщается в проводнике действий.</span><span class="sxs-lookup"><span data-stu-id="218f7-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="218f7-143">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-143">Source</span></span>  |<span data-ttu-id="218f7-144">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-144">Reported in activity explorer</span></span>|<span data-ttu-id="218f7-145">Примечание</span><span class="sxs-lookup"><span data-stu-id="218f7-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="218f7-146">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="218f7-147">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-147">yes</span></span>         |
|<span data-ttu-id="218f7-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-148">Outlook</span></span>         |<span data-ttu-id="218f7-149">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-149">yes</span></span>         |<span data-ttu-id="218f7-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="218f7-150">Win 32</span></span>|
|<span data-ttu-id="218f7-151">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="218f7-152">да</span><span class="sxs-lookup"><span data-stu-id="218f7-152">yes</span></span>         |
|<span data-ttu-id="218f7-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-153">Exchange</span></span>         |<span data-ttu-id="218f7-154">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-154">yes</span></span>         |
|<span data-ttu-id="218f7-155">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-155">AIP unified client</span></span>         |<span data-ttu-id="218f7-156">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-156">yes</span></span>         |
|<span data-ttu-id="218f7-157">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-157">AIP unified scanner</span></span>         |<span data-ttu-id="218f7-158">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-158">yes</span></span>         |
|<span data-ttu-id="218f7-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-159">MIP SDK</span></span>         |<span data-ttu-id="218f7-160">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-160">yes</span></span>         |
|<span data-ttu-id="218f7-161">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="218f7-161">RMS service</span></span>         |<span data-ttu-id="218f7-162">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-162">not applicable</span></span>         |
|<span data-ttu-id="218f7-163">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="218f7-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="218f7-164">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-164">no</span></span>         |<span data-ttu-id="218f7-165">доступны в журналах Microsoft 365 аудита</span><span class="sxs-lookup"><span data-stu-id="218f7-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="218f7-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-166">MCAS</span></span>     |<span data-ttu-id="218f7-167">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="218f7-168">Метка конфиденциальности удалена</span><span class="sxs-lookup"><span data-stu-id="218f7-168">Sensitivity label removed</span></span>

<span data-ttu-id="218f7-169">Это событие создается каждый раз, когда метка конфиденциальности удаляется из файла или документа.</span><span class="sxs-lookup"><span data-stu-id="218f7-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="218f7-170">Это событие фиксируется во время сохранения в Office приложениях и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="218f7-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="218f7-171">Она фиксируется во время появления в надстройки для защиты информации Azure.</span><span class="sxs-lookup"><span data-stu-id="218f7-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="218f7-172">Маркировка конфиденциальности с Office меткой MIP на Outlook собирает последнее событие метки, которое было сгенерировано до сохранения файлов или действий отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="218f7-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="218f7-173">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-173">Source</span></span>  |<span data-ttu-id="218f7-174">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-174">Reported in activity explorer</span></span> | <span data-ttu-id="218f7-175">Примечание</span><span class="sxs-lookup"><span data-stu-id="218f7-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="218f7-176">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="218f7-177">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-177">yes</span></span>         |
|<span data-ttu-id="218f7-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-178">Outlook</span></span>         |<span data-ttu-id="218f7-179">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-179">yes</span></span>         |<span data-ttu-id="218f7-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="218f7-180">Win 32</span></span>|
|<span data-ttu-id="218f7-181">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="218f7-182">да</span><span class="sxs-lookup"><span data-stu-id="218f7-182">yes</span></span>         |
|<span data-ttu-id="218f7-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-183">Exchange</span></span>         |<span data-ttu-id="218f7-184">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-184">yes</span></span>         |
|<span data-ttu-id="218f7-185">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-185">AIP unified client</span></span>         |<span data-ttu-id="218f7-186">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-186">yes</span></span>         |<span data-ttu-id="218f7-187">действие AIP *по удалению метки* сопостраняется с действием *метки, удаленным* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="218f7-188">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-188">AIP unified scanner</span></span>         |<span data-ttu-id="218f7-189">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-189">yes</span></span>         |<span data-ttu-id="218f7-190">действие AIP *по удалению метки* сопостраняется с действием *метки, удаленным* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="218f7-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-191">MIP SDK</span></span>         |<span data-ttu-id="218f7-192">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-192">yes</span></span>         |<span data-ttu-id="218f7-193">действие AIP *по удалению метки* сопостраняется с действием *метки, удаленным* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="218f7-194">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="218f7-194">RMS service</span></span>         |<span data-ttu-id="218f7-195">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-195">not applicable</span></span>         |
|<span data-ttu-id="218f7-196">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="218f7-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="218f7-197">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-197">no</span></span>         |<span data-ttu-id="218f7-198">доступны в журналах Microsoft 365 аудита</span><span class="sxs-lookup"><span data-stu-id="218f7-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="218f7-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-199">MCAS</span></span>     |<span data-ttu-id="218f7-200">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="218f7-201">Чтение файла метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="218f7-201">Sensitivity label file read</span></span>

<span data-ttu-id="218f7-202">Это событие создается при каждом открываемом документе с меткой конфиденциальности или защищенной защитой.</span><span class="sxs-lookup"><span data-stu-id="218f7-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="218f7-203">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-203">Source</span></span>  |<span data-ttu-id="218f7-204">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-204">Reported in activity explorer</span></span> | <span data-ttu-id="218f7-205">Примечание</span><span class="sxs-lookup"><span data-stu-id="218f7-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="218f7-206">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="218f7-207">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-207">yes</span></span>         |
|<span data-ttu-id="218f7-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-208">Outlook</span></span>         |<span data-ttu-id="218f7-209">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-209">no</span></span>         |
|<span data-ttu-id="218f7-210">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="218f7-211">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-211">no</span></span>         |
|<span data-ttu-id="218f7-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-212">Exchange</span></span>         |<span data-ttu-id="218f7-213">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-213">no</span></span>         |
|<span data-ttu-id="218f7-214">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-214">AIP unified client</span></span>         |<span data-ttu-id="218f7-215">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-215">yes</span></span>         |<span data-ttu-id="218f7-216">действие доступа *AIP* сопоно  с действием чтения файла в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="218f7-217">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-217">AIP unified scanner</span></span>         |<span data-ttu-id="218f7-218">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-218">yes</span></span>         |<span data-ttu-id="218f7-219">действие доступа *AIP* сопоно  с действием чтения файла в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="218f7-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-220">MIP SDK</span></span>         |<span data-ttu-id="218f7-221">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-221">yes</span></span>         |<span data-ttu-id="218f7-222">действие доступа *AIP* сопоно  с действием чтения файла в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="218f7-223">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="218f7-223">RMS service</span></span>         |<span data-ttu-id="218f7-224">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-224">yes</span></span>         |<span data-ttu-id="218f7-225">действие *доступа* соотнося с действием чтения *файла* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="218f7-226">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="218f7-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="218f7-227">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-227">no</span></span>         |<span data-ttu-id="218f7-228">доступны в журналах Microsoft 365 аудита</span><span class="sxs-lookup"><span data-stu-id="218f7-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="218f7-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-229">MCAS</span></span>     |<span data-ttu-id="218f7-230">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="218f7-231">Обнаруженные файлы</span><span class="sxs-lookup"><span data-stu-id="218f7-231">Files discovered</span></span>

<span data-ttu-id="218f7-232">Это событие создается каждый раз, когда файлы обнаруживаются при том, что сканер AIP используется для сканирования конфиденциальных данных в различных местах и обнаружения файлов.</span><span class="sxs-lookup"><span data-stu-id="218f7-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="218f7-233">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-233">Source</span></span>  |<span data-ttu-id="218f7-234">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-234">Reported in activity explorer</span></span> | <span data-ttu-id="218f7-235">Примечание</span><span class="sxs-lookup"><span data-stu-id="218f7-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="218f7-236">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="218f7-237">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-237">not applicable</span></span>         |
|<span data-ttu-id="218f7-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-238">Outlook</span></span>         |<span data-ttu-id="218f7-239">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-239">not applicable</span></span>         |
|<span data-ttu-id="218f7-240">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="218f7-241">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-241">not applicable</span></span>         |
|<span data-ttu-id="218f7-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-242">Exchange</span></span>         |<span data-ttu-id="218f7-243">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-243">not applicable</span></span>         |
|<span data-ttu-id="218f7-244">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-244">AIP unified client</span></span>         |<span data-ttu-id="218f7-245">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-245">not applicable</span></span>       |
|<span data-ttu-id="218f7-246">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-246">AIP unified scanner</span></span>         |<span data-ttu-id="218f7-247">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-247">yes</span></span>         |<span data-ttu-id="218f7-248">действие обнаружения *AIP* сопопоясается с *файлами,* обнаруженными в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="218f7-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-249">MIP SDK</span></span>         |<span data-ttu-id="218f7-250">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-250">yes</span></span>         |<span data-ttu-id="218f7-251">действие обнаружения *AIP* сопопослано действию *обнаруженного файла* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="218f7-252">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="218f7-252">RMS service</span></span>         |<span data-ttu-id="218f7-253">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-253">not applicable</span></span>         |
|<span data-ttu-id="218f7-254">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="218f7-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="218f7-255">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-255">not applicable</span></span>         |
|<span data-ttu-id="218f7-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-256">MCAS</span></span>     |<span data-ttu-id="218f7-257">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="218f7-258">Переименован файл метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="218f7-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="218f7-259">Это событие создается при каждом переименовании документа с меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="218f7-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="218f7-260">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-260">Source</span></span>  | <span data-ttu-id="218f7-261">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-261">Reported in activity explorer</span></span> | <span data-ttu-id="218f7-262">Примечание</span><span class="sxs-lookup"><span data-stu-id="218f7-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="218f7-263">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="218f7-264">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-264">yes</span></span>         |
|<span data-ttu-id="218f7-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-265">Outlook</span></span>         |<span data-ttu-id="218f7-266">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-266">not applicable</span></span>         |
|<span data-ttu-id="218f7-267">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="218f7-268">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-268">no</span></span>        |
|<span data-ttu-id="218f7-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-269">Exchange</span></span>         |<span data-ttu-id="218f7-270">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-270">not applicable</span></span>         |
|<span data-ttu-id="218f7-271">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-271">AIP unified client</span></span>         |<span data-ttu-id="218f7-272">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-272">no</span></span>         |
|<span data-ttu-id="218f7-273">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-273">AIP unified scanner</span></span>         |<span data-ttu-id="218f7-274">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-274">no</span></span>         |
|<span data-ttu-id="218f7-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-275">MIP SDK</span></span>         |<span data-ttu-id="218f7-276">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-276">no</span></span>         |
|<span data-ttu-id="218f7-277">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="218f7-277">RMS service</span></span>         |<span data-ttu-id="218f7-278">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-278">no</span></span>      |
|<span data-ttu-id="218f7-279">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="218f7-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="218f7-280">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-280">no</span></span>         |
|<span data-ttu-id="218f7-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-281">MCAS</span></span>     |<span data-ttu-id="218f7-282">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="218f7-283">Файл удален</span><span class="sxs-lookup"><span data-stu-id="218f7-283">File removed</span></span>

<span data-ttu-id="218f7-284">Это событие создается каждый раз, когда сканер AIP обнаруживает, что ранее отсканированный файл был удален.</span><span class="sxs-lookup"><span data-stu-id="218f7-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="218f7-285">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-285">Source</span></span>  |<span data-ttu-id="218f7-286">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-286">Reported in activity explorer</span></span> | <span data-ttu-id="218f7-287">Примечание</span><span class="sxs-lookup"><span data-stu-id="218f7-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="218f7-288">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="218f7-289">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-289">not applicable</span></span>         |
|<span data-ttu-id="218f7-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-290">Outlook</span></span>         |<span data-ttu-id="218f7-291">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-291">not applicable</span></span>         |
|<span data-ttu-id="218f7-292">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="218f7-293">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-293">not applicable</span></span>           |
|<span data-ttu-id="218f7-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-294">Exchange</span></span>         |<span data-ttu-id="218f7-295">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-295">not applicable</span></span>         |
|<span data-ttu-id="218f7-296">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-296">AIP unified client</span></span>         |<span data-ttu-id="218f7-297">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-297">not applicable</span></span>            |
|<span data-ttu-id="218f7-298">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-298">AIP unified scanner</span></span>         |<span data-ttu-id="218f7-299">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-299">yes</span></span>         |
|<span data-ttu-id="218f7-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-300">MIP SDK</span></span>         |<span data-ttu-id="218f7-301">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-301">not applicable</span></span>            |
|<span data-ttu-id="218f7-302">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="218f7-302">RMS service</span></span>         |<span data-ttu-id="218f7-303">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-303">not applicable</span></span>         |
|<span data-ttu-id="218f7-304">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="218f7-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="218f7-305">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-305">not applicable</span></span>  |
|<span data-ttu-id="218f7-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-306">MCAS</span></span>     |<span data-ttu-id="218f7-307">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="218f7-308">Применена защита</span><span class="sxs-lookup"><span data-stu-id="218f7-308">Protection applied</span></span>

<span data-ttu-id="218f7-309">Это событие создается впервые, когда защита добавляется вручную к элементу, у него нет метки.</span><span class="sxs-lookup"><span data-stu-id="218f7-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="218f7-310">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-310">Source</span></span>  |<span data-ttu-id="218f7-311">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-311">Reported in activity explorer</span></span> | <span data-ttu-id="218f7-312">Примечание</span><span class="sxs-lookup"><span data-stu-id="218f7-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="218f7-313">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="218f7-314">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-314">no</span></span>         |
|<span data-ttu-id="218f7-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-315">Outlook</span></span>         |<span data-ttu-id="218f7-316">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-316">no</span></span>         |
|<span data-ttu-id="218f7-317">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="218f7-318">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-318">not applicable</span></span>           |
|<span data-ttu-id="218f7-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-319">Exchange</span></span>         |<span data-ttu-id="218f7-320">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-320">no</span></span>       |
|<span data-ttu-id="218f7-321">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-321">AIP unified client</span></span>         |<span data-ttu-id="218f7-322">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-322">yes</span></span>            |
|<span data-ttu-id="218f7-323">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-323">AIP unified scanner</span></span>         |<span data-ttu-id="218f7-324">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-324">not applicable</span></span>         |
|<span data-ttu-id="218f7-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-325">MIP SDK</span></span>         |<span data-ttu-id="218f7-326">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-326">yes</span></span>            |
|<span data-ttu-id="218f7-327">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="218f7-327">RMS service</span></span>         |<span data-ttu-id="218f7-328">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-328">not applicable</span></span>         |
|<span data-ttu-id="218f7-329">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="218f7-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="218f7-330">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-330">not applicable</span></span>            |
|<span data-ttu-id="218f7-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-331">MCAS</span></span>     |<span data-ttu-id="218f7-332">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="218f7-333">Изменена защита</span><span class="sxs-lookup"><span data-stu-id="218f7-333">Protection changed</span></span>

<span data-ttu-id="218f7-334">Это событие создается каждый раз, когда защита на ненаблюдном документе меняется вручную.</span><span class="sxs-lookup"><span data-stu-id="218f7-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="218f7-335">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-335">Source</span></span>  |<span data-ttu-id="218f7-336">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="218f7-337">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="218f7-338">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-338">no</span></span>         |
|<span data-ttu-id="218f7-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-339">Outlook</span></span>         |<span data-ttu-id="218f7-340">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-340">no</span></span>         |
|<span data-ttu-id="218f7-341">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="218f7-342">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-342">not applicable</span></span>           |
|<span data-ttu-id="218f7-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-343">Exchange</span></span>         |<span data-ttu-id="218f7-344">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-344">no</span></span>       |
|<span data-ttu-id="218f7-345">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-345">AIP unified client</span></span>         |<span data-ttu-id="218f7-346">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-346">yes</span></span>            |
|<span data-ttu-id="218f7-347">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-347">AIP unified scanner</span></span>         |<span data-ttu-id="218f7-348">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-348">not applicable</span></span>         |
|<span data-ttu-id="218f7-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-349">MIP SDK</span></span>         |<span data-ttu-id="218f7-350">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-350">yes</span></span>            |
|<span data-ttu-id="218f7-351">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="218f7-351">RMS service</span></span>         |<span data-ttu-id="218f7-352">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-352">not applicable</span></span>         |
|<span data-ttu-id="218f7-353">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="218f7-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="218f7-354">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-354">not applicable</span></span>            |
|<span data-ttu-id="218f7-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-355">MCAS</span></span>     |<span data-ttu-id="218f7-356">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="218f7-357">Защита удалена</span><span class="sxs-lookup"><span data-stu-id="218f7-357">Protection removed</span></span>

<span data-ttu-id="218f7-358">Это событие создается каждый раз, когда защита на ненаблюдном документе меняется вручную.</span><span class="sxs-lookup"><span data-stu-id="218f7-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="218f7-359">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-359">Source</span></span>  |<span data-ttu-id="218f7-360">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="218f7-361">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="218f7-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="218f7-362">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-362">no</span></span>         |
|<span data-ttu-id="218f7-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="218f7-363">Outlook</span></span>         |<span data-ttu-id="218f7-364">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-364">no</span></span>         |
|<span data-ttu-id="218f7-365">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="218f7-366">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-366">not applicable</span></span>           |
|<span data-ttu-id="218f7-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-367">Exchange</span></span>         |<span data-ttu-id="218f7-368">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-368">no</span></span>       |
|<span data-ttu-id="218f7-369">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-369">AIP unified client</span></span>         |<span data-ttu-id="218f7-370">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-370">yes</span></span>            |
|<span data-ttu-id="218f7-371">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="218f7-371">AIP unified scanner</span></span>         |<span data-ttu-id="218f7-372">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-372">not applicable</span></span>         |
|<span data-ttu-id="218f7-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="218f7-373">MIP SDK</span></span>         |<span data-ttu-id="218f7-374">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-374">yes</span></span>            |
|<span data-ttu-id="218f7-375">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="218f7-375">RMS service</span></span>         |<span data-ttu-id="218f7-376">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-376">not applicable</span></span>         |
|<span data-ttu-id="218f7-377">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="218f7-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="218f7-378">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-378">not applicable</span></span>            |
|<span data-ttu-id="218f7-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-379">MCAS</span></span>     |<span data-ttu-id="218f7-380">неприменимо</span><span class="sxs-lookup"><span data-stu-id="218f7-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="218f7-381">Политика DLP</span><span class="sxs-lookup"><span data-stu-id="218f7-381">DLP policy matched</span></span>

<span data-ttu-id="218f7-382">Это событие создается каждый раз, когда политика DLP совпадает с документом или электронной почтой.</span><span class="sxs-lookup"><span data-stu-id="218f7-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="218f7-383">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-383">Source</span></span>  |<span data-ttu-id="218f7-384">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="218f7-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-385">Exchange</span></span>         |<span data-ttu-id="218f7-386">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-386">yes</span></span>       |
|<span data-ttu-id="218f7-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="218f7-387">SharePoint Online</span></span>|<span data-ttu-id="218f7-388">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-388">yes</span></span>          |
|<span data-ttu-id="218f7-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-389">OneDrive</span></span> |<span data-ttu-id="218f7-390">да</span><span class="sxs-lookup"><span data-stu-id="218f7-390">yes</span></span>|
|<span data-ttu-id="218f7-391">Teams</span><span class="sxs-lookup"><span data-stu-id="218f7-391">Teams</span></span> |<span data-ttu-id="218f7-392">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-392">yes</span></span>   |
|<span data-ttu-id="218f7-393">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="218f7-393">Windows 10 devices</span></span>         |<span data-ttu-id="218f7-394">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-394">yes</span></span> |
|<span data-ttu-id="218f7-395">MAC</span><span class="sxs-lookup"><span data-stu-id="218f7-395">MAC</span></span>         |<span data-ttu-id="218f7-396">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-396">no</span></span>     |
|<span data-ttu-id="218f7-397">локальное</span><span class="sxs-lookup"><span data-stu-id="218f7-397">on-premises</span></span>         |<span data-ttu-id="218f7-398">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-398">no</span></span>|
|<span data-ttu-id="218f7-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="218f7-399">MCAS</span></span>     |<span data-ttu-id="218f7-400">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-400">no</span></span>        | 

<span data-ttu-id="218f7-401">События для Windows 10 устройств (конечная точка DLP) являются:</span><span class="sxs-lookup"><span data-stu-id="218f7-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="218f7-402">удаленный файл</span><span class="sxs-lookup"><span data-stu-id="218f7-402">file deleted</span></span>
- <span data-ttu-id="218f7-403">созданный файл</span><span class="sxs-lookup"><span data-stu-id="218f7-403">file created</span></span>
- <span data-ttu-id="218f7-404">файл скопирован в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="218f7-404">file copied to clipboard</span></span>
- <span data-ttu-id="218f7-405">изменение файла</span><span class="sxs-lookup"><span data-stu-id="218f7-405">file modified</span></span>
- <span data-ttu-id="218f7-406">чтение файла</span><span class="sxs-lookup"><span data-stu-id="218f7-406">file read</span></span>
- <span data-ttu-id="218f7-407">файл распечатан</span><span class="sxs-lookup"><span data-stu-id="218f7-407">file printed</span></span>
- <span data-ttu-id="218f7-408">переименован файл</span><span class="sxs-lookup"><span data-stu-id="218f7-408">file renamed</span></span>
- <span data-ttu-id="218f7-409">файл скопирован в сетевую папку</span><span class="sxs-lookup"><span data-stu-id="218f7-409">file copied to network share</span></span>
- <span data-ttu-id="218f7-410">файл, доступный в незаверяемом приложении</span><span class="sxs-lookup"><span data-stu-id="218f7-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="218f7-411">Применена метка хранения</span><span class="sxs-lookup"><span data-stu-id="218f7-411">Retention label applied</span></span> 

<span data-ttu-id="218f7-412">Это событие создается каждый раз, когда документ без маркировки или отправка электронной почты с меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="218f7-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="218f7-413">Он фиксируется во время сохранения документа и во время отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="218f7-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="218f7-414">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-414">Source</span></span>  |<span data-ttu-id="218f7-415">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="218f7-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-416">Exchange</span></span>         |<span data-ttu-id="218f7-417">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-417">no</span></span>       |
|<span data-ttu-id="218f7-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="218f7-418">SharePoint Online</span></span>|<span data-ttu-id="218f7-419">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-419">yes</span></span>          |
|<span data-ttu-id="218f7-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-420">OneDrive</span></span> |<span data-ttu-id="218f7-421">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="218f7-422">Метка хранения изменена</span><span class="sxs-lookup"><span data-stu-id="218f7-422">Retention label changed</span></span>

<span data-ttu-id="218f7-423">Это событие создается каждый раз, когда метка обновляется в документе или электронной почте.</span><span class="sxs-lookup"><span data-stu-id="218f7-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="218f7-424">Он фиксируется во время сохранения документа и во время отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="218f7-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="218f7-425">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-425">Source</span></span>  |<span data-ttu-id="218f7-426">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="218f7-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-427">Exchange</span></span>         |<span data-ttu-id="218f7-428">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-428">no</span></span>       |
|<span data-ttu-id="218f7-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="218f7-429">SharePoint Online</span></span>|<span data-ttu-id="218f7-430">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-430">yes</span></span>          |
|<span data-ttu-id="218f7-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-431">OneDrive</span></span> |<span data-ttu-id="218f7-432">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="218f7-433">Метка хранения удалена</span><span class="sxs-lookup"><span data-stu-id="218f7-433">Retention label removed</span></span>

<span data-ttu-id="218f7-434">Это событие создается каждый раз, когда метка удаляется из файла или документа.</span><span class="sxs-lookup"><span data-stu-id="218f7-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="218f7-435">Он фиксируется во время сохранения документа и во время отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="218f7-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="218f7-436">Источник</span><span class="sxs-lookup"><span data-stu-id="218f7-436">Source</span></span>  |<span data-ttu-id="218f7-437">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="218f7-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="218f7-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="218f7-438">Exchange</span></span>         |<span data-ttu-id="218f7-439">нет</span><span class="sxs-lookup"><span data-stu-id="218f7-439">no</span></span>       |
|<span data-ttu-id="218f7-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="218f7-440">SharePoint Online</span></span>|<span data-ttu-id="218f7-441">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-441">yes</span></span>          |
|<span data-ttu-id="218f7-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="218f7-442">OneDrive</span></span> |<span data-ttu-id="218f7-443">Да</span><span class="sxs-lookup"><span data-stu-id="218f7-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="218f7-444">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="218f7-444">Known issues</span></span>
  
- <span data-ttu-id="218f7-445">Когда рекомендуемый совет средства метки отображается конечному пользователю, он не захватывается.</span><span class="sxs-lookup"><span data-stu-id="218f7-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="218f7-446">Но если пользователь решил применить рекомендуемую метку, метка будет показана в поле *How applied* as *Recommended*</span><span class="sxs-lookup"><span data-stu-id="218f7-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="218f7-447">Текст обоснования в настоящее время не доступен для понижения метки конфиденциальности с Sharepoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="218f7-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="218f7-448">Типы конфиденциальной информации в настоящее время недоступны для действий автолабелинга из Word, Excel, PowerPoint и Outlook, а также SharePoint Online и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="218f7-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
