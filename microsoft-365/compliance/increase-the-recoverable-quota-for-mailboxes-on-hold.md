---
title: Увеличение квоты для папки "Элементы с возможностью восстановления" для почтовых ящиков на удержании
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 'Включите архивный почтовый ящик и включите автоматическое расширение архивации, чтобы увеличить размер папки "элементы с возможностью восстановления" для почтового ящика в Office 365. '
ms.openlocfilehash: 884a03bc1693ec76cd3e80d85f62f4054e1d9911
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222712"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="44ced-103">Увеличение квоты для папки "Элементы с возможностью восстановления" для почтовых ящиков на удержании</span><span class="sxs-lookup"><span data-stu-id="44ced-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="44ced-104">Политика хранения по умолчанию с именем "политика управления ЗАПИСЯМИ сообщений по умолчанию", которая автоматически применяется к новым почтовым ящикам в Exchange Online, содержит тег хранения с именем "элементы с возможностью восстановления" через 14 дней перемещение в архив.</span><span class="sxs-lookup"><span data-stu-id="44ced-104">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="44ced-105">Этот тег хранения перемещает элементы из папки "элементы с возможностью восстановления" в основном почтовом ящике пользователя в папку "элементы с возможностью восстановления" в архивном почтовом ящике пользователя по истечении срока хранения в течение 14 дней до истечения срока действия элемента.</span><span class="sxs-lookup"><span data-stu-id="44ced-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="44ced-106">Чтобы это происходило, архивный почтовый ящик пользователя должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="44ced-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="44ced-107">Если архивный почтовый ящик не включен, никакие действия не выполняются, что означает, что элементы в папке "элементы с возможностью восстановления" для почтового ящика на удержании не перемещаются в архивный почтовый ящик по истечении срока хранения в течение 14 дней.</span><span class="sxs-lookup"><span data-stu-id="44ced-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="44ced-108">Так как в почтовом ящике ничего не удаляется, возможно, превышена квота хранилища для папки "элементы с возможностью восстановления", особенно если архивный почтовый ящик пользователя не включен.</span><span class="sxs-lookup"><span data-stu-id="44ced-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="44ced-109">Чтобы уменьшить вероятность превышения этого ограничения, квота хранилища для папки "элементы с возможностью восстановления" автоматически увеличивается с 30 ГБ до 100 ГБ при размещении в почтовом ящике в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="44ced-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="44ced-110">Если архивный почтовый ящик включен, квота хранилища для папки "Элементы с возможностью восстановления" в нем также увеличивается с 30 ГБ до 100 ГБ.</span><span class="sxs-lookup"><span data-stu-id="44ced-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="44ced-111">Если функция автоматического расширения архивации в Exchange Online включена, квота хранилища для папки "элементы с возможностью восстановления" в архиве пользователя будет неограниченна.</span><span class="sxs-lookup"><span data-stu-id="44ced-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="44ced-112"> В приведенной ниже таблице указаны квоты хранилища для папки "Элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="44ced-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="44ced-113">**Расположение папки "Элементы с возможностью восстановления"**</span><span class="sxs-lookup"><span data-stu-id="44ced-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="44ced-114">**Почтовые ящики не на удержании**</span><span class="sxs-lookup"><span data-stu-id="44ced-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="44ced-115">**Почтовые ящики на удержании**</span><span class="sxs-lookup"><span data-stu-id="44ced-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44ced-116">Основной почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="44ced-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="44ced-117">30 ГБ</span><span class="sxs-lookup"><span data-stu-id="44ced-117">30 GB</span></span>  <br/> |<span data-ttu-id="44ced-118">100 ГБ</span><span class="sxs-lookup"><span data-stu-id="44ced-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="44ced-119">Архивный почтовый ящик<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44ced-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="44ced-120">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="44ced-120">Unlimited</span></span>  <br/> |<span data-ttu-id="44ced-121">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="44ced-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="44ced-122">**Общая квота хранилищ для папки "Элементы с возможностью восстановления"**</span><span class="sxs-lookup"><span data-stu-id="44ced-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="44ced-123">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="44ced-123">Unlimited</span></span>  <br/> |<span data-ttu-id="44ced-124">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="44ced-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="44ced-125"><sup>\*</sup>Первоначальной квотой хранилища для архивного почтового ящика является 100 ГБ для пользователей с лицензией на Exchange Online (план 2).</span><span class="sxs-lookup"><span data-stu-id="44ced-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="44ced-126">Однако если включено автоматическое расширение архивации для почтовых ящиков на удержании, квота хранилища для архивного почтового ящика и папки "элементы с возможностью восстановления" увеличивается до 110 ГБ.</span><span class="sxs-lookup"><span data-stu-id="44ced-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="44ced-127">Дополнительное дисковое пространство для архивов будет подготовлено при необходимости, что приведет к неограниченному объему архивного хранилища.</span><span class="sxs-lookup"><span data-stu-id="44ced-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="44ced-128">Дополнительные сведения об автоматическом развертывании архивации приведены [в статье Обзор неограниченного архивирования в Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="44ced-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="44ced-129">Когда размер папки "Элементы с возможностью восстановления" в основном почтовом ящике на удержании будет приближаться к предельному значению квоты хранилища, можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="44ced-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="44ced-130">**Включите архивный почтовый ящик и включите автоматическое расширение архивации** — вы можете включить неограниченную емкость хранилища для папки "элементы с возможностью восстановления", просто включив архивный почтовый ящик, а затем включив функцию автоматического развертывания архивации в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="44ced-130">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="44ced-131">Это приводит к 110 ГБ для папки "элементы с возможностью восстановления" в основном почтовом ящике и неограниченному количеству емкости хранилища для папки "элементы с возможностью восстановления" в архиве пользователя.</span><span class="sxs-lookup"><span data-stu-id="44ced-131">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="44ced-132">Узнайте, как [Включить архивные почтовые ящики в центре безопасности & соответствия требованиям](enable-archive-mailboxes.md) и [включить неограниченную архивацию в Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="44ced-132">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="44ced-133">Если объем данных в папке "Элементы с возможностью восстановления" почтового ящика, для которого включен архив, скоро превысит квоту хранилища, может понадобиться вручную запустить обработку этого ящика с использованием помощника по работе с управляемыми папками, чтобы переместить элементы с истекшим сроком действия в папку "Элементы с возможностью восстановления" в архивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="44ced-133">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="44ced-134">Инструкции см. в разделе, описывающем [этап 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings).</span><span class="sxs-lookup"><span data-stu-id="44ced-134">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="44ced-135">Обратите внимание на то, что другие элементы в почтовом ящике пользователя могут быть перемещены в новый архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="44ced-135">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="44ced-136">Рассмотрите возможность сообщить пользователю, что это может произойти после включения архивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="44ced-136">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="44ced-137">**Создание настраиваемой политики хранения для почтовых ящиков на удержании** Добавление архивного почтового ящика и автоматического расширения архивации для почтовых ящиков на хранение для судебного разбирательства или хранение на месте может также потребоваться создать настраиваемую политику хранения для почтовых ящиков на удержании.</span><span class="sxs-lookup"><span data-stu-id="44ced-137">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold.</span></span> <span data-ttu-id="44ced-138">Это позволяет применять политику хранения к почтовым ящикам на удержании, которые отличаются от политики управления ЗАПИСЯМИ сообщений по умолчанию, которая применяется к почтовым ящикам, которые не находятся на удержании.</span><span class="sxs-lookup"><span data-stu-id="44ced-138">This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold.</span></span> <span data-ttu-id="44ced-139">Это позволяет применять теги хранения, предназначенные специально для почтовых ящиков на удержании.</span><span class="sxs-lookup"><span data-stu-id="44ced-139">This lets you to apply retention tags that are specifically designed for mailboxes on hold.</span></span> <span data-ttu-id="44ced-140">Это включает создание нового тега хранения для папки "элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="44ced-140">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="44ced-141">В оставшейся части этой статьи приведены пошаговые инструкции по созданию настраиваемой политики хранения для почтовых ящиков на удержании.</span><span class="sxs-lookup"><span data-stu-id="44ced-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="44ced-142">Этап 1. Создание настраиваемых тегов хранения для папки "Элементы с возможностью восстановления"</span><span class="sxs-lookup"><span data-stu-id="44ced-142">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

