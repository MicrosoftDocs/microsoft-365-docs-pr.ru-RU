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
description: Узнайте, как настроить настраиваемый соединиттель для импорта сторонних данных из источников данных, таких как Salesforce Chatter, Yahoo Messenger или Yammer.
ms.openlocfilehash: 2026e3c584cb0bc467a2db3903c51b7ed50e51e1
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228763"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="27c2f-103">Архивация сторонних данных при помощи партнера</span><span class="sxs-lookup"><span data-stu-id="27c2f-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="27c2f-104">Вы можете работать с партнером Майкрософт для импорта и архива данных из сторонного источника данных для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27c2f-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="27c2f-105">Партнер может предоставить вам настраиваемый соединититель, настроенный для извлечения элементов из стороннего источника данных (на регулярной основе), а затем импортировать эти элементы.</span><span class="sxs-lookup"><span data-stu-id="27c2f-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="27c2f-106">Соединититель партнеров преобразует содержимое элемента из источника данных в формат сообщений электронной почты, а затем сохраняет элементы в почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="27c2f-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="27c2f-107">После импорта сторонних данных к этим данным можно применять Microsoft 365, такие как хранение судебного разбирательства, открытие электронных данных, In-Place архива, аудит и Microsoft 365 хранения.</span><span class="sxs-lookup"><span data-stu-id="27c2f-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27c2f-108">Решение [соответствия требованиям](communication-compliance.md) Microsoft 365 не может применяться к сторонним данным, импортируемым соединитетелями партнеров, упомянутыми в этой статье.</span><span class="sxs-lookup"><span data-stu-id="27c2f-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span>

<span data-ttu-id="27c2f-109">Ниже представлен обзор процесса и действий, необходимых для работы с партнером Майкрософт для импорта сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="27c2f-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="27c2f-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="27c2f-111">Шаг 2. Создание и настройка сторонних почтовых ящиков данных</span><span class="sxs-lookup"><span data-stu-id="27c2f-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[<span data-ttu-id="27c2f-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="27c2f-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="27c2f-113">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="27c2f-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="27c2f-114">Шаг 5. Регистрация стороннего соединиттеля данных в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="27c2f-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="27c2f-115">Как происходит импорт сторонних данных</span><span class="sxs-lookup"><span data-stu-id="27c2f-115">How the third-party data import process works</span></span>

<span data-ttu-id="27c2f-116">В следующей иллюстрации и описании описано, как работает процесс импорта сторонних данных при работе с партнером.</span><span class="sxs-lookup"><span data-stu-id="27c2f-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>

![Как происходит импорт сторонних данных](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)

1. <span data-ttu-id="27c2f-118">Клиент работает со своим партнером по выбору, чтобы настроить соединители, которые будут извлекать элементы из стороннего источника данных, а затем импортировать эти элементы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27c2f-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>

2. <span data-ttu-id="27c2f-119">Соединититель партнеров подключается к сторонним источникам данных с помощью стороннего API (на плановой или настраиваемой основе) и извлекает элементы из источника данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="27c2f-120">Партнерский соединитель преобразует содержимое элемента в формат сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="27c2f-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="27c2f-121">Дополнительные [сведения см.](#more-information) в разделе Описание схемы формата сообщений.</span><span class="sxs-lookup"><span data-stu-id="27c2f-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span>

3. <span data-ttu-id="27c2f-122">Соединититель партнеров подключается к службе Azure Microsoft 365 в Exchange веб-службе (EWS) с помощью известной точки.</span><span class="sxs-lookup"><span data-stu-id="27c2f-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>

4. <span data-ttu-id="27c2f-p103">Элементы импортируются в почтовый ящик определенного пользователя или общий почтовый ящик для сторонних данных. Элемент импортируется в почтовый ящик определенного пользователя или общий почтовый ящик для сторонних данных, исходя из следующих критериев:</span><span class="sxs-lookup"><span data-stu-id="27c2f-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>

   1. <span data-ttu-id="27c2f-125">**Элементы, которые имеют пользовательский ID, соответствующий учетной записи пользователя:** Если соединитель партнеров может соединять пользовательский код элемента в стороннем источнике данных с определенным пользовательским ИД в Microsoft 365, элемент копируется в папку **Purges** в папке "Извлекаемые элементы" пользователя.</span><span class="sxs-lookup"><span data-stu-id="27c2f-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Microsoft 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="27c2f-126">У пользователей нет доступа к элементам в папке "Очистка".</span><span class="sxs-lookup"><span data-stu-id="27c2f-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="27c2f-127">Однако для поиска элементов в папке Purges можно использовать средства для поиска электронных открытий.</span><span class="sxs-lookup"><span data-stu-id="27c2f-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>

   1. <span data-ttu-id="27c2f-128">**Элементы, у них нет пользовательского ИД, соответствующего учетной записи пользователя:** Если соединителер-партнер не может соединять пользовательский ID элемента с определенным пользовательским ИД, элемент копируется в папку **"Входящие"** в сторонний почтовый ящик данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="27c2f-129">Импорт элементов в почтовый ящик позволяет вам или кому-либо из вашей организации войти в сторонний почтовый ящик, чтобы просмотреть и управлять этими элементами, а также узнать, необходимо ли вносить какие-либо изменения в конфигурацию соединиттеля партнеров.</span><span class="sxs-lookup"><span data-stu-id="27c2f-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>

## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="27c2f-130">Шаг 1. Поиск партнера по работе со сторонними данными</span><span class="sxs-lookup"><span data-stu-id="27c2f-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="27c2f-131">Ключевым компонентом архива сторонних данных в Microsoft 365 является поиск и работа с партнером Майкрософт, который специализируется на захвате данных из сторонного источника данных и их импорте в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27c2f-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Microsoft 365.</span></span> <span data-ttu-id="27c2f-132">После импорта данных их можно архивировать и сохранять вместе с другими данными Майкрософт вашей организации, такими как электронная почта из Exchange и документы из SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="27c2f-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="27c2f-133">Партнер создает соединитель, который извлекает данные из сторонних источников данных организации (таких как BlackBerry, Facebook, Google+, Thomson Reuters, Twitter и YouTube) и передает эти данные в API Microsoft 365, который импортирует элементы в Exchange почтовые ящики в качестве сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="27c2f-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to a Microsoft 365 API that imports items to Exchange mailboxes as email messages.</span></span>

<span data-ttu-id="27c2f-134">В следующих разделах перечисляются партнеры Майкрософт (и поддерживаемые ими сторонние источники данных), участвующие в программе архивации сторонних данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27c2f-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Microsoft 365.</span></span>

