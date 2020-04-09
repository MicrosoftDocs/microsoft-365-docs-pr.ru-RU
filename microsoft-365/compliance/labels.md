---
title: Обзор меток хранения
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Используйте метки хранения, чтобы классифицировать данные в организации для системы управления и применять правила хранения на основе этой классификации. Вы также можете использовать метки хранения для внедрения решения по управлению записями для Microsoft 365.
ms.openlocfilehash: 720a5b0b2fca16701dd4c2a752ac31b81e2233ab
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189066"
---
# <a name="overview-of-retention-labels"></a><span data-ttu-id="0e75d-104">Обзор меток хранения</span><span class="sxs-lookup"><span data-stu-id="0e75d-104">Overview of retention labels</span></span>

><span data-ttu-id="0e75d-105">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="0e75d-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0e75d-p102">В вашей организации наверняка есть контент различных типов, с которым требуется выполнять разные действия для соблюдения отраслевых нормативов и внутренних политик. Например, у вас могут быть:</span><span class="sxs-lookup"><span data-stu-id="0e75d-p102">Across your organization, you probably have different types of content that require different actions taken on them in order to comply with industry regulations and internal policies. For example, you might have:</span></span>
  
- <span data-ttu-id="0e75d-108">налоговые декларации, которые необходимо **хранить** не меньше определенного срока;</span><span class="sxs-lookup"><span data-stu-id="0e75d-108">Tax forms that need to be **retained** for a minimum period of time.</span></span> 
    
- <span data-ttu-id="0e75d-109">материалы для прессы, которые требуется **безвозвратно удалять** по достижении определенной давности;</span><span class="sxs-lookup"><span data-stu-id="0e75d-109">Press materials that need to be **permanently deleted** when they reach a certain age.</span></span> 
    
- <span data-ttu-id="0e75d-110">исследования конкурентов, которые требуется **сохранять**, а затем **окончательно удалять**;</span><span class="sxs-lookup"><span data-stu-id="0e75d-110">Competitive research that needs to be both **retained** and then **permanently deleted**.</span></span> 
    
- <span data-ttu-id="0e75d-111">рабочие визы, которые требуется **отмечать как записи**, чтобы их невозможно было редактировать и удалять.</span><span class="sxs-lookup"><span data-stu-id="0e75d-111">Work visas that must be **marked as a record** so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="0e75d-p103">Во всех вышеописанных случаях метки хранения в Office 365 помогут вам выполнять с контентом действия, соответствующие его характеру. Используя метки хранения, вы можете классифицировать данные в организации для системы управления и применять правила хранения на основе этой классификации.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p103">In all of these cases, retention labels in Office 365 can help you take the right actions on the right content. With retention labels, you can classify data across your organization for governance, and enforce retention rules based on that classification.</span></span>
  
<span data-ttu-id="0e75d-114">С помощью меток хранения вы можете:</span><span class="sxs-lookup"><span data-stu-id="0e75d-114">With retention labels, you can:</span></span>
  
- <span data-ttu-id="0e75d-p104">**Разрешить пользователям в организации вручную применять метки хранения** к содержимому в Outlook 2010 и более поздних версий, Outlook в Интернете, OneDrive, SharePoint и группах Office 365. Пользователи часто знают лучше других, с каким содержимым они работают, поэтому могут классифицировать его и применять соответствующие политики.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p104">**Enable people in your organization to apply a retention label manually** to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Office 365 groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate policy applied.</span></span> 
    
- <span data-ttu-id="0e75d-117">**Обеспечить автоматическое применение меток хранения к контенту**, если он соответствует определенным условиям, например если он содержит:</span><span class="sxs-lookup"><span data-stu-id="0e75d-117">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    
    - <span data-ttu-id="0e75d-118">конфиденциальную информацию определенных типов;</span><span class="sxs-lookup"><span data-stu-id="0e75d-118">Specific types of sensitive information.</span></span>
    
    - <span data-ttu-id="0e75d-119">определенные ключевые слова, соответствующие созданному запросу.</span><span class="sxs-lookup"><span data-stu-id="0e75d-119">Specific keywords that match a query you create.</span></span>
    
    - <span data-ttu-id="0e75d-120">совпадения с шаблоном для обучаемого классификатора.</span><span class="sxs-lookup"><span data-stu-id="0e75d-120">Pattern matches for a trainable classifier.</span></span>
    
  <span data-ttu-id="0e75d-121">Возможность автоматически применять метки хранения к контенту важна, потому что:</span><span class="sxs-lookup"><span data-stu-id="0e75d-121">The ability to apply retention labels to content automatically is important because:</span></span>
    
     - <span data-ttu-id="0e75d-122">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="0e75d-122">You don't need to train your users on all of your classifications.</span></span>
    
     - <span data-ttu-id="0e75d-123">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="0e75d-123">You don't need to rely on users to classify all content correctly.</span></span>
    
   - <span data-ttu-id="0e75d-124">пользователям больше не нужно будет знать о политиках управления данными — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="0e75d-124">Users no longer need to know about data governance policies - they can instead focus on their work.</span></span>

- <span data-ttu-id="0e75d-p105">**Выполнять управление записями в рамках Office 365**, включая электронную почту и документы. С помощью метки хранения вы можете классифицировать контент как запись. При этом метку невозможно изменить или удалить, как и сам контент.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p105">**Implement records management across Office 365**, including both email and documents. You can use a retention label to classify content as a record. When this happens, the label can't be changed or removed, and the content can't be edited or deleted.</span></span> 

- <span data-ttu-id="0e75d-128">**Применить стандартную метку хранения к библиотеке документов, папке или набору документов** в SharePoint, чтобы все документы, поступающие в это расположение, наследовали эту метку.</span><span class="sxs-lookup"><span data-stu-id="0e75d-128">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that arrive in that location inherit the default retention label.</span></span>  
    
<span data-ttu-id="0e75d-129">Создавать метки хранения можно в Центре соответствия требованиям Microsoft 365, Центре безопасности Microsoft 365 или Центре безопасности и соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e75d-129">You create retention labels in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span>

## <a name="how-retention-labels-work-with-retention-label-policies"></a><span data-ttu-id="0e75d-130">Как работают метки хранения с политиками</span><span class="sxs-lookup"><span data-stu-id="0e75d-130">How retention labels work with retention label policies</span></span>

<span data-ttu-id="0e75d-131">Чтобы предоставить сотрудникам своей организации метки хранения, с помощью которых они смогут классифицировать содержимое, вы должны выполнить два действия: создать метки хранения, а затем опубликовать их в выбранном расположении.</span><span class="sxs-lookup"><span data-stu-id="0e75d-131">Making retention labels available to people in your organization so that they can classify content is a two-step process: first you create the retention labels, and then you publish them to the locations you choose.</span></span> <span data-ttu-id="0e75d-132">Когда вы публикуете метки хранения, создается политика меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-132">When you publish retention labels, a retention label policy gets created.</span></span>
  
