---
title: Действия по маркировке, о чем сообщалось в обозревателе действий
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
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902954"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="2ca2b-103">Действия по маркировке, доступные в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="2ca2b-104">Метка "Чувствительность", примененная</span><span class="sxs-lookup"><span data-stu-id="2ca2b-104">Sensitivity label applied</span></span>

<span data-ttu-id="2ca2b-105">Это событие создается каждый раз, когда документ без маркировки или отправка электронной почты с меткой.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-105">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span> 

- <span data-ttu-id="2ca2b-106">Оно фиксируется во время сохранения в приложениях и веб-приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="2ca2b-107">Она фиксируется во время появления в надстройки для защиты информации Azure.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="2ca2b-108">Действия по обновлению и понижению меток также можно отслеживать с помощью поля типа событий *Label* и фильтра.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="2ca2b-109">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-109">Source</span></span>  |<span data-ttu-id="2ca2b-110">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-110">Reported in activity explorer</span></span> | <span data-ttu-id="2ca2b-111">Примечание</span><span class="sxs-lookup"><span data-stu-id="2ca2b-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="2ca2b-112">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="2ca2b-113">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-113">yes</span></span> |
|<span data-ttu-id="2ca2b-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-114">Outlook</span></span>| <span data-ttu-id="2ca2b-115">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-115">yes</span></span> |<span data-ttu-id="2ca2b-116">из Win 32</span><span class="sxs-lookup"><span data-stu-id="2ca2b-116">from Win 32</span></span> |
|<span data-ttu-id="2ca2b-117">SharePoint online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="2ca2b-118">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-118">yes</span></span> | |
|<span data-ttu-id="2ca2b-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-119">Exchange</span></span>        |<span data-ttu-id="2ca2b-120">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-120">yes</span></span>         | |
|<span data-ttu-id="2ca2b-121">Унифицированный клиент Azure Information Protection (AIP) и единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="2ca2b-122">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-122">yes</span></span> |<span data-ttu-id="2ca2b-123">действие новой *метки* AIP сопоположено с *меткой, примененной* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="2ca2b-124">Microsoft information protection (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="2ca2b-125">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-125">yes</span></span>|<span data-ttu-id="2ca2b-126">действие новой *метки* AIP сопоположено с *меткой, примененной* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="2ca2b-127">Служба управления правами (RMS)</span><span class="sxs-lookup"><span data-stu-id="2ca2b-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="2ca2b-128">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-128">not applicable</span></span>         | |
|<span data-ttu-id="2ca2b-129">Power BI desktop and web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-129">Power BI desktop and web</span></span>        | <span data-ttu-id="2ca2b-130">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-130">no</span></span>| <span data-ttu-id="2ca2b-131">доступны в журналах аудита Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ca2b-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="2ca2b-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="2ca2b-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="2ca2b-133">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="2ca2b-134">Метка "Чувствительность" изменена</span><span class="sxs-lookup"><span data-stu-id="2ca2b-134">Sensitivity label changed</span></span>

<span data-ttu-id="2ca2b-135">Это событие создается каждый раз, когда метка обновляется в документе или электронной почте.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-135">This event is generated each time a label is updated on the document or email.</span></span>

