---
title: Увеличение квоты для папки "Элементы с возможностью восстановления" для почтовых ящиков на удержании
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: Включив архивный почтовый ящик и включив автоматическое расширение архива, вы увеличите размер папки "Элементы с возможностью восстановления" для почтового ящика в Microsoft 365.
ms.openlocfilehash: c674d3df4ad14dabce13effd0dd6729edaeab715
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804648"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="df2ea-103">Увеличение квоты для папки "Элементы с возможностью восстановления" для почтовых ящиков на удержании</span><span class="sxs-lookup"><span data-stu-id="df2ea-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="df2ea-104">Политика хранения Exchange по умолчанию с именем *Default MRM Policy,* которая автоматически применяется к новым почтовым ящикам в Exchange Online, содержит тег хранения с именем "Элементы с возможностью восстановления" через 14 дней, перемещаемый в архив.</span><span class="sxs-lookup"><span data-stu-id="df2ea-104">The default Exchange retention policy—named *Default MRM Policy*—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="df2ea-105">Этот тег хранения перемещает элементы из папки "Элементы с возможностью восстановления" основного почтового ящика пользователя в папку "Элементы с возможностью восстановления" в архивном почтовом ящике пользователя по истечении 14-дневного срока хранения элемента.</span><span class="sxs-lookup"><span data-stu-id="df2ea-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="df2ea-106">Для этого необходимо включить архивный почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="df2ea-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="df2ea-107">Если архивный почтовый ящик не включен, никакие действия не принимаются, что означает, что элементы в папке "Элементы с возможностью восстановления" для почтового ящика на удержании не перемещаются в архивный почтовый ящик по истечении 14-дневного срока хранения.</span><span class="sxs-lookup"><span data-stu-id="df2ea-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="df2ea-108">Так как из почтового ящика на удержании ничего не удаляется, квота хранилища для папки "Элементы с возможностью восстановления" может быть превышена, особенно если архивный почтовый ящик пользователя не включен.</span><span class="sxs-lookup"><span data-stu-id="df2ea-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="df2ea-109">Чтобы уменьшить вероятность превышения этого ограничения, квота хранилища для папки "Элементы с возможностью восстановления" автоматически увеличивается с 30 ГБ до 100 ГБ при удержании почтового ящика в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="df2ea-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="df2ea-110">Если архивный почтовый ящик включен, квота хранилища для папки "Элементы с возможностью восстановления" в нем также увеличивается с 30 ГБ до 100 ГБ.</span><span class="sxs-lookup"><span data-stu-id="df2ea-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="df2ea-111">Если функция автоматического расширения архивирования в Exchange Online включена, квота хранилища для папки "Элементы с возможностью восстановления" в архиве пользователя будет неограниченной.</span><span class="sxs-lookup"><span data-stu-id="df2ea-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="df2ea-112"> В приведенной ниже таблице указаны квоты хранилища для папки "Элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="df2ea-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="df2ea-113">**Расположение папки "Элементы с возможностью восстановления"**</span><span class="sxs-lookup"><span data-stu-id="df2ea-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="df2ea-114">**Почтовые ящики не на удержании**</span><span class="sxs-lookup"><span data-stu-id="df2ea-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="df2ea-115">**Почтовые ящики на удержании**</span><span class="sxs-lookup"><span data-stu-id="df2ea-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="df2ea-116">Основной почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="df2ea-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="df2ea-117">30 ГБ</span><span class="sxs-lookup"><span data-stu-id="df2ea-117">30 GB</span></span>  <br/> |<span data-ttu-id="df2ea-118">100 ГБ</span><span class="sxs-lookup"><span data-stu-id="df2ea-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="df2ea-119">Архивный почтовый ящик<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="df2ea-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="df2ea-120">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="df2ea-120">Unlimited</span></span>  <br/> |<span data-ttu-id="df2ea-121">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="df2ea-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="df2ea-122">**Общая квота хранилищ для папки "Элементы с возможностью восстановления"**</span><span class="sxs-lookup"><span data-stu-id="df2ea-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="df2ea-123">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="df2ea-123">Unlimited</span></span>  <br/> |<span data-ttu-id="df2ea-124">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="df2ea-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="df2ea-125"><sup>\*</sup> Начальная квота хранилища для архивного почтового ящика составляет 100 ГБ для пользователей с лицензией Exchange Online (план 2).</span><span class="sxs-lookup"><span data-stu-id="df2ea-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="df2ea-126">Однако если архивирование с автоматическим расширением включено для почтовых ящиков на удержании, квота хранилища для архивного почтового ящика и папки "Элементы с возможностью восстановления" увеличивается до 110 ГБ.</span><span class="sxs-lookup"><span data-stu-id="df2ea-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="df2ea-127">Дополнительное архивное хранилище будет резервироваться при необходимости, что приводит к неограниченному объему архивного хранилища.</span><span class="sxs-lookup"><span data-stu-id="df2ea-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="df2ea-128">Дополнительные сведения об автоматическом расширении архивных данных см. в обзоре неограниченной архиватуры [в Office 365.](unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="df2ea-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="df2ea-129">Когда размер папки "Элементы с возможностью восстановления" в основном почтовом ящике на удержании будет приближаться к предельному значению квоты хранилища, можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="df2ea-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="df2ea-130">**Включив архивный почтовый ящик и включив автоматическое расширение архива.**</span><span class="sxs-lookup"><span data-stu-id="df2ea-130">**Enable the archive mailbox and turn on auto-expanding archiving.**</span></span> <span data-ttu-id="df2ea-131">Вы можете включить неограниченный объем хранилища для папки "Элементы с возможностью восстановления", просто включив архивный почтовый ящик и включив функцию автоматического расширения архивирования в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="df2ea-131">You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="df2ea-132">Это приводит к 110 ГБ для папки "Элементы с возможностью восстановления" в основном почтовом ящике и неограниченному объему памяти для папки "Элементы с возможностью восстановления" в архиве пользователя.</span><span class="sxs-lookup"><span data-stu-id="df2ea-132">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="df2ea-133">Узнайте, как включить [архивные](enable-archive-mailboxes.md) почтовые ящики в Центре безопасности & соответствия требованиям и включить неограниченную архивировать [в Office 365.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="df2ea-133">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="df2ea-134">После того как архив почтового ящика почти превышает квоту хранилища для папки "Элементы с возможностью восстановления", может потребоваться запустить помощник для управляемых папок, чтобы вручную запустить помощник для обработки почтового ящика, чтобы элементы с истекшим сроком действия перемещались в папку "Элементы с возможностью восстановления" в архивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="df2ea-134">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="df2ea-135">Инструкции см. в разделе, описывающем [этап 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings).</span><span class="sxs-lookup"><span data-stu-id="df2ea-135">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="df2ea-136">Обратите внимание на то, что другие элементы в почтовом ящике пользователя могут быть перемещены в новый архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="df2ea-136">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="df2ea-137">Рассмотрите возможность сообщения пользователю о том, что это может произойти после того, как вы в включаете архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="df2ea-137">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="df2ea-138">**Создайте настраиваемую политику хранения Exchange для почтовых ящиков на удержании.**</span><span class="sxs-lookup"><span data-stu-id="df2ea-138">**Create a custom Exchange retention policy for mailboxes on hold.**</span></span> <span data-ttu-id="df2ea-139">Помимо включения архивного почтового ящика и автоматического расширения архивных данных для почтовых ящиков, для почтовых ящиков на хранении для судебного разбирательства или удержании In-Place, можно также создать настраиваемую политику хранения Exchange для почтовых ящиков на удержании.</span><span class="sxs-lookup"><span data-stu-id="df2ea-139">In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom Exchange retention policy for mailboxes on hold.</span></span> <span data-ttu-id="df2ea-140">Это позволяет применять политику хранения к почтовым ящикам на удержании, которая отличается от политики mrM по умолчанию, применяемой к почтовым ящикам, которые не находятся на удержании, и позволяет применять теги хранения, предназначенные для почтовых ящиков на удержании.</span><span class="sxs-lookup"><span data-stu-id="df2ea-140">This lets you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold, and lets you apply retention tags that are designed for mailboxes on hold.</span></span> <span data-ttu-id="df2ea-141">Это включает создание нового тега хранения для папки "Элементы с функцией восстановления".</span><span class="sxs-lookup"><span data-stu-id="df2ea-141">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="df2ea-142">В оставшейся части этой темы описываются пошаговые процедуры по созданию настраиваемой политики хранения Exchange для почтовых ящиков на удержании.</span><span class="sxs-lookup"><span data-stu-id="df2ea-142">The remainder of this topic describes the step-by-step procedures to create a custom Exchange retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="df2ea-143">Этап 1. Создание настраиваемых тегов хранения для папки "Элементы с возможностью восстановления"</span><span class="sxs-lookup"><span data-stu-id="df2ea-143">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[<span data-ttu-id="df2ea-144">Шаг 2. Создание новой политики хранения Exchange для почтовых ящиков на удержании</span><span class="sxs-lookup"><span data-stu-id="df2ea-144">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[<span data-ttu-id="df2ea-145">Шаг 3. Применение новой политики хранения Exchange к почтовым ящикам на удержании</span><span class="sxs-lookup"><span data-stu-id="df2ea-145">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="df2ea-146">Этап 4 (необязательный). Запуск помощника по работе с управляемыми папками для применения новых параметров хранения</span><span class="sxs-lookup"><span data-stu-id="df2ea-146">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="df2ea-147">Этап 1. Создание настраиваемых тегов хранения для папки "Элементы с возможностью восстановления"</span><span class="sxs-lookup"><span data-stu-id="df2ea-147">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="df2ea-148">Первый этап — создание пользовательского тега хранения (также называемого тегом политики хранения, или RPT) для папки "Элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="df2ea-148">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="df2ea-149">Как пояснялось ранее, RPT перемещает элементы из папки "Элементы с возможностью восстановления" основного почтового ящика пользователя в такую же папку архивного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="df2ea-149">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="df2ea-150">Для создания RPT для папки "Элементы с возможностью восстановления" необходимо использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df2ea-150">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="df2ea-151">Вы не можете сделать этого в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="df2ea-151">You can't use the Exchange admin center (EAC).</span></span> 
  
