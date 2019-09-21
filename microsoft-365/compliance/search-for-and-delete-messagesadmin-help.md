---
title: Поиск и удаление сообщений (справка администратора)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: Администраторы могут использовать командлет Search-Mailbox для поиска и удаления сообщений в почтовых ящиках пользователей.
ms.openlocfilehash: bb375bc7a3273e78acb44807e51a1cee0261e7af
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090769"
---
# <a name="search-for-and-delete-messages---admin-help"></a><span data-ttu-id="f28a8-103">Поиск и удаление сообщений (справка администратора)</span><span class="sxs-lookup"><span data-stu-id="f28a8-103">Search for and delete messages - Admin help</span></span>
  
<span data-ttu-id="f28a8-104">Администраторы могут использовать командлет **Search-Mailbox** для поиска и удаления сообщений в почтовых ящиках пользователей.</span><span class="sxs-lookup"><span data-stu-id="f28a8-104">Administrators can use the **Search-Mailbox** cmdlet to search user mailboxes and then delete messages from a mailbox.</span></span> 
  
<span data-ttu-id="f28a8-p101">Чтобы найти и одновременно удалить сообщения, выполните командлет **Search-Mailbox** с параметром  _DeleteContent_. Однако при этом вы не сможете предварительно просмотреть результаты поиска или создать журнал сообщений, которые будут возвращены в результатах поиска. Таким образом, вы можете случайно удалить сообщения, которые не хотели удалять. Чтобы просмотреть журнал сообщений в результатах поиска перед их удалением, выполните командлет **Search-Mailbox** с параметром  _LogOnly_.</span><span class="sxs-lookup"><span data-stu-id="f28a8-p101">To search and delete messages in one step, run the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. However, when you do this, you can't preview search results or generate a log of messages that will be returned by the search, and you may inadvertently delete messages that you didn't intend to. To preview a log of the messages found in the search before they're deleted, run the **Search-Mailbox** cmdlet with the  _LogOnly_ switch.</span></span> 
  
<span data-ttu-id="f28a8-p102">В целях дополнительной защиты данных можно предварительно скопировать сообщения в другой почтовый ящик с помощью параметров  _TargetMailbox_ и  _TargetFolder_. Благодаря этому сохранится копия удаленных сообщений на случай необходимости доступа к ним в будущем.</span><span class="sxs-lookup"><span data-stu-id="f28a8-p102">As an additional safeguard, you can first copy the messages to another mailbox by using the  _TargetMailbox_ and  _TargetFolder_ parameters. By doing this, you retain a copy of the deleted messages in case you need to access them again.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="f28a8-110">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f28a8-110">Before you begin</span></span>

- <span data-ttu-id="f28a8-p103">Предполагаемое время выполнения: 10 минут. Фактическое время зависит от размера почтового ящика и запроса поиска.</span><span class="sxs-lookup"><span data-stu-id="f28a8-p103">Estimated time to complete: 10 minutes. The actual time may vary depending on the size of the mailbox and the search query.</span></span>
    
- <span data-ttu-id="f28a8-p104">Для выполнения этих процедур нельзя использовать Центр администрирования Exchange. Необходимо использовать командную консоль.</span><span class="sxs-lookup"><span data-stu-id="f28a8-p104">You can't use the Exchange admin center (EAC) to perform these procedures. You must use the Shell.</span></span>
    