- <span data-ttu-id="2ca2b-136">Для единого клиента AIP, источников единого сканера и SDK  *MIP* метка обновления AIP и карты действий метки понижения до метки обозревателя *действий изменены.*</span><span class="sxs-lookup"><span data-stu-id="2ca2b-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="2ca2b-137">Он фиксируется в точке сохранения в приложениях Office и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="2ca2b-138">Он фиксируется во время появления в Azure Information Protection унифицированных клиентских надстройок и правоохранительных органов сканера.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="2ca2b-139">Действия по обновлению и понижению меток также можно отслеживать с помощью поля типа событий *Label* и фильтра.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="2ca2b-140">Текст *обоснования* также захвачен, за исключением SharePoint Online и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="2ca2b-141">Метка конфиденциальности, сделанная в родных приложениях Office в Outlook, собирает последнее действие, которое было сгенерировано до сохранения файлов или действий отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="2ca2b-142">Например, если перед отправкой пользователь несколько раз меняет метку на электронной почте, последняя метка, найденная в электронной почте при отправке, запечатлена в журнале аудита и затем сообщается в проводнике действий.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="2ca2b-143">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-143">Source</span></span>  |<span data-ttu-id="2ca2b-144">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-144">Reported in activity explorer</span></span>|<span data-ttu-id="2ca2b-145">Примечание</span><span class="sxs-lookup"><span data-stu-id="2ca2b-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2ca2b-146">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2ca2b-147">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-147">yes</span></span>         |
|<span data-ttu-id="2ca2b-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-148">Outlook</span></span>         |<span data-ttu-id="2ca2b-149">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-149">yes</span></span>         |<span data-ttu-id="2ca2b-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="2ca2b-150">Win 32</span></span>|
|<span data-ttu-id="2ca2b-151">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2ca2b-152">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-152">yes</span></span>         |
|<span data-ttu-id="2ca2b-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-153">Exchange</span></span>         |<span data-ttu-id="2ca2b-154">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-154">yes</span></span>         |
|<span data-ttu-id="2ca2b-155">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-155">AIP unified client</span></span>         |<span data-ttu-id="2ca2b-156">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-156">yes</span></span>         |
|<span data-ttu-id="2ca2b-157">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-157">AIP unified scanner</span></span>         |<span data-ttu-id="2ca2b-158">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-158">yes</span></span>         |
|<span data-ttu-id="2ca2b-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-159">MIP SDK</span></span>         |<span data-ttu-id="2ca2b-160">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-160">yes</span></span>         |
|<span data-ttu-id="2ca2b-161">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-161">RMS service</span></span>         |<span data-ttu-id="2ca2b-162">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-162">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-163">Power BI desktop and Web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="2ca2b-164">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-164">no</span></span>         |<span data-ttu-id="2ca2b-165">доступны в журналах аудита Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ca2b-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="2ca2b-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-166">MCAS</span></span>     |<span data-ttu-id="2ca2b-167">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="2ca2b-168">Метка конфиденциальности удалена</span><span class="sxs-lookup"><span data-stu-id="2ca2b-168">Sensitivity label removed</span></span>

<span data-ttu-id="2ca2b-169">Это событие создается каждый раз, когда метка удаляется из файла или документа.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-169">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="2ca2b-170">Это событие фиксируется во время сохранения в родных приложениях и веб-приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="2ca2b-171">Она фиксируется во время появления в надстройки для защиты информации Azure.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="2ca2b-172">Метка конфиденциальности с меткой Office на основе MIP в Outlook собирает последнее событие метки, которое было сгенерировано до сохранения файлов или действий отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="2ca2b-173">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-173">Source</span></span>  |<span data-ttu-id="2ca2b-174">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-174">Reported in activity explorer</span></span> | <span data-ttu-id="2ca2b-175">Примечание</span><span class="sxs-lookup"><span data-stu-id="2ca2b-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2ca2b-176">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2ca2b-177">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-177">yes</span></span>         |
|<span data-ttu-id="2ca2b-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-178">Outlook</span></span>         |<span data-ttu-id="2ca2b-179">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-179">yes</span></span>         |<span data-ttu-id="2ca2b-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="2ca2b-180">Win 32</span></span>|
|<span data-ttu-id="2ca2b-181">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2ca2b-182">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-182">yes</span></span>         |
|<span data-ttu-id="2ca2b-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-183">Exchange</span></span>         |<span data-ttu-id="2ca2b-184">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-184">yes</span></span>         |
|<span data-ttu-id="2ca2b-185">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-185">AIP unified client</span></span>         |<span data-ttu-id="2ca2b-186">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-186">yes</span></span>         |<span data-ttu-id="2ca2b-187">действие AIP *по удалению метки* сопостраняется с действием *метки, удаленным* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="2ca2b-188">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-188">AIP unified scanner</span></span>         |<span data-ttu-id="2ca2b-189">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-189">yes</span></span>         |<span data-ttu-id="2ca2b-190">действие AIP *по удалению метки* сопостраняется с действием *метки, удаленным* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="2ca2b-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-191">MIP SDK</span></span>         |<span data-ttu-id="2ca2b-192">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-192">yes</span></span>         |<span data-ttu-id="2ca2b-193">действие AIP *по удалению метки* сопостраняется с действием *метки, удаленным* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="2ca2b-194">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-194">RMS service</span></span>         |<span data-ttu-id="2ca2b-195">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-195">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-196">Power BI desktop and Web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="2ca2b-197">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-197">no</span></span>         |<span data-ttu-id="2ca2b-198">доступны в журналах аудита Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ca2b-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="2ca2b-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-199">MCAS</span></span>     |<span data-ttu-id="2ca2b-200">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="2ca2b-201">Чтение файла метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="2ca2b-201">Sensitivity label file read</span></span>

