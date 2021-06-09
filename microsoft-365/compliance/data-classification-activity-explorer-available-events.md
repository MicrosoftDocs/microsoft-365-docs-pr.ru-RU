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
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="0c07f-103">Действия по маркировке, доступные в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="0c07f-104">Метка "Чувствительность", примененная</span><span class="sxs-lookup"><span data-stu-id="0c07f-104">Sensitivity label applied</span></span>

<span data-ttu-id="0c07f-105">Это событие создается каждый раз, когда не помечен документ или отправляется сообщение электронной почты с меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="0c07f-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="0c07f-106">Оно фиксируется во время сохранения в Office и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="0c07f-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="0c07f-107">Она фиксируется во время появления в надстройки для защиты информации Azure.</span><span class="sxs-lookup"><span data-stu-id="0c07f-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="0c07f-108">Действия по обновлению и понижению меток также можно отслеживать с помощью поля типа событий *Label* и фильтра.</span><span class="sxs-lookup"><span data-stu-id="0c07f-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="0c07f-109">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-109">Source</span></span>  |<span data-ttu-id="0c07f-110">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-110">Reported in activity explorer</span></span> | <span data-ttu-id="0c07f-111">Примечание</span><span class="sxs-lookup"><span data-stu-id="0c07f-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="0c07f-112">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="0c07f-113">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-113">yes</span></span> |
|<span data-ttu-id="0c07f-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-114">Outlook</span></span>| <span data-ttu-id="0c07f-115">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-115">yes</span></span> |<span data-ttu-id="0c07f-116">из Win 32</span><span class="sxs-lookup"><span data-stu-id="0c07f-116">from Win 32</span></span> |
|<span data-ttu-id="0c07f-117">SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="0c07f-118">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-118">yes</span></span> | |
|<span data-ttu-id="0c07f-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-119">Exchange</span></span>        |<span data-ttu-id="0c07f-120">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-120">yes</span></span>         | |
|<span data-ttu-id="0c07f-121">Унифицированный клиент Azure Information Protection (AIP) и единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="0c07f-122">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-122">yes</span></span> |<span data-ttu-id="0c07f-123">действие новой *метки* AIP сопоположено с *меткой, примененной* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="0c07f-124">Microsoft information protection (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="0c07f-125">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-125">yes</span></span>|<span data-ttu-id="0c07f-126">действие новой *метки* AIP сопоположено с *меткой, примененной* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="0c07f-127">Служба управления правами (RMS)</span><span class="sxs-lookup"><span data-stu-id="0c07f-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="0c07f-128">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-128">not applicable</span></span>         | |
|<span data-ttu-id="0c07f-129">Power BI и веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-129">Power BI desktop and web</span></span>        | <span data-ttu-id="0c07f-130">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-130">no</span></span>| <span data-ttu-id="0c07f-131">доступны в журналах Microsoft 365 аудита</span><span class="sxs-lookup"><span data-stu-id="0c07f-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="0c07f-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="0c07f-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="0c07f-133">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="0c07f-134">Метка "Чувствительность" изменена</span><span class="sxs-lookup"><span data-stu-id="0c07f-134">Sensitivity label changed</span></span>

