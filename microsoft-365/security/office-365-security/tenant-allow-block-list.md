---
title: Управление вашими допусками и блоками в списке разрешить или блокировать клиента
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться настраивать разрешит и блокирует в списке разрешить или заблокировать клиента на портале безопасности.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 960fbf26b610485fb46c935b04aedcc593b85752
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407254"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-103">Управление списком разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="1fceb-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1fceb-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="1fceb-104">**Applies to**</span></span>
- [<span data-ttu-id="1fceb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1fceb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1fceb-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="1fceb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="1fceb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fceb-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="1fceb-108">Функции, описанные в этой статье, находятся в предварительном просмотре, могут изменяться и недоступны во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="1fceb-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="1fceb-109">В настоящее время нельзя **настроить разрешенные** элементы в списке разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="1fceb-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="1fceb-110">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не согласиться с вердиктом по фильтрации EOP.</span><span class="sxs-lookup"><span data-stu-id="1fceb-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="1fceb-111">Например, хорошее сообщение может быть помечено как плохое (ложное положительное) или плохое сообщение может быть разрешено (ложное отрицательное).</span><span class="sxs-lookup"><span data-stu-id="1fceb-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="1fceb-112">Список разрешить или заблокировать клиента в Центре & безопасности позволяет вручную переопредировать решения по фильтрации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1fceb-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="1fceb-113">Список разрешить/заблокировать клиента используется во время потока почты и во время щелчков пользователя.</span><span class="sxs-lookup"><span data-stu-id="1fceb-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="1fceb-114">Вы можете указать URL-адреса или файлы, чтобы всегда блокировать.</span><span class="sxs-lookup"><span data-stu-id="1fceb-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="1fceb-115">В этой статье описывается настройка записей в Списке разрешения клиента или блока в Центре обеспечения безопасности & или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="1fceb-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1fceb-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="1fceb-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1fceb-117">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1fceb-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1fceb-118">Чтобы перейти непосредственно на **страницу Разрешить или заблокировать** список клиента, используйте <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="1fceb-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="1fceb-119">Вы указываете файлы, используя значение hash SHA256 для файла.</span><span class="sxs-lookup"><span data-stu-id="1fceb-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="1fceb-120">Чтобы найти значение hash SHA256 для файла в Windows, запустите следующую команду в командной подсказке:</span><span class="sxs-lookup"><span data-stu-id="1fceb-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="1fceb-121">Например, значение `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="1fceb-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="1fceb-122">Перцептивные значения hash (pHash) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1fceb-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="1fceb-123">Доступные значения URL-адресов описаны в синтаксисе [URL-адресов](#url-syntax-for-the-tenant-allowblock-list) для раздела "Разрешить или заблокировать список клиента" в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1fceb-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="1fceb-124">Список разрешить или блокировать клиента позволяет не более 500 записей для URL-адресов и 500 записей для хеш-файлов.</span><span class="sxs-lookup"><span data-stu-id="1fceb-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="1fceb-125">Запись должна быть активна в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="1fceb-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="1fceb-126">По умолчанию срок действия записей в списке разрешить или блокировать клиента истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="1fceb-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="1fceb-127">Вы можете указать дату или установить, чтобы срок их действия никогда не истек.</span><span class="sxs-lookup"><span data-stu-id="1fceb-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="1fceb-128">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1fceb-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1fceb-129">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1fceb-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1fceb-130">Вам необходимо получить разрешения в **Exchange Online,** прежде чем вы сможете сделать процедуры в этой статье:</span><span class="sxs-lookup"><span data-stu-id="1fceb-130">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1fceb-131">Чтобы добавить и удалить значения из списка "Разрешить или заблокировать клиента", необходимо быть членом группы ролей администратора организации или **администратора** безопасности. </span><span class="sxs-lookup"><span data-stu-id="1fceb-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="1fceb-132">Чтобы получить доступ только для чтения к списку разрешить или заблокировать клиента, необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="1fceb-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="1fceb-133">Дополнительные сведения см. в статье [Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="1fceb-133">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="1fceb-134">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="1fceb-134">**Notes**:</span></span>

  - <span data-ttu-id="1fceb-135">Добавление пользователей к соответствующей роли Azure Active Directory в центре администрирования Microsoft  365 дает пользователям необходимые разрешения и разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1fceb-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1fceb-136">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1fceb-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="1fceb-137">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="1fceb-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-138">Используйте Центр & безопасности для создания записей URL-адресов в списке разрешить или блокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1fceb-139">Подробные сведения о синтаксисе записей URL-адресов см. в разделе [Синтаксис](#url-syntax-for-the-tenant-allowblock-list) URL-адресов для раздела Разрешить или заблокировать список клиента в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1fceb-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="1fceb-140">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="1fceb-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1fceb-141">На странице **Разрешить или заблокировать** список клиента убедитесь, что выбрана вкладка URL-адресов, а затем нажмите **кнопку Блок** </span><span class="sxs-lookup"><span data-stu-id="1fceb-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="1fceb-142">В **вылете** url-адресов блока, который отображается, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1fceb-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1fceb-143">**Добавление URL-адресов для блокировки:** введите один URL-адрес на строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="1fceb-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1fceb-144">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1fceb-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1fceb-145">Проверьте отключение параметра (Отключение) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. </span><span class="sxs-lookup"><span data-stu-id="1fceb-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1fceb-146">или</span><span class="sxs-lookup"><span data-stu-id="1fceb-146">or</span></span>

     - <span data-ttu-id="1fceb-147">Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия:</span><span class="sxs-lookup"><span data-stu-id="1fceb-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="1fceb-149">.</span><span class="sxs-lookup"><span data-stu-id="1fceb-149">.</span></span>

   - <span data-ttu-id="1fceb-150">**Необязательный** примечание. Введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="1fceb-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1fceb-151">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1fceb-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-152">Используйте Центр & безопасности для создания записей файлов в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1fceb-153">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="1fceb-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1fceb-154">На странице **Разрешить или блокировать** список клиента выберите вкладку **Файлы** и нажмите **кнопку Блок**.</span><span class="sxs-lookup"><span data-stu-id="1fceb-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="1fceb-155">В **добавлении файлов для блокировки** вылетов, которые появляются, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1fceb-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1fceb-156">**Добавление хеша файла:** введите одно хеш-значение SHA256 за строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="1fceb-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1fceb-157">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1fceb-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1fceb-158">Проверьте отключение параметра (Отключение) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. </span><span class="sxs-lookup"><span data-stu-id="1fceb-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1fceb-159">или</span><span class="sxs-lookup"><span data-stu-id="1fceb-159">or</span></span>

     - <span data-ttu-id="1fceb-160">Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия:</span><span class="sxs-lookup"><span data-stu-id="1fceb-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="1fceb-162">.</span><span class="sxs-lookup"><span data-stu-id="1fceb-162">.</span></span>

   - <span data-ttu-id="1fceb-163">**Необязательный** примечание. Введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="1fceb-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1fceb-164">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1fceb-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-165">Используйте Центр & безопасности для просмотра записей в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1fceb-166">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="1fceb-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1fceb-167">Выберите **вкладку URL-адреса** или **вкладку Files.**</span><span class="sxs-lookup"><span data-stu-id="1fceb-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="1fceb-168">Нажмите на следующие заголовки столбца, чтобы отсортироваться в порядке по возрастанию или убыванию:</span><span class="sxs-lookup"><span data-stu-id="1fceb-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="1fceb-169">**Значение:** URL-адрес или hash файла.</span><span class="sxs-lookup"><span data-stu-id="1fceb-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="1fceb-170">**Последняя обновленная дата**</span><span class="sxs-lookup"><span data-stu-id="1fceb-170">**Last updated date**</span></span>
- <span data-ttu-id="1fceb-171">**Срок действия**</span><span class="sxs-lookup"><span data-stu-id="1fceb-171">**Expiration date**</span></span>
- <span data-ttu-id="1fceb-172">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="1fceb-172">**Note**</span></span>

<span data-ttu-id="1fceb-173">Щелкните **Поиск,** введите все или часть значения, а затем нажмите КНОПКУ ВВОДА, чтобы найти определенное значение.</span><span class="sxs-lookup"><span data-stu-id="1fceb-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="1fceb-174">По завершению щелкните **значок Clear Search** Clear search ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="1fceb-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="1fceb-175">Щелкните **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="1fceb-175">Click **Filter**.</span></span> <span data-ttu-id="1fceb-176">В **вылете Filter,** который отображается, настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="1fceb-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="1fceb-177">**Никогда не истекает:** Выберите отключение: ![ отключите или ](../../media/scc-toggle-off.png) включите. ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="1fceb-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="1fceb-178">**Последнее обновление:** Выберите дату начала **(Из**), даты окончания **(To)** или обоих.</span><span class="sxs-lookup"><span data-stu-id="1fceb-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="1fceb-179">**Срок действия:** Выберите дату начала **(От),** даты окончания **(к)** или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="1fceb-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="1fceb-180">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="1fceb-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="1fceb-181">Чтобы очистить существующие фильтры, **щелкните Фильтр,** а в вылете **Фильтр,** который появится, щелкните **Очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="1fceb-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-182">Используйте Центр & безопасности для изменения записей блоков в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1fceb-183">Вы не можете изменить существующие заблокированные URL-адрес или значения файлов в записи.</span><span class="sxs-lookup"><span data-stu-id="1fceb-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="1fceb-184">Чтобы изменить эти значения, необходимо удалить и воссоздать запись.</span><span class="sxs-lookup"><span data-stu-id="1fceb-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="1fceb-185">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="1fceb-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1fceb-186">Выберите **вкладку URL-адреса** или **вкладку Files.**</span><span class="sxs-lookup"><span data-stu-id="1fceb-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="1fceb-187">Выберите блок-запись, которую необходимо изменить, а затем нажмите **кнопку Изменить значок Редактирование** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="1fceb-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="1fceb-188">В вылете, который отображается, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1fceb-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1fceb-189">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1fceb-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1fceb-190">Убедитесь, что параметр отключен (отключается) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записи. </span><span class="sxs-lookup"><span data-stu-id="1fceb-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="1fceb-191">или</span><span class="sxs-lookup"><span data-stu-id="1fceb-191">or</span></span>

     - <span data-ttu-id="1fceb-192">Перемещение точки вправо, чтобы настроить запись, чтобы не истек срок действия:</span><span class="sxs-lookup"><span data-stu-id="1fceb-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="1fceb-194">.</span><span class="sxs-lookup"><span data-stu-id="1fceb-194">.</span></span>

   - <span data-ttu-id="1fceb-195">**Необязательный примечание.** Введите описательный текст для записи.</span><span class="sxs-lookup"><span data-stu-id="1fceb-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="1fceb-196">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1fceb-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-197">Используйте Центр & безопасности для удаления блоковых записей из списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1fceb-198">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="1fceb-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1fceb-199">Выберите **вкладку URL-адреса** или **вкладку Files.**</span><span class="sxs-lookup"><span data-stu-id="1fceb-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="1fceb-200">Выберите блок-запись, которую необходимо удалить, а затем нажмите **кнопку Удалить значок Удалить** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="1fceb-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="1fceb-201">В диалоговом октаге предупреждения нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1fceb-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-202">Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки списка разрешить/заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-203">Использование PowerShell для добавления записей блоков в список разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="1fceb-204">Чтобы добавить блоковые записи в список разрешить или блокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1fceb-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="1fceb-205">В этом примере добавляется запись URL-адреса contoso.com всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1fceb-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="1fceb-206">Поскольку мы не использовали параметры ExpireDate или NoExpiration, срок действия записи истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="1fceb-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="1fceb-207">В этом примере добавляется запись заблокированного файла для указанных файлов, срок действия которых никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="1fceb-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="1fceb-208">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="1fceb-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-209">Использование PowerShell для просмотра записей в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1fceb-210">Чтобы просмотреть записи в списке разрешить или блокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1fceb-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="1fceb-211">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="1fceb-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="1fceb-212">В этом примере возвращается информация для указанного значения hash файла.</span><span class="sxs-lookup"><span data-stu-id="1fceb-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="1fceb-213">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="1fceb-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-214">Использование PowerShell для изменения записей блоков в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1fceb-215">Вы не можете изменить существующие значения URL-адресов или файлов в блок-записи.</span><span class="sxs-lookup"><span data-stu-id="1fceb-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="1fceb-216">Чтобы изменить эти значения, необходимо удалить и воссоздать запись.</span><span class="sxs-lookup"><span data-stu-id="1fceb-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="1fceb-217">Чтобы изменить записи блокировки в списке разрешить или блокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1fceb-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="1fceb-218">В этом примере изменяется срок действия указанной блок-записи.</span><span class="sxs-lookup"><span data-stu-id="1fceb-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="1fceb-219">Подробные сведения о синтаксисе и параметрах см. в [ссылке Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="1fceb-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-220">Использование PowerShell для удаления записей блокировки из списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="1fceb-221">Чтобы удалить блоковые записи из списка "Разрешить или блокировать клиента", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1fceb-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="1fceb-222">В этом примере удаляется указанная запись URL-адреса блокировки из списка разрешить или блокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="1fceb-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="1fceb-223">Подробные сведения о синтаксисе и параметрах см. в [ссылке Remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="1fceb-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="1fceb-224">Синтаксис URL-адреса для списка разрешить или блокировать клиента</span><span class="sxs-lookup"><span data-stu-id="1fceb-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="1fceb-225">Ip4v и IPv6-адреса разрешены, но порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="1fceb-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="1fceb-226">Расширения filename не разрешены (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="1fceb-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="1fceb-227">Юникод не поддерживается, но Punycode есть.</span><span class="sxs-lookup"><span data-stu-id="1fceb-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="1fceb-228">Имена хост-кодов разрешены, если все следующие утверждения верны:</span><span class="sxs-lookup"><span data-stu-id="1fceb-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="1fceb-229">Имя хост-пользователя содержит период.</span><span class="sxs-lookup"><span data-stu-id="1fceb-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="1fceb-230">Существует по крайней мере один символ слева от периода.</span><span class="sxs-lookup"><span data-stu-id="1fceb-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="1fceb-231">Справа от периода имеется по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="1fceb-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="1fceb-232">Например, `t.co` разрешено или `.com` `contoso.` запрещено.</span><span class="sxs-lookup"><span data-stu-id="1fceb-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="1fceb-233">Subpaths не подразумеваются.</span><span class="sxs-lookup"><span data-stu-id="1fceb-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="1fceb-234">Например, `contoso.com` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="1fceb-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="1fceb-235">Поддиальды (\*) разрешены в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="1fceb-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="1fceb-236">За левой подгруппой должен следовать период, чтобы указать поддомен.</span><span class="sxs-lookup"><span data-stu-id="1fceb-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="1fceb-237">Например, `*.contoso.com` разрешено; `*contoso.com` запрещено.</span><span class="sxs-lookup"><span data-stu-id="1fceb-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="1fceb-238">Правая подмайка должна следовать за полосой вперед (/), чтобы указать путь.</span><span class="sxs-lookup"><span data-stu-id="1fceb-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="1fceb-239">Например, `contoso.com/*` разрешено или `contoso.com*` `contoso.com/ab*` запрещено.</span><span class="sxs-lookup"><span data-stu-id="1fceb-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="1fceb-240">Все подпаты не подразумеваются правой подгруппой.</span><span class="sxs-lookup"><span data-stu-id="1fceb-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="1fceb-241">Например, `contoso.com/*` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="1fceb-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="1fceb-242">`*.com*` является недействительным (не разрешимый домен, а правая подкратная карточка не следует передовую черту).</span><span class="sxs-lookup"><span data-stu-id="1fceb-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="1fceb-243">В IP-адресах запрещено использовать поддиальдные знаки.</span><span class="sxs-lookup"><span data-stu-id="1fceb-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="1fceb-244">Символ tilde (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="1fceb-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="1fceb-245">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="1fceb-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="1fceb-246">Например, `~contoso.com` включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="1fceb-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="1fceb-247">Записи URL-адресов, содержащие протоколы (например, или ) не будут работать, так как URL-записи применяются `http://` `https://` к всем `ftp://` протоколам.</span><span class="sxs-lookup"><span data-stu-id="1fceb-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="1fceb-248">Имя пользователя или пароль не поддерживаются или не требуются.</span><span class="sxs-lookup"><span data-stu-id="1fceb-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="1fceb-249">Кавычка (' или ") являются недействительными символами.</span><span class="sxs-lookup"><span data-stu-id="1fceb-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="1fceb-250">URL-адрес должен включать все перенаправления, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="1fceb-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="1fceb-251">Сценарии ввода URL-адресов</span><span class="sxs-lookup"><span data-stu-id="1fceb-251">URL entry scenarios</span></span>

<span data-ttu-id="1fceb-252">Допустимые записи URL-адресов и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="1fceb-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="1fceb-253">Сценарий: нет поддиальдов</span><span class="sxs-lookup"><span data-stu-id="1fceb-253">Scenario: No wildcards</span></span>

<span data-ttu-id="1fceb-254">**Запись:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1fceb-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="1fceb-255">**Разрешить совпадение:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="1fceb-256">**Разрешить не совпадать:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="1fceb-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-257">abc-contoso.com</span></span>
  - <span data-ttu-id="1fceb-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1fceb-258">contoso.com/a</span></span>
  - <span data-ttu-id="1fceb-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="1fceb-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="1fceb-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1fceb-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-262">www.contoso.com</span></span>
  - <span data-ttu-id="1fceb-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="1fceb-264">**Совпадение блоков:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-264">**Block match**:</span></span>

  - <span data-ttu-id="1fceb-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-265">contoso.com</span></span>
  - <span data-ttu-id="1fceb-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1fceb-266">contoso.com/a</span></span>
  - <span data-ttu-id="1fceb-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="1fceb-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="1fceb-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1fceb-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-270">www.contoso.com</span></span>
  - <span data-ttu-id="1fceb-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="1fceb-272">**Блок не соответствует**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="1fceb-273">Сценарий: левая подгруппа (subdomain)</span><span class="sxs-lookup"><span data-stu-id="1fceb-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="1fceb-274">**Запись:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1fceb-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="1fceb-275">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1fceb-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-276">www.contoso.com</span></span>
  - <span data-ttu-id="1fceb-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1fceb-278">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1fceb-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-279">123contoso.com</span></span>
  - <span data-ttu-id="1fceb-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-280">contoso.com</span></span>
  - <span data-ttu-id="1fceb-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="1fceb-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1fceb-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="1fceb-283">Сценарий: правая под диктовка в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="1fceb-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="1fceb-284">**Запись:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="1fceb-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="1fceb-285">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1fceb-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="1fceb-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="1fceb-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1fceb-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1fceb-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="1fceb-289">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1fceb-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-290">contoso.com</span></span>
  - <span data-ttu-id="1fceb-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1fceb-291">contoso.com/a</span></span>
  - <span data-ttu-id="1fceb-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-292">www.contoso.com</span></span>
  - <span data-ttu-id="1fceb-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="1fceb-294">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="1fceb-294">Scenario: Left tilde</span></span>

<span data-ttu-id="1fceb-295">**Запись:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1fceb-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="1fceb-296">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1fceb-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-297">contoso.com</span></span>
  - <span data-ttu-id="1fceb-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-298">www.contoso.com</span></span>
  - <span data-ttu-id="1fceb-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1fceb-300">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1fceb-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-301">123contoso.com</span></span>
  - <span data-ttu-id="1fceb-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1fceb-302">contoso.com/abc</span></span>
  - <span data-ttu-id="1fceb-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1fceb-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="1fceb-304">Сценарий: суффикс правой подстановки</span><span class="sxs-lookup"><span data-stu-id="1fceb-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="1fceb-305">**Запись:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1fceb-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="1fceb-306">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1fceb-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="1fceb-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1fceb-308">contoso.com/a</span></span>
  - <span data-ttu-id="1fceb-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1fceb-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1fceb-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1fceb-310">contoso.com/ab</span></span>
  - <span data-ttu-id="1fceb-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1fceb-311">contoso.com/b</span></span>
  - <span data-ttu-id="1fceb-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1fceb-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1fceb-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1fceb-313">contoso.com/ba</span></span>

- <span data-ttu-id="1fceb-314">**Разрешить не совпадать** и **блок не совпадает**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="1fceb-315">Сценарий. Поддомайн левой подстановки и суффикс правой подстановки</span><span class="sxs-lookup"><span data-stu-id="1fceb-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="1fceb-316">**Запись:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1fceb-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="1fceb-317">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1fceb-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1fceb-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="1fceb-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1fceb-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1fceb-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1fceb-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="1fceb-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1fceb-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1fceb-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1fceb-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="1fceb-323">**Разрешить не совпадать** и **блок не соответствует**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1fceb-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="1fceb-324">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="1fceb-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="1fceb-325">**Запись:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="1fceb-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="1fceb-326">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1fceb-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-327">contoso.com</span></span>
  - <span data-ttu-id="1fceb-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1fceb-328">contoso.com/a</span></span>
  - <span data-ttu-id="1fceb-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-329">www.contoso.com</span></span>
  - <span data-ttu-id="1fceb-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1fceb-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="1fceb-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1fceb-332">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1fceb-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-333">123contoso.com</span></span>
  - <span data-ttu-id="1fceb-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="1fceb-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="1fceb-335">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1fceb-335">Scenario: IP address</span></span>

<span data-ttu-id="1fceb-336">**Запись:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="1fceb-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="1fceb-337">**Разрешить совпадение** **и блокировку:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1fceb-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="1fceb-338">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1fceb-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1fceb-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="1fceb-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1fceb-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="1fceb-341">IP-адрес с правой подголой карточкой</span><span class="sxs-lookup"><span data-stu-id="1fceb-341">IP address with right wildcard</span></span>

<span data-ttu-id="1fceb-342">**Запись:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="1fceb-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="1fceb-343">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1fceb-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="1fceb-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="1fceb-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="1fceb-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="1fceb-346">Примеры недействительных записей</span><span class="sxs-lookup"><span data-stu-id="1fceb-346">Examples of invalid entries</span></span>

<span data-ttu-id="1fceb-347">Следующие записи являются недействительными:</span><span class="sxs-lookup"><span data-stu-id="1fceb-347">The following entries are invalid:</span></span>

- <span data-ttu-id="1fceb-348">**Отсутствующие или недействительные значения домена:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="1fceb-349">contoso</span><span class="sxs-lookup"><span data-stu-id="1fceb-349">contoso</span></span>
  - <span data-ttu-id="1fceb-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="1fceb-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="1fceb-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-351">\*.com</span></span>
  - <span data-ttu-id="1fceb-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="1fceb-352">\*.pdf</span></span>

- <span data-ttu-id="1fceb-353">**Под диктовка текста или без интервалов символов:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="1fceb-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-354">\*contoso.com</span></span>
  - <span data-ttu-id="1fceb-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="1fceb-355">contoso.com\*</span></span>
  - <span data-ttu-id="1fceb-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1fceb-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="1fceb-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="1fceb-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="1fceb-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="1fceb-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="1fceb-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="1fceb-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="1fceb-360">**IP-адреса с портами:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="1fceb-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="1fceb-361">contoso.com:443</span></span>
  - <span data-ttu-id="1fceb-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="1fceb-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="1fceb-363">**Неописуемые подражательные знаки:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="1fceb-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="1fceb-364">\*.\*</span></span>

- <span data-ttu-id="1fceb-365">**Средние подкарды:**</span><span class="sxs-lookup"><span data-stu-id="1fceb-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="1fceb-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-366">conto\*so.com</span></span>
  - <span data-ttu-id="1fceb-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="1fceb-367">conto~so.com</span></span>

- <span data-ttu-id="1fceb-368">**Двойные подкарды**</span><span class="sxs-lookup"><span data-stu-id="1fceb-368">**Double wildcards**</span></span>

  - <span data-ttu-id="1fceb-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="1fceb-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="1fceb-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="1fceb-370">contoso.com/\*/\*</span></span>
