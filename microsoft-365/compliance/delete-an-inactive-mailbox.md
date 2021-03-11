---
title: Удаление неактивного почтового ящика
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Если вам больше не нужно сохранять содержимое неактивного почтового ящика Microsoft 365, вы можете навсегда удалить неактивный почтовый ящик.
ms.openlocfilehash: d5acccbf37ee5b6958d282de14edafc0b9b00182
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717578"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="41cb6-103">Удаление неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="41cb6-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="41cb6-104">Неактивный почтовый ящик используется для сохранения электронной почты бывшего сотрудника после того, как он покинет организацию.</span><span class="sxs-lookup"><span data-stu-id="41cb6-104">An inactive mailbox is used to preserve a former employee's email after they leave your organization.</span></span> <span data-ttu-id="41cb6-105">Если больше нет необходимости хранить контент неактивного почтового ящика, можно окончательно удалить его, выключив режим хранения.</span><span class="sxs-lookup"><span data-stu-id="41cb6-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="41cb6-106">Кроме того, возможно, что к неактивному почтовому ящику применяются несколько инцидентов удержания.</span><span class="sxs-lookup"><span data-stu-id="41cb6-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="41cb6-107">Например, неактивный почтовый ящик может находиться в режиме хранения для судебного разбирательства или хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="41cb6-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="41cb6-108">Кроме того, к неактивному почтовому ящику может применяться политика хранения (созданная в центре безопасности и соответствия требованиям в Office 365 или Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="41cb6-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="41cb6-109">Чтобы удалить его, необходимо удалить все политики хранения и хранения из неактивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="41cb6-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="41cb6-110">После удаления политик хранения и хранения неактивный почтовый ящик помечается для удаления и удаляется после обработки.</span><span class="sxs-lookup"><span data-stu-id="41cb6-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="41cb6-111">По мере того как мы продолжаем инвестировать в различные способы сохранения контента почтовых ящиков, мы объявляем об уходе In-Place хранит в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="41cb6-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="41cb6-112">Это означает, что для создания неактивного почтового ящика необходимо использовать политики хранения и хранения для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="41cb6-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="41cb6-113">С 1 июля 2020 г. вы не сможете создавать новые In-Place в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41cb6-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="41cb6-114">Но вы все равно сможете изменить продолжительность удержания In-Place, размещенного на неактивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="41cb6-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="41cb6-115">Однако с 1 октября 2020 г. вы не сможете изменить продолжительность удержания.</span><span class="sxs-lookup"><span data-stu-id="41cb6-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="41cb6-116">Удалить неактивный почтовый ящик можно только путем удаления In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="41cb6-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="41cb6-117">Существующие неактивные почтовые ящики, In-Place удержание, будут сохраняться до удаления удержания.</span><span class="sxs-lookup"><span data-stu-id="41cb6-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="41cb6-118">Дополнительные сведения об уходе из In-Place содержится в см. в In-Place устаревших средств [eDiscovery.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="41cb6-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="41cb6-119">Описание того, что происходит после удаления инцидента удержания для неактивного почтового ящика, см. в статье [Дополнительные сведения](#more-information).</span><span class="sxs-lookup"><span data-stu-id="41cb6-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="41cb6-120">Перед удалением неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="41cb6-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="41cb6-121">Чтобы удалить удержание судебного разбирательства из неактивного почтового ящика, необходимо использовать Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41cb6-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="41cb6-122">Вы не можете сделать этого в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="41cb6-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="41cb6-123">Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="41cb6-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="41cb6-124">Вы можете скопировать содержимое неактивного почтового ящика в другой почтовый ящик, прежде чем удалить инцидент удержания и сам почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="41cb6-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="41cb6-125">Дополнительные сведения см. [в материале Восстановление неактивного почтового ящика в Office 365.](restore-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="41cb6-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="41cb6-126">Если вы удалите политику удержания или хранения из неактивного почтового ящика, а срок хранения почтового ящика с мягким удалением для почтового ящика истек, почтовый ящик будет окончательно удален.</span><span class="sxs-lookup"><span data-stu-id="41cb6-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="41cb6-127">После удаления его невозможно будет восстановить.</span><span class="sxs-lookup"><span data-stu-id="41cb6-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="41cb6-128">Прежде чем удалять инцидент удержания, убедитесь, что вам больше не требуется содержимое почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="41cb6-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="41cb6-129">Если вы хотите активировать неактивный почтовый ящик, его можно восстановить.</span><span class="sxs-lookup"><span data-stu-id="41cb6-129">If you want to reactivate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="41cb6-130">Дополнительные сведения [см. в материале Восстановление неактивного почтового ящика в Office 365.](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="41cb6-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="41cb6-131">Дополнительные сведения о неактивных почтовых ящиках см. в списке Неактивные почтовые [ящики в Office 365.](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="41cb6-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="41cb6-132">Этап 1. Определение инцидентов удержания для неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="41cb6-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="41cb6-133">Как уже говорилось ранее, политика удержания, In-Place хранения или хранения может быть размещена на неактивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="41cb6-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="41cb6-134">Первый шаг состоит в определении инцидентов удержания неактивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="41cb6-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="41cb6-135">Выполните следующую команду, чтобы отобразить сведения об удержании для всех неактивных почтовых ящиков в организации.</span><span class="sxs-lookup"><span data-stu-id="41cb6-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="41cb6-136">Значение **True** свойства **LitigationHoldEnabled** указывает, что неактивный почтовый ящик находится на хранении для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="41cb6-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="41cb6-137">Если для неактивного почтового ящика включено хранение на месте, GUID удержания отображается как значение свойства **InPlaceHolds**.</span><span class="sxs-lookup"><span data-stu-id="41cb6-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="41cb6-138">Например, в следующих результатах для двух неактивных почтовых ящиков покажут, что в Ann Beebe размещено удержание судебного разбирательства и что политика хранения и хранения In-Place для Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="41cb6-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="41cb6-139">Если на неактивном почтовом ящике In-Place много политик хранения или удержания, не все In-Place GUID hold будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="41cb6-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="41cb6-140">Для отображения всех GUID-объектов в свойстве InPlaceHolds можно выполнить следующую команду:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="41cb6-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="41cb6-141">Дополнительные сведения о выявлении удержаний см. в [сообщении How to identify the type of hold placed on a mailbox.](identify-a-hold-on-an-exchange-online-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="41cb6-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="41cb6-142">Действие 2. Удаление инцидента удержания неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="41cb6-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="41cb6-p109">После определения типа удержания или количества инцидентов удержания для неактивного почтового ящика следующий шаг  снятие удержаний. Как указывалось ранее, вам необходимо удалить все инциденты удержания, чтобы окончательно удалить неактивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="41cb6-p109">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="41cb6-145">Отключение хранения для судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="41cb6-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="41cb6-p110">Как было сказано выше, необходимо отключить режим хранения для судебного разбирательства для неактивного почтового ящика с помощью Windows PowerShell. Для этого не может использоваться EAC. Выполните следующую команду, чтобы отключить хранение для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="41cb6-p110">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="41cb6-p111">Лучший способ идентификации неактивного почтового ящика  использовать его различающееся имя или идентификатор GUID Exchange. Используя одно из этих значений, вы не укажете по ошибке неверный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="41cb6-p111">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="41cb6-151">Удаление неактивного почтового ящика из политики хранения</span><span class="sxs-lookup"><span data-stu-id="41cb6-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="41cb6-152">Процедура удаления неактивного почтового ящика из политики хранения Microsoft 365 зависит от того, является ли политика хранения, назначенная неактивному почтовому ящику, широкой организацией или явной.</span><span class="sxs-lookup"><span data-stu-id="41cb6-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="41cb6-153">о типе политики хранения, назначенной неактивному почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="41cb6-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="41cb6-154">Политики хранения для всей организации, присвоенные всем почтовым ящикам организации.</span><span class="sxs-lookup"><span data-stu-id="41cb6-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="41cb6-155">Чтобы получить сведения о политиках хранения в организации, используйте в Exchange Online PowerShell **cmdlet Get-OrganizationConfig.**</span><span class="sxs-lookup"><span data-stu-id="41cb6-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="41cb6-156">Определенные политики хранения расположения, присвоенные определенным почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="41cb6-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="41cb6-157">Это политики, которые назначены расположениям контента определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="41cb6-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="41cb6-158">Для получения сведений о политиках хранения, присвоенных определенным неактивным почтовым ящикам, используйте в Exchange Online PowerShell комлет **Get-Mailbox -IncludeInactiveMailbox.**</span><span class="sxs-lookup"><span data-stu-id="41cb6-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="41cb6-159">Удаление неактивного почтового ящика из политики хранения всей организации</span><span class="sxs-lookup"><span data-stu-id="41cb6-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="41cb6-160">Запустите следующую команду в Exchange Online PowerShell, чтобы исключить неактивный почтовый ящик из политики хранения по всей организации.</span><span class="sxs-lookup"><span data-stu-id="41cb6-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="41cb6-161">Дополнительные сведения о политиках хранения для всей организации, применяемых к неактивному почтовому ящику, и получении GUID [](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)для политики хранения см. в разделе "Get-OrganizationConfig" в разделе Как определить тип удержания, размещенного на почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="41cb6-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="41cb6-162">Кроме того, можно выполнить следующую команду, чтобы удалить неактивный почтовый ящик из всех политик всей организации:</span><span class="sxs-lookup"><span data-stu-id="41cb6-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="41cb6-163">Удаление неактивного почтового ящика из определенной политики хранения местоположения</span><span class="sxs-lookup"><span data-stu-id="41cb6-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="41cb6-164">Запустите следующую команду в [центре & PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) чтобы удалить неактивный почтовый ящик из явной политики хранения.</span><span class="sxs-lookup"><span data-stu-id="41cb6-164">Run the following command in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="41cb6-165">Дополнительные сведения о конкретных политиках хранения расположения, применяемых к неактивному почтовому ящику, и получении GUID для политики хранения см. в разделе "Get-Mailbox" в разделе Как определить тип удержания, размещенного на почтовом [ящике.](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)</span><span class="sxs-lookup"><span data-stu-id="41cb6-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="41cb6-166">Отключение хранения на месте</span><span class="sxs-lookup"><span data-stu-id="41cb6-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="41cb6-167">Отключить хранение на месте для неактивного почтового ящика можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="41cb6-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="41cb6-168">**Удаление объекта In-Place Hold**.</span><span class="sxs-lookup"><span data-stu-id="41cb6-168">**Delete the In-Place Hold object**.</span></span> <span data-ttu-id="41cb6-169">Если неактивный почтовый ящик, который необходимо окончательно удалить, является единственным исходным почтовым ящиком для In-Place Hold, можно просто удалить объект In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="41cb6-169">If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="41cb6-p116">Перед этим необходимо отключить хранение на месте. При попытке удаления объекта с включенным хранением на месте появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="41cb6-p116">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="41cb6-172">**Удалите неактивный почтовый ящик** в качестве источника почтового ящика In-Place hold .</span><span class="sxs-lookup"><span data-stu-id="41cb6-172">**Remove the inactive mailbox as a source mailbox of an In-Place Hold**.</span></span> <span data-ttu-id="41cb6-173">Если вы хотите сохранить другие исходные почтовые ящики для хранения на месте, можно удалить неактивный почтовый ящик из списка исходных почтовых ящиков и сохранить объект хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="41cb6-173">If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="41cb6-174">Удаление In-Place удержания</span><span class="sxs-lookup"><span data-stu-id="41cb6-174">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="41cb6-p118">Создайте переменную, содержащую свойства инцидента хранения на месте, который требуется удалить. Используйте GUID хранения на месте, полученный в [Действие 1. Определение инцидентов удержания для неактивного почтового ящика](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="41cb6-p118">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="41cb6-177">Отключите хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="41cb6-177">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="41cb6-178">Затем удалите инцидент хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="41cb6-178">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="41cb6-179">Удаление неактивного почтового ящика из In-Place Hold</span><span class="sxs-lookup"><span data-stu-id="41cb6-179">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="41cb6-180">Если инцидент хранения на месте содержит большое количество исходных почтовых ящиков, возможно, что неактивный почтовый ящик не будет показан на странице **Источники** в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="41cb6-180">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="41cb6-181">При редактировании инцидента хранения на месте на странице **Источники** отображаются до 3000 почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="41cb6-181">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="41cb6-182">Если неактивный почтовый ящик не  указан на странице Источники, вы можете использовать Exchange Online PowerShell, чтобы удалить его из In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="41cb6-182">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="41cb6-p120">Создайте переменную, содержащую свойства инцидента хранения на месте, примененного к неактивному почтовому ящику. Используйте GUID хранения на месте, полученный в [Действие 1. Определение инцидентов удержания для неактивного почтового ящика](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="41cb6-p120">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="41cb6-185">Убедитесь, что неактивный почтовый ящик указан как исходный почтовый ящик для хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="41cb6-185">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="41cb6-p121">Свойство *Sources* хранения на месте определяет исходные почтовые ящики по свойству *LegacyExchangeDN*. Поскольку это свойство уникально идентифицирует неактивные почтовые ящики, использование свойства *Sources* хранения на месте предотвращает удаление неверного почтового ящика. Это также позволяет избежать проблем, если у двух почтовых ящиков одинаковый псевдоним или SMTP-адрес.</span><span class="sxs-lookup"><span data-stu-id="41cb6-p121">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="41cb6-p122">Удалите неактивный почтовый ящик из списка исходных почтовых ящиков в переменной. Обязательно используйте свойство **LegacyExchangeDN** неактивного почтового ящика, возвращаемое командой на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="41cb6-p122">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="41cb6-191">Например, следующая команда удаляет неактивный почтовый ящик для пользователя Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="41cb6-191">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="41cb6-192">Убедитесь, что неактивный почтовый ящик удален из списка исходных почтовых ящиков в переменной.</span><span class="sxs-lookup"><span data-stu-id="41cb6-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="41cb6-193">Измените инцидент хранения на месте, используя обновленный список исходных почтовых ящиков, в который не входит неактивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="41cb6-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="41cb6-194">Убедитесь, что неактивный почтовый ящик удален из списка исходных почтовых ящиков для хранения на месте.</span><span class="sxs-lookup"><span data-stu-id="41cb6-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="41cb6-195">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="41cb6-195">More information</span></span>

