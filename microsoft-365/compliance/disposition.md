---
title: Расстановка контента
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Мониторинг и управление выбытием содержимого независимо от того, используется ли обзор ликвидации или содержимое автоматически удаляется в соответствии с настроенными параметрами.
ms.openlocfilehash: 8936289ccf42fa50b78b611c46742710cd035727
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678995"
---
# <a name="disposition-of-content"></a><span data-ttu-id="9c854-103">Расстановка контента</span><span class="sxs-lookup"><span data-stu-id="9c854-103">Disposition of content</span></span>

><span data-ttu-id="9c854-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="9c854-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="9c854-105">Используйте вкладку " **положение** " из списка " **Управление записями** " в центре соответствия требованиям Microsoft 365 для управления проверками расстановки и просмотра [записей](records.md) , которые были автоматически удалены в конце срока хранения.</span><span class="sxs-lookup"><span data-stu-id="9c854-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="9c854-106">Необходимые условия для просмотра расстановки содержимого</span><span class="sxs-lookup"><span data-stu-id="9c854-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="9c854-107">Для управления обзорами ликвидации и подтверждения того, что записи удалены, необходимо иметь достаточные разрешения, и аудит должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="9c854-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="9c854-108">Разрешения для ликвидации</span><span class="sxs-lookup"><span data-stu-id="9c854-108">Permissions for disposition</span></span>

<span data-ttu-id="9c854-109">Для успешного доступа к вкладке " **положение** " в центре соответствия требованиям Microsoft 365 необходимо быть участником роли **управления ликвидацией** и ролью " **журналы аудита только для просмотра** ".</span><span class="sxs-lookup"><span data-stu-id="9c854-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, you must be members of the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="9c854-110">Мы рекомендуем создать новую группу ролей с именем **проверяющих**и добавить эти две роли в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="9c854-110">We recommend creating a new role group called **Disposition Reviewers**, and add these two roles to that role group.</span></span> <span data-ttu-id="9c854-111">Даже если вы являетесь **глобальным пользователем администратора** , вам потребуется участие в роли **управления ликвидацией** , чтобы получить доступ к вкладке ликвидации.</span><span class="sxs-lookup"><span data-stu-id="9c854-111">Even if you are a **Global Admin** user, you will have to be part of the **Disposition Management** role for you to access the disposition tab.</span></span>

<span data-ttu-id="9c854-112">Относится только к роли **журналов аудита только для просмотра** :</span><span class="sxs-lookup"><span data-stu-id="9c854-112">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="9c854-113">Так как базовый командлет, используемый для поиска в журнале аудита, является командлетом Exchange Online, ему необходимо назначить эту роль с помощью [центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), а не с помощью страницы **разрешений** в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9c854-113">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="9c854-114">Инструкции см в разделе [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="9c854-114">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="9c854-115">Группы Microsoft 365 ([ранее группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) не поддерживаются для этой роли.</span><span class="sxs-lookup"><span data-stu-id="9c854-115">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="9c854-116">Вместо этого назначьте почтовые ящики пользователей, почтовые пользователи или группы безопасности с включенной поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="9c854-116">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="9c854-117">Инструкции по предоставлению пользователям роли **управления ликвидацией** и созданию новой роли **проверяющих проверяющих** можно узнать в статье [предоставление пользователям доступа к центру безопасности и &amp; соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9c854-117">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="9c854-118">Включение аудита</span><span class="sxs-lookup"><span data-stu-id="9c854-118">Enable auditing</span></span>

