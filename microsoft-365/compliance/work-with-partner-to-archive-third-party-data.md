---
title: Архивация сторонних данных при помощи партнера
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как настроить настраиваемый соединитель для импорта сторонних данных из источников данных, таких как Salesforce chatter;, Yahoo Messenger или Yammer.
ms.openlocfilehash: c3b824909ae1243e2dd1f12b799e53d00d9615ca
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126658"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="a30de-103">Архивация сторонних данных при помощи партнера</span><span class="sxs-lookup"><span data-stu-id="a30de-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="a30de-104">Вы можете работать с партнером Майкрософт, чтобы импортировать и архивировать данные из стороннего источника данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="a30de-105">Партнер может предоставить настраиваемый соединитель, настроенный на извлечение элементов из стороннего источника данных (на регулярной основе), а затем импортировать эти элементы.</span><span class="sxs-lookup"><span data-stu-id="a30de-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="a30de-106">Соединитель партнера преобразует содержимое элемента из источника данных в формат сообщения электронной почты, а затем сохраняет элементы в почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="a30de-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="a30de-107">После импорта сторонних данных можно применить к этим данным функции соответствия требованиям Microsoft 365, такие как хранение для судебного разбирательства, поиск контента, Архивация на месте, аудит и политики хранения Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>
  
<span data-ttu-id="a30de-108">Ниже приведен обзор процесса и действий, необходимых для работы с партнером Майкрософт по импорту сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="a30de-108">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="a30de-109">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="a30de-109">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="a30de-110">Шаг 2: создание и Настройка почтового ящика с данными сторонних поставщиков</span><span class="sxs-lookup"><span data-stu-id="a30de-110">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="a30de-111">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="a30de-111">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="a30de-112">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="a30de-112">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="a30de-113">Шаг 5: Зарегистрируйте сторонний соединитель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a30de-113">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="a30de-114">Как происходит импорт сторонних данных</span><span class="sxs-lookup"><span data-stu-id="a30de-114">How the third-party data import process works</span></span>

