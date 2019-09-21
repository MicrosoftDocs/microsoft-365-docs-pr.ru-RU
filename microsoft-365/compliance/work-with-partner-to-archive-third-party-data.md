---
title: Работа с партнером для архивации сторонних данных в Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Организация может работать с партнером корпорации Майкрософт, чтобы настроить настраиваемый соединитель для импорта сторонних данных из источников данных, таких как Salesforce chatter;, Yahoo Messenger или Yammer. Это позволяет архивировать данные из сторонних источников данных в Office 365, чтобы можно было использовать функции соответствия требованиям Office 365, такие как юридические удержания, поиск контента и политики хранения, для управления данными сторонних организаций.
ms.openlocfilehash: a22b4226efb582969072bbd92149080cca9b749c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090836"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a><span data-ttu-id="fff99-104">Работа с партнером для архивации сторонних данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="fff99-104">Work with a partner to archive third-party data in Office 365</span></span>

<span data-ttu-id="fff99-105">Вы можете работать с партнером Майкрософт, чтобы импортировать и архивировать данные из стороннего источника данных в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-105">You can work with a Microsoft Partner to import and archive data from a third-party data source to Office 365.</span></span> <span data-ttu-id="fff99-106">Партнер может предоставить настраиваемый соединитель, настроенный на извлечение элементов из стороннего источника данных (на регулярной основе), а затем импортировать эти элементы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-106">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items to Office 365.</span></span> <span data-ttu-id="fff99-107">Соединитель партнера преобразует содержимое элемента из источника данных в формат сообщения электронной почты, а затем сохраняет элементы в почтовых ящиках в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-107">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes in Office 365.</span></span> <span data-ttu-id="fff99-108">После импорта сторонних данных можно применить к этим данным функции соответствия требованиям Office 365, такие как хранение для судебного разбирательства, поиск контента, Архивация на месте, аудит и политики хранения Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-108">After third-party data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies to this data.</span></span>
  
<span data-ttu-id="fff99-109">Ниже приведен обзор процесса и действий, необходимых для работы с партнером Майкрософт по импорту сторонних данных в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data to Office 365.</span></span>