<span data-ttu-id="9c854-119">Убедитесь, что аудит включен по крайней мере один день перед первым действием ликвидации.</span><span class="sxs-lookup"><span data-stu-id="9c854-119">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="9c854-120">Дополнительные сведения можно найти в статье [Поиск в журнале аудита в центре безопасности и &amp; соответствия требованиям Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="9c854-120">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="9c854-121">Проверки перед ликвидацией</span><span class="sxs-lookup"><span data-stu-id="9c854-121">Disposition reviews</span></span>

<span data-ttu-id="9c854-122">Когда содержимое достигает окончания срока хранения, существует несколько причин, по которым может потребоваться проверить, можно ли его удалить ("удалено").</span><span class="sxs-lookup"><span data-stu-id="9c854-122">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="9c854-123">Например, может потребоваться выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9c854-123">For example, you might need to:</span></span>
  
- <span data-ttu-id="9c854-124">Приостановить удаление релевантного контента в случае судебного разбирательства или аудита.</span><span class="sxs-lookup"><span data-stu-id="9c854-124">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="9c854-125">Удаление контента из списка расстановки для хранения в архиве, если это содержимое содержит исследование или историческое значение.</span><span class="sxs-lookup"><span data-stu-id="9c854-125">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="9c854-126">Назначьте другой срок хранения содержимому, возможно, из-за того, что первоначальные параметры хранения были временными или предварительными решениями.</span><span class="sxs-lookup"><span data-stu-id="9c854-126">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="9c854-127">Возврат контента клиентам или их передача в другую организацию.</span><span class="sxs-lookup"><span data-stu-id="9c854-127">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="9c854-128">Когда проверка ликвидации инициируется в конце периода хранения:</span><span class="sxs-lookup"><span data-stu-id="9c854-128">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="9c854-129">Выбранные пользователи получат уведомление по электронной почте о том, что у них есть контент для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9c854-129">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="9c854-130">Такими проверяющими могут быть отдельные пользователи, группы рассылки или группы безопасности или группы безопасности Microsoft 365 ([ранее — группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span><span class="sxs-lookup"><span data-stu-id="9c854-130">These reviewers can be individual users, distribution or security groups, or Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span></span> <span data-ttu-id="9c854-131">Обратите внимание, что уведомления отправляются еженедельно.</span><span class="sxs-lookup"><span data-stu-id="9c854-131">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="9c854-132">Рецензенты отправляются на вкладку " **положение** " в центре соответствия требованиям Microsoft 365, чтобы проверить содержимое и решить, следует ли окончательно удалить его, продлить срок хранения или применить другую метку хранения.</span><span class="sxs-lookup"><span data-stu-id="9c854-132">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="9c854-133">Обзор ликвидации может включать контент в почтовые ящики Exchange, сайты SharePoint, учетные записи OneDrive и группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9c854-133">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="9c854-134">Содержимое, ожидающее проверки ликвидации в этих расположениях, удаляется только после того, как рецензент выберет окончательное удаление контента.</span><span class="sxs-lookup"><span data-stu-id="9c854-134">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="9c854-135">Для поддержки проверок расстановки в почтовом ящике должно быть по крайней мере 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="9c854-135">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="9c854-136">Обзор всех ожидающих расстановки можно просмотреть на вкладке **Обзор** . Например:</span><span class="sxs-lookup"><span data-stu-id="9c854-136">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Общие сведения о ожидающих отположениях в управлении записями](../media/dispositions-overview.png)

<span data-ttu-id="9c854-138">Когда вы выбираете **Просмотр всех ожидающих расстановки**, вы перейдете на страницу " **положение** ".</span><span class="sxs-lookup"><span data-stu-id="9c854-138">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="9c854-139">Например,</span><span class="sxs-lookup"><span data-stu-id="9c854-139">For example:</span></span>

