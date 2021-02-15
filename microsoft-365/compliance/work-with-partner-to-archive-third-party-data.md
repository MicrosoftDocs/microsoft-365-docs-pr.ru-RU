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
description: Узнайте, как настроить настраиваемый соединитель для импорта сторонних данных из таких источников данных, как Salesforce Chatter, Yahoo Messenger или Yammer.
ms.openlocfilehash: 64e903604ea56e5f53e3cc154bd54459a6d8d554
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620215"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="e0a26-103">Архивация сторонних данных при помощи партнера</span><span class="sxs-lookup"><span data-stu-id="e0a26-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="e0a26-104">Вы можете вместе с партнером Майкрософт импортировать и архивировать данные из стороного источника данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="e0a26-105">Партнер может предоставить вам настраиваемый соединититель, настроенный для извлечения элементов из стороннего источника данных (на регулярной основе), а затем импортировать эти элементы.</span><span class="sxs-lookup"><span data-stu-id="e0a26-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="e0a26-106">Партнерский соединититель преобразует содержимое элемента из источника данных в формат сообщений электронной почты, а затем сохраняет элементы в почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="e0a26-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="e0a26-107">После импорта сторонних данных вы можете применить к этим данным такие функции соответствия требованиям Microsoft 365, как хранение для судебного разбирательства, eDiscovery, In-Place архивировать, аудит и политики хранения Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e0a26-108">Решение [соответствия коммуникациям](communication-compliance.md) в Microsoft 365 не может применяться к сторонним данным, импортируемым партнерскими соединитетелями, упомянутыми в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e0a26-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span> 

<span data-ttu-id="e0a26-109">Ниже представлен обзор процесса и действий, необходимых для работы с партнером Майкрософт по импорту сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="e0a26-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="e0a26-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="e0a26-111">Шаг 2. Создание и настройка почтового ящика сторонних данных</span><span class="sxs-lookup"><span data-stu-id="e0a26-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[<span data-ttu-id="e0a26-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="e0a26-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="e0a26-113">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="e0a26-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="e0a26-114">Шаг 5. Регистрация стороннего соединитела данных в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e0a26-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="e0a26-115">Как происходит импорт сторонних данных</span><span class="sxs-lookup"><span data-stu-id="e0a26-115">How the third-party data import process works</span></span>

<span data-ttu-id="e0a26-116">На следующем рисунке и описании объясняется, как процесс импорта сторонних данных работает при работе с партнером.</span><span class="sxs-lookup"><span data-stu-id="e0a26-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Как происходит импорт сторонних данных](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="e0a26-118">Клиент вместе со своим партнером настраивает соединители, которые будут извлекать элементы из стороннего источника данных, а затем импортировать их в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="e0a26-119">Партнерский соединититель подключается к сторонним источникам данных через сторонний API (по расписанию или по настройке) и извлекает элементы из источника данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="e0a26-120">Партнерский соединитель преобразует содержимое элемента в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e0a26-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="e0a26-121">Описание [схемы](#more-information) формата сообщений см. в разделе "Дополнительные сведения".</span><span class="sxs-lookup"><span data-stu-id="e0a26-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="e0a26-122">Партнерский соединитель подключается к службе Azure в Microsoft 365 с помощью веб-службы Exchange (EWS) через хорошо известные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="e0a26-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="e0a26-p103">Элементы импортируются в почтовый ящик определенного пользователя или общий почтовый ящик для сторонних данных. Элемент импортируется в почтовый ящик определенного пользователя или общий почтовый ящик для сторонних данных, исходя из следующих критериев:</span><span class="sxs-lookup"><span data-stu-id="e0a26-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="e0a26-125">**Элементы с ИД пользователя, соответствующие учетной записи пользователя:** Если партнерский соединитель может соединять код пользователя элемента в стороннем источнике данных с определенным ид пользователя  в Microsoft 365, элемент копируется в папку "Очистка" в папке пользователя "Элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="e0a26-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Microsoft 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="e0a26-126">У пользователей нет доступа к элементам в папке "Очистка".</span><span class="sxs-lookup"><span data-stu-id="e0a26-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="e0a26-127">Однако для поиска элементов в папке "Очистка" можно использовать средства eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e0a26-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="e0a26-128">**Элементы без ИД пользователя, соответствующего учетной записи пользователя:** Если партнерский соединиталь не может связать ИД пользователя элемента с определенным ИД пользователя,  элемент копируется в папку "Входящие" стороннего почтового ящика данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="e0a26-129">Импорт элементов в почтовый ящик позволяет вам или другим пользователям в вашей организации войти в сторонний почтовый ящик для просмотра и управления этими элементами, а также узнать, необходимо ли внести какие-либо изменения в конфигурацию соединители партнера.</span><span class="sxs-lookup"><span data-stu-id="e0a26-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="e0a26-130">Шаг 1. Поиск партнера по работе со сторонними данными</span><span class="sxs-lookup"><span data-stu-id="e0a26-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="e0a26-131">Ключевым компонентом архива сторонних данных в Microsoft 365 является поиск и работа с партнером Корпорации Майкрософт, специализирующимся на захвате данных из стороного источника данных и их импорте в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Microsoft 365.</span></span> <span data-ttu-id="e0a26-132">После импорта данных их можно архивировать и сохранить вместе с другими данными Майкрософт вашей организации, такими как электронная почта из Exchange и документы из SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e0a26-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="e0a26-133">Партнер создает соединитель, который извлекает данные из сторонних источников данных вашей организации (таких как BlackBerry, Facebook, Google+, Thomson Reuters, Twitter и YouTube) и передает эти данные в API Microsoft 365, который импортирует элементы в почтовые ящики Exchange в качестве сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e0a26-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to a Microsoft 365 API that imports items to Exchange mailboxes as email messages.</span></span>
  
<span data-ttu-id="e0a26-134">В следующих разделах списке партнеров Майкрософт (и сторонних источников данных, которые они поддерживают), которые участвуют в программе архивации сторонних данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Microsoft 365.</span></span>