<span data-ttu-id="0c07f-135">Это событие создается каждый раз, когда метка конфиденциальности обновляется в документе или электронной почте.</span><span class="sxs-lookup"><span data-stu-id="0c07f-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="0c07f-136">Для единого клиента AIP, источников единого сканера и SDK  *MIP* метка обновления AIP и карты действий метки понижения до метки обозревателя *действий изменены.*</span><span class="sxs-lookup"><span data-stu-id="0c07f-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="0c07f-137">Он фиксируется в точке сохранения в Office приложениях и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="0c07f-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="0c07f-138">Он фиксируется во время появления в Azure Information Protection унифицированных клиентских надстройок и правоохранительных органов сканера.</span><span class="sxs-lookup"><span data-stu-id="0c07f-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="0c07f-139">Действия по обновлению и понижению меток также можно отслеживать с помощью поля типа событий *Label* и фильтра.</span><span class="sxs-lookup"><span data-stu-id="0c07f-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="0c07f-140">Текст *обоснования* также захвачен, за исключением SharePoint Online и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0c07f-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="0c07f-141">Маркировка конфиденциальности, Office в Outlook, собирает последнее действие, которое было сгенерировано до сохранения файлов или действий отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c07f-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="0c07f-142">Например, если перед отправкой пользователь несколько раз меняет метку на электронной почте, последняя метка, найденная в электронной почте при отправке, запечатлена в журнале аудита и затем сообщается в проводнике действий.</span><span class="sxs-lookup"><span data-stu-id="0c07f-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="0c07f-143">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-143">Source</span></span>  |<span data-ttu-id="0c07f-144">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-144">Reported in activity explorer</span></span>|<span data-ttu-id="0c07f-145">Примечание</span><span class="sxs-lookup"><span data-stu-id="0c07f-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="0c07f-146">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="0c07f-147">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-147">yes</span></span>         |
|<span data-ttu-id="0c07f-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-148">Outlook</span></span>         |<span data-ttu-id="0c07f-149">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-149">yes</span></span>         |<span data-ttu-id="0c07f-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="0c07f-150">Win 32</span></span>|
|<span data-ttu-id="0c07f-151">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="0c07f-152">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-152">yes</span></span>         |
|<span data-ttu-id="0c07f-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-153">Exchange</span></span>         |<span data-ttu-id="0c07f-154">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-154">yes</span></span>         |
|<span data-ttu-id="0c07f-155">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-155">AIP unified client</span></span>         |<span data-ttu-id="0c07f-156">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-156">yes</span></span>         |
|<span data-ttu-id="0c07f-157">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-157">AIP unified scanner</span></span>         |<span data-ttu-id="0c07f-158">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-158">yes</span></span>         |
|<span data-ttu-id="0c07f-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-159">MIP SDK</span></span>         |<span data-ttu-id="0c07f-160">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-160">yes</span></span>         |
|<span data-ttu-id="0c07f-161">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="0c07f-161">RMS service</span></span>         |<span data-ttu-id="0c07f-162">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-162">not applicable</span></span>         |
|<span data-ttu-id="0c07f-163">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="0c07f-164">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-164">no</span></span>         |<span data-ttu-id="0c07f-165">доступны в журналах Microsoft 365 аудита</span><span class="sxs-lookup"><span data-stu-id="0c07f-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="0c07f-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-166">MCAS</span></span>     |<span data-ttu-id="0c07f-167">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="0c07f-168">Метка конфиденциальности удалена</span><span class="sxs-lookup"><span data-stu-id="0c07f-168">Sensitivity label removed</span></span>

