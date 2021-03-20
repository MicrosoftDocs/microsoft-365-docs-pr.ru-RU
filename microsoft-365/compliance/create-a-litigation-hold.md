---
title: Создание удержания для судебного разбирательства
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Узнайте, как разместить почтовый ящик в удержании судебного разбирательства, сохранив все содержимое почтового ящика во время расследования.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 046ee6fdc7c42026b1a69805883175982e3100b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908403"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="33bb4-103">Создание удержания для судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="33bb4-103">Create a Litigation Hold</span></span>

<span data-ttu-id="33bb4-104">Вы можете разместить почтовый ящик в удержании судебного разбирательства, чтобы сохранить все содержимое почтовых ящиков, включая удаленные элементы и оригинальные версии измененных элементов.</span><span class="sxs-lookup"><span data-stu-id="33bb4-104">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="33bb4-105">При найме почтового ящика пользователя на удержание судебного разбирательства содержимое архивного почтового ящика пользователя (если включено) также сохраняется.</span><span class="sxs-lookup"><span data-stu-id="33bb4-105">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="33bb4-106">При создании удержания можно указать продолжительность удержания (также называемую удержанием на основе времени), чтобы удаленные и измененные элементы сохраняли в течение указанного периода и затем окончательно удалялись из почтового ящика. </span><span class="sxs-lookup"><span data-stu-id="33bb4-106">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="33bb4-107">Или вы можете просто хранить контент на неопределенный срок (называется *бесконечным* удержанием) или до тех пор, пока не будет удалено удержание судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="33bb4-107">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="33bb4-108">Если указать период длительности удержания, он рассчитывается с даты, когда будет получено сообщение или будет создан элемент почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="33bb4-108">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="33bb4-109">Вот что происходит при создании судебного удержания.</span><span class="sxs-lookup"><span data-stu-id="33bb4-109">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="33bb4-110">Элементы, которые постоянно удаляются пользователем, сохраняются в папке "Извлекаемые элементы" в почтовом ящике пользователя на время удержания.</span><span class="sxs-lookup"><span data-stu-id="33bb4-110">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="33bb4-111">Элементы, извлекаемые пользователем из папки "Извлекаемые элементы", сохраняются на время удержания.</span><span class="sxs-lookup"><span data-stu-id="33bb4-111">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="33bb4-112">Квота хранилища для папки "Извлекаемые элементы" увеличивается с 30 ГБ до 110 ГБ.</span><span class="sxs-lookup"><span data-stu-id="33bb4-112">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="33bb4-113">Элементы в основных и архивных почтовых ящиках пользователя сохраняются</span><span class="sxs-lookup"><span data-stu-id="33bb4-113">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="assign-an-exchange-online-plan-2-license"></a><span data-ttu-id="33bb4-114">Назначение лицензии Exchange Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="33bb4-114">Assign an Exchange Online Plan 2 license</span></span>