<span data-ttu-id="2ca2b-202">Это событие создается каждый раз, когда открывается защищенный или помеченный документ.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-202">This event is generated each time a labeled or protected document is opened.</span></span>

|<span data-ttu-id="2ca2b-203">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-203">Source</span></span>  |<span data-ttu-id="2ca2b-204">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-204">Reported in activity explorer</span></span> | <span data-ttu-id="2ca2b-205">Примечание</span><span class="sxs-lookup"><span data-stu-id="2ca2b-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2ca2b-206">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2ca2b-207">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-207">yes</span></span>         |
|<span data-ttu-id="2ca2b-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-208">Outlook</span></span>         |<span data-ttu-id="2ca2b-209">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-209">no</span></span>         |
|<span data-ttu-id="2ca2b-210">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2ca2b-211">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-211">no</span></span>         |
|<span data-ttu-id="2ca2b-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-212">Exchange</span></span>         |<span data-ttu-id="2ca2b-213">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-213">no</span></span>         |
|<span data-ttu-id="2ca2b-214">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-214">AIP unified client</span></span>         |<span data-ttu-id="2ca2b-215">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-215">yes</span></span>         |<span data-ttu-id="2ca2b-216">действие доступа *AIP* сопоно  с действием чтения файла в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="2ca2b-217">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-217">AIP unified scanner</span></span>         |<span data-ttu-id="2ca2b-218">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-218">yes</span></span>         |<span data-ttu-id="2ca2b-219">действие доступа *AIP* сопоно  с действием чтения файла в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="2ca2b-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-220">MIP SDK</span></span>         |<span data-ttu-id="2ca2b-221">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-221">yes</span></span>         |<span data-ttu-id="2ca2b-222">действие доступа *AIP* сопоно  с действием чтения файла в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="2ca2b-223">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-223">RMS service</span></span>         |<span data-ttu-id="2ca2b-224">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-224">yes</span></span>         |<span data-ttu-id="2ca2b-225">действие *доступа* соотнося с действием чтения *файла* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="2ca2b-226">Power BI desktop and Web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="2ca2b-227">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-227">no</span></span>         |<span data-ttu-id="2ca2b-228">доступны в журналах аудита Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ca2b-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="2ca2b-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-229">MCAS</span></span>     |<span data-ttu-id="2ca2b-230">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-230">no</span></span>         |         |


## <a name="sensitivity-label-files-discovered"></a><span data-ttu-id="2ca2b-231">Обнаруженные файлы меток чувствительности</span><span class="sxs-lookup"><span data-stu-id="2ca2b-231">Sensitivity label files discovered</span></span>