<span data-ttu-id="0c07f-169">Это событие создается каждый раз, когда метка конфиденциальности удаляется из файла или документа.</span><span class="sxs-lookup"><span data-stu-id="0c07f-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="0c07f-170">Это событие фиксируется во время сохранения в Office приложениях и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="0c07f-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="0c07f-171">Она фиксируется во время появления в надстройки для защиты информации Azure.</span><span class="sxs-lookup"><span data-stu-id="0c07f-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="0c07f-172">Маркировка конфиденциальности с Office меткой MIP на Outlook собирает последнее событие метки, которое было сгенерировано до сохранения файлов или действий отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c07f-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="0c07f-173">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-173">Source</span></span>  |<span data-ttu-id="0c07f-174">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-174">Reported in activity explorer</span></span> | <span data-ttu-id="0c07f-175">Примечание</span><span class="sxs-lookup"><span data-stu-id="0c07f-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="0c07f-176">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="0c07f-177">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-177">yes</span></span>         |
|<span data-ttu-id="0c07f-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-178">Outlook</span></span>         |<span data-ttu-id="0c07f-179">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-179">yes</span></span>         |<span data-ttu-id="0c07f-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="0c07f-180">Win 32</span></span>|
|<span data-ttu-id="0c07f-181">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="0c07f-182">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-182">yes</span></span>         |
|<span data-ttu-id="0c07f-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-183">Exchange</span></span>         |<span data-ttu-id="0c07f-184">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-184">yes</span></span>         |
|<span data-ttu-id="0c07f-185">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-185">AIP unified client</span></span>         |<span data-ttu-id="0c07f-186">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-186">yes</span></span>         |<span data-ttu-id="0c07f-187">действие AIP *по удалению метки* сопостраняется с действием *метки, удаленным* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="0c07f-188">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-188">AIP unified scanner</span></span>         |<span data-ttu-id="0c07f-189">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-189">yes</span></span>         |<span data-ttu-id="0c07f-190">действие AIP *по удалению метки* сопостраняется с действием *метки, удаленным* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="0c07f-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-191">MIP SDK</span></span>         |<span data-ttu-id="0c07f-192">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-192">yes</span></span>         |<span data-ttu-id="0c07f-193">действие AIP *по удалению метки* сопостраняется с действием *метки, удаленным* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="0c07f-194">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="0c07f-194">RMS service</span></span>         |<span data-ttu-id="0c07f-195">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-195">not applicable</span></span>         |
|<span data-ttu-id="0c07f-196">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="0c07f-197">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-197">no</span></span>         |<span data-ttu-id="0c07f-198">доступны в журналах Microsoft 365 аудита</span><span class="sxs-lookup"><span data-stu-id="0c07f-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="0c07f-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-199">MCAS</span></span>     |<span data-ttu-id="0c07f-200">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="0c07f-201">Чтение файла метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="0c07f-201">Sensitivity label file read</span></span>

<span data-ttu-id="0c07f-202">Это событие создается при каждом открываемом документе с меткой конфиденциальности или защищенной защитой.</span><span class="sxs-lookup"><span data-stu-id="0c07f-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="0c07f-203">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-203">Source</span></span>  |<span data-ttu-id="0c07f-204">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-204">Reported in activity explorer</span></span> | <span data-ttu-id="0c07f-205">Примечание</span><span class="sxs-lookup"><span data-stu-id="0c07f-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="0c07f-206">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="0c07f-207">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-207">yes</span></span>         |
|<span data-ttu-id="0c07f-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-208">Outlook</span></span>         |<span data-ttu-id="0c07f-209">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-209">no</span></span>         |
|<span data-ttu-id="0c07f-210">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="0c07f-211">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-211">no</span></span>         |
|<span data-ttu-id="0c07f-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-212">Exchange</span></span>         |<span data-ttu-id="0c07f-213">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-213">no</span></span>         |
|<span data-ttu-id="0c07f-214">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-214">AIP unified client</span></span>         |<span data-ttu-id="0c07f-215">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-215">yes</span></span>         |<span data-ttu-id="0c07f-216">действие доступа *AIP* сопоно  с действием чтения файла в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="0c07f-217">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-217">AIP unified scanner</span></span>         |<span data-ttu-id="0c07f-218">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-218">yes</span></span>         |<span data-ttu-id="0c07f-219">действие доступа *AIP* сопоно  с действием чтения файла в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="0c07f-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-220">MIP SDK</span></span>         |<span data-ttu-id="0c07f-221">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-221">yes</span></span>         |<span data-ttu-id="0c07f-222">действие доступа *AIP* сопоно  с действием чтения файла в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="0c07f-223">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="0c07f-223">RMS service</span></span>         |<span data-ttu-id="0c07f-224">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-224">yes</span></span>         |<span data-ttu-id="0c07f-225">действие *доступа* соотнося с действием чтения *файла* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="0c07f-226">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="0c07f-227">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-227">no</span></span>         |<span data-ttu-id="0c07f-228">доступны в журналах Microsoft 365 аудита</span><span class="sxs-lookup"><span data-stu-id="0c07f-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="0c07f-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-229">MCAS</span></span>     |<span data-ttu-id="0c07f-230">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="0c07f-231">Обнаруженные файлы</span><span class="sxs-lookup"><span data-stu-id="0c07f-231">Files discovered</span></span>