- <span data-ttu-id="33bb4-115">Чтобы разместить почтовый ящик Exchange Online на удержание судебного разбирательства, ему должна быть назначена лицензия Exchange Online Plan 2.</span><span class="sxs-lookup"><span data-stu-id="33bb4-115">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="33bb4-116">Если почтовому ящику назначена лицензия Exchange Online Plan 1, необходимо назначить ему отдельную лицензию архивация на базе Exchange Online для ее удержания.</span><span class="sxs-lookup"><span data-stu-id="33bb4-116">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="33bb4-117">Перевод почтового ящика в режим хранения для судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="33bb4-117">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="33bb4-118">Ниже 1. Действия, необходимые для того, чтобы разместить почтовый ящик в удержании судебного разбирательства с помощью центра администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="33bb4-118">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="33bb4-119">Перейдите [https://outlook.office.com/ecp](https://outlook.office.com/ecp) и войдите в свою учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="33bb4-119">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="33bb4-120">Щелкните **Получатели > почтовые ящики в** левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="33bb4-120">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="33bb4-121">Выберите почтовый ящик, который необходимо разместить в удержании судебного разбирательства, а затем нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="33bb4-121">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="33bb4-122">На странице свойств почтового ящика щелкните **Функции почтового ящика**.</span><span class="sxs-lookup"><span data-stu-id="33bb4-122">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="33bb4-123">В разделе **Хранение для судебного разбирательства: отключено** нажмите кнопку **Включить**, чтобы применить к почтовому ящику хранение для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="33bb4-123">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="33bb4-124">На странице **Удержание судебного разбирательства** введите следующие необязательные сведения:</span><span class="sxs-lookup"><span data-stu-id="33bb4-124">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="33bb4-125">**Длительность хранения (дни)** для судебного разбирательства . Используйте это поле для создания удержания на основе времени и укажите, как долго находятся элементы почтовых ящиков при размещении почтового ящика в удержании судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="33bb4-125">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="33bb4-126">Этот срок рассчитывается с даты получения или создания элемента почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="33bb4-126">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="33bb4-127">По истечении срока действия удержания для определенного элемента этот элемент больше не будет сохраняться.</span><span class="sxs-lookup"><span data-stu-id="33bb4-127">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="33bb4-128">Если оставить это поле пустым, элементы сохраняются на неопределенный срок или до удаления удержания.</span><span class="sxs-lookup"><span data-stu-id="33bb4-128">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="33bb4-129">Длительность указывается в днях.</span><span class="sxs-lookup"><span data-stu-id="33bb4-129">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="33bb4-130">**Примечание.** Используйте это поле, чтобы сообщить пользователю, что его почтовый ящик находится в удержании судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="33bb4-130">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="33bb4-131">Примечание появится на странице Сведения об учетной записи в почтовом ящике пользователя, если они используют Outlook 2010 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="33bb4-131">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="33bb4-132">Чтобы получить доступ к этой странице, пользователи могут **щелкнуть Файл в** Outlook.</span><span class="sxs-lookup"><span data-stu-id="33bb4-132">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="33bb4-133">**URL-адрес** . Используйте это поле, чтобы направить пользователя на веб-сайт, чтобы получить дополнительные сведения о удержании судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="33bb4-133">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="33bb4-134">Этот URL-адрес отображается на странице Сведения о учетной записи в почтовом ящике пользователя, если он использует Outlook 2010 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="33bb4-134">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="33bb4-135">Чтобы получить доступ к этой странице, пользователи могут щелкнуть **Файл** в Outlook..</span><span class="sxs-lookup"><span data-stu-id="33bb4-135">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="33bb4-136">Нажмите **кнопку Сохранить** на странице **Удержание** судебного разбирательства, а затем нажмите **сохранить** на странице свойства почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="33bb4-136">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="33bb4-137">Создание судебного удержания с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="33bb4-137">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="33bb4-138">Вы также можете создать удержание для судебного разбирательства, запуская следующую команду [в Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="33bb4-138">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="33bb4-139">Предыдущая команда сохраняет элементы бесконечно, так как продолжительность удержания не указана.</span><span class="sxs-lookup"><span data-stu-id="33bb4-139">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="33bb4-140">Чтобы создать удержание на основе времени, используя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="33bb4-140">To created a time-based hold, using the following command:</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="33bb4-141">Дополнительные сведения см. в статье [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="33bb4-141">For more information, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="33bb4-142">Как работает хранение для судебного разбирательства?</span><span class="sxs-lookup"><span data-stu-id="33bb4-142">How does Litigation Hold work?</span></span>

<span data-ttu-id="33bb4-143">Если почтовый ящик не на хранении, после удаления с помощью клавиш Shift+Delete или удаления из папки "Удаленные" элемент перемещается в подпапку удаления в папке "Элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="33bb4-143">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="33bb4-144">По истечении срока хранения, заданного политикой удаления (тег хранения, для которого настроено действие хранения), элементы также перемещаются в подпапку удаления.</span><span class="sxs-lookup"><span data-stu-id="33bb4-144">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="33bb4-145">Когда пользователь удаляет элемент в папке "Элементы с возможностью восстановления" или истекает срок хранения удаленного элемента, он перемещается в подпапку очистки и помечается для окончательного удаления.</span><span class="sxs-lookup"><span data-stu-id="33bb4-145">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="33bb4-146">Он будет удален из Exchange при следующей обработке почтового ящика помощником для управляемых папок.</span><span class="sxs-lookup"><span data-stu-id="33bb4-146">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="33bb4-p108">Если почтовый ящик находится на хранении для судебного разбирательства, элементы в подпапке очистки хранятся в течение указанного срока. Срок хранения рассчитывается от даты получения или создания элемента. По истечении срока хранения элемент в подпапке очистки помечается для окончательного удаления и удаляется из Exchange при следующей обработке почтового ящика помощником для управляемых папок. Если почтовый ящик помещен на бессрочное хранение, элементы никогда не удаляются из подпапки очистки.</span><span class="sxs-lookup"><span data-stu-id="33bb4-p108">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="33bb4-151">На следующем рисунке показаны подпапки в папке "Элементы с возможностью восстановления" и рабочий процесс хранения.</span><span class="sxs-lookup"><span data-stu-id="33bb4-151">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![Судебный цикл удержания](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="33bb4-153">Если удержание, связанное с случаем обнаружения электронных данных, помещается в почтовый ящик, удаленные элементы перемещаются из подложки Deletions в подмостки DiscoveryHolds и сохраняются до тех пор, пока почтовый ящик не будет освобожден из трюма обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="33bb4-153">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