<span data-ttu-id="2ca2b-232">Это событие создается каждый раз, когда файлы обнаруживаются при том, что сканер AIP используется для сканирования конфиденциальных данных в различных местах и обнаружения файлов.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="2ca2b-233">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-233">Source</span></span>  |<span data-ttu-id="2ca2b-234">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-234">Reported in activity explorer</span></span> | <span data-ttu-id="2ca2b-235">Примечание</span><span class="sxs-lookup"><span data-stu-id="2ca2b-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2ca2b-236">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2ca2b-237">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-237">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-238">Outlook</span></span>         |<span data-ttu-id="2ca2b-239">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-239">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-240">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2ca2b-241">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-241">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-242">Exchange</span></span>         |<span data-ttu-id="2ca2b-243">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-243">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-244">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-244">AIP unified client</span></span>         |<span data-ttu-id="2ca2b-245">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-245">not applicable</span></span>       |
|<span data-ttu-id="2ca2b-246">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-246">AIP unified scanner</span></span>         |<span data-ttu-id="2ca2b-247">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-247">yes</span></span>         |<span data-ttu-id="2ca2b-248">действие обнаружения *AIP* сопопоясается с *файлами,* обнаруженными в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="2ca2b-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-249">MIP SDK</span></span>         |<span data-ttu-id="2ca2b-250">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-250">yes</span></span>         |<span data-ttu-id="2ca2b-251">действие обнаружения *AIP* сопопослано действию *обнаруженного файла* в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="2ca2b-252">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-252">RMS service</span></span>         |<span data-ttu-id="2ca2b-253">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-253">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-254">Power BI desktop and Web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="2ca2b-255">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-255">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-256">MCAS</span></span>     |<span data-ttu-id="2ca2b-257">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="2ca2b-258">Переименован файл метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="2ca2b-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="2ca2b-259">Это событие создается при каждом переименовании документа с меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="2ca2b-260">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-260">Source</span></span>  | <span data-ttu-id="2ca2b-261">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-261">Reported in activity explorer</span></span> | <span data-ttu-id="2ca2b-262">Примечание</span><span class="sxs-lookup"><span data-stu-id="2ca2b-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2ca2b-263">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2ca2b-264">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-264">yes</span></span>         |
|<span data-ttu-id="2ca2b-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-265">Outlook</span></span>         |<span data-ttu-id="2ca2b-266">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-266">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-267">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2ca2b-268">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-268">no</span></span>        |
|<span data-ttu-id="2ca2b-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-269">Exchange</span></span>         |<span data-ttu-id="2ca2b-270">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-270">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-271">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-271">AIP unified client</span></span>         |<span data-ttu-id="2ca2b-272">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-272">no</span></span>         |
|<span data-ttu-id="2ca2b-273">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-273">AIP unified scanner</span></span>         |<span data-ttu-id="2ca2b-274">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-274">no</span></span>         |
|<span data-ttu-id="2ca2b-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-275">MIP SDK</span></span>         |<span data-ttu-id="2ca2b-276">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-276">no</span></span>         |
|<span data-ttu-id="2ca2b-277">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-277">RMS service</span></span>         |<span data-ttu-id="2ca2b-278">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-278">no</span></span>      |
|<span data-ttu-id="2ca2b-279">Power BI desktop and Web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="2ca2b-280">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-280">no</span></span>         |
|<span data-ttu-id="2ca2b-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-281">MCAS</span></span>     |<span data-ttu-id="2ca2b-282">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-282">no</span></span>         |         |


## <a name="sensitivity-label-file-removed"></a><span data-ttu-id="2ca2b-283">Удален файл метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="2ca2b-283">Sensitivity label file removed</span></span>

<span data-ttu-id="2ca2b-284">Это событие создается каждый раз, когда сканер AIP обнаруживает, что ранее отсканированный файл был удален.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="2ca2b-285">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-285">Source</span></span>  |<span data-ttu-id="2ca2b-286">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-286">Reported in activity explorer</span></span> | <span data-ttu-id="2ca2b-287">Примечание</span><span class="sxs-lookup"><span data-stu-id="2ca2b-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2ca2b-288">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2ca2b-289">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-289">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-290">Outlook</span></span>         |<span data-ttu-id="2ca2b-291">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-291">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-292">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2ca2b-293">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-293">not applicable</span></span>           |
|<span data-ttu-id="2ca2b-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-294">Exchange</span></span>         |<span data-ttu-id="2ca2b-295">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-295">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-296">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-296">AIP unified client</span></span>         |<span data-ttu-id="2ca2b-297">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-297">not applicable</span></span>            |
|<span data-ttu-id="2ca2b-298">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-298">AIP unified scanner</span></span>         |<span data-ttu-id="2ca2b-299">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-299">yes</span></span>         |
|<span data-ttu-id="2ca2b-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-300">MIP SDK</span></span>         |<span data-ttu-id="2ca2b-301">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-301">not applicable</span></span>            |
|<span data-ttu-id="2ca2b-302">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-302">RMS service</span></span>         |<span data-ttu-id="2ca2b-303">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-303">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-304">Power BI desktop and Web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="2ca2b-305">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-305">not applicable</span></span>  |
|<span data-ttu-id="2ca2b-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-306">MCAS</span></span>     |<span data-ttu-id="2ca2b-307">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-307">not applicable</span></span>        |         |

### <a name="sensitivity-label-protection-applied"></a><span data-ttu-id="2ca2b-308">Применена защита меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="2ca2b-308">Sensitivity label protection applied</span></span>