<span data-ttu-id="0c07f-232">Это событие создается каждый раз, когда файлы обнаруживаются при том, что сканер AIP используется для сканирования конфиденциальных данных в различных местах и обнаружения файлов.</span><span class="sxs-lookup"><span data-stu-id="0c07f-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="0c07f-233">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-233">Source</span></span>  |<span data-ttu-id="0c07f-234">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-234">Reported in activity explorer</span></span> | <span data-ttu-id="0c07f-235">Примечание</span><span class="sxs-lookup"><span data-stu-id="0c07f-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="0c07f-236">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="0c07f-237">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-237">not applicable</span></span>         |
|<span data-ttu-id="0c07f-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-238">Outlook</span></span>         |<span data-ttu-id="0c07f-239">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-239">not applicable</span></span>         |
|<span data-ttu-id="0c07f-240">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="0c07f-241">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-241">not applicable</span></span>         |
|<span data-ttu-id="0c07f-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-242">Exchange</span></span>         |<span data-ttu-id="0c07f-243">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-243">not applicable</span></span>         |
|<span data-ttu-id="0c07f-244">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-244">AIP unified client</span></span>         |<span data-ttu-id="0c07f-245">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-245">not applicable</span></span>       |
|<span data-ttu-id="0c07f-246">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-246">AIP unified scanner</span></span>         |<span data-ttu-id="0c07f-247">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-247">yes</span></span>         |<span data-ttu-id="0c07f-248">действие обнаружения *AIP* сопопоясается с *файлами,* обнаруженными в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="0c07f-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-249">MIP SDK</span></span>         |<span data-ttu-id="0c07f-250">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-250">yes</span></span>         |<span data-ttu-id="0c07f-251">действие обнаружения *AIP* сопопослано действию *обнаруженного файла* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="0c07f-252">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="0c07f-252">RMS service</span></span>         |<span data-ttu-id="0c07f-253">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-253">not applicable</span></span>         |
|<span data-ttu-id="0c07f-254">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="0c07f-255">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-255">not applicable</span></span>         |
|<span data-ttu-id="0c07f-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-256">MCAS</span></span>     |<span data-ttu-id="0c07f-257">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="0c07f-258">Переименован файл метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="0c07f-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="0c07f-259">Это событие создается при каждом переименовании документа с меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="0c07f-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="0c07f-260">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-260">Source</span></span>  | <span data-ttu-id="0c07f-261">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-261">Reported in activity explorer</span></span> | <span data-ttu-id="0c07f-262">Примечание</span><span class="sxs-lookup"><span data-stu-id="0c07f-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="0c07f-263">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="0c07f-264">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-264">yes</span></span>         |
|<span data-ttu-id="0c07f-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-265">Outlook</span></span>         |<span data-ttu-id="0c07f-266">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-266">not applicable</span></span>         |
|<span data-ttu-id="0c07f-267">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="0c07f-268">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-268">no</span></span>        |
|<span data-ttu-id="0c07f-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-269">Exchange</span></span>         |<span data-ttu-id="0c07f-270">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-270">not applicable</span></span>         |
|<span data-ttu-id="0c07f-271">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-271">AIP unified client</span></span>         |<span data-ttu-id="0c07f-272">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-272">no</span></span>         |
|<span data-ttu-id="0c07f-273">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-273">AIP unified scanner</span></span>         |<span data-ttu-id="0c07f-274">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-274">no</span></span>         |
|<span data-ttu-id="0c07f-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-275">MIP SDK</span></span>         |<span data-ttu-id="0c07f-276">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-276">no</span></span>         |
|<span data-ttu-id="0c07f-277">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="0c07f-277">RMS service</span></span>         |<span data-ttu-id="0c07f-278">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-278">no</span></span>      |
|<span data-ttu-id="0c07f-279">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="0c07f-280">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-280">no</span></span>         |
|<span data-ttu-id="0c07f-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-281">MCAS</span></span>     |<span data-ttu-id="0c07f-282">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="0c07f-283">Файл удален</span><span class="sxs-lookup"><span data-stu-id="0c07f-283">File removed</span></span>