[<span data-ttu-id="fff99-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="fff99-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="fff99-111">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="fff99-111">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="fff99-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="fff99-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="fff99-113">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="fff99-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="fff99-114">Шаг 5: Зарегистрируйте сторонний соединитель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fff99-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="fff99-115">Как происходит импорт сторонних данных</span><span class="sxs-lookup"><span data-stu-id="fff99-115">How the third-party data import process works</span></span>

<span data-ttu-id="fff99-116">На следующем рисунке и описание описывается работа стороннего процесса импорта данных при работе с партнером.</span><span class="sxs-lookup"><span data-stu-id="fff99-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Как происходит импорт сторонних данных](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="fff99-118">Клиент работает с партнером по выбору, чтобы настроить соединитель, который будет извлекать элементы из стороннего источника данных, а затем импортировать эти элементы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="fff99-119">Соединитель партнера подключается к сторонним источникам данных с помощью стороннего API (на основе запланированной или настроенной конфигурации) и извлекает элементы из источника данных.</span><span class="sxs-lookup"><span data-stu-id="fff99-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="fff99-120">Партнерский соединитель преобразует содержимое элемента в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fff99-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="fff99-121">В разделе [More Information](#more-information) представлено описание схемы формата сообщений.</span><span class="sxs-lookup"><span data-stu-id="fff99-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="fff99-122">Партнерский соединитель подключается к службе Azure в Office 365 с помощью веб-службы Exchange (EWS) через хорошо известную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="fff99-122">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="fff99-p104">Элементы импортируются в почтовый ящик определенного пользователя или общий почтовый ящик для сторонних данных. Элемент импортируется в почтовый ящик определенного пользователя или общий почтовый ящик для сторонних данных, исходя из следующих критериев:</span><span class="sxs-lookup"><span data-stu-id="fff99-p104">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="fff99-125">а.</span><span class="sxs-lookup"><span data-stu-id="fff99-125">a.</span></span> <span data-ttu-id="fff99-126">**Элементы с идентификатором пользователя, соответствующим учетной записи пользователя Office 365:** Если соединитель партнера может сопоставить идентификатор пользователя элемента в источнике данных стороннего производителя с определенным ИДЕНТИФИКАТОРом пользователя в Office 365, элемент будет скопирован в папку " **очистки** " в папке "элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="fff99-126">**Items that have a user ID that corresponds to an Office 365 user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="fff99-127">У пользователей нет доступа к элементам в папке "Очистка".</span><span class="sxs-lookup"><span data-stu-id="fff99-127">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="fff99-128">Тем не менее, вы можете использовать средства обнаружения электронных данных Office 365 для поиска элементов в папке "очистки".</span><span class="sxs-lookup"><span data-stu-id="fff99-128">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="fff99-129">б)</span><span class="sxs-lookup"><span data-stu-id="fff99-129">b.</span></span> <span data-ttu-id="fff99-130">**Элементы, у которых нет идентификатора пользователя, соответствующего учетной записи пользователя Office 365:** Если соединителю партнера не удается сопоставить идентификатор пользователя с определенным ИДЕНТИФИКАТОРом пользователя в Office 365, то он копируется в папку **"Входящие"** в почтовом ящике данных стороннего производителя.</span><span class="sxs-lookup"><span data-stu-id="fff99-130">**Items that don't have a user ID that corresponds to an Office 365 user account:** If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="fff99-131">При импорте элементов в папку "Входящие" вы или другой пользователь в Организации можете войти в почтовый ящик стороннего производителя для просмотра этих элементов и управления ими, а также узнать, нужно ли вносить какие-либо изменения в конфигурацию соединителя партнера.</span><span class="sxs-lookup"><span data-stu-id="fff99-131">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="fff99-132">Шаг 1. Поиск партнера по работе со сторонними данными</span><span class="sxs-lookup"><span data-stu-id="fff99-132">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="fff99-133">Ключевой компонент для архивации сторонних данных в Office 365: Поиск и работа с партнером Майкрософт, специализирующимся на сборе данных из стороннего источника данных и их импорте в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-133">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="fff99-134">После импорта данные можно заархивировать и сохранить вместе с другими данными Майкрософт, такими как электронная почта от Exchange и документы из SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="fff99-134">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="fff99-135">Партнер создает соединитель, который извлекает данные из сторонних источников данных Организации (таких как BlackBerry, Facebook, Google +, Thomson Reuters, Twitter и YouTube), и передает эти данные в API Office 365, который импортирует элементы в почтовые ящики Exchange как сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fff99-135">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="fff99-136">В следующих разделах перечислены партнеры Майкрософт (и сторонние источники данных, которые они поддерживаются), которые участвуют в программе для архивации сторонних данных в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-136">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="fff99-137">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="fff99-137">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="fff99-138">арчивесоЦиал</span><span class="sxs-lookup"><span data-stu-id="fff99-138">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="fff99-139">глобанет</span><span class="sxs-lookup"><span data-stu-id="fff99-139">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="fff99-140">OpenText</span><span class="sxs-lookup"><span data-stu-id="fff99-140">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="fff99-141">смарш</span><span class="sxs-lookup"><span data-stu-id="fff99-141">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="fff99-142">Глагол</span><span class="sxs-lookup"><span data-stu-id="fff99-142">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="fff99-143">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="fff99-143">17a-4 LLC</span></span>

<span data-ttu-id="fff99-144">[17A – 4 LLC](https://www.17a-4.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="fff99-144">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="fff99-145">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="fff99-145">BlackBerry</span></span>
    
- <span data-ttu-id="fff99-146">потоки данных Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="fff99-146">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="fff99-147">Cisco Jabber;</span><span class="sxs-lookup"><span data-stu-id="fff99-147">Cisco Jabber</span></span>
    
- <span data-ttu-id="fff99-148">Факт</span><span class="sxs-lookup"><span data-stu-id="fff99-148">FactSet</span></span>
    
- <span data-ttu-id="fff99-149">хипчат</span><span class="sxs-lookup"><span data-stu-id="fff99-149">HipChat</span></span>
    
- <span data-ttu-id="fff99-150">инвестедже</span><span class="sxs-lookup"><span data-stu-id="fff99-150">InvestEdge</span></span>
    
- <span data-ttu-id="fff99-151">ливеперсон</span><span class="sxs-lookup"><span data-stu-id="fff99-151">LivePerson</span></span>
    
- <span data-ttu-id="fff99-152">MessageLabs Data Streams;</span><span class="sxs-lookup"><span data-stu-id="fff99-152">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="fff99-153">OpenText</span><span class="sxs-lookup"><span data-stu-id="fff99-153">OpenText</span></span>
    
- <span data-ttu-id="fff99-154">Oracle/ATG Click-to-Call Live Help;</span><span class="sxs-lookup"><span data-stu-id="fff99-154">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="fff99-155">Pivot IMTRADER;</span><span class="sxs-lookup"><span data-stu-id="fff99-155">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="fff99-156">Microsoft SharePoint;</span><span class="sxs-lookup"><span data-stu-id="fff99-156">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="fff99-157">миндалигн</span><span class="sxs-lookup"><span data-stu-id="fff99-157">MindAlign</span></span>
    
- <span data-ttu-id="fff99-158">Sitrion One (Newsgator);</span><span class="sxs-lookup"><span data-stu-id="fff99-158">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="fff99-159">Skype для бизнеса (Lync/OCS);</span><span class="sxs-lookup"><span data-stu-id="fff99-159">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="fff99-160">Skype для бизнеса Online (Lync Online);</span><span class="sxs-lookup"><span data-stu-id="fff99-160">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="fff99-161">базы данных SQL;</span><span class="sxs-lookup"><span data-stu-id="fff99-161">SQL Databases</span></span>
    
- <span data-ttu-id="fff99-162">скуавкер</span><span class="sxs-lookup"><span data-stu-id="fff99-162">Squawker</span></span>
    
- <span data-ttu-id="fff99-163">Thomson Reuters Eikon Messenger.</span><span class="sxs-lookup"><span data-stu-id="fff99-163">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="fff99-164">арчивесоЦиал</span><span class="sxs-lookup"><span data-stu-id="fff99-164">ArchiveSocial</span></span>

<span data-ttu-id="fff99-165">[АрчивесоЦиал](https://www.archivesocial.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="fff99-165">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="fff99-166">Facebook</span><span class="sxs-lookup"><span data-stu-id="fff99-166">Facebook</span></span>
    
- <span data-ttu-id="fff99-167">Flickr</span><span class="sxs-lookup"><span data-stu-id="fff99-167">Flickr</span></span>
    
- <span data-ttu-id="fff99-168">инстаграм</span><span class="sxs-lookup"><span data-stu-id="fff99-168">Instagram</span></span>
    
- <span data-ttu-id="fff99-169">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="fff99-169">LinkedIn</span></span>
    
- <span data-ttu-id="fff99-170">пинтерест</span><span class="sxs-lookup"><span data-stu-id="fff99-170">Pinterest</span></span>
    
- <span data-ttu-id="fff99-171">Twitter</span><span class="sxs-lookup"><span data-stu-id="fff99-171">Twitter</span></span>
    
- <span data-ttu-id="fff99-172">YouTube</span><span class="sxs-lookup"><span data-stu-id="fff99-172">YouTube</span></span>
    
- <span data-ttu-id="fff99-173">Vimeo</span><span class="sxs-lookup"><span data-stu-id="fff99-173">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="fff99-174">глобанет</span><span class="sxs-lookup"><span data-stu-id="fff99-174">Globanet</span></span>

<span data-ttu-id="fff99-175">[Глобанет](https://www.globanet.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="fff99-175">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="fff99-176">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="fff99-176">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="fff99-177">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="fff99-177">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="fff99-178">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="fff99-178">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="fff99-179">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="fff99-179">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="fff99-180">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="fff99-180">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="fff99-181">Bloomberg Chat;</span><span class="sxs-lookup"><span data-stu-id="fff99-181">Bloomberg Chat</span></span>
    
- <span data-ttu-id="fff99-182">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="fff99-182">Bloomberg Mail</span></span>
    
- <span data-ttu-id="fff99-183">Box</span><span class="sxs-lookup"><span data-stu-id="fff99-183">Box</span></span>
    
- <span data-ttu-id="fff99-184">CipherCloud для Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="fff99-184">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="fff99-185">Сервер для &amp; обмена мгновенными сообщениями Cisco (10, v 10.5.1 SU1, v SU2, v 11.5)</span><span class="sxs-lookup"><span data-stu-id="fff99-185">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="fff99-186">Cisco Вебекс Teams</span><span class="sxs-lookup"><span data-stu-id="fff99-186">Cisco Webex Teams</span></span>

- <span data-ttu-id="fff99-187">ShareFile рабочей &amp; области Citrix</span><span class="sxs-lookup"><span data-stu-id="fff99-187">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="fff99-188">кровдкомпасс</span><span class="sxs-lookup"><span data-stu-id="fff99-188">CrowdCompass</span></span>

- <span data-ttu-id="fff99-189">Текстовые файлы с разделителями</span><span class="sxs-lookup"><span data-stu-id="fff99-189">Custom-delimited text files</span></span>
    
- <span data-ttu-id="fff99-190">настраиваемые XML-файлы;</span><span class="sxs-lookup"><span data-stu-id="fff99-190">Custom XML files</span></span>
    
- <span data-ttu-id="fff99-191">Facebook (страницы)</span><span class="sxs-lookup"><span data-stu-id="fff99-191">Facebook (Pages)</span></span>
    
- <span data-ttu-id="fff99-192">Факт</span><span class="sxs-lookup"><span data-stu-id="fff99-192">Factset</span></span>
    
- <span data-ttu-id="fff99-193">фксконнект</span><span class="sxs-lookup"><span data-stu-id="fff99-193">FXConnect</span></span>
    
- <span data-ttu-id="fff99-194">ICE Chat или YellowJacket;</span><span class="sxs-lookup"><span data-stu-id="fff99-194">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="fff99-195">Jive</span><span class="sxs-lookup"><span data-stu-id="fff99-195">Jive</span></span>
    
- <span data-ttu-id="fff99-196">Macgregor XIP;</span><span class="sxs-lookup"><span data-stu-id="fff99-196">Macgregor XIP</span></span>

- <span data-ttu-id="fff99-197">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="fff99-197">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="fff99-198">Microsoft OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fff99-198">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="fff99-199">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fff99-199">Microsoft Teams</span></span>
       
- <span data-ttu-id="fff99-200">Microsoft Yammer;</span><span class="sxs-lookup"><span data-stu-id="fff99-200">Microsoft Yammer</span></span>
    
- <span data-ttu-id="fff99-201">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="fff99-201">Mobile Guard</span></span>
    
- <span data-ttu-id="fff99-202">Сводка</span><span class="sxs-lookup"><span data-stu-id="fff99-202">Pivot</span></span>
    
- <span data-ttu-id="fff99-203">Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="fff99-203">Salesforce Chatter</span></span>

- <span data-ttu-id="fff99-204">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="fff99-204">Skype for Business Online</span></span>
    
- <span data-ttu-id="fff99-205">Skype для бизнеса, версии от 2007 R2 до 2016 (локальные);</span><span class="sxs-lookup"><span data-stu-id="fff99-205">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="fff99-206">Slack Enterprise Grid;</span><span class="sxs-lookup"><span data-stu-id="fff99-206">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="fff99-207">симфони</span><span class="sxs-lookup"><span data-stu-id="fff99-207">Symphony</span></span>
    
- <span data-ttu-id="fff99-208">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="fff99-208">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="fff99-209">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="fff99-209">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="fff99-210">Thomson Reuters Dealings 3000 или FX Trading;</span><span class="sxs-lookup"><span data-stu-id="fff99-210">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="fff99-211">Twitter</span><span class="sxs-lookup"><span data-stu-id="fff99-211">Twitter</span></span>
    
- <span data-ttu-id="fff99-212">UBS Chat;</span><span class="sxs-lookup"><span data-stu-id="fff99-212">UBS Chat</span></span>
    
- <span data-ttu-id="fff99-213">YouTube</span><span class="sxs-lookup"><span data-stu-id="fff99-213">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="fff99-214">OpenText</span><span class="sxs-lookup"><span data-stu-id="fff99-214">OpenText</span></span>

<span data-ttu-id="fff99-215">[Опентекст](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="fff99-215">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="fff99-216">Axs Encrypted;</span><span class="sxs-lookup"><span data-stu-id="fff99-216">Axs Encrypted</span></span>
    
- <span data-ttu-id="fff99-217">Axs Exchange;</span><span class="sxs-lookup"><span data-stu-id="fff99-217">Axs Exchange</span></span>
    
- <span data-ttu-id="fff99-218">Axs Local Archive;</span><span class="sxs-lookup"><span data-stu-id="fff99-218">Axs Local Archive</span></span>
    
- <span data-ttu-id="fff99-219">Axs PlaceHolder;</span><span class="sxs-lookup"><span data-stu-id="fff99-219">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="fff99-220">Axs Signed;</span><span class="sxs-lookup"><span data-stu-id="fff99-220">Axs Signed</span></span>
    
- <span data-ttu-id="fff99-221">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="fff99-221">Bloomberg</span></span>
    
- <span data-ttu-id="fff99-222">Thomson Reuters.</span><span class="sxs-lookup"><span data-stu-id="fff99-222">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="fff99-223">смарш</span><span class="sxs-lookup"><span data-stu-id="fff99-223">Smarsh</span></span>

<span data-ttu-id="fff99-224">[Смарш](https://www.smarsh.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="fff99-224">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="fff99-225">СТАРАЙТЕСЬ</span><span class="sxs-lookup"><span data-stu-id="fff99-225">AIM</span></span>
    
- <span data-ttu-id="fff99-226">American Idol;</span><span class="sxs-lookup"><span data-stu-id="fff99-226">American Idol</span></span>
    
- <span data-ttu-id="fff99-227">Apple Juice;</span><span class="sxs-lookup"><span data-stu-id="fff99-227">Apple Juice</span></span>
    
- <span data-ttu-id="fff99-228">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="fff99-228">AOL with Pivot client</span></span>
    
- <span data-ttu-id="fff99-229">арес</span><span class="sxs-lookup"><span data-stu-id="fff99-229">Ares</span></span>
    
- <span data-ttu-id="fff99-230">Bazaar Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-230">Bazaar Voice</span></span>
    
- <span data-ttu-id="fff99-231">Bear Share;</span><span class="sxs-lookup"><span data-stu-id="fff99-231">Bear Share</span></span>
    
- <span data-ttu-id="fff99-232">Bit Torrent;</span><span class="sxs-lookup"><span data-stu-id="fff99-232">Bit Torrent</span></span>
    
- <span data-ttu-id="fff99-233">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="fff99-233">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="fff99-234">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="fff99-234">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="fff99-235">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="fff99-235">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="fff99-236">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="fff99-236">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="fff99-237">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="fff99-237">Bloomberg Mail</span></span>
    
- <span data-ttu-id="fff99-238">целлтруст</span><span class="sxs-lookup"><span data-stu-id="fff99-238">CellTrust</span></span>
    
- <span data-ttu-id="fff99-239">импорт чата;</span><span class="sxs-lookup"><span data-stu-id="fff99-239">Chat Import</span></span>
    
- <span data-ttu-id="fff99-240">политика и ведение журнала чата в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="fff99-240">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="fff99-241">Chatter;</span><span class="sxs-lookup"><span data-stu-id="fff99-241">Chatter</span></span>
    
- <span data-ttu-id="fff99-242">Сервер Cisco &amp; IM Presence Server (v 9.0.1, v 9.1, v 9.1.1 SU1, 10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="fff99-242">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="fff99-243">Cisco Unified Presence Server (версии 8.6.3, 8.6.4, 8.6.5);</span><span class="sxs-lookup"><span data-stu-id="fff99-243">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="fff99-244">импорт совместной работы;</span><span class="sxs-lookup"><span data-stu-id="fff99-244">Collaboration Import</span></span>
    
- <span data-ttu-id="fff99-245">ведение журнала совместной работы в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="fff99-245">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="fff99-246">Direct Connect;</span><span class="sxs-lookup"><span data-stu-id="fff99-246">Direct Connect</span></span>
    
- <span data-ttu-id="fff99-247">Facebook</span><span class="sxs-lookup"><span data-stu-id="fff99-247">Facebook</span></span>
    
- <span data-ttu-id="fff99-248">Факт</span><span class="sxs-lookup"><span data-stu-id="fff99-248">FactSet</span></span>
    
- <span data-ttu-id="fff99-249">FastTrack</span><span class="sxs-lookup"><span data-stu-id="fff99-249">FastTrack</span></span>
    
- <span data-ttu-id="fff99-250">гнутелла</span><span class="sxs-lookup"><span data-stu-id="fff99-250">Gnutella</span></span>
    
- <span data-ttu-id="fff99-251">Google +</span><span class="sxs-lookup"><span data-stu-id="fff99-251">Google+</span></span>
    
- <span data-ttu-id="fff99-252">готомипк</span><span class="sxs-lookup"><span data-stu-id="fff99-252">GoToMyPC</span></span>
    
- <span data-ttu-id="fff99-253">хопстер</span><span class="sxs-lookup"><span data-stu-id="fff99-253">Hopster</span></span>
    
- <span data-ttu-id="fff99-254">хубконнекс</span><span class="sxs-lookup"><span data-stu-id="fff99-254">HubConnex</span></span>
    
- <span data-ttu-id="fff99-255">IBM Connections (версии 3.0.1, 4.0, 4.5, 4.5 CR3, 5);</span><span class="sxs-lookup"><span data-stu-id="fff99-255">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="fff99-256">IBM Connections Chat Cloud;</span><span class="sxs-lookup"><span data-stu-id="fff99-256">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="fff99-257">IBM Connections Social Cloud;</span><span class="sxs-lookup"><span data-stu-id="fff99-257">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="fff99-258">IBM SameTime Advanced 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="fff99-258">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="fff99-259">IBM SameTime Communicate 9.0;</span><span class="sxs-lookup"><span data-stu-id="fff99-259">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="fff99-260">IBM SameTime Community (версии 8.0.2, 8.5.1 IFR2, 8.5.2 IFR1, 9.1);</span><span class="sxs-lookup"><span data-stu-id="fff99-260">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="fff99-261">IBM SameTime Complete 9.0;</span><span class="sxs-lookup"><span data-stu-id="fff99-261">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="fff99-262">IBM SameTime Conference 9.0;</span><span class="sxs-lookup"><span data-stu-id="fff99-262">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="fff99-263">IBM SameTime Meeting 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="fff99-263">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="fff99-264">ICE/Елловжаккет</span><span class="sxs-lookup"><span data-stu-id="fff99-264">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="fff99-265">импорт мгновенных сообщений;</span><span class="sxs-lookup"><span data-stu-id="fff99-265">IM Import</span></span>
    
- <span data-ttu-id="fff99-266">политика и ведение журнала обмена мгновенными сообщениями в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="fff99-266">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="fff99-267">Indii Messenger;</span><span class="sxs-lookup"><span data-stu-id="fff99-267">Indii Messenger</span></span>
    
- <span data-ttu-id="fff99-268">Instant Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="fff99-268">Instant Bloomberg</span></span>
    
- <span data-ttu-id="fff99-269">IRC</span><span class="sxs-lookup"><span data-stu-id="fff99-269">IRC</span></span>
    
- <span data-ttu-id="fff99-270">Jive</span><span class="sxs-lookup"><span data-stu-id="fff99-270">Jive</span></span>
    
- <span data-ttu-id="fff99-271">Jive 6 Real Time Logging (версии 6, 7);</span><span class="sxs-lookup"><span data-stu-id="fff99-271">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="fff99-272">импорт Jive;</span><span class="sxs-lookup"><span data-stu-id="fff99-272">Jive Import</span></span>
    
- <span data-ttu-id="fff99-273">жкста</span><span class="sxs-lookup"><span data-stu-id="fff99-273">JXTA</span></span>
    
- <span data-ttu-id="fff99-274">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="fff99-274">LinkedIn</span></span>
    
- <span data-ttu-id="fff99-275">Microsoft Lync (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="fff99-275">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="fff99-276">мфтп</span><span class="sxs-lookup"><span data-stu-id="fff99-276">MFTP</span></span>
    
- <span data-ttu-id="fff99-277">Microsoft Lync 2013 Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-277">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="fff99-278">Microsoft SharePoint (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="fff99-278">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="fff99-279">Microsoft SharePoint Online;</span><span class="sxs-lookup"><span data-stu-id="fff99-279">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="fff99-280">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="fff99-280">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="fff99-281">миндалигн</span><span class="sxs-lookup"><span data-stu-id="fff99-281">MindAlign</span></span>
    
- <span data-ttu-id="fff99-282">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="fff99-282">Mobile Guard</span></span>
    
- <span data-ttu-id="fff99-283">СЕТЬЮ</span><span class="sxs-lookup"><span data-stu-id="fff99-283">MSN</span></span>
    
- <span data-ttu-id="fff99-284">My Space;</span><span class="sxs-lookup"><span data-stu-id="fff99-284">My Space</span></span>
    
- <span data-ttu-id="fff99-285">неонетворк</span><span class="sxs-lookup"><span data-stu-id="fff99-285">NEONetwork</span></span>
    
- <span data-ttu-id="fff99-286">Office 365 Lync Dedicated;</span><span class="sxs-lookup"><span data-stu-id="fff99-286">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="fff99-287">групповой чат Office 365;</span><span class="sxs-lookup"><span data-stu-id="fff99-287">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="fff99-288">пинтерест</span><span class="sxs-lookup"><span data-stu-id="fff99-288">Pinterest</span></span>
    
- <span data-ttu-id="fff99-289">Сводка</span><span class="sxs-lookup"><span data-stu-id="fff99-289">Pivot</span></span>
    
- <span data-ttu-id="fff99-290">QQ</span><span class="sxs-lookup"><span data-stu-id="fff99-290">QQ</span></span>
    
- <span data-ttu-id="fff99-291">Skype для бизнеса 2015;</span><span class="sxs-lookup"><span data-stu-id="fff99-291">Skype for Business 2015</span></span>
    
- <span data-ttu-id="fff99-292">софтесер</span><span class="sxs-lookup"><span data-stu-id="fff99-292">SoftEther</span></span>
    
- <span data-ttu-id="fff99-293">симфони</span><span class="sxs-lookup"><span data-stu-id="fff99-293">Symphony</span></span>
    
- <span data-ttu-id="fff99-294">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="fff99-294">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="fff99-295">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="fff99-295">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="fff99-296">тор</span><span class="sxs-lookup"><span data-stu-id="fff99-296">Tor</span></span>
    
- <span data-ttu-id="fff99-297">ттт</span><span class="sxs-lookup"><span data-stu-id="fff99-297">TTT</span></span>
    
- <span data-ttu-id="fff99-298">Twitter</span><span class="sxs-lookup"><span data-stu-id="fff99-298">Twitter</span></span>
    
- <span data-ttu-id="fff99-299">винмкс</span><span class="sxs-lookup"><span data-stu-id="fff99-299">WinMX</span></span>
    
- <span data-ttu-id="fff99-300">винни</span><span class="sxs-lookup"><span data-stu-id="fff99-300">Winny</span></span>
    
- <span data-ttu-id="fff99-301">Yahoo</span><span class="sxs-lookup"><span data-stu-id="fff99-301">Yahoo</span></span>
    
- <span data-ttu-id="fff99-302">Yammer</span><span class="sxs-lookup"><span data-stu-id="fff99-302">Yammer</span></span>
    
- <span data-ttu-id="fff99-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="fff99-303">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="fff99-304">Глагол</span><span class="sxs-lookup"><span data-stu-id="fff99-304">Verba</span></span>

<span data-ttu-id="fff99-305">[Verb](https://www.verba.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="fff99-305">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="fff99-306">Avaya Aura Video;</span><span class="sxs-lookup"><span data-stu-id="fff99-306">Avaya Aura Video</span></span>
    
- <span data-ttu-id="fff99-307">Avaya Aura Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-307">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="fff99-308">Avtec Radio;</span><span class="sxs-lookup"><span data-stu-id="fff99-308">Avtec Radio</span></span>
    
- <span data-ttu-id="fff99-309">Bosch/Telex Radio;</span><span class="sxs-lookup"><span data-stu-id="fff99-309">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="fff99-310">BroadSoft Video;</span><span class="sxs-lookup"><span data-stu-id="fff99-310">BroadSoft Video</span></span>
    
- <span data-ttu-id="fff99-311">BroadSoft Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-311">BroadSoft Voice</span></span>
    
- <span data-ttu-id="fff99-312">Centile Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-312">Centile Voice</span></span>
    
- <span data-ttu-id="fff99-313">Cisco Jabber IM;</span><span class="sxs-lookup"><span data-stu-id="fff99-313">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="fff99-314">Cisco UC Video;</span><span class="sxs-lookup"><span data-stu-id="fff99-314">Cisco UC Video</span></span>
    
- <span data-ttu-id="fff99-315">Cisco UC Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-315">Cisco UC Voice</span></span>
    
- <span data-ttu-id="fff99-316">Cisco UCCX/UCCE Video</span><span class="sxs-lookup"><span data-stu-id="fff99-316">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="fff99-317">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="fff99-317">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="fff99-318">ESChat Radio;</span><span class="sxs-lookup"><span data-stu-id="fff99-318">ESChat Radio</span></span>
    
- <span data-ttu-id="fff99-319">Geoman Contact Expert;</span><span class="sxs-lookup"><span data-stu-id="fff99-319">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="fff99-320">IP Trade Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-320">IP Trade Voice</span></span>
    
- <span data-ttu-id="fff99-321">Luware LUCS Contact Center;</span><span class="sxs-lookup"><span data-stu-id="fff99-321">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="fff99-322">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="fff99-322">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="fff99-323">Mitel MiContact Center для Lync (prairieFyre);</span><span class="sxs-lookup"><span data-stu-id="fff99-323">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="fff99-324">Oracle / Acme Packet Session Border Controller Video;</span><span class="sxs-lookup"><span data-stu-id="fff99-324">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="fff99-325">Oracle / Acme Packet Session Border Controller Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-325">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="fff99-326">Singtel Mobile Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-326">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="fff99-327">SIPREC Video;</span><span class="sxs-lookup"><span data-stu-id="fff99-327">SIPREC Video</span></span>
    
-  <span data-ttu-id="fff99-328">SIPREC Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-328">SIPREC Voice</span></span> 
    
- <span data-ttu-id="fff99-329">Skype для бизнеса / Lync IM;</span><span class="sxs-lookup"><span data-stu-id="fff99-329">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="fff99-330">Skype для бизнеса / Lync Video;</span><span class="sxs-lookup"><span data-stu-id="fff99-330">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="fff99-331">Skype для бизнеса / Lync Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-331">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="fff99-332">Speakerbus Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-332">Speakerbus Voice</span></span>
    
- <span data-ttu-id="fff99-333">Standard SIP/H.323 Video;</span><span class="sxs-lookup"><span data-stu-id="fff99-333">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="fff99-334">Standard SIP/H.323 Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-334">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="fff99-335">Truphone Voice;</span><span class="sxs-lookup"><span data-stu-id="fff99-335">Truphone Voice</span></span>
    
- <span data-ttu-id="fff99-336">TwistedPair Radio;</span><span class="sxs-lookup"><span data-stu-id="fff99-336">TwistedPair Radio</span></span>
    
- <span data-ttu-id="fff99-337">рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="fff99-337">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="fff99-338">Шаг 2. Создание и настройка почтового ящика сторонних данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="fff99-338">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="fff99-339">Ниже приведены действия по созданию и настройке почтового ящика данных стороннего производителя для импорта данных в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-339">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="fff99-340">Как было сказано выше, элементы импортируются в этот почтовый ящик, если соединитель партнера не может сопоставить идентификатор пользователя с учетной записью пользователя Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-340">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="fff99-341">**Выполните эти действия в центре администрирования Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="fff99-341">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="fff99-342">Создайте учетную запись пользователя в Office 365 и назначьте ей лицензию на Exchange Online (план 2). Ознакомьтесь [со статьей Добавление пользователей в Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="fff99-342">Create a user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="fff99-343">Лицензия на план 2 необходима, чтобы поместить почтовый ящик на хранение для судебного разбирательства или включить архивный почтовый ящик с неограниченной квотой.</span><span class="sxs-lookup"><span data-stu-id="fff99-343">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="fff99-344">Добавьте учетную запись пользователя для почтового ящика данных стороннего производителя в роль администратора **администратора Exchange** в Office 365; [в разделе Назначение ролей администратора в Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="fff99-344">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="fff99-345">Запишите данные этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="fff99-345">Write down the credentials for this user account.</span></span> <span data-ttu-id="fff99-346">Их необходимо предоставить партнеру, как описано в шаге 4.</span><span class="sxs-lookup"><span data-stu-id="fff99-346">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="fff99-347">**Выполнение этих задач в центре администрирования Exchange**</span><span class="sxs-lookup"><span data-stu-id="fff99-347">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="fff99-348">Скрытие почтового ящика сторонних данных из адресной книги и других списков адресов в Организации; в разделе [Управление почтовыми ящиками пользователей](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="fff99-348">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="fff99-349">Можно также выполнить следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fff99-349">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="fff99-350">Назначьте разрешение **FullAccess** для почтового ящика данных стороннего производителя, чтобы администраторы или руководители соответствия могли открыть сторонний почтовый ящик данных в клиенте Outlook для настольных ПК. Ознакомьтесь с [разрешениями Управление разрешениями для получателей](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="fff99-350">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="fff99-351">Включите следующие функции Office 365, связанные с соответствием требованиям, для почтового ящика данных стороннего производителя:</span><span class="sxs-lookup"><span data-stu-id="fff99-351">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="fff99-352">Включение архивного почтового ящика; Разрешите [архивирование почтовых ящиков](enable-archive-mailboxes.md) и [включите неограниченное архивирование](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="fff99-352">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="fff99-353">Это позволяет освободить дисковое пространство в основном почтовом ящике, настроив политику архивации, которая перемещает сторонние элементы данных в архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="fff99-353">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="fff99-354">Это обеспечивает неограниченное хранение данных сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="fff99-354">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="fff99-355">Поместите почтовый ящик сторонних данных на хранение для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="fff99-355">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="fff99-356">Вы также можете применить политику хранения Office 365 в центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fff99-356">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="fff99-357">При помещении этого почтового ящика в удержание сохраняются сторонние элементы данных (неопределенное время или продолжительность действия), и их не следует очищать из почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="fff99-357">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="fff99-358">Просмотрите один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="fff99-358">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="fff99-359">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="fff99-359">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="fff99-360">Общие сведения о политиках хранения в Office 365</span><span class="sxs-lookup"><span data-stu-id="fff99-360">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="fff99-361">Включите ведение журнала аудита доступа к почтовому ящику сторонних данных со стороны владельца, делегата и администратора; см. статью [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="fff99-361">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="fff99-362">Это позволяет выполнять аудит всех действий, выполняемых любым пользователем, имеющим доступ к почтовому ящику данных стороннего производителя.</span><span class="sxs-lookup"><span data-stu-id="fff99-362">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="fff99-363">Шаг 3. Настройка поддержки сторонних данных для почтовых ящиков пользователей</span><span class="sxs-lookup"><span data-stu-id="fff99-363">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="fff99-364">Следующим шагом является настройка поддержки сторонних данных для почтовых ящиков пользователей.</span><span class="sxs-lookup"><span data-stu-id="fff99-364">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="fff99-365">Выполните указанные ниже действия с помощью центра администрирования Exchange или соответствующих командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fff99-365">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="fff99-366">Включите архивный почтовый ящик для каждого пользователя; Разрешите [архивирование почтовых ящиков](enable-archive-mailboxes.md) и [включите неограниченное архивирование](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="fff99-366">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="fff99-367">Помещайте почтовые ящики пользователей на хранение для судебного разбирательства или примените политику хранения Office 365; Просмотрите один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="fff99-367">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="fff99-368">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="fff99-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="fff99-369">Общие сведения о политиках хранения в Office 365</span><span class="sxs-lookup"><span data-stu-id="fff99-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="fff99-370">Как отмечалось ранее, при помещении почтовых ящиков на хранение можно указать длительность хранения элементов из источника сторонних данных или выбрать бессрочное хранение.</span><span class="sxs-lookup"><span data-stu-id="fff99-370">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="fff99-371">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="fff99-371">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="fff99-372">Последний шаг — предоставить партнеру указанные ниже сведения, чтобы он смог настроить соединитель для подключения к организации Office 365 и импорта данных в почтовые ящики пользователей и почтовый ящик сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="fff99-372">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="fff99-373">Конечная точка, используемая для подключения к службе Azure в Office 365:</span><span class="sxs-lookup"><span data-stu-id="fff99-373">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="fff99-374">Учетные данные для входа (Office 365 ID пользователя и пароль) почтового ящика данных стороннего производителя, созданного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="fff99-374">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="fff99-375">Эти учетные данные требуются соединителю партнера для доступа к элементам и их импорта в почтовые ящики пользователей и почтовый ящик со сторонними данными.</span><span class="sxs-lookup"><span data-stu-id="fff99-375">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="fff99-376">Шаг 5: Зарегистрируйте сторонний соединитель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fff99-376">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="fff99-377">Начиная с 30 сентября 2018, служба Azure в Office 365 начнет использовать современные проверки подлинности в Exchange Online для проверки подлинности сторонних соединителей данных, пытающихся подключиться к организации Office 365 для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="fff99-377">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="fff99-378">Причина этого изменения заключается в том, что современная проверка подлинности обеспечивает большую безопасность, чем текущий метод, основанный на соединителях третьих сторон вхителистинг, использующих ранее описанную конечную точку для подключения к службе Azure.</span><span class="sxs-lookup"><span data-stu-id="fff99-378">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="fff99-379">Чтобы включить сторонний соединитель данных для подключения к Office 365 с помощью нового метода проверки подлинности, администратору в организации Office 365 необходимо согласиться на регистрацию соединителя как доверенного приложения службы в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fff99-379">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="fff99-380">Для этого необходимо принять запрос на разрешение соединителей на доступ к данным Организации в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fff99-380">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="fff99-381">После принятия этого запроса сторонний соединитель данных добавляется в качестве корпоративного приложения в Azure Active Directory и представляется в качестве субъекта-службы.</span><span class="sxs-lookup"><span data-stu-id="fff99-381">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="fff99-382">Более подробную информацию можно найти в разделе [согласие администратора клиента](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="fff99-382">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="fff99-383">Ниже описаны действия, которые необходимо выполнить, чтобы получить доступ и принять запрос на регистрацию соединителя:</span><span class="sxs-lookup"><span data-stu-id="fff99-383">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="fff99-384">Перейдите на [эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) и войдите в систему, используя учетные данные глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-384">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="fff99-385">Отображается следующее диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="fff99-385">The following dialog box is displayed.</span></span> <span data-ttu-id="fff99-386">Вы можете развернуть символы крышки, чтобы просмотреть разрешения, которые будут назначены соединителю.</span><span class="sxs-lookup"><span data-stu-id="fff99-386">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="fff99-387">![Отображается диалоговое окно запроса разрешений](media/O365-ThirdPartyDataConnector-OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="fff99-387">![The permissions request dialog is displayed](media/O365-ThirdPartyDataConnector-OptIn1.png)</span></span>
2. <span data-ttu-id="fff99-388">Нажмите кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="fff99-388">Click **Accept**.</span></span>

<span data-ttu-id="fff99-389">После принятия запроса отображается [портал Azure](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="fff99-389">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="fff99-390">Чтобы просмотреть список приложений для вашей организации, щелкните элемент **Azure Active Directory** > **Enterprise Applications**.</span><span class="sxs-lookup"><span data-stu-id="fff99-390">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="fff99-391">Сторонний соединитель данных Office 365 указан в колонке **корпоративные приложения** .</span><span class="sxs-lookup"><span data-stu-id="fff99-391">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fff99-392">После 30 сентября 2018 данные сторонних поставщиков больше не будут импортироваться в почтовые ящики в вашей организации, если вы не зарегистрируете сторонний соединитель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fff99-392">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="fff99-393">Обратите внимание, что существующие сторонние соединители данных (созданные до 30 сентября 2018) также должны быть зарегистрированы в Azure Active Directory, выполнив действия, описанные в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="fff99-393">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="fff99-394">Отзыв согласия с сторонним соединителем данных</span><span class="sxs-lookup"><span data-stu-id="fff99-394">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="fff99-395">После того как ваша организация отправила запрос на разрешения на регистрацию стороннего соединителя данных в Azure Active Directory, ваша организация может в любой момент отозвать это согласие.</span><span class="sxs-lookup"><span data-stu-id="fff99-395">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="fff99-396">Однако отзыв согласия для соединителя означает, что данные из стороннего источника данных больше не будут импортироваться в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-396">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="fff99-397">Чтобы отозвать согласие на сторонние соединители данных, можно удалить приложение (удалив соответствующий субъект-службу) из Azure Active Directory, используя колонку **корпоративных приложений** на портале Azure, или с помощью [ Remove – MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fff99-397">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="fff99-398">Вы также можете использовать командлет [Remove – азуреадсервицепринЦипал](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) в Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fff99-398">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="fff99-399">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="fff99-399">More information</span></span>

- <span data-ttu-id="fff99-400">Как объяснялось ранее, элементы из сторонних источников данных импортируются в почтовые ящики Exchange в виде сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fff99-400">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="fff99-401">Соединитель партнера импортирует элемент, используя схему, требуемую API Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-401">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="fff99-402">В приведенной ниже таблице описываются свойства элемента из стороннего источника данных после его импорта в почтовый ящик Exchange в виде сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fff99-402">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="fff99-403">В этой таблице также указывается, является ли свойство сообщения обязательным.</span><span class="sxs-lookup"><span data-stu-id="fff99-403">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="fff99-404">Обязательные свойства должны быть заполнены.</span><span class="sxs-lookup"><span data-stu-id="fff99-404">Mandatory properties must be populated.</span></span> <span data-ttu-id="fff99-405">Если для элемента отсутствует обязательное свойство, оно не будет импортировано в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-405">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="fff99-406">Процесс импорта возвращает сообщение об ошибке, объясняющее, почему элемент не был импортирован и какое свойство отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fff99-406">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="fff99-407">**Свойство сообщения**</span><span class="sxs-lookup"><span data-stu-id="fff99-407">**Message property**</span></span>|<span data-ttu-id="fff99-408">**Обязательный?**</span><span class="sxs-lookup"><span data-stu-id="fff99-408">**Mandatory?**</span></span>|<span data-ttu-id="fff99-409">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fff99-409">**Description**</span></span>|<span data-ttu-id="fff99-410">**Пример значения**</span><span class="sxs-lookup"><span data-stu-id="fff99-410">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fff99-411">**FROM**</span><span class="sxs-lookup"><span data-stu-id="fff99-411">**FROM**</span></span> <br/> |<span data-ttu-id="fff99-412">Да</span><span class="sxs-lookup"><span data-stu-id="fff99-412">Yes</span></span>  <br/> |<span data-ttu-id="fff99-413">Пользователь, который создал или отправил элемент из стороннего источника данных.</span><span class="sxs-lookup"><span data-stu-id="fff99-413">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="fff99-414">Соединитель партнера пытается сопоставить идентификатор пользователя с исходным элементом (например, с маркером Twitter) с учетной записью пользователя Office 365 для всех участников (в полях "от" и "Кому").</span><span class="sxs-lookup"><span data-stu-id="fff99-414">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="fff99-415">Копия сообщения будет импортирована в почтовый ящик каждого участника.</span><span class="sxs-lookup"><span data-stu-id="fff99-415">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="fff99-416">Если ни один из участников этого элемента не может быть сопоставлен с учетной записью пользователя Office 365, он будет импортирован в почтовый ящик стороннего пользователя для архивации в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff99-416">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="fff99-417">Участник, идентифицированный как отправитель элемента, должен иметь в организации Office 365 активный почтовый ящик, в который импортируется элемент.</span><span class="sxs-lookup"><span data-stu-id="fff99-417">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="fff99-418">Если у отправителя нет активного почтового ящика, возвращается следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="fff99-418">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="fff99-419">**TO**</span><span class="sxs-lookup"><span data-stu-id="fff99-419">**TO**</span></span> <br/> |<span data-ttu-id="fff99-420">Да</span><span class="sxs-lookup"><span data-stu-id="fff99-420">Yes</span></span>  <br/> |<span data-ttu-id="fff99-421">Пользователь, получивший элемент, если это применимо к элементу в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="fff99-421">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="fff99-422">**Тема**</span><span class="sxs-lookup"><span data-stu-id="fff99-422">**SUBJECT**</span></span> <br/> |<span data-ttu-id="fff99-423">Нет</span><span class="sxs-lookup"><span data-stu-id="fff99-423">No</span></span>  <br/> |<span data-ttu-id="fff99-424">Тема исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="fff99-424">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="fff99-425">**БУДУЩ**</span><span class="sxs-lookup"><span data-stu-id="fff99-425">**DATE**</span></span> <br/> |<span data-ttu-id="fff99-426">Да</span><span class="sxs-lookup"><span data-stu-id="fff99-426">Yes</span></span>  <br/> |<span data-ttu-id="fff99-427">Дата первоначального создания или публикации элемента в источнике данных клиента.</span><span class="sxs-lookup"><span data-stu-id="fff99-427">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="fff99-428">Например, это дата, когда сообщение Twitter было твитом.</span><span class="sxs-lookup"><span data-stu-id="fff99-428">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="fff99-429">**ТЕКСТ**</span><span class="sxs-lookup"><span data-stu-id="fff99-429">**BODY**</span></span> <br/> |<span data-ttu-id="fff99-430">Нет</span><span class="sxs-lookup"><span data-stu-id="fff99-430">No</span></span>  <br/> |<span data-ttu-id="fff99-431">Содержимое сообщения или публикации.</span><span class="sxs-lookup"><span data-stu-id="fff99-431">The contents of the message or post.</span></span> <span data-ttu-id="fff99-432">Для некоторых источников данных содержимое этого свойства может совпадать с содержимым свойства **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="fff99-432">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="fff99-433">Во время процесса импорта соединитель партнера предпринимает попытку сохранить полную точность источника контента, как это возможно.</span><span class="sxs-lookup"><span data-stu-id="fff99-433">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="fff99-434">По возможности в это свойство включаются файлы, рисунки или другое содержимое исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="fff99-434">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="fff99-435">В противном случае содержимое исходного элемента включается в свойство **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="fff99-435">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="fff99-436">Содержимое этого свойства зависит от соединителя партнера и от возможности исходной платформы.</span><span class="sxs-lookup"><span data-stu-id="fff99-436">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="fff99-437">**Крепление**</span><span class="sxs-lookup"><span data-stu-id="fff99-437">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="fff99-438">Нет</span><span class="sxs-lookup"><span data-stu-id="fff99-438">No</span></span>  <br/> |<span data-ttu-id="fff99-439">Если элемент в источнике данных (например, твит в Twitter или беседе обмена мгновенными сообщениями) имеет вложенный файл или включает изображения, то партнер по подключению будет сначала пытаться включить вложения в свойство **Body** .</span><span class="sxs-lookup"><span data-stu-id="fff99-439">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="fff99-440">Если это невозможно, то оно добавляется в свойство \* \* вложение \* \*.</span><span class="sxs-lookup"><span data-stu-id="fff99-440">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="fff99-441">К другим примерам вложений относятся отметки "Нравится" в Facebook, метаданные из источника контента, а также ответы на сообщение или публикацию.</span><span class="sxs-lookup"><span data-stu-id="fff99-441">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="fff99-442">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="fff99-442">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="fff99-443">Да</span><span class="sxs-lookup"><span data-stu-id="fff99-443">Yes</span></span>  <br/> | <span data-ttu-id="fff99-444">Это свойство с несколькими значениями, которое создается и заполняется соединителем партнера.</span><span class="sxs-lookup"><span data-stu-id="fff99-444">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="fff99-445">Это свойство имеет `IPM.NOTE.Source.Event`следующий формат.</span><span class="sxs-lookup"><span data-stu-id="fff99-445">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="fff99-446">(Это свойство должно начинаться `IPM.NOTE`с.</span><span class="sxs-lookup"><span data-stu-id="fff99-446">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="fff99-447">Этот формат похож на один для класса `IPM.NOTE.X` Message.) Это свойство содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fff99-447">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="fff99-448">`Source`: Указывает источник данных стороннего производителя; Например, Twitter, Facebook или BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="fff99-448">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="fff99-449">`Event`: Указывает тип действия, которое выполнялось в источнике данных стороннего производителя, который создал элементы; Например, твит в Twitter или в учетной записи Facebook.</span><span class="sxs-lookup"><span data-stu-id="fff99-449">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="fff99-450">Каждому источнику данных характерны свои события.</span><span class="sxs-lookup"><span data-stu-id="fff99-450">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="fff99-451">Одна из целей этого свойства — фильтрация элементов на основе типа события или источника данных, в котором создан элемент.</span><span class="sxs-lookup"><span data-stu-id="fff99-451">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="fff99-452">Например, при поиске с помощью функции обнаружения электронных данных можно найти все твиты, опубликованные определенным пользователем.</span><span class="sxs-lookup"><span data-stu-id="fff99-452">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="fff99-453">При успешном импорте элементов в почтовые ящики в Office 365, в качестве части HTTP-ответа возвращается уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="fff99-453">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="fff99-454">Этот идентификатор, называемый `x-IngestionCorrelationID`, может использоваться для последующих задач по устранению неполадок, которые являются участниками для сквозного отслеживания элементов.</span><span class="sxs-lookup"><span data-stu-id="fff99-454">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="fff99-455">Партнерам рекомендуется фиксировать эту информацию и записывать ее в журнал соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="fff99-455">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="fff99-456">Пример HTTP-отклика, содержащего этот идентификатор:</span><span class="sxs-lookup"><span data-stu-id="fff99-456">Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="fff99-457">С помощью средства "поиск контента" в центре безопасности и соответствия требованиям можно искать элементы, импортированные в почтовые ящики в Office 365, из стороннего источника данных.</span><span class="sxs-lookup"><span data-stu-id="fff99-457">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="fff99-458">Чтобы выполнить поиск в этих импортированных элементах, можно использовать следующие пары "свойство: значение сообщения" в поле ключевое слово для поиска контента.</span><span class="sxs-lookup"><span data-stu-id="fff99-458">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="fff99-459">**`kind:externaldata`**: Используйте эту комбинацию свойства и значения для поиска всех сторонних типов данных.</span><span class="sxs-lookup"><span data-stu-id="fff99-459">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="fff99-460">Например, чтобы найти элементы, импортированные из стороннего источника данных и содержали слово "contoso" в свойстве subject импортированного элемента, используйте запрос `kind:externaldata AND subject:contoso`ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="fff99-460">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="fff99-461">**`itemclass:ipm.externaldata.<third-party data type>`**: Используйте эту комбинацию свойства и значения, чтобы выполнять поиск только по указанному типу сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="fff99-461">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="fff99-462">Например, чтобы искать только данные Facebook, содержащие слово "contoso" в свойстве subject, следует использовать запрос `itemclass:ipm.externaldata.Facebook* AND subject:contoso`ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="fff99-462">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="fff99-463">Полный список значений, которые необходимо использовать для сторонних типов данных для `itemclass` свойства, приведен в разделе [Использование поиска контента для поиска данных сторонних производителей, импортированных в Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="fff99-463">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="fff99-464">Дополнительные сведения об использовании средства "Поиск контента" и создании поисковых запросов по ключевым словам см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="fff99-464">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="fff99-465">Поиск контента в Office 365</span><span class="sxs-lookup"><span data-stu-id="fff99-465">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="fff99-466">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="fff99-466">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
