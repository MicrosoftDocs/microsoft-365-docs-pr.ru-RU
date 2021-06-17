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
ms.openlocfilehash: 1548eda760b7b6b19214cb834d7fc43357dc0357
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985496"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-103">Управление списком разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="eafac-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eafac-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="eafac-104">**Applies to**</span></span>
- [<span data-ttu-id="eafac-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eafac-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eafac-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="eafac-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eafac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eafac-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="eafac-108">Функции, описанные в этой статье, находятся в предварительном просмотре, могут изменяться и недоступны во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="eafac-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="eafac-109">Если в вашей организации нет функций подмены, как описано в этой статье, см. более старый опыт управления подменой в manage [spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="eafac-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="eafac-110">В данный момент нельзя **настроить** разрешенный URL-адрес или элементы файлов в списке разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="eafac-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="eafac-111">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков, вы можете не согласиться с вердиктом по фильтрации EOP.</span><span class="sxs-lookup"><span data-stu-id="eafac-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="eafac-112">Например, хорошее сообщение может быть помечено как плохое (ложное положительное) или плохое сообщение может быть разрешено (ложное отрицательное).</span><span class="sxs-lookup"><span data-stu-id="eafac-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="eafac-113">Список разрешить или заблокировать клиента на портале Microsoft 365 Defender позволяет вручную переопределять Microsoft 365 фильтрации.</span><span class="sxs-lookup"><span data-stu-id="eafac-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="eafac-114">Список разрешить/заблокировать клиента используется во время потока почты и во время щелчков пользователя.</span><span class="sxs-lookup"><span data-stu-id="eafac-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="eafac-115">Можно указать следующие типы переопределей:</span><span class="sxs-lookup"><span data-stu-id="eafac-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="eafac-116">URL-адреса для блокировки.</span><span class="sxs-lookup"><span data-stu-id="eafac-116">URLs to block.</span></span>
- <span data-ttu-id="eafac-117">Файлы для блокировки.</span><span class="sxs-lookup"><span data-stu-id="eafac-117">Files to block.</span></span>
- <span data-ttu-id="eafac-118">Spoofed senders to allow or block.</span><span class="sxs-lookup"><span data-stu-id="eafac-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="eafac-119">Если переопределять решение разрешить [](learn-about-spoof-intelligence.md)или заблокировать в анализе подмены сведений, подмена отправитель становится ручным разрешением или блокировкой записи, которая отображается только на вкладке **Spoof** в списке разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="eafac-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="eafac-120">Вы также можете вручную создавать записи для подмены отправителей, прежде чем они будут обнаружены с помощью подмены.</span><span class="sxs-lookup"><span data-stu-id="eafac-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="eafac-121">В этой статье описывается настройка записей в Списке разрешения и блокировки клиента на портале Microsoft 365 Defender или в PowerShell (Exchange Online PowerShell для Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без Exchange Online почтовых ящиков).</span><span class="sxs-lookup"><span data-stu-id="eafac-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eafac-122">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="eafac-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eafac-123">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="eafac-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="eafac-124">Чтобы перейти непосредственно на страницу **Разрешить или блокировать списки клиента,** используйте <https://security.microsoft.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="eafac-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="eafac-125">Вы указываете файлы, используя значение hash SHA256 для файла.</span><span class="sxs-lookup"><span data-stu-id="eafac-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="eafac-126">Чтобы найти значение hash SHA256 для файла в Windows, запустите следующую команду в командной подсказке:</span><span class="sxs-lookup"><span data-stu-id="eafac-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="eafac-127">Например, значение `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="eafac-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="eafac-128">Перцептивные значения hash (pHash) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="eafac-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="eafac-129">Доступные значения URL-адресов описаны в синтаксисе [URL-адресов](#url-syntax-for-the-tenant-allowblock-list) для раздела "Разрешить или заблокировать список клиента" в этой статье.</span><span class="sxs-lookup"><span data-stu-id="eafac-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="eafac-130">Список разрешить или блокировать клиента позволяет не более 500 записей для URL-адресов и 500 записей для хеш-файлов.</span><span class="sxs-lookup"><span data-stu-id="eafac-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="eafac-131">Максимальное количество символов для каждой записи:</span><span class="sxs-lookup"><span data-stu-id="eafac-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="eafac-132">Хеши файла = 64</span><span class="sxs-lookup"><span data-stu-id="eafac-132">File hashes = 64</span></span>
  - <span data-ttu-id="eafac-133">URL-адрес = 250</span><span class="sxs-lookup"><span data-stu-id="eafac-133">URL = 250</span></span>

- <span data-ttu-id="eafac-134">Запись должна быть активна в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="eafac-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="eafac-135">По умолчанию срок действия записей в списке разрешить или блокировать клиента истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="eafac-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="eafac-136">Вы можете указать дату или установить, чтобы срок их действия никогда не истек.</span><span class="sxs-lookup"><span data-stu-id="eafac-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="eafac-137">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="eafac-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="eafac-138">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="eafac-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="eafac-139">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="eafac-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="eafac-140">**URL-адреса и файлы:**</span><span class="sxs-lookup"><span data-stu-id="eafac-140">**URLs and files**:</span></span>
    - <span data-ttu-id="eafac-141">Чтобы добавить и удалить значения из списка "Разрешить или заблокировать клиента", необходимо быть членом группы ролей администратора организации или **администратора** безопасности. </span><span class="sxs-lookup"><span data-stu-id="eafac-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="eafac-142">Чтобы получить доступ только для чтения к списку разрешить или заблокировать клиента, необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="eafac-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="eafac-143">**Spoofing**: Одна из следующих комбинаций:</span><span class="sxs-lookup"><span data-stu-id="eafac-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="eafac-144">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="eafac-144">**Organization Management**</span></span>
    - <span data-ttu-id="eafac-145">**Администратор безопасности** <u>и</u> **конфигурация** только для просмотра или управление организацией только **для просмотра.**</span><span class="sxs-lookup"><span data-stu-id="eafac-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="eafac-146">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="eafac-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="eafac-147">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eafac-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="eafac-148">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="eafac-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="eafac-149">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="eafac-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-150">Использование портала Microsoft 365 Defender для создания записей URL-адресов блокировки в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="eafac-151">На портале Microsoft 365 Defender перейдите **к разделу** Политики & правила правил политики \>  \>  \> **угрозы Клиент разрешить и блокировать списки**.</span><span class="sxs-lookup"><span data-stu-id="eafac-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eafac-152">На странице **Разрешить или блокировать** список клиента убедитесь, что вкладка **URL-адресов** выбрана, а затем нажмите ![ кнопку Блок ](../../media/m365-cc-sc-create-icon.png) **значок Block**.</span><span class="sxs-lookup"><span data-stu-id="eafac-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="eafac-153">В **вылете** url-адресов блока, который отображается, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="eafac-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="eafac-154">**Добавление URL-адресов с поддиальдами:** введите один URL-адрес на одну строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="eafac-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="eafac-155">Подробные сведения о синтаксисе записей URL-адресов см. в разделе [Синтаксис](#url-syntax-for-the-tenant-allowblock-list) URL-адресов для раздела Разрешить или заблокировать список клиента в этой статье.</span><span class="sxs-lookup"><span data-stu-id="eafac-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="eafac-156">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="eafac-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="eafac-157">Убедитесь, что параметр отключен (отключите) и используйте удаление в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. </span><span class="sxs-lookup"><span data-stu-id="eafac-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="eafac-158">или</span><span class="sxs-lookup"><span data-stu-id="eafac-158">or</span></span>

     - <span data-ttu-id="eafac-159">Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия:</span><span class="sxs-lookup"><span data-stu-id="eafac-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="eafac-161">.</span><span class="sxs-lookup"><span data-stu-id="eafac-161">.</span></span>
   - <span data-ttu-id="eafac-162">**Необязательный** примечание. Введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="eafac-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="eafac-163">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eafac-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-164">Использование портала Microsoft 365 Defender для создания записей заблокированных файлов в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="eafac-165">На портале Microsoft 365 Defender перейдите **к разделу** Политики & правила правил политики \>  \>  \> **угрозы Клиент разрешить и блокировать списки**.</span><span class="sxs-lookup"><span data-stu-id="eafac-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eafac-166">На странице **Разрешить или блокировать** список клиента выберите вкладку **Файлы** и нажмите блок ![ блок ](../../media/m365-cc-sc-create-icon.png) **значка Block**.</span><span class="sxs-lookup"><span data-stu-id="eafac-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="eafac-167">В **вылете блок-файлов,** который отображается, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="eafac-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="eafac-168">**Добавление хеша файла:** введите одно хеш-значение SHA256 за строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="eafac-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="eafac-169">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="eafac-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="eafac-170">Убедитесь, что параметр отключен (отключите) и используйте удаление в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. </span><span class="sxs-lookup"><span data-stu-id="eafac-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="eafac-171">или</span><span class="sxs-lookup"><span data-stu-id="eafac-171">or</span></span>

     - <span data-ttu-id="eafac-172">Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия:</span><span class="sxs-lookup"><span data-stu-id="eafac-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="eafac-174">.</span><span class="sxs-lookup"><span data-stu-id="eafac-174">.</span></span>
   - <span data-ttu-id="eafac-175">**Необязательный** примечание. Введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="eafac-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="eafac-176">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eafac-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-177">Используйте портал Microsoft 365 Defender для создания записей отправителя с подменой или блокировки в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-178">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="eafac-178">**Notes**:</span></span>

- <span data-ttu-id="eafac-179">Только сочетание _подмены_ пользователя  и инфраструктуры отправки, как определено в доменной паре, разрешено или заблокировано от подмены.</span><span class="sxs-lookup"><span data-stu-id="eafac-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="eafac-180">При настройке разрешить или заблокировать запись для доменной пары сообщения из этой пары домена больше не отображаются в анализе подмены сведений.</span><span class="sxs-lookup"><span data-stu-id="eafac-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="eafac-181">Срок действия записей для поддельных отправителей никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="eafac-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="eafac-182">На портале Microsoft 365 Defender перейдите **к разделу** Политики & правила правил политики \>  \>  \> **угрозы Клиент разрешить и блокировать списки**.</span><span class="sxs-lookup"><span data-stu-id="eafac-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eafac-183">На странице **Разрешить или блокировать** список клиента выберите вкладку **Spoofing** и нажмите ![ кнопку Добавить значок ](../../media/m365-cc-sc-create-icon.png) **Block**.</span><span class="sxs-lookup"><span data-stu-id="eafac-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="eafac-184">В **вылете Добавить новые пары** домена, который появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="eafac-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="eafac-185">**Добавление новых доменных пар с подкардами:** введите одну доменную пару в строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="eafac-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="eafac-186">Подробные сведения о синтаксисе для записей подмены отправителя см. в разделе Синтаксис пары домена для записей подмены отправителя в разделе [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) более поздней в этой статье.</span><span class="sxs-lookup"><span data-stu-id="eafac-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="eafac-187">**Тип Spoof:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="eafac-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="eafac-188">**Внутренний:** подмена отправитель находится в домене, который принадлежит вашей организации [(принятый домен).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="eafac-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="eafac-189">**Внешний.** Поддельный отправитель находится во внешнем домене.</span><span class="sxs-lookup"><span data-stu-id="eafac-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="eafac-190">**Действие:** **Выберите разрешить или** **заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="eafac-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="eafac-191">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eafac-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-192">Используйте портал Microsoft 365 Defender для просмотра записей в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="eafac-193">На портале Microsoft 365 Defender перейдите **к разделу** Политики & правила правил политики \>  \>  \> **угрозы Клиент разрешить и блокировать списки**.</span><span class="sxs-lookup"><span data-stu-id="eafac-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eafac-194">Выберите вкладку, которая вам нужна.</span><span class="sxs-lookup"><span data-stu-id="eafac-194">Select the tab you want.</span></span> <span data-ttu-id="eafac-195">Доступные столбцы зависят от выбранной вкладки:</span><span class="sxs-lookup"><span data-stu-id="eafac-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="eafac-196">**URL-адреса:**</span><span class="sxs-lookup"><span data-stu-id="eafac-196">**URLs**:</span></span>
     - <span data-ttu-id="eafac-197">**Значение:** URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="eafac-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="eafac-198">**Действие**: Блок **значений**.</span><span class="sxs-lookup"><span data-stu-id="eafac-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="eafac-199">**Последнее обновление**</span><span class="sxs-lookup"><span data-stu-id="eafac-199">**Last updated**</span></span>
     - <span data-ttu-id="eafac-200">**Удаление на**</span><span class="sxs-lookup"><span data-stu-id="eafac-200">**Remove on**</span></span>
     - <span data-ttu-id="eafac-201">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="eafac-201">**Notes**</span></span>
   - <span data-ttu-id="eafac-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="eafac-202">**Files**</span></span>
     - <span data-ttu-id="eafac-203">**Значение:** hash файла.</span><span class="sxs-lookup"><span data-stu-id="eafac-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="eafac-204">**Действие**: Блок **значений**.</span><span class="sxs-lookup"><span data-stu-id="eafac-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="eafac-205">**Последнее обновление**</span><span class="sxs-lookup"><span data-stu-id="eafac-205">**Last updated**</span></span>
     - <span data-ttu-id="eafac-206">**Удаление на**</span><span class="sxs-lookup"><span data-stu-id="eafac-206">**Remove on**</span></span>
     - <span data-ttu-id="eafac-207">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="eafac-207">**Notes**</span></span>
   - <span data-ttu-id="eafac-208">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="eafac-208">**Spoofing**</span></span>
     - <span data-ttu-id="eafac-209">**Подмена пользователя**</span><span class="sxs-lookup"><span data-stu-id="eafac-209">**Spoofed user**</span></span>
     - <span data-ttu-id="eafac-210">**Отправка инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="eafac-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="eafac-211">**Тип Spoof:** Значение **Внутреннее или** **Внешнее**.</span><span class="sxs-lookup"><span data-stu-id="eafac-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="eafac-212">**Действие:** блок **значения или** **разрешить**.</span><span class="sxs-lookup"><span data-stu-id="eafac-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="eafac-213">Вы можете нажать на столбец заголовка для сортировки в порядке по возрастанию или убыванию.</span><span class="sxs-lookup"><span data-stu-id="eafac-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="eafac-214">Вы можете нажать **группу,** чтобы сгруппить результаты.</span><span class="sxs-lookup"><span data-stu-id="eafac-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="eafac-215">Доступные значения зависят от выбранной вкладки:</span><span class="sxs-lookup"><span data-stu-id="eafac-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="eafac-216">**URL-адреса.** Результаты можно сгруппить по **action.**</span><span class="sxs-lookup"><span data-stu-id="eafac-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="eafac-217">**Файлы.** Результаты можно сгруппить по **action.**</span><span class="sxs-lookup"><span data-stu-id="eafac-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="eafac-218">**Спуфинг:** Результаты можно сгруппить по **типу Action** или **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="eafac-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="eafac-219">Щелкните **Поиск,** введите все или часть значения, а затем нажмите КНОПКУ ВВОДА, чтобы найти определенное значение.</span><span class="sxs-lookup"><span data-stu-id="eafac-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="eafac-220">По завершению щелкните ![ значок Clear search ](../../media/m365-cc-sc-close-icon.png) **Clear Search .**</span><span class="sxs-lookup"><span data-stu-id="eafac-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="eafac-221">Щелкните **Фильтр,** чтобы отфильтровать результаты.</span><span class="sxs-lookup"><span data-stu-id="eafac-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="eafac-222">Значения, доступные в **вылете Filter,** зависят от выбранной вкладки:</span><span class="sxs-lookup"><span data-stu-id="eafac-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="eafac-223">**URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="eafac-223">**URLs**</span></span>
     - <span data-ttu-id="eafac-224">**Действие**</span><span class="sxs-lookup"><span data-stu-id="eafac-224">**Action**</span></span>
     - <span data-ttu-id="eafac-225">**Не истекает срок действия**</span><span class="sxs-lookup"><span data-stu-id="eafac-225">**Never expire**</span></span>
     - <span data-ttu-id="eafac-226">**Последняя обновленная дата**</span><span class="sxs-lookup"><span data-stu-id="eafac-226">**Last updated date**</span></span>
     - <span data-ttu-id="eafac-227">**Удаление на**</span><span class="sxs-lookup"><span data-stu-id="eafac-227">**Remove on**</span></span>
   - <span data-ttu-id="eafac-228">**Files**</span><span class="sxs-lookup"><span data-stu-id="eafac-228">**Files**</span></span>
     - <span data-ttu-id="eafac-229">**Действие**</span><span class="sxs-lookup"><span data-stu-id="eafac-229">**Action**</span></span>
     - <span data-ttu-id="eafac-230">**Не истекает срок действия**</span><span class="sxs-lookup"><span data-stu-id="eafac-230">**Never expire**</span></span>
     - <span data-ttu-id="eafac-231">**Последнее обновление**</span><span class="sxs-lookup"><span data-stu-id="eafac-231">**Last updated**</span></span>
     - <span data-ttu-id="eafac-232">**Удаление на**</span><span class="sxs-lookup"><span data-stu-id="eafac-232">**Remove on**</span></span>
   - <span data-ttu-id="eafac-233">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="eafac-233">**Spoofing**</span></span>
     - <span data-ttu-id="eafac-234">**Действие**</span><span class="sxs-lookup"><span data-stu-id="eafac-234">**Action**</span></span>
     - <span data-ttu-id="eafac-235">**Тип Spoof**</span><span class="sxs-lookup"><span data-stu-id="eafac-235">**Spoof type**</span></span>

   <span data-ttu-id="eafac-236">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="eafac-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="eafac-237">Чтобы очистить существующие фильтры, **щелкните Фильтр,** а в вылете **Фильтр,** который появится, щелкните **Очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="eafac-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-238">Использование портала Microsoft 365 Defender для изменения записей в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="eafac-239">На портале Microsoft 365 Defender перейдите **к разделу** Политики & правила правил политики \>  \>  \> **угрозы Клиент разрешить и блокировать списки**.</span><span class="sxs-lookup"><span data-stu-id="eafac-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eafac-240">Выберите вкладку, которая содержит тип записи, которую необходимо изменить:</span><span class="sxs-lookup"><span data-stu-id="eafac-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="eafac-241">**URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="eafac-241">**URLs**</span></span>
   - <span data-ttu-id="eafac-242">**Files**</span><span class="sxs-lookup"><span data-stu-id="eafac-242">**Files**</span></span>
   - <span data-ttu-id="eafac-243">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="eafac-243">**Spoofing**</span></span>

3. <span data-ttu-id="eafac-244">Выберите запись, которую необходимо изменить, а затем нажмите ![ кнопку Изменить значок ](../../media/m365-cc-sc-edit-icon.png) **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="eafac-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="eafac-245">Значения, которые можно изменить в вылете, зависят от вкладки, выбранной на предыдущем шаге:</span><span class="sxs-lookup"><span data-stu-id="eafac-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="eafac-246">**URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="eafac-246">**URLs**</span></span>
     - <span data-ttu-id="eafac-247">**Не истекает** и/или не истекает срок действия.</span><span class="sxs-lookup"><span data-stu-id="eafac-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="eafac-248">**Необязательная заметка**</span><span class="sxs-lookup"><span data-stu-id="eafac-248">**Optional note**</span></span>
   - <span data-ttu-id="eafac-249">**Files**</span><span class="sxs-lookup"><span data-stu-id="eafac-249">**Files**</span></span>
     - <span data-ttu-id="eafac-250">**Не истекает** и/или не истекает срок действия.</span><span class="sxs-lookup"><span data-stu-id="eafac-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="eafac-251">**Необязательная заметка**</span><span class="sxs-lookup"><span data-stu-id="eafac-251">**Optional note**</span></span>
   - <span data-ttu-id="eafac-252">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="eafac-252">**Spoofing**</span></span>
     - <span data-ttu-id="eafac-253">**Действие.** Можно изменить значение **Разрешить или** **заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="eafac-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="eafac-254">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="eafac-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-255">Использование портала Microsoft 365 Defender для удаления записей из списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="eafac-256">На портале Microsoft 365 Defender перейдите **к разделу** Политики & правила правил политики \>  \>  \> **угрозы Клиент разрешить и блокировать списки**.</span><span class="sxs-lookup"><span data-stu-id="eafac-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eafac-257">Выберите вкладку, которая содержит тип записи, которую необходимо удалить:</span><span class="sxs-lookup"><span data-stu-id="eafac-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="eafac-258">**URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="eafac-258">**URLs**</span></span>
   - <span data-ttu-id="eafac-259">**Files**</span><span class="sxs-lookup"><span data-stu-id="eafac-259">**Files**</span></span>
   - <span data-ttu-id="eafac-260">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="eafac-260">**Spoofing**</span></span>

3. <span data-ttu-id="eafac-261">Выберите запись, которую необходимо удалить, а затем нажмите ![ кнопку Удалить значок ](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span><span class="sxs-lookup"><span data-stu-id="eafac-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="eafac-262">В диалоговом октаге предупреждения нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="eafac-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-263">Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-264">Использование PowerShell для добавления блок-файла или записей URL-адресов в список разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-265">Чтобы добавить блок-файл или ЗАПИСИ URL-адресов в список Разрешить или Заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eafac-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="eafac-266">В этом примере добавляется запись заблокированного файла для указанных файлов, срок действия которых никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="eafac-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="eafac-267">В этом примере добавляется запись URL-адреса contoso.com всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eafac-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="eafac-268">Поскольку мы не использовали параметры ExpireDate или NoExpiration, срок действия записи истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="eafac-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="eafac-269">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="eafac-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-270">Используйте PowerShell, чтобы добавить в список разрешить или заблокировать поддельные записи отправителя в список разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="eafac-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-271">Чтобы добавить подменные записи отправителя в список разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eafac-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="eafac-272">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="eafac-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-273">Использование PowerShell для просмотра записей блок-файла или URL-адресов в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-274">Чтобы просмотреть записи заблокированного файла или URL-адресов в списке разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eafac-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="eafac-275">В этом примере возвращается информация для указанного значения hash файла.</span><span class="sxs-lookup"><span data-stu-id="eafac-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="eafac-276">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="eafac-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="eafac-277">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="eafac-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-278">Использование PowerShell для просмотра записей подмены отправителя в списке разрешить или заблокировать подмену</span><span class="sxs-lookup"><span data-stu-id="eafac-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-279">Чтобы просмотреть поддельные записи отправителя в списке "Разрешить или заблокировать клиента", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eafac-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="eafac-280">В этом примере возвращаются все поддельные записи отправителя в списке разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="eafac-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="eafac-281">В этом примере возвращаются все записи подмены отправитель, которые являются внутренними.</span><span class="sxs-lookup"><span data-stu-id="eafac-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="eafac-282">В этом примере возвращаются все заблокированные поддельные записи отправитель, которые являются внешними.</span><span class="sxs-lookup"><span data-stu-id="eafac-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="eafac-283">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="eafac-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-284">Использование PowerShell для изменения записей блок-файла и URL-адресов в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-285">Чтобы изменить записи заблокированного файла и URL-адресов в списке разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eafac-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="eafac-286">В этом примере изменяется срок действия указанной записи URL-адреса блока.</span><span class="sxs-lookup"><span data-stu-id="eafac-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="eafac-287">Подробные сведения о синтаксисе и параметрах см. в [ссылке Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="eafac-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-288">Использование PowerShell для изменения допуска или блокировки подмены записей отправителя в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-289">Чтобы изменить допустимые или заблокированные записи отправителя в списке разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eafac-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="eafac-290">В этом примере изменяется подмена записи отправитель с разрешением на блокировку.</span><span class="sxs-lookup"><span data-stu-id="eafac-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="eafac-291">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="eafac-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-292">Использование PowerShell для удаления URL-адресов или записей файлов из списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-293">Чтобы удалить записи файлов и URL-адресов из списка разрешить или заблокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eafac-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="eafac-294">В этом примере удаляется указанная запись URL-адреса блокировки из списка разрешить или блокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="eafac-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="eafac-295">Подробные сведения о синтаксисе и параметрах см. в [ссылке Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="eafac-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-296">Использование PowerShell для удаления записей отправителя с подменой или блокировки из списка разрешить/заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-297">Чтобы удалить записи отправителя подмены из списка разрешить или заблокировать подмену, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eafac-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="eafac-298">Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="eafac-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-299">Синтаксис URL-адреса для списка разрешить или блокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="eafac-300">Ip4v и IPv6-адреса разрешены, но порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="eafac-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="eafac-301">Расширения filename не разрешены (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="eafac-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="eafac-302">Юникод не поддерживается, но Punycode есть.</span><span class="sxs-lookup"><span data-stu-id="eafac-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="eafac-303">Имена хост-кодов разрешены, если все следующие утверждения верны:</span><span class="sxs-lookup"><span data-stu-id="eafac-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="eafac-304">Имя хост-пользователя содержит период.</span><span class="sxs-lookup"><span data-stu-id="eafac-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="eafac-305">Существует по крайней мере один символ слева от периода.</span><span class="sxs-lookup"><span data-stu-id="eafac-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="eafac-306">Справа от периода имеется по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="eafac-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="eafac-307">Например, `t.co` разрешено или `.com` `contoso.` запрещено.</span><span class="sxs-lookup"><span data-stu-id="eafac-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="eafac-308">Subpaths не подразумеваются.</span><span class="sxs-lookup"><span data-stu-id="eafac-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="eafac-309">Например, `contoso.com` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="eafac-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="eafac-310">Поддиальды (\*) разрешены в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="eafac-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="eafac-311">За левой подгруппой должен следовать период, чтобы указать поддомен.</span><span class="sxs-lookup"><span data-stu-id="eafac-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="eafac-312">Например, `*.contoso.com` разрешено; `*contoso.com` запрещено.</span><span class="sxs-lookup"><span data-stu-id="eafac-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="eafac-313">Правая подмайка должна следовать за полосой вперед (/), чтобы указать путь.</span><span class="sxs-lookup"><span data-stu-id="eafac-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="eafac-314">Например, `contoso.com/*` разрешено или `contoso.com*` `contoso.com/ab*` запрещено.</span><span class="sxs-lookup"><span data-stu-id="eafac-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="eafac-315">Все подпаты не подразумеваются правой подгруппой.</span><span class="sxs-lookup"><span data-stu-id="eafac-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="eafac-316">Например, `contoso.com/*` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="eafac-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="eafac-317">`*.com*` является недействительным (не разрешимый домен, а правая подкратная карточка не следует передовую черту).</span><span class="sxs-lookup"><span data-stu-id="eafac-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="eafac-318">В IP-адресах запрещено использовать поддиальдные знаки.</span><span class="sxs-lookup"><span data-stu-id="eafac-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="eafac-319">Символ tilde (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="eafac-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="eafac-320">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="eafac-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="eafac-321">Например, `~contoso.com` включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="eafac-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="eafac-322">Записи URL-адресов, содержащие протоколы (например, или ) не будут работать, так как URL-записи применяются `http://` `https://` к всем `ftp://` протоколам.</span><span class="sxs-lookup"><span data-stu-id="eafac-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="eafac-323">Имя пользователя или пароль не поддерживаются или не требуются.</span><span class="sxs-lookup"><span data-stu-id="eafac-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="eafac-324">Кавычка (' или ") являются недействительными символами.</span><span class="sxs-lookup"><span data-stu-id="eafac-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="eafac-325">URL-адрес должен включать все перенаправления, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="eafac-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="eafac-326">Сценарии ввода URL-адресов</span><span class="sxs-lookup"><span data-stu-id="eafac-326">URL entry scenarios</span></span>

<span data-ttu-id="eafac-327">Допустимые записи URL-адресов и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="eafac-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="eafac-328">Сценарий: нет поддиальдов</span><span class="sxs-lookup"><span data-stu-id="eafac-328">Scenario: No wildcards</span></span>

<span data-ttu-id="eafac-329">**Запись:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="eafac-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="eafac-330">**Разрешить совпадение:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="eafac-331">**Разрешить не совпадать:**</span><span class="sxs-lookup"><span data-stu-id="eafac-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="eafac-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-332">abc-contoso.com</span></span>
  - <span data-ttu-id="eafac-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eafac-333">contoso.com/a</span></span>
  - <span data-ttu-id="eafac-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="eafac-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="eafac-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="eafac-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-337">www.contoso.com</span></span>
  - <span data-ttu-id="eafac-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="eafac-339">**Совпадение блоков:**</span><span class="sxs-lookup"><span data-stu-id="eafac-339">**Block match**:</span></span>

  - <span data-ttu-id="eafac-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-340">contoso.com</span></span>
  - <span data-ttu-id="eafac-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eafac-341">contoso.com/a</span></span>
  - <span data-ttu-id="eafac-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="eafac-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="eafac-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="eafac-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-345">www.contoso.com</span></span>
  - <span data-ttu-id="eafac-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="eafac-347">**Блок не соответствует**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="eafac-348">Сценарий: левая подгруппа (subdomain)</span><span class="sxs-lookup"><span data-stu-id="eafac-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="eafac-349">**Запись:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="eafac-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="eafac-350">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="eafac-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eafac-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-351">www.contoso.com</span></span>
  - <span data-ttu-id="eafac-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="eafac-353">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="eafac-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eafac-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-354">123contoso.com</span></span>
  - <span data-ttu-id="eafac-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-355">contoso.com</span></span>
  - <span data-ttu-id="eafac-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="eafac-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="eafac-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="eafac-358">Сценарий: правая под диктовка в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="eafac-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="eafac-359">**Запись:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="eafac-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="eafac-360">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="eafac-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eafac-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="eafac-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="eafac-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="eafac-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="eafac-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="eafac-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="eafac-364">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="eafac-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eafac-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-365">contoso.com</span></span>
  - <span data-ttu-id="eafac-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eafac-366">contoso.com/a</span></span>
  - <span data-ttu-id="eafac-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-367">www.contoso.com</span></span>
  - <span data-ttu-id="eafac-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="eafac-369">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="eafac-369">Scenario: Left tilde</span></span>

<span data-ttu-id="eafac-370">**Запись:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="eafac-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="eafac-371">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="eafac-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eafac-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-372">contoso.com</span></span>
  - <span data-ttu-id="eafac-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-373">www.contoso.com</span></span>
  - <span data-ttu-id="eafac-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="eafac-375">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="eafac-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eafac-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-376">123contoso.com</span></span>
  - <span data-ttu-id="eafac-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="eafac-377">contoso.com/abc</span></span>
  - <span data-ttu-id="eafac-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="eafac-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="eafac-379">Сценарий: суффикс правой подстановки</span><span class="sxs-lookup"><span data-stu-id="eafac-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="eafac-380">**Запись:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="eafac-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="eafac-381">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="eafac-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eafac-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="eafac-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="eafac-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eafac-383">contoso.com/a</span></span>
  - <span data-ttu-id="eafac-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="eafac-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="eafac-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="eafac-385">contoso.com/ab</span></span>
  - <span data-ttu-id="eafac-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="eafac-386">contoso.com/b</span></span>
  - <span data-ttu-id="eafac-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="eafac-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="eafac-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="eafac-388">contoso.com/ba</span></span>

- <span data-ttu-id="eafac-389">**Разрешить не совпадать** и **блок не совпадает**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="eafac-390">Сценарий. Поддомайн левой подстановки и суффикс правой подстановки</span><span class="sxs-lookup"><span data-stu-id="eafac-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="eafac-391">**Запись:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="eafac-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="eafac-392">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="eafac-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eafac-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="eafac-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="eafac-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="eafac-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="eafac-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eafac-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="eafac-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="eafac-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="eafac-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="eafac-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="eafac-398">**Разрешить не совпадать** и **блок не соответствует**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="eafac-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="eafac-399">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="eafac-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="eafac-400">**Запись:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="eafac-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="eafac-401">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="eafac-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eafac-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-402">contoso.com</span></span>
  - <span data-ttu-id="eafac-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eafac-403">contoso.com/a</span></span>
  - <span data-ttu-id="eafac-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-404">www.contoso.com</span></span>
  - <span data-ttu-id="eafac-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="eafac-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="eafac-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="eafac-407">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="eafac-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eafac-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-408">123contoso.com</span></span>
  - <span data-ttu-id="eafac-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="eafac-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="eafac-410">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="eafac-410">Scenario: IP address</span></span>

<span data-ttu-id="eafac-411">**Запись:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="eafac-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="eafac-412">**Разрешить совпадение** **и блокировку:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="eafac-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="eafac-413">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="eafac-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eafac-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="eafac-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="eafac-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="eafac-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="eafac-416">IP-адрес с правой подголой карточкой</span><span class="sxs-lookup"><span data-stu-id="eafac-416">IP address with right wildcard</span></span>

<span data-ttu-id="eafac-417">**Запись:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="eafac-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="eafac-418">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="eafac-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eafac-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="eafac-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="eafac-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="eafac-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="eafac-421">Примеры недействительных записей</span><span class="sxs-lookup"><span data-stu-id="eafac-421">Examples of invalid entries</span></span>

<span data-ttu-id="eafac-422">Следующие записи являются недействительными:</span><span class="sxs-lookup"><span data-stu-id="eafac-422">The following entries are invalid:</span></span>

- <span data-ttu-id="eafac-423">**Отсутствующие или недействительные значения домена:**</span><span class="sxs-lookup"><span data-stu-id="eafac-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="eafac-424">contoso</span><span class="sxs-lookup"><span data-stu-id="eafac-424">contoso</span></span>
  - <span data-ttu-id="eafac-425">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="eafac-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="eafac-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="eafac-426">\*.com</span></span>
  - <span data-ttu-id="eafac-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="eafac-427">\*.pdf</span></span>

- <span data-ttu-id="eafac-428">**Под диктовка текста или без интервалов символов:**</span><span class="sxs-lookup"><span data-stu-id="eafac-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="eafac-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafac-429">\*contoso.com</span></span>
  - <span data-ttu-id="eafac-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="eafac-430">contoso.com\*</span></span>
  - <span data-ttu-id="eafac-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="eafac-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="eafac-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="eafac-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="eafac-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="eafac-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="eafac-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="eafac-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="eafac-435">**IP-адреса с портами:**</span><span class="sxs-lookup"><span data-stu-id="eafac-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="eafac-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="eafac-436">contoso.com:443</span></span>
  - <span data-ttu-id="eafac-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="eafac-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="eafac-438">**Неописуемые подражательные знаки:**</span><span class="sxs-lookup"><span data-stu-id="eafac-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="eafac-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="eafac-439">\*.\*</span></span>

- <span data-ttu-id="eafac-440">**Средние подкарды:**</span><span class="sxs-lookup"><span data-stu-id="eafac-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="eafac-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="eafac-441">conto\*so.com</span></span>
  - <span data-ttu-id="eafac-442">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="eafac-442">conto~so.com</span></span>

- <span data-ttu-id="eafac-443">**Двойные подкарды**</span><span class="sxs-lookup"><span data-stu-id="eafac-443">**Double wildcards**</span></span>

  - <span data-ttu-id="eafac-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="eafac-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="eafac-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="eafac-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eafac-446">Синтаксис пары домена для подмены записей отправителя в списке Разрешить или Заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="eafac-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eafac-447">Доменная пара для подмены отправителя в Списке разрешить или заблокировать клиента использует следующий синтаксис: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="eafac-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="eafac-448">**Поддельный** пользователь. Это значение включает адрес электронной почты подмены пользователя, отображаемого в поле **From** в клиентах электронной почты.</span><span class="sxs-lookup"><span data-stu-id="eafac-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="eafac-449">Этот адрес также известен как `5322.From` адрес.</span><span class="sxs-lookup"><span data-stu-id="eafac-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="eafac-450">Допустимыми являются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="eafac-450">Valid values include:</span></span>
  - <span data-ttu-id="eafac-451">Отдельный адрес электронной почты (например, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eafac-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="eafac-452">Домен электронной почты (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eafac-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="eafac-453">Символ под диктовки (например, \* ).</span><span class="sxs-lookup"><span data-stu-id="eafac-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="eafac-454">**Инфраструктура отправки.** Это значение указывает источник сообщений от подмены пользователя.</span><span class="sxs-lookup"><span data-stu-id="eafac-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="eafac-455">Допустимыми являются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="eafac-455">Valid values include:</span></span>
  - <span data-ttu-id="eafac-456">Домен, найденный в обратной DNS-записи IP-адреса сервера электронной почты источника (например, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="eafac-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="eafac-457">Если исходный IP-адрес не имеет записи PTR, инфраструктура отправки определена как \<source IP\> /24 (например, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="eafac-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="eafac-458">Вот несколько примеров допустимой пары домена для определения поддельных отправителей:</span><span class="sxs-lookup"><span data-stu-id="eafac-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="eafac-459">Максимальное количество подмены записей отправитель 1000.</span><span class="sxs-lookup"><span data-stu-id="eafac-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="eafac-460">Добавление доменной пары позволяет или  блокирует только сочетание подмены пользователя и *инфраструктуры* отправки.</span><span class="sxs-lookup"><span data-stu-id="eafac-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="eafac-461">Он не разрешает электронную почту от подмены пользователя из любого источника, а также не разрешает электронную почту из источника инфраструктуры отправки для любого подменного пользователя.</span><span class="sxs-lookup"><span data-stu-id="eafac-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="eafac-462">Например, вы добавляете допустимую запись для следующей пары доменов:</span><span class="sxs-lookup"><span data-stu-id="eafac-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="eafac-463">**Домен**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="eafac-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="eafac-464">**Инфраструктура**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="eafac-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="eafac-465">Подмену допускаются только сообщения из этого *домена* и пара инфраструктуры отправки.</span><span class="sxs-lookup"><span data-stu-id="eafac-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="eafac-466">Другие отправители, пытающиеся gmail.com, не допускаются.</span><span class="sxs-lookup"><span data-stu-id="eafac-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="eafac-467">Сообщения от отправителей в других доменах, исходя из tms.mx.com, проверяются с помощью spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="eafac-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
