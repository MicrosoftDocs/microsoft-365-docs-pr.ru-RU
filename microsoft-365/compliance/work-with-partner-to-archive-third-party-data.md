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
ms.openlocfilehash: 97e36566c3dcc9b069a39eb50e203cda971ba3c2
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931951"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="3523c-103">Архивация сторонних данных при помощи партнера</span><span class="sxs-lookup"><span data-stu-id="3523c-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="3523c-104">Вы можете работать с партнером Майкрософт, чтобы импортировать и архивировать данные из стороннего источника данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="3523c-105">Партнер может предоставить настраиваемый соединитель, настроенный на извлечение элементов из стороннего источника данных (на регулярной основе), а затем импортировать эти элементы.</span><span class="sxs-lookup"><span data-stu-id="3523c-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="3523c-106">Соединитель партнера преобразует содержимое элемента из источника данных в формат сообщения электронной почты, а затем сохраняет элементы в почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="3523c-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="3523c-107">После импорта сторонних данных можно применить к этим данным функции соответствия требованиям Microsoft 365, такие как хранение для судебного разбирательства, обнаружение электронных данных, In-Place архивации, аудит и политики хранения Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>
 
>[!IMPORTANT]
><span data-ttu-id="3523c-108">Решение для [обеспечения соответствия требованиям](communication-compliance.md) в Microsoft 365 не может быть применено к сторонним данным, импортированным соединителями партнеров, указанным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3523c-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span> 
 
<span data-ttu-id="3523c-109">Ниже приведен обзор процесса и действий, необходимых для работы с партнером Майкрософт по импорту сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="3523c-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="3523c-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="3523c-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="3523c-111">Шаг 2: создание и Настройка почтового ящика с данными сторонних поставщиков</span><span class="sxs-lookup"><span data-stu-id="3523c-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="3523c-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="3523c-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="3523c-113">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="3523c-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="3523c-114">Шаг 5: Зарегистрируйте сторонний соединитель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3523c-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="3523c-115">Как происходит импорт сторонних данных</span><span class="sxs-lookup"><span data-stu-id="3523c-115">How the third-party data import process works</span></span>