- <span data-ttu-id="f28a8-115">Для поиска и удаления сообщений в почтовых ящиках пользователей необходимы обе указанные ниже роли управления.</span><span class="sxs-lookup"><span data-stu-id="f28a8-115">You need to be assigned both of the following management roles to search for and delete messages in users' mailboxes:</span></span>
    
  - <span data-ttu-id="f28a8-116">**Поиск в почтовом ящике**— эта роль позволяет искать сообщения в нескольких почтовых ящиках в Организации.</span><span class="sxs-lookup"><span data-stu-id="f28a8-116">**Mailbox Search**- This role allows you to search for messages across multiple mailboxes in your organization.</span></span> <span data-ttu-id="f28a8-117">Администраторы не назначают эту роль по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f28a8-117">Administrators aren't assigned this role by default.</span></span> <span data-ttu-id="f28a8-118">Чтобы назначить себе эту роль, чтобы можно было выполнять поиск в почтовых ящиках, добавьте себя в качестве участника группы ролей "Управление обнаружением".</span><span class="sxs-lookup"><span data-stu-id="f28a8-118">To assign yourself this role so that you can search mailboxes, add yourself as a member of the Discovery Management role group.</span></span> <span data-ttu-id="f28a8-119">Ознакомьтесь со статьей [Добавление пользователя в группу ролей Управление обнаружением](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span><span class="sxs-lookup"><span data-stu-id="f28a8-119">See [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span></span>
    
  - <span data-ttu-id="f28a8-120">**Экспорт импорта почтовых ящиков** — эта роль позволяет удалять сообщения из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="f28a8-120">**Mailbox Import Export** - This role allows you to delete messages from a user's mailbox.</span></span> <span data-ttu-id="f28a8-121">По умолчанию эта роль группе ролей не назначена.</span><span class="sxs-lookup"><span data-stu-id="f28a8-121">By default, this role isn't assigned to any role group.</span></span> <span data-ttu-id="f28a8-122">Для удаления сообщений из почтовых ящиков пользователей следует добавить роль "Импорт и экспорт почтовых ящиков" в группу ролей "Управление организацией".</span><span class="sxs-lookup"><span data-stu-id="f28a8-122">To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="f28a8-123">Дополнительные сведения можно найти в разделе "Добавление роли в группу ролей" в разделе [Управление группами ролей](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f28a8-123">For more information, see the "Add a role to a role group" section in [Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span></span> 
    
- <span data-ttu-id="f28a8-p107">Если для почтового ящика, из которого необходимо удалить сообщения, включена функция восстановления одного элемента, сначала необходимо отключить ее. Дополнительные сведения см. в статье [Включение или отключение восстановления одного элемента в почтовом ящике](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span><span class="sxs-lookup"><span data-stu-id="f28a8-p107">If the mailbox from which you want to delete messages has single item recovery enabled, you must first disable the feature. For more information, see [Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span></span>
    
- <span data-ttu-id="f28a8-126">Если почтовый ящик, из которого необходимо удалить сообщения, помещен на хранение, рекомендуем обратиться в отдел управления записями или юридический отдел, прежде чем отключать хранение и удалять содержимое почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="f28a8-126">If the mailbox from which you want to delete messages is placed on hold, we recommend that you check with your records management or legal department before removing the hold and deleting the mailbox content.</span></span> <span data-ttu-id="f28a8-127">После получения утверждения выполните действия, описанные в разделе [Очистка папки "элементы с возможностью восстановления"](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span><span class="sxs-lookup"><span data-stu-id="f28a8-127">After you obtain approval, follow the steps listed in the topic [Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span></span>
    
- <span data-ttu-id="f28a8-p109">С помощью командлета **Search-Mailbox** можно выполнить поиск не более чем в 10 000 почтовых ящиков. Если в вашей организации Exchange Online более 10 000 почтовых ящиков, вы можете использовать функцию поиска соответствия (или связанный с ней командлет **New-ComplianceSearch** ), чтобы выполнять поиск в неограниченном количестве почтовых ящиков. Затем вы можете удалить сообщения, возвращенные поиском соответствия, с помощью командлета **New-ComplianceSearchAction**. Дополнительные сведения см. в статье [Поиск и удаление сообщений электронной почты из организации Office 365](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span><span class="sxs-lookup"><span data-stu-id="f28a8-p109">You can search a maximum of 10,000 mailboxes using the **Search-Mailbox** cmdlet. If you're an Exchange Online organization and have more than 10,000 mailboxes, you can use the Compliance Search feature (or the corresponding **New-ComplianceSearch** cmdlet) to search an unlimited number of mailboxes. Then you can use the **New-ComplianceSearchAction** cmdlet to delete the messages returned by a compliance search. For more information, see [Search for and delete email messages from your Office 365 organization](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span></span>
    
- <span data-ttu-id="f28a8-p110">Если вы включите поисковый запрос (используя параметр  *SearchQuery*  ), командлет **Search-Mailbox** вернет максимум 10 000 элементов. Поэтому, чтобы удалить более 10 000 элементов, может потребоваться выполнить команду **Search-Mailbox** несколько раз.</span><span class="sxs-lookup"><span data-stu-id="f28a8-p110">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
    
- <span data-ttu-id="f28a8-134">При запуске командлета **Search-Mailbox** поиск также выполняется в архивном почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="f28a8-134">The user's archive mailbox will also be searched when you run the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="f28a8-135">Аналогично, при использовании командлета **Search-Mailbox** с параметром  _DeleteContent_ удаляются элементы в основном архивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="f28a8-135">Similarly, items in the primary archive mailbox will be deleted when you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch.</span></span> <span data-ttu-id="f28a8-136">Чтобы этого не произошло, можно включить параметр  *DoNotIncludeArchive*  .</span><span class="sxs-lookup"><span data-stu-id="f28a8-136">To prevent this, you can include the  *DoNotIncludeArchive*  switch.</span></span>
    
## <a name="search-messages-and-log-the-search-results"></a><span data-ttu-id="f28a8-137">Поиск сообщений и ведение журнала результатов</span><span class="sxs-lookup"><span data-stu-id="f28a8-137">Search messages and log the search results</span></span>

<span data-ttu-id="f28a8-p112">В этом примере в почтовом ящике пользователя April Stewart выполняется поиск сообщений, содержащих фразу "Your bank statement" в теме; результаты поиска записываются в журнал в папке SearchAndDeleteLog почтового ящика администратора. Сообщения не копируются в целевой почтовый ящик и не удаляются из него.</span><span class="sxs-lookup"><span data-stu-id="f28a8-p112">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and logs the search results in the SearchAndDeleteLog folder of the administrator's mailbox. Messages aren't copied to or deleted from the target mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="f28a8-140">В этом примере во всех почтовых ящиках организации выполняется поиск сообщений с любыми типами вложенных файлов, содержащих слово Trojan в имени. При этом сообщение журнала отправляется в почтовый ящик администратора.</span><span class="sxs-lookup"><span data-stu-id="f28a8-140">This example searches all mailboxes in the organization for messages that have any type of attached file that contains the word "Trojan" in the filename and sends a log message to the administrator's mailbox.</span></span>
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="f28a8-141">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span><span class="sxs-lookup"><span data-stu-id="f28a8-141">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
 
## <a name="search-and-delete-messages"></a><span data-ttu-id="f28a8-142">Поиск и удаление сообщений</span><span class="sxs-lookup"><span data-stu-id="f28a8-142">Search and delete messages</span></span>

<span data-ttu-id="f28a8-p113">В этом примере в почтовом ящике пользователя April Stewart выполняется поиск сообщений, содержащих фразу "Your bank statement" в теме; сообщения удаляются из исходного почтового ящика без копирования результатов поиска в другую папку. Как было указано ранее, вам должна быть назначена роль управления "Экспорт и импорт почтового ящика", чтобы удалять сообщения из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="f28a8-p113">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and deletes the messages from the source mailbox without copying the search results to another folder. As previously explained, you need to be assigned the Mailbox Import Export management role to delete messages from a user's mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f28a8-p114">При использовании командлета **Search-Mailbox** с параметром  _DeleteContent_ сообщения окончательно удаляются из исходного почтового ящика. Перед окончательным удалением сообщений рекомендуется использовать параметр  _LogOnly_ для создания журнала сообщений, найденных в результатах поиска, или скопировать эти сообщения в другой почтовый ящик перед их удалением из исходного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="f28a8-p114">When you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch, messages are permanently deleted from the source mailbox. Before you permanently delete messages, we recommend that you either use the  _LogOnly_ switch to generate a log of the messages found in the search before they're deleted or copy the messages to another mailbox before deleting them from the source mailbox.</span></span> 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

<span data-ttu-id="f28a8-147">В этом примере в почтовом ящике пользователя April Stewart выполняется поиск сообщений, содержащих фразу "Your bank statement" в теме; результаты поиска копируются в папку AprilStewart-DeletedMessages почтового ящика BackupMailbox, а сообщения удаляются из почтового ящика April.</span><span class="sxs-lookup"><span data-stu-id="f28a8-147">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field, copies the search results to the folder AprilStewart-DeletedMessages in the mailbox BackupMailbox, and deletes the messages from April's mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

<span data-ttu-id="f28a8-148">В этом примере во всех почтовых ящиках организации выполняется поиск сообщений, содержащих строчку "Download this file" в теме, после чего эти сообщения безвозвратно удаляются.</span><span class="sxs-lookup"><span data-stu-id="f28a8-148">This example searches all mailboxes in the organization for messages with the subject line "Download this file", and then permanently deletes them.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

<span data-ttu-id="f28a8-149">Подробные сведения о синтаксисе и параметрах см. в разделе [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span><span class="sxs-lookup"><span data-stu-id="f28a8-149">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>

## <a name="using-the--loglevel-full-parameter"></a><span data-ttu-id="f28a8-150">Использование параметра -LogLevel Full</span><span class="sxs-lookup"><span data-stu-id="f28a8-150">Using the -LogLevel Full parameter</span></span>

<span data-ttu-id="f28a8-p115">В некоторых предыдущих примерах параметр  _LogLevel_ со значением  `Full` используется для записи подробной информации о результатах, возвращаемых командлетом **Search-Mailbox**. Если этот параметр включен, в почтовый ящик, указанный параметром  _TargetMailbox_, отправляется сообщение с файлом журнала (Search Results.csv), который будет находиться в папке, указанной параметром  _TargetFolder_. Файл журнала содержит по одной строке для каждого сообщения, включенного в результаты поиска при выполнении командлета **Search-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="f28a8-p115">In some of the previous examples, the  _LogLevel_ parameter, with the  `Full` value is used to log detailed information about the results returned by the **Search-Mailbox** cmdlet. When you included this parameter, an email message is created and sent to the mailbox specified by the  _TargetMailbox_ parameter. The log file (which is a CSV-formatted file named Search Results.csv) is attached to this email message, and will be located in the folder specified by the  _TargetFolder_ parameter. The log file contains a row for each message that's included in the search results when you run the **Search-Mailbox** cmdlet.</span></span> 