<span data-ttu-id="a30de-115">На следующем рисунке и описание описывается работа стороннего процесса импорта данных при работе с партнером.</span><span class="sxs-lookup"><span data-stu-id="a30de-115">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Как происходит импорт сторонних данных](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="a30de-117">Клиент работает с партнером по выбору, чтобы настроить соединитель, который будет извлекать элементы из стороннего источника данных, а затем импортировать эти элементы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-117">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="a30de-118">Соединитель партнера подключается к сторонним источникам данных с помощью стороннего API (на основе запланированной или настроенной конфигурации) и извлекает элементы из источника данных.</span><span class="sxs-lookup"><span data-stu-id="a30de-118">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="a30de-119">Партнерский соединитель преобразует содержимое элемента в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a30de-119">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="a30de-120">В разделе [More Information](#more-information) представлено описание схемы формата сообщений.</span><span class="sxs-lookup"><span data-stu-id="a30de-120">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="a30de-121">Партнерский соединитель подключается к службе Azure в Microsoft 365 с помощью веб-службы Exchange (EWS) через хорошо известную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="a30de-121">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="a30de-122">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox.</span><span class="sxs-lookup"><span data-stu-id="a30de-122">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox.</span></span> <span data-ttu-id="a30de-123">Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span><span class="sxs-lookup"><span data-stu-id="a30de-123">Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="a30de-124">**Элементы с идентификатором пользователя, соответствующим учетной записи пользователя:** Если соединитель партнера может сопоставить идентификатор пользователя элемента в источнике данных стороннего производителя с определенным ИДЕНТИФИКАТОРом пользователя в Office 365, элемент будет скопирован в папку " **очистки** " в папке "элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="a30de-124">**Items that have a user ID that corresponds to an user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="a30de-125">У пользователей нет доступа к элементам в папке "Очистка".</span><span class="sxs-lookup"><span data-stu-id="a30de-125">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="a30de-126">Тем не менее, можно использовать средства обнаружения электронных данных для поиска элементов в папке "очистки".</span><span class="sxs-lookup"><span data-stu-id="a30de-126">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="a30de-127">**Элементы, у которых нет идентификатора пользователя, соответствующего учетной записи пользователя:** Если соединителю партнера не удается сопоставить идентификатор пользователя с определенным ИДЕНТИФИКАТОРом пользователя, он копируется в папку **"Входящие"** в почтовом ящике данных стороннего производителя.</span><span class="sxs-lookup"><span data-stu-id="a30de-127">**Items that don't have a user ID that corresponds to an user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="a30de-128">При импорте элементов в папку "Входящие" вы или другой пользователь в Организации можете войти в почтовый ящик стороннего производителя для просмотра этих элементов и управления ими, а также узнать, нужно ли вносить какие-либо изменения в конфигурацию соединителя партнера.</span><span class="sxs-lookup"><span data-stu-id="a30de-128">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="a30de-129">Шаг 1. Поиск партнера по работе со сторонними данными</span><span class="sxs-lookup"><span data-stu-id="a30de-129">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="a30de-130">Ключевой компонент для архивации сторонних данных в Microsoft 365 — Поиск и работа с партнером Майкрософт, который специализируется на сборе данных из стороннего источника данных и импортирует их в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-130">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="a30de-131">После импорта данные можно заархивировать и сохранить вместе с другими данными Майкрософт, такими как электронная почта от Exchange и документы из SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a30de-131">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="a30de-132">Партнер создает соединитель, который извлекает данные из сторонних источников данных Организации (таких как BlackBerry, Facebook, Google +, Thomson Reuters, Twitter и YouTube), и передает эти данные в API Office 365, который импортирует элементы в почтовые ящики Exchange как сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a30de-132">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="a30de-133">В следующих разделах перечислены партнеры Майкрософт (и сторонние источники данных, которые они поддерживаются), которые участвуют в программе для архивации сторонних данных в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-133">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="a30de-134">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="a30de-134">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="a30de-135">арчивесоЦиал</span><span class="sxs-lookup"><span data-stu-id="a30de-135">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="a30de-136">глобанет</span><span class="sxs-lookup"><span data-stu-id="a30de-136">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="a30de-137">OpenText</span><span class="sxs-lookup"><span data-stu-id="a30de-137">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="a30de-138">смарш</span><span class="sxs-lookup"><span data-stu-id="a30de-138">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="a30de-139">Глагол</span><span class="sxs-lookup"><span data-stu-id="a30de-139">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="a30de-140">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="a30de-140">17a-4 LLC</span></span>

<span data-ttu-id="a30de-141">[17A – 4 LLC](https://www.17a-4.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="a30de-141">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="a30de-142">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a30de-142">BlackBerry</span></span>
    
- <span data-ttu-id="a30de-143">потоки данных Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="a30de-143">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="a30de-144">Cisco Jabber;</span><span class="sxs-lookup"><span data-stu-id="a30de-144">Cisco Jabber</span></span>
    
- <span data-ttu-id="a30de-145">Факт</span><span class="sxs-lookup"><span data-stu-id="a30de-145">FactSet</span></span>
    
- <span data-ttu-id="a30de-146">хипчат</span><span class="sxs-lookup"><span data-stu-id="a30de-146">HipChat</span></span>
    
- <span data-ttu-id="a30de-147">инвестедже</span><span class="sxs-lookup"><span data-stu-id="a30de-147">InvestEdge</span></span>
    
- <span data-ttu-id="a30de-148">ливеперсон</span><span class="sxs-lookup"><span data-stu-id="a30de-148">LivePerson</span></span>
    
- <span data-ttu-id="a30de-149">MessageLabs Data Streams;</span><span class="sxs-lookup"><span data-stu-id="a30de-149">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="a30de-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="a30de-150">OpenText</span></span>
    
- <span data-ttu-id="a30de-151">Oracle/ATG Click-to-Call Live Help;</span><span class="sxs-lookup"><span data-stu-id="a30de-151">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="a30de-152">Pivot IMTRADER;</span><span class="sxs-lookup"><span data-stu-id="a30de-152">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="a30de-153">Microsoft SharePoint;</span><span class="sxs-lookup"><span data-stu-id="a30de-153">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="a30de-154">миндалигн</span><span class="sxs-lookup"><span data-stu-id="a30de-154">MindAlign</span></span>
    
- <span data-ttu-id="a30de-155">Sitrion One (Newsgator);</span><span class="sxs-lookup"><span data-stu-id="a30de-155">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="a30de-156">Skype для бизнеса (Lync/OCS);</span><span class="sxs-lookup"><span data-stu-id="a30de-156">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="a30de-157">Skype для бизнеса Online (Lync Online);</span><span class="sxs-lookup"><span data-stu-id="a30de-157">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="a30de-158">базы данных SQL;</span><span class="sxs-lookup"><span data-stu-id="a30de-158">SQL Databases</span></span>
    
- <span data-ttu-id="a30de-159">скуавкер</span><span class="sxs-lookup"><span data-stu-id="a30de-159">Squawker</span></span>
    
- <span data-ttu-id="a30de-160">Thomson Reuters Eikon Messenger.</span><span class="sxs-lookup"><span data-stu-id="a30de-160">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="a30de-161">арчивесоЦиал</span><span class="sxs-lookup"><span data-stu-id="a30de-161">ArchiveSocial</span></span>

<span data-ttu-id="a30de-162">[АрчивесоЦиал](https://www.archivesocial.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="a30de-162">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a30de-163">Facebook</span><span class="sxs-lookup"><span data-stu-id="a30de-163">Facebook</span></span>
    
- <span data-ttu-id="a30de-164">Flickr</span><span class="sxs-lookup"><span data-stu-id="a30de-164">Flickr</span></span>
    
- <span data-ttu-id="a30de-165">инстаграм</span><span class="sxs-lookup"><span data-stu-id="a30de-165">Instagram</span></span>
    
- <span data-ttu-id="a30de-166">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a30de-166">LinkedIn</span></span>
    
- <span data-ttu-id="a30de-167">пинтерест</span><span class="sxs-lookup"><span data-stu-id="a30de-167">Pinterest</span></span>
    
- <span data-ttu-id="a30de-168">Twitter</span><span class="sxs-lookup"><span data-stu-id="a30de-168">Twitter</span></span>
    
- <span data-ttu-id="a30de-169">YouTube</span><span class="sxs-lookup"><span data-stu-id="a30de-169">YouTube</span></span>
    
- <span data-ttu-id="a30de-170">Vimeo</span><span class="sxs-lookup"><span data-stu-id="a30de-170">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="a30de-171">глобанет</span><span class="sxs-lookup"><span data-stu-id="a30de-171">Globanet</span></span>

<span data-ttu-id="a30de-172">[Глобанет](https://www.globanet.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="a30de-172">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a30de-173">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="a30de-173">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="a30de-174">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="a30de-174">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a30de-175">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="a30de-175">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a30de-176">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="a30de-176">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a30de-177">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="a30de-177">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a30de-178">Bloomberg Chat;</span><span class="sxs-lookup"><span data-stu-id="a30de-178">Bloomberg Chat</span></span>
    
- <span data-ttu-id="a30de-179">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="a30de-179">Bloomberg Mail</span></span>
    
- <span data-ttu-id="a30de-180">Box</span><span class="sxs-lookup"><span data-stu-id="a30de-180">Box</span></span>
    
- <span data-ttu-id="a30de-181">CipherCloud для Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="a30de-181">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="a30de-182">Сервер для обмена мгновенными сообщениями Cisco &amp; (10, v 10.5.1 SU1, v SU2, v 11.5)</span><span class="sxs-lookup"><span data-stu-id="a30de-182">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="a30de-183">Cisco Вебекс Teams</span><span class="sxs-lookup"><span data-stu-id="a30de-183">Cisco Webex Teams</span></span>

- <span data-ttu-id="a30de-184">ShareFile рабочей области Citrix &amp;</span><span class="sxs-lookup"><span data-stu-id="a30de-184">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="a30de-185">кровдкомпасс</span><span class="sxs-lookup"><span data-stu-id="a30de-185">CrowdCompass</span></span>

- <span data-ttu-id="a30de-186">Текстовые файлы с разделителями</span><span class="sxs-lookup"><span data-stu-id="a30de-186">Custom-delimited text files</span></span>
    
- <span data-ttu-id="a30de-187">настраиваемые XML-файлы;</span><span class="sxs-lookup"><span data-stu-id="a30de-187">Custom XML files</span></span>
    
- <span data-ttu-id="a30de-188">Facebook (страницы)</span><span class="sxs-lookup"><span data-stu-id="a30de-188">Facebook (Pages)</span></span>
    
- <span data-ttu-id="a30de-189">Факт</span><span class="sxs-lookup"><span data-stu-id="a30de-189">Factset</span></span>
    
- <span data-ttu-id="a30de-190">фксконнект</span><span class="sxs-lookup"><span data-stu-id="a30de-190">FXConnect</span></span>
    
- <span data-ttu-id="a30de-191">ICE Chat или YellowJacket;</span><span class="sxs-lookup"><span data-stu-id="a30de-191">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="a30de-192">Jive</span><span class="sxs-lookup"><span data-stu-id="a30de-192">Jive</span></span>
    
- <span data-ttu-id="a30de-193">Macgregor XIP;</span><span class="sxs-lookup"><span data-stu-id="a30de-193">Macgregor XIP</span></span>

- <span data-ttu-id="a30de-194">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a30de-194">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="a30de-195">Microsoft OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a30de-195">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="a30de-196">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a30de-196">Microsoft Teams</span></span>
       
- <span data-ttu-id="a30de-197">Microsoft Yammer;</span><span class="sxs-lookup"><span data-stu-id="a30de-197">Microsoft Yammer</span></span>
    
- <span data-ttu-id="a30de-198">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="a30de-198">Mobile Guard</span></span>
    
- <span data-ttu-id="a30de-199">Сводка</span><span class="sxs-lookup"><span data-stu-id="a30de-199">Pivot</span></span>
    
- <span data-ttu-id="a30de-200">Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="a30de-200">Salesforce Chatter</span></span>

- <span data-ttu-id="a30de-201">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a30de-201">Skype for Business Online</span></span>
    
- <span data-ttu-id="a30de-202">Skype для бизнеса, версии от 2007 R2 до 2016 (локальные);</span><span class="sxs-lookup"><span data-stu-id="a30de-202">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="a30de-203">Slack Enterprise Grid;</span><span class="sxs-lookup"><span data-stu-id="a30de-203">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="a30de-204">симфони</span><span class="sxs-lookup"><span data-stu-id="a30de-204">Symphony</span></span>
    
- <span data-ttu-id="a30de-205">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="a30de-205">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="a30de-206">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="a30de-206">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="a30de-207">Thomson Reuters Dealings 3000 или FX Trading;</span><span class="sxs-lookup"><span data-stu-id="a30de-207">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="a30de-208">Twitter</span><span class="sxs-lookup"><span data-stu-id="a30de-208">Twitter</span></span>
    
- <span data-ttu-id="a30de-209">UBS Chat;</span><span class="sxs-lookup"><span data-stu-id="a30de-209">UBS Chat</span></span>
    
- <span data-ttu-id="a30de-210">YouTube</span><span class="sxs-lookup"><span data-stu-id="a30de-210">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="a30de-211">OpenText</span><span class="sxs-lookup"><span data-stu-id="a30de-211">OpenText</span></span>

<span data-ttu-id="a30de-212">[Опентекст](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="a30de-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a30de-213">Axs Encrypted;</span><span class="sxs-lookup"><span data-stu-id="a30de-213">Axs Encrypted</span></span>
    
- <span data-ttu-id="a30de-214">Axs Exchange;</span><span class="sxs-lookup"><span data-stu-id="a30de-214">Axs Exchange</span></span>
    
- <span data-ttu-id="a30de-215">Axs Local Archive;</span><span class="sxs-lookup"><span data-stu-id="a30de-215">Axs Local Archive</span></span>
    
- <span data-ttu-id="a30de-216">Axs PlaceHolder;</span><span class="sxs-lookup"><span data-stu-id="a30de-216">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="a30de-217">Axs Signed;</span><span class="sxs-lookup"><span data-stu-id="a30de-217">Axs Signed</span></span>
    
- <span data-ttu-id="a30de-218">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a30de-218">Bloomberg</span></span>
    
- <span data-ttu-id="a30de-219">Thomson Reuters.</span><span class="sxs-lookup"><span data-stu-id="a30de-219">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="a30de-220">смарш</span><span class="sxs-lookup"><span data-stu-id="a30de-220">Smarsh</span></span>

<span data-ttu-id="a30de-221">[Смарш](https://www.smarsh.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="a30de-221">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a30de-222">СТАРАЙТЕСЬ</span><span class="sxs-lookup"><span data-stu-id="a30de-222">AIM</span></span>
    
- <span data-ttu-id="a30de-223">American Idol;</span><span class="sxs-lookup"><span data-stu-id="a30de-223">American Idol</span></span>
    
- <span data-ttu-id="a30de-224">Apple Juice;</span><span class="sxs-lookup"><span data-stu-id="a30de-224">Apple Juice</span></span>
    
- <span data-ttu-id="a30de-225">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="a30de-225">AOL with Pivot client</span></span>
    
- <span data-ttu-id="a30de-226">арес</span><span class="sxs-lookup"><span data-stu-id="a30de-226">Ares</span></span>
    
- <span data-ttu-id="a30de-227">Bazaar Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-227">Bazaar Voice</span></span>
    
- <span data-ttu-id="a30de-228">Bear Share;</span><span class="sxs-lookup"><span data-stu-id="a30de-228">Bear Share</span></span>
    
- <span data-ttu-id="a30de-229">Bit Torrent;</span><span class="sxs-lookup"><span data-stu-id="a30de-229">Bit Torrent</span></span>
    
- <span data-ttu-id="a30de-230">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="a30de-230">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a30de-231">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="a30de-231">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a30de-232">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="a30de-232">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a30de-233">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="a30de-233">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a30de-234">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="a30de-234">Bloomberg Mail</span></span>
    
- <span data-ttu-id="a30de-235">целлтруст</span><span class="sxs-lookup"><span data-stu-id="a30de-235">CellTrust</span></span>
    
- <span data-ttu-id="a30de-236">импорт чата;</span><span class="sxs-lookup"><span data-stu-id="a30de-236">Chat Import</span></span>
    
- <span data-ttu-id="a30de-237">политика и ведение журнала чата в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="a30de-237">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="a30de-238">Chatter;</span><span class="sxs-lookup"><span data-stu-id="a30de-238">Chatter</span></span>
    
- <span data-ttu-id="a30de-239">Сервер Cisco IM &amp; Presence Server (v 9.0.1, v 9.1, v 9.1.1 SU1, 10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="a30de-239">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="a30de-240">Cisco Unified Presence Server (версии 8.6.3, 8.6.4, 8.6.5);</span><span class="sxs-lookup"><span data-stu-id="a30de-240">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="a30de-241">импорт совместной работы;</span><span class="sxs-lookup"><span data-stu-id="a30de-241">Collaboration Import</span></span>
    
- <span data-ttu-id="a30de-242">ведение журнала совместной работы в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="a30de-242">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="a30de-243">Direct Connect;</span><span class="sxs-lookup"><span data-stu-id="a30de-243">Direct Connect</span></span>
    
- <span data-ttu-id="a30de-244">Facebook</span><span class="sxs-lookup"><span data-stu-id="a30de-244">Facebook</span></span>
    
- <span data-ttu-id="a30de-245">Факт</span><span class="sxs-lookup"><span data-stu-id="a30de-245">FactSet</span></span>
    
- <span data-ttu-id="a30de-246">FastTrack</span><span class="sxs-lookup"><span data-stu-id="a30de-246">FastTrack</span></span>
    
- <span data-ttu-id="a30de-247">гнутелла</span><span class="sxs-lookup"><span data-stu-id="a30de-247">Gnutella</span></span>
    
- <span data-ttu-id="a30de-248">Google +</span><span class="sxs-lookup"><span data-stu-id="a30de-248">Google+</span></span>
    
- <span data-ttu-id="a30de-249">готомипк</span><span class="sxs-lookup"><span data-stu-id="a30de-249">GoToMyPC</span></span>
    
- <span data-ttu-id="a30de-250">хопстер</span><span class="sxs-lookup"><span data-stu-id="a30de-250">Hopster</span></span>
    
- <span data-ttu-id="a30de-251">хубконнекс</span><span class="sxs-lookup"><span data-stu-id="a30de-251">HubConnex</span></span>
    
- <span data-ttu-id="a30de-252">IBM Connections (версии 3.0.1, 4.0, 4.5, 4.5 CR3, 5);</span><span class="sxs-lookup"><span data-stu-id="a30de-252">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="a30de-253">IBM Connections Chat Cloud;</span><span class="sxs-lookup"><span data-stu-id="a30de-253">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="a30de-254">IBM Connections Social Cloud;</span><span class="sxs-lookup"><span data-stu-id="a30de-254">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="a30de-255">IBM SameTime Advanced 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="a30de-255">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="a30de-256">IBM SameTime Communicate 9.0;</span><span class="sxs-lookup"><span data-stu-id="a30de-256">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="a30de-257">IBM SameTime Community (версии 8.0.2, 8.5.1 IFR2, 8.5.2 IFR1, 9.1);</span><span class="sxs-lookup"><span data-stu-id="a30de-257">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="a30de-258">IBM SameTime Complete 9.0;</span><span class="sxs-lookup"><span data-stu-id="a30de-258">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="a30de-259">IBM SameTime Conference 9.0;</span><span class="sxs-lookup"><span data-stu-id="a30de-259">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="a30de-260">IBM SameTime Meeting 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="a30de-260">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="a30de-261">ICE/Елловжаккет</span><span class="sxs-lookup"><span data-stu-id="a30de-261">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="a30de-262">импорт мгновенных сообщений;</span><span class="sxs-lookup"><span data-stu-id="a30de-262">IM Import</span></span>
    
- <span data-ttu-id="a30de-263">политика и ведение журнала обмена мгновенными сообщениями в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="a30de-263">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="a30de-264">Indii Messenger;</span><span class="sxs-lookup"><span data-stu-id="a30de-264">Indii Messenger</span></span>
    
- <span data-ttu-id="a30de-265">Instant Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="a30de-265">Instant Bloomberg</span></span>
    
- <span data-ttu-id="a30de-266">IRC</span><span class="sxs-lookup"><span data-stu-id="a30de-266">IRC</span></span>
    
- <span data-ttu-id="a30de-267">Jive</span><span class="sxs-lookup"><span data-stu-id="a30de-267">Jive</span></span>
    
- <span data-ttu-id="a30de-268">Jive 6 Real Time Logging (версии 6, 7);</span><span class="sxs-lookup"><span data-stu-id="a30de-268">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="a30de-269">импорт Jive;</span><span class="sxs-lookup"><span data-stu-id="a30de-269">Jive Import</span></span>
    
- <span data-ttu-id="a30de-270">жкста</span><span class="sxs-lookup"><span data-stu-id="a30de-270">JXTA</span></span>
    
- <span data-ttu-id="a30de-271">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a30de-271">LinkedIn</span></span>
    
- <span data-ttu-id="a30de-272">Microsoft Lync (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="a30de-272">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="a30de-273">мфтп</span><span class="sxs-lookup"><span data-stu-id="a30de-273">MFTP</span></span>
    
- <span data-ttu-id="a30de-274">Microsoft Lync 2013 Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-274">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="a30de-275">Microsoft SharePoint (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="a30de-275">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="a30de-276">Microsoft SharePoint Online;</span><span class="sxs-lookup"><span data-stu-id="a30de-276">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="a30de-277">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="a30de-277">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="a30de-278">миндалигн</span><span class="sxs-lookup"><span data-stu-id="a30de-278">MindAlign</span></span>
    
- <span data-ttu-id="a30de-279">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="a30de-279">Mobile Guard</span></span>
    
- <span data-ttu-id="a30de-280">СЕТЬЮ</span><span class="sxs-lookup"><span data-stu-id="a30de-280">MSN</span></span>
    
- <span data-ttu-id="a30de-281">My Space;</span><span class="sxs-lookup"><span data-stu-id="a30de-281">My Space</span></span>
    
- <span data-ttu-id="a30de-282">неонетворк</span><span class="sxs-lookup"><span data-stu-id="a30de-282">NEONetwork</span></span>
    
- <span data-ttu-id="a30de-283">Office 365 Lync Dedicated;</span><span class="sxs-lookup"><span data-stu-id="a30de-283">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="a30de-284">групповой чат Office 365;</span><span class="sxs-lookup"><span data-stu-id="a30de-284">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="a30de-285">пинтерест</span><span class="sxs-lookup"><span data-stu-id="a30de-285">Pinterest</span></span>
    
- <span data-ttu-id="a30de-286">Сводка</span><span class="sxs-lookup"><span data-stu-id="a30de-286">Pivot</span></span>
    
- <span data-ttu-id="a30de-287">QQ</span><span class="sxs-lookup"><span data-stu-id="a30de-287">QQ</span></span>
    
- <span data-ttu-id="a30de-288">Skype для бизнеса 2015;</span><span class="sxs-lookup"><span data-stu-id="a30de-288">Skype for Business 2015</span></span>
    
- <span data-ttu-id="a30de-289">софтесер</span><span class="sxs-lookup"><span data-stu-id="a30de-289">SoftEther</span></span>
    
- <span data-ttu-id="a30de-290">симфони</span><span class="sxs-lookup"><span data-stu-id="a30de-290">Symphony</span></span>
    
- <span data-ttu-id="a30de-291">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="a30de-291">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="a30de-292">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="a30de-292">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="a30de-293">тор</span><span class="sxs-lookup"><span data-stu-id="a30de-293">Tor</span></span>
    
- <span data-ttu-id="a30de-294">ттт</span><span class="sxs-lookup"><span data-stu-id="a30de-294">TTT</span></span>
    
- <span data-ttu-id="a30de-295">Twitter</span><span class="sxs-lookup"><span data-stu-id="a30de-295">Twitter</span></span>
    
- <span data-ttu-id="a30de-296">винмкс</span><span class="sxs-lookup"><span data-stu-id="a30de-296">WinMX</span></span>
    
- <span data-ttu-id="a30de-297">винни</span><span class="sxs-lookup"><span data-stu-id="a30de-297">Winny</span></span>
    
- <span data-ttu-id="a30de-298">Yahoo</span><span class="sxs-lookup"><span data-stu-id="a30de-298">Yahoo</span></span>
    
- <span data-ttu-id="a30de-299">Yammer</span><span class="sxs-lookup"><span data-stu-id="a30de-299">Yammer</span></span>
    
- <span data-ttu-id="a30de-300">YouTube</span><span class="sxs-lookup"><span data-stu-id="a30de-300">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="a30de-301">Глагол</span><span class="sxs-lookup"><span data-stu-id="a30de-301">Verba</span></span>

<span data-ttu-id="a30de-302">[Verb](https://www.verba.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="a30de-302">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a30de-303">Avaya Aura Video;</span><span class="sxs-lookup"><span data-stu-id="a30de-303">Avaya Aura Video</span></span>
    
- <span data-ttu-id="a30de-304">Avaya Aura Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-304">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="a30de-305">Avtec Radio;</span><span class="sxs-lookup"><span data-stu-id="a30de-305">Avtec Radio</span></span>
    
- <span data-ttu-id="a30de-306">Bosch/Telex Radio;</span><span class="sxs-lookup"><span data-stu-id="a30de-306">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="a30de-307">BroadSoft Video;</span><span class="sxs-lookup"><span data-stu-id="a30de-307">BroadSoft Video</span></span>
    
- <span data-ttu-id="a30de-308">BroadSoft Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-308">BroadSoft Voice</span></span>
    
- <span data-ttu-id="a30de-309">Centile Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-309">Centile Voice</span></span>
    
- <span data-ttu-id="a30de-310">Cisco Jabber IM;</span><span class="sxs-lookup"><span data-stu-id="a30de-310">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="a30de-311">Cisco UC Video;</span><span class="sxs-lookup"><span data-stu-id="a30de-311">Cisco UC Video</span></span>
    
- <span data-ttu-id="a30de-312">Cisco UC Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-312">Cisco UC Voice</span></span>
    
- <span data-ttu-id="a30de-313">Cisco UCCX/UCCE Video</span><span class="sxs-lookup"><span data-stu-id="a30de-313">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="a30de-314">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="a30de-314">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="a30de-315">ESChat Radio;</span><span class="sxs-lookup"><span data-stu-id="a30de-315">ESChat Radio</span></span>
    
- <span data-ttu-id="a30de-316">Geoman Contact Expert;</span><span class="sxs-lookup"><span data-stu-id="a30de-316">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="a30de-317">IP Trade Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-317">IP Trade Voice</span></span>
    
- <span data-ttu-id="a30de-318">Luware LUCS Contact Center;</span><span class="sxs-lookup"><span data-stu-id="a30de-318">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="a30de-319">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="a30de-319">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="a30de-320">Mitel MiContact Center для Lync (prairieFyre);</span><span class="sxs-lookup"><span data-stu-id="a30de-320">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="a30de-321">Oracle / Acme Packet Session Border Controller Video;</span><span class="sxs-lookup"><span data-stu-id="a30de-321">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="a30de-322">Oracle / Acme Packet Session Border Controller Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-322">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="a30de-323">Singtel Mobile Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-323">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="a30de-324">SIPREC Video;</span><span class="sxs-lookup"><span data-stu-id="a30de-324">SIPREC Video</span></span>
    
-  <span data-ttu-id="a30de-325">SIPREC Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-325">SIPREC Voice</span></span> 
    
- <span data-ttu-id="a30de-326">Skype для бизнеса / Lync IM;</span><span class="sxs-lookup"><span data-stu-id="a30de-326">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="a30de-327">Skype для бизнеса / Lync Video;</span><span class="sxs-lookup"><span data-stu-id="a30de-327">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="a30de-328">Skype для бизнеса / Lync Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-328">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="a30de-329">Speakerbus Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-329">Speakerbus Voice</span></span>
    
- <span data-ttu-id="a30de-330">Standard SIP/H.323 Video;</span><span class="sxs-lookup"><span data-stu-id="a30de-330">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="a30de-331">Standard SIP/H.323 Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-331">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="a30de-332">Truphone Voice;</span><span class="sxs-lookup"><span data-stu-id="a30de-332">Truphone Voice</span></span>
    
- <span data-ttu-id="a30de-333">TwistedPair Radio;</span><span class="sxs-lookup"><span data-stu-id="a30de-333">TwistedPair Radio</span></span>
    
- <span data-ttu-id="a30de-334">рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="a30de-334">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="a30de-335">Шаг 2. Создание и настройка почтового ящика сторонних данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="a30de-335">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="a30de-336">Ниже приведены действия по созданию и настройке почтового ящика данных стороннего производителя для импорта данных в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-336">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="a30de-337">Как описано выше, элементы импортируются в этот почтовый ящик, если соединитель партнера не может сопоставить идентификатор пользователя элемента с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="a30de-337">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an user account.</span></span>
  
 <span data-ttu-id="a30de-338">**Выполните эти действия в центре администрирования Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="a30de-338">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="a30de-339">Создайте учетную запись пользователя и назначьте ей лицензию на Exchange Online (план 2). Ознакомьтесь [со статьей Добавление пользователей в Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="a30de-339">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="a30de-340">Лицензия на план 2 необходима, чтобы поместить почтовый ящик на хранение для судебного разбирательства или включить архивный почтовый ящик с неограниченной квотой.</span><span class="sxs-lookup"><span data-stu-id="a30de-340">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="a30de-341">Добавьте учетную запись пользователя для почтового ящика данных стороннего производителя в роль администратора **администратора Exchange** в Office 365; [в разделе Назначение ролей администратора в Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="a30de-341">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a30de-342">Запишите данные этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="a30de-342">Write down the credentials for this user account.</span></span> <span data-ttu-id="a30de-343">Их необходимо предоставить партнеру, как описано в шаге 4.</span><span class="sxs-lookup"><span data-stu-id="a30de-343">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="a30de-344">**Выполнение этих задач в центре администрирования Exchange**</span><span class="sxs-lookup"><span data-stu-id="a30de-344">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="a30de-345">Скрытие почтового ящика сторонних данных из адресной книги и других списков адресов в Организации; в разделе [Управление почтовыми ящиками пользователей](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="a30de-345">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="a30de-346">Можно также выполнить следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a30de-346">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="a30de-347">Назначьте разрешение **FullAccess** для почтового ящика данных стороннего производителя, чтобы администраторы или руководители соответствия могли открыть сторонний почтовый ящик данных в клиенте Outlook для настольных ПК. Ознакомьтесь с [разрешениями Управление разрешениями для получателей](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="a30de-347">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="a30de-348">Включите следующие функции, связанные с соответствием требованиям, для почтового ящика данных стороннего производителя:</span><span class="sxs-lookup"><span data-stu-id="a30de-348">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="a30de-349">Включение архивного почтового ящика; Разрешите [архивирование почтовых ящиков](enable-archive-mailboxes.md) и [включите неограниченное архивирование](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a30de-349">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="a30de-350">Это позволяет освободить дисковое пространство в основном почтовом ящике, настроив политику архивации, которая перемещает сторонние элементы данных в архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="a30de-350">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="a30de-351">Это обеспечивает неограниченное хранение данных сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="a30de-351">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="a30de-352">Поместите почтовый ящик сторонних данных на хранение для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="a30de-352">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="a30de-353">Вы также можете применить политику хранения Microsoft 365 в центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a30de-353">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="a30de-354">При помещении этого почтового ящика в удержание сохраняются сторонние элементы данных (неопределенное время или продолжительность действия), и их не следует очищать из почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="a30de-354">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="a30de-355">Просмотрите один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="a30de-355">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="a30de-356">Применение к почтовому ящику функции судебного удержания</span><span class="sxs-lookup"><span data-stu-id="a30de-356">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="a30de-357">Сведения о политиках хранения и метках хранения</span><span class="sxs-lookup"><span data-stu-id="a30de-357">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="a30de-358">Включение ведения журнала аудита почтовых ящиков для владельца, представителя и административного доступа к почтовому ящику данных стороннего производителя; в разделе [включить аудит почтовых ящиков](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="a30de-358">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="a30de-359">Это позволяет выполнять аудит всех действий, выполняемых любым пользователем, имеющим доступ к почтовому ящику данных стороннего производителя.</span><span class="sxs-lookup"><span data-stu-id="a30de-359">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="a30de-360">Шаг 3. Настройка поддержки сторонних данных для почтовых ящиков пользователей</span><span class="sxs-lookup"><span data-stu-id="a30de-360">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="a30de-361">Следующим шагом является настройка поддержки сторонних данных для почтовых ящиков пользователей.</span><span class="sxs-lookup"><span data-stu-id="a30de-361">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="a30de-362">Выполните указанные ниже действия с помощью центра администрирования Exchange или соответствующих командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a30de-362">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="a30de-363">Включите архивный почтовый ящик для каждого пользователя; Разрешите [архивирование почтовых ящиков](enable-archive-mailboxes.md) и [включите неограниченное архивирование](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a30de-363">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="a30de-364">Помещайте почтовые ящики пользователей на хранение для судебного разбирательства или примените политику хранения Microsoft 365; Просмотрите один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="a30de-364">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="a30de-365">Применение к почтовому ящику функции судебного удержания</span><span class="sxs-lookup"><span data-stu-id="a30de-365">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="a30de-366">Сведения о политиках хранения и метках хранения</span><span class="sxs-lookup"><span data-stu-id="a30de-366">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="a30de-367">Как отмечалось ранее, при помещении почтовых ящиков на хранение можно указать длительность хранения элементов из источника сторонних данных или выбрать бессрочное хранение.</span><span class="sxs-lookup"><span data-stu-id="a30de-367">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="a30de-368">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="a30de-368">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="a30de-369">Последним этапом является предоставление партнеру следующих сведений, чтобы можно было настроить соединитель для подключения к Организации, чтобы импортировать данные в почтовые ящики пользователей и в почтовые ящики сторонних поставщиков данных.</span><span class="sxs-lookup"><span data-stu-id="a30de-369">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="a30de-370">Конечная точка, используемая для подключения к службе Azure в Office 365:</span><span class="sxs-lookup"><span data-stu-id="a30de-370">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="a30de-371">Учетные данные для входа (идентификатор пользователя и пароль Microsoft 365) для почтового ящика данных стороннего производителя, созданного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="a30de-371">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="a30de-372">Эти учетные данные требуются соединителю партнера для доступа к элементам и их импорта в почтовые ящики пользователей и почтовый ящик со сторонними данными.</span><span class="sxs-lookup"><span data-stu-id="a30de-372">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="a30de-373">Шаг 5: Зарегистрируйте сторонний соединитель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a30de-373">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="a30de-374">Начиная с 30 сентября 2018, служба Azure в Office 365 начнет использовать современные проверки подлинности в Exchange Online для проверки подлинности сторонних соединителей данных, пытающихся подключиться к Организации для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="a30de-374">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="a30de-375">Причина этого изменения заключается в том, что современная проверка подлинности обеспечивает большую безопасность, чем текущий метод, основанный на списке разрешений для сторонних соединителей, использующих ранее описанную конечную точку для подключения к службе Azure.</span><span class="sxs-lookup"><span data-stu-id="a30de-375">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="a30de-376">Чтобы включить сторонний соединитель данных для подключения к Office 365 с помощью нового метода проверки подлинности, администратору организации необходимо согласиться зарегистрировать соединитель как доверенное приложение службы в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a30de-376">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="a30de-377">Для этого необходимо принять запрос на разрешение соединителей на доступ к данным Организации в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a30de-377">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="a30de-378">После принятия этого запроса сторонний соединитель данных добавляется в качестве корпоративного приложения в Azure Active Directory и представляется в качестве субъекта-службы.</span><span class="sxs-lookup"><span data-stu-id="a30de-378">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="a30de-379">Более подробную информацию можно найти в разделе [согласие администратора клиента](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="a30de-379">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="a30de-380">Ниже описаны действия, которые необходимо выполнить, чтобы получить доступ и принять запрос на регистрацию соединителя:</span><span class="sxs-lookup"><span data-stu-id="a30de-380">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="a30de-381">Перейдите на [эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) и войдите в систему, используя учетные данные глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="a30de-381">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="a30de-382">Отображается следующее диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="a30de-382">The following dialog box is displayed.</span></span> <span data-ttu-id="a30de-383">Вы можете развернуть символы крышки, чтобы просмотреть разрешения, которые будут назначены соединителю.</span><span class="sxs-lookup"><span data-stu-id="a30de-383">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Отображается диалоговое окно запроса разрешений](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="a30de-385">Нажмите кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="a30de-385">Click **Accept**.</span></span>

<span data-ttu-id="a30de-386">После принятия запроса отображается [портал Azure](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="a30de-386">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="a30de-387">Чтобы просмотреть список приложений для вашей организации, щелкните элемент **Azure Active Directory**  >  **Enterprise Applications**.</span><span class="sxs-lookup"><span data-stu-id="a30de-387">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="a30de-388">Сторонний соединитель данных Office 365 указан в колонке **корпоративные приложения** .</span><span class="sxs-lookup"><span data-stu-id="a30de-388">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a30de-389">После 30 сентября 2018 данные сторонних поставщиков больше не будут импортироваться в почтовые ящики в вашей организации, если вы не зарегистрируете сторонний соединитель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a30de-389">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="a30de-390">Обратите внимание, что существующие сторонние соединители данных (созданные до 30 сентября 2018) также должны быть зарегистрированы в Azure Active Directory, выполнив действия, описанные в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="a30de-390">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="a30de-391">Отзыв согласия с сторонним соединителем данных</span><span class="sxs-lookup"><span data-stu-id="a30de-391">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="a30de-392">После того как ваша организация отправила запрос на разрешения на регистрацию стороннего соединителя данных в Azure Active Directory, ваша организация может в любой момент отозвать это согласие.</span><span class="sxs-lookup"><span data-stu-id="a30de-392">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="a30de-393">Однако отзыв согласия для соединителя означает, что данные из стороннего источника данных больше не будут импортироваться в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-393">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="a30de-394">Чтобы отозвать согласие для стороннего соединителя данных, можно удалить приложение (удалив соответствующий субъект-службу) из Azure Active Directory с помощью колонки " **корпоративные приложения** " на портале Azure или с помощью командлета [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) в Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a30de-394">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="a30de-395">Вы также можете использовать командлет [Remove – азуреадсервицепринЦипал](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) в Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a30de-395">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="a30de-396">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a30de-396">More information</span></span>

- <span data-ttu-id="a30de-397">Как объяснялось ранее, элементы из сторонних источников данных импортируются в почтовые ящики Exchange в виде сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a30de-397">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="a30de-398">Соединитель партнера импортирует элемент, используя схему, требуемую API Office 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-398">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="a30de-399">В приведенной ниже таблице описываются свойства элемента из стороннего источника данных после его импорта в почтовый ящик Exchange в виде сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a30de-399">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="a30de-400">В этой таблице также указывается, является ли свойство сообщения обязательным.</span><span class="sxs-lookup"><span data-stu-id="a30de-400">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="a30de-401">Обязательные свойства должны быть заполнены.</span><span class="sxs-lookup"><span data-stu-id="a30de-401">Mandatory properties must be populated.</span></span> <span data-ttu-id="a30de-402">Если для элемента отсутствует обязательное свойство, оно не будет импортировано в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-402">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="a30de-403">Процесс импорта возвращает сообщение об ошибке, объясняющее, почему элемент не был импортирован и какое свойство отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a30de-403">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="a30de-404">**Свойство сообщения**</span><span class="sxs-lookup"><span data-stu-id="a30de-404">**Message property**</span></span>|<span data-ttu-id="a30de-405">**Обязательный?**</span><span class="sxs-lookup"><span data-stu-id="a30de-405">**Mandatory?**</span></span>|<span data-ttu-id="a30de-406">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a30de-406">**Description**</span></span>|<span data-ttu-id="a30de-407">**Пример значения**</span><span class="sxs-lookup"><span data-stu-id="a30de-407">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a30de-408">**FROM**</span><span class="sxs-lookup"><span data-stu-id="a30de-408">**FROM**</span></span> <br/> |<span data-ttu-id="a30de-409">Да</span><span class="sxs-lookup"><span data-stu-id="a30de-409">Yes</span></span>  <br/> |<span data-ttu-id="a30de-410">Пользователь, который создал или отправил элемент из стороннего источника данных.</span><span class="sxs-lookup"><span data-stu-id="a30de-410">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="a30de-411">Соединитель партнера пытается сопоставить идентификатор пользователя с исходным элементом (например, с маркером Twitter) с учетной записью пользователя для всех участников (в полях "от" и "Кому").</span><span class="sxs-lookup"><span data-stu-id="a30de-411">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="a30de-412">Копия сообщения будет импортирована в почтовый ящик каждого участника.</span><span class="sxs-lookup"><span data-stu-id="a30de-412">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="a30de-413">Если ни один из участников этого элемента не может быть сопоставлен с учетной записью пользователя, он будет импортирован в почтовый ящик стороннего производителя для архивации в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a30de-413">If none of the participants from the item can be mapped to an user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="a30de-414">Участник, идентифицированный как отправитель элемента, должен иметь активный почтовый ящик в Организации, в которую импортируется элемент.</span><span class="sxs-lookup"><span data-stu-id="a30de-414">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="a30de-415">Если у отправителя нет активного почтового ящика, возвращается следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="a30de-415">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="a30de-416">**TO**</span><span class="sxs-lookup"><span data-stu-id="a30de-416">**TO**</span></span> <br/> |<span data-ttu-id="a30de-417">Да</span><span class="sxs-lookup"><span data-stu-id="a30de-417">Yes</span></span>  <br/> |<span data-ttu-id="a30de-418">Пользователь, получивший элемент, если это применимо к элементу в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="a30de-418">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="a30de-419">**Тема**</span><span class="sxs-lookup"><span data-stu-id="a30de-419">**SUBJECT**</span></span> <br/> |<span data-ttu-id="a30de-420">Нет</span><span class="sxs-lookup"><span data-stu-id="a30de-420">No</span></span>  <br/> |<span data-ttu-id="a30de-421">Тема исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="a30de-421">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="a30de-422">**БУДУЩ**</span><span class="sxs-lookup"><span data-stu-id="a30de-422">**DATE**</span></span> <br/> |<span data-ttu-id="a30de-423">Да</span><span class="sxs-lookup"><span data-stu-id="a30de-423">Yes</span></span>  <br/> |<span data-ttu-id="a30de-424">Дата первоначального создания или публикации элемента в источнике данных клиента.</span><span class="sxs-lookup"><span data-stu-id="a30de-424">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="a30de-425">Например, это дата, когда сообщение Twitter было твитом.</span><span class="sxs-lookup"><span data-stu-id="a30de-425">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="a30de-426">**ТЕКСТ**</span><span class="sxs-lookup"><span data-stu-id="a30de-426">**BODY**</span></span> <br/> |<span data-ttu-id="a30de-427">Нет</span><span class="sxs-lookup"><span data-stu-id="a30de-427">No</span></span>  <br/> |<span data-ttu-id="a30de-428">Содержимое сообщения или публикации.</span><span class="sxs-lookup"><span data-stu-id="a30de-428">The contents of the message or post.</span></span> <span data-ttu-id="a30de-429">Для некоторых источников данных содержимое этого свойства может совпадать с содержимым свойства **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="a30de-429">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="a30de-430">Во время процесса импорта соединитель партнера предпринимает попытку сохранить полную точность источника контента, как это возможно.</span><span class="sxs-lookup"><span data-stu-id="a30de-430">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="a30de-431">По возможности в это свойство включаются файлы, рисунки или другое содержимое исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="a30de-431">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="a30de-432">В противном случае содержимое исходного элемента включается в свойство **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="a30de-432">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="a30de-433">Содержимое этого свойства зависит от соединителя партнера и от возможности исходной платформы.</span><span class="sxs-lookup"><span data-stu-id="a30de-433">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="a30de-434">**Крепление**</span><span class="sxs-lookup"><span data-stu-id="a30de-434">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="a30de-435">Нет</span><span class="sxs-lookup"><span data-stu-id="a30de-435">No</span></span>  <br/> |<span data-ttu-id="a30de-436">Если элемент в источнике данных (например, твит в Twitter или беседе обмена мгновенными сообщениями) имеет вложенный файл или включает изображения, то партнер по подключению будет сначала пытаться включить вложения в свойство **Body** .</span><span class="sxs-lookup"><span data-stu-id="a30de-436">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="a30de-437">Если это невозможно, то оно добавляется в свойство \* \* вложение \* \*.</span><span class="sxs-lookup"><span data-stu-id="a30de-437">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="a30de-438">К другим примерам вложений относятся отметки "Нравится" в Facebook, метаданные из источника контента, а также ответы на сообщение или публикацию.</span><span class="sxs-lookup"><span data-stu-id="a30de-438">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="a30de-439">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="a30de-439">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="a30de-440">Да</span><span class="sxs-lookup"><span data-stu-id="a30de-440">Yes</span></span>  <br/> | <span data-ttu-id="a30de-441">Это свойство с несколькими значениями, которое создается и заполняется соединителем партнера.</span><span class="sxs-lookup"><span data-stu-id="a30de-441">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="a30de-442">Это свойство имеет следующий формат `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="a30de-442">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="a30de-443">(Это свойство должно начинаться с `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="a30de-443">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="a30de-444">Этот формат похож на один для `IPM.NOTE.X` класса Message.) Это свойство содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a30de-444">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="a30de-445">`Source`: Указывает источник данных стороннего производителя; Например, Twitter, Facebook или BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="a30de-445">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="a30de-446">`Event`: Указывает тип действия, которое выполнялось в источнике данных стороннего производителя, который создал элементы; Например, твит в Twitter или в учетной записи Facebook.</span><span class="sxs-lookup"><span data-stu-id="a30de-446">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="a30de-447">Каждому источнику данных характерны свои события.</span><span class="sxs-lookup"><span data-stu-id="a30de-447">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="a30de-448">Одна из целей этого свойства — фильтрация элементов на основе типа события или источника данных, в котором создан элемент.</span><span class="sxs-lookup"><span data-stu-id="a30de-448">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="a30de-449">Например, при поиске с помощью функции обнаружения электронных данных можно найти все твиты, опубликованные определенным пользователем.</span><span class="sxs-lookup"><span data-stu-id="a30de-449">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="a30de-450">При успешном импорте элементов в почтовые ящики в Office 365, в качестве части HTTP-ответа возвращается уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="a30de-450">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="a30de-451">Этот идентификатор, называемый `x-IngestionCorrelationID` , может использоваться для последующих задач по устранению неполадок, которые являются участниками для сквозного отслеживания элементов.</span><span class="sxs-lookup"><span data-stu-id="a30de-451">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="a30de-452">Партнерам рекомендуется фиксировать эту информацию и записывать ее в журнал соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="a30de-452">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="a30de-453">Пример HTTP-отклика, содержащего этот идентификатор:</span><span class="sxs-lookup"><span data-stu-id="a30de-453">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="a30de-454">С помощью средства "поиск контента" в центре безопасности и соответствия требованиям можно искать элементы, импортированные в почтовые ящики из стороннего источника данных.</span><span class="sxs-lookup"><span data-stu-id="a30de-454">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="a30de-455">Чтобы выполнить поиск в этих импортированных элементах, можно использовать следующие пары "свойство: значение сообщения" в поле ключевое слово для поиска контента.</span><span class="sxs-lookup"><span data-stu-id="a30de-455">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="a30de-456">**`kind:externaldata`**: Используйте эту комбинацию свойства и значения для поиска всех сторонних типов данных.</span><span class="sxs-lookup"><span data-stu-id="a30de-456">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="a30de-457">Например, чтобы найти элементы, импортированные из стороннего источника данных и содержали слово "contoso" в свойстве subject импортированного элемента, используйте запрос ключевого слова `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="a30de-457">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="a30de-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Используйте эту комбинацию свойства и значения, чтобы выполнять поиск только по указанному типу сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="a30de-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="a30de-459">Например, чтобы искать только данные Facebook, содержащие слово "contoso" в свойстве subject, следует использовать запрос ключевого слова `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="a30de-459">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="a30de-460">Полный список значений, которые необходимо использовать для сторонних типов данных для `itemclass` свойства, приведен [в разделе Использование поиска контента для поиска сторонних данных, импортированных в Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span><span class="sxs-lookup"><span data-stu-id="a30de-460">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="a30de-461">Дополнительные сведения об использовании средства "Поиск контента" и создании поисковых запросов по ключевым словам см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="a30de-461">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="a30de-462">Поиск контента в Office 365</span><span class="sxs-lookup"><span data-stu-id="a30de-462">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="a30de-463">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="a30de-463">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