![Схема ролей и задач для меток](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
<span data-ttu-id="0e75d-134">Метки хранения — это независимые многократно используемые стандартные блоки, включаемые в одну или несколько политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-134">Retention labels are independent, reusable building blocks that are included in one or more retention label policies.</span></span> <span data-ttu-id="0e75d-135">Основное назначение политики меток хранения состоит в группировке набора меток хранения и указании расположений, где эти метки должны отображаться.</span><span class="sxs-lookup"><span data-stu-id="0e75d-135">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span>
  
![Схема меток, политик и расположений](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. <span data-ttu-id="0e75d-137">Когда вы публикуете метки хранения, они тем самым включаются в соответствующую политику.</span><span class="sxs-lookup"><span data-stu-id="0e75d-137">When you publish retention labels, they're included in a retention label policy.</span></span> <span data-ttu-id="0e75d-138">Имена меток хранения являются неизменяемыми. Это означает, что их нельзя изменить после создания.</span><span class="sxs-lookup"><span data-stu-id="0e75d-138">Retention label names are immutable, which means that they and cannot be edited after they're created.</span></span>


2. <span data-ttu-id="0e75d-139">Одну и ту же метку хранения можно включить в несколько политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-139">A single retention label can be included in many retention label policies.</span></span>

3. <span data-ttu-id="0e75d-140">Одно и то же расположение можно включить в несколько политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-140">A single location can also be included in many retention label policies.</span></span>    
    
3. <span data-ttu-id="0e75d-141">Политики меток хранения задают расположения для публикации меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-141">Retention label policies specify the locations to publish the retention labels.</span></span>
    
## <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="0e75d-142">По одной метке хранения</span><span class="sxs-lookup"><span data-stu-id="0e75d-142">Only one retention label at a time</span></span>

<span data-ttu-id="0e75d-143">Важно понимать, что к такому контенту, как электронные письма и документы, можно применять только по одной метке хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-143">It's important to know that content like an email or document can have only a single retention label assigned to it at a time:</span></span>
  
- <span data-ttu-id="0e75d-144">Метки хранения, назначенные пользователями вручную, можно удалять и менять.</span><span class="sxs-lookup"><span data-stu-id="0e75d-144">For retention labels assigned manually by end users, people can remove or change the retention label that's assigned.</span></span>
    
- <span data-ttu-id="0e75d-145">Если контенту назначена автоматически применяемая метка, то пользователь может заменить ее на метку хранения, назначенную вручную.</span><span class="sxs-lookup"><span data-stu-id="0e75d-145">If content has an auto-apply label assigned, an auto-apply label can be replaced by a retention label assigned manually by an end user.</span></span>
    
- <span data-ttu-id="0e75d-146">Если пользователь вручную назначил метку хранения контенту, то автоматически применяемая метка не может заменить ее.</span><span class="sxs-lookup"><span data-stu-id="0e75d-146">If content has a retention label assigned manually by an end user, an auto-apply label cannot replace the manually assigned retention label.</span></span>
    
- <span data-ttu-id="0e75d-147">Если имеется ряд правил, назначающих автоматически применяемую метку, а контент соответствует условиям нескольких из них, назначается метка хранения самого старого правила.</span><span class="sxs-lookup"><span data-stu-id="0e75d-147">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule is assigned.</span></span>
    
<span data-ttu-id="0e75d-p109">Метки, назначаемые вручную, применяются явно. Автоматически применяемые метки назначаются неявно. Приоритет явной метки хранения выше, чем неявной. Дополнительные сведения см. в разделе [Принципы хранения и приоритеты](#the-principles-of-retention-or-what-takes-precedence) ниже.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p109">Manually assigned labels are explicitly assigned; auto-apply labels are implicitly assigned; an explicit retention label takes precedence over an implicit label. For more information, see the below section on [The principles of retention, or what takes precedence?](#the-principles-of-retention-or-what-takes-precedence).</span></span>

<span data-ttu-id="0e75d-p110">Все сведения этого раздела относятся только к меткам хранения. Обратите внимание, что в дополнение к одной метке хранения к элементу контента также может применяться одна метка конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p110">All the information in this section applies only to retention labels. Note that an item of content can also have one sensitivity label applied to it, in addition to one retention label.</span></span>
  
## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="0e75d-152">Срок вступления меток хранения в силу</span><span class="sxs-lookup"><span data-stu-id="0e75d-152">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="0e75d-153">При публикации автоматически применяемые метки хранения не сразу вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="0e75d-153">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="0e75d-154">Для начала необходимо синхронизировать политику меток с расположениями при помощи Центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="0e75d-154">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="0e75d-155">Затем в конкретном расположении может потребоваться некоторое время, чтобы опубликованные метки хранения стали доступными конечным пользователям или чтобы содержимому были автоматически присвоены соответствующие метки.</span><span class="sxs-lookup"><span data-stu-id="0e75d-155">Then the location may require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="0e75d-156">Необходимое для этого время зависит от расположения и типа метки хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-156">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="0e75d-157">Опубликованные метки хранения</span><span class="sxs-lookup"><span data-stu-id="0e75d-157">Published retention labels</span></span>

<span data-ttu-id="0e75d-p112">При публикации меток хранения в SharePoint или OneDrive могут потребоваться сутки, чтобы эти метки хранения стали видны пользователям. Кроме того, при публикации меток хранения в Exchange может потребоваться 7 дней, чтобы эти метки хранения стали видны пользователям, а почтовый ящик должен содержать не менее 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p112">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![Схема, иллюстрирующая, когда вручную применяемые метки вступают в силу](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="0e75d-161">Метки хранения, применяемые автоматически</span><span class="sxs-lookup"><span data-stu-id="0e75d-161">Auto-apply retention labels</span></span>

<span data-ttu-id="0e75d-162">Если метки хранения автоматически применяются к контенту, соответствующему определенным условиям, может потребоваться семь дней, чтобы метки хранения были применены ко всему существующему контенту, соответствующему условиям.</span><span class="sxs-lookup"><span data-stu-id="0e75d-162">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Схема, иллюстрирующая, когда автоматически применяемые метки вступают в силу](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="0e75d-164">Проверка состояния меток хранения, опубликованных в Exchange</span><span class="sxs-lookup"><span data-stu-id="0e75d-164">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="0e75d-p113">В Exchange Online метки хранения становятся доступны пользователям в ходе процесса, выполняемого каждые семь дней. С помощью Powershell можно узнать, когда этот процесс выполнялся в прошлый раз, и определить, когда он запустится снова.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p113">In Exchange Online, retention labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.</span></span>
  
1. <span data-ttu-id="0e75d-167">[Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="0e75d-167">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="0e75d-168">Выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="0e75d-168">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="0e75d-169">В результатах свойство `ELCLastSuccessTimeStamp` (UTC) показывает, когда система в последний раз обрабатывала ваш почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="0e75d-169">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="0e75d-170">Если этого не происходило с момента создания политики, метки не будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="0e75d-170">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="0e75d-171">Для принудительной обработки выполните команду `Start-ManagedFolderAssistant -Identity <user>`.</span><span class="sxs-lookup"><span data-stu-id="0e75d-171">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="0e75d-172">Если метки не отображаются в Outlook в Интернете, хотя они должны быть видны, очистите кэш браузера (CTRL+F5).</span><span class="sxs-lookup"><span data-stu-id="0e75d-172">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    
## <a name="retention-label-policies-and-locations"></a><span data-ttu-id="0e75d-173">Политики и расположения меток хранения</span><span class="sxs-lookup"><span data-stu-id="0e75d-173">Retention label policies and locations</span></span>

<span data-ttu-id="0e75d-174">Метки хранения различных типов можно публиковать в разных расположениях, зависящих от назначения метки хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-174">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="0e75d-175">**Тип метки хранения**</span><span class="sxs-lookup"><span data-stu-id="0e75d-175">**If the retention label is…**</span></span>|<span data-ttu-id="0e75d-176">**Сфера применения политики меток**</span><span class="sxs-lookup"><span data-stu-id="0e75d-176">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e75d-177">Публикуемая для пользователей</span><span class="sxs-lookup"><span data-stu-id="0e75d-177">Published to end users</span></span>  <br/> |<span data-ttu-id="0e75d-178">Exchange, SharePoint, OneDrive, группы Office 365</span><span class="sxs-lookup"><span data-stu-id="0e75d-178">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
|<span data-ttu-id="0e75d-179">Автоматически применяемая в соответствии с типами конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="0e75d-179">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="0e75d-180">Exchange (только ко всем почтовым ящикам), SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="0e75d-180">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="0e75d-181">Автоматически применяемая по запросу</span><span class="sxs-lookup"><span data-stu-id="0e75d-181">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="0e75d-182">Exchange, SharePoint, OneDrive, группы Office 365</span><span class="sxs-lookup"><span data-stu-id="0e75d-182">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
   
<span data-ttu-id="0e75d-183">В Exchange метки хранения (и для запросов, и для конфиденциальной информации) присваиваются автоматически только недавно отправленным сообщениям (данным при передаче), а не ко всем элементам в почтовом ящике (неактивным данным).</span><span class="sxs-lookup"><span data-stu-id="0e75d-183">In Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="0e75d-184">Кроме того, метки хранения для типов конфиденциальной информации могут автоматически присваиваться только всем почтовым ящикам: выбирать определенные почтовые ящики нельзя.</span><span class="sxs-lookup"><span data-stu-id="0e75d-184">Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="0e75d-185">Общедоступные папки Exchange и Skype не поддерживают метки.</span><span class="sxs-lookup"><span data-stu-id="0e75d-185">Exchange public folders and Skype do not support labels.</span></span>
  
## <a name="how-retention-labels-enforce-retention"></a><span data-ttu-id="0e75d-186">Как метки хранения способствуют хранению</span><span class="sxs-lookup"><span data-stu-id="0e75d-186">How retention labels enforce retention</span></span>

<span data-ttu-id="0e75d-187">С помощью меток хранения можно обеспечить выполнение тех же действий по хранению, что и с помощью политики хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-187">Retention labels can enforce the same retention actions that a retention policy can.</span></span> <span data-ttu-id="0e75d-188">Метки хранения позволяют реализовать сложный план работы с содержимым (или файлами).</span><span class="sxs-lookup"><span data-stu-id="0e75d-188">You can use retention labels to implement a sophisticated content plan (or file plan).</span></span> <span data-ttu-id="0e75d-189">Подробнее о том, как работают политики хранения, см. в статье [Общие сведения о политиках хранения](retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-189">For more information on how retention works, see [Overview of retention policies](retention-policies.md).</span></span>
  
<span data-ttu-id="0e75d-p117">Кроме того, для меток хранения предусмотрено два варианта хранения, недоступных в политиках хранения. С помощью метки хранения вы можете:</span><span class="sxs-lookup"><span data-stu-id="0e75d-p117">In addition, a retention label has two retention options that are available only in a retention label and not in a retention policy. With a retention label, you can:</span></span>
  
- <span data-ttu-id="0e75d-p118">вызвать проверку перед ликвидацией в конце периода хранения, чтобы документы SharePoint и OneDrive требовалось проверять перед удалением. Дополнительные сведения см. в статье [Общие сведения о проверках перед ликвидацией](disposition-reviews.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-p118">Trigger a disposition review at the end of the retention period, so that SharePoint and OneDrive documents must be reviewed before they can be deleted. For more information, see [Overview of disposition reviews](disposition-reviews.md).</span></span>
    
- <span data-ttu-id="0e75d-194">начинать период хранения с момента добавления метки к контенту, а не с момента создания контента или его последнего изменения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-194">Start the retention period from when the content was labeled, instead of the age of the content or when it was last modified.</span></span> <span data-ttu-id="0e75d-195">Этот вариант применяется только к контенту на сайтах SharePoint и в учетных записях OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0e75d-195">This option applies only to content in SharePoint sites and OneDrive accounts.</span></span> <span data-ttu-id="0e75d-196">Для электронной почты Exchange срок хранения всегда основывается на дате отправки или получения сообщения, независимо от того, какой вариант вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="0e75d-196">For Exchange email, the retention period is always based on the date when the message was sent or received, no matter which option you choose here.</span></span>
    
![Настройки хранения со специальными параметрами меток](../media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## <a name="where-published-retention-labels-can-appear-to-end-users"></a><span data-ttu-id="0e75d-198">Где пользователям видны опубликованные метки хранения</span><span class="sxs-lookup"><span data-stu-id="0e75d-198">Where published retention labels can appear to end users</span></span>

<span data-ttu-id="0e75d-199">Если пользователи назначают метку хранения контенту, ее можно опубликовать в:</span><span class="sxs-lookup"><span data-stu-id="0e75d-199">If your retention label will be assigned to content by end users, you can publish it to:</span></span>
  
- <span data-ttu-id="0e75d-200">Outlook в Интернете;</span><span class="sxs-lookup"><span data-stu-id="0e75d-200">Outlook on the web</span></span>
    
- <span data-ttu-id="0e75d-201">Outlook 2010 и более поздних версиях;</span><span class="sxs-lookup"><span data-stu-id="0e75d-201">Outlook 2010 and later</span></span>
    
- <span data-ttu-id="0e75d-202">OneDrive;</span><span class="sxs-lookup"><span data-stu-id="0e75d-202">OneDrive</span></span>
    
- <span data-ttu-id="0e75d-203">SharePoint;</span><span class="sxs-lookup"><span data-stu-id="0e75d-203">SharePoint</span></span>
    
- <span data-ttu-id="0e75d-204">группах Office 365 (как на сайте группы, так и в ее почтовом ящике в Outlook в Интернете).</span><span class="sxs-lookup"><span data-stu-id="0e75d-204">Office 365 groups (both the group site and group mailbox in Outlook on the web)</span></span>
    
<span data-ttu-id="0e75d-205">В последующих разделах описано, как метки отображаются в различных приложениях для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0e75d-205">The sections that follow explain how labels appear in different apps to people in your organization.</span></span>
  
### <a name="outlook-on-the-web"></a><span data-ttu-id="0e75d-206">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="0e75d-206">Outlook on the web</span></span>

<span data-ttu-id="0e75d-207">Чтобы назначить метку элементу в Outlook в Интернете, щелкните его правой кнопкой мыши, нажмите **Назначить политику** и выберите метку хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-207">To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label.</span></span> 
  
![Меню назначения политики в Outlook в Интернете](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
<span data-ttu-id="0e75d-p120">После применения метки хранения ее описание и выполняемые ею действия отображаются в верхней части описания элемента. Если сообщение классифицировано и с ним связан период хранения, вы можете сразу понять, когда истекает срок его действия.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p120">After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.</span></span>
  
![Метка, назначенная электронному сообщению в Outlook в Интернете](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
<span data-ttu-id="0e75d-212">Вы также можете применять метки хранения к папкам. В этом случае:</span><span class="sxs-lookup"><span data-stu-id="0e75d-212">You can also apply retention labels to folders, in which case:</span></span>
  
- <span data-ttu-id="0e75d-p121">ко всем элементам в папке автоматически применяется одна и та же метка хранения, **за исключением** элементов, к которым явно применены другие метки хранения. У таких элементов остаются имеющиеся метки хранения. Дополнительные сведения см. ниже в разделе, посвященном принципам хранения;</span><span class="sxs-lookup"><span data-stu-id="0e75d-p121">All items in the folder automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing retention label. For more information, see the below section on the principles of retention.</span></span> 
    
- <span data-ttu-id="0e75d-216">если изменить или удалить используемую по умолчанию метку хранения папки, также меняются или удаляются метки хранения всех элементов в этой папке, **кроме** элементов с явными метками хранения;</span><span class="sxs-lookup"><span data-stu-id="0e75d-216">If you change or remove the default retention label for a folder, the retention label's also changed or removed for all items in the folder, **except** items with explicit retention labels.</span></span> 
    
- <span data-ttu-id="0e75d-217">если переместить элемент с меткой хранения по умолчанию в другую папку, к которой по умолчанию применяется другая метка хранения, к элементу будет применена новая метка хранения по умолчанию;</span><span class="sxs-lookup"><span data-stu-id="0e75d-217">If you move an item with a default retention label from one folder to another folder with a different default retention label, the item gets the new default retention label.</span></span>
    
- <span data-ttu-id="0e75d-218">если переместить элемент с меткой хранения по умолчанию в другую папку без метки хранения по умолчанию, старая метка хранения по умолчанию удаляется.</span><span class="sxs-lookup"><span data-stu-id="0e75d-218">If you move an item with a default retention label from one folder to another folder with no default retention label, the old default retention label is removed.</span></span>
    
### <a name="outlook-2010-and-later"></a><span data-ttu-id="0e75d-219">Outlook 2010 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="0e75d-219">Outlook 2010 and later</span></span>

<span data-ttu-id="0e75d-220">Чтобы присвоить элементу метку в классическом клиенте Outlook, выберите элемент.</span><span class="sxs-lookup"><span data-stu-id="0e75d-220">To label an item in the Outlook desktop client, select the item.</span></span> <span data-ttu-id="0e75d-221">На вкладке **Главная** на ленте щелкните **Назначить политику**, а затем выберите метку хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-221">On the **Home** tab on the ribbon, click **Assign Policy**, and then choose the retention label.</span></span> 
  
![Кнопка "Назначить политику"](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
<span data-ttu-id="0e75d-223">Можно также щелкнуть правой кнопкой мыши элемент, выбрать команду **Назначить политику** в контекстном меню, а затем выбрать метку хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-223">You can also right-click an item, click **Assign Policy** in the context menu, and then choose the retention label.</span></span> 

<span data-ttu-id="0e75d-224">После того как метка хранения будет присвоена, в верхней части элемента можно будет просмотреть эту метку и описание действий, которые она выполняет.</span><span class="sxs-lookup"><span data-stu-id="0e75d-224">After the retention label is applied, you can view that retention label and what action it takes at the top of the item.</span></span> <span data-ttu-id="0e75d-225">Если к электронному сообщению применена метка хранения, для которой задан срок хранения, то вы сразу сможете увидеть, когда истекает этот срок.</span><span class="sxs-lookup"><span data-stu-id="0e75d-225">If an email has a retention label applied that has an associated retention period, you can see at a glance when the email expires.</span></span>
  
<span data-ttu-id="0e75d-226">Вы также можете применять метки хранения к папкам.</span><span class="sxs-lookup"><span data-stu-id="0e75d-226">You can also apply retention labels to folders.</span></span> <span data-ttu-id="0e75d-227">Это работает одинаково как в Outlook 2010 и более поздних версий, так и в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0e75d-227">This works the same in Outlook 2010 and later as it does in Outlook on the web.</span></span> <span data-ttu-id="0e75d-228">Дополнительные сведения см. в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="0e75d-228">See the previous section for more info.</span></span>
  
### <a name="onedrive-and-sharepoint"></a><span data-ttu-id="0e75d-229">OneDrive и SharePoint</span><span class="sxs-lookup"><span data-stu-id="0e75d-229">OneDrive and SharePoint</span></span>

<span data-ttu-id="0e75d-230">Чтобы применить метку к документу (включая файлы OneNote) в OneDrive или SharePoint, выберите элемент \> в правом верхнем углу нажмите **Открыть область сведений**![Значок области сведений](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Применить метку хранения** и выберите метку хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-230">To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label.</span></span> 
  
<span data-ttu-id="0e75d-231">Вы также можете применить метку хранения к папке или набору документов, а также задать метку хранения по умолчанию для библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="0e75d-231">You can also apply a retention label to a folder or document set, and you can set a default retention label for a document library.</span></span> <span data-ttu-id="0e75d-232">Подробнее см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="0e75d-232">See the section below for more information.</span></span>
  
![Применение списка меток к элементу в SharePoint](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
<span data-ttu-id="0e75d-234">Применив метку хранения к элементу, вы можете просмотреть ее в области сведений при выборе этого элемента.</span><span class="sxs-lookup"><span data-stu-id="0e75d-234">After a retention label is applied to an item, you can view it in the details pane when that item's selected.</span></span>
  
![Примененная метка в области сведений](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
<span data-ttu-id="0e75d-p126">Вы также можете создать представление библиотеки, содержащей столбец **Метки** или **Элемент является записью**, чтобы вы могли сразу видеть, какие метки хранения назначены всем элементам и какие элементы являются записями. Однако следует помнить, что представление невозможно отфильтровать по столбцу **Элемент является записью**.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p126">You can also create a view of the library that contains the **Labels** column or **Item is a Record** column, so that you can see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column.</span></span> 
  
![Столбец библиотеки для меток, показанных в пользовательском представлении](../media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### <a name="office-365-groups"></a><span data-ttu-id="0e75d-239">Группы Office 365</span><span class="sxs-lookup"><span data-stu-id="0e75d-239">Office 365 groups</span></span>

<span data-ttu-id="0e75d-p127">Когда вы публикуете метки хранения в группе Office 365, они отображаются как на сайте группы, так и в почтовом ящике группы в Outlook в Интернете. Процесс применения метки хранения к контенту идентичен показанному выше процессу для электронных сообщений и документов.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p127">When you publish retention labels to an Office 365 group, the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that shown above for email and documents.</span></span>

<span data-ttu-id="0e75d-p128">Чтобы хранить контент для группы Office 365, необходимо использовать расположение групп Office 365. Хотя у группы Office 365 есть почтовый ящик Exchange, политика хранения, включающая все расположение Exchange, не будет содержать контент из почтовых ящиков групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p128">To retain content for an Office 365 group, you need to use the Office 365 groups location. Even though an Office 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Office 365 group mailboxes.</span></span>

<span data-ttu-id="0e75d-244">Кроме того, нельзя использовать расположение Exchange для включения или исключения определенного почтового ящика группы.</span><span class="sxs-lookup"><span data-stu-id="0e75d-244">In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox.</span></span> <span data-ttu-id="0e75d-245">Хотя расположение Exchange изначально позволяет выбирать почтовый ящик группы, при попытке сохранить политику хранения появится ошибка, уведомляющая, что RemoteGroupMailbox является недопустимым выбором для расположения Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e75d-245">Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>
  
## <a name="applying-a-retention-label-automatically-based-on-conditions"></a><span data-ttu-id="0e75d-246">Автоматическое применение метки хранения в соответствии с условиями</span><span class="sxs-lookup"><span data-stu-id="0e75d-246">Applying a retention label automatically based on conditions</span></span>

<span data-ttu-id="0e75d-247">Одно из главных преимуществ меток хранения — возможность автоматически их присваивать содержимому, которое соответствует определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="0e75d-247">One of the most powerful features of retention labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="0e75d-248">В этом случае сотрудникам вашей организации не нужно будет самостоятельно присваивать метки хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-248">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="0e75d-249">Office 365 все сделает за них</span><span class="sxs-lookup"><span data-stu-id="0e75d-249">Office 365 does the work for them.</span></span>
  
![Схема ролей и задач для автоматически применяемых меток](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
<span data-ttu-id="0e75d-251">Автоматически применяемые метки хранения удобны, потому что:</span><span class="sxs-lookup"><span data-stu-id="0e75d-251">Auto-apply retention labels are powerful because:</span></span>
  
- <span data-ttu-id="0e75d-252">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="0e75d-252">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="0e75d-253">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="0e75d-253">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="0e75d-254">пользователям больше не нужно будет знать о политиках управления данными — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="0e75d-254">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="0e75d-255">Вы можете автоматически применять метки хранения к контенту, содержащему:</span><span class="sxs-lookup"><span data-stu-id="0e75d-255">You can choose to apply retention labels to content automatically when that content contains:</span></span>
  
- <span data-ttu-id="0e75d-256">[конфиденциальную информацию определенных типов](#auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information);</span><span class="sxs-lookup"><span data-stu-id="0e75d-256">[Specific types of sensitive information](#auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information)</span></span>
    
- <span data-ttu-id="0e75d-257">[определенные ключевые слова, соответствующие созданному запросу](#auto-apply-labels-to-content-with-keywords-or-searchable-properties);</span><span class="sxs-lookup"><span data-stu-id="0e75d-257">[Specific keywords that match a query you create](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)</span></span>

- <span data-ttu-id="0e75d-258">[совпадение для обучаемых классификаторов](#auto-apply-labels-to-content-by-using-trainable-classifiers).</span><span class="sxs-lookup"><span data-stu-id="0e75d-258">[A match for trainable classifiers](#auto-apply-labels-to-content-by-using-trainable-classifiers)</span></span>
    
![Страница выбора условий для автоматически применяемых меток](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="0e75d-260">Автоматическое применение меток хранения к контенту, соответствующему заданным условиям, может занять до семи дней.</span><span class="sxs-lookup"><span data-stu-id="0e75d-260">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>
  
> [!TIP]
> <span data-ttu-id="0e75d-261">Подробный сценарий использования управляемых свойств в SharePoint для автоматического применения меток хранения и реализации хранения, зависящего от возникновения события, см. в статье [Управление жизненным циклом документов SharePoint с метками хранения](auto-apply-retention-labels-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-261">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="0e75d-262">Автоматическое применение меток хранения к контенту с определенными типами конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="0e75d-262">Auto-apply retention labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="0e75d-263">Когда вы создаете автоматически присваиваемые метки хранения для конфиденциальной информации, вы видите тот же список шаблонов политик, что и при создании политики защиты от потери данных (DLP) .</span><span class="sxs-lookup"><span data-stu-id="0e75d-263">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="0e75d-264">Каждый шаблон политик настроен для поиска определенных типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="0e75d-264">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="0e75d-265">Например, показанный здесь шаблон служит для выявления идентификационного номера налогоплательщика (ITIN), номера социального страхования (SSN) и номера паспорта в американском формате.</span><span class="sxs-lookup"><span data-stu-id="0e75d-265">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="0e75d-266">Дополнительные сведения см. в статье [Обзор политик защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-266">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Шаблоны политик с типами конфиденциальной информации](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="0e75d-p132">Выбрав шаблон политики, вы можете добавлять или удалять конфиденциальную информацию любых типов, а также менять количество экземпляров и точность совпадения. В приведенном ниже примере метка хранения будет автоматически применяться, только если:</span><span class="sxs-lookup"><span data-stu-id="0e75d-p132">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="0e75d-p133">контент содержит от 1 до 9 экземпляров любого из этих трех типов конфиденциальной информации. Вы можете удалить **максимальное** значение, чтобы оно изменилось на **Любое**;</span><span class="sxs-lookup"><span data-stu-id="0e75d-p133">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="0e75d-p134">для определяемого типа конфиденциальной информации задана точность совпадения (или уровень надежности) не менее 75. Для многих типов конфиденциальной информации определяется несколько шаблонов. Чем выше точность совпадения, тем больше признаков (например, ключевых слов, дат или адресов) нужно для обнаружения шаблона. Проще говоря, чем ниже **минимальная** точность совпадения, тем проще сопоставить контент с условием.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p134">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="0e75d-275">Дополнительные сведения об этих параметрах см. в разделе [Настройка правил для упрощения или усложнения сопоставления](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="0e75d-275">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Параметры определения типов конфиденциальной информации](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="0e75d-277">Автоматическое применение меток к контенту с ключевыми словами или доступными для поиска свойствами</span><span class="sxs-lookup"><span data-stu-id="0e75d-277">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="0e75d-p135">Вы можете автоматически применять метки к контенту, соответствующему определенным условиям. Имеющиеся в данный момент условия поддерживают применение метки к контенту, содержащему определенные слова, фразы или значения доступных для поиска свойств. Вы можете уточнить запрос с помощью таких операторов поиска, как AND, OR и NOT.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p135">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="0e75d-281">Дополнительные сведения о синтаксисе запросов см. в статье:</span><span class="sxs-lookup"><span data-stu-id="0e75d-281">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="0e75d-282">Руководство по синтаксису языка запросов по ключевым словам (KQL)</span><span class="sxs-lookup"><span data-stu-id="0e75d-282">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="0e75d-p136">Метки на основе запросов используют индекс поиска для определения контента. Дополнительные сведения о допустимых свойствах, доступных для поиска, см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="0e75d-p136">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="0e75d-285">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="0e75d-285">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="0e75d-286">Обзор свойств для обхода и управляемых свойств в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="0e75d-286">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="0e75d-287">Примеры запросов:</span><span class="sxs-lookup"><span data-stu-id="0e75d-287">Examples queries:</span></span>

- <span data-ttu-id="0e75d-288">Exchange</span><span class="sxs-lookup"><span data-stu-id="0e75d-288">Exchange</span></span>
    - <span data-ttu-id="0e75d-289">subject:"Квартальное финансирование"</span><span class="sxs-lookup"><span data-stu-id="0e75d-289">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="0e75d-290">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="0e75d-290">recipients:garthf</span></span><!--nolink--><span data-ttu-id="0e75d-291">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0e75d-291">@contoso.com</span></span>
- <span data-ttu-id="0e75d-292">SharePoint и OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e75d-292">SharePoint and OneDrive for Business</span></span>
    - <span data-ttu-id="0e75d-293">contenttype:контракт</span><span class="sxs-lookup"><span data-stu-id="0e75d-293">contenttype:contract</span></span>
    - <span data-ttu-id="0e75d-294">site:https</span><span class="sxs-lookup"><span data-stu-id="0e75d-294">site:https</span></span><!--nolink--><span data-ttu-id="0e75d-295">://contoso.sharepoint.com/sites/teams/procurement И contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="0e75d-295">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Редактор запросов](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="0e75d-297">Автоматическое применение меток к контенту с помощью обучаемых классификаторов</span><span class="sxs-lookup"><span data-stu-id="0e75d-297">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="0e75d-298">При использовании варианта для обучаемого классификатора вы можете выбрать один из встроенных классификаторов или настраиваемый классификатор.</span><span class="sxs-lookup"><span data-stu-id="0e75d-298">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="0e75d-299">К встроенным классификаторам относятся **Оскорбительная лексика**, **Резюме**, **Исходный код**, **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="0e75d-299">The built-in classifiers include **Offensive Language**, **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Выбор обучаемого классификатора](../media/retention-label-classifers.png)

<span data-ttu-id="0e75d-301">Для автоматического применения меток с помощью классификатора на сайтах и в почтовых ящиках SharePoint Online должно быть не менее 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="0e75d-301">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="0e75d-302">Дополнительные сведения об обучаемых классификаторах см. в статье [Начало работы с обучаемыми классификаторами (предварительная версия)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-302">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="0e75d-303">Пример конфигурации см. в статье [Подготовка к использованию и использование встроенных классификаторов](classifier-using-a-ready-to-use-classifier.md#how-to-prepare-for-and-use-a-built-in-classifier).</span><span class="sxs-lookup"><span data-stu-id="0e75d-303">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-prepare-for-and-use-a-built-in-classifier).</span></span>

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a><span data-ttu-id="0e75d-304">Применение метки хранения по умолчанию ко всему контенту в библиотеке SharePoint, папке или набору документов</span><span class="sxs-lookup"><span data-stu-id="0e75d-304">Applying a default retention label to all content in a SharePoint library, folder, or document set</span></span>

<span data-ttu-id="0e75d-305">Вы можете не только разрешить пользователям применять метки хранения к отдельным документам, но и назначить метку хранения по умолчанию библиотеке SharePoint, папке или набору документов, чтобы эта метка хранения применялась ко всем документам в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="0e75d-305">In addition to enabling people to apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set, so that all documents in that location get the default retention label.</span></span>
  
<span data-ttu-id="0e75d-306">Для библиотеки документов это можно сделать на странице **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="0e75d-306">For a document library, this is done on the **Library settings** page for a document library.</span></span> <span data-ttu-id="0e75d-307">Выбрав метку хранения по умолчанию, вы также можете присвоить ее существующим элементам в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="0e75d-307">When you choose the default retention label, you can also choose to apply it to existing items in the library.</span></span> 
  
<span data-ttu-id="0e75d-308">Например, если у вас есть тег для маркетинговых материалов и вы знаете, что определенная библиотека документов содержит контент только этого типа, вы можете сделать тег маркетинговых материалов стандартным для всех документов в этой библиотеке.</span><span class="sxs-lookup"><span data-stu-id="0e75d-308">For example, if you have a tag for marketing materials, and you know a specific document library contains only that type of content, you can make the Marketing Materials tag the default for all documents in that library.</span></span>
  
![Команда применения метки на странице параметров библиотеки](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
<span data-ttu-id="0e75d-310">Если вы применяете метку хранения по умолчанию к имеющимся элементам в библиотеке, папке или наборе документов:</span><span class="sxs-lookup"><span data-stu-id="0e75d-310">If you apply a default retention label to existing items in the library, folder, or document set:</span></span>
  
- <span data-ttu-id="0e75d-311">ко всем элементам в библиотеке, папке или наборе документов автоматически применяется та же метка хранения, **за исключением** элементов, к которым явно применены другие метки хранения, например к записям</span><span class="sxs-lookup"><span data-stu-id="0e75d-311">All items in the library, folder, or document set automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them (such as records).</span></span> <span data-ttu-id="0e75d-312">(у таких элементов метка остается прежней).</span><span class="sxs-lookup"><span data-stu-id="0e75d-312">Explicitly labeled items keep their existing label.</span></span> <span data-ttu-id="0e75d-313">Дополнительные сведения см. ниже в разделе [Принципы хранения и приоритеты](#the-principles-of-retention-or-what-takes-precedence);</span><span class="sxs-lookup"><span data-stu-id="0e75d-313">For more information, see the below section on [The principles of retention, or what takes precedence](#the-principles-of-retention-or-what-takes-precedence).</span></span>
    
- <span data-ttu-id="0e75d-314">если изменить или удалить используемую по умолчанию метку хранения библиотеки, папки или набора документов, также меняются или удаляются метки хранения всех элементов в этой библиотеке, папке или наборе документов, **кроме** элементов с явными метками хранения (например, записи);</span><span class="sxs-lookup"><span data-stu-id="0e75d-314">If you change or remove the default retention label for a library, folder, or document set, the retention label is also changed or removed for all items in the library, folder, or document set, **except** items with explicit retention labels (such as records).</span></span>
    
- <span data-ttu-id="0e75d-315">если переместить элемент с меткой хранения по умолчанию в другое семейство веб-сайтов, библиотеку, папку или набор документов с другой меткой, то у элемента останется текущая метка хранения по умолчанию, даже если к новому расположению применяется другая метка хранения по умолчанию;</span><span class="sxs-lookup"><span data-stu-id="0e75d-315">If you move an item with a default retention label from one site collection, library, folder, or document set to another site collection, library, folder, or document set that has a different label, the item keeps its existing default retention label, even if the new location has a different default retention label.</span></span> <span data-ttu-id="0e75d-316">если у элемента нет метки перед перемещением, к нему будет применена метка хранения, используемая по умолчанию в новом расположении.</span><span class="sxs-lookup"><span data-stu-id="0e75d-316">If the item does not have a label before moving, it will take on the default retention label of the new location.</span></span>

<span data-ttu-id="0e75d-317">**Записи.** Если применить стандартную метку записи к библиотеке, папке или набору документов, метка записи применяется ко всем отдельным элементам в этих расположениях.</span><span class="sxs-lookup"><span data-stu-id="0e75d-317">**Records:** If you apply a default record label to a library, folder, or document set, then a record label is applied to all the individual items within those locations.</span></span> <span data-ttu-id="0e75d-318">При перемещении нового элемента в расположение с меткой записи этот элемент помечается как запись.</span><span class="sxs-lookup"><span data-stu-id="0e75d-318">When you move a new item into a location with a record label, that item is labeled a record.</span></span> <span data-ttu-id="0e75d-319">Но если используемая по умолчанию метка хранения меняется на метку, не объявляющую содержимое записью, это действие **не** удаляет метку записи из отдельных элементов. Эти элементы сохраняют свою метку записи.</span><span class="sxs-lookup"><span data-stu-id="0e75d-319">However, if you change the default retention label to a label that doesn't declare content as a record, that action **does not** remove the record label from the individual items; those items retain their record label.</span></span> <span data-ttu-id="0e75d-320">Только администратор семейства веб-сайтов может явно удалить или изменить метку хранения для записей.</span><span class="sxs-lookup"><span data-stu-id="0e75d-320">Only a site collection admin can explicitly remove or change the retention label of record items.</span></span>

<span data-ttu-id="0e75d-321">Дополнительные сведения о метках хранения, объявляющих содержимое записью, см. в статье [Обзор записей](records.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-321">For more information about retention labels that declare content as a record, see [Overview of records](records.md).</span></span>
    
## <a name="applying-a-retention-label-to-email-by-using-rules"></a><span data-ttu-id="0e75d-322">Применение метки хранения к электронному сообщению с помощью правил</span><span class="sxs-lookup"><span data-stu-id="0e75d-322">Applying a retention label to email by using rules</span></span>

<span data-ttu-id="0e75d-323">В Outlook 2010 и более поздних версиях можно создавать правила, применяемые к метке хранения или политике хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-323">In Outlook 2010 or later, you can create rules to apply a retention label or retention policy.</span></span>
  
<span data-ttu-id="0e75d-324">Например, вы можете создать правило, которое применяет ту или иную метку хранения ко всем сообщениям, отправляемым в определенную группу рассылки или из нее.</span><span class="sxs-lookup"><span data-stu-id="0e75d-324">For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.</span></span>
  
<span data-ttu-id="0e75d-325">Чтобы создать правило, щелкните элемент правой кнопкой мыши и выберите **Правила** \> **Создать правило** \> **Дополнительные параметры** \> **Мастер правил** \> **Применить политику хранения**.</span><span class="sxs-lookup"><span data-stu-id="0e75d-325">To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.</span></span>
  
![Мастер правил с командой применения политик хранения](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="0e75d-327">Классификация контента без применения действий</span><span class="sxs-lookup"><span data-stu-id="0e75d-327">Classifying content without applying any actions</span></span>

<span data-ttu-id="0e75d-p142">Создавая метку хранения, вы можете не включать хранение или другие действия, как показано ниже. В этом случае метку хранения можно использовать исключительно как текстовую подпись, не выполняющую никаких действий.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p142">When you create a retention label, you can do so without turning on any retention or other actions, as shown below. In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="0e75d-330">Например, вы можете создать метку хранения под названием "Просмотреть позже" без действий, а затем автоматически применять эту метку хранения к контенту с конфиденциальной информацией или запрашиваемому контенту.</span><span class="sxs-lookup"><span data-stu-id="0e75d-330">For example, you can create a retention label named "Review later" with no actions, and then auto-apply that retention label to content with sensitive information types or queried content.</span></span>
  
![Страница параметров метки с отключенным хранением](../media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a><span data-ttu-id="0e75d-332">Использование меток хранения для управления записями</span><span class="sxs-lookup"><span data-stu-id="0e75d-332">Using retention labels for records management</span></span>
    
<span data-ttu-id="0e75d-333">Метки хранения можно использовать для объявления содержимого записью.</span><span class="sxs-lookup"><span data-stu-id="0e75d-333">You can use retention labels to declare content as a record.</span></span> <span data-ttu-id="0e75d-334">Это позволит реализовать единую согласованную стратегию управления записями в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e75d-334">This lets you implement a single, consistent records-management strategy across Office 365.</span></span> <span data-ttu-id="0e75d-335">Дополнительные сведения см. в статье [Обзор записей](records.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-335">For more information, see [Overview of records](records.md).</span></span>
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="0e75d-336">Использование метки хранения в качестве условия в политике защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="0e75d-336">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="0e75d-p144">Метка хранения может применять действия по хранению контента. Кроме того, вы можете использовать метку хранения как условие в политике защиты от потери данных (DLP), и политика защиты от потери данных может применять другие действия (например, ограничение доступа) к контенту с определенной меткой.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p144">A retention label can enforce retention actions on content. In addition, you can use a retention label as a condition in a data loss prevention (DLP) policy, and the DLP policy can enforce other actions, such as restricting access, on content that contains a specific label.</span></span> 
  
<span data-ttu-id="0e75d-339">Дополнительные сведения см. в разделе [Использование метки в качестве условия в политике защиты от потери данных](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span><span class="sxs-lookup"><span data-stu-id="0e75d-339">For more information, see [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="monitor-retention-labels"></a><span data-ttu-id="0e75d-340">Отслеживание меток хранения</span><span class="sxs-lookup"><span data-stu-id="0e75d-340">Monitor retention labels</span></span>

<span data-ttu-id="0e75d-p145">После публикации и автоматического применения меток хранения вам нужно убедиться, что они применяются к контенту, как планировалось. Для отслеживания меток хранения можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="0e75d-p145">After you publish or auto-apply your retention labels, you'll want to verify that they're being applied to content as you intended. To monitor your retention labels, you can use the:</span></span>
  
- <span data-ttu-id="0e75d-p146">**Обозреватель действий с метками**. С помощью обозревателя (показанного ниже) вы можете быстро находить и просматривать действия с метками хранения для всего контента в SharePoint и OneDrive для бизнеса за последние 30 дней. Дополнительные сведения см. в статье [Просмотр действий с метками для документов](view-label-activity-for-documents.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-p146">**Label Activity Explorer**. With the explorer (shown below), you can quickly search and view retention label activity for all content across SharePoint and OneDrive for Business over the past 30 days. For more information, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

- <span data-ttu-id="0e75d-346">Страница **Аналитика меток**.</span><span class="sxs-lookup"><span data-stu-id="0e75d-346">**Label analytics** page.</span></span> <span data-ttu-id="0e75d-347">В Центре соответствия требованиям Microsoft 365 и Центре безопасности Microsoft 365 можно быстро просмотреть основные метки и область их применения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-347">In the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly view your top labels and where they're applied.</span></span> <span data-ttu-id="0e75d-348">Также можно просмотреть все содержимое с определенной меткой.</span><span class="sxs-lookup"><span data-stu-id="0e75d-348">You can also view all content with a specific label.</span></span> <span data-ttu-id="0e75d-349">Дополнительные сведения см. в статье [Просмотр использования меток с помощью аналитики меток](label-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-349">For more information, see [View label usage with label analytics](label-analytics.md).</span></span>
    
- <span data-ttu-id="0e75d-p148">**Отчеты об управлении данными**. С помощью этих отчетов вы можете быстро просматривать тенденции и действия с метками хранения для всего контента в Exchange, SharePoint и OneDrive для бизнеса за последние 90 дней. Дополнительные сведения см. в статье [Просмотр отчетов об управлении данными](view-the-data-governance-reports.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-p148">**Data governance reports**. With these reports, you can quickly view retention label trends and activity for all content across Exchange, SharePoint, and OneDrive for Business over the past 90 days. For more information, see [View the data governance reports](view-the-data-governance-reports.md).</span></span>
    
![Обозреватель действий с метками](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a><span data-ttu-id="0e75d-354">Использование средства "Поиск контента" для поиска содержимого с определенной меткой хранения</span><span class="sxs-lookup"><span data-stu-id="0e75d-354">Using Content Search to find all content with a specific retention label applied to it</span></span>

<span data-ttu-id="0e75d-355">Когда метки хранения будут назначены содержимому (либо пользователями, либо автоматически), вы можете использовать средство "Поиск контента", чтобы найти весь контент с определенной меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-355">After retention labels are assigned to content, either by users or auto-applied, you can use content search to find all content that's classified with a specific retention label.</span></span>
  
<span data-ttu-id="0e75d-p149">Создавая запрос на поиск контента, выберите условие **Тег соответствия требованиям**, а затем укажите полное имя метки либо введите его часть и используйте подстановочный знак. Дополнительные сведения см. в статье [Запросы ключевых слов и условия поиска контента](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-p149">When you create a content search, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard. For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![Условие "Тег соответствия требованиям"](../media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="0e75d-359">Принципы хранения и приоритеты</span><span class="sxs-lookup"><span data-stu-id="0e75d-359">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="0e75d-p150">Возможно (и даже вероятно), что к содержимому применено несколько политик хранения с разными действиями (хранением и/или удалением) и периодом хранения. Какая политика имеет приоритет? Во-первых, вы можете быть уверены, что содержимое, сохраняемое одной политикой, не может быть безвозвратно удалено другой.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p150">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.</span></span>
  
![Схема принципов хранения](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="0e75d-364">Чтобы понять, как различные метки с действиями хранения применяются к контенту, запомните следующие принципы хранения:</span><span class="sxs-lookup"><span data-stu-id="0e75d-364">To understand how different labels with retention actions are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="0e75d-p151">**Хранение имеет приоритет перед удалением.** Допустим, одна политика хранения предписывает удаление электронной почты Exchange спустя три года, а другая — ее хранение в течение пяти лет с последующим удалением. Весь контент трехлетней давности будет удален и скрыт от пользователя, но останется в папке "Элементы с возможностью восстановления", пока его возраст не достигнет пяти лет, после чего он будет окончательно удален.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p151">**Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted.</span></span> 
    
2. <span data-ttu-id="0e75d-p152">**Самый продолжительный период хранения имеет приоритет.** Если к содержимому применено несколько политик, сохраняющих его, оно будет храниться до окончания самого длительного периода хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p152">**The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="0e75d-p153">**Явное включение имеет приоритет перед неявным.** Это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="0e75d-p153">**Explicit inclusion wins over implicit inclusion.** This means:</span></span> 
    
    1. <span data-ttu-id="0e75d-372">Если пользователь вручную присваивает метку хранения с параметрами хранения тому или иному элементу, например сообщению электронной почты Exchange или документу OneDrive, эта метка хранения имеет преимущество как над политикой, которая назначена на уровне сайта или почтового ящика, так и над меткой хранения по умолчанию, которая присваивается библиотекой документов.</span><span class="sxs-lookup"><span data-stu-id="0e75d-372">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a policy assigned at the site or mailbox level and a default retention label assigned by the document library.</span></span> <span data-ttu-id="0e75d-373">Например, если в метке хранения явно указан десятилетний срок хранения, а в назначенной сайту политике хранения — пятилетний, приоритет отдается метке хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-373">For example, if the explicit retention label says to retain for 10 years, but the retention policy assigned to the site says to retain for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="0e75d-374">Автоматически присваиваемые метки хранения считаются неявными именно в силу автоматического их присваивания в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e75d-374">Auto-applied retention labels are considered implicit, not explicit, because they're applied automatically by Office 365.</span></span>
    
    2. <span data-ttu-id="0e75d-375">Если политика хранения включает определенное расположение, например учетную запись OneDrive для бизнеса или почтовый ящик конкретного пользователя, то эта политика имеет приоритет перед другой политикой хранения, которая применяется к учетным записям OneDrive для бизнеса или почтовым ящикам всех пользователей, но не включает почтовый ящик именно этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0e75d-375">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive for Business account, that policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive for Business accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="0e75d-p155">**Кратчайший период удаления имеет приоритет.** Если же к содержимому применено несколько политик, удаляющих его (без хранения), то оно будет удалено по истечении кратчайшего периода хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p155">**The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="0e75d-378">Следует понимать, что принципы хранения используются как поток разрешения конфликтов (сверху вниз): если правила, применяемые всеми политиками или метками, совпадают на одном уровне, то поток переходит на уровень ниже, чтобы определить приоритет применения правил.</span><span class="sxs-lookup"><span data-stu-id="0e75d-378">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all policies or labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="0e75d-p156">Политика хранения или метка не может безвозвратно удалить какое-либо содержимое, находящееся на удержании для обнаружения электронных данных. При отмене удержания содержимое снова становится доступным для вышеописанного процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p156">Finally, a retention policy or label cannot permanently delete any content that's on hold for eDiscovery. When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>

### <a name="precedence-for-auto-labeling-with-trainable-classifiers"></a><span data-ttu-id="0e75d-381">Приоритеты для автоматического применения меток с помощью обучаемых классификаторов</span><span class="sxs-lookup"><span data-stu-id="0e75d-381">Precedence for auto-labeling with trainable classifiers</span></span>

<span data-ttu-id="0e75d-382">Все метки хранения, настроенные для обучаемых классификаторов, оцениваются одновременно.</span><span class="sxs-lookup"><span data-stu-id="0e75d-382">All retention labels that are configured for trainable classifiers are evaluated simultaneously.</span></span> <span data-ttu-id="0e75d-383">Если элемент обнаруживается несколькими обучаемыми классификаторами, используются следующие условия, чтобы определить применяемую метку хранения:</span><span class="sxs-lookup"><span data-stu-id="0e75d-383">If an item is detected by more than one trainable classifier, the following criteria is used to determine which retention label to apply:</span></span>

1. <span data-ttu-id="0e75d-384">Метки хранения, настроенные только для хранения или для хранения с последующим удалением имеют более высокий приоритет, чем метки хранения, настроенные только для удаления.</span><span class="sxs-lookup"><span data-stu-id="0e75d-384">Retention labels configured for retain-only or retain and then delete have a higher priority over retention labels that are configured for delete-only.</span></span>

2. <span data-ttu-id="0e75d-385">В случае меток хранения, настроенных только для хранения или для хранения с последующим удалением, приоритет имеет метка хранения с более длительным сроком хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-385">For retention labels that are configured for retain-only or retain and then delete, the retention label that is configured for the longest retention period wins.</span></span>

3. <span data-ttu-id="0e75d-386">В случае меток хранения, настроенных только для удаления, приоритет имеет метка хранения с наименьшим сроком.</span><span class="sxs-lookup"><span data-stu-id="0e75d-386">For retention labels that are configured for delete-only, the retention label that has been configured for the shortest period wins.</span></span>

4. <span data-ttu-id="0e75d-387">Метки хранения с одинаковым действием и сроком относятся к недетерминированному выбору меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-387">Retention labels with the same action and the same period result in a retention label selection that is non-deterministic.</span></span>

## <a name="use-retention-labels-instead-of-these-features"></a><span data-ttu-id="0e75d-388">Использование меток хранения вместо этих функций</span><span class="sxs-lookup"><span data-stu-id="0e75d-388">Use retention labels instead of these features</span></span>

<span data-ttu-id="0e75d-p158">Метки хранения легко сделать доступными всей организации и ее контенту в Office 365, включая Exchange, SharePoint, OneDrive и группы Office 365. Если вам нужно классифицировать контент или управлять записями в какой-либо службе из Office 365, рекомендуем использовать метки хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p158">Retention labels can easily be made available to an entire organization and its content across Office 365, including Exchange, SharePoint, OneDrive, and Office 365 groups. If you need to classify content or manage records anywhere in Office 365, we recommend that you use retention labels.</span></span>
  
<span data-ttu-id="0e75d-391">Существуют другие функции, которые раньше использовались для классификации содержимого и управления записями в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e75d-391">There are several other features that have previously been used to classify content or manage records in Office 365.</span></span> <span data-ttu-id="0e75d-392">Они перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="0e75d-392">These are listed below.</span></span> <span data-ttu-id="0e75d-393">Эти функции будут работать наряду с метками хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-393">These features will continue to work side by side with retention labels.</span></span> <span data-ttu-id="0e75d-394">Несмотря на то, что в некоторых случаях реализация меток хранения отличается от действия предыдущих функций, развитие управления записями в Office 365 основывается на эволюции применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-394">While there are instances where the implementation of retention labels differs from previous features, the evolution of retention labels will drive the future of records management across Office 365.</span></span> <span data-ttu-id="0e75d-395">По этой причине в дальнейшем для управления данными рекомендуем вместо этих функций использовать метки хранения.</span><span class="sxs-lookup"><span data-stu-id="0e75d-395">Therefore, moving forward, for data governance, we recommend that you use retention labels instead of these features.</span></span>
  
### <a name="exchange-online"></a><span data-ttu-id="0e75d-396">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0e75d-396">Exchange Online</span></span>

- <span data-ttu-id="0e75d-397">[Теги и политики хранения](https://go.microsoft.com/fwlink/?linkid=846125), также называемые средствами [управления записями сообщений (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (только для удаления)</span><span class="sxs-lookup"><span data-stu-id="0e75d-397">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (Deletion only)</span></span> 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="0e75d-398">SharePoint Online и OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e75d-398">SharePoint Online and OneDrive for Business</span></span>

- <span data-ttu-id="0e75d-399">[Настройка управления записями на месте](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (хранение)</span><span class="sxs-lookup"><span data-stu-id="0e75d-399">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Retention)</span></span> 
    
- <span data-ttu-id="0e75d-400">[Общие сведения о центре записей](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (хранение)</span><span class="sxs-lookup"><span data-stu-id="0e75d-400">[Introduction to the Records Center](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (Retention)</span></span> 
    
- <span data-ttu-id="0e75d-401">[Политики управления информацией](intro-to-info-mgmt-policies.md) (только удаление)</span><span class="sxs-lookup"><span data-stu-id="0e75d-401">[Information management policies](intro-to-info-mgmt-policies.md) (Deletion only)</span></span> 
    
## <a name="permissions"></a><span data-ttu-id="0e75d-402">Разрешения</span><span class="sxs-lookup"><span data-stu-id="0e75d-402">Permissions</span></span>

<span data-ttu-id="0e75d-403">Участникам команды по обеспечению соответствия требованиям, которые будут создавать метки хранения, потребуются разрешения для Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="0e75d-403">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="0e75d-404">По умолчанию администратор клиента обладает доступом к этому расположению и может предоставить ответственным за обеспечение соответствия требованиям и другим лицам доступ к Центру безопасности и соответствия требованиям, не предоставляя им все разрешения администратора клиента. Для этого рекомендуем вам перейти на страницу **Разрешения** в Центре безопасности и соответствия требованиям, изменить группу ролей **Администратор соответствия требованиям** и добавить участников в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="0e75d-404">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="0e75d-405">Дополнительные сведения см. в статье [Предоставление пользователям доступа к Центру безопасности и соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0e75d-405">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="0e75d-p161">Эти разрешения необходимы только для создания и применения меток хранения и соответствующей политики. Для применения политики не требуется доступ к контенту.</span><span class="sxs-lookup"><span data-stu-id="0e75d-p161">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>  
## <a name="find-the-powershell-cmdlets-for-labels"></a><span data-ttu-id="0e75d-408">Командлеты PowerShell для работы с метками</span><span class="sxs-lookup"><span data-stu-id="0e75d-408">Find the PowerShell cmdlets for labels</span></span>

<span data-ttu-id="0e75d-409">Чтобы использовать командлеты для работы с метками, необходимо:</span><span class="sxs-lookup"><span data-stu-id="0e75d-409">To use the label cmdlets, you need to:</span></span>
  
1. [<span data-ttu-id="0e75d-410">Подключение к PowerShell Центра безопасности и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="0e75d-410">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="0e75d-411">Используйте эти командлеты Центра безопасности и соответствия требованиям Office 365:</span><span class="sxs-lookup"><span data-stu-id="0e75d-411">Use these Office 365 Security & Compliance Center cmdlets:</span></span>

  - [<span data-ttu-id="0e75d-412">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="0e75d-412">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)

  - [<span data-ttu-id="0e75d-413">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="0e75d-413">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)

  - [<span data-ttu-id="0e75d-414">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="0e75d-414">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)

  - [<span data-ttu-id="0e75d-415">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="0e75d-415">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)

  - [<span data-ttu-id="0e75d-416">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="0e75d-416">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)

  - [<span data-ttu-id="0e75d-417">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="0e75d-417">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)

  - [<span data-ttu-id="0e75d-418">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="0e75d-418">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)

  - [<span data-ttu-id="0e75d-419">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="0e75d-419">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)

  - [<span data-ttu-id="0e75d-420">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="0e75d-420">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)

  - [<span data-ttu-id="0e75d-421">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="0e75d-421">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)

  - [<span data-ttu-id="0e75d-422">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="0e75d-422">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)

  - [<span data-ttu-id="0e75d-423">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="0e75d-423">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)

  - [<span data-ttu-id="0e75d-424">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="0e75d-424">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)

  - [<span data-ttu-id="0e75d-425">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="0e75d-425">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