<span data-ttu-id="2ca2b-309">Это событие создается впервые, когда защита добавляется вручную к элементу, у него нет метки.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="2ca2b-310">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-310">Source</span></span>  |<span data-ttu-id="2ca2b-311">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-311">Reported in activity explorer</span></span> | <span data-ttu-id="2ca2b-312">Примечание</span><span class="sxs-lookup"><span data-stu-id="2ca2b-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2ca2b-313">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2ca2b-314">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-314">no</span></span>         |
|<span data-ttu-id="2ca2b-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-315">Outlook</span></span>         |<span data-ttu-id="2ca2b-316">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-316">no</span></span>         |
|<span data-ttu-id="2ca2b-317">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2ca2b-318">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-318">not applicable</span></span>           |
|<span data-ttu-id="2ca2b-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-319">Exchange</span></span>         |<span data-ttu-id="2ca2b-320">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-320">no</span></span>       |
|<span data-ttu-id="2ca2b-321">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-321">AIP unified client</span></span>         |<span data-ttu-id="2ca2b-322">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-322">yes</span></span>            |
|<span data-ttu-id="2ca2b-323">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-323">AIP unified scanner</span></span>         |<span data-ttu-id="2ca2b-324">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-324">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-325">MIP SDK</span></span>         |<span data-ttu-id="2ca2b-326">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-326">yes</span></span>            |
|<span data-ttu-id="2ca2b-327">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-327">RMS service</span></span>         |<span data-ttu-id="2ca2b-328">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-328">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-329">Power BI desktop and Web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="2ca2b-330">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-330">not applicable</span></span>            |
|<span data-ttu-id="2ca2b-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-331">MCAS</span></span>     |<span data-ttu-id="2ca2b-332">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-332">not applicable</span></span>        |         |

## <a name="sensitivity-label-protection-changed"></a><span data-ttu-id="2ca2b-333">Изменена защита меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="2ca2b-333">Sensitivity label protection changed</span></span>

<span data-ttu-id="2ca2b-334">Это событие создается каждый раз, когда защита на ненаблюдном документе меняется вручную.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="2ca2b-335">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-335">Source</span></span>  |<span data-ttu-id="2ca2b-336">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2ca2b-337">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2ca2b-338">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-338">no</span></span>         |
|<span data-ttu-id="2ca2b-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-339">Outlook</span></span>         |<span data-ttu-id="2ca2b-340">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-340">no</span></span>         |
|<span data-ttu-id="2ca2b-341">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2ca2b-342">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-342">not applicable</span></span>           |
|<span data-ttu-id="2ca2b-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-343">Exchange</span></span>         |<span data-ttu-id="2ca2b-344">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-344">no</span></span>       |
|<span data-ttu-id="2ca2b-345">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-345">AIP unified client</span></span>         |<span data-ttu-id="2ca2b-346">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-346">yes</span></span>            |
|<span data-ttu-id="2ca2b-347">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-347">AIP unified scanner</span></span>         |<span data-ttu-id="2ca2b-348">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-348">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-349">MIP SDK</span></span>         |<span data-ttu-id="2ca2b-350">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-350">yes</span></span>            |
|<span data-ttu-id="2ca2b-351">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-351">RMS service</span></span>         |<span data-ttu-id="2ca2b-352">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-352">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-353">Power BI desktop and Web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="2ca2b-354">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-354">not applicable</span></span>            |
|<span data-ttu-id="2ca2b-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-355">MCAS</span></span>     |<span data-ttu-id="2ca2b-356">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-356">not applicable</span></span>        |

## <a name="sensitivity-label-protection-removed"></a><span data-ttu-id="2ca2b-357">Удалена защита меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="2ca2b-357">Sensitivity label protection removed</span></span>

<span data-ttu-id="2ca2b-358">Это событие создается каждый раз, когда защита на ненаблюдном документе меняется вручную.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="2ca2b-359">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-359">Source</span></span>  |<span data-ttu-id="2ca2b-360">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2ca2b-361">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2ca2b-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2ca2b-362">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-362">no</span></span>         |
|<span data-ttu-id="2ca2b-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca2b-363">Outlook</span></span>         |<span data-ttu-id="2ca2b-364">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-364">no</span></span>         |
|<span data-ttu-id="2ca2b-365">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2ca2b-366">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-366">not applicable</span></span>           |
|<span data-ttu-id="2ca2b-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-367">Exchange</span></span>         |<span data-ttu-id="2ca2b-368">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-368">no</span></span>       |
|<span data-ttu-id="2ca2b-369">Единый клиент AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-369">AIP unified client</span></span>         |<span data-ttu-id="2ca2b-370">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-370">yes</span></span>            |
|<span data-ttu-id="2ca2b-371">Единый сканер AIP</span><span class="sxs-lookup"><span data-stu-id="2ca2b-371">AIP unified scanner</span></span>         |<span data-ttu-id="2ca2b-372">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-372">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2ca2b-373">MIP SDK</span></span>         |<span data-ttu-id="2ca2b-374">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-374">yes</span></span>            |
|<span data-ttu-id="2ca2b-375">Служба RMS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-375">RMS service</span></span>         |<span data-ttu-id="2ca2b-376">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-376">not applicable</span></span>         |
|<span data-ttu-id="2ca2b-377">Power BI desktop and Web</span><span class="sxs-lookup"><span data-stu-id="2ca2b-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="2ca2b-378">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-378">not applicable</span></span>            |
|<span data-ttu-id="2ca2b-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-379">MCAS</span></span>     |<span data-ttu-id="2ca2b-380">неприменимо</span><span class="sxs-lookup"><span data-stu-id="2ca2b-380">not applicable</span></span>        |