<span data-ttu-id="0c07f-284">Это событие создается каждый раз, когда сканер AIP обнаруживает, что ранее отсканированный файл был удален.</span><span class="sxs-lookup"><span data-stu-id="0c07f-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="0c07f-285">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-285">Source</span></span>  |<span data-ttu-id="0c07f-286">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-286">Reported in activity explorer</span></span> | <span data-ttu-id="0c07f-287">Примечание</span><span class="sxs-lookup"><span data-stu-id="0c07f-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="0c07f-288">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="0c07f-289">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-289">not applicable</span></span>         |
|<span data-ttu-id="0c07f-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-290">Outlook</span></span>         |<span data-ttu-id="0c07f-291">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-291">not applicable</span></span>         |
|<span data-ttu-id="0c07f-292">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="0c07f-293">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-293">not applicable</span></span>           |
|<span data-ttu-id="0c07f-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-294">Exchange</span></span>         |<span data-ttu-id="0c07f-295">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-295">not applicable</span></span>         |
|<span data-ttu-id="0c07f-296">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-296">AIP unified client</span></span>         |<span data-ttu-id="0c07f-297">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-297">not applicable</span></span>            |
|<span data-ttu-id="0c07f-298">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-298">AIP unified scanner</span></span>         |<span data-ttu-id="0c07f-299">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-299">yes</span></span>         |
|<span data-ttu-id="0c07f-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-300">MIP SDK</span></span>         |<span data-ttu-id="0c07f-301">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-301">not applicable</span></span>            |
|<span data-ttu-id="0c07f-302">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="0c07f-302">RMS service</span></span>         |<span data-ttu-id="0c07f-303">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-303">not applicable</span></span>         |
|<span data-ttu-id="0c07f-304">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="0c07f-305">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-305">not applicable</span></span>  |
|<span data-ttu-id="0c07f-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-306">MCAS</span></span>     |<span data-ttu-id="0c07f-307">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="0c07f-308">Применена защита</span><span class="sxs-lookup"><span data-stu-id="0c07f-308">Protection applied</span></span>

<span data-ttu-id="0c07f-309">Это событие создается впервые, когда защита добавляется вручную к элементу, у него нет метки.</span><span class="sxs-lookup"><span data-stu-id="0c07f-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="0c07f-310">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-310">Source</span></span>  |<span data-ttu-id="0c07f-311">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-311">Reported in activity explorer</span></span> | <span data-ttu-id="0c07f-312">Примечание</span><span class="sxs-lookup"><span data-stu-id="0c07f-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="0c07f-313">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="0c07f-314">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-314">no</span></span>         |
|<span data-ttu-id="0c07f-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-315">Outlook</span></span>         |<span data-ttu-id="0c07f-316">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-316">no</span></span>         |
|<span data-ttu-id="0c07f-317">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="0c07f-318">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-318">not applicable</span></span>           |
|<span data-ttu-id="0c07f-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-319">Exchange</span></span>         |<span data-ttu-id="0c07f-320">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-320">no</span></span>       |
|<span data-ttu-id="0c07f-321">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-321">AIP unified client</span></span>         |<span data-ttu-id="0c07f-322">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-322">yes</span></span>            |
|<span data-ttu-id="0c07f-323">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-323">AIP unified scanner</span></span>         |<span data-ttu-id="0c07f-324">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-324">not applicable</span></span>         |
|<span data-ttu-id="0c07f-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-325">MIP SDK</span></span>         |<span data-ttu-id="0c07f-326">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-326">yes</span></span>            |
|<span data-ttu-id="0c07f-327">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="0c07f-327">RMS service</span></span>         |<span data-ttu-id="0c07f-328">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-328">not applicable</span></span>         |
|<span data-ttu-id="0c07f-329">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="0c07f-330">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-330">not applicable</span></span>            |
|<span data-ttu-id="0c07f-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-331">MCAS</span></span>     |<span data-ttu-id="0c07f-332">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="0c07f-333">Изменена защита</span><span class="sxs-lookup"><span data-stu-id="0c07f-333">Protection changed</span></span>