- <span data-ttu-id="41cb6-p123">**Неактивный почтовый ящик  это тип обратимо удаленного почтового ящика.** В Exchange Online обратимо удаленный почтовый ящик  это удаленный ящик, который можно восстановить в течение определенного периода. Срок хранения обратимо удаленного почтового ящика в Exchange Online составляет 30 дней. Это значит, что почтовый ящик можно восстановить в течение 30 дней после обратимого удаления. Через 30 дней обратимо удаленный почтовый ящик помечается для окончательного удаления без возможности восстановления.</span><span class="sxs-lookup"><span data-stu-id="41cb6-p123">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="41cb6-201">**Что происходит после удаления удержания на неактивном почтовом ящике?**</span><span class="sxs-lookup"><span data-stu-id="41cb6-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="41cb6-202">Почтовый ящик рассматривается, как и другие удаленные электронные почтовые ящики, и по истечении 30-дневного периода хранения электронных почтовых ящиков помечен для постоянного удаления.</span><span class="sxs-lookup"><span data-stu-id="41cb6-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="41cb6-203">Этот период хранения начинается с даты первого неактивного действия почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="41cb6-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="41cb6-204">Эта дата называется датой мягкого удаления, которая является датой удаления соответствующей учетной записи пользователя или удалением почтового ящика Exchange Online с помощью cmdlet **Remove-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="41cb6-204">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="41cb6-205">Дата мягкого удаления не является датой удаления удержания.</span><span class="sxs-lookup"><span data-stu-id="41cb6-205">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="41cb6-p125">**Неактивный почтовый ящик окончательно удаляется сразу после снятия с удержания?** Если неактивный почтовый ящик был обратимо удален более 30 дней назад, он не будет удален окончательно сразу после снятия с удержания. Почтовый ящик будет отмечен для окончательного удаления и удален при следующей обработке.</span><span class="sxs-lookup"><span data-stu-id="41cb6-p125">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span>