## <a name="sensitivity-label-dlp-policy-matched"></a><span data-ttu-id="2ca2b-381">Политика DLP метки конфиденциальности соответствует</span><span class="sxs-lookup"><span data-stu-id="2ca2b-381">Sensitivity label DLP policy matched</span></span>

<span data-ttu-id="2ca2b-382">Это событие создается при каждом совпадении политики DLP.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-382">This event is generated each time a DLP policy is matched.</span></span>

|<span data-ttu-id="2ca2b-383">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-383">Source</span></span>  |<span data-ttu-id="2ca2b-384">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2ca2b-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-385">Exchange</span></span>         |<span data-ttu-id="2ca2b-386">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-386">yes</span></span>       |
|<span data-ttu-id="2ca2b-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2ca2b-387">SharePoint Online</span></span>|<span data-ttu-id="2ca2b-388">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-388">yes</span></span>          |
|<span data-ttu-id="2ca2b-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-389">OneDrive</span></span> |<span data-ttu-id="2ca2b-390">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-390">yes</span></span>|
|<span data-ttu-id="2ca2b-391">Teams</span><span class="sxs-lookup"><span data-stu-id="2ca2b-391">Teams</span></span> |<span data-ttu-id="2ca2b-392">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-392">yes</span></span>   |
|<span data-ttu-id="2ca2b-393">устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="2ca2b-393">Windows 10 devices</span></span>         |<span data-ttu-id="2ca2b-394">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-394">yes</span></span> |
|<span data-ttu-id="2ca2b-395">MAC</span><span class="sxs-lookup"><span data-stu-id="2ca2b-395">MAC</span></span>         |<span data-ttu-id="2ca2b-396">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-396">no</span></span>     |
|<span data-ttu-id="2ca2b-397">локальное</span><span class="sxs-lookup"><span data-stu-id="2ca2b-397">on-premises</span></span>         |<span data-ttu-id="2ca2b-398">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-398">no</span></span>|
|<span data-ttu-id="2ca2b-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="2ca2b-399">MCAS</span></span>     |<span data-ttu-id="2ca2b-400">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-400">no</span></span>        | 

<span data-ttu-id="2ca2b-401">События для устройств с Windows 10 (конечная точка DLP) являются:</span><span class="sxs-lookup"><span data-stu-id="2ca2b-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="2ca2b-402">удаленный файл</span><span class="sxs-lookup"><span data-stu-id="2ca2b-402">file deleted</span></span>
- <span data-ttu-id="2ca2b-403">созданный файл</span><span class="sxs-lookup"><span data-stu-id="2ca2b-403">file created</span></span>
- <span data-ttu-id="2ca2b-404">файл скопирован в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="2ca2b-404">file copied to clipboard</span></span>
- <span data-ttu-id="2ca2b-405">изменение файла</span><span class="sxs-lookup"><span data-stu-id="2ca2b-405">file modified</span></span>
- <span data-ttu-id="2ca2b-406">чтение файла</span><span class="sxs-lookup"><span data-stu-id="2ca2b-406">file read</span></span>
- <span data-ttu-id="2ca2b-407">файл распечатан</span><span class="sxs-lookup"><span data-stu-id="2ca2b-407">file printed</span></span>
- <span data-ttu-id="2ca2b-408">переименован файл</span><span class="sxs-lookup"><span data-stu-id="2ca2b-408">file renamed</span></span>
- <span data-ttu-id="2ca2b-409">файл скопирован в сетевую папку</span><span class="sxs-lookup"><span data-stu-id="2ca2b-409">file copied to network share</span></span>
- <span data-ttu-id="2ca2b-410">файл, доступный в незаверяемом приложении</span><span class="sxs-lookup"><span data-stu-id="2ca2b-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="2ca2b-411">Применена метка хранения</span><span class="sxs-lookup"><span data-stu-id="2ca2b-411">Retention label applied</span></span> 