<span data-ttu-id="44ced-143">[[Шаг 2: создание новой политики хранения для почтовых ящиков на удержании](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="44ced-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="44ced-144">Этап 3. Применение новой политики хранения к почтовым ящикам на удержании</span><span class="sxs-lookup"><span data-stu-id="44ced-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="44ced-145">Этап 4 (необязательный). Запуск помощника по работе с управляемыми папками для применения новых параметров хранения</span><span class="sxs-lookup"><span data-stu-id="44ced-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="44ced-146">Этап 1. Создание настраиваемых тегов хранения для папки "Элементы с возможностью восстановления"</span><span class="sxs-lookup"><span data-stu-id="44ced-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="44ced-147">Первый этап — создание пользовательского тега хранения (также называемого тегом политики хранения, или RPT) для папки "Элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="44ced-147">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="44ced-148">Как пояснялось ранее, RPT перемещает элементы из папки "Элементы с возможностью восстановления" основного почтового ящика пользователя в такую же папку архивного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="44ced-148">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="44ced-149">Чтобы создать RPT для папки "элементы с возможностью восстановления", необходимо использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44ced-149">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="44ced-150">Вы не можете сделать этого в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="44ced-150">You can't use the Exchange admin center (EAC).</span></span> 
  
1. <span data-ttu-id="44ced-151">[Подключитесь к Exchange Online с помощью удаленного сеанса PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span><span class="sxs-lookup"><span data-stu-id="44ced-151">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)</span></span>
    
2. <span data-ttu-id="44ced-152">Выполните следующую команду, чтобы создать новый RPT для папки "Элементы с возможностью восстановления": </span><span class="sxs-lookup"><span data-stu-id="44ced-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="44ced-p108">Например, приведенная ниже команда создает для папки "Элементы с возможностью восстановления" RPT с именем "Recoverable Items 30 days for mailboxes on hold" (Элементы с возможностью восстановления, 30 дней для почтовых ящиков на удержании) со сроком хранения 30 дней. Это значит, что по истечении 30 дней хранения элемента в папке "Элементы с возможностью восстановления" он будет перемещен в такую же папку архивного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="44ced-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="44ced-155">Рекомендуется, чтобы срок хранения (определенный параметром _ажелимитфорретентион_ ) для элементов с возможностью восстановления был таким же, как и срок хранения удаленных элементов для почтовых ящиков, к которым будет применяться RPT.</span><span class="sxs-lookup"><span data-stu-id="44ced-155">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="44ced-156">Это позволяет пользователю восстанавливать удаленные элементы в течение всего срока хранения, прежде чем они будут перемещены в архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="44ced-156">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="44ced-157">В предыдущем примере был задан срок хранения 30 дней на основании предположения, что период хранения удаленных элементов для почтового ящика составляет 30 дней.</span><span class="sxs-lookup"><span data-stu-id="44ced-157">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="44ced-158">Почтовый ящик Exchange Online по умолчанию настроен на хранение удаленных элементов в течение 14 дней.</span><span class="sxs-lookup"><span data-stu-id="44ced-158">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="44ced-159">Но этот период можно изменить, задав максимальное значение — 30 дней.</span><span class="sxs-lookup"><span data-stu-id="44ced-159">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="44ced-160">Дополнительную информацию можно узнать в статье [изменение срока хранения удаленных элементов для почтового ящика в Exchange Online](https://www.microsoft.com/?ref=go).</span><span class="sxs-lookup"><span data-stu-id="44ced-160">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="44ced-161">Этап 2. Создание политики хранения для почтовых ящиков на удержании</span><span class="sxs-lookup"><span data-stu-id="44ced-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="44ced-p110">Следующий этап — создание новой политики хранения и добавление в нее тегов хранения, в том числе RPT элементов с возможностью восстановления, созданного на этапе 1. Эта новая политика будет применена к почтовым ящикам на удержании на следующем этапе. </span><span class="sxs-lookup"><span data-stu-id="44ced-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="44ced-p111">Прежде чем создавать новую политику хранения, определите дополнительные теги хранения, которые вы хотите добавить. Список тегов хранения, которые будут добавлены к политике управления записями сообщений по умолчанию, а также сведения о создании новых тегов хранения см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="44ced-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="44ced-166">Политика хранения по умолчанию в Exchange Online </span><span class="sxs-lookup"><span data-stu-id="44ced-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="44ced-167">Папки по умолчанию, которые поддерживают теги политики хранения</span><span class="sxs-lookup"><span data-stu-id="44ced-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="44ced-168">Раздел "Создание тега хранения" в разделе [Создание политики хранения](https://go.microsoft.com/fwlink/p/?LinkId=404422) .</span><span class="sxs-lookup"><span data-stu-id="44ced-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="44ced-169">Для создания политики хранения можно использовать центр администрирования Exchange или Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44ced-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="44ced-170">Создание политики хранения с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="44ced-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="44ced-171">В центре администрирования Exchange перейдите к разделу политики хранения **управления соответствием требованиям** \> **Retention policies**и нажмите кнопку **Добавить** ![ значок ](../media/ITPro-EAC-AddIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="44ced-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="44ced-172">В поле **Имя** на странице **Новая политика хранения** введите имя, описывающее назначение политики хранения, например **MRM Policy for Mailboxes on Hold** (Политика управления записями сообщений для почтовых ящиков на удержании). </span><span class="sxs-lookup"><span data-stu-id="44ced-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="44ced-173">В разделе **теги хранения**нажмите кнопку **Добавить** ![ значок ](../media/ITPro-EAC-AddIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="44ced-173">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="44ced-174">В списке тегов хранения выберите RPT элементов с возможностью восстановления, созданный на этапе 1, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="44ced-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![Выберите настраиваемый тег хранения "Элементы с возможностью восстановления"](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="44ced-p112">Выберите дополнительные теги, которые необходимо добавить к политике хранения. Например, может потребоваться добавить теги, которые уже включены в политику управления записями сообщений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44ced-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="44ced-178">Добавив все теги хранения, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="44ced-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="44ced-179">Нажмите кнопку **Сохранить**, чтобы создать новую политику хранения.</span><span class="sxs-lookup"><span data-stu-id="44ced-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="44ced-180">Обратите внимание, что теги хранения, связанные с политикой хранения, отображаются в области сведений.</span><span class="sxs-lookup"><span data-stu-id="44ced-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![Теги хранения, связанные с политикой хранения, в области сведений](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="44ced-182">Создание политики хранения с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="44ced-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="44ced-183">Чтобы создать политику хранения для почтовых ящиков на удержании, выполните приведенную ниже команду. </span><span class="sxs-lookup"><span data-stu-id="44ced-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="44ced-184">Например, приведенная ниже команда создает политику хранения и связанные теги хранения, отображенные на предыдущем рисунке.</span><span class="sxs-lookup"><span data-stu-id="44ced-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="44ced-185">Этап 3. Применение новой политики хранения к почтовым ящикам на удержании</span><span class="sxs-lookup"><span data-stu-id="44ced-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="44ced-186">Последний этап — применение новой политики хранения, созданной на этапе 2, к почтовым ящикам на удержании в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="44ced-186">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="44ced-187">С помощью центра администрирования Exchange или Exchange Online PowerShell можно применить политику хранения к одному почтовому ящику или нескольким почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="44ced-187">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="44ced-188">Применение новой политики хранения с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="44ced-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="44ced-189">Перейдите к разделу **Получатели** \> **Почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="44ced-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="44ced-190">В представлении списка выберите почтовый ящик, к которому нужно применить политику хранения, и нажмите кнопку **изменить** ![ значок редактирования ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="44ced-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="44ced-191">На странице **Изменить почтовый ящик пользователя** выберите пункт **Функции почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="44ced-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="44ced-192">В разделе **Политика хранения** выберите политику хранения, созданную на этапе 2, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="44ced-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="44ced-193">С помощью Центра администрирования Exchange можно также применить политику хранения к нескольким почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="44ced-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="44ced-194">Перейдите к разделу **Получатели** \> **Почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="44ced-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="44ced-195">В представлении списка воспользуйтесь клавишами SHIFT или CTRL, чтобы выбрать несколько почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="44ced-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="44ced-196">В области сведений щелкните **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="44ced-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="44ced-197">В разделе **Политика хранения** щелкните **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="44ced-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="44ced-198">На странице **Массовое назначение политики хранения** выберите политику хранения, созданную на этапе 2, и нажмите кнопку **Сохранить**. </span><span class="sxs-lookup"><span data-stu-id="44ced-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="44ced-199">Применение новой политики хранения с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="44ced-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="44ced-200">С помощью Exchange Online PowerShell можно применить новую политику хранения к одному почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="44ced-200">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="44ced-201">Но вы можете использовать PowerShell, чтобы быстро определить все почтовые ящики в Организации, которые находятся на хранении судебного разбирательства или хранение на месте, а затем применить новую политику хранения ко всем почтовым ящикам, которые хранятся в одной команде.</span><span class="sxs-lookup"><span data-stu-id="44ced-201">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="44ced-202">Ниже приведено несколько примеров использования Exchange PowerShell для применения политики хранения к одному или нескольким почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="44ced-202">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="44ced-203">Во всех примерах применяется политика, созданная на этапе 2.</span><span class="sxs-lookup"><span data-stu-id="44ced-203">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="44ced-204">В этом примере новая политика хранения применяется к почтовому ящику пользователя Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="44ced-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="44ced-205">В этом примере показано, как применить созданную политику хранения ко всем почтовым ящикам в организации, находящимся на хранении для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="44ced-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="44ced-206">В этом примере показано, как применить созданную политику хранения ко всем почтовым ящикам в организации, находящимся на удержании на месте.</span><span class="sxs-lookup"><span data-stu-id="44ced-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="44ced-207">Чтобы проверить, применена ли новая политика хранения, используйте командлет **Get-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="44ced-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="44ced-208">Ниже показано несколько вариантов кода, позволяющих проверить, применили ли команды из предыдущих примеров политику "MRM Policy for Mailboxes on Hold" (Управление записями сообщений для почтовых ящиков на удержании) к почтовым ящикам, которые находятся на хранении для судебного разбирательства или на удержании на месте.</span><span class="sxs-lookup"><span data-stu-id="44ced-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="44ced-209">Этап 4 (необязательный). Запуск помощника по работе с управляемыми папками для применения новых параметров хранения</span><span class="sxs-lookup"><span data-stu-id="44ced-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="44ced-210">После применения новой политики хранения к почтовым ящикам на удержании может потребоваться до 7 дней в Exchange Online для обработки этих почтовых ящиков с помощью параметров новой политики хранения.</span><span class="sxs-lookup"><span data-stu-id="44ced-210">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="44ced-211">Вы можете не ожидать, пока будут обработаны ящики, к которым была применена новая политика хранения, а запустить помощника по работе с управляемыми папками вручную с помощью командлета **Start-ManagedFolderAssistant**.</span><span class="sxs-lookup"><span data-stu-id="44ced-211">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="44ced-212">Выполните приведенную ниже команду, чтобы запустить помощник по работе с управляемыми папками для почтового ящика пользователя Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="44ced-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="44ced-213">Выполните приведенную ниже команду, чтобы запустить помощник по работе с управляемыми папками для всех почтовых ящиков на удержании.</span><span class="sxs-lookup"><span data-stu-id="44ced-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="44ced-214">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="44ced-214">More information</span></span>

- <span data-ttu-id="44ced-215">После включения архивного почтового ящика рекомендуем сообщить пользователю о том, что в архивный почтовый ящик могут переместиться не только элементы из папки "Элементы с возможностью восстановления", но и другие.</span><span class="sxs-lookup"><span data-stu-id="44ced-215">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="44ced-216">Это связано с тем, что политика управления ЗАПИСЯМИ сообщений по умолчанию, назначенная для почтовых ящиков Exchange Online, содержит тег хранения (с именем Default 2 года перемещение в архив), который перемещает элементы в архивный почтовый ящик через два года после того, как дата доставки элемента в почтовый ящик или создана пользователем.</span><span class="sxs-lookup"><span data-stu-id="44ced-216">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="44ced-217">Дополнительные сведения см. [в статье политика хранения по умолчанию в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="44ced-217">For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="44ced-218">После включения архивного почтового ящика рекомендуем сообщить пользователю, что он может восстановить удаленные элементы благодаря папке "Элементы с возможностью восстановления" своего архивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="44ced-218">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="44ced-219">Это можно сделать в Outlook, выбрав папку " **Удаленные** " в архивном почтовом ящике, а затем нажав кнопку **восстановить удаленные элементы с сервера** на вкладке **Главная** . Дополнительные сведения о восстановлении удаленных элементов приведены [в статье Восстановление удаленных элементов в Outlook для Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span><span class="sxs-lookup"><span data-stu-id="44ced-219">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