![Страница "расположения" в центре соответствия требованиям Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="9c854-141">Рабочий процесс для проверки ликвидации</span><span class="sxs-lookup"><span data-stu-id="9c854-141">Workflow for a disposition review</span></span>

<span data-ttu-id="9c854-142">Это базовый рабочий процесс для проверки ликвидации, когда подпись хранения публикуется и затем вручную применяется пользователем.</span><span class="sxs-lookup"><span data-stu-id="9c854-142">This is the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="9c854-143">Кроме того, метка хранения, настроенная для проверки ликвидации, может быть автоматически применена к содержимому.</span><span class="sxs-lookup"><span data-stu-id="9c854-143">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Диаграмма, на которой показано, как работает процесс ликвидации](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="9c854-145">Включение проверки ликвидации в конце периода хранения — это параметр конфигурации, доступный только с [меткой хранения](labels.md).</span><span class="sxs-lookup"><span data-stu-id="9c854-145">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a [retention label](labels.md).</span></span> <span data-ttu-id="9c854-146">Этот параметр недоступен в политике хранения.</span><span class="sxs-lookup"><span data-stu-id="9c854-146">This option is not available in a retention policy.</span></span>
  
![Параметры хранения для метки](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="9c854-148">При выборе параметра **уведомлять этих пользователей о наличии элементов, готовых к просмотру**, укажите пользователя или группу безопасности с включенной поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="9c854-148">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="9c854-149">Группы Microsoft 365 ([ранее группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) не поддерживаются этим параметром.</span><span class="sxs-lookup"><span data-stu-id="9c854-149">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="9c854-150">Просмотр и удаление контента</span><span class="sxs-lookup"><span data-stu-id="9c854-150">Viewing and disposing of content</span></span>

<span data-ttu-id="9c854-151">Когда проверяющий получает уведомление по электронной почте о том, что контент готов к просмотру, он переходит на вкладку " **положение** " в разделе **Управление записями** в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9c854-151">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9c854-152">Проверяющие могут видеть, сколько элементов для каждой метки хранения ожидают расстановки, а затем выберите метку хранения, чтобы просмотреть все содержимое с этой меткой.</span><span class="sxs-lookup"><span data-stu-id="9c854-152">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="9c854-153">После выбора метки хранения вы увидите все ожидающие утверждения для этой метки на вкладке **Отложенное расположение** . Выберите один или несколько элементов, в которых можно выбрать действие и ввести комментарий по обоснования:</span><span class="sxs-lookup"><span data-stu-id="9c854-153">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Параметры расстановки](../media/retention-disposition-options.png)

<span data-ttu-id="9c854-155">Как видно на рисунке, поддерживаемые действия:</span><span class="sxs-lookup"><span data-stu-id="9c854-155">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="9c854-156">Окончательное удаление элемента</span><span class="sxs-lookup"><span data-stu-id="9c854-156">Permanently delete the item</span></span>
- <span data-ttu-id="9c854-157">Продление срока хранения</span><span class="sxs-lookup"><span data-stu-id="9c854-157">Extend the retention period</span></span>
- <span data-ttu-id="9c854-158">Применение другой метки хранения</span><span class="sxs-lookup"><span data-stu-id="9c854-158">Apply a different retention label</span></span>

<span data-ttu-id="9c854-159">Если у вас есть разрешения на доступ к расположению и содержимому, вы можете использовать ссылку в столбце " **Расположение** ", чтобы просматривать документы в их исходном расположении.</span><span class="sxs-lookup"><span data-stu-id="9c854-159">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="9c854-160">Во время проверки ликвидации содержимое никогда не перемещается из исходного расположения и никогда не удаляется до тех пор, пока проверяющий не решит это.</span><span class="sxs-lookup"><span data-stu-id="9c854-160">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="9c854-161">Уведомления по электронной почте автоматически отправляются рецензентам по неделям.</span><span class="sxs-lookup"><span data-stu-id="9c854-161">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="9c854-162">Этот запланированный процесс означает, что когда содержимое достигает окончания срока хранения, рецензентам может потребоваться до семи дней, чтобы рецензенты получали уведомление о том, что содержимое ожидает расстановки.</span><span class="sxs-lookup"><span data-stu-id="9c854-162">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="9c854-163">Все действия ликвидации можно подвергать аудиту, а текст выравнивания, введенный рецензентом, сохраняется и отображается в столбце **Comments** на странице **ликвидированных элементов** .</span><span class="sxs-lookup"><span data-stu-id="9c854-163">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="9c854-164">Время до окончательного удаления ликвидации контента</span><span class="sxs-lookup"><span data-stu-id="9c854-164">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="9c854-165">Контент, ожидающий проверки ликвидации, удаляется только после того, как рецензент выберет окончательное удаление контента.</span><span class="sxs-lookup"><span data-stu-id="9c854-165">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="9c854-166">Когда проверяющий выбирает этот параметр, контент на сайте SharePoint или в учетной записи OneDrive становится доступным для стандартного процесса очистки, описанного в разделе [как политика хранения работает с контентом на месте](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="9c854-166">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="9c854-167">Расстановка записей</span><span class="sxs-lookup"><span data-stu-id="9c854-167">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="9c854-168">Возможность просматривать записи, которые были автоматически удалены без проверки ликвидации, постепенно превышена до клиентов в течение апреля и мая 2020, поэтому вы можете не видеть этот интерфейс немедленно.</span><span class="sxs-lookup"><span data-stu-id="9c854-168">The ability to see records that were automatically deleted without a disposition review is gradually rolling out to tenants during April and May 2020, so you might not see this experience immediately.</span></span>

<span data-ttu-id="9c854-169">Используйте вкладку " **расстановка** " на странице " **Управление записями** ", чтобы определить записи, которые автоматически удаляются.</span><span class="sxs-lookup"><span data-stu-id="9c854-169">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="9c854-170">Эти элементы отображают **записи** , которые удалены в столбце **тип** .</span><span class="sxs-lookup"><span data-stu-id="9c854-170">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="9c854-171">Например,</span><span class="sxs-lookup"><span data-stu-id="9c854-171">For example:</span></span>

![Элементы, которые были удалены без проверки ликвидации](../media/records-disposed2.png)

<span data-ttu-id="9c854-173">Элементы, отображаемые на вкладке **выгруженных элементов** для меток записи, хранятся в течение 7 лет после удаления элемента с предельным числом 1 000 000 элементов на запись для этого периода.</span><span class="sxs-lookup"><span data-stu-id="9c854-173">Items that are shown in the **Disposed Items** tab for record labels are kept for up to 7 years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="9c854-174">Если вы **видите число, близкое к этому** ограничению 1 000 000, и вам требуется подтверждение расстановки записей, обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="9c854-174">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="9c854-175">Эта функция основана на сведениях из [единого журнала аудита](search-the-audit-log-in-security-and-compliance.md) и, следовательно, требует [включения и поиска](turn-audit-log-search-on-or-off.md) соответствующих событий.</span><span class="sxs-lookup"><span data-stu-id="9c854-175">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="9c854-176">Фильтрация и экспорт представлений</span><span class="sxs-lookup"><span data-stu-id="9c854-176">Filter and export the views</span></span>

<span data-ttu-id="9c854-177">При выборе метки хранения на странице **размещения** , вкладка **ожидающее расположение** (если это возможно) и вкладка **Удаленные элементы** позволяют фильтровать представления для упрощения поиска элементов.</span><span class="sxs-lookup"><span data-stu-id="9c854-177">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="9c854-178">Для ожидающих расстановки диапазон времени зависит от даты истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="9c854-178">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="9c854-179">Для списанных элементов диапазон времени зависит от даты удаления.</span><span class="sxs-lookup"><span data-stu-id="9c854-179">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="9c854-180">Вы можете экспортировать информацию о элементах в любом представлении в виде CSV-файла, который можно сортировать и управлять с помощью Excel:</span><span class="sxs-lookup"><span data-stu-id="9c854-180">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Параметр Export для ликвидации](../media/retention-export-option.png)
  
![Экспортированные данные о расположении в Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