[<span data-ttu-id="e0a26-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="e0a26-135">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="e0a26-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="e0a26-136">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="e0a26-137">Globanet</span><span class="sxs-lookup"><span data-stu-id="e0a26-137">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="e0a26-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="e0a26-138">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="e0a26-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="e0a26-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="e0a26-140">Verba</span><span class="sxs-lookup"><span data-stu-id="e0a26-140">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="e0a26-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="e0a26-141">17a-4 LLC</span></span>

<span data-ttu-id="e0a26-142">[17a-4 LLC](https://www.17a-4.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="e0a26-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="e0a26-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="e0a26-143">BlackBerry</span></span>
    
- <span data-ttu-id="e0a26-144">потоки данных Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="e0a26-144">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="e0a26-145">Cisco Jabber;</span><span class="sxs-lookup"><span data-stu-id="e0a26-145">Cisco Jabber</span></span>
    
- <span data-ttu-id="e0a26-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="e0a26-146">FactSet</span></span>
    
- <span data-ttu-id="e0a26-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="e0a26-147">HipChat</span></span>
    
- <span data-ttu-id="e0a26-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="e0a26-148">InvestEdge</span></span>
    
- <span data-ttu-id="e0a26-149">LivePerson</span><span class="sxs-lookup"><span data-stu-id="e0a26-149">LivePerson</span></span>
    
- <span data-ttu-id="e0a26-150">MessageLabs Data Streams;</span><span class="sxs-lookup"><span data-stu-id="e0a26-150">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="e0a26-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="e0a26-151">OpenText</span></span>
    
- <span data-ttu-id="e0a26-152">Oracle/ATG Click-to-Call Live Help;</span><span class="sxs-lookup"><span data-stu-id="e0a26-152">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="e0a26-153">Pivot IMTRADER;</span><span class="sxs-lookup"><span data-stu-id="e0a26-153">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="e0a26-154">Microsoft SharePoint;</span><span class="sxs-lookup"><span data-stu-id="e0a26-154">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="e0a26-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="e0a26-155">MindAlign</span></span>
    
- <span data-ttu-id="e0a26-156">Sitrion One (Newsgator);</span><span class="sxs-lookup"><span data-stu-id="e0a26-156">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="e0a26-157">Skype для бизнеса (Lync/OCS);</span><span class="sxs-lookup"><span data-stu-id="e0a26-157">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="e0a26-158">Skype для бизнеса Online (Lync Online);</span><span class="sxs-lookup"><span data-stu-id="e0a26-158">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="e0a26-159">базы данных SQL;</span><span class="sxs-lookup"><span data-stu-id="e0a26-159">SQL Databases</span></span>
    
- <span data-ttu-id="e0a26-160">Squawker</span><span class="sxs-lookup"><span data-stu-id="e0a26-160">Squawker</span></span>
    
- <span data-ttu-id="e0a26-161">Thomson Reuters Eikon Messenger.</span><span class="sxs-lookup"><span data-stu-id="e0a26-161">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="e0a26-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="e0a26-162">ArchiveSocial</span></span>

<span data-ttu-id="e0a26-163">[ArchiveSocial ](https://www.archivesocial.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="e0a26-163">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0a26-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="e0a26-164">Facebook</span></span>
    
- <span data-ttu-id="e0a26-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="e0a26-165">Flickr</span></span>
    
- <span data-ttu-id="e0a26-166">Много</span><span class="sxs-lookup"><span data-stu-id="e0a26-166">Instagram</span></span>
    
- <span data-ttu-id="e0a26-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e0a26-167">LinkedIn</span></span>
    
- <span data-ttu-id="e0a26-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="e0a26-168">Pinterest</span></span>
    
- <span data-ttu-id="e0a26-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="e0a26-169">Twitter</span></span>
    
- <span data-ttu-id="e0a26-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="e0a26-170">YouTube</span></span>
    
- <span data-ttu-id="e0a26-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="e0a26-171">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="e0a26-172">Globanet</span><span class="sxs-lookup"><span data-stu-id="e0a26-172">Globanet</span></span>

<span data-ttu-id="e0a26-173">[Globanet](https://www.globanet.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="e0a26-173">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0a26-174">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="e0a26-174">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="e0a26-175">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="e0a26-175">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0a26-176">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="e0a26-176">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0a26-177">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="e0a26-177">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0a26-178">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="e0a26-178">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0a26-179">Bloomberg Chat;</span><span class="sxs-lookup"><span data-stu-id="e0a26-179">Bloomberg Chat</span></span>
    
- <span data-ttu-id="e0a26-180">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="e0a26-180">Bloomberg Mail</span></span>
    
- <span data-ttu-id="e0a26-181">Box</span><span class="sxs-lookup"><span data-stu-id="e0a26-181">Box</span></span>
    
- <span data-ttu-id="e0a26-182">CipherCloud для Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="e0a26-182">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="e0a26-183">Cisco IM &amp; Presence Server (10, 10.5.1 SU1, 11.0, 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="e0a26-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="e0a26-184">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="e0a26-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="e0a26-185">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="e0a26-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="e0a26-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="e0a26-186">CrowdCompass</span></span>

- <span data-ttu-id="e0a26-187">Пользовательские текстовые файлы с делегировками</span><span class="sxs-lookup"><span data-stu-id="e0a26-187">Custom-delimited text files</span></span>
    
- <span data-ttu-id="e0a26-188">настраиваемые XML-файлы;</span><span class="sxs-lookup"><span data-stu-id="e0a26-188">Custom XML files</span></span>
    
- <span data-ttu-id="e0a26-189">Facebook (страницы)</span><span class="sxs-lookup"><span data-stu-id="e0a26-189">Facebook (Pages)</span></span>
    
- <span data-ttu-id="e0a26-190">Набор фактов</span><span class="sxs-lookup"><span data-stu-id="e0a26-190">Factset</span></span>
    
- <span data-ttu-id="e0a26-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="e0a26-191">FXConnect</span></span>
    
- <span data-ttu-id="e0a26-192">ICE Chat или YellowJacket;</span><span class="sxs-lookup"><span data-stu-id="e0a26-192">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="e0a26-193">Jive</span><span class="sxs-lookup"><span data-stu-id="e0a26-193">Jive</span></span>
    
- <span data-ttu-id="e0a26-194">Macgregor XIP;</span><span class="sxs-lookup"><span data-stu-id="e0a26-194">Macgregor XIP</span></span>

- <span data-ttu-id="e0a26-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e0a26-195">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="e0a26-196">Microsoft OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e0a26-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="e0a26-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0a26-197">Microsoft Teams</span></span>
       
- <span data-ttu-id="e0a26-198">Microsoft Yammer;</span><span class="sxs-lookup"><span data-stu-id="e0a26-198">Microsoft Yammer</span></span>
    
- <span data-ttu-id="e0a26-199">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="e0a26-199">Mobile Guard</span></span>
    
- <span data-ttu-id="e0a26-200">Pivot</span><span class="sxs-lookup"><span data-stu-id="e0a26-200">Pivot</span></span>
    
- <span data-ttu-id="e0a26-201">Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="e0a26-201">Salesforce Chatter</span></span>

- <span data-ttu-id="e0a26-202">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e0a26-202">Skype for Business Online</span></span>
    
- <span data-ttu-id="e0a26-203">Skype для бизнеса, версии от 2007 R2 до 2016 (локальные);</span><span class="sxs-lookup"><span data-stu-id="e0a26-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="e0a26-204">Slack Enterprise Grid;</span><span class="sxs-lookup"><span data-stu-id="e0a26-204">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="e0a26-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="e0a26-205">Symphony</span></span>
    
- <span data-ttu-id="e0a26-206">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="e0a26-206">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="e0a26-207">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="e0a26-207">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="e0a26-208">Thomson Reuters Dealings 3000 или FX Trading;</span><span class="sxs-lookup"><span data-stu-id="e0a26-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="e0a26-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="e0a26-209">Twitter</span></span>
    
- <span data-ttu-id="e0a26-210">UBS Chat;</span><span class="sxs-lookup"><span data-stu-id="e0a26-210">UBS Chat</span></span>
    
- <span data-ttu-id="e0a26-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="e0a26-211">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="e0a26-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="e0a26-212">OpenText</span></span>

<span data-ttu-id="e0a26-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="e0a26-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0a26-214">Axs Encrypted;</span><span class="sxs-lookup"><span data-stu-id="e0a26-214">Axs Encrypted</span></span>
    
- <span data-ttu-id="e0a26-215">Axs Exchange;</span><span class="sxs-lookup"><span data-stu-id="e0a26-215">Axs Exchange</span></span>
    
- <span data-ttu-id="e0a26-216">Axs Local Archive;</span><span class="sxs-lookup"><span data-stu-id="e0a26-216">Axs Local Archive</span></span>
    
- <span data-ttu-id="e0a26-217">Axs PlaceHolder;</span><span class="sxs-lookup"><span data-stu-id="e0a26-217">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="e0a26-218">Axs Signed;</span><span class="sxs-lookup"><span data-stu-id="e0a26-218">Axs Signed</span></span>
    
- <span data-ttu-id="e0a26-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e0a26-219">Bloomberg</span></span>
    
- <span data-ttu-id="e0a26-220">Thomson Reuters.</span><span class="sxs-lookup"><span data-stu-id="e0a26-220">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="e0a26-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="e0a26-221">Smarsh</span></span>

<span data-ttu-id="e0a26-222">[Smarsh](https://www.smarsh.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="e0a26-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0a26-223">AIM</span><span class="sxs-lookup"><span data-stu-id="e0a26-223">AIM</span></span>
    
- <span data-ttu-id="e0a26-224">American Idol;</span><span class="sxs-lookup"><span data-stu-id="e0a26-224">American Idol</span></span>
    
- <span data-ttu-id="e0a26-225">Apple Juice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-225">Apple Juice</span></span>
    
- <span data-ttu-id="e0a26-226">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="e0a26-226">AOL with Pivot client</span></span>
    
- <span data-ttu-id="e0a26-227">Ares</span><span class="sxs-lookup"><span data-stu-id="e0a26-227">Ares</span></span>
    
- <span data-ttu-id="e0a26-228">Bazaar Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-228">Bazaar Voice</span></span>
    
- <span data-ttu-id="e0a26-229">Bear Share;</span><span class="sxs-lookup"><span data-stu-id="e0a26-229">Bear Share</span></span>
    
- <span data-ttu-id="e0a26-230">Bit Torrent;</span><span class="sxs-lookup"><span data-stu-id="e0a26-230">Bit Torrent</span></span>
    
- <span data-ttu-id="e0a26-231">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="e0a26-231">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0a26-232">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="e0a26-232">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0a26-233">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="e0a26-233">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0a26-234">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="e0a26-234">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0a26-235">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="e0a26-235">Bloomberg Mail</span></span>
    
- <span data-ttu-id="e0a26-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="e0a26-236">CellTrust</span></span>
    
- <span data-ttu-id="e0a26-237">импорт чата;</span><span class="sxs-lookup"><span data-stu-id="e0a26-237">Chat Import</span></span>
    
- <span data-ttu-id="e0a26-238">политика и ведение журнала чата в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="e0a26-238">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="e0a26-239">Чаттер</span><span class="sxs-lookup"><span data-stu-id="e0a26-239">Chatter</span></span>
    
- <span data-ttu-id="e0a26-240">Cisco IM &amp; Presence Server (9.0.1, 9.1, 9.1.1 SU1, 10, 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="e0a26-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="e0a26-241">Cisco Unified Presence Server (версии 8.6.3, 8.6.4, 8.6.5);</span><span class="sxs-lookup"><span data-stu-id="e0a26-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="e0a26-242">импорт совместной работы;</span><span class="sxs-lookup"><span data-stu-id="e0a26-242">Collaboration Import</span></span>
    
- <span data-ttu-id="e0a26-243">ведение журнала совместной работы в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="e0a26-243">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="e0a26-244">Direct Connect;</span><span class="sxs-lookup"><span data-stu-id="e0a26-244">Direct Connect</span></span>
    
- <span data-ttu-id="e0a26-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="e0a26-245">Facebook</span></span>
    
- <span data-ttu-id="e0a26-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="e0a26-246">FactSet</span></span>
    
- <span data-ttu-id="e0a26-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="e0a26-247">FastTrack</span></span>
    
- <span data-ttu-id="e0a26-248">Гнунелла</span><span class="sxs-lookup"><span data-stu-id="e0a26-248">Gnutella</span></span>
    
- <span data-ttu-id="e0a26-249">Google+</span><span class="sxs-lookup"><span data-stu-id="e0a26-249">Google+</span></span>
    
- <span data-ttu-id="e0a26-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="e0a26-250">GoToMyPC</span></span>
    
- <span data-ttu-id="e0a26-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="e0a26-251">Hopster</span></span>
    
- <span data-ttu-id="e0a26-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="e0a26-252">HubConnex</span></span>
    
- <span data-ttu-id="e0a26-253">IBM Connections (версии 3.0.1, 4.0, 4.5, 4.5 CR3, 5);</span><span class="sxs-lookup"><span data-stu-id="e0a26-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="e0a26-254">IBM Connections Chat Cloud;</span><span class="sxs-lookup"><span data-stu-id="e0a26-254">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="e0a26-255">IBM Connections Social Cloud;</span><span class="sxs-lookup"><span data-stu-id="e0a26-255">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="e0a26-256">IBM SameTime Advanced 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="e0a26-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="e0a26-257">IBM SameTime Communicate 9.0;</span><span class="sxs-lookup"><span data-stu-id="e0a26-257">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="e0a26-258">IBM SameTime Community (версии 8.0.2, 8.5.1 IFR2, 8.5.2 IFR1, 9.1);</span><span class="sxs-lookup"><span data-stu-id="e0a26-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="e0a26-259">IBM SameTime Complete 9.0;</span><span class="sxs-lookup"><span data-stu-id="e0a26-259">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="e0a26-260">IBM SameTime Conference 9.0;</span><span class="sxs-lookup"><span data-stu-id="e0a26-260">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="e0a26-261">IBM SameTime Meeting 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="e0a26-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="e0a26-262">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="e0a26-262">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="e0a26-263">импорт мгновенных сообщений;</span><span class="sxs-lookup"><span data-stu-id="e0a26-263">IM Import</span></span>
    
- <span data-ttu-id="e0a26-264">политика и ведение журнала обмена мгновенными сообщениями в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="e0a26-264">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="e0a26-265">Indii Messenger;</span><span class="sxs-lookup"><span data-stu-id="e0a26-265">Indii Messenger</span></span>
    
- <span data-ttu-id="e0a26-266">Instant Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="e0a26-266">Instant Bloomberg</span></span>
    
- <span data-ttu-id="e0a26-267">IRC</span><span class="sxs-lookup"><span data-stu-id="e0a26-267">IRC</span></span>
    
- <span data-ttu-id="e0a26-268">Jive</span><span class="sxs-lookup"><span data-stu-id="e0a26-268">Jive</span></span>
    
- <span data-ttu-id="e0a26-269">Jive 6 Real Time Logging (версии 6, 7);</span><span class="sxs-lookup"><span data-stu-id="e0a26-269">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="e0a26-270">импорт Jive;</span><span class="sxs-lookup"><span data-stu-id="e0a26-270">Jive Import</span></span>
    
- <span data-ttu-id="e0a26-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="e0a26-271">JXTA</span></span>
    
- <span data-ttu-id="e0a26-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e0a26-272">LinkedIn</span></span>
    
- <span data-ttu-id="e0a26-273">Microsoft Lync (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="e0a26-273">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="e0a26-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="e0a26-274">MFTP</span></span>
    
- <span data-ttu-id="e0a26-275">Microsoft Lync 2013 Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-275">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="e0a26-276">Microsoft SharePoint (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="e0a26-276">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="e0a26-277">Microsoft SharePoint Online;</span><span class="sxs-lookup"><span data-stu-id="e0a26-277">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="e0a26-278">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="e0a26-278">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="e0a26-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="e0a26-279">MindAlign</span></span>
    
- <span data-ttu-id="e0a26-280">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="e0a26-280">Mobile Guard</span></span>
    
- <span data-ttu-id="e0a26-281">MSN</span><span class="sxs-lookup"><span data-stu-id="e0a26-281">MSN</span></span>
    
- <span data-ttu-id="e0a26-282">My Space;</span><span class="sxs-lookup"><span data-stu-id="e0a26-282">My Space</span></span>
    
- <span data-ttu-id="e0a26-283">THENetwork</span><span class="sxs-lookup"><span data-stu-id="e0a26-283">NEONetwork</span></span>
    
- <span data-ttu-id="e0a26-284">Microsoft 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="e0a26-284">Microsoft 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="e0a26-285">Общий мгновенный доступ к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0a26-285">Microsoft 365 Shared IM</span></span>
    
- <span data-ttu-id="e0a26-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="e0a26-286">Pinterest</span></span>
    
- <span data-ttu-id="e0a26-287">Pivot</span><span class="sxs-lookup"><span data-stu-id="e0a26-287">Pivot</span></span>
    
- <span data-ttu-id="e0a26-288">QQ</span><span class="sxs-lookup"><span data-stu-id="e0a26-288">QQ</span></span>
    
- <span data-ttu-id="e0a26-289">Skype для бизнеса 2015;</span><span class="sxs-lookup"><span data-stu-id="e0a26-289">Skype for Business 2015</span></span>
    
- <span data-ttu-id="e0a26-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="e0a26-290">SoftEther</span></span>
    
- <span data-ttu-id="e0a26-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="e0a26-291">Symphony</span></span>
    
- <span data-ttu-id="e0a26-292">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="e0a26-292">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="e0a26-293">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="e0a26-293">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="e0a26-294">Tor</span><span class="sxs-lookup"><span data-stu-id="e0a26-294">Tor</span></span>
    
- <span data-ttu-id="e0a26-295">TTT</span><span class="sxs-lookup"><span data-stu-id="e0a26-295">TTT</span></span>
    
- <span data-ttu-id="e0a26-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="e0a26-296">Twitter</span></span>
    
- <span data-ttu-id="e0a26-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="e0a26-297">WinMX</span></span>
    
- <span data-ttu-id="e0a26-298">Winny</span><span class="sxs-lookup"><span data-stu-id="e0a26-298">Winny</span></span>
    
- <span data-ttu-id="e0a26-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="e0a26-299">Yahoo</span></span>
    
- <span data-ttu-id="e0a26-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="e0a26-300">Yammer</span></span>
    
- <span data-ttu-id="e0a26-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="e0a26-301">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="e0a26-302">Verba</span><span class="sxs-lookup"><span data-stu-id="e0a26-302">Verba</span></span>

<span data-ttu-id="e0a26-303">[Verba](https://www.verba.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="e0a26-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0a26-304">Avaya Aura Video;</span><span class="sxs-lookup"><span data-stu-id="e0a26-304">Avaya Aura Video</span></span>
    
- <span data-ttu-id="e0a26-305">Avaya Aura Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-305">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="e0a26-306">Avtec Radio;</span><span class="sxs-lookup"><span data-stu-id="e0a26-306">Avtec Radio</span></span>
    
- <span data-ttu-id="e0a26-307">Bosch/Telex Radio;</span><span class="sxs-lookup"><span data-stu-id="e0a26-307">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="e0a26-308">BroadSoft Video;</span><span class="sxs-lookup"><span data-stu-id="e0a26-308">BroadSoft Video</span></span>
    
- <span data-ttu-id="e0a26-309">BroadSoft Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-309">BroadSoft Voice</span></span>
    
- <span data-ttu-id="e0a26-310">Centile Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-310">Centile Voice</span></span>
    
- <span data-ttu-id="e0a26-311">Cisco Jabber IM;</span><span class="sxs-lookup"><span data-stu-id="e0a26-311">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="e0a26-312">Cisco UC Video;</span><span class="sxs-lookup"><span data-stu-id="e0a26-312">Cisco UC Video</span></span>
    
- <span data-ttu-id="e0a26-313">Cisco UC Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-313">Cisco UC Voice</span></span>
    
- <span data-ttu-id="e0a26-314">Cisco UCCX/UCCE Video</span><span class="sxs-lookup"><span data-stu-id="e0a26-314">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="e0a26-315">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="e0a26-315">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="e0a26-316">ESChat Radio;</span><span class="sxs-lookup"><span data-stu-id="e0a26-316">ESChat Radio</span></span>
    
- <span data-ttu-id="e0a26-317">Geoman Contact Expert;</span><span class="sxs-lookup"><span data-stu-id="e0a26-317">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="e0a26-318">IP Trade Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-318">IP Trade Voice</span></span>
    
- <span data-ttu-id="e0a26-319">Luware LUCS Contact Center;</span><span class="sxs-lookup"><span data-stu-id="e0a26-319">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="e0a26-320">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="e0a26-320">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="e0a26-321">Mitel MiContact Center для Lync (prairieFyre);</span><span class="sxs-lookup"><span data-stu-id="e0a26-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="e0a26-322">Oracle / Acme Packet Session Border Controller Video;</span><span class="sxs-lookup"><span data-stu-id="e0a26-322">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="e0a26-323">Oracle / Acme Packet Session Border Controller Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-323">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="e0a26-324">Singtel Mobile Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-324">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="e0a26-325">SIPREC Video;</span><span class="sxs-lookup"><span data-stu-id="e0a26-325">SIPREC Video</span></span>
    
-  <span data-ttu-id="e0a26-326">SIPREC Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-326">SIPREC Voice</span></span> 
    
- <span data-ttu-id="e0a26-327">Skype для бизнеса / Lync IM;</span><span class="sxs-lookup"><span data-stu-id="e0a26-327">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="e0a26-328">Skype для бизнеса / Lync Video;</span><span class="sxs-lookup"><span data-stu-id="e0a26-328">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="e0a26-329">Skype для бизнеса / Lync Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-329">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="e0a26-330">Speakerbus Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-330">Speakerbus Voice</span></span>
    
- <span data-ttu-id="e0a26-331">Standard SIP/H.323 Video;</span><span class="sxs-lookup"><span data-stu-id="e0a26-331">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="e0a26-332">Standard SIP/H.323 Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-332">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="e0a26-333">Truphone Voice;</span><span class="sxs-lookup"><span data-stu-id="e0a26-333">Truphone Voice</span></span>
    
- <span data-ttu-id="e0a26-334">TwistedPair Radio;</span><span class="sxs-lookup"><span data-stu-id="e0a26-334">TwistedPair Radio</span></span>
    
- <span data-ttu-id="e0a26-335">рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="e0a26-335">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a><span data-ttu-id="e0a26-336">Шаг 2. Создание и настройка почтового ящика сторонних данных в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0a26-336">Step 2: Create and configure a third-party data mailbox in Microsoft 365</span></span>

<span data-ttu-id="e0a26-337">Вот как создать и настроить сторонний почтовый ящик данных для импорта данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Microsoft 365.</span></span> <span data-ttu-id="e0a26-338">Как объяснялось ранее, элементы импортируется в этот почтовый ящик, если партнерский соединититель не может связать его с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="e0a26-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>
  
 <span data-ttu-id="e0a26-339">**Выполнение этих задач в Центре администрирования Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="e0a26-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="e0a26-340">Создайте учетную запись пользователя и назначьте ее лицензии на Exchange Online (план 2); см. ["Добавление пользователей в Microsoft 365".](https://go.microsoft.com/fwlink/p/?LinkId=692098)</span><span class="sxs-lookup"><span data-stu-id="e0a26-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="e0a26-341">Лицензия плана 2 необходима для помещения почтового ящика на хранение для судебного разбирательства или для архивного почтового ящика с неограниченной квотой хранилища.</span><span class="sxs-lookup"><span data-stu-id="e0a26-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="e0a26-342">Добавьте учетную запись пользователя для почтового ящика сторонних данных в роль администратора **Exchange** в Microsoft 365; см. ["Назначение ролей администратора" в Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=532393)</span><span class="sxs-lookup"><span data-stu-id="e0a26-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Microsoft 365; see [Assign admin roles in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e0a26-343">Запишите данные этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e0a26-343">Write down the credentials for this user account.</span></span> <span data-ttu-id="e0a26-344">Их необходимо предоставить партнеру, как описано в шаге 4.</span><span class="sxs-lookup"><span data-stu-id="e0a26-344">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="e0a26-345">**Выполнение этих задач в Центре администрирования Exchange**</span><span class="sxs-lookup"><span data-stu-id="e0a26-345">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="e0a26-346">Скрытие почтового ящика сторонних данных из адресной книги и других списков адресов в организации; см. ["Управление почтовыми ящиками пользователей".](https://go.microsoft.com/fwlink/p/?LinkId=616058)</span><span class="sxs-lookup"><span data-stu-id="e0a26-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="e0a26-347">Можно также выполнить следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e0a26-347">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="e0a26-348">**Назначьте** стороне почтовому ящику данных разрешение "Полный доступ", чтобы администраторы или сотрудники по обеспечению соответствия требованиям могли открывать сторонний почтовый ящик данных в настольном клиенте Outlook; см. ["Управление разрешениями для получателей".](https://go.microsoft.com/fwlink/p/?LinkId=692104)</span><span class="sxs-lookup"><span data-stu-id="e0a26-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="e0a26-349">В включить следующие функции, связанные с соответствием требованиям, для почтового ящика сторонних данных:</span><span class="sxs-lookup"><span data-stu-id="e0a26-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="e0a26-350">Включить архивный почтовый ящик; см. ["Включить архивные почтовые ящики"](enable-archive-mailboxes.md) и ["Включить неограниченное архивировать".](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="e0a26-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="e0a26-351">Это позволяет освободить место в основном почтовом ящике путем настройки политики архивирования, которая перемещает сторонние элементы данных в архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="e0a26-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="e0a26-352">Это обеспечивает неограниченное хранение сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-352">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="e0a26-353">Поместите почтовый ящик сторонних данных на хранение для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="e0a26-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="e0a26-354">Вы также можете применить политику хранения Microsoft 365 в Центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e0a26-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="e0a26-355">Помещение этого почтового ящика на удержание позволяет хранить сторонние элементы данных (неопределенное время или в течение указанного срока) и не позволяет им быть стертыми из почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="e0a26-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="e0a26-356">См. один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="e0a26-356">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="e0a26-357">Применение к почтовому ящику функции судебного удержания</span><span class="sxs-lookup"><span data-stu-id="e0a26-357">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="e0a26-358">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="e0a26-358">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="e0a26-359">Включить ведение журнала аудита почтовых ящиков для доступа владельца, делегата и администратора к почтовому ящику сторонних данных; см. ["Включить аудит почтовых ящиков".](enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="e0a26-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="e0a26-360">Это позволяет проверять все действия, выполняемые любым пользователем, который имеет доступ к почтовому ящику сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="e0a26-361">Шаг 3. Настройка поддержки сторонних данных для почтовых ящиков пользователей</span><span class="sxs-lookup"><span data-stu-id="e0a26-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="e0a26-362">Следующим шагом является настройка поддержки сторонних данных для почтовых ящиков пользователей.</span><span class="sxs-lookup"><span data-stu-id="e0a26-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="e0a26-363">Выполните эти задачи с помощью Центра администрирования Exchange или с помощью соответствующих Windows PowerShell управления.</span><span class="sxs-lookup"><span data-stu-id="e0a26-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="e0a26-364">Включить архивный почтовый ящик для каждого пользователя; см. ["Включить архивные почтовые ящики"](enable-archive-mailboxes.md) и ["Включить неограниченное архивировать".](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="e0a26-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="e0a26-365">Применение политики хранения Microsoft 365 к почтовым ящикам пользователей на хранение для судебного разбирательства; см. один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="e0a26-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="e0a26-366">Применение к почтовому ящику функции судебного удержания</span><span class="sxs-lookup"><span data-stu-id="e0a26-366">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="e0a26-367">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="e0a26-367">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="e0a26-368">Как отмечалось ранее, при помещении почтовых ящиков на хранение можно указать длительность хранения элементов из источника сторонних данных или выбрать бессрочное хранение.</span><span class="sxs-lookup"><span data-stu-id="e0a26-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="e0a26-369">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="e0a26-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="e0a26-370">Последний шаг — предоставить партнеру следующие сведения, чтобы он может настроить соединители для подключения к организации для импорта данных в почтовые ящики пользователей и в почтовый ящик сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="e0a26-371">Конечная точка, используемая для подключения к службе Azure в Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e0a26-371">The endpoint used to connect to the Azure service in Microsoft 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="e0a26-372">Учетные данные для входа (ИД пользователя Microsoft 365 и пароль) почтового ящика сторонних данных, созданного на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="e0a26-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="e0a26-373">Эти учетные данные требуются соединителю партнера для доступа к элементам и их импорта в почтовые ящики пользователей и почтовый ящик со сторонними данными.</span><span class="sxs-lookup"><span data-stu-id="e0a26-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="e0a26-374">Шаг 5. Регистрация стороннего соединитела данных в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e0a26-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="e0a26-375">С 30 сентября 2018 г. служба Azure в Microsoft 365 начнет использовать современную проверку подлинности в Exchange Online для проверки подлинности сторонних соединителях данных, которые пытаются подключиться к организации для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-375">Starting September 30, 2018, the Azure service in Microsoft 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="e0a26-376">Причина этого изменения заключается в том, что современная проверка подлинности обеспечивает больше безопасности, чем текущий метод, основанный на списке разрешаний для сторонних соединителях, которые используют ранее описанную конечную точку для подключения к службе Azure.</span><span class="sxs-lookup"><span data-stu-id="e0a26-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="e0a26-377">Чтобы позволить стороннему соединителу данных подключаться к Microsoft 365 с помощью нового современного метода проверки подлинности, администратор вашей организации должен согласиться зарегистрировать соединителение в качестве доверенного приложения-службы в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e0a26-377">To enable a third-party data connector to connect to Microsoft 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="e0a26-378">Для этого необходимо принять запрос на разрешение, чтобы разрешить соединители получать доступ к данным вашей организации в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e0a26-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="e0a26-379">После того как вы примете этот запрос, сторонний соединитатель данных будет добавлен в качестве корпоративного приложения в Azure Active Directory и представлен в качестве участника-службы.</span><span class="sxs-lookup"><span data-stu-id="e0a26-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="e0a26-380">Дополнительные сведения о процессе получения согласия см. в [процедуре согласия администратора клиента.](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent)</span><span class="sxs-lookup"><span data-stu-id="e0a26-380">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="e0a26-381">Вот как получить доступ к запросу на регистрацию соединители и принять его:</span><span class="sxs-lookup"><span data-stu-id="e0a26-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="e0a26-382">Перейдите [на эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) и войдите, используя учетные данные глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e0a26-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="e0a26-383">Отобразилось следующее диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="e0a26-383">The following dialog box is displayed.</span></span> <span data-ttu-id="e0a26-384">Вы можете развернуть этот список, чтобы просмотреть разрешения, которые будут назначены соединители.</span><span class="sxs-lookup"><span data-stu-id="e0a26-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Отобразилось диалоговое окно запроса разрешений](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="e0a26-386">Нажмите кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="e0a26-386">Click **Accept**.</span></span>

<span data-ttu-id="e0a26-387">После того как вы примете запрос, отобразит портал [Azure.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="e0a26-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="e0a26-388">Чтобы просмотреть список приложений для организации, щелкните **приложения Azure Active Directory**  >  **Enterprise.**</span><span class="sxs-lookup"><span data-stu-id="e0a26-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="e0a26-389">В blade корпоративных приложений указан сторонний соединитатель  данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-389">The Microsoft 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0a26-390">После 30 сентября 2018 г. сторонние данные больше не будут импортироваться в почтовые ящики в организации, если вы не зарегистрируете сторонний соединиталь данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e0a26-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="e0a26-391">Обратите внимание, что существующие сторонние соединители данных (созданные до 30 сентября 2018 г.) также должны быть зарегистрированы в Azure Active Directory, следуя процедуре, которая была создана до 30 сентября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="e0a26-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="e0a26-392">Отзыв согласия для стороннего соединитела данных</span><span class="sxs-lookup"><span data-stu-id="e0a26-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="e0a26-393">После того как ваша организация согласится на запрос разрешений для регистрации стороннего соединитела данных в Azure Active Directory, ваша организация может отопросить это согласие в любое время.</span><span class="sxs-lookup"><span data-stu-id="e0a26-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="e0a26-394">Однако отзыв согласия для соединители означает, что данные из стороннего источника данных больше не будут импортироваться в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Microsoft 365.</span></span>

<span data-ttu-id="e0a26-395">Чтобы отопустить согласие для стороннего соединителя данных, можно удалить приложение (удалит соответствующего участника-службы) из Azure Active Directory с помощью blade корпоративных приложений на портале Azure или с помощью [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) в Microsoft 365 PowerShell. </span><span class="sxs-lookup"><span data-stu-id="e0a26-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span></span> <span data-ttu-id="e0a26-396">Кроме того, в Azure Active Directory PowerShell можно использовать cmdlet [Remove-AzureADServicePrincipal.](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal)</span><span class="sxs-lookup"><span data-stu-id="e0a26-396">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="e0a26-397">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e0a26-397">More information</span></span>

- <span data-ttu-id="e0a26-398">Как объяснялось ранее, элементы из сторонних источников данных импортируются в почтовые ящики Exchange в виде сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e0a26-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="e0a26-399">Партнерский соединитель импортирует элемент с помощью схемы, требуемой API Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-399">The partner connector imports the item using a schema required by the Microsoft 365 API.</span></span> <span data-ttu-id="e0a26-400">В приведенной ниже таблице описываются свойства элемента из стороннего источника данных после его импорта в почтовый ящик Exchange в виде сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e0a26-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="e0a26-401">В этой таблице также указывается, является ли свойство сообщения обязательным.</span><span class="sxs-lookup"><span data-stu-id="e0a26-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="e0a26-402">Обязательные свойства должны быть заполнены.</span><span class="sxs-lookup"><span data-stu-id="e0a26-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="e0a26-403">Если элемент отсутствует обязательное свойство, он не будет импортироваться в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-403">If an item is missing a mandatory property, it won't be imported to Microsoft 365.</span></span> <span data-ttu-id="e0a26-404">Процесс импорта возвращает сообщение об ошибке, объясняя, почему элемент не импортируется и какое свойство отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e0a26-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="e0a26-405">**Свойство сообщения**</span><span class="sxs-lookup"><span data-stu-id="e0a26-405">**Message property**</span></span>|<span data-ttu-id="e0a26-406">**Обязательный?**</span><span class="sxs-lookup"><span data-stu-id="e0a26-406">**Mandatory?**</span></span>|<span data-ttu-id="e0a26-407">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e0a26-407">**Description**</span></span>|<span data-ttu-id="e0a26-408">**Пример значения**</span><span class="sxs-lookup"><span data-stu-id="e0a26-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e0a26-409">**FROM**</span><span class="sxs-lookup"><span data-stu-id="e0a26-409">**FROM**</span></span> <br/> |<span data-ttu-id="e0a26-410">Да</span><span class="sxs-lookup"><span data-stu-id="e0a26-410">Yes</span></span>  <br/> |<span data-ttu-id="e0a26-411">Пользователь, который создал или отправил элемент из стороннего источника данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="e0a26-412">Партнерский соединититель пытается связать ИД пользователя из элемента источника (например, окне Twitter) с учетной записью пользователя для всех участников (пользователей в полях "ОТ" и "К").</span><span class="sxs-lookup"><span data-stu-id="e0a26-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="e0a26-413">Копия сообщения будет импортирована в почтовый ящик каждого участника.</span><span class="sxs-lookup"><span data-stu-id="e0a26-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="e0a26-414">Если ни один из участников из элемента не может быть соотобращен с учетной записью пользователя, элемент будет импортироваться в сторонний почтовый ящик архива в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a26-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Microsoft 365.</span></span>  <br/> <br/> <span data-ttu-id="e0a26-415">У участника, который определен как отправитель элемента, должен быть активный почтовый ящик в организации, в которую импортируется элемент.</span><span class="sxs-lookup"><span data-stu-id="e0a26-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="e0a26-416">Если у отправителя нет активного почтового ящика, возвращается следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="e0a26-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="e0a26-417">**TO**</span><span class="sxs-lookup"><span data-stu-id="e0a26-417">**TO**</span></span> <br/> |<span data-ttu-id="e0a26-418">Да</span><span class="sxs-lookup"><span data-stu-id="e0a26-418">Yes</span></span>  <br/> |<span data-ttu-id="e0a26-419">Пользователь, получивший элемент, если это применимо к элементу в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="e0a26-420">**Тема**</span><span class="sxs-lookup"><span data-stu-id="e0a26-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="e0a26-421">Нет</span><span class="sxs-lookup"><span data-stu-id="e0a26-421">No</span></span>  <br/> |<span data-ttu-id="e0a26-422">Тема исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="e0a26-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="e0a26-423">**DATE**</span><span class="sxs-lookup"><span data-stu-id="e0a26-423">**DATE**</span></span> <br/> |<span data-ttu-id="e0a26-424">Да</span><span class="sxs-lookup"><span data-stu-id="e0a26-424">Yes</span></span>  <br/> |<span data-ttu-id="e0a26-425">Дата создания или публикации элемента в источнике данных клиента.</span><span class="sxs-lookup"><span data-stu-id="e0a26-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="e0a26-426">Например, эта дата, когда сообщение в Twitter было в твите.</span><span class="sxs-lookup"><span data-stu-id="e0a26-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="e0a26-427">**BODY**</span><span class="sxs-lookup"><span data-stu-id="e0a26-427">**BODY**</span></span> <br/> |<span data-ttu-id="e0a26-428">Нет</span><span class="sxs-lookup"><span data-stu-id="e0a26-428">No</span></span>  <br/> |<span data-ttu-id="e0a26-429">Содержимое сообщения или публикации.</span><span class="sxs-lookup"><span data-stu-id="e0a26-429">The contents of the message or post.</span></span> <span data-ttu-id="e0a26-430">Для некоторых источников данных содержимое этого свойства может совпадать с содержимым свойства **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="e0a26-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="e0a26-431">В процессе импорта партнерский соединитель пытается обеспечить полную надзорность источника контента, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="e0a26-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="e0a26-432">По возможности в это свойство включаются файлы, рисунки или другое содержимое исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="e0a26-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="e0a26-433">В противном случае содержимое исходного элемента включается в свойство **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="e0a26-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="e0a26-434">Содержимое этого свойства зависит от партнерского соединитела и возможности платформы источника.</span><span class="sxs-lookup"><span data-stu-id="e0a26-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="e0a26-435">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="e0a26-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="e0a26-436">Нет</span><span class="sxs-lookup"><span data-stu-id="e0a26-436">No</span></span>  <br/> |<span data-ttu-id="e0a26-437">Если элемент в источнике данных (например, твит в Twitter или беседа с обменом мгновенными сообщениями) содержит вложенный файл или изображения, партнерский подключение сначала попытается включить вложения в свойство **BODY.**</span><span class="sxs-lookup"><span data-stu-id="e0a26-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="e0a26-438">Если это невозможно, оно добавляется в свойство \*\* ATTACHMENT \*\*.</span><span class="sxs-lookup"><span data-stu-id="e0a26-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="e0a26-439">К другим примерам вложений относятся отметки "Нравится" в Facebook, метаданные из источника контента, а также ответы на сообщение или публикацию.</span><span class="sxs-lookup"><span data-stu-id="e0a26-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="e0a26-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="e0a26-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="e0a26-441">Да</span><span class="sxs-lookup"><span data-stu-id="e0a26-441">Yes</span></span>  <br/> | <span data-ttu-id="e0a26-442">Это свойство с несколькими значениями, которое создается и заполняется партнерским соединитетелем.</span><span class="sxs-lookup"><span data-stu-id="e0a26-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="e0a26-443">Формат этого свойства:  `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="e0a26-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="e0a26-444">(Это свойство должно начинаться с  `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="e0a26-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="e0a26-445">Этот формат аналогиен формату для  `IPM.NOTE.X` класса сообщений.) Это свойство включает следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e0a26-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="e0a26-446">`Source`: указывает сторонний источник данных; например, Twitter, Facebook или BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="e0a26-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="e0a26-447">`Event`: указывает тип действия, выполненного в стороном источнике данных, который выпустил элементы; например, твит в Twitter или запись в Facebook.</span><span class="sxs-lookup"><span data-stu-id="e0a26-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="e0a26-448">Каждому источнику данных характерны свои события.</span><span class="sxs-lookup"><span data-stu-id="e0a26-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="e0a26-449">Одна из целей этого свойства — фильтрация элементов на основе типа события или источника данных, в котором создан элемент.</span><span class="sxs-lookup"><span data-stu-id="e0a26-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="e0a26-450">Например, при поиске с помощью функции обнаружения электронных данных можно найти все твиты, опубликованные определенным пользователем.</span><span class="sxs-lookup"><span data-stu-id="e0a26-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="e0a26-451">При успешном импорте элементов в почтовые ящики в Microsoft 365 уникальный идентификатор возвращается вызываемой части HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e0a26-451">When items are successfully imported to mailboxes in Microsoft 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="e0a26-452">Этот идентификатор, который называется , может использоваться партнерами для последующего устранения неполадок для последующего отслеживания  `x-IngestionCorrelationID` элементов.</span><span class="sxs-lookup"><span data-stu-id="e0a26-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="e0a26-453">Партнерам рекомендуется фиксировать эту информацию и записывать ее в журнал соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e0a26-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="e0a26-454">Пример HTTP-отклика, содержащего этот идентификатор:</span><span class="sxs-lookup"><span data-stu-id="e0a26-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="e0a26-455">Средство "Поиск контента" можно использовать в Центре безопасности и соответствия требованиям для поиска элементов, импортируемых в почтовые ящики из стороного источника данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="e0a26-456">Для поиска импортируемых элементов можно использовать следующие пары "свойство-значение сообщения" в поле ключевых слов для поиска контента.</span><span class="sxs-lookup"><span data-stu-id="e0a26-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="e0a26-457">**`kind:externaldata`**: Используйте эту пару "свойство-значение" для поиска по всем сторонним типам данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-457">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="e0a26-458">Например, для поиска элементов, импортируемых из стороненного источника данных и содержащих слово "contoso" в свойстве Subject импортируемого элемента, используется запрос по ключевому слову  `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="e0a26-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="e0a26-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Используйте эту пару "свойство-значение", чтобы искать только тип сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="e0a26-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="e0a26-460">Например, чтобы искать только данные Facebook, которые содержат слово "contoso" в свойстве Subject, используйте запрос по ключевому  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` слову.</span><span class="sxs-lookup"><span data-stu-id="e0a26-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="e0a26-461">Полный список значений, которые можно использовать для типов данных сторонних пользователей для этого свойства, см. в под этой теме, в этой теме вы можете найти сторонние данные, импортируемые в `itemclass` [Microsoft 365.](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="e0a26-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="e0a26-462">Дополнительные сведения об использовании средства "Поиск контента" и создании поисковых запросов по ключевым словам см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="e0a26-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="e0a26-463">Поиск контента</span><span class="sxs-lookup"><span data-stu-id="e0a26-463">Content Search</span></span>](content-search.md)
    
  - [<span data-ttu-id="e0a26-464">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="e0a26-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
