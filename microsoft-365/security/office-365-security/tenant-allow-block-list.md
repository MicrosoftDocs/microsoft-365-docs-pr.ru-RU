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
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538967"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="57056-103">Управление списком разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="57056-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="57056-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="57056-104">**Applies to**</span></span>
- [<span data-ttu-id="57056-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="57056-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="57056-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="57056-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="57056-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57056-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="57056-108">Функции, описанные в этой статье, находятся в предварительном просмотре, могут изменяться и недоступны во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="57056-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="57056-109">Если в вашей организации нет функций подмены, как описано в этой статье, см. более старый опыт управления подменой в manage [spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="57056-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="57056-110">В данный момент нельзя **настроить** разрешенный URL-адрес или элементы файлов в списке разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="57056-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="57056-111">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков, вы можете не согласиться с вердиктом по фильтрации EOP.</span><span class="sxs-lookup"><span data-stu-id="57056-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="57056-112">Например, хорошее сообщение может быть помечено как плохое (ложное положительное) или плохое сообщение может быть разрешено (ложное отрицательное).</span><span class="sxs-lookup"><span data-stu-id="57056-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="57056-113">Список разрешить или заблокировать клиента в Центре & безопасности позволяет вручную переопредировать решения по Microsoft 365 фильтрации.</span><span class="sxs-lookup"><span data-stu-id="57056-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="57056-114">Список разрешить/заблокировать клиента используется во время потока почты и во время щелчков пользователя.</span><span class="sxs-lookup"><span data-stu-id="57056-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="57056-115">Можно указать следующие типы переопределей:</span><span class="sxs-lookup"><span data-stu-id="57056-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="57056-116">URL-адреса для блокировки.</span><span class="sxs-lookup"><span data-stu-id="57056-116">URLs to block.</span></span>
- <span data-ttu-id="57056-117">Файлы для блокировки.</span><span class="sxs-lookup"><span data-stu-id="57056-117">Files to block.</span></span>
- <span data-ttu-id="57056-118">Массовые домены отправитель почты, чтобы разрешить.</span><span class="sxs-lookup"><span data-stu-id="57056-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="57056-119">Дополнительные сведения о массовой почте, уровне массовой уверенности (BCL) и массовой фильтрации почты политиками защиты от нежелательной почты см. в сообщении [Bulk complaint level (BCL) в EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="57056-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="57056-120">Spoofed senders to allow or block.</span><span class="sxs-lookup"><span data-stu-id="57056-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="57056-121">Если переопределять решение разрешить [](learn-about-spoof-intelligence.md)или заблокировать в анализе подмены сведений, подмена отправитель становится ручным разрешением или блокировкой записи, которая отображается только на вкладке **Spoof** в списке разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="57056-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="57056-122">Вы также можете вручную создавать записи для подмены отправителей, прежде чем они будут обнаружены с помощью подмены.</span><span class="sxs-lookup"><span data-stu-id="57056-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="57056-123">В этой статье описывается настройка записей в Списке разрешения клиента или блока в Центре обеспечения безопасности & или в PowerShell (Exchange Online PowerShell для Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без Exchange Online почтовых ящиков).</span><span class="sxs-lookup"><span data-stu-id="57056-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="57056-124">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="57056-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="57056-125">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="57056-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="57056-126">Чтобы перейти непосредственно на **страницу Разрешить или заблокировать** список клиента, используйте <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="57056-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="57056-127">Вы указываете файлы, используя значение hash SHA256 для файла.</span><span class="sxs-lookup"><span data-stu-id="57056-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="57056-128">Чтобы найти значение hash SHA256 для файла в Windows, запустите следующую команду в командной подсказке:</span><span class="sxs-lookup"><span data-stu-id="57056-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="57056-129">Например, значение `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="57056-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="57056-130">Перцептивные значения hash (pHash) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="57056-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="57056-131">Доступные значения URL-адресов описаны в синтаксисе [URL-адресов](#url-syntax-for-the-tenant-allowblock-list) для раздела "Разрешить или заблокировать список клиента" в этой статье.</span><span class="sxs-lookup"><span data-stu-id="57056-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="57056-132">Список разрешить или блокировать клиента позволяет не более 500 записей для URL-адресов и 500 записей для хеш-файлов.</span><span class="sxs-lookup"><span data-stu-id="57056-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="57056-133">Максимальное количество символов для каждой записи:</span><span class="sxs-lookup"><span data-stu-id="57056-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="57056-134">Хеши файла = 64</span><span class="sxs-lookup"><span data-stu-id="57056-134">File hashes = 64</span></span>
  - <span data-ttu-id="57056-135">URL-адрес = 250</span><span class="sxs-lookup"><span data-stu-id="57056-135">URL = 250</span></span>

- <span data-ttu-id="57056-136">Запись должна быть активна в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="57056-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="57056-137">По умолчанию срок действия записей в списке разрешить или блокировать клиента истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="57056-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="57056-138">Вы можете указать дату или установить, чтобы срок их действия никогда не истек.</span><span class="sxs-lookup"><span data-stu-id="57056-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="57056-139">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="57056-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="57056-140">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="57056-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="57056-141">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="57056-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="57056-142">**URL-адреса, файлы и разрешить массовым отправителям:**</span><span class="sxs-lookup"><span data-stu-id="57056-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="57056-143">Чтобы добавить и удалить значения из списка "Разрешить или заблокировать клиента", необходимо быть членом группы ролей администратора организации или **администратора** безопасности. </span><span class="sxs-lookup"><span data-stu-id="57056-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="57056-144">Чтобы получить доступ только для чтения к списку разрешить или заблокировать клиента, необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="57056-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="57056-145">**Spoofing**: Одна из следующих комбинаций:</span><span class="sxs-lookup"><span data-stu-id="57056-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="57056-146">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="57056-146">**Organization Management**</span></span>
    - <span data-ttu-id="57056-147">**Администратор безопасности** <u>и</u> **конфигурация** только для просмотра или управление организацией только **для просмотра.**</span><span class="sxs-lookup"><span data-stu-id="57056-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="57056-148">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="57056-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="57056-149">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57056-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="57056-150">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="57056-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="57056-151">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="57056-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-152">Используйте Центр & безопасности для создания записей url-адресов блокировки в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="57056-153">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="57056-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="57056-154">На странице **Разрешить или заблокировать** список клиента убедитесь, что выбрана вкладка URL-адресов, а затем нажмите **кнопку Блок** </span><span class="sxs-lookup"><span data-stu-id="57056-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="57056-155">В **вылете** url-адресов блока, который отображается, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57056-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="57056-156">**Добавление URL-адресов для блокировки:** введите один URL-адрес на строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="57056-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="57056-157">Подробные сведения о синтаксисе записей URL-адресов см. в разделе [Синтаксис](#url-syntax-for-the-tenant-allowblock-list) URL-адресов для раздела Разрешить или заблокировать список клиента в этой статье.</span><span class="sxs-lookup"><span data-stu-id="57056-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="57056-158">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="57056-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="57056-159">Проверьте отключение параметра (Отключение) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. </span><span class="sxs-lookup"><span data-stu-id="57056-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="57056-160">или</span><span class="sxs-lookup"><span data-stu-id="57056-160">or</span></span>

     - <span data-ttu-id="57056-161">Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия:</span><span class="sxs-lookup"><span data-stu-id="57056-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="57056-163">.</span><span class="sxs-lookup"><span data-stu-id="57056-163">.</span></span>

   - <span data-ttu-id="57056-164">**Необязательный** примечание. Введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="57056-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="57056-165">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="57056-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-166">Используйте Центр & безопасности для создания записей заблокированных файлов в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="57056-167">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="57056-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="57056-168">На странице **Разрешить или заблокировать список клиента** выберите вкладку **Files** и нажмите **кнопку Блок**.</span><span class="sxs-lookup"><span data-stu-id="57056-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="57056-169">В **добавлении файлов для блокировки** вылетов, которые появляются, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57056-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="57056-170">**Добавление хеша файла:** введите одно хеш-значение SHA256 за строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="57056-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="57056-171">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="57056-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="57056-172">Проверьте отключение параметра (Отключение) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. </span><span class="sxs-lookup"><span data-stu-id="57056-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="57056-173">или</span><span class="sxs-lookup"><span data-stu-id="57056-173">or</span></span>

     - <span data-ttu-id="57056-174">Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия:</span><span class="sxs-lookup"><span data-stu-id="57056-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="57056-176">.</span><span class="sxs-lookup"><span data-stu-id="57056-176">.</span></span>

   - <span data-ttu-id="57056-177">**Необязательный** примечание. Введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="57056-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="57056-178">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="57056-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-179">Используйте Центр & безопасности, чтобы создать возможность массовой записи домена отправителя почты в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="57056-180">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="57056-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="57056-181">На странице **Разрешить или заблокировать** список клиента выберите домены Отправитель для вкладки **обхода BCL** и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="57056-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="57056-182">В **домене Добавить отправитель для обхода BCL,** который отображается, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57056-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="57056-183">**Добавление доменов отправитель для обхода BCL:** Введите один исходный домен хорошей массовой почты в строке, не более 20.</span><span class="sxs-lookup"><span data-stu-id="57056-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="57056-184">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="57056-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="57056-185">Проверьте отключение параметра (Отключение) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. </span><span class="sxs-lookup"><span data-stu-id="57056-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="57056-186">или</span><span class="sxs-lookup"><span data-stu-id="57056-186">or</span></span>

     - <span data-ttu-id="57056-187">Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия:</span><span class="sxs-lookup"><span data-stu-id="57056-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="57056-189">.</span><span class="sxs-lookup"><span data-stu-id="57056-189">.</span></span>

4. <span data-ttu-id="57056-190">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="57056-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-191">Используйте Центр & безопасности для создания записей подмены отправителя в списке разрешить или заблокировать подмену</span><span class="sxs-lookup"><span data-stu-id="57056-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-192">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="57056-192">**Notes**:</span></span>

- <span data-ttu-id="57056-193">Только сочетание _подмены_ пользователя  и инфраструктуры отправки, как определено в доменной паре, разрешено или заблокировано от подмены.</span><span class="sxs-lookup"><span data-stu-id="57056-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="57056-194">При настройке разрешить или заблокировать запись для доменной пары сообщения из этой пары домена больше не отображаются в анализе подмены сведений.</span><span class="sxs-lookup"><span data-stu-id="57056-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="57056-195">Срок действия записей для поддельных отправителей никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="57056-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="57056-196">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="57056-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="57056-197">На странице **Разрешить или заблокировать** список клиента выберите вкладку **Spoofing** и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="57056-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="57056-198">В **вылете Добавить новые пары** домена, который появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57056-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="57056-199">**Добавление новых доменных пар с подкардами:** введите одну доменную пару в строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="57056-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="57056-200">Подробные сведения о синтаксисе для записей подмены отправителя см. в разделе Синтаксис пары домена для записей подмены отправителя в разделе [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) более поздней в этой статье.</span><span class="sxs-lookup"><span data-stu-id="57056-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="57056-201">**Тип Spoof:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="57056-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="57056-202">**Внутренний:** подмена отправитель находится в домене, который принадлежит вашей организации [(принятый домен).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="57056-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="57056-203">**Внешний.** Поддельный отправитель находится во внешнем домене.</span><span class="sxs-lookup"><span data-stu-id="57056-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="57056-204">**Действие:** **Выберите разрешить или** **заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="57056-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="57056-205">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="57056-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-206">Используйте Центр & безопасности для просмотра записей в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="57056-207">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="57056-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="57056-208">Выберите вкладку, которая вам нужна.</span><span class="sxs-lookup"><span data-stu-id="57056-208">Select the tab you want.</span></span> <span data-ttu-id="57056-209">Доступные столбцы зависят от выбранной вкладки:</span><span class="sxs-lookup"><span data-stu-id="57056-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="57056-210">**URL-адреса:**</span><span class="sxs-lookup"><span data-stu-id="57056-210">**URLs**:</span></span>
     - <span data-ttu-id="57056-211">**Значение:** URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="57056-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="57056-212">**Действие**: Блок **значений**.</span><span class="sxs-lookup"><span data-stu-id="57056-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="57056-213">**Последняя обновленная дата**</span><span class="sxs-lookup"><span data-stu-id="57056-213">**Last updated date**</span></span>
     - <span data-ttu-id="57056-214">**Срок действия**</span><span class="sxs-lookup"><span data-stu-id="57056-214">**Expiration date**</span></span>
     - <span data-ttu-id="57056-215">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="57056-215">**Note**</span></span>

   - <span data-ttu-id="57056-216">**Files**</span><span class="sxs-lookup"><span data-stu-id="57056-216">**Files**</span></span>
     - <span data-ttu-id="57056-217">**Значение:** hash файла.</span><span class="sxs-lookup"><span data-stu-id="57056-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="57056-218">**Действие**: Блок **значений**.</span><span class="sxs-lookup"><span data-stu-id="57056-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="57056-219">**Последняя обновленная дата**</span><span class="sxs-lookup"><span data-stu-id="57056-219">**Last updated date**</span></span>
     - <span data-ttu-id="57056-220">**Срок действия**</span><span class="sxs-lookup"><span data-stu-id="57056-220">**Expiration date**</span></span>
     - <span data-ttu-id="57056-221">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="57056-221">**Note**</span></span>

   - <span data-ttu-id="57056-222">**Домены отправитель для обхода BCL**</span><span class="sxs-lookup"><span data-stu-id="57056-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="57056-223">**Значение.** Домен отправитель массовой почты.</span><span class="sxs-lookup"><span data-stu-id="57056-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="57056-224">**Последняя обновленная дата**</span><span class="sxs-lookup"><span data-stu-id="57056-224">**Last updated date**</span></span>
     - <span data-ttu-id="57056-225">**Срок действия**</span><span class="sxs-lookup"><span data-stu-id="57056-225">**Expiration date**</span></span>

   - <span data-ttu-id="57056-226">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="57056-226">**Spoofing**</span></span>
     - <span data-ttu-id="57056-227">**Подмена пользователя**</span><span class="sxs-lookup"><span data-stu-id="57056-227">**Spoofed user**</span></span>
     - <span data-ttu-id="57056-228">**Отправка инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="57056-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="57056-229">**Тип Spoof:** Значение **Внутреннее или** **Внешнее**.</span><span class="sxs-lookup"><span data-stu-id="57056-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="57056-230">**Действие:** блок **значения или** **разрешить**.</span><span class="sxs-lookup"><span data-stu-id="57056-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="57056-231">Вы можете нажать на столбец заголовка для сортировки в порядке по возрастанию или убыванию.</span><span class="sxs-lookup"><span data-stu-id="57056-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="57056-232">Вы можете нажать **группу,** чтобы сгруппить результаты.</span><span class="sxs-lookup"><span data-stu-id="57056-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="57056-233">Доступные значения зависят от выбранной вкладки:</span><span class="sxs-lookup"><span data-stu-id="57056-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="57056-234">**URL-адреса.** Результаты можно сгруппить по **action.**</span><span class="sxs-lookup"><span data-stu-id="57056-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="57056-235">**Файлы.** Результаты можно сгруппить по **action.**</span><span class="sxs-lookup"><span data-stu-id="57056-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="57056-236">**Домены отправитель для обхода BCL:** **Группа** недоступна на этой вкладке.</span><span class="sxs-lookup"><span data-stu-id="57056-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="57056-237">**Спуфинг:** Результаты можно сгруппить по **типу Action** или **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="57056-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="57056-238">Щелкните **Поиск,** введите все или часть значения, а затем нажмите КНОПКУ ВВОДА, чтобы найти определенное значение.</span><span class="sxs-lookup"><span data-stu-id="57056-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="57056-239">По завершению щелкните **значок Clear Search** Clear search ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="57056-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="57056-240">Щелкните **Фильтр,** чтобы отфильтровать результаты.</span><span class="sxs-lookup"><span data-stu-id="57056-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="57056-241">Значения, доступные в **вылете Filter,** зависят от выбранной вкладки:</span><span class="sxs-lookup"><span data-stu-id="57056-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="57056-242">**URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="57056-242">**URLs**</span></span>
     - <span data-ttu-id="57056-243">**Действие**</span><span class="sxs-lookup"><span data-stu-id="57056-243">**Action**</span></span>
     - <span data-ttu-id="57056-244">**Не истекает срок действия**</span><span class="sxs-lookup"><span data-stu-id="57056-244">**Never expire**</span></span>
     - <span data-ttu-id="57056-245">**Последняя обновленная дата**</span><span class="sxs-lookup"><span data-stu-id="57056-245">**Last updated date**</span></span>
     - <span data-ttu-id="57056-246">**Срок действия**</span><span class="sxs-lookup"><span data-stu-id="57056-246">**Expiration date**</span></span>

   - <span data-ttu-id="57056-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="57056-247">**Files**</span></span>
     - <span data-ttu-id="57056-248">**Действие**</span><span class="sxs-lookup"><span data-stu-id="57056-248">**Action**</span></span>
     - <span data-ttu-id="57056-249">**Не истекает срок действия**</span><span class="sxs-lookup"><span data-stu-id="57056-249">**Never expire**</span></span>
     - <span data-ttu-id="57056-250">**Последняя обновленная дата**</span><span class="sxs-lookup"><span data-stu-id="57056-250">**Last updated date**</span></span>
     - <span data-ttu-id="57056-251">**Срок действия**</span><span class="sxs-lookup"><span data-stu-id="57056-251">**Expiration date**</span></span>

   - <span data-ttu-id="57056-252">**Домены отправитель для обхода BCL**</span><span class="sxs-lookup"><span data-stu-id="57056-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="57056-253">**Не истекает срок действия**</span><span class="sxs-lookup"><span data-stu-id="57056-253">**Never expire**</span></span>
     - <span data-ttu-id="57056-254">**Последняя обновленная дата**</span><span class="sxs-lookup"><span data-stu-id="57056-254">**Last updated date**</span></span>
     - <span data-ttu-id="57056-255">**Срок действия**</span><span class="sxs-lookup"><span data-stu-id="57056-255">**Expiration date**</span></span>

   - <span data-ttu-id="57056-256">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="57056-256">**Spoofing**</span></span>
     - <span data-ttu-id="57056-257">**Действие**</span><span class="sxs-lookup"><span data-stu-id="57056-257">**Action**</span></span>
     - <span data-ttu-id="57056-258">**Тип Spoof**</span><span class="sxs-lookup"><span data-stu-id="57056-258">**Spoof type**</span></span>

   <span data-ttu-id="57056-259">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="57056-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="57056-260">Чтобы очистить существующие фильтры, **щелкните Фильтр,** а в вылете **Фильтр,** который появится, щелкните **Очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="57056-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-261">Используйте Центр & безопасности для изменения записей в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="57056-262">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="57056-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="57056-263">Выберите вкладку, которая содержит тип записи, которую необходимо изменить:</span><span class="sxs-lookup"><span data-stu-id="57056-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="57056-264">**URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="57056-264">**URLs**</span></span>
   - <span data-ttu-id="57056-265">**Files**</span><span class="sxs-lookup"><span data-stu-id="57056-265">**Files**</span></span>
   - <span data-ttu-id="57056-266">**Домены отправитель для обхода BCL**</span><span class="sxs-lookup"><span data-stu-id="57056-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="57056-267">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="57056-267">**Spoofing**</span></span>

3. <span data-ttu-id="57056-268">Выберите запись, которую необходимо изменить, а затем нажмите **кнопку Изменить значок Изменить** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="57056-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="57056-269">Значения, которые можно изменить в вылете, зависят от вкладки, выбранной на предыдущем шаге:</span><span class="sxs-lookup"><span data-stu-id="57056-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="57056-270">**URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="57056-270">**URLs**</span></span>
     - <span data-ttu-id="57056-271">**Не истекает** и/или не истекает срок действия.</span><span class="sxs-lookup"><span data-stu-id="57056-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="57056-272">**Необязательная заметка**</span><span class="sxs-lookup"><span data-stu-id="57056-272">**Optional note**</span></span>

   - <span data-ttu-id="57056-273">**Files**</span><span class="sxs-lookup"><span data-stu-id="57056-273">**Files**</span></span>
     - <span data-ttu-id="57056-274">**Не истекает** и/или не истекает срок действия.</span><span class="sxs-lookup"><span data-stu-id="57056-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="57056-275">**Необязательная заметка**</span><span class="sxs-lookup"><span data-stu-id="57056-275">**Optional note**</span></span>

   - <span data-ttu-id="57056-276">**Домены отправитель для обхода BCL**</span><span class="sxs-lookup"><span data-stu-id="57056-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="57056-277">**Не истекает** и/или не истекает срок действия.</span><span class="sxs-lookup"><span data-stu-id="57056-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="57056-278">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="57056-278">**Spoofing**</span></span>
     - <span data-ttu-id="57056-279">**Действие.** Можно изменить значение **Разрешить или** **заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="57056-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="57056-280">По завершении нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="57056-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="57056-281">Используйте Центр & безопасности для удаления записей из списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="57056-282">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="57056-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="57056-283">Выберите вкладку, которая содержит тип записи, которую необходимо удалить:</span><span class="sxs-lookup"><span data-stu-id="57056-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="57056-284">**URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="57056-284">**URLs**</span></span>
   - <span data-ttu-id="57056-285">**Files**</span><span class="sxs-lookup"><span data-stu-id="57056-285">**Files**</span></span>
   - <span data-ttu-id="57056-286">**Домены отправитель для обхода BCL**</span><span class="sxs-lookup"><span data-stu-id="57056-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="57056-287">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="57056-287">**Spoofing**</span></span>

3. <span data-ttu-id="57056-288">Выберите запись, которую необходимо удалить, а затем нажмите **кнопку Удалить значок Delete** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="57056-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="57056-289">В диалоговом октаге предупреждения нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="57056-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="57056-290">Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="57056-291">Использование PowerShell для добавления блок-файла или записей URL-адресов в список разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-292">Чтобы добавить блок-файл или ЗАПИСИ URL-адресов в список Разрешить или Заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="57056-293">В этом примере добавляется запись заблокированного файла для указанных файлов, срок действия которых никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="57056-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="57056-294">В этом примере добавляется запись URL-адреса contoso.com всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="57056-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="57056-295">Поскольку мы не использовали параметры ExpireDate или NoExpiration, срок действия записи истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="57056-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="57056-296">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="57056-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="57056-297">Использование PowerShell для добавления записей домена отправителя массовой почты в список разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-298">Чтобы добавить допустимые объемные записи домена отправителя почты в списке разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="57056-299">В этом примере добавляется разрешенная запись отправитель массы для указанного домена, срок действия которого никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="57056-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="57056-300">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="57056-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="57056-301">Используйте PowerShell, чтобы добавить в список разрешить или заблокировать поддельные записи отправителя в список разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="57056-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-302">Чтобы добавить подменные записи отправителя в список разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="57056-303">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="57056-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-304">Использование PowerShell для просмотра записей блок-файла или URL-адресов в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-305">Чтобы просмотреть записи заблокированного файла или URL-адресов в списке разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="57056-306">В этом примере возвращается информация для указанного значения hash файла.</span><span class="sxs-lookup"><span data-stu-id="57056-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="57056-307">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="57056-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="57056-308">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="57056-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-309">Использование PowerShell для просмотра записей домена отправителя массовой почты в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-310">Чтобы просмотреть допустимые записи домена отправителя массовой почты в списке разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="57056-311">В этом примере возвращаются все разрешенные домены отправитель массовой почты.</span><span class="sxs-lookup"><span data-stu-id="57056-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="57056-312">В этом примере возвращается информация для указанного домена отправитель массы.</span><span class="sxs-lookup"><span data-stu-id="57056-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="57056-313">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="57056-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-314">Использование PowerShell для просмотра записей подмены отправителя в списке разрешить или заблокировать подмену</span><span class="sxs-lookup"><span data-stu-id="57056-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-315">Чтобы просмотреть поддельные записи отправителя в списке "Разрешить или заблокировать клиента", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="57056-316">В этом примере возвращаются все поддельные записи отправителя в списке разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="57056-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="57056-317">В этом примере возвращаются все записи подмены отправитель, которые являются внутренними.</span><span class="sxs-lookup"><span data-stu-id="57056-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="57056-318">В этом примере возвращаются все заблокированные поддельные записи отправитель, которые являются внешними.</span><span class="sxs-lookup"><span data-stu-id="57056-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="57056-319">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="57056-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-320">Использование PowerShell для изменения записей блок-файла и URL-адресов в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-321">Чтобы изменить записи заблокированного файла и URL-адресов в списке разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="57056-322">В этом примере изменяется срок действия указанной записи URL-адреса блока.</span><span class="sxs-lookup"><span data-stu-id="57056-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="57056-323">Подробные сведения о синтаксисе и параметрах см. в [ссылке Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="57056-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-324">Использование PowerShell для изменения допуска записей домена отправителя массовой почты в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-325">Чтобы изменить допустимые объемные записи домена отправителя почты в списке разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="57056-326">В этом примере изменяется срок действия указанной записи домена отправитель массовой почты, которая никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="57056-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="57056-327">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="57056-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-328">Использование PowerShell для изменения допуска или блокировки подмены записей отправителя в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-329">Чтобы изменить допустимые или заблокированные записи отправителя в списке разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="57056-330">В этом примере изменяется подмена записи отправитель с разрешением на блокировку.</span><span class="sxs-lookup"><span data-stu-id="57056-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="57056-331">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="57056-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="57056-332">Использование PowerShell для удаления домена, файла и домена для массовой отправки почты из списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-333">Чтобы удалить допустимые объемные записи домена отправителя почты, блокировать записи файлов и блокировать записи URL-адресов из списка разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="57056-334">В этом примере удаляется указанная запись URL-адреса блокировки из списка разрешить или блокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="57056-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="57056-335">Подробные сведения о синтаксисе и параметрах см. в [ссылке Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="57056-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="57056-336">Использование PowerShell для удаления записей отправителя с подменой или блокировки из списка разрешить/заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-337">Чтобы удалить записи отправителя подмены из списка разрешить или заблокировать подмену, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57056-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="57056-338">Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="57056-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="57056-339">Синтаксис URL-адреса для списка разрешить или блокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="57056-340">Ip4v и IPv6-адреса разрешены, но порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="57056-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="57056-341">Расширения filename не разрешены (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="57056-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="57056-342">Юникод не поддерживается, но Punycode есть.</span><span class="sxs-lookup"><span data-stu-id="57056-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="57056-343">Имена хост-кодов разрешены, если все следующие утверждения верны:</span><span class="sxs-lookup"><span data-stu-id="57056-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="57056-344">Имя хост-пользователя содержит период.</span><span class="sxs-lookup"><span data-stu-id="57056-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="57056-345">Существует по крайней мере один символ слева от периода.</span><span class="sxs-lookup"><span data-stu-id="57056-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="57056-346">Справа от периода имеется по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="57056-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="57056-347">Например, `t.co` разрешено или `.com` `contoso.` запрещено.</span><span class="sxs-lookup"><span data-stu-id="57056-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="57056-348">Subpaths не подразумеваются.</span><span class="sxs-lookup"><span data-stu-id="57056-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="57056-349">Например, `contoso.com` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="57056-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="57056-350">Поддиальды (\*) разрешены в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="57056-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="57056-351">За левой подгруппой должен следовать период, чтобы указать поддомен.</span><span class="sxs-lookup"><span data-stu-id="57056-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="57056-352">Например, `*.contoso.com` разрешено; `*contoso.com` запрещено.</span><span class="sxs-lookup"><span data-stu-id="57056-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="57056-353">Правая подмайка должна следовать за полосой вперед (/), чтобы указать путь.</span><span class="sxs-lookup"><span data-stu-id="57056-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="57056-354">Например, `contoso.com/*` разрешено или `contoso.com*` `contoso.com/ab*` запрещено.</span><span class="sxs-lookup"><span data-stu-id="57056-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="57056-355">Все подпаты не подразумеваются правой подгруппой.</span><span class="sxs-lookup"><span data-stu-id="57056-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="57056-356">Например, `contoso.com/*` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="57056-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="57056-357">`*.com*` является недействительным (не разрешимый домен, а правая подкратная карточка не следует передовую черту).</span><span class="sxs-lookup"><span data-stu-id="57056-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="57056-358">В IP-адресах запрещено использовать поддиальдные знаки.</span><span class="sxs-lookup"><span data-stu-id="57056-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="57056-359">Символ tilde (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="57056-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="57056-360">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="57056-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="57056-361">Например, `~contoso.com` включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="57056-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="57056-362">Записи URL-адресов, содержащие протоколы (например, или ) не будут работать, так как URL-записи применяются `http://` `https://` к всем `ftp://` протоколам.</span><span class="sxs-lookup"><span data-stu-id="57056-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="57056-363">Имя пользователя или пароль не поддерживаются или не требуются.</span><span class="sxs-lookup"><span data-stu-id="57056-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="57056-364">Кавычка (' или ") являются недействительными символами.</span><span class="sxs-lookup"><span data-stu-id="57056-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="57056-365">URL-адрес должен включать все перенаправления, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="57056-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="57056-366">Сценарии ввода URL-адресов</span><span class="sxs-lookup"><span data-stu-id="57056-366">URL entry scenarios</span></span>

<span data-ttu-id="57056-367">Допустимые записи URL-адресов и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="57056-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="57056-368">Сценарий: нет поддиальдов</span><span class="sxs-lookup"><span data-stu-id="57056-368">Scenario: No wildcards</span></span>

<span data-ttu-id="57056-369">**Запись:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="57056-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="57056-370">**Разрешить совпадение:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="57056-371">**Разрешить не совпадать:**</span><span class="sxs-lookup"><span data-stu-id="57056-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="57056-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-372">abc-contoso.com</span></span>
  - <span data-ttu-id="57056-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="57056-373">contoso.com/a</span></span>
  - <span data-ttu-id="57056-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="57056-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="57056-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="57056-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-377">www.contoso.com</span></span>
  - <span data-ttu-id="57056-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="57056-379">**Совпадение блоков:**</span><span class="sxs-lookup"><span data-stu-id="57056-379">**Block match**:</span></span>

  - <span data-ttu-id="57056-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-380">contoso.com</span></span>
  - <span data-ttu-id="57056-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="57056-381">contoso.com/a</span></span>
  - <span data-ttu-id="57056-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="57056-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="57056-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="57056-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-385">www.contoso.com</span></span>
  - <span data-ttu-id="57056-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="57056-387">**Блок не соответствует**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="57056-388">Сценарий: левая подгруппа (subdomain)</span><span class="sxs-lookup"><span data-stu-id="57056-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="57056-389">**Запись:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="57056-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="57056-390">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="57056-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="57056-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-391">www.contoso.com</span></span>
  - <span data-ttu-id="57056-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="57056-393">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="57056-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="57056-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-394">123contoso.com</span></span>
  - <span data-ttu-id="57056-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-395">contoso.com</span></span>
  - <span data-ttu-id="57056-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="57056-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="57056-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="57056-398">Сценарий: правая под диктовка в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="57056-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="57056-399">**Запись:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="57056-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="57056-400">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="57056-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="57056-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="57056-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="57056-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="57056-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="57056-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="57056-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="57056-404">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="57056-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="57056-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-405">contoso.com</span></span>
  - <span data-ttu-id="57056-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="57056-406">contoso.com/a</span></span>
  - <span data-ttu-id="57056-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-407">www.contoso.com</span></span>
  - <span data-ttu-id="57056-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="57056-409">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="57056-409">Scenario: Left tilde</span></span>

<span data-ttu-id="57056-410">**Запись:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="57056-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="57056-411">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="57056-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="57056-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-412">contoso.com</span></span>
  - <span data-ttu-id="57056-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-413">www.contoso.com</span></span>
  - <span data-ttu-id="57056-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="57056-415">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="57056-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="57056-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-416">123contoso.com</span></span>
  - <span data-ttu-id="57056-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="57056-417">contoso.com/abc</span></span>
  - <span data-ttu-id="57056-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="57056-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="57056-419">Сценарий: суффикс правой подстановки</span><span class="sxs-lookup"><span data-stu-id="57056-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="57056-420">**Запись:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="57056-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="57056-421">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="57056-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="57056-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="57056-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="57056-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="57056-423">contoso.com/a</span></span>
  - <span data-ttu-id="57056-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="57056-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="57056-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="57056-425">contoso.com/ab</span></span>
  - <span data-ttu-id="57056-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="57056-426">contoso.com/b</span></span>
  - <span data-ttu-id="57056-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="57056-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="57056-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="57056-428">contoso.com/ba</span></span>

- <span data-ttu-id="57056-429">**Разрешить не совпадать** и **блок не совпадает**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="57056-430">Сценарий. Поддомайн левой подстановки и суффикс правой подстановки</span><span class="sxs-lookup"><span data-stu-id="57056-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="57056-431">**Запись:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="57056-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="57056-432">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="57056-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="57056-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="57056-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="57056-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="57056-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="57056-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="57056-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="57056-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="57056-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="57056-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="57056-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="57056-438">**Разрешить не совпадать** и **блок не соответствует**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="57056-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="57056-439">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="57056-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="57056-440">**Запись:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="57056-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="57056-441">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="57056-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="57056-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-442">contoso.com</span></span>
  - <span data-ttu-id="57056-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="57056-443">contoso.com/a</span></span>
  - <span data-ttu-id="57056-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-444">www.contoso.com</span></span>
  - <span data-ttu-id="57056-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="57056-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="57056-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="57056-447">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="57056-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="57056-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-448">123contoso.com</span></span>
  - <span data-ttu-id="57056-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="57056-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="57056-450">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="57056-450">Scenario: IP address</span></span>

<span data-ttu-id="57056-451">**Запись:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="57056-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="57056-452">**Разрешить совпадение** **и блокировку:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="57056-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="57056-453">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="57056-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="57056-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="57056-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="57056-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="57056-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="57056-456">IP-адрес с правой подголой карточкой</span><span class="sxs-lookup"><span data-stu-id="57056-456">IP address with right wildcard</span></span>

<span data-ttu-id="57056-457">**Запись:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="57056-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="57056-458">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="57056-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="57056-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="57056-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="57056-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="57056-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="57056-461">Примеры недействительных записей</span><span class="sxs-lookup"><span data-stu-id="57056-461">Examples of invalid entries</span></span>

<span data-ttu-id="57056-462">Следующие записи являются недействительными:</span><span class="sxs-lookup"><span data-stu-id="57056-462">The following entries are invalid:</span></span>

- <span data-ttu-id="57056-463">**Отсутствующие или недействительные значения домена:**</span><span class="sxs-lookup"><span data-stu-id="57056-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="57056-464">contoso</span><span class="sxs-lookup"><span data-stu-id="57056-464">contoso</span></span>
  - <span data-ttu-id="57056-465">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="57056-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="57056-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="57056-466">\*.com</span></span>
  - <span data-ttu-id="57056-467">\*PDF</span><span class="sxs-lookup"><span data-stu-id="57056-467">\*.pdf</span></span>

- <span data-ttu-id="57056-468">**Под диктовка текста или без интервалов символов:**</span><span class="sxs-lookup"><span data-stu-id="57056-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="57056-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="57056-469">\*contoso.com</span></span>
  - <span data-ttu-id="57056-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="57056-470">contoso.com\*</span></span>
  - <span data-ttu-id="57056-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="57056-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="57056-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="57056-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="57056-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="57056-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="57056-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="57056-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="57056-475">**IP-адреса с портами:**</span><span class="sxs-lookup"><span data-stu-id="57056-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="57056-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="57056-476">contoso.com:443</span></span>
  - <span data-ttu-id="57056-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="57056-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="57056-478">**Неописуемые подражательные знаки:**</span><span class="sxs-lookup"><span data-stu-id="57056-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="57056-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="57056-479">\*.\*</span></span>

- <span data-ttu-id="57056-480">**Средние подкарды:**</span><span class="sxs-lookup"><span data-stu-id="57056-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="57056-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="57056-481">conto\*so.com</span></span>
  - <span data-ttu-id="57056-482">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="57056-482">conto~so.com</span></span>

- <span data-ttu-id="57056-483">**Двойные подкарды**</span><span class="sxs-lookup"><span data-stu-id="57056-483">**Double wildcards**</span></span>

  - <span data-ttu-id="57056-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="57056-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="57056-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="57056-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="57056-486">Синтаксис пары домена для подмены записей отправителя в списке Разрешить или Заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="57056-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="57056-487">Доменная пара для подмены отправителя в Списке разрешить или заблокировать клиента использует следующий синтаксис: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="57056-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="57056-488">**Поддельный** пользователь. Это значение включает адрес электронной почты подмены пользователя, отображаемого в поле **From** в клиентах электронной почты.</span><span class="sxs-lookup"><span data-stu-id="57056-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="57056-489">Этот адрес также известен как `5322.From` адрес.</span><span class="sxs-lookup"><span data-stu-id="57056-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="57056-490">Допустимыми являются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="57056-490">Valid values include:</span></span>
  - <span data-ttu-id="57056-491">Отдельный адрес электронной почты (например, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="57056-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="57056-492">Домен электронной почты (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="57056-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="57056-493">Символ под диктовки (например, \* ).</span><span class="sxs-lookup"><span data-stu-id="57056-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="57056-494">**Инфраструктура отправки.** Это значение указывает источник сообщений от подмены пользователя.</span><span class="sxs-lookup"><span data-stu-id="57056-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="57056-495">Допустимыми являются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="57056-495">Valid values include:</span></span>
  - <span data-ttu-id="57056-496">Домен, найденный в обратной DNS-записи IP-адреса сервера электронной почты источника (например, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="57056-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="57056-497">Если исходный IP-адрес не имеет записи PTR, инфраструктура отправки определена как \<source IP\> /24 (например, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="57056-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="57056-498">Вот несколько примеров допустимой пары домена для определения поддельных отправителей:</span><span class="sxs-lookup"><span data-stu-id="57056-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="57056-499">Добавление доменной пары позволяет или  блокирует только сочетание подмены пользователя и *инфраструктуры* отправки.</span><span class="sxs-lookup"><span data-stu-id="57056-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="57056-500">Он не разрешает электронную почту от подмены пользователя из любого источника, а также не разрешает электронную почту из источника инфраструктуры отправки для любого подменного пользователя.</span><span class="sxs-lookup"><span data-stu-id="57056-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="57056-501">Например, вы добавляете допустимую запись для следующей пары доменов:</span><span class="sxs-lookup"><span data-stu-id="57056-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="57056-502">**Домен**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="57056-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="57056-503">**Инфраструктура**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="57056-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="57056-504">Подмену допускаются только сообщения из этого *домена* и пара инфраструктуры отправки.</span><span class="sxs-lookup"><span data-stu-id="57056-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="57056-505">Другие отправители, пытающиеся gmail.com, не допускаются.</span><span class="sxs-lookup"><span data-stu-id="57056-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="57056-506">Сообщения от отправителей в других доменах, исходя из tms.mx.com, проверяются с помощью spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="57056-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