<span data-ttu-id="0c07f-334">Это событие создается каждый раз, когда защита на ненаблюдном документе меняется вручную.</span><span class="sxs-lookup"><span data-stu-id="0c07f-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="0c07f-335">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-335">Source</span></span>  |<span data-ttu-id="0c07f-336">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="0c07f-337">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="0c07f-338">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-338">no</span></span>         |
|<span data-ttu-id="0c07f-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-339">Outlook</span></span>         |<span data-ttu-id="0c07f-340">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-340">no</span></span>         |
|<span data-ttu-id="0c07f-341">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="0c07f-342">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-342">not applicable</span></span>           |
|<span data-ttu-id="0c07f-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-343">Exchange</span></span>         |<span data-ttu-id="0c07f-344">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-344">no</span></span>       |
|<span data-ttu-id="0c07f-345">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-345">AIP unified client</span></span>         |<span data-ttu-id="0c07f-346">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-346">yes</span></span>            |
|<span data-ttu-id="0c07f-347">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-347">AIP unified scanner</span></span>         |<span data-ttu-id="0c07f-348">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-348">not applicable</span></span>         |
|<span data-ttu-id="0c07f-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-349">MIP SDK</span></span>         |<span data-ttu-id="0c07f-350">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-350">yes</span></span>            |
|<span data-ttu-id="0c07f-351">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="0c07f-351">RMS service</span></span>         |<span data-ttu-id="0c07f-352">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-352">not applicable</span></span>         |
|<span data-ttu-id="0c07f-353">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="0c07f-354">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-354">not applicable</span></span>            |
|<span data-ttu-id="0c07f-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-355">MCAS</span></span>     |<span data-ttu-id="0c07f-356">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="0c07f-357">Защита удалена</span><span class="sxs-lookup"><span data-stu-id="0c07f-357">Protection removed</span></span>

<span data-ttu-id="0c07f-358">Это событие создается каждый раз, когда защита на ненаблюдном документе меняется вручную.</span><span class="sxs-lookup"><span data-stu-id="0c07f-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="0c07f-359">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-359">Source</span></span>  |<span data-ttu-id="0c07f-360">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="0c07f-361">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0c07f-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="0c07f-362">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-362">no</span></span>         |
|<span data-ttu-id="0c07f-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="0c07f-363">Outlook</span></span>         |<span data-ttu-id="0c07f-364">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-364">no</span></span>         |
|<span data-ttu-id="0c07f-365">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="0c07f-366">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-366">not applicable</span></span>           |
|<span data-ttu-id="0c07f-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-367">Exchange</span></span>         |<span data-ttu-id="0c07f-368">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-368">no</span></span>       |
|<span data-ttu-id="0c07f-369">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-369">AIP unified client</span></span>         |<span data-ttu-id="0c07f-370">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-370">yes</span></span>            |
|<span data-ttu-id="0c07f-371">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="0c07f-371">AIP unified scanner</span></span>         |<span data-ttu-id="0c07f-372">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-372">not applicable</span></span>         |
|<span data-ttu-id="0c07f-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="0c07f-373">MIP SDK</span></span>         |<span data-ttu-id="0c07f-374">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-374">yes</span></span>            |
|<span data-ttu-id="0c07f-375">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="0c07f-375">RMS service</span></span>         |<span data-ttu-id="0c07f-376">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-376">not applicable</span></span>         |
|<span data-ttu-id="0c07f-377">Power BI и Веб</span><span class="sxs-lookup"><span data-stu-id="0c07f-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="0c07f-378">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-378">not applicable</span></span>            |
|<span data-ttu-id="0c07f-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-379">MCAS</span></span>     |<span data-ttu-id="0c07f-380">неприменимо</span><span class="sxs-lookup"><span data-stu-id="0c07f-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="0c07f-381">Политика DLP</span><span class="sxs-lookup"><span data-stu-id="0c07f-381">DLP policy matched</span></span>