[<span data-ttu-id="27c2f-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="27c2f-135">17a-4 LLC</span></span>](#17a-4-llc)

[<span data-ttu-id="27c2f-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="27c2f-136">ArchiveSocial</span></span>](#archivesocial)

[<span data-ttu-id="27c2f-137">Veritas</span><span class="sxs-lookup"><span data-stu-id="27c2f-137">Veritas</span></span>](#veritas)

[<span data-ttu-id="27c2f-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="27c2f-138">OpenText</span></span>](#opentext)

[<span data-ttu-id="27c2f-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="27c2f-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="27c2f-140">Verba</span><span class="sxs-lookup"><span data-stu-id="27c2f-140">Verba</span></span>](#verba)

### <a name="17a-4-llc"></a><span data-ttu-id="27c2f-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="27c2f-141">17a-4 LLC</span></span>

<span data-ttu-id="27c2f-142">[17a-4 LLC](https://www.17a-4.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="27c2f-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="27c2f-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="27c2f-143">BlackBerry</span></span>

- <span data-ttu-id="27c2f-144">потоки данных Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="27c2f-144">Bloomberg Data Streams</span></span>

- <span data-ttu-id="27c2f-145">Cisco Jabber;</span><span class="sxs-lookup"><span data-stu-id="27c2f-145">Cisco Jabber</span></span>

- <span data-ttu-id="27c2f-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="27c2f-146">FactSet</span></span>

- <span data-ttu-id="27c2f-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="27c2f-147">HipChat</span></span>

- <span data-ttu-id="27c2f-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="27c2f-148">InvestEdge</span></span>

- <span data-ttu-id="27c2f-149">LivePerson</span><span class="sxs-lookup"><span data-stu-id="27c2f-149">LivePerson</span></span>

- <span data-ttu-id="27c2f-150">MessageLabs Data Streams;</span><span class="sxs-lookup"><span data-stu-id="27c2f-150">MessageLabs Data Streams</span></span>

- <span data-ttu-id="27c2f-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="27c2f-151">OpenText</span></span>

- <span data-ttu-id="27c2f-152">Oracle/ATG Click-to-Call Live Help;</span><span class="sxs-lookup"><span data-stu-id="27c2f-152">Oracle/ATG 'click-to-call' Live Help</span></span>

- <span data-ttu-id="27c2f-153">Pivot IMTRADER;</span><span class="sxs-lookup"><span data-stu-id="27c2f-153">Pivot IMTRADER</span></span>

- <span data-ttu-id="27c2f-154">Microsoft SharePoint;</span><span class="sxs-lookup"><span data-stu-id="27c2f-154">Microsoft SharePoint</span></span>

- <span data-ttu-id="27c2f-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="27c2f-155">MindAlign</span></span>

- <span data-ttu-id="27c2f-156">Sitrion One (Newsgator);</span><span class="sxs-lookup"><span data-stu-id="27c2f-156">Sitrion One (Newsgator)</span></span>

- <span data-ttu-id="27c2f-157">Skype для бизнеса (Lync/OCS);</span><span class="sxs-lookup"><span data-stu-id="27c2f-157">Skype for Business (Lync/OCS)</span></span>

- <span data-ttu-id="27c2f-158">Skype для бизнеса Online (Lync Online);</span><span class="sxs-lookup"><span data-stu-id="27c2f-158">Skype for Business Online (Lync Online)</span></span>

- <span data-ttu-id="27c2f-159">базы данных SQL;</span><span class="sxs-lookup"><span data-stu-id="27c2f-159">SQL Databases</span></span>

- <span data-ttu-id="27c2f-160">Squawker</span><span class="sxs-lookup"><span data-stu-id="27c2f-160">Squawker</span></span>

- <span data-ttu-id="27c2f-161">Thomson Reuters Eikon Messenger.</span><span class="sxs-lookup"><span data-stu-id="27c2f-161">Thomson Reuters Eikon Messenger</span></span>

### <a name="archivesocial"></a><span data-ttu-id="27c2f-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="27c2f-162">ArchiveSocial</span></span>

<span data-ttu-id="27c2f-163">[ArchiveSocial](https://www.archivesocial.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="27c2f-163">[ArchiveSocial](https://www.archivesocial.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="27c2f-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="27c2f-164">Facebook</span></span>

- <span data-ttu-id="27c2f-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="27c2f-165">Flickr</span></span>

- <span data-ttu-id="27c2f-166">Instagram</span><span class="sxs-lookup"><span data-stu-id="27c2f-166">Instagram</span></span>

- <span data-ttu-id="27c2f-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="27c2f-167">LinkedIn</span></span>

- <span data-ttu-id="27c2f-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="27c2f-168">Pinterest</span></span>

- <span data-ttu-id="27c2f-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="27c2f-169">Twitter</span></span>

- <span data-ttu-id="27c2f-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="27c2f-170">YouTube</span></span>

- <span data-ttu-id="27c2f-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="27c2f-171">Vimeo</span></span>

### <a name="veritas"></a><span data-ttu-id="27c2f-172">Veritas</span><span class="sxs-lookup"><span data-stu-id="27c2f-172">Veritas</span></span>

<span data-ttu-id="27c2f-173">[Veritas](https://www.globanet.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="27c2f-173">[Veritas](https://www.globanet.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="27c2f-174">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="27c2f-174">AOL with Pivot Client</span></span>

- <span data-ttu-id="27c2f-175">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="27c2f-175">BlackBerry Call Logs (v5, v10, v12)</span></span>

- <span data-ttu-id="27c2f-176">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="27c2f-176">BlackBerry Messenger (v5, v10, v12)</span></span>

- <span data-ttu-id="27c2f-177">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="27c2f-177">BlackBerry PIN (v5, v10, v12)</span></span>

- <span data-ttu-id="27c2f-178">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="27c2f-178">BlackBerry SMS (v5, v10, v12)</span></span>

- <span data-ttu-id="27c2f-179">Bloomberg Chat;</span><span class="sxs-lookup"><span data-stu-id="27c2f-179">Bloomberg Chat</span></span>

- <span data-ttu-id="27c2f-180">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="27c2f-180">Bloomberg Mail</span></span>

- <span data-ttu-id="27c2f-181">Box</span><span class="sxs-lookup"><span data-stu-id="27c2f-181">Box</span></span>

- <span data-ttu-id="27c2f-182">CipherCloud для Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="27c2f-182">CipherCloud for Salesforce Chatter</span></span>

- <span data-ttu-id="27c2f-183">Сервер присутствия cisco im &amp; (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="27c2f-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="27c2f-184">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="27c2f-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="27c2f-185">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="27c2f-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="27c2f-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="27c2f-186">CrowdCompass</span></span>

- <span data-ttu-id="27c2f-187">Настраиваемые текстовые файлы</span><span class="sxs-lookup"><span data-stu-id="27c2f-187">Custom-delimited text files</span></span>

- <span data-ttu-id="27c2f-188">настраиваемые XML-файлы;</span><span class="sxs-lookup"><span data-stu-id="27c2f-188">Custom XML files</span></span>

- <span data-ttu-id="27c2f-189">Facebook (Страницы)</span><span class="sxs-lookup"><span data-stu-id="27c2f-189">Facebook (Pages)</span></span>

- <span data-ttu-id="27c2f-190">Factset</span><span class="sxs-lookup"><span data-stu-id="27c2f-190">Factset</span></span>

- <span data-ttu-id="27c2f-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="27c2f-191">FXConnect</span></span>

- <span data-ttu-id="27c2f-192">ICE Chat или YellowJacket;</span><span class="sxs-lookup"><span data-stu-id="27c2f-192">ICE Chat/YellowJacket</span></span>

- <span data-ttu-id="27c2f-193">Jive</span><span class="sxs-lookup"><span data-stu-id="27c2f-193">Jive</span></span>

- <span data-ttu-id="27c2f-194">Macgregor XIP;</span><span class="sxs-lookup"><span data-stu-id="27c2f-194">Macgregor XIP</span></span>

- <span data-ttu-id="27c2f-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="27c2f-195">Microsoft Exchange Server</span></span>

- <span data-ttu-id="27c2f-196">Microsoft OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="27c2f-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="27c2f-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="27c2f-197">Microsoft Teams</span></span>

- <span data-ttu-id="27c2f-198">Microsoft Yammer;</span><span class="sxs-lookup"><span data-stu-id="27c2f-198">Microsoft Yammer</span></span>

- <span data-ttu-id="27c2f-199">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="27c2f-199">Mobile Guard</span></span>

- <span data-ttu-id="27c2f-200">Pivot</span><span class="sxs-lookup"><span data-stu-id="27c2f-200">Pivot</span></span>

- <span data-ttu-id="27c2f-201">Salesforce Chatter;</span><span class="sxs-lookup"><span data-stu-id="27c2f-201">Salesforce Chatter</span></span>

- <span data-ttu-id="27c2f-202">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="27c2f-202">Skype for Business Online</span></span>

- <span data-ttu-id="27c2f-203">Skype для бизнеса, версии от 2007 R2 до 2016 (локальные);</span><span class="sxs-lookup"><span data-stu-id="27c2f-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>

- <span data-ttu-id="27c2f-204">Slack Enterprise Grid;</span><span class="sxs-lookup"><span data-stu-id="27c2f-204">Slack Enterprise Grid</span></span>

- <span data-ttu-id="27c2f-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="27c2f-205">Symphony</span></span>

- <span data-ttu-id="27c2f-206">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="27c2f-206">Thomson Reuters Eikon</span></span>

- <span data-ttu-id="27c2f-207">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="27c2f-207">Thomson Reuters Messenger</span></span>

- <span data-ttu-id="27c2f-208">Thomson Reuters Dealings 3000 или FX Trading;</span><span class="sxs-lookup"><span data-stu-id="27c2f-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>

- <span data-ttu-id="27c2f-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="27c2f-209">Twitter</span></span>

- <span data-ttu-id="27c2f-210">UBS Chat;</span><span class="sxs-lookup"><span data-stu-id="27c2f-210">UBS Chat</span></span>

- <span data-ttu-id="27c2f-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="27c2f-211">YouTube</span></span>

### <a name="opentext"></a><span data-ttu-id="27c2f-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="27c2f-212">OpenText</span></span>

<span data-ttu-id="27c2f-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="27c2f-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span>

- <span data-ttu-id="27c2f-214">Axs Encrypted;</span><span class="sxs-lookup"><span data-stu-id="27c2f-214">Axs Encrypted</span></span>

- <span data-ttu-id="27c2f-215">Axs Exchange;</span><span class="sxs-lookup"><span data-stu-id="27c2f-215">Axs Exchange</span></span>

- <span data-ttu-id="27c2f-216">Axs Local Archive;</span><span class="sxs-lookup"><span data-stu-id="27c2f-216">Axs Local Archive</span></span>

- <span data-ttu-id="27c2f-217">Axs PlaceHolder;</span><span class="sxs-lookup"><span data-stu-id="27c2f-217">Axs PlaceHolder</span></span>

- <span data-ttu-id="27c2f-218">Axs Signed;</span><span class="sxs-lookup"><span data-stu-id="27c2f-218">Axs Signed</span></span>

- <span data-ttu-id="27c2f-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="27c2f-219">Bloomberg</span></span>

- <span data-ttu-id="27c2f-220">Thomson Reuters.</span><span class="sxs-lookup"><span data-stu-id="27c2f-220">Thomson Reuters</span></span>

### <a name="smarsh"></a><span data-ttu-id="27c2f-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="27c2f-221">Smarsh</span></span>

<span data-ttu-id="27c2f-222">[Smarsh](https://www.smarsh.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="27c2f-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="27c2f-223">AIM</span><span class="sxs-lookup"><span data-stu-id="27c2f-223">AIM</span></span>

- <span data-ttu-id="27c2f-224">American Idol;</span><span class="sxs-lookup"><span data-stu-id="27c2f-224">American Idol</span></span>

- <span data-ttu-id="27c2f-225">Apple Juice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-225">Apple Juice</span></span>

- <span data-ttu-id="27c2f-226">AOL с клиентом Pivot;</span><span class="sxs-lookup"><span data-stu-id="27c2f-226">AOL with Pivot client</span></span>

- <span data-ttu-id="27c2f-227">Ares</span><span class="sxs-lookup"><span data-stu-id="27c2f-227">Ares</span></span>

- <span data-ttu-id="27c2f-228">Bazaar Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-228">Bazaar Voice</span></span>

- <span data-ttu-id="27c2f-229">Bear Share;</span><span class="sxs-lookup"><span data-stu-id="27c2f-229">Bear Share</span></span>

- <span data-ttu-id="27c2f-230">Bit Torrent;</span><span class="sxs-lookup"><span data-stu-id="27c2f-230">Bit Torrent</span></span>

- <span data-ttu-id="27c2f-231">журналы вызовов BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="27c2f-231">BlackBerry Call Logs (v5, v10, v12)</span></span>

- <span data-ttu-id="27c2f-232">BlackBerry Messenger (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="27c2f-232">BlackBerry Messenger (v5, v10, v12)</span></span>

- <span data-ttu-id="27c2f-233">PIN-код BlackBerry (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="27c2f-233">BlackBerry PIN (v5, v10, v12)</span></span>

- <span data-ttu-id="27c2f-234">BlackBerry SMS (версии 5, 10, 12);</span><span class="sxs-lookup"><span data-stu-id="27c2f-234">BlackBerry SMS (v5, v10, v12)</span></span>

- <span data-ttu-id="27c2f-235">Bloomberg Mail;</span><span class="sxs-lookup"><span data-stu-id="27c2f-235">Bloomberg Mail</span></span>

- <span data-ttu-id="27c2f-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="27c2f-236">CellTrust</span></span>

- <span data-ttu-id="27c2f-237">импорт чата;</span><span class="sxs-lookup"><span data-stu-id="27c2f-237">Chat Import</span></span>

- <span data-ttu-id="27c2f-238">политика и ведение журнала чата в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="27c2f-238">Chat Real Time Logging and Policy</span></span>

- <span data-ttu-id="27c2f-239">Chatter</span><span class="sxs-lookup"><span data-stu-id="27c2f-239">Chatter</span></span>

- <span data-ttu-id="27c2f-240">Сервер присутствия cisco im &amp; (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="27c2f-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>

- <span data-ttu-id="27c2f-241">Cisco Unified Presence Server (версии 8.6.3, 8.6.4, 8.6.5);</span><span class="sxs-lookup"><span data-stu-id="27c2f-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>

- <span data-ttu-id="27c2f-242">импорт совместной работы;</span><span class="sxs-lookup"><span data-stu-id="27c2f-242">Collaboration Import</span></span>

- <span data-ttu-id="27c2f-243">ведение журнала совместной работы в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="27c2f-243">Collaboration Real Time Logging</span></span>

- <span data-ttu-id="27c2f-244">Direct Connect;</span><span class="sxs-lookup"><span data-stu-id="27c2f-244">Direct Connect</span></span>

- <span data-ttu-id="27c2f-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="27c2f-245">Facebook</span></span>

- <span data-ttu-id="27c2f-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="27c2f-246">FactSet</span></span>

- <span data-ttu-id="27c2f-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="27c2f-247">FastTrack</span></span>

- <span data-ttu-id="27c2f-248">Gnutella</span><span class="sxs-lookup"><span data-stu-id="27c2f-248">Gnutella</span></span>

- <span data-ttu-id="27c2f-249">Google+</span><span class="sxs-lookup"><span data-stu-id="27c2f-249">Google+</span></span>

- <span data-ttu-id="27c2f-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="27c2f-250">GoToMyPC</span></span>

- <span data-ttu-id="27c2f-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="27c2f-251">Hopster</span></span>

- <span data-ttu-id="27c2f-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="27c2f-252">HubConnex</span></span>

- <span data-ttu-id="27c2f-253">IBM Connections (версии 3.0.1, 4.0, 4.5, 4.5 CR3, 5);</span><span class="sxs-lookup"><span data-stu-id="27c2f-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>

- <span data-ttu-id="27c2f-254">IBM Connections Chat Cloud;</span><span class="sxs-lookup"><span data-stu-id="27c2f-254">IBM Connections Chat Cloud</span></span>

- <span data-ttu-id="27c2f-255">IBM Connections Social Cloud;</span><span class="sxs-lookup"><span data-stu-id="27c2f-255">IBM Connections Social Cloud</span></span>

- <span data-ttu-id="27c2f-256">IBM SameTime Advanced 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="27c2f-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>

- <span data-ttu-id="27c2f-257">IBM SameTime Communicate 9.0;</span><span class="sxs-lookup"><span data-stu-id="27c2f-257">IBM SameTime Communicate 9.0</span></span>

- <span data-ttu-id="27c2f-258">IBM SameTime Community (версии 8.0.2, 8.5.1 IFR2, 8.5.2 IFR1, 9.1);</span><span class="sxs-lookup"><span data-stu-id="27c2f-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>

- <span data-ttu-id="27c2f-259">IBM SameTime Complete 9.0;</span><span class="sxs-lookup"><span data-stu-id="27c2f-259">IBM SameTime Complete 9.0</span></span>

- <span data-ttu-id="27c2f-260">IBM SameTime Conference 9.0;</span><span class="sxs-lookup"><span data-stu-id="27c2f-260">IBM SameTime Conference 9.0</span></span>

- <span data-ttu-id="27c2f-261">IBM SameTime Meeting 8.5.2 IFR1;</span><span class="sxs-lookup"><span data-stu-id="27c2f-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>

- <span data-ttu-id="27c2f-262">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="27c2f-262">ICE/YellowJacket</span></span>

- <span data-ttu-id="27c2f-263">импорт мгновенных сообщений;</span><span class="sxs-lookup"><span data-stu-id="27c2f-263">IM Import</span></span>

- <span data-ttu-id="27c2f-264">политика и ведение журнала обмена мгновенными сообщениями в реальном времени;</span><span class="sxs-lookup"><span data-stu-id="27c2f-264">IM Real Time Logging and Policy</span></span>

- <span data-ttu-id="27c2f-265">Indii Messenger;</span><span class="sxs-lookup"><span data-stu-id="27c2f-265">Indii Messenger</span></span>

- <span data-ttu-id="27c2f-266">Instant Bloomberg;</span><span class="sxs-lookup"><span data-stu-id="27c2f-266">Instant Bloomberg</span></span>

- <span data-ttu-id="27c2f-267">IRC</span><span class="sxs-lookup"><span data-stu-id="27c2f-267">IRC</span></span>

- <span data-ttu-id="27c2f-268">Jive</span><span class="sxs-lookup"><span data-stu-id="27c2f-268">Jive</span></span>

- <span data-ttu-id="27c2f-269">Jive 6 Real Time Logging (версии 6, 7);</span><span class="sxs-lookup"><span data-stu-id="27c2f-269">Jive 6 Real Time Logging (v6, v7)</span></span>

- <span data-ttu-id="27c2f-270">импорт Jive;</span><span class="sxs-lookup"><span data-stu-id="27c2f-270">Jive Import</span></span>

- <span data-ttu-id="27c2f-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="27c2f-271">JXTA</span></span>

- <span data-ttu-id="27c2f-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="27c2f-272">LinkedIn</span></span>

- <span data-ttu-id="27c2f-273">Microsoft Lync (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="27c2f-273">Microsoft Lync (2010, 2013)</span></span>

- <span data-ttu-id="27c2f-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="27c2f-274">MFTP</span></span>

- <span data-ttu-id="27c2f-275">Microsoft Lync 2013 Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-275">Microsoft Lync 2013 Voice</span></span>

- <span data-ttu-id="27c2f-276">Microsoft SharePoint (2010, 2013);</span><span class="sxs-lookup"><span data-stu-id="27c2f-276">Microsoft SharePoint (2010, 2013)</span></span>

- <span data-ttu-id="27c2f-277">Microsoft SharePoint Online;</span><span class="sxs-lookup"><span data-stu-id="27c2f-277">Microsoft SharePoint Online</span></span>

- <span data-ttu-id="27c2f-278">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="27c2f-278">Microsoft UC (Unified Communications)</span></span>

- <span data-ttu-id="27c2f-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="27c2f-279">MindAlign</span></span>

- <span data-ttu-id="27c2f-280">Mobile Guard;</span><span class="sxs-lookup"><span data-stu-id="27c2f-280">Mobile Guard</span></span>

- <span data-ttu-id="27c2f-281">MSN</span><span class="sxs-lookup"><span data-stu-id="27c2f-281">MSN</span></span>

- <span data-ttu-id="27c2f-282">My Space;</span><span class="sxs-lookup"><span data-stu-id="27c2f-282">My Space</span></span>

- <span data-ttu-id="27c2f-283">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="27c2f-283">NEONetwork</span></span>

- <span data-ttu-id="27c2f-284">Microsoft 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="27c2f-284">Microsoft 365 Lync Dedicated</span></span>

- <span data-ttu-id="27c2f-285">Microsoft 365 Общий чат</span><span class="sxs-lookup"><span data-stu-id="27c2f-285">Microsoft 365 Shared IM</span></span>

- <span data-ttu-id="27c2f-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="27c2f-286">Pinterest</span></span>

- <span data-ttu-id="27c2f-287">Pivot</span><span class="sxs-lookup"><span data-stu-id="27c2f-287">Pivot</span></span>

- <span data-ttu-id="27c2f-288">QQ</span><span class="sxs-lookup"><span data-stu-id="27c2f-288">QQ</span></span>

- <span data-ttu-id="27c2f-289">Skype для бизнеса 2015;</span><span class="sxs-lookup"><span data-stu-id="27c2f-289">Skype for Business 2015</span></span>

- <span data-ttu-id="27c2f-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="27c2f-290">SoftEther</span></span>

- <span data-ttu-id="27c2f-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="27c2f-291">Symphony</span></span>

- <span data-ttu-id="27c2f-292">Thomson Reuters Eikon;</span><span class="sxs-lookup"><span data-stu-id="27c2f-292">Thomson Reuters Eikon</span></span>

- <span data-ttu-id="27c2f-293">Thomson Reuters Messenger;</span><span class="sxs-lookup"><span data-stu-id="27c2f-293">Thomson Reuters Messenger</span></span>

- <span data-ttu-id="27c2f-294">Tor</span><span class="sxs-lookup"><span data-stu-id="27c2f-294">Tor</span></span>

- <span data-ttu-id="27c2f-295">TTT</span><span class="sxs-lookup"><span data-stu-id="27c2f-295">TTT</span></span>

- <span data-ttu-id="27c2f-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="27c2f-296">Twitter</span></span>

- <span data-ttu-id="27c2f-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="27c2f-297">WinMX</span></span>

- <span data-ttu-id="27c2f-298">Winny</span><span class="sxs-lookup"><span data-stu-id="27c2f-298">Winny</span></span>

- <span data-ttu-id="27c2f-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="27c2f-299">Yahoo</span></span>

- <span data-ttu-id="27c2f-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="27c2f-300">Yammer</span></span>

- <span data-ttu-id="27c2f-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="27c2f-301">YouTube</span></span>


### <a name="verba"></a><span data-ttu-id="27c2f-302">Verba</span><span class="sxs-lookup"><span data-stu-id="27c2f-302">Verba</span></span>

<span data-ttu-id="27c2f-303">[Verba](https://www.verba.com) поддерживает следующие сторонние источники данных:</span><span class="sxs-lookup"><span data-stu-id="27c2f-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="27c2f-304">Avaya Aura Video;</span><span class="sxs-lookup"><span data-stu-id="27c2f-304">Avaya Aura Video</span></span>

- <span data-ttu-id="27c2f-305">Avaya Aura Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-305">Avaya Aura Voice</span></span>

- <span data-ttu-id="27c2f-306">Avtec Radio;</span><span class="sxs-lookup"><span data-stu-id="27c2f-306">Avtec Radio</span></span>

- <span data-ttu-id="27c2f-307">Bosch/Telex Radio;</span><span class="sxs-lookup"><span data-stu-id="27c2f-307">Bosch/Telex Radio</span></span>

- <span data-ttu-id="27c2f-308">BroadSoft Video;</span><span class="sxs-lookup"><span data-stu-id="27c2f-308">BroadSoft Video</span></span>

- <span data-ttu-id="27c2f-309">BroadSoft Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-309">BroadSoft Voice</span></span>

- <span data-ttu-id="27c2f-310">Centile Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-310">Centile Voice</span></span>

- <span data-ttu-id="27c2f-311">Cisco Jabber IM;</span><span class="sxs-lookup"><span data-stu-id="27c2f-311">Cisco Jabber IM</span></span>

- <span data-ttu-id="27c2f-312">Cisco UC Video;</span><span class="sxs-lookup"><span data-stu-id="27c2f-312">Cisco UC Video</span></span>

- <span data-ttu-id="27c2f-313">Cisco UC Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-313">Cisco UC Voice</span></span>

- <span data-ttu-id="27c2f-314">Видео Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="27c2f-314">Cisco UCCX/UCCE Video</span></span>

- <span data-ttu-id="27c2f-315">Голос Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="27c2f-315">Cisco UCCX/UCCE Voice</span></span>

- <span data-ttu-id="27c2f-316">ESChat Radio;</span><span class="sxs-lookup"><span data-stu-id="27c2f-316">ESChat Radio</span></span>

- <span data-ttu-id="27c2f-317">Geoman Contact Expert;</span><span class="sxs-lookup"><span data-stu-id="27c2f-317">Geoman Contact Expert</span></span>

- <span data-ttu-id="27c2f-318">IP Trade Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-318">IP Trade Voice</span></span>

- <span data-ttu-id="27c2f-319">Luware LUCS Contact Center;</span><span class="sxs-lookup"><span data-stu-id="27c2f-319">Luware LUCS Contact Center</span></span>

- <span data-ttu-id="27c2f-320">Microsoft UC (Unified Communications);</span><span class="sxs-lookup"><span data-stu-id="27c2f-320">Microsoft UC (Unified Communications)</span></span>

- <span data-ttu-id="27c2f-321">Mitel MiContact Center для Lync (prairieFyre);</span><span class="sxs-lookup"><span data-stu-id="27c2f-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>

- <span data-ttu-id="27c2f-322">Oracle / Acme Packet Session Border Controller Video;</span><span class="sxs-lookup"><span data-stu-id="27c2f-322">Oracle / Acme Packet Session Border Controller Video</span></span>

- <span data-ttu-id="27c2f-323">Oracle / Acme Packet Session Border Controller Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-323">Oracle / Acme Packet Session Border Controller Voice</span></span>

- <span data-ttu-id="27c2f-324">Singtel Mobile Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-324">Singtel Mobile Voice</span></span>

- <span data-ttu-id="27c2f-325">SIPREC Video;</span><span class="sxs-lookup"><span data-stu-id="27c2f-325">SIPREC Video</span></span>

-  <span data-ttu-id="27c2f-326">SIPREC Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-326">SIPREC Voice</span></span>

- <span data-ttu-id="27c2f-327">Skype для бизнеса / Lync IM;</span><span class="sxs-lookup"><span data-stu-id="27c2f-327">Skype for Business / Lync IM</span></span>

- <span data-ttu-id="27c2f-328">Skype для бизнеса / Lync Video;</span><span class="sxs-lookup"><span data-stu-id="27c2f-328">Skype for Business / Lync Video</span></span>

- <span data-ttu-id="27c2f-329">Skype для бизнеса / Lync Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-329">Skype for Business / Lync Voice</span></span>

- <span data-ttu-id="27c2f-330">Speakerbus Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-330">Speakerbus Voice</span></span>

- <span data-ttu-id="27c2f-331">Standard SIP/H.323 Video;</span><span class="sxs-lookup"><span data-stu-id="27c2f-331">Standard SIP/H.323 Video</span></span>

- <span data-ttu-id="27c2f-332">Standard SIP/H.323 Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-332">Standard SIP/H.323 Voice</span></span>

- <span data-ttu-id="27c2f-333">Truphone Voice;</span><span class="sxs-lookup"><span data-stu-id="27c2f-333">Truphone Voice</span></span>

- <span data-ttu-id="27c2f-334">TwistedPair Radio;</span><span class="sxs-lookup"><span data-stu-id="27c2f-334">TwistedPair Radio</span></span>

- <span data-ttu-id="27c2f-335">рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="27c2f-335">Windows Desktop Computer Screen</span></span>

## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a><span data-ttu-id="27c2f-336">Шаг 2. Создание и настройка сторонних почтовых ящиков данных в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27c2f-336">Step 2: Create and configure a third-party data mailbox in Microsoft 365</span></span>

<span data-ttu-id="27c2f-337">Ниже личные сведения о том, как создать и настроить сторонний почтовый ящик данных для импорта данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27c2f-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Microsoft 365.</span></span> <span data-ttu-id="27c2f-338">Как объяснялось ранее, элементы импортируют в этот почтовый ящик, если соединители партнер не может соотносят пользовательский ID элемента с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="27c2f-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>

 <span data-ttu-id="27c2f-339">**Выполните эти задачи в Центр администрирования Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="27c2f-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>

1. <span data-ttu-id="27c2f-340">Создание учетной записи пользователя и назначение Exchange Online plan 2; см. [добавление пользователей в Microsoft 365](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="27c2f-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Microsoft 365](../admin/add-users/add-users.md).</span></span> <span data-ttu-id="27c2f-341">Для хранения почтового ящика в удержании судебного разбирательства или для архивного почтового ящика с неограниченной квотой хранения требуется лицензия Plan 2.</span><span class="sxs-lookup"><span data-stu-id="27c2f-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>

2. <span data-ttu-id="27c2f-342">Добавление учетной записи пользователя для сторонних почтовых ящиков данных в Exchange **администратора** в Microsoft 365; см. [назначение ролей администратора в Microsoft 365](../admin/add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="27c2f-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Microsoft 365; see [Assign admin roles in Microsoft 365](../admin/add-users/assign-admin-roles.md).</span></span>

    > [!TIP]
    > <span data-ttu-id="27c2f-p109">Запишите данные этой учетной записи. Их необходимо предоставить партнеру, как описано в шаге 4.</span><span class="sxs-lookup"><span data-stu-id="27c2f-p109">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span>

 <span data-ttu-id="27c2f-345">**Выполните эти задачи в Exchange центре администрирования**</span><span class="sxs-lookup"><span data-stu-id="27c2f-345">**Complete these tasks in the Exchange admin center**</span></span>

1. <span data-ttu-id="27c2f-346">Скрыть сторонний почтовый ящик данных из адресной книги и других списков адресов в организации; см. [управление почтовыми ящиками пользователей.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="27c2f-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span></span> <span data-ttu-id="27c2f-347">Можно также выполнить следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="27c2f-347">Alternatively, you can run the following PowerShell command:</span></span>

    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="27c2f-348">Назначьте разрешение **FullAccess** в сторонний почтовый ящик данных, чтобы администраторы или сотрудники по обеспечению соответствия требованиям могли открыть сторонний почтовый ящик данных в клиенте Outlook настольного компьютера; см. в руб. Управление [разрешениями для получателей.](https://go.microsoft.com/fwlink/p/?LinkId=692104)</span><span class="sxs-lookup"><span data-stu-id="27c2f-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>

3. <span data-ttu-id="27c2f-349">Включить следующие функции, связанные с соответствием требованиям для почтового ящика сторонних данных:</span><span class="sxs-lookup"><span data-stu-id="27c2f-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>

    - <span data-ttu-id="27c2f-350">Включить архивный почтовый ящик; см. [включить архивные почтовые ящики](enable-archive-mailboxes.md) и [включить неограниченный архив.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="27c2f-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="27c2f-351">Это позволяет освободить пространство для хранения в основном почтовом ящике путем настройки политики архивирования, которая перемещает сторонние элементы данных в архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="27c2f-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="27c2f-352">Это предоставляет неограниченное хранилище для сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-352">This provides you with unlimited storage for third-party data.</span></span>

    - <span data-ttu-id="27c2f-353">Поместите почтовый ящик сторонних данных на хранение для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="27c2f-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="27c2f-354">Вы также можете применить политику Microsoft 365 хранения в центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="27c2f-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="27c2f-355">При размещении этого почтового ящика на удержание сохраняются сторонние элементы данных (на неопределенный срок или на определенный срок) и они не будут выгрены из почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="27c2f-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="27c2f-356">См. один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="27c2f-356">See one of the following topics:</span></span>

      - [<span data-ttu-id="27c2f-357">Применение к почтовому ящику функции судебного удержания</span><span class="sxs-lookup"><span data-stu-id="27c2f-357">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)

      - [<span data-ttu-id="27c2f-358">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="27c2f-358">Learn about retention policies and retention labels</span></span>](retention.md)

    - <span data-ttu-id="27c2f-359">Включить ведение журнала аудита почтовых ящиков для владельца, делегата и администратора к сторонним почтовым ящикам данных; см. [включить аудит почтовых ящиков.](enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="27c2f-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="27c2f-360">Это позволяет проверять все действия, выполняемые любым пользователем, который имеет доступ к сторонним почтовым ящикам данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="27c2f-361">Шаг 3. Настройка поддержки сторонних данных для почтовых ящиков пользователей</span><span class="sxs-lookup"><span data-stu-id="27c2f-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="27c2f-362">Следующим шагом является настройка поддержки сторонних данных для почтовых ящиков пользователей.</span><span class="sxs-lookup"><span data-stu-id="27c2f-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="27c2f-363">Выполните эти задачи с Exchange центра администрирования или с помощью соответствующих Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27c2f-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>

1. <span data-ttu-id="27c2f-364">Включить архивный почтовый ящик для каждого пользователя; см. [включить архивные почтовые ящики](enable-archive-mailboxes.md) и [включить неограниченный архив.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="27c2f-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

2. <span data-ttu-id="27c2f-365">Поместите почтовые ящики пользователей в удержание судебного разбирательства или применяйте политику Microsoft 365 хранения; см. один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="27c2f-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span>

    - [<span data-ttu-id="27c2f-366">Применение к почтовому ящику функции судебного удержания</span><span class="sxs-lookup"><span data-stu-id="27c2f-366">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)

    - [<span data-ttu-id="27c2f-367">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="27c2f-367">Learn about retention policies and retention labels</span></span>](retention.md)

    <span data-ttu-id="27c2f-368">Как отмечалось ранее, при помещении почтовых ящиков на хранение можно указать длительность хранения элементов из источника сторонних данных или выбрать бессрочное хранение.</span><span class="sxs-lookup"><span data-stu-id="27c2f-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="27c2f-369">Шаг 4. Предоставление сведений партнеру</span><span class="sxs-lookup"><span data-stu-id="27c2f-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="27c2f-370">Последний шаг — предоставить партнеру следующую информацию, чтобы он настроит соединители для подключения к организации для импорта данных в почтовые ящики пользователей и в сторонний почтовый ящик данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span>

- <span data-ttu-id="27c2f-371">Конечная точка, используемая для подключения к службе Azure в Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="27c2f-371">The endpoint used to connect to the Azure service in Microsoft 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="27c2f-372">Учетные данные входа (Microsoft 365 пользователя и пароль) почтового ящика сторонних данных, созданного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="27c2f-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="27c2f-373">Эти учетные данные требуются соединителю партнера для доступа к элементам и их импорта в почтовые ящики пользователей и почтовый ящик со сторонними данными.</span><span class="sxs-lookup"><span data-stu-id="27c2f-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>

## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="27c2f-374">Шаг 5. Регистрация стороннего соединиттеля данных в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="27c2f-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="27c2f-375">С 30 сентября 2018 г. служба Azure в Microsoft 365 начнет использовать современную проверку подлинности в Exchange Online для проверки подлинности сторонних соединители данных, которые пытаются подключиться к организации для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-375">Starting September 30, 2018, the Azure service in Microsoft 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="27c2f-376">Причина этого изменения заключается в том, что современная проверка подлинности обеспечивает больше безопасности, чем текущий метод, основанный на списке разрешаний для сторонних соединитений, которые используют ранее описанную конечную точку для подключения к службе Azure.</span><span class="sxs-lookup"><span data-stu-id="27c2f-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="27c2f-377">Чтобы подключиться к Microsoft 365 с помощью нового метода современной проверки подлинности, администратор в организации должен дать согласие на регистрацию соединителя в качестве надежного приложения-службы в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27c2f-377">To enable a third-party data connector to connect to Microsoft 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="27c2f-378">Это делается, принимая запрос на разрешение, чтобы разрешить соединитеку получать доступ к данным организации в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27c2f-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="27c2f-379">После того как вы принимаете этот запрос, сторонний соединитатель данных добавляется в качестве корпоративного приложения для Azure Active Directory и представляется в качестве основного участника службы.</span><span class="sxs-lookup"><span data-stu-id="27c2f-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="27c2f-380">Дополнительные сведения о процессе согласия см. в см. [в деле Согласие администратора клиента.](/skype-sdk/trusted-application-api/docs/tenantadminconsent)</span><span class="sxs-lookup"><span data-stu-id="27c2f-380">For more information the consent process, see  [Tenant Admin Consent](/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="27c2f-381">Ниже зарегистрировано, как получить доступ и принять запрос на регистрацию соединитетеля:</span><span class="sxs-lookup"><span data-stu-id="27c2f-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="27c2f-382">Перейдите [на эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) и войдите с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="27c2f-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="27c2f-383">Отображается следующее диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="27c2f-383">The following dialog box is displayed.</span></span> <span data-ttu-id="27c2f-384">Вы можете расширить уходу, чтобы просмотреть разрешения, которые будут назначены соединитектору.</span><span class="sxs-lookup"><span data-stu-id="27c2f-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Отображается диалоговое окно запроса разрешений](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="27c2f-386">Нажмите кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="27c2f-386">Click **Accept**.</span></span>

<span data-ttu-id="27c2f-387">После того как вы принимаете запрос, отображается [портал Azure.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="27c2f-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="27c2f-388">Чтобы просмотреть список приложений для организации, **щелкните Azure Active Directory**  >  **Enterprise приложения.**</span><span class="sxs-lookup"><span data-stu-id="27c2f-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="27c2f-389">Соедините Microsoft 365 сторонних данных перечислены на Enterprise **приложениях.**</span><span class="sxs-lookup"><span data-stu-id="27c2f-389">The Microsoft 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27c2f-390">После 30 сентября 2018 г. сторонние данные больше не будут импортироваться в почтовые ящики в организации, если вы не зарегистрируете сторонний соединитатель данных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27c2f-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="27c2f-391">Обратите внимание, что существующие сторонние соединители данных (созданные до 30 сентября 2018 г.) также должны быть зарегистрированы в Azure Active Directory, следуя процедуре в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="27c2f-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="27c2f-392">Отмена согласия для стороннего соединиттеля данных</span><span class="sxs-lookup"><span data-stu-id="27c2f-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="27c2f-393">После того как организация согласится на запрос разрешений на регистрацию стороннего соединитетеля данных в Azure Active Directory, организация может отопросить это согласие в любое время.</span><span class="sxs-lookup"><span data-stu-id="27c2f-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="27c2f-394">Однако отмена согласия на подключение означает, что данные из стороннего источника данных больше не будут импортироваться в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27c2f-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Microsoft 365.</span></span>

<span data-ttu-id="27c2f-395">Чтобы отопустить согласие для стороннего соединителя данных, вы можете удалить приложение (удалив соответствующего директора службы) из Azure Active Directory с помощью лезвия **Enterprise** приложений на портале Azure или с помощью [remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) в Microsoft 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27c2f-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span></span> <span data-ttu-id="27c2f-396">Кроме того, в powerShell можно использовать [cmdlet Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27c2f-396">You can also use the [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>

## <a name="more-information"></a><span data-ttu-id="27c2f-397">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="27c2f-397">More information</span></span>

- <span data-ttu-id="27c2f-398">Как объяснялось ранее, элементы из сторонних источников данных импортируются в почтовые ящики Exchange в виде сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="27c2f-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="27c2f-399">Соединитель партнеров импортирует элемент с помощью схемы, требуемой Microsoft 365 API.</span><span class="sxs-lookup"><span data-stu-id="27c2f-399">The partner connector imports the item using a schema required by the Microsoft 365 API.</span></span> <span data-ttu-id="27c2f-400">В приведенной ниже таблице описываются свойства элемента из стороннего источника данных после его импорта в почтовый ящик Exchange в виде сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="27c2f-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="27c2f-401">В этой таблице также указывается, является ли свойство сообщения обязательным.</span><span class="sxs-lookup"><span data-stu-id="27c2f-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="27c2f-402">Обязательные свойства должны быть заполнены.</span><span class="sxs-lookup"><span data-stu-id="27c2f-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="27c2f-403">Если элемент отсутствует обязательное свойство, он не будет импортироваться в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27c2f-403">If an item is missing a mandatory property, it won't be imported to Microsoft 365.</span></span> <span data-ttu-id="27c2f-404">Процесс импорта возвращает сообщение об ошибке, объясняя, почему элемент не импортируется и какое свойство отсутствует.</span><span class="sxs-lookup"><span data-stu-id="27c2f-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>

    |<span data-ttu-id="27c2f-405">**Свойство сообщения**</span><span class="sxs-lookup"><span data-stu-id="27c2f-405">**Message property**</span></span>|<span data-ttu-id="27c2f-406">**Обязательный?**</span><span class="sxs-lookup"><span data-stu-id="27c2f-406">**Mandatory?**</span></span>|<span data-ttu-id="27c2f-407">**Описание**</span><span class="sxs-lookup"><span data-stu-id="27c2f-407">**Description**</span></span>|<span data-ttu-id="27c2f-408">**Пример значения**</span><span class="sxs-lookup"><span data-stu-id="27c2f-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="27c2f-409">**FROM**</span><span class="sxs-lookup"><span data-stu-id="27c2f-409">**FROM**</span></span> <br/> |<span data-ttu-id="27c2f-410">Да</span><span class="sxs-lookup"><span data-stu-id="27c2f-410">Yes</span></span>  <br/> |<span data-ttu-id="27c2f-411">Пользователь, который создал или отправил элемент из стороннего источника данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="27c2f-412">Соединититель партнеров пытается связать код пользователя с исходным элементом (например, с ручкой Twitter) на учетную запись пользователя для всех участников (пользователей в полях FROM и TO).</span><span class="sxs-lookup"><span data-stu-id="27c2f-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="27c2f-413">Копия сообщения будет импортирована в почтовый ящик каждого участника.</span><span class="sxs-lookup"><span data-stu-id="27c2f-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="27c2f-414">Если ни один из участников элемента не может быть соотносят с учетной записью пользователя, он будет импортироваться в сторонний почтовый ящик архива Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27c2f-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Microsoft 365.</span></span>  <br/> <br/> <span data-ttu-id="27c2f-415">Участник, идентифицированный как отправитель элемента, должен иметь активный почтовый ящик в организации, в которую он импортируется.</span><span class="sxs-lookup"><span data-stu-id="27c2f-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="27c2f-416">Если у отправителя нет активного почтового ящика, возвращается следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="27c2f-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="27c2f-417">**TO**</span><span class="sxs-lookup"><span data-stu-id="27c2f-417">**TO**</span></span> <br/> |<span data-ttu-id="27c2f-418">Да</span><span class="sxs-lookup"><span data-stu-id="27c2f-418">Yes</span></span>  <br/> |<span data-ttu-id="27c2f-419">Пользователь, получивший элемент, если это применимо к элементу в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="27c2f-420">**Тема**</span><span class="sxs-lookup"><span data-stu-id="27c2f-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="27c2f-421">Нет</span><span class="sxs-lookup"><span data-stu-id="27c2f-421">No</span></span>  <br/> |<span data-ttu-id="27c2f-422">Тема исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="27c2f-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="27c2f-423">**DATE**</span><span class="sxs-lookup"><span data-stu-id="27c2f-423">**DATE**</span></span> <br/> |<span data-ttu-id="27c2f-424">Да</span><span class="sxs-lookup"><span data-stu-id="27c2f-424">Yes</span></span>  <br/> |<span data-ttu-id="27c2f-425">Дата создания или публикации элемента в источнике данных клиента.</span><span class="sxs-lookup"><span data-stu-id="27c2f-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="27c2f-426">Например, в эту дату, когда было отобрано сообщение в Twitter.</span><span class="sxs-lookup"><span data-stu-id="27c2f-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="27c2f-427">**BODY**</span><span class="sxs-lookup"><span data-stu-id="27c2f-427">**BODY**</span></span> <br/> |<span data-ttu-id="27c2f-428">Нет</span><span class="sxs-lookup"><span data-stu-id="27c2f-428">No</span></span>  <br/> |<span data-ttu-id="27c2f-429">Содержимое сообщения или публикации.</span><span class="sxs-lookup"><span data-stu-id="27c2f-429">The contents of the message or post.</span></span> <span data-ttu-id="27c2f-430">Для некоторых источников данных содержимое этого свойства может совпадать с содержимым свойства **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="27c2f-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="27c2f-431">В процессе импорта соединитель партнеров пытается сохранить полную верность от источника контента.</span><span class="sxs-lookup"><span data-stu-id="27c2f-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="27c2f-432">По возможности в это свойство включаются файлы, рисунки или другое содержимое исходного элемента.</span><span class="sxs-lookup"><span data-stu-id="27c2f-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="27c2f-433">В противном случае содержимое исходного элемента включается в свойство **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="27c2f-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="27c2f-434">Содержимое этого свойства зависит от соединитетеля-партнера и от возможностей исходных платформ.</span><span class="sxs-lookup"><span data-stu-id="27c2f-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="27c2f-435">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="27c2f-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="27c2f-436">Нет</span><span class="sxs-lookup"><span data-stu-id="27c2f-436">No</span></span>  <br/> |<span data-ttu-id="27c2f-437">Если элемент в источнике данных (например, твит в Twitter или беседа с мгновенными сообщениями) имеет присоединенный файл или содержит изображения, подключение партнера сначала попытается включить вложения в свойство **BODY.**</span><span class="sxs-lookup"><span data-stu-id="27c2f-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="27c2f-438">Если это невозможно, оно добавляется в свойство \*\* ATTACHMENT \*\* .</span><span class="sxs-lookup"><span data-stu-id="27c2f-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="27c2f-439">К другим примерам вложений относятся отметки "Нравится" в Facebook, метаданные из источника контента, а также ответы на сообщение или публикацию.</span><span class="sxs-lookup"><span data-stu-id="27c2f-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="27c2f-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="27c2f-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="27c2f-441">Да</span><span class="sxs-lookup"><span data-stu-id="27c2f-441">Yes</span></span>  <br/> | <span data-ttu-id="27c2f-442">Это свойство с несколькими значениями, которое создается и заполняется соединитетелем партнеров.</span><span class="sxs-lookup"><span data-stu-id="27c2f-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="27c2f-443">Формат этого свойства  `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="27c2f-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="27c2f-444">(Это свойство должно начинаться с  `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="27c2f-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="27c2f-445">Этот формат похож на формат для  `IPM.NOTE.X` класса сообщений.) Это свойство содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="27c2f-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="27c2f-446">`Source`: Указывает сторонний источник данных; например, Twitter, Facebook или BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="27c2f-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="27c2f-447">`Event`: Указывает тип действий, выполняемых в стороном источнике данных, изготовив элементы; например, твит в Twitter или сообщение в Facebook.</span><span class="sxs-lookup"><span data-stu-id="27c2f-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="27c2f-448">Каждому источнику данных характерны свои события.</span><span class="sxs-lookup"><span data-stu-id="27c2f-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="27c2f-449">Одна из целей этого свойства — фильтрация элементов на основе типа события или источника данных, в котором создан элемент.</span><span class="sxs-lookup"><span data-stu-id="27c2f-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="27c2f-450">Например, при поиске с помощью функции обнаружения электронных данных можно найти все твиты, опубликованные определенным пользователем.</span><span class="sxs-lookup"><span data-stu-id="27c2f-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |

- <span data-ttu-id="27c2f-451">Когда элементы успешно импортируется в почтовые ящики в Microsoft 365, уникальный идентификатор возвращается вызываемой в рамках http-ответа.</span><span class="sxs-lookup"><span data-stu-id="27c2f-451">When items are successfully imported to mailboxes in Microsoft 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="27c2f-452">Этот идентификатор, называемый , можно использовать для последующих целей устранения неполадок партнерами для конечного отслеживания  `x-IngestionCorrelationID` элементов.</span><span class="sxs-lookup"><span data-stu-id="27c2f-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="27c2f-453">Партнерам рекомендуется фиксировать эту информацию и записывать ее в журнал соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="27c2f-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="27c2f-454">Пример HTTP-отклика, содержащего этот идентификатор:</span><span class="sxs-lookup"><span data-stu-id="27c2f-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT
    ```

- <span data-ttu-id="27c2f-455">Вы можете использовать средство поиска контента в центре безопасности и соответствия требованиям для поиска элементов, импортируемых в почтовые ящики из сторонних источников данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="27c2f-456">Для поиска этих импортируемых элементов можно использовать следующие пары свойств сообщений в поле ключевого слова для поиска контента.</span><span class="sxs-lookup"><span data-stu-id="27c2f-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>

  - <span data-ttu-id="27c2f-457">**`kind:externaldata`**. Используйте эту пару значений свойства для поиска всех типов сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-457">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="27c2f-458">Например, для поиска элементов, импортируемых из сторонних источников данных и содержащих слово "contoso" в свойстве Subject импортируемого элемента, используется запрос ключевого слова  `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="27c2f-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>

  - <span data-ttu-id="27c2f-459">**`itemclass:ipm.externaldata.<third-party data type>`**. Используйте эту пару значений свойства только для поиска конкретного типа сторонних данных.</span><span class="sxs-lookup"><span data-stu-id="27c2f-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="27c2f-460">Например, для поиска данных Facebook, которые содержат слово "contoso" в свойстве Subject, используется запрос по ключевому слову  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="27c2f-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span>

  <span data-ttu-id="27c2f-461">Полный список значений, которые можно использовать для типов сторонних данных для свойства, см. в материалах Use Content Search для поиска сторонних данных, импортируемых `itemclass` [в Microsoft 365.](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="27c2f-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>

   <span data-ttu-id="27c2f-462">Дополнительные сведения об использовании средства "Поиск контента" и создании поисковых запросов по ключевым словам см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="27c2f-462">For more information about using Content Search and creating keyword search queries, see:</span></span>

  - [<span data-ttu-id="27c2f-463">Поиск контента</span><span class="sxs-lookup"><span data-stu-id="27c2f-463">Content Search</span></span>](content-search.md)

  - [<span data-ttu-id="27c2f-464">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="27c2f-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)