<span data-ttu-id="2ca2b-412">Это событие создается каждый раз, когда документ без маркировки или отправка электронной почты с меткой.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-412">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span>

- <span data-ttu-id="2ca2b-413">Оно фиксируется во время сохранения в приложениях и веб-приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-413">It is captured at the time of save in Office native applications and web applications.</span></span>

|<span data-ttu-id="2ca2b-414">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-414">Source</span></span>  |<span data-ttu-id="2ca2b-415">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2ca2b-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-416">Exchange</span></span>         |<span data-ttu-id="2ca2b-417">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-417">no</span></span>       |
|<span data-ttu-id="2ca2b-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2ca2b-418">SharePoint Online</span></span>|<span data-ttu-id="2ca2b-419">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-419">yes</span></span>          |
|<span data-ttu-id="2ca2b-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-420">OneDrive</span></span> |<span data-ttu-id="2ca2b-421">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="2ca2b-422">Метка хранения изменена</span><span class="sxs-lookup"><span data-stu-id="2ca2b-422">Retention label changed</span></span>

<span data-ttu-id="2ca2b-423">Это событие создается каждый раз, когда метка обновляется в документе или электронной почте.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="2ca2b-424">Он захватывается во время сохранения.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-424">It is captured at the time of save.</span></span>

|<span data-ttu-id="2ca2b-425">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-425">Source</span></span>  |<span data-ttu-id="2ca2b-426">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2ca2b-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-427">Exchange</span></span>         |<span data-ttu-id="2ca2b-428">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-428">no</span></span>       |
|<span data-ttu-id="2ca2b-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2ca2b-429">SharePoint Online</span></span>|<span data-ttu-id="2ca2b-430">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-430">yes</span></span>          |
|<span data-ttu-id="2ca2b-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-431">OneDrive</span></span> |<span data-ttu-id="2ca2b-432">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="2ca2b-433">Метка хранения удалена</span><span class="sxs-lookup"><span data-stu-id="2ca2b-433">Retention label removed</span></span>

<span data-ttu-id="2ca2b-434">Это событие создается каждый раз, когда метка удаляется из файла или документа.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="2ca2b-435">Он захватывается во время сохранения.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-435">It is captured at the time of save.</span></span>

|<span data-ttu-id="2ca2b-436">Source</span><span class="sxs-lookup"><span data-stu-id="2ca2b-436">Source</span></span>  |<span data-ttu-id="2ca2b-437">Сообщается в проводнике действий</span><span class="sxs-lookup"><span data-stu-id="2ca2b-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2ca2b-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ca2b-438">Exchange</span></span>         |<span data-ttu-id="2ca2b-439">нет</span><span class="sxs-lookup"><span data-stu-id="2ca2b-439">no</span></span>       |
|<span data-ttu-id="2ca2b-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2ca2b-440">SharePoint Online</span></span>|<span data-ttu-id="2ca2b-441">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-441">yes</span></span>          |
|<span data-ttu-id="2ca2b-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ca2b-442">OneDrive</span></span> |<span data-ttu-id="2ca2b-443">да</span><span class="sxs-lookup"><span data-stu-id="2ca2b-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="2ca2b-444">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="2ca2b-444">Known issues</span></span>
  
- <span data-ttu-id="2ca2b-445">Когда рекомендуемый совет средства метки отображается конечному пользователю, он не захватывается.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="2ca2b-446">Но если пользователь решил применить рекомендуемую метку, метка будет показана в поле *How applied* as *Recommended*</span><span class="sxs-lookup"><span data-stu-id="2ca2b-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="2ca2b-447">Текст обоснования в настоящее время не доступен для понижения метки конфиденциальности с Sharepoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="2ca2b-448">В настоящее время типы конфиденциальной информации недоступны для действий автолабелинга из Word, Excel, PowerPoint и Outlook, а также SharePoint Online и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2ca2b-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
