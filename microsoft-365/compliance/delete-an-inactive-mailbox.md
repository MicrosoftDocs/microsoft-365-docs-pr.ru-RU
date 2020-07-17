---
title: Удаление неактивного почтового ящика
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Если вы больше не хотите сохранять содержимое неактивного почтового ящика Microsoft 365, вы можете окончательно удалить неактивный почтовый ящик.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817898"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="dfd5c-103">Удаление неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="dfd5c-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="dfd5c-104">Неактивный почтовый ящик используется для хранения электронной почты бывшего сотрудника после увольнения.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="dfd5c-105">Если больше нет необходимости хранить контент неактивного почтового ящика, можно окончательно удалить его, выключив режим хранения.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="dfd5c-106">Кроме того, возможно, что к неактивному почтовому ящику применяются несколько инцидентов удержания.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="dfd5c-107">Например, неактивный почтовый ящик может находиться в режиме хранения для судебного разбирательства или хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="dfd5c-108">Кроме того, политика хранения (созданная в центре безопасности и соответствия требованиям в Office 365 или Microsoft 365) может быть применена к неактивному почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="dfd5c-109">Необходимо удалить все удержания и политики хранения из неактивного почтового ящика, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="dfd5c-110">После удаления политик хранения и хранения неактивный почтовый ящик помечается для удаления и безвозвратно удаляется после его обработки.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dfd5c-111">Так как мы будем хранить содержимое почтового ящика разными способами, мы сообщаем выбытие на месте в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="dfd5c-112">Это означает, что для создания неактивного почтового ящика следует использовать удержания и политики хранения для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="dfd5c-113">Начиная с 1 июля, 2020 вы не сможете создавать новые удержания на месте в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="dfd5c-114">Но вы по-прежнему можете изменить срок хранения на месте, включенный для неактивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="dfd5c-115">Однако, начиная с 1 октября 2020, вы не сможете изменить срок хранения.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="dfd5c-116">Удаление неактивного почтового ящика позволит удалить удержание на месте.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="dfd5c-117">Существующие Неактивные почтовые ящики, которые включены в удержание на месте, будут сохранены до тех пор, пока не будет удалено удержание.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="dfd5c-118">Для получения дополнительных сведений о прекращении удержания на месте, ознакомьтесь со статьей [выбытие средств прежних версий электронных данных](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="dfd5c-119">Описание того, что происходит после удаления инцидента удержания для неактивного почтового ящика, см. в статье [Дополнительные сведения](#more-information).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="dfd5c-120">Перед удалением неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="dfd5c-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="dfd5c-121">Чтобы удалить удержание для судебного разбирательства из неактивного почтового ящика, необходимо использовать Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="dfd5c-122">Вы не можете сделать этого в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="dfd5c-123">Пошаговые инструкции приведены [в статье подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="dfd5c-124">Чтобы удалить удержание на месте из неактивного почтового ящика, можно использовать Exchange Online PowerShell или центр администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-124">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="dfd5c-125">Вы можете скопировать содержимое неактивного почтового ящика в другой почтовый ящик, прежде чем удалить инцидент удержания и сам почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-125">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="dfd5c-126">Дополнительные сведения см. [в статье восстановление неактивного почтового ящика в Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-126">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="dfd5c-127">Если удалить политику хранения или хранения из неактивного почтового ящика и срок хранения обратимо удаленного почтового ящика для почтового ящика, почтовый ящик будет окончательно удален.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-127">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="dfd5c-128">После удаления его невозможно будет восстановить.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-128">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="dfd5c-129">Прежде чем удалять инцидент удержания, убедитесь, что вам больше не требуется содержимое почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-129">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="dfd5c-130">Если вы захотите повторно активировать неактивный почтовый ящик, его можно восстановить.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-130">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="dfd5c-131">Дополнительные сведения см. [в статье восстановление неактивного почтового ящика в Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-131">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="dfd5c-132">Дополнительные сведения о неактивных почтовых ящиках приведены [в статье Неактивные почтовые ящики в Office 365](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="dfd5c-132">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="dfd5c-133">Этап 1. Определение инцидентов удержания для неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="dfd5c-133">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="dfd5c-134">Как отмечалось ранее, хранение для судебного разбирательства, хранение на месте или политика хранения могут быть размещены на неактивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-134">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="dfd5c-135">Первый шаг состоит в определении инцидентов удержания неактивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-135">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="dfd5c-136">Выполните следующую команду, чтобы отобразить сведения об удержании для всех неактивных почтовых ящиков в организации.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-136">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="dfd5c-p107">Значение **True** свойства **LitigationHoldEnabled** указывает, что неактивный почтовый ящик находится на хранении для судебного разбирательства. Если для неактивного почтового ящика включено хранение на месте, GUID удержания отображается как значение свойства **InPlaceHolds**. Например, в следующих результатах для двух неактивных почтовых ящиков видно, что хранение для судебного разбирательства включено для ящика Ann Beebe и что два инцидента хранения на месте применены к ящику Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p107">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="dfd5c-140">Если для неактивного почтового ящика применено множество инцидентов хранения на месте, будут показаны не все идентификаторы GUID хранения.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-140">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="dfd5c-141">Для отображения всех идентификаторов GUID хранения на месте можно выполнить следующую команду:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="dfd5c-141">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="dfd5c-142">Действие 2. Удаление инцидента удержания неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="dfd5c-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="dfd5c-p109">После определения типа удержания или количества инцидентов удержания для неактивного почтового ящика следующий шаг  снятие удержаний. Как указывалось ранее, вам необходимо удалить все инциденты удержания, чтобы окончательно удалить неактивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p109">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="dfd5c-145">Отключение хранения для судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="dfd5c-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="dfd5c-p110">Как было сказано выше, необходимо отключить режим хранения для судебного разбирательства для неактивного почтового ящика с помощью Windows PowerShell. Для этого не может использоваться EAC. Выполните следующую команду, чтобы отключить хранение для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p110">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="dfd5c-p111">Лучший способ идентификации неактивного почтового ящика — использовать его различающееся имя или идентификатор GUID Exchange. Используя одно из этих значений, вы не укажете по ошибке неверный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p111">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="dfd5c-151">Отключение хранения на месте</span><span class="sxs-lookup"><span data-stu-id="dfd5c-151">Remove In-Place Holds</span></span>

 <span data-ttu-id="dfd5c-152">Отключить хранение на месте для неактивного почтового ящика можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="dfd5c-152">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="dfd5c-153">**Удаление объекта хранения на месте** Если неактивный почтовый ящик, который необходимо окончательно удалить, является единственным исходным почтовым ящиком для хранения на месте, можно просто удалить объект хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-153">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="dfd5c-p112">Перед этим необходимо отключить хранение на месте. При попытке удаления объекта с включенным хранением на месте появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p112">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="dfd5c-156">**Удалить неактивный почтовый ящик как исходный почтовый ящик хранения на месте**. Если вы хотите сохранить другие исходные почтовые ящики для хранения на месте, можно удалить неактивный почтовый ящик из списка исходных почтовых ящиков и сохранить объект хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-156">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="dfd5c-157">Использование Центра администрирования Exchange для отключения хранения на месте</span><span class="sxs-lookup"><span data-stu-id="dfd5c-157">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="dfd5c-p113">Если вы знаете имя хранения на месте, которое требуется удалить, можно перейти к следующему шагу. В противном случае выполните следующую команду, чтобы получить имя хранения на месте, назначенного неактивному почтовому ящику, который требуется удалить. Используйте GUID хранения на месте, полученный в [Действие 1. Определение инцидентов удержания для неактивного почтового ящика](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p113">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="dfd5c-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="dfd5c-162">Выберите удержание на месте, которое нужно удалить, а затем нажмите кнопку **изменить** ![ значок редактирования ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="dfd5c-162">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="dfd5c-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="dfd5c-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="dfd5c-165">В окне предупреждения щелкните **Да**, чтобы удалить инцидент хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-165">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="dfd5c-166">Удаление хранения на месте с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfd5c-166">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="dfd5c-p114">Создайте переменную, содержащую свойства инцидента хранения на месте, который требуется удалить. Используйте GUID хранения на месте, полученный в [Действие 1. Определение инцидентов удержания для неактивного почтового ящика](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p114">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="dfd5c-169">Отключите хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-169">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="dfd5c-170">Затем удалите инцидент хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-170">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="dfd5c-171">Использование Центра администрирования Exchange для отключения хранения на месте неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="dfd5c-171">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="dfd5c-p115">Если вы знаете имя инцидента хранения на месте для неактивного почтового ящика, можно перейти к следующему шагу. В противном случае выполните следующую команду, чтобы получить имя. Используйте GUID хранения на месте, полученный в [Действие 1. Определение инцидентов удержания для неактивного почтового ящика](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p115">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="dfd5c-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="dfd5c-176">Выберите удержание на месте для неактивного почтового ящика, а затем щелкните **изменить** ![ значок редактирования ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="dfd5c-176">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="dfd5c-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="dfd5c-178">В списке исходных почтовых ящиков щелкните имя неактивного почтового ящика, который требуется удалить, а затем нажмите кнопку **Удалить**![Значок "Удалить"](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-178">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="dfd5c-p116">Чтобы сохранить изменения, нажмите кнопку **Сохранить**. Появится сообщение о том, что операция успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p116">Click **Save** to save the change. A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="dfd5c-181">Повторите шаги с 1 по 6, чтобы удалить другие инциденты хранения на месте для неактивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-181">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="dfd5c-182">Удаление неактивного почтового ящика из хранения на месте с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfd5c-182">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="dfd5c-183">Если инцидент хранения на месте содержит большое количество исходных почтовых ящиков, возможно, что неактивный почтовый ящик не будет показан на странице **Источники** в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="dfd5c-184">При редактировании инцидента хранения на месте на странице **Источники** отображаются до 3000 почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="dfd5c-185">Если неактивный почтовый ящик не указан на странице **источники** , можно удалить его из удержания на месте с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="dfd5c-p118">Создайте переменную, содержащую свойства инцидента хранения на месте, примененного к неактивному почтовому ящику. Используйте GUID хранения на месте, полученный в [Действие 1. Определение инцидентов удержания для неактивного почтового ящика](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p118">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="dfd5c-188">Убедитесь, что неактивный почтовый ящик указан как исходный почтовый ящик для хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-188">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="dfd5c-189">**Примечание:** Свойство *Sources* хранения на месте определяет исходные почтовые ящики по их свойствам *legacyExchangeDN* .</span><span class="sxs-lookup"><span data-stu-id="dfd5c-189">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="dfd5c-190">Поскольку это свойство уникально идентифицирует неактивные почтовые ящики, использование свойства *Sources* хранения на месте предотвращает удаление неверного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-190">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="dfd5c-191">Это также позволяет избежать проблем, если у двух почтовых ящиков одинаковый псевдоним или SMTP-адрес.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-191">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="dfd5c-p120">Удалите неактивный почтовый ящик из списка исходных почтовых ящиков в переменной. Обязательно используйте свойство **LegacyExchangeDN** неактивного почтового ящика, возвращаемое командой на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p120">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="dfd5c-194">Например, следующая команда удаляет неактивный почтовый ящик для пользователя Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-194">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="dfd5c-195">Убедитесь, что неактивный почтовый ящик удален из списка исходных почтовых ящиков в переменной.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-195">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="dfd5c-196">Измените инцидент хранения на месте, используя обновленный список исходных почтовых ящиков, в который не входит неактивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-196">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="dfd5c-197">Убедитесь, что неактивный почтовый ящик удален из списка исходных почтовых ящиков для хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-197">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="dfd5c-198">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="dfd5c-198">More information</span></span>

- <span data-ttu-id="dfd5c-p121">**Неактивный почтовый ящик  это тип обратимо удаленного почтового ящика.** В Exchange Online обратимо удаленный почтовый ящик  это удаленный ящик, который можно восстановить в течение определенного периода. Срок хранения обратимо удаленного почтового ящика в Exchange Online составляет 30 дней. Это значит, что почтовый ящик можно восстановить в течение 30 дней после обратимого удаления. Через 30 дней обратимо удаленный почтовый ящик помечается для окончательного удаления без возможности восстановления.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p121">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="dfd5c-204">**Что происходит после удаления удержания на неактивном почтовом ящике?**</span><span class="sxs-lookup"><span data-stu-id="dfd5c-204">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="dfd5c-205">Почтовый ящик рассматривается как другие обратимо удаленные почтовые ящики и помечается для окончательного удаления после истечения 30-дневного периода хранения с обратимым удаленным почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-205">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="dfd5c-206">Этот период хранения начинается с даты первого совершения почтовых ящиков в неактивном состоянии.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-206">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="dfd5c-207">Эта дата известна как дата обратимого удаления, которая соответствует дате удаления соответствующей учетной записи пользователя или при удалении почтового ящика Exchange Online с помощью командлета **Remove-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="dfd5c-207">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="dfd5c-208">Дата обратимого удаления не является датой, на которую вы удаляете удержание.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-208">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="dfd5c-p123">**Неактивный почтовый ящик окончательно удаляется сразу после снятия с удержания?** Если неактивный почтовый ящик был обратимо удален более 30 дней назад, он не будет удален окончательно сразу после снятия с удержания. Почтовый ящик будет отмечен для окончательного удаления и удален при следующей обработке.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-p123">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="dfd5c-212">**Как период хранения обратимо удаленного почтового ящика влияет на неактивные почтовые ящики?**</span><span class="sxs-lookup"><span data-stu-id="dfd5c-212">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="dfd5c-213">Если дата удаления неактивного почтового ящика превышает 30 дней до даты, когда была удалена удержание, почтовый ящик помечается для постоянного удаления.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-213">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="dfd5c-214">Но если дата обратимого удаления неактивного почтового ящика попадает в последние 30 дней и вы удалите инцидент удержания, почтовый ящик можно восстановить до истечения срока хранения обратимо удаленного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-214">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="dfd5c-215">Дополнительные сведения см. [в статье Удаление или восстановление почтовых ящиков пользователей в Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-215">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="dfd5c-216">После истечения срока хранения обратимо удаленных почтовых ящиков вы можете восстановить неактивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-216">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="dfd5c-217">Дополнительные сведения см. [в статье восстановление неактивного почтового ящика в Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="dfd5c-217">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="dfd5c-218">**Как отобразить сведения о неактивном почтовом ящике после снятия с удержания?**</span><span class="sxs-lookup"><span data-stu-id="dfd5c-218">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="dfd5c-219">После удаления удержания и возврата неактивного почтового ящика обратно в обратимо удаленный почтовый ящик он не будет возвращен с помощью параметра *инактивемаилбоксонли* командлета **Get-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="dfd5c-219">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="dfd5c-220">Однако вы можете отобразить сведения о почтовом ящике с помощью команды **Get-Mailbox -SoftDeletedMailbox**.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-220">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="dfd5c-221">Например:</span><span class="sxs-lookup"><span data-stu-id="dfd5c-221">For example:</span></span> 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  <span data-ttu-id="dfd5c-222">В приведенном выше примере свойство *WhenSoftDeleted* определяет дату обратимого удаления, которая в данном примере составляет 30 октября 2014 г.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-222">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="dfd5c-223">Если этот Обратимо удаленный почтовый ящик ранее был неактивным почтовым ящиком, для которого было удалено удержание, оно будет безвозвратно удалено в течение 30 дней после значения свойства *WhenSoftDeleted* .</span><span class="sxs-lookup"><span data-stu-id="dfd5c-223">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="dfd5c-224">В этом случае почтовый ящик окончательно удаляется после 30 ноября 2014 г.</span><span class="sxs-lookup"><span data-stu-id="dfd5c-224">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