1. <span data-ttu-id="df2ea-152">[Подключитесь к Exchange Online с помощью удаленного сеанса PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span><span class="sxs-lookup"><span data-stu-id="df2ea-152">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)</span></span>
    
2. <span data-ttu-id="df2ea-153">Выполните следующую команду, чтобы создать новый RPT для папки "Элементы с возможностью восстановления": </span><span class="sxs-lookup"><span data-stu-id="df2ea-153">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="df2ea-154">Например, следующая команда создает RPT для папки "Элементы с возможностью восстановления" с именем "Элементы с возможностью восстановления 30 дней для почтовых ящиков на удержании" с сроком хранения 30 дней.</span><span class="sxs-lookup"><span data-stu-id="df2ea-154">For example, the following command creates an RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="df2ea-155">Это значит, что по истечении 30 дней хранения элемента в папке "Элементы с возможностью восстановления" он будет перемещен в такую же папку архивного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="df2ea-155">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="df2ea-156">Рекомендуется, чтобы период хранения (определенный параметром  _AgeLimitForRetention)_ для RPT элементов для восстановления был таким же, как и период хранения удаленных элементов для почтовых ящиков, к которые будет применяться RPT.</span><span class="sxs-lookup"><span data-stu-id="df2ea-156">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="df2ea-157">Это позволяет пользователю восстанавливать удаленные элементы в течение всего срока хранения, прежде чем они будут перемещены в архивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="df2ea-157">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="df2ea-158">В предыдущем примере был задан срок хранения 30 дней на основании предположения, что период хранения удаленных элементов для почтового ящика составляет 30 дней.</span><span class="sxs-lookup"><span data-stu-id="df2ea-158">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="df2ea-159">Почтовый ящик Exchange Online по умолчанию сохраняет удаленные элементы в течение 14 дней.</span><span class="sxs-lookup"><span data-stu-id="df2ea-159">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="df2ea-160">Но этот период можно изменить, задав максимальное значение — 30 дней.</span><span class="sxs-lookup"><span data-stu-id="df2ea-160">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="df2ea-161">Дополнительные сведения см. в статье "Изменение периода хранения удаленных элементов [для почтового ящика в Exchange Online".](https://www.microsoft.com/?ref=go)</span><span class="sxs-lookup"><span data-stu-id="df2ea-161">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="df2ea-162">Шаг 2. Создание новой политики хранения Exchange для почтовых ящиков на удержании</span><span class="sxs-lookup"><span data-stu-id="df2ea-162">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>

<span data-ttu-id="df2ea-p110">Следующий этап — создание новой политики хранения и добавление в нее тегов хранения, в том числе RPT элементов с возможностью восстановления, созданного на этапе 1. Эта новая политика будет применена к почтовым ящикам на удержании на следующем этапе. </span><span class="sxs-lookup"><span data-stu-id="df2ea-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="df2ea-p111">Прежде чем создавать новую политику хранения, определите дополнительные теги хранения, которые вы хотите добавить. Список тегов хранения, которые будут добавлены к политике управления записями сообщений по умолчанию, а также сведения о создании новых тегов хранения см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="df2ea-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="df2ea-167">Политика хранения по умолчанию в Exchange Online </span><span class="sxs-lookup"><span data-stu-id="df2ea-167">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="df2ea-168">Папки по умолчанию, которые поддерживают теги политики хранения</span><span class="sxs-lookup"><span data-stu-id="df2ea-168">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="df2ea-169">Раздел "Создание тега хранения" в разделе ["Создание политики хранения".](https://go.microsoft.com/fwlink/p/?LinkId=404422)</span><span class="sxs-lookup"><span data-stu-id="df2ea-169">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="df2ea-170">Для создания политики хранения можно использовать EAC или Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df2ea-170">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="df2ea-171">Создание политики хранения с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="df2ea-171">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="df2ea-172">В EAC перейдите к **политикам** хранения для управления соответствием требованиям и нажмите кнопку \>  **"Добавить** ![ значок добавления". ](../media/ITPro-EAC-AddIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="df2ea-172">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="df2ea-173">В поле **Имя** на странице **Новая политика хранения** введите имя, описывающее назначение политики хранения, например **MRM Policy for Mailboxes on Hold** (Политика управления записями сообщений для почтовых ящиков на удержании). </span><span class="sxs-lookup"><span data-stu-id="df2ea-173">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="df2ea-174">В **тегах хранения нажмите** **кнопку "Добавить** ![ значок добавления". ](../media/ITPro-EAC-AddIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="df2ea-174">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="df2ea-175">В списке тегов хранения выберите RPT элементов с возможностью восстановления, созданный на этапе 1, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="df2ea-175">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![Выберите настраиваемый тег хранения "Элементы с возможностью восстановления"](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="df2ea-p112">Выберите дополнительные теги, которые необходимо добавить к политике хранения. Например, может потребоваться добавить теги, которые уже включены в политику управления записями сообщений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="df2ea-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="df2ea-179">Добавив все теги хранения, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="df2ea-179">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="df2ea-180">Нажмите кнопку **Сохранить**, чтобы создать новую политику хранения.</span><span class="sxs-lookup"><span data-stu-id="df2ea-180">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="df2ea-181">Обратите внимание, что теги хранения, связанные с политикой хранения, отображаются в области сведений.</span><span class="sxs-lookup"><span data-stu-id="df2ea-181">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![Теги хранения, связанные с политикой хранения, в области сведений](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="df2ea-183">Создание политики хранения с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="df2ea-183">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="df2ea-184">Чтобы создать политику хранения для почтовых ящиков на удержании, выполните приведенную ниже команду. </span><span class="sxs-lookup"><span data-stu-id="df2ea-184">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="df2ea-185">Например, следующая команда создает политику хранения и связанные теги хранения, которые отображаются на предыдущем рисунке.</span><span class="sxs-lookup"><span data-stu-id="df2ea-185">For example, the following command creates the retention policy and linked retention tags that are displayed in the previous illustration.</span></span>
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="df2ea-186">Шаг 3. Применение новой политики хранения Exchange к почтовым ящикам на удержании</span><span class="sxs-lookup"><span data-stu-id="df2ea-186">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>

<span data-ttu-id="df2ea-187">Последний этап — применение новой политики хранения, созданной на этапе 2, к почтовым ящикам на удержании в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="df2ea-187">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="df2ea-188">Вы можете использовать EAC или Exchange Online PowerShell, чтобы применить политику хранения к одному или нескольким почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="df2ea-188">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="df2ea-189">Применение новой политики хранения с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="df2ea-189">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="df2ea-190">Перейдите **в**  >  **почтовые ящики получателей.**</span><span class="sxs-lookup"><span data-stu-id="df2ea-190">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="df2ea-191">В представлении списка выберите почтовый ящик, к который необходимо  применить политику хранения, и нажмите значок ![ редактирования. ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)</span><span class="sxs-lookup"><span data-stu-id="df2ea-191">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="df2ea-192">На странице **Изменить почтовый ящик пользователя** выберите пункт **Функции почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="df2ea-192">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="df2ea-193">В разделе **Политика хранения** выберите политику хранения, созданную на этапе 2, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="df2ea-193">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="df2ea-194">С помощью Центра администрирования Exchange можно также применить политику хранения к нескольким почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="df2ea-194">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="df2ea-195">Перейдите **в**  >  **почтовые ящики получателей.**</span><span class="sxs-lookup"><span data-stu-id="df2ea-195">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="df2ea-196">В представлении списка воспользуйтесь клавишами SHIFT или CTRL, чтобы выбрать несколько почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="df2ea-196">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="df2ea-197">В области сведений щелкните **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="df2ea-197">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="df2ea-198">В разделе **Политика хранения** щелкните **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="df2ea-198">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="df2ea-199">На странице **Массовое назначение политики хранения** выберите политику хранения, созданную на этапе 2, и нажмите кнопку **Сохранить**. </span><span class="sxs-lookup"><span data-stu-id="df2ea-199">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="df2ea-200">Применение новой политики хранения с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="df2ea-200">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="df2ea-201">С помощью Exchange Online PowerShell можно применить новую политику хранения к одному почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="df2ea-201">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="df2ea-202">Однако в настоящее время PowerShell можно использовать для быстрого определения всех почтовых ящиков в организации, которые находятся на хранении для судебного разбирательства или удержании In-Place, а затем применить новую политику хранения к всем почтовым ящикам на удержании одной командой.</span><span class="sxs-lookup"><span data-stu-id="df2ea-202">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="df2ea-203">Вот несколько примеров использования Exchange PowerShell для применения политики хранения к одному или нескольких почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="df2ea-203">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="df2ea-204">Во всех примерах применяется политика, созданная на этапе 2.</span><span class="sxs-lookup"><span data-stu-id="df2ea-204">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="df2ea-205">В этом примере новая политика хранения применяется к почтовому ящику пользователя Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="df2ea-205">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="df2ea-206">В этом примере показано, как применить созданную политику хранения ко всем почтовым ящикам в организации, находящимся на хранении для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="df2ea-206">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="df2ea-207">В этом примере показано, как применить созданную политику хранения ко всем почтовым ящикам в организации, находящимся на удержании на месте.</span><span class="sxs-lookup"><span data-stu-id="df2ea-207">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="df2ea-208">Чтобы проверить, применена ли новая политика хранения, используйте командлет **Get-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="df2ea-208">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="df2ea-209">Ниже показано несколько вариантов кода, позволяющих проверить, применили ли команды из предыдущих примеров политику "MRM Policy for Mailboxes on Hold" (Управление записями сообщений для почтовых ящиков на удержании) к почтовым ящикам, которые находятся на хранении для судебного разбирательства или на удержании на месте.</span><span class="sxs-lookup"><span data-stu-id="df2ea-209">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="df2ea-210">Этап 4 (необязательный). Запуск помощника по работе с управляемыми папками для применения новых параметров хранения</span><span class="sxs-lookup"><span data-stu-id="df2ea-210">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="df2ea-211">После применения новой политики хранения Exchange к почтовым ящикам на удержании может занять до 7 дней в Exchange Online, чтобы помощник по обработке управляемых папок обработать эти почтовые ящики с помощью параметров новой политики хранения.</span><span class="sxs-lookup"><span data-stu-id="df2ea-211">After you apply the new Exchange retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="df2ea-212">Вы можете не ожидать, пока будут обработаны ящики, к которым была применена новая политика хранения, а запустить помощника по работе с управляемыми папками вручную с помощью командлета **Start-ManagedFolderAssistant**.</span><span class="sxs-lookup"><span data-stu-id="df2ea-212">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="df2ea-213">Выполните приведенную ниже команду, чтобы запустить помощник по работе с управляемыми папками для почтового ящика пользователя Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="df2ea-213">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="df2ea-214">Выполните приведенную ниже команду, чтобы запустить помощник по работе с управляемыми папками для всех почтовых ящиков на удержании.</span><span class="sxs-lookup"><span data-stu-id="df2ea-214">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="df2ea-215">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="df2ea-215">More information</span></span>

- <span data-ttu-id="df2ea-216">После включения архивного почтового ящика рекомендуем сообщить пользователю о том, что в архивный почтовый ящик могут переместиться не только элементы из папки "Элементы с возможностью восстановления", но и другие.</span><span class="sxs-lookup"><span data-stu-id="df2ea-216">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="df2ea-217">Это необходимо, поскольку политика mrM по умолчанию, назначенная почтовым ящикам Exchange Online, содержит тег хранения (с именем "Перемещение в архив по умолчанию через 2 года"), который перемещает элементы в архивный почтовый ящик через два года после даты доставки элемента в почтовый ящик или создания пользователем.</span><span class="sxs-lookup"><span data-stu-id="df2ea-217">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="df2ea-218">Дополнительные сведения см. в [политике хранения по умолчанию в Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="df2ea-218">For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="df2ea-219">После включения архивного почтового ящика рекомендуем сообщить пользователю, что он может восстановить удаленные элементы благодаря папке "Элементы с возможностью восстановления" своего архивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="df2ea-219">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="df2ea-220">Это можно сделать в Outlook, выбрав папку **"Удаленные"** в архивном  почтовом ящике и нажав кнопку "Восстановить удаленные элементы с сервера" на вкладке **"Главная".** Дополнительные сведения о восстановлении удаленных элементов см. в теме "Восстановление удаленных элементов [в Outlook для Windows".](https://go.microsoft.com/fwlink/p/?LinkId=624829)</span><span class="sxs-lookup"><span data-stu-id="df2ea-220">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