<span data-ttu-id="0c07f-382">Это событие создается каждый раз, когда политика DLP совпадает с документом или электронной почтой.</span><span class="sxs-lookup"><span data-stu-id="0c07f-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="0c07f-383">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-383">Source</span></span>  |<span data-ttu-id="0c07f-384">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="0c07f-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-385">Exchange</span></span>         |<span data-ttu-id="0c07f-386">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-386">yes</span></span>       |
|<span data-ttu-id="0c07f-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0c07f-387">SharePoint Online</span></span>|<span data-ttu-id="0c07f-388">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-388">yes</span></span>          |
|<span data-ttu-id="0c07f-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-389">OneDrive</span></span> |<span data-ttu-id="0c07f-390">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-390">yes</span></span>|
|<span data-ttu-id="0c07f-391">Teams</span><span class="sxs-lookup"><span data-stu-id="0c07f-391">Teams</span></span> |<span data-ttu-id="0c07f-392">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-392">yes</span></span>   |
|<span data-ttu-id="0c07f-393">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="0c07f-393">Windows 10 devices</span></span>         |<span data-ttu-id="0c07f-394">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-394">yes</span></span> |
|<span data-ttu-id="0c07f-395">MAC</span><span class="sxs-lookup"><span data-stu-id="0c07f-395">MAC</span></span>         |<span data-ttu-id="0c07f-396">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-396">no</span></span>     |
|<span data-ttu-id="0c07f-397">локальное</span><span class="sxs-lookup"><span data-stu-id="0c07f-397">on-premises</span></span>         |<span data-ttu-id="0c07f-398">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-398">no</span></span>|
|<span data-ttu-id="0c07f-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="0c07f-399">MCAS</span></span>     |<span data-ttu-id="0c07f-400">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-400">no</span></span>        | 

<span data-ttu-id="0c07f-401">События для Windows 10 устройств (конечная точка DLP) являются:</span><span class="sxs-lookup"><span data-stu-id="0c07f-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="0c07f-402">удаленный файл</span><span class="sxs-lookup"><span data-stu-id="0c07f-402">file deleted</span></span>
- <span data-ttu-id="0c07f-403">созданный файл</span><span class="sxs-lookup"><span data-stu-id="0c07f-403">file created</span></span>
- <span data-ttu-id="0c07f-404">файл скопирован в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="0c07f-404">file copied to clipboard</span></span>
- <span data-ttu-id="0c07f-405">изменение файла</span><span class="sxs-lookup"><span data-stu-id="0c07f-405">file modified</span></span>
- <span data-ttu-id="0c07f-406">чтение файла</span><span class="sxs-lookup"><span data-stu-id="0c07f-406">file read</span></span>
- <span data-ttu-id="0c07f-407">файл распечатан</span><span class="sxs-lookup"><span data-stu-id="0c07f-407">file printed</span></span>
- <span data-ttu-id="0c07f-408">переименован файл</span><span class="sxs-lookup"><span data-stu-id="0c07f-408">file renamed</span></span>
- <span data-ttu-id="0c07f-409">файл скопирован в сетевую папку</span><span class="sxs-lookup"><span data-stu-id="0c07f-409">file copied to network share</span></span>
- <span data-ttu-id="0c07f-410">файл, доступный в незаверяемом приложении</span><span class="sxs-lookup"><span data-stu-id="0c07f-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="0c07f-411">Применена метка хранения</span><span class="sxs-lookup"><span data-stu-id="0c07f-411">Retention label applied</span></span> 