- <span data-ttu-id="41cb6-209">**Как период хранения обратимо удаленного почтового ящика влияет на неактивные почтовые ящики?**</span><span class="sxs-lookup"><span data-stu-id="41cb6-209">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="41cb6-210">Если дата мягкого удаления неактивного почтового ящика превышает 30 дней до даты удаления удержания, почтовый ящик помечен для постоянного удаления.</span><span class="sxs-lookup"><span data-stu-id="41cb6-210">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="41cb6-211">Но если дата обратимого удаления неактивного почтового ящика попадает в последние 30 дней и вы удалите инцидент удержания, почтовый ящик можно восстановить до истечения срока хранения обратимо удаленного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="41cb6-211">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="41cb6-212">Подробные сведения см. в [публикации Удаление или восстановление](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)почтовых ящиков пользователей в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41cb6-212">For details, see [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span></span> <span data-ttu-id="41cb6-213">По истечении срока хранения удаленных почтовых ящиков необходимо следовать процедурам восстановления неактивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="41cb6-213">After the soft-deleted mailbox retention period expires, you have to follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="41cb6-214">Дополнительные сведения [см. в материале Восстановление неактивного почтового ящика в Office 365.](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="41cb6-214">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="41cb6-215">**Как отобразить сведения о неактивном почтовом ящике после снятия с удержания?**</span><span class="sxs-lookup"><span data-stu-id="41cb6-215">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="41cb6-216">После удаления удержания и возврата неактивного почтового ящика в электронный удаленный почтовый ящик он не возвращается с помощью параметра *InactiveMailboxOnly* с помощью cmdlet **Get-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="41cb6-216">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="41cb6-217">Однако вы можете отобразить сведения о почтовом ящике с помощью команды **Get-Mailbox -SoftDeletedMailbox**.</span><span class="sxs-lookup"><span data-stu-id="41cb6-217">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="41cb6-218">Например:</span><span class="sxs-lookup"><span data-stu-id="41cb6-218">For example:</span></span>

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

  <span data-ttu-id="41cb6-219">В этом примере свойство *WhenSoftDeleted* определяет дату мягкого удаления, которая в этом примере — 30 октября 2014 г.</span><span class="sxs-lookup"><span data-stu-id="41cb6-219">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="41cb6-220">Если этот электронный удаленный почтовый ящик ранее был неактивным почтовым ящиком, для которого был удален удержание, он будет окончательно удален через 30 дней после значения свойства *WhenSoftDeleted.*</span><span class="sxs-lookup"><span data-stu-id="41cb6-220">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="41cb6-221">В этом случае почтовый ящик окончательно удаляется после 30 ноября 2014 г.</span><span class="sxs-lookup"><span data-stu-id="41cb6-221">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>