<span data-ttu-id="3523c-116">На следующем рисунке и описание описывается работа стороннего процесса импорта данных при работе с партнером.</span><span class="sxs-lookup"><span data-stu-id="3523c-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Как происходит импорт сторонних данных](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="3523c-118">Клиент работает с партнером по выбору, чтобы настроить соединитель, который будет извлекать элементы из стороннего источника данных, а затем импортировать эти элементы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="3523c-119">Соединитель партнера подключается к сторонним источникам данных с помощью стороннего API (на основе запланированной или настроенной конфигурации) и извлекает элементы из источника данных.</span><span class="sxs-lookup"><span data-stu-id="3523c-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="3523c-120">Партнерский соединитель преобразует содержимое элемента в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3523c-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="3523c-121">В разделе [More Information](#more-information) представлено описание схемы формата сообщений.</span><span class="sxs-lookup"><span data-stu-id="3523c-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="3523c-122">Партнерский соединитель подключается к службе Azure в Microsoft 365 с помощью веб-службы Exchange (EWS) через хорошо известную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="3523c-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="3523c-p103">Элементы импортируются в почтовый ящик определенного пользователя или общий почтовый ящик для сторонних данных. Элемент импортируется в почтовый ящик определенного пользователя или общий почтовый ящик для сторонних данных, исходя из следующих критериев:</span><span class="sxs-lookup"><span data-stu-id="3523c-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="3523c-125">**Элементы с идентификатором пользователя, соответствующим учетной записи пользователя:** Если соединитель партнера может сопоставить идентификатор пользователя элемента в источнике данных стороннего производителя с определенным ИДЕНТИФИКАТОРом пользователя в Office 365, элемент будет скопирован в папку " **очистки** " в папке "элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="3523c-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="3523c-126">У пользователей нет доступа к элементам в папке "Очистка".</span><span class="sxs-lookup"><span data-stu-id="3523c-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="3523c-127">Тем не менее, можно использовать средства обнаружения электронных данных для поиска элементов в папке "очистки".</span><span class="sxs-lookup"><span data-stu-id="3523c-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="3523c-128">**Элементы, у которых нет идентификатора пользователя, соответствующего учетной записи пользователя:** Если соединителю партнера не удается сопоставить идентификатор пользователя с определенным ИДЕНТИФИКАТОРом пользователя, он копируется в папку **"Входящие"** в почтовом ящике данных стороннего производителя.</span><span class="sxs-lookup"><span data-stu-id="3523c-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="3523c-129">При импорте элементов в папку "Входящие" вы или другой пользователь в Организации можете войти в почтовый ящик стороннего производителя для просмотра этих элементов и управления ими, а также узнать, нужно ли вносить какие-либо изменения в конфигурацию соединителя партнера.</span><span class="sxs-lookup"><span data-stu-id="3523c-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="3523c-130">Шаг 1. Поиск партнера по работе со сторонними данными</span><span class="sxs-lookup"><span data-stu-id="3523c-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="3523c-131">Ключевой компонент для архивации сторонних данных в Microsoft 365 — Поиск и работа с партнером Майкрософт, который специализируется на сборе данных из стороннего источника данных и импортирует их в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="3523c-132">После импорта данные можно заархивировать и сохранить вместе с другими данными Майкрософт, такими как электронная почта от Exchange и документы из SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3523c-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="3523c-133">Партнер создает соединитель, который извлекает данные из сторонних источников данных Организации (таких как BlackBerry, Facebook, Google +, Thomson Reuters, Twitter и YouTube), и передает эти данные в API Office 365, который импортирует элементы в почтовые ящики Exchange как сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3523c-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="3523c-134">В следующих разделах перечислены партнеры Майкрософт (и сторонние источники данных, которые они поддерживаются), которые участвуют в программе для архивации сторонних данных в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="3523c-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="3523c-135">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="3523c-136">арчивесоЦиал</span><span class="sxs-lookup"><span data-stu-id="3523c-136">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="3523c-137">глобанет</span><span class="sxs-lookup"><span data-stu-id="3523c-137">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="3523c-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="3523c-138">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="3523c-139">смарш</span><span class="sxs-lookup"><span data-stu-id="3523c-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="3523c-140">Глагол</span><span class="sxs-lookup"><span data-stu-id="3523c-140">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="3523c-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="3523c-141">17a-4 LLC</span></span>

<span data-ttu-id="3523c-142">[17A – 4 LLC](https://www.17a-4.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="3523c-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="3523c-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="3523c-143">BlackBerry</span></span>
    
- <span data-ttu-id="3523c-144">потоки данных Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="3523c-144">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="3523c-145">Cisco Jabber;</span><span class="sxs-lookup"><span data-stu-id="3523c-145">Cisco Jabber</span></span>
    
- <span data-ttu-id="3523c-146">Факт</span><span class="sxs-lookup"><span data-stu-id="3523c-146">FactSet</span></span>
    
- <span data-ttu-id="3523c-147">хипчат</span><span class="sxs-lookup"><span data-stu-id="3523c-147">HipChat</span></span>
    
- <span data-ttu-id="3523c-148">инвестедже</span><span class="sxs-lookup"><span data-stu-id="3523c-148">InvestEdge</span></span>
    
- <span data-ttu-id="3523c-149">ливеперсон</span><span class="sxs-lookup"><span data-stu-id="3523c-149">LivePerson</span></span>
    
- <span data-ttu-id="3523c-150">MessageLabs Data Streams;</span><span class="sxs-lookup"><span data-stu-id="3523c-150">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="3523c-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="3523c-151">OpenText</span></span>
    
- <span data-ttu-id="3523c-152">Oracle/ATG Click-to-Call Live Help;</span><span class="sxs-lookup"><span data-stu-id="3523c-152">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="3523c-153">Pivot IMTRADER;</span><span class="sxs-lookup"><span data-stu-id="3523c-153">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="3523c-154">Microsoft SharePoint;</span><span class="sxs-lookup"><span data-stu-id="3523c-154">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="3523c-155">миндалигн</span><span class="sxs-lookup"><span data-stu-id="3523c-155">MindAlign</span></span>
    
- <span data-ttu-id="3523c-156">Sitrion One (Newsgator);</span><span class="sxs-lookup"><span data-stu-id="3523c-156">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="3523c-157">Skype для бизнеса (Lync/OCS);</span><span class="sxs-lookup"><span data-stu-id="3523c-157">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="3523c-158">Skype для бизнеса Online (Lync Online);</span><span class="sxs-lookup"><span data-stu-id="3523c-158">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="3523c-159">базы данных SQL;</span><span class="sxs-lookup"><span data-stu-id="3523c-159">SQL Databases</span></span>
    
- <span data-ttu-id="3523c-160">скуавкер</span><span class="sxs-lookup"><span data-stu-id="3523c-160">Squawker</span></span>
    
- <span data-ttu-id="3523c-161">Thomson Reuters Eikon Messenger.</span><span class="sxs-lookup"><span data-stu-id="3523c-161">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="3523c-162">арчивесоЦиал</span><span class="sxs-lookup"><span data-stu-id="3523c-162">ArchiveSocial</span></span>

<span data-ttu-id="3523c-163">[АрчивесоЦиал ](https://www.archivesocial.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="3523c-163">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3523c-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="3523c-164">Facebook</span></span>
    
- <span data-ttu-id="3523c-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="3523c-165">Flickr</span></span>
    
- <span data-ttu-id="3523c-166">инстаграм</span><span class="sxs-lookup"><span data-stu-id="3523c-166">Instagram</span></span>
    
- <span data-ttu-id="3523c-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="3523c-167">LinkedIn</span></span>
    
- <span data-ttu-id="3523c-168">пинтерест</span><span class="sxs-lookup"><span data-stu-id="3523c-168">Pinterest</span></span>
    
- <span data-ttu-id="3523c-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="3523c-169">Twitter</span></span>
    
- <span data-ttu-id="3523c-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="3523c-170">YouTube</span></span>
    
- <span data-ttu-id="3523c-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="3523c-171">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="3523c-172">глобанет</span><span class="sxs-lookup"><span data-stu-id="3523c-172">Globanet</span></span>

<span data-ttu-id="3523c-173">[Глобанет](https://www.globanet.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="3523c-173">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3523c-174">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="3523c-174">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="3523c-175">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="3523c-175">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3523c-176">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="3523c-176">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3523c-177">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="3523c-177">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3523c-178">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="3523c-178">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3523c-179">Bloomberg Chat;</span><span class="sxs-lookup"><span data-stu-id="3523c-179">Bloomberg Chat</span></span>
    
- <span data-ttu-id="3523c-180">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="3523c-180">Bloomberg Mail</span></span>
    
- <span data-ttu-id="3523c-181">Box</span><span class="sxs-lookup"><span data-stu-id="3523c-181">Box</span></span>
    
- <span data-ttu-id="3523c-182">CipherCloud для Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="3523c-182">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="3523c-183">Сервер для обмена мгновенными сообщениями Cisco &amp; (10, v 10.5.1 SU1, v SU2, v 11.5)</span><span class="sxs-lookup"><span data-stu-id="3523c-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="3523c-184">Cisco Вебекс Teams</span><span class="sxs-lookup"><span data-stu-id="3523c-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="3523c-185">ShareFile рабочей области Citrix &amp;</span><span class="sxs-lookup"><span data-stu-id="3523c-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="3523c-186">кровдкомпасс</span><span class="sxs-lookup"><span data-stu-id="3523c-186">CrowdCompass</span></span>

- <span data-ttu-id="3523c-187">Текстовые файлы с разделителями</span><span class="sxs-lookup"><span data-stu-id="3523c-187">Custom-delimited text files</span></span>
    
- <span data-ttu-id="3523c-188">настраиваемые XML-файлы;</span><span class="sxs-lookup"><span data-stu-id="3523c-188">Custom XML files</span></span>
    
- <span data-ttu-id="3523c-189">Facebook (страницы)</span><span class="sxs-lookup"><span data-stu-id="3523c-189">Facebook (Pages)</span></span>
    
- <span data-ttu-id="3523c-190">Факт</span><span class="sxs-lookup"><span data-stu-id="3523c-190">Factset</span></span>
    
- <span data-ttu-id="3523c-191">фксконнект</span><span class="sxs-lookup"><span data-stu-id="3523c-191">FXConnect</span></span>
    
- <span data-ttu-id="3523c-192">ICE Chat или YellowJacket;</span><span class="sxs-lookup"><span data-stu-id="3523c-192">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="3523c-193">Jive</span><span class="sxs-lookup"><span data-stu-id="3523c-193">Jive</span></span>
    
- <span data-ttu-id="3523c-194">Macgregor XIP;</span><span class="sxs-lookup"><span data-stu-id="3523c-194">Macgregor XIP</span></span>

- <span data-ttu-id="3523c-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3523c-195">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="3523c-196">Microsoft OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3523c-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="3523c-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3523c-197">Microsoft Teams</span></span>
       
- <span data-ttu-id="3523c-198">Microsoft Yammer;</span><span class="sxs-lookup"><span data-stu-id="3523c-198">Microsoft Yammer</span></span>
    
- <span data-ttu-id="3523c-199">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="3523c-199">Mobile Guard</span></span>
    
- <span data-ttu-id="3523c-200">Pivot</span><span class="sxs-lookup"><span data-stu-id="3523c-200">Pivot</span></span>
    
- <span data-ttu-id="3523c-201">Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="3523c-201">Salesforce Chatter</span></span>

- <span data-ttu-id="3523c-202">Skype для Бизнеса Онлайн</span><span class="sxs-lookup"><span data-stu-id="3523c-202">Skype for Business Online</span></span>
    
- <span data-ttu-id="3523c-203">Skype для бизнеса, версии от 2007 R2 до 2016 (локальные);</span><span class="sxs-lookup"><span data-stu-id="3523c-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="3523c-204">Slack Enterprise Grid;</span><span class="sxs-lookup"><span data-stu-id="3523c-204">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="3523c-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="3523c-205">Symphony</span></span>
    
- <span data-ttu-id="3523c-206">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="3523c-206">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="3523c-207">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="3523c-207">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="3523c-208">Thomson Reuters Dealings 3000 или FX Trading;</span><span class="sxs-lookup"><span data-stu-id="3523c-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="3523c-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="3523c-209">Twitter</span></span>
    
- <span data-ttu-id="3523c-210">UBS Chat;</span><span class="sxs-lookup"><span data-stu-id="3523c-210">UBS Chat</span></span>
    
- <span data-ttu-id="3523c-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="3523c-211">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="3523c-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="3523c-212">OpenText</span></span>

<span data-ttu-id="3523c-213">[Опентекст](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="3523c-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3523c-214">Axs Encrypted;</span><span class="sxs-lookup"><span data-stu-id="3523c-214">Axs Encrypted</span></span>
    
- <span data-ttu-id="3523c-215">Axs Exchange;</span><span class="sxs-lookup"><span data-stu-id="3523c-215">Axs Exchange</span></span>
    
- <span data-ttu-id="3523c-216">Axs Local Archive;</span><span class="sxs-lookup"><span data-stu-id="3523c-216">Axs Local Archive</span></span>
    
- <span data-ttu-id="3523c-217">Axs PlaceHolder;</span><span class="sxs-lookup"><span data-stu-id="3523c-217">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="3523c-218">Axs Signed;</span><span class="sxs-lookup"><span data-stu-id="3523c-218">Axs Signed</span></span>
    
- <span data-ttu-id="3523c-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="3523c-219">Bloomberg</span></span>
    
- <span data-ttu-id="3523c-220">Thomson Reuters.</span><span class="sxs-lookup"><span data-stu-id="3523c-220">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="3523c-221">смарш</span><span class="sxs-lookup"><span data-stu-id="3523c-221">Smarsh</span></span>

<span data-ttu-id="3523c-222">[Смарш](https://www.smarsh.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="3523c-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3523c-223">СТАРАЙТЕСЬ</span><span class="sxs-lookup"><span data-stu-id="3523c-223">AIM</span></span>
    
- <span data-ttu-id="3523c-224">American Idol;</span><span class="sxs-lookup"><span data-stu-id="3523c-224">American Idol</span></span>
    
- <span data-ttu-id="3523c-225">Apple Juice;</span><span class="sxs-lookup"><span data-stu-id="3523c-225">Apple Juice</span></span>
    
- <span data-ttu-id="3523c-226">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="3523c-226">AOL with Pivot client</span></span>
    
- <span data-ttu-id="3523c-227">арес</span><span class="sxs-lookup"><span data-stu-id="3523c-227">Ares</span></span>
    
- <span data-ttu-id="3523c-228">Bazaar Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-228">Bazaar Voice</span></span>
    
- <span data-ttu-id="3523c-229">Bear Share;</span><span class="sxs-lookup"><span data-stu-id="3523c-229">Bear Share</span></span>
    
- <span data-ttu-id="3523c-230">Bit Torrent;</span><span class="sxs-lookup"><span data-stu-id="3523c-230">Bit Torrent</span></span>
    
- <span data-ttu-id="3523c-231">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="3523c-231">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3523c-232">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="3523c-232">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3523c-233">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="3523c-233">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3523c-234">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="3523c-234">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3523c-235">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="3523c-235">Bloomberg Mail</span></span>
    
- <span data-ttu-id="3523c-236">целлтруст</span><span class="sxs-lookup"><span data-stu-id="3523c-236">CellTrust</span></span>
    
- <span data-ttu-id="3523c-237">импорт чата;</span><span class="sxs-lookup"><span data-stu-id="3523c-237">Chat Import</span></span>
    
- <span data-ttu-id="3523c-238">политика и ведение журнала чата в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="3523c-238">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="3523c-239">Chatter;</span><span class="sxs-lookup"><span data-stu-id="3523c-239">Chatter</span></span>
    
- <span data-ttu-id="3523c-240">Сервер Cisco IM &amp; Presence Server (v 9.0.1, v 9.1, v 9.1.1 SU1, 10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="3523c-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="3523c-241">Cisco Unified Presence Server (версии 8.6.3, 8.6.4, 8.6.5);</span><span class="sxs-lookup"><span data-stu-id="3523c-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="3523c-242">импорт совместной работы;</span><span class="sxs-lookup"><span data-stu-id="3523c-242">Collaboration Import</span></span>
    
- <span data-ttu-id="3523c-243">ведение журнала совместной работы в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="3523c-243">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="3523c-244">Direct Connect;</span><span class="sxs-lookup"><span data-stu-id="3523c-244">Direct Connect</span></span>
    
- <span data-ttu-id="3523c-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="3523c-245">Facebook</span></span>
    
- <span data-ttu-id="3523c-246">Факт</span><span class="sxs-lookup"><span data-stu-id="3523c-246">FactSet</span></span>
    
- <span data-ttu-id="3523c-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="3523c-247">FastTrack</span></span>
    
- <span data-ttu-id="3523c-248">гнутелла</span><span class="sxs-lookup"><span data-stu-id="3523c-248">Gnutella</span></span>
    
- <span data-ttu-id="3523c-249">Google +</span><span class="sxs-lookup"><span data-stu-id="3523c-249">Google+</span></span>
    
- <span data-ttu-id="3523c-250">готомипк</span><span class="sxs-lookup"><span data-stu-id="3523c-250">GoToMyPC</span></span>
    
- <span data-ttu-id="3523c-251">хопстер</span><span class="sxs-lookup"><span data-stu-id="3523c-251">Hopster</span></span>
    
- <span data-ttu-id="3523c-252">хубконнекс</span><span class="sxs-lookup"><span data-stu-id="3523c-252">HubConnex</span></span>
    
- <span data-ttu-id="3523c-253">IBM Connections (версии 3.0.1, 4.0, 4.5, 4.5 CR3, 5);</span><span class="sxs-lookup"><span data-stu-id="3523c-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="3523c-254">IBM Connections Chat Cloud;</span><span class="sxs-lookup"><span data-stu-id="3523c-254">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="3523c-255">IBM Connections Social Cloud;</span><span class="sxs-lookup"><span data-stu-id="3523c-255">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="3523c-256">IBM SameTime Advanced 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="3523c-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="3523c-257">IBM SameTime Communicate 9.0;</span><span class="sxs-lookup"><span data-stu-id="3523c-257">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="3523c-258">IBM SameTime Community (версии 8.0.2, 8.5.1 IFR2, 8.5.2 IFR1, 9.1);</span><span class="sxs-lookup"><span data-stu-id="3523c-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="3523c-259">IBM SameTime Complete 9.0;</span><span class="sxs-lookup"><span data-stu-id="3523c-259">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="3523c-260">IBM SameTime Conference 9.0;</span><span class="sxs-lookup"><span data-stu-id="3523c-260">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="3523c-261">IBM SameTime Meeting 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="3523c-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="3523c-262">ICE/Елловжаккет</span><span class="sxs-lookup"><span data-stu-id="3523c-262">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="3523c-263">импорт мгновенных сообщений;</span><span class="sxs-lookup"><span data-stu-id="3523c-263">IM Import</span></span>
    
- <span data-ttu-id="3523c-264">политика и ведение журнала обмена мгновенными сообщениями в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="3523c-264">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="3523c-265">Indii Messenger;</span><span class="sxs-lookup"><span data-stu-id="3523c-265">Indii Messenger</span></span>
    
- <span data-ttu-id="3523c-266">Instant Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="3523c-266">Instant Bloomberg</span></span>
    
- <span data-ttu-id="3523c-267">IRC</span><span class="sxs-lookup"><span data-stu-id="3523c-267">IRC</span></span>
    
- <span data-ttu-id="3523c-268">Jive</span><span class="sxs-lookup"><span data-stu-id="3523c-268">Jive</span></span>
    
- <span data-ttu-id="3523c-269">Jive 6 Real Time Logging (версии 6, 7);</span><span class="sxs-lookup"><span data-stu-id="3523c-269">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="3523c-270">импорт Jive;</span><span class="sxs-lookup"><span data-stu-id="3523c-270">Jive Import</span></span>
    
- <span data-ttu-id="3523c-271">жкста</span><span class="sxs-lookup"><span data-stu-id="3523c-271">JXTA</span></span>
    
- <span data-ttu-id="3523c-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="3523c-272">LinkedIn</span></span>
    
- <span data-ttu-id="3523c-273">Microsoft Lync (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="3523c-273">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="3523c-274">мфтп</span><span class="sxs-lookup"><span data-stu-id="3523c-274">MFTP</span></span>
    
- <span data-ttu-id="3523c-275">Microsoft Lync 2013 Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-275">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="3523c-276">Microsoft SharePoint (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="3523c-276">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="3523c-277">Microsoft SharePoint Online;</span><span class="sxs-lookup"><span data-stu-id="3523c-277">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="3523c-278">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="3523c-278">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="3523c-279">миндалигн</span><span class="sxs-lookup"><span data-stu-id="3523c-279">MindAlign</span></span>
    
- <span data-ttu-id="3523c-280">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="3523c-280">Mobile Guard</span></span>
    
- <span data-ttu-id="3523c-281">СЕТЬЮ</span><span class="sxs-lookup"><span data-stu-id="3523c-281">MSN</span></span>
    
- <span data-ttu-id="3523c-282">My Space;</span><span class="sxs-lookup"><span data-stu-id="3523c-282">My Space</span></span>
    
- <span data-ttu-id="3523c-283">неонетворк</span><span class="sxs-lookup"><span data-stu-id="3523c-283">NEONetwork</span></span>
    
- <span data-ttu-id="3523c-284">Office 365 Lync Dedicated;</span><span class="sxs-lookup"><span data-stu-id="3523c-284">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="3523c-285">групповой чат Office 365;</span><span class="sxs-lookup"><span data-stu-id="3523c-285">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="3523c-286">пинтерест</span><span class="sxs-lookup"><span data-stu-id="3523c-286">Pinterest</span></span>
    
- <span data-ttu-id="3523c-287">Pivot</span><span class="sxs-lookup"><span data-stu-id="3523c-287">Pivot</span></span>
    
- <span data-ttu-id="3523c-288">QQ</span><span class="sxs-lookup"><span data-stu-id="3523c-288">QQ</span></span>
    
- <span data-ttu-id="3523c-289">Skype для бизнеса 2015;</span><span class="sxs-lookup"><span data-stu-id="3523c-289">Skype for Business 2015</span></span>
    
- <span data-ttu-id="3523c-290">софтесер</span><span class="sxs-lookup"><span data-stu-id="3523c-290">SoftEther</span></span>
    
- <span data-ttu-id="3523c-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="3523c-291">Symphony</span></span>
    
- <span data-ttu-id="3523c-292">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="3523c-292">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="3523c-293">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="3523c-293">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="3523c-294">тор</span><span class="sxs-lookup"><span data-stu-id="3523c-294">Tor</span></span>
    
- <span data-ttu-id="3523c-295">ттт</span><span class="sxs-lookup"><span data-stu-id="3523c-295">TTT</span></span>
    
- <span data-ttu-id="3523c-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="3523c-296">Twitter</span></span>
    
- <span data-ttu-id="3523c-297">винмкс</span><span class="sxs-lookup"><span data-stu-id="3523c-297">WinMX</span></span>
    
- <span data-ttu-id="3523c-298">винни</span><span class="sxs-lookup"><span data-stu-id="3523c-298">Winny</span></span>
    
- <span data-ttu-id="3523c-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="3523c-299">Yahoo</span></span>
    
- <span data-ttu-id="3523c-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="3523c-300">Yammer</span></span>
    
- <span data-ttu-id="3523c-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="3523c-301">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="3523c-302">Глагол</span><span class="sxs-lookup"><span data-stu-id="3523c-302">Verba</span></span>

<span data-ttu-id="3523c-303">[Verb](https://www.verba.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="3523c-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3523c-304">Avaya Aura Video;</span><span class="sxs-lookup"><span data-stu-id="3523c-304">Avaya Aura Video</span></span>
    
- <span data-ttu-id="3523c-305">Avaya Aura Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-305">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="3523c-306">Avtec Radio;</span><span class="sxs-lookup"><span data-stu-id="3523c-306">Avtec Radio</span></span>
    
- <span data-ttu-id="3523c-307">Bosch/Telex Radio;</span><span class="sxs-lookup"><span data-stu-id="3523c-307">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="3523c-308">BroadSoft Video;</span><span class="sxs-lookup"><span data-stu-id="3523c-308">BroadSoft Video</span></span>
    
- <span data-ttu-id="3523c-309">BroadSoft Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-309">BroadSoft Voice</span></span>
    
- <span data-ttu-id="3523c-310">Centile Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-310">Centile Voice</span></span>
    
- <span data-ttu-id="3523c-311">Cisco Jabber IM;</span><span class="sxs-lookup"><span data-stu-id="3523c-311">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="3523c-312">Cisco UC Video;</span><span class="sxs-lookup"><span data-stu-id="3523c-312">Cisco UC Video</span></span>
    
- <span data-ttu-id="3523c-313">Cisco UC Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-313">Cisco UC Voice</span></span>
    
- <span data-ttu-id="3523c-314">Cisco UCCX/UCCE Video</span><span class="sxs-lookup"><span data-stu-id="3523c-314">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="3523c-315">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="3523c-315">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="3523c-316">ESChat Radio;</span><span class="sxs-lookup"><span data-stu-id="3523c-316">ESChat Radio</span></span>
    
- <span data-ttu-id="3523c-317">Geoman Contact Expert;</span><span class="sxs-lookup"><span data-stu-id="3523c-317">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="3523c-318">IP Trade Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-318">IP Trade Voice</span></span>
    
- <span data-ttu-id="3523c-319">Luware LUCS Contact Center;</span><span class="sxs-lookup"><span data-stu-id="3523c-319">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="3523c-320">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="3523c-320">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="3523c-321">Mitel MiContact Center для Lync (prairieFyre);</span><span class="sxs-lookup"><span data-stu-id="3523c-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="3523c-322">Oracle / Acme Packet Session Border Controller Video;</span><span class="sxs-lookup"><span data-stu-id="3523c-322">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="3523c-323">Oracle / Acme Packet Session Border Controller Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-323">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="3523c-324">Singtel Mobile Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-324">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="3523c-325">SIPREC Video;</span><span class="sxs-lookup"><span data-stu-id="3523c-325">SIPREC Video</span></span>
    
-  <span data-ttu-id="3523c-326">SIPREC Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-326">SIPREC Voice</span></span> 
    
- <span data-ttu-id="3523c-327">Skype для бизнеса / Lync IM;</span><span class="sxs-lookup"><span data-stu-id="3523c-327">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="3523c-328">Skype для бизнеса / Lync Video;</span><span class="sxs-lookup"><span data-stu-id="3523c-328">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="3523c-329">Skype для бизнеса / Lync Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-329">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="3523c-330">Speakerbus Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-330">Speakerbus Voice</span></span>
    
- <span data-ttu-id="3523c-331">Standard SIP/H.323 Video;</span><span class="sxs-lookup"><span data-stu-id="3523c-331">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="3523c-332">Standard SIP/H.323 Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-332">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="3523c-333">Truphone Voice;</span><span class="sxs-lookup"><span data-stu-id="3523c-333">Truphone Voice</span></span>
    
- <span data-ttu-id="3523c-334">TwistedPair Radio;</span><span class="sxs-lookup"><span data-stu-id="3523c-334">TwistedPair Radio</span></span>
    
- <span data-ttu-id="3523c-335">рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="3523c-335">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="3523c-336">Шаг 2. Создание и настройка почтового ящика сторонних данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="3523c-336">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="3523c-337">Ниже приведены действия по созданию и настройке почтового ящика данных стороннего производителя для импорта данных в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="3523c-338">Как было сказано выше, элементы импортируются в этот почтовый ящик, если соединитель партнера не может сопоставить идентификатор пользователя элемента с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="3523c-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>
  
 <span data-ttu-id="3523c-339">**Выполните эти действия в центре администрирования Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="3523c-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="3523c-340">Создайте учетную запись пользователя и назначьте ей лицензию на Exchange Online (план 2). Ознакомьтесь [со статьей Добавление пользователей в Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="3523c-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="3523c-341">Лицензия на план 2 необходима, чтобы поместить почтовый ящик на хранение для судебного разбирательства или включить архивный почтовый ящик с неограниченной квотой.</span><span class="sxs-lookup"><span data-stu-id="3523c-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="3523c-342">Добавьте учетную запись пользователя для почтового ящика данных стороннего производителя в роль администратора **администратора Exchange** в Office 365; [в разделе Назначение ролей администратора в Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="3523c-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3523c-343">Запишите данные этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3523c-343">Write down the credentials for this user account.</span></span> <span data-ttu-id="3523c-344">Их необходимо предоставить партнеру, как описано в шаге 4.</span><span class="sxs-lookup"><span data-stu-id="3523c-344">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="3523c-345">**Выполнение этих задач в центре администрирования Exchange**</span><span class="sxs-lookup"><span data-stu-id="3523c-345">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="3523c-346">Скрытие почтового ящика сторонних данных из адресной книги и других списков адресов в Организации; в разделе [Управление почтовыми ящиками пользователей](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="3523c-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="3523c-347">Можно также выполнить следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3523c-347">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="3523c-348">Назначьте разрешение **FullAccess** для почтового ящика данных стороннего производителя, чтобы администраторы или руководители соответствия могли открыть сторонний почтовый ящик данных в клиенте Outlook для настольных ПК. Ознакомьтесь с [разрешениями Управление разрешениями для получателей](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="3523c-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="3523c-349">Включите следующие функции, связанные с соответствием требованиям, для почтового ящика данных стороннего производителя:</span><span class="sxs-lookup"><span data-stu-id="3523c-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="3523c-350">Включение архивного почтового ящика; Разрешите [архивирование почтовых ящиков](enable-archive-mailboxes.md) и [включите неограниченное архивирование](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="3523c-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="3523c-351">Это позволяет освободить дисковое пространство в основном почтовом ящике, настроив политику архивации, которая перемещает сторонние элементы данных в архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3523c-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="3523c-352">Это обеспечивает неограниченное хранение данных сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="3523c-352">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="3523c-353">Поместите почтовый ящик сторонних данных на хранение для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="3523c-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="3523c-354">Вы также можете применить политику хранения Microsoft 365 в центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3523c-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="3523c-355">При помещении этого почтового ящика в удержание сохраняются сторонние элементы данных (неопределенное время или продолжительность действия), и их не следует очищать из почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3523c-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="3523c-356">Просмотрите один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="3523c-356">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="3523c-357">Применение к почтовому ящику функции судебного удержания</span><span class="sxs-lookup"><span data-stu-id="3523c-357">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="3523c-358">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="3523c-358">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="3523c-359">Включение ведения журнала аудита почтовых ящиков для владельца, представителя и административного доступа к почтовому ящику данных стороннего производителя; в разделе [включить аудит почтовых ящиков](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="3523c-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="3523c-360">Это позволяет выполнять аудит всех действий, выполняемых любым пользователем, имеющим доступ к почтовому ящику данных стороннего производителя.</span><span class="sxs-lookup"><span data-stu-id="3523c-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="3523c-361">Шаг 3. Настройка поддержки сторонних данных для почтовых ящиков пользователей</span><span class="sxs-lookup"><span data-stu-id="3523c-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="3523c-362">Следующим шагом является настройка поддержки сторонних данных для почтовых ящиков пользователей.</span><span class="sxs-lookup"><span data-stu-id="3523c-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="3523c-363">Выполните указанные ниже действия с помощью центра администрирования Exchange или соответствующих командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3523c-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="3523c-364">Включите архивный почтовый ящик для каждого пользователя; Разрешите [архивирование почтовых ящиков](enable-archive-mailboxes.md) и [включите неограниченное архивирование](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="3523c-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="3523c-365">Помещайте почтовые ящики пользователей на хранение для судебного разбирательства или примените политику хранения Microsoft 365; Просмотрите один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="3523c-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="3523c-366">Применение к почтовому ящику функции судебного удержания</span><span class="sxs-lookup"><span data-stu-id="3523c-366">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="3523c-367">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="3523c-367">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="3523c-368">Как отмечалось ранее, при помещении почтовых ящиков на хранение можно указать длительность хранения элементов из источника сторонних данных или выбрать бессрочное хранение.</span><span class="sxs-lookup"><span data-stu-id="3523c-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="3523c-369">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="3523c-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="3523c-370">Последним этапом является предоставление партнеру следующих сведений, чтобы можно было настроить соединитель для подключения к Организации, чтобы импортировать данные в почтовые ящики пользователей и в почтовые ящики сторонних поставщиков данных.</span><span class="sxs-lookup"><span data-stu-id="3523c-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="3523c-371">Конечная точка, используемая для подключения к службе Azure в Office 365:</span><span class="sxs-lookup"><span data-stu-id="3523c-371">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="3523c-372">Учетные данные для входа (идентификатор пользователя и пароль Microsoft 365) для почтового ящика данных стороннего производителя, созданного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="3523c-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="3523c-373">Эти учетные данные требуются соединителю партнера для доступа к элементам и их импорта в почтовые ящики пользователей и почтовый ящик со сторонними данными.</span><span class="sxs-lookup"><span data-stu-id="3523c-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="3523c-374">Шаг 5: Зарегистрируйте сторонний соединитель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3523c-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="3523c-375">Начиная с 30 сентября 2018, служба Azure в Office 365 начнет использовать современные проверки подлинности в Exchange Online для проверки подлинности сторонних соединителей данных, пытающихся подключиться к Организации для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="3523c-375">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="3523c-376">Причина этого изменения заключается в том, что современная проверка подлинности обеспечивает большую безопасность, чем текущий метод, основанный на списке разрешений для сторонних соединителей, использующих ранее описанную конечную точку для подключения к службе Azure.</span><span class="sxs-lookup"><span data-stu-id="3523c-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="3523c-377">Чтобы включить сторонний соединитель данных для подключения к Office 365 с помощью нового метода проверки подлинности, администратору организации необходимо согласиться зарегистрировать соединитель как доверенное приложение службы в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3523c-377">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="3523c-378">Для этого необходимо принять запрос на разрешение соединителей на доступ к данным Организации в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3523c-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="3523c-379">После принятия этого запроса сторонний соединитель данных добавляется в качестве корпоративного приложения в Azure Active Directory и представляется в качестве субъекта-службы.</span><span class="sxs-lookup"><span data-stu-id="3523c-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="3523c-380">Более подробную информацию можно найти в разделе  [согласие администратора клиента](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="3523c-380">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="3523c-381">Ниже описаны действия, которые необходимо выполнить, чтобы получить доступ и принять запрос на регистрацию соединителя:</span><span class="sxs-lookup"><span data-stu-id="3523c-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="3523c-382">Перейдите на [эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) и войдите в систему, используя учетные данные глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="3523c-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="3523c-383">Отображается следующее диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="3523c-383">The following dialog box is displayed.</span></span> <span data-ttu-id="3523c-384">Вы можете развернуть символы крышки, чтобы просмотреть разрешения, которые будут назначены соединителю.</span><span class="sxs-lookup"><span data-stu-id="3523c-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Отображается диалоговое окно запроса разрешений](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="3523c-386">Нажмите кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="3523c-386">Click **Accept**.</span></span>

<span data-ttu-id="3523c-387">После принятия запроса отображается [портал Azure](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="3523c-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="3523c-388">Чтобы просмотреть список приложений для вашей организации, щелкните элемент **Azure Active Directory**  >  **Enterprise Applications**.</span><span class="sxs-lookup"><span data-stu-id="3523c-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="3523c-389">Сторонний соединитель данных Office 365 указан в колонке **корпоративные приложения** .</span><span class="sxs-lookup"><span data-stu-id="3523c-389">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3523c-390">После 30 сентября 2018 данные сторонних поставщиков больше не будут импортироваться в почтовые ящики в вашей организации, если вы не зарегистрируете сторонний соединитель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3523c-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="3523c-391">Обратите внимание, что существующие сторонние соединители данных (созданные до 30 сентября 2018) также должны быть зарегистрированы в Azure Active Directory, выполнив действия, описанные в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="3523c-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="3523c-392">Отзыв согласия с сторонним соединителем данных</span><span class="sxs-lookup"><span data-stu-id="3523c-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="3523c-393">После того как ваша организация отправила запрос на разрешения на регистрацию стороннего соединителя данных в Azure Active Directory, ваша организация может в любой момент отозвать это согласие.</span><span class="sxs-lookup"><span data-stu-id="3523c-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="3523c-394">Однако отзыв согласия для соединителя означает, что данные из стороннего источника данных больше не будут импортироваться в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="3523c-395">Чтобы отозвать согласие для стороннего соединителя данных, можно удалить приложение (удалив соответствующий субъект-службу) из Azure Active Directory с помощью колонки " **корпоративные приложения** " на портале Azure или с помощью командлета [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) в Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3523c-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="3523c-396">Вы также можете использовать командлет [Remove – азуреадсервицепринЦипал](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) в Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3523c-396">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="3523c-397">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3523c-397">More information</span></span>

- <span data-ttu-id="3523c-398">Как объяснялось ранее, элементы из сторонних источников данных импортируются в почтовые ящики Exchange в виде сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3523c-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="3523c-399">Соединитель партнера импортирует элемент, используя схему, требуемую API Office 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-399">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="3523c-400">В приведенной ниже таблице описываются свойства элемента из стороннего источника данных после его импорта в почтовый ящик Exchange в виде сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3523c-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="3523c-401">В этой таблице также указывается, является ли свойство сообщения обязательным.</span><span class="sxs-lookup"><span data-stu-id="3523c-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="3523c-402">Обязательные свойства должны быть заполнены.</span><span class="sxs-lookup"><span data-stu-id="3523c-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="3523c-403">Если для элемента отсутствует обязательное свойство, оно не будет импортировано в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-403">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="3523c-404">Процесс импорта возвращает сообщение об ошибке, объясняющее, почему элемент не был импортирован и какое свойство отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3523c-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="3523c-405">**Свойство сообщения**</span><span class="sxs-lookup"><span data-stu-id="3523c-405">**Message property**</span></span>|<span data-ttu-id="3523c-406">**Обязательный?**</span><span class="sxs-lookup"><span data-stu-id="3523c-406">**Mandatory?**</span></span>|<span data-ttu-id="3523c-407">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3523c-407">**Description**</span></span>|<span data-ttu-id="3523c-408">**Пример значения**</span><span class="sxs-lookup"><span data-stu-id="3523c-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3523c-409">**FROM**</span><span class="sxs-lookup"><span data-stu-id="3523c-409">**FROM**</span></span> <br/> |<span data-ttu-id="3523c-410">Да</span><span class="sxs-lookup"><span data-stu-id="3523c-410">Yes</span></span>  <br/> |<span data-ttu-id="3523c-411">Пользователь, который создал или отправил элемент из стороннего источника данных.</span><span class="sxs-lookup"><span data-stu-id="3523c-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="3523c-412">Соединитель партнера пытается сопоставить идентификатор пользователя с исходным элементом (например, с маркером Twitter) с учетной записью пользователя для всех участников (в полях "от" и "Кому").</span><span class="sxs-lookup"><span data-stu-id="3523c-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="3523c-413">Копия сообщения будет импортирована в почтовый ящик каждого участника.</span><span class="sxs-lookup"><span data-stu-id="3523c-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="3523c-414">Если ни один из участников этого элемента не может быть сопоставлен с учетной записью пользователя, он будет импортирован в почтовый ящик стороннего производителя для архивации в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3523c-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="3523c-415">Участник, идентифицированный как отправитель элемента, должен иметь активный почтовый ящик в Организации, в которую импортируется элемент.</span><span class="sxs-lookup"><span data-stu-id="3523c-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="3523c-416">Если у отправителя нет активного почтового ящика, возвращается следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="3523c-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="3523c-417">**TO**</span><span class="sxs-lookup"><span data-stu-id="3523c-417">**TO**</span></span> <br/> |<span data-ttu-id="3523c-418">Да</span><span class="sxs-lookup"><span data-stu-id="3523c-418">Yes</span></span>  <br/> |<span data-ttu-id="3523c-419">Пользователь, получивший элемент, если это применимо к элементу в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="3523c-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="3523c-420">**Тема**</span><span class="sxs-lookup"><span data-stu-id="3523c-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="3523c-421">Нет</span><span class="sxs-lookup"><span data-stu-id="3523c-421">No</span></span>  <br/> |<span data-ttu-id="3523c-422">Тема исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="3523c-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="3523c-423">**БУДУЩ**</span><span class="sxs-lookup"><span data-stu-id="3523c-423">**DATE**</span></span> <br/> |<span data-ttu-id="3523c-424">Да</span><span class="sxs-lookup"><span data-stu-id="3523c-424">Yes</span></span>  <br/> |<span data-ttu-id="3523c-425">Дата первоначального создания или публикации элемента в источнике данных клиента.</span><span class="sxs-lookup"><span data-stu-id="3523c-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="3523c-426">Например, это дата, когда сообщение Twitter было твитом.</span><span class="sxs-lookup"><span data-stu-id="3523c-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="3523c-427">**ТЕКСТ**</span><span class="sxs-lookup"><span data-stu-id="3523c-427">**BODY**</span></span> <br/> |<span data-ttu-id="3523c-428">Нет</span><span class="sxs-lookup"><span data-stu-id="3523c-428">No</span></span>  <br/> |<span data-ttu-id="3523c-429">Содержимое сообщения или публикации.</span><span class="sxs-lookup"><span data-stu-id="3523c-429">The contents of the message or post.</span></span> <span data-ttu-id="3523c-430">Для некоторых источников данных содержимое этого свойства может совпадать с содержимым свойства **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="3523c-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="3523c-431">Во время процесса импорта соединитель партнера предпринимает попытку сохранить полную точность источника контента, как это возможно.</span><span class="sxs-lookup"><span data-stu-id="3523c-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="3523c-432">По возможности в это свойство включаются файлы, рисунки или другое содержимое исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="3523c-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="3523c-433">В противном случае содержимое исходного элемента включается в свойство **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="3523c-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="3523c-434">Содержимое этого свойства зависит от соединителя партнера и от возможности исходной платформы.</span><span class="sxs-lookup"><span data-stu-id="3523c-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="3523c-435">**Крепление**</span><span class="sxs-lookup"><span data-stu-id="3523c-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="3523c-436">Нет</span><span class="sxs-lookup"><span data-stu-id="3523c-436">No</span></span>  <br/> |<span data-ttu-id="3523c-437">Если элемент в источнике данных (например, твит в Twitter или беседе обмена мгновенными сообщениями) имеет вложенный файл или включает изображения, то партнер по подключению будет сначала пытаться включить вложения в свойство **Body** .</span><span class="sxs-lookup"><span data-stu-id="3523c-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="3523c-438">Если это невозможно, то оно добавляется в свойство \* \* вложение \* \*.</span><span class="sxs-lookup"><span data-stu-id="3523c-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="3523c-439">К другим примерам вложений относятся отметки "Нравится" в Facebook, метаданные из источника контента, а также ответы на сообщение или публикацию.</span><span class="sxs-lookup"><span data-stu-id="3523c-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="3523c-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="3523c-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="3523c-441">Да</span><span class="sxs-lookup"><span data-stu-id="3523c-441">Yes</span></span>  <br/> | <span data-ttu-id="3523c-442">Это свойство с несколькими значениями, которое создается и заполняется соединителем партнера.</span><span class="sxs-lookup"><span data-stu-id="3523c-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="3523c-443">Это свойство имеет следующий формат  `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="3523c-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="3523c-444">(Это свойство должно начинаться с  `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="3523c-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="3523c-445">Этот формат похож на один для  `IPM.NOTE.X` класса Message.) Это свойство содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3523c-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="3523c-446">`Source`: Указывает источник данных стороннего производителя; Например, Twitter, Facebook или BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="3523c-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="3523c-447">`Event`: Указывает тип действия, которое выполнялось в источнике данных стороннего производителя, который создал элементы; Например, твит в Twitter или в учетной записи Facebook.</span><span class="sxs-lookup"><span data-stu-id="3523c-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="3523c-448">Каждому источнику данных характерны свои события.</span><span class="sxs-lookup"><span data-stu-id="3523c-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="3523c-449">Одна из целей этого свойства — фильтрация элементов на основе типа события или источника данных, в котором создан элемент.</span><span class="sxs-lookup"><span data-stu-id="3523c-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="3523c-450">Например, при поиске с помощью функции обнаружения электронных данных можно найти все твиты, опубликованные определенным пользователем.</span><span class="sxs-lookup"><span data-stu-id="3523c-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="3523c-451">При успешном импорте элементов в почтовые ящики в Office 365, в качестве части HTTP-ответа возвращается уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="3523c-451">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="3523c-452">Этот идентификатор, называемый  `x-IngestionCorrelationID` , может использоваться для последующих задач по устранению неполадок, которые являются участниками для сквозного отслеживания элементов.</span><span class="sxs-lookup"><span data-stu-id="3523c-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="3523c-453">Партнерам рекомендуется фиксировать эту информацию и записывать ее в журнал соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="3523c-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="3523c-454">Пример HTTP-отклика, содержащего этот идентификатор:</span><span class="sxs-lookup"><span data-stu-id="3523c-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="3523c-455">С помощью средства "поиск контента" в центре безопасности и соответствия требованиям можно искать элементы, импортированные в почтовые ящики из стороннего источника данных.</span><span class="sxs-lookup"><span data-stu-id="3523c-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="3523c-456">Чтобы выполнить поиск в этих импортированных элементах, можно использовать следующие пары "свойство: значение сообщения" в поле ключевое слово для поиска контента.</span><span class="sxs-lookup"><span data-stu-id="3523c-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="3523c-457">**`kind:externaldata`** : Используйте эту комбинацию свойства и значения для поиска всех сторонних типов данных.</span><span class="sxs-lookup"><span data-stu-id="3523c-457">**`kind:externaldata`** : Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="3523c-458">Например, чтобы найти элементы, импортированные из стороннего источника данных и содержали слово "contoso" в свойстве subject импортированного элемента, используйте запрос ключевого слова  `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="3523c-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="3523c-459">**`itemclass:ipm.externaldata.<third-party data type>`** : Используйте эту комбинацию свойства и значения, чтобы выполнять поиск только по указанному типу сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="3523c-459">**`itemclass:ipm.externaldata.<third-party data type>`** : Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="3523c-460">Например, чтобы искать только данные Facebook, содержащие слово "contoso" в свойстве subject, следует использовать запрос ключевого слова  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="3523c-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="3523c-461">Полный список значений, которые необходимо использовать для сторонних типов данных для  `itemclass` свойства, приведен [в разделе Использование поиска контента для поиска сторонних данных, импортированных в Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span><span class="sxs-lookup"><span data-stu-id="3523c-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="3523c-462">Дополнительные сведения об использовании средства "Поиск контента" и создании поисковых запросов по ключевым словам см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="3523c-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="3523c-463">Поиск контента в Office 365</span><span class="sxs-lookup"><span data-stu-id="3523c-463">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="3523c-464">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="3523c-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