<span data-ttu-id="0c07f-412">Это событие создается каждый раз, когда документ без маркировки или отправка электронной почты с меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="0c07f-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="0c07f-413">Он фиксируется во время сохранения документа и во время отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c07f-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="0c07f-414">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-414">Source</span></span>  |<span data-ttu-id="0c07f-415">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="0c07f-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-416">Exchange</span></span>         |<span data-ttu-id="0c07f-417">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-417">no</span></span>       |
|<span data-ttu-id="0c07f-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0c07f-418">SharePoint Online</span></span>|<span data-ttu-id="0c07f-419">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-419">yes</span></span>          |
|<span data-ttu-id="0c07f-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-420">OneDrive</span></span> |<span data-ttu-id="0c07f-421">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="0c07f-422">Метка хранения изменена</span><span class="sxs-lookup"><span data-stu-id="0c07f-422">Retention label changed</span></span>

<span data-ttu-id="0c07f-423">Это событие создается каждый раз, когда метка обновляется в документе или электронной почте.</span><span class="sxs-lookup"><span data-stu-id="0c07f-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="0c07f-424">Он фиксируется во время сохранения документа и во время отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c07f-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="0c07f-425">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-425">Source</span></span>  |<span data-ttu-id="0c07f-426">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="0c07f-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-427">Exchange</span></span>         |<span data-ttu-id="0c07f-428">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-428">no</span></span>       |
|<span data-ttu-id="0c07f-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0c07f-429">SharePoint Online</span></span>|<span data-ttu-id="0c07f-430">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-430">yes</span></span>          |
|<span data-ttu-id="0c07f-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-431">OneDrive</span></span> |<span data-ttu-id="0c07f-432">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="0c07f-433">Метка хранения удалена</span><span class="sxs-lookup"><span data-stu-id="0c07f-433">Retention label removed</span></span>

<span data-ttu-id="0c07f-434">Это событие создается каждый раз, когда метка удаляется из файла или документа.</span><span class="sxs-lookup"><span data-stu-id="0c07f-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="0c07f-435">Он фиксируется во время сохранения документа и во время отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c07f-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="0c07f-436">Источник</span><span class="sxs-lookup"><span data-stu-id="0c07f-436">Source</span></span>  |<span data-ttu-id="0c07f-437">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="0c07f-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="0c07f-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="0c07f-438">Exchange</span></span>         |<span data-ttu-id="0c07f-439">нет</span><span class="sxs-lookup"><span data-stu-id="0c07f-439">no</span></span>       |
|<span data-ttu-id="0c07f-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0c07f-440">SharePoint Online</span></span>|<span data-ttu-id="0c07f-441">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-441">yes</span></span>          |
|<span data-ttu-id="0c07f-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c07f-442">OneDrive</span></span> |<span data-ttu-id="0c07f-443">да</span><span class="sxs-lookup"><span data-stu-id="0c07f-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="0c07f-444">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="0c07f-444">Known issues</span></span>
  
- <span data-ttu-id="0c07f-445">Когда рекомендуемый совет средства метки отображается конечному пользователю, он не захватывается.</span><span class="sxs-lookup"><span data-stu-id="0c07f-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="0c07f-446">Но если пользователь решил применить рекомендуемую метку, метка будет показана в поле *How applied* as *Recommended*</span><span class="sxs-lookup"><span data-stu-id="0c07f-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="0c07f-447">Текст обоснования в настоящее время не доступен для понижения метки конфиденциальности с Sharepoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0c07f-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="0c07f-448">Типы конфиденциальной информации в настоящее время недоступны для действий автолабелинга из Word, Excel, PowerPoint и Outlook, а также SharePoint Online и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0c07f-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
