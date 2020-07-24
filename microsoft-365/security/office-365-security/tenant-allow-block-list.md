---
title: Управление разрешенными и заблокированными URL-адресами и файлами в списке разрешенных и запрещенных клиентов
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться настраивать URL-адреса и записи файлов в списке разрешенных и запрещенных клиентов в центре безопасности & соответствия требованиям.
ms.openlocfilehash: db34abf28b5ead8106eb0b1447052d63072b2da3
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391570"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-103">Управление URL-адресами и файлами в списке разрешенных и заблокированных клиентов</span><span class="sxs-lookup"><span data-stu-id="ba378-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="ba378-104">Функции, описанные в этой статье, в предварительной версии, могут быть изменены и недоступны во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="ba378-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="ba378-105">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или в автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не противовниманияию фильтра EOP вредоносности.</span><span class="sxs-lookup"><span data-stu-id="ba378-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="ba378-106">Например, хорошее сообщение может быть помечено как плохое (ложный положительный результат), или может быть разрешено неправильное сообщение (ложное отрицательное).</span><span class="sxs-lookup"><span data-stu-id="ba378-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="ba378-107">Список разрешенных и заблокированных клиентов в центре безопасности & соответствия требованиям позволяет вручную переопределить вердиктс фильтрации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba378-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="ba378-108">Список разрешенных и заблокированных клиентов используется во время процесса обработки почты и при нажатии пользователем.</span><span class="sxs-lookup"><span data-stu-id="ba378-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="ba378-109">Вы можете указать URL-адреса и файлы, которые будут разрешены или заблокированы в списке разрешенных или запрещенных клиентов.</span><span class="sxs-lookup"><span data-stu-id="ba378-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="ba378-110">В этом разделе описывается, как настроить записи в списке разрешенных и запрещенных клиентов в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ba378-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ba378-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="ba378-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ba378-112">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ba378-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ba378-113">Чтобы перейти непосредственно на страницу **списка разрешенных и заблокированных клиентов** , используйте <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="ba378-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="ba378-114">Вы указываете файлы, используя значение хэша SHA256 файла.</span><span class="sxs-lookup"><span data-stu-id="ba378-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="ba378-115">Чтобы найти хэш-значение SHA256 файла в Windows, выполните следующую команду в командной строки:</span><span class="sxs-lookup"><span data-stu-id="ba378-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="ba378-116">Пример значения: `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="ba378-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="ba378-117">Значения хэша перцептуал (Фаш) не допускаются.</span><span class="sxs-lookup"><span data-stu-id="ba378-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="ba378-118">Доступные значения URL-адреса описаны в [синтаксисе URL-адреса для списка разрешений/блокировок клиентов](#url-syntax-for-the-tenant-allowblock-list) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ba378-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="ba378-119">В списке разрешенных и запрещенных клиентов можно указать не более 500 записей для URL-адресов и 500 записей для хэшей файлов.</span><span class="sxs-lookup"><span data-stu-id="ba378-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="ba378-120">Запись должна быть активна в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="ba378-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="ba378-121">Записи блокировки имеют приоритет над разрешающими записями.</span><span class="sxs-lookup"><span data-stu-id="ba378-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="ba378-122">По умолчанию срок действия записей в списке разрешений/блокировок клиентов истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="ba378-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="ba378-123">Вы можете указать дату или запретить срок ее действия.</span><span class="sxs-lookup"><span data-stu-id="ba378-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="ba378-124">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ba378-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ba378-125">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ba378-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ba378-126">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="ba378-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="ba378-127">Чтобы добавить или удалить значения из списка разрешенных и заблокированных клиентов, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="ba378-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ba378-128">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ba378-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ba378-129">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ba378-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="ba378-130">Для доступа только для чтения к списку разрешенных и запрещенных клиентов необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="ba378-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ba378-131">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ba378-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ba378-132">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ba378-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-133">Использование центра безопасности & соответствия требованиям для создания записей URL-адресов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="ba378-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ba378-134">Для получения подробных сведений о синтаксисе для записей URL-адресов просмотрите [синтаксис URL-адресов для списка разрешенных и заблокированных адресов](#url-syntax-for-the-tenant-allowblock-list) в разделе далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ba378-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="ba378-135">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="ba378-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ba378-136">На странице **списка разрешенных и заблокированных клиентов** убедитесь, что выбрана вкладка **URL-адреса** , а затем нажмите кнопку **добавить** .</span><span class="sxs-lookup"><span data-stu-id="ba378-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="ba378-137">В появившемся всплывающем окне **Добавление новых URL-адресов** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ba378-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ba378-138">**Добавьте URL-адреса с подстановочными знаками**: введите один URL-адрес в строке длиной не более 20.</span><span class="sxs-lookup"><span data-stu-id="ba378-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ba378-139">**Блокировать/Разрешить**: укажите, хотите ли вы **Разрешить** или **запретить** указанные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="ba378-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="ba378-140">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="ba378-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ba378-141">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и в поле **истечение срока действия** указан срок действия для записей.</span><span class="sxs-lookup"><span data-stu-id="ba378-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ba378-142">или</span><span class="sxs-lookup"><span data-stu-id="ba378-142">or</span></span>

     - <span data-ttu-id="ba378-143">Переместите переключатель вправо, чтобы задать срок действия бессрочных записей:</span><span class="sxs-lookup"><span data-stu-id="ba378-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="ba378-145">.</span><span class="sxs-lookup"><span data-stu-id="ba378-145">.</span></span>

   - <span data-ttu-id="ba378-146">**Необязательное примечание**: введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="ba378-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ba378-147">По завершении нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ba378-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-148">Использование центра безопасности & соответствия требованиям для создания записей файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="ba378-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ba378-149">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="ba378-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ba378-150">На странице " **список разрешений/блокировок клиентов** " выберите вкладку **файлы** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="ba378-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="ba378-151">В появившемся всплывающем окне **Добавление новых файлов** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ba378-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ba378-152">**Добавить хэши файлов**: введите одно значение хэша SHA256 на строку длиной не более 20.</span><span class="sxs-lookup"><span data-stu-id="ba378-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ba378-153">**Блокировать/Разрешить**: укажите, хотите ли вы **Разрешить** или **запретить** указанные файлы.</span><span class="sxs-lookup"><span data-stu-id="ba378-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="ba378-154">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="ba378-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ba378-155">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и в поле **истечение срока действия** указан срок действия для записей.</span><span class="sxs-lookup"><span data-stu-id="ba378-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ba378-156">или</span><span class="sxs-lookup"><span data-stu-id="ba378-156">or</span></span>

     - <span data-ttu-id="ba378-157">Переместите переключатель вправо, чтобы задать срок действия бессрочных записей:</span><span class="sxs-lookup"><span data-stu-id="ba378-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="ba378-159">.</span><span class="sxs-lookup"><span data-stu-id="ba378-159">.</span></span>

   - <span data-ttu-id="ba378-160">**Необязательное примечание**: введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="ba378-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ba378-161">По завершении нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ba378-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-162">Использование центра безопасности & соответствия требованиям для просмотра записей URL-адресов и файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="ba378-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ba378-163">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="ba378-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ba378-164">Перейдите на вкладку " **URL-адреса** " или " **файлы** ".</span><span class="sxs-lookup"><span data-stu-id="ba378-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="ba378-165">Щелкните следующие заголовки столбцов, чтобы отсортировать их по возрастанию или убыванию:</span><span class="sxs-lookup"><span data-stu-id="ba378-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="ba378-166">**Значение**: URL-адрес или хэш файла.</span><span class="sxs-lookup"><span data-stu-id="ba378-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="ba378-167">**Действие**: **блокировать** или **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="ba378-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="ba378-168">**Дата последнего обновления**</span><span class="sxs-lookup"><span data-stu-id="ba378-168">**Last updated date**</span></span>
- <span data-ttu-id="ba378-169">**Дата истечения срока действия**</span><span class="sxs-lookup"><span data-stu-id="ba378-169">**Expiration date**</span></span>
- <span data-ttu-id="ba378-170">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="ba378-170">**Note**</span></span>

<span data-ttu-id="ba378-171">Щелкните **Group (Группа** ), чтобы сгруппировать записи по **действию** (**блокировать** или **Разрешить**) или **нет**.</span><span class="sxs-lookup"><span data-stu-id="ba378-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="ba378-172">Нажмите кнопку **Поиск**, введите полностью или частично URL-адрес или значение файла, а затем нажмите клавишу ВВОД, чтобы найти конкретное значение.</span><span class="sxs-lookup"><span data-stu-id="ba378-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="ba378-173">По завершении нажмите кнопку **очистить** поиск ![ Очистить поиск значок ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="ba378-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="ba378-174">Нажмите кнопку **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="ba378-174">Click **Filter**.</span></span> <span data-ttu-id="ba378-175">В появившемся всплывающем окне **фильтра** настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ba378-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="ba378-176">**Действие**: выберите **Разрешить**, **блокировать** или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="ba378-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="ba378-177">**Никогда не истечет**: выберите Выключить (выключить ![ ](../../media/scc-toggle-off.png) ) или включить (включить ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="ba378-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="ba378-178">**Последнее обновление**: выберите дату начала (**from**), конечную дату (конечную) или и**то, и**другое.</span><span class="sxs-lookup"><span data-stu-id="ba378-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="ba378-179">**Дата окончания срока действия**: выберите дату начала (**от**), конечную дату (**до**) или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="ba378-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="ba378-180">Когда все будет готово, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ba378-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="ba378-181">Чтобы очистить существующие фильтры, нажмите кнопку **Фильтр**, а затем в появившемся всплывающем окне **фильтра** щелкните **Очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="ba378-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-182">Используйте центр соответствия требованиям & безопасности для изменения URL-адресов и записей файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="ba378-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ba378-183">Невозможно изменить URL-адрес или значение файла.</span><span class="sxs-lookup"><span data-stu-id="ba378-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="ba378-184">Вместо этого необходимо удалить запись и создать ее повторно.</span><span class="sxs-lookup"><span data-stu-id="ba378-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="ba378-185">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="ba378-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ba378-186">Перейдите на вкладку " **URL-адреса** " или " **файлы** ".</span><span class="sxs-lookup"><span data-stu-id="ba378-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="ba378-187">Выберите запись, которую необходимо изменить, а затем щелкните **изменить** ![ значок редактирования ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="ba378-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="ba378-188">В появившемся всплывающем меню настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ba378-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ba378-189">**Блокировать/Разрешить**: выберите **Разрешить** или **заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="ba378-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="ba378-190">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="ba378-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ba378-191">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и укажите срок действия для записи, используя поле **срок действия** .</span><span class="sxs-lookup"><span data-stu-id="ba378-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="ba378-192">или</span><span class="sxs-lookup"><span data-stu-id="ba378-192">or</span></span>

     - <span data-ttu-id="ba378-193">Переместите переключатель вправо, чтобы задать срок действия бессрочной записи:</span><span class="sxs-lookup"><span data-stu-id="ba378-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="ba378-195">.</span><span class="sxs-lookup"><span data-stu-id="ba378-195">.</span></span>

   - <span data-ttu-id="ba378-196">**Необязательное примечание**: введите описательный текст для записи.</span><span class="sxs-lookup"><span data-stu-id="ba378-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="ba378-197">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ba378-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-198">Использование центра безопасности & соответствия требованиям для удаления записей URL и файлов из списка разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="ba378-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ba378-199">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="ba378-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ba378-200">Перейдите на вкладку " **URL-адреса** " или " **файлы** ".</span><span class="sxs-lookup"><span data-stu-id="ba378-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="ba378-201">Выберите запись, которую нужно удалить, и нажмите кнопку **Удалить** ![ значок удаления ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="ba378-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="ba378-202">В появившемся диалоговом окне предупреждения нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ba378-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-203">Настройка списка разрешений/блокировок клиентов с помощью Exchange Online PowerShell или изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba378-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-204">Добавление URL-адресов и записей файлов в список разрешений/блокировок клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba378-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ba378-205">Чтобы добавить URL-адреса и записи файлов в список разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ba378-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ba378-206">В этом примере добавляется запись блока URL-адреса для contoso.com и всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ba378-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="ba378-207">Так как мы не использовали параметры ExpirationDate или параметру expiration, срок действия записи истечет через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="ba378-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="ba378-208">В этом примере показано, как добавить в файл запись разрешения для указанных файлов, срок действия которых не ограничен.</span><span class="sxs-lookup"><span data-stu-id="ba378-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="ba378-209">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ba378-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-210">Использование PowerShell для просмотра записей URL-адресов и файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="ba378-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ba378-211">Чтобы просмотреть записи URL-адресов и файлов в списке разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ba378-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="ba378-212">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="ba378-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="ba378-213">В этом примере возвращаются сведения о указанном хэш-значении файла.</span><span class="sxs-lookup"><span data-stu-id="ba378-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="ba378-214">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ba378-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-215">Использование PowerShell для изменения записей URL-адресов и файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="ba378-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ba378-216">Невозможно изменить URL-адрес или значение файла.</span><span class="sxs-lookup"><span data-stu-id="ba378-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="ba378-217">Вместо этого необходимо удалить запись и создать ее повторно.</span><span class="sxs-lookup"><span data-stu-id="ba378-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="ba378-218">Чтобы изменить URL-адреса и записи файлов в списке разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ba378-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ba378-219">В этом примере изменяется дата окончания срока действия указанной записи.</span><span class="sxs-lookup"><span data-stu-id="ba378-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="ba378-220">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ba378-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-221">Удаление URL-адресов и записей файлов из списка разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba378-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ba378-222">Чтобы удалить URL-адреса и записи файлов из списка разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ba378-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ba378-223">В этом примере из списка разрешенных и запрещенных клиентов удаляется указанная запись URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="ba378-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="ba378-224">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ba378-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="ba378-225">Синтаксис URL-адреса для списка разрешений/блокировок клиентов</span><span class="sxs-lookup"><span data-stu-id="ba378-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="ba378-226">IP4v и IPv6-адреса разрешены, но порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="ba378-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="ba378-227">Расширения имен файлов не допускаются (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="ba378-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="ba378-228">Юникод не поддерживается, но Punycode — Punycode.</span><span class="sxs-lookup"><span data-stu-id="ba378-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="ba378-229">Имена узлов разрешены, если выполняются все приведенные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="ba378-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="ba378-230">Имя узла содержит точку.</span><span class="sxs-lookup"><span data-stu-id="ba378-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="ba378-231">Слева от точки есть по крайней мере один символ.</span><span class="sxs-lookup"><span data-stu-id="ba378-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="ba378-232">Справа от точки есть по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="ba378-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="ba378-233">Например, `t.co` разрешено; `.com` или `contoso.` не разрешено.</span><span class="sxs-lookup"><span data-stu-id="ba378-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="ba378-234">Вложенные пути не являются подразумеваемыми.</span><span class="sxs-lookup"><span data-stu-id="ba378-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="ba378-235">Например, не `contoso.com` включается `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ba378-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="ba378-236">Подстановочные знаки (\*) разрешены в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="ba378-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="ba378-237">За левым подстановочным знаком должен следовать точка для указания поддомена.</span><span class="sxs-lookup"><span data-stu-id="ba378-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="ba378-238">Например, `*.contoso.com` разрешено; запрещено `*contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="ba378-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="ba378-239">Для указания пути должен следовать символу подстановки (/).</span><span class="sxs-lookup"><span data-stu-id="ba378-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="ba378-240">Например, `contoso.com/*` разрешено; `contoso.com*` или `contoso.com/ab*` не разрешено.</span><span class="sxs-lookup"><span data-stu-id="ba378-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="ba378-241">Все подпути не подразумеваются с помощью подстановочного знака справа.</span><span class="sxs-lookup"><span data-stu-id="ba378-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="ba378-242">Например, не `contoso.com/*` включается `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ba378-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="ba378-243">`*.com*`недействителен (не является разрешимым доменом, а правильный подстановочный знак не следует за косой чертой).</span><span class="sxs-lookup"><span data-stu-id="ba378-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="ba378-244">Подстановочные знаки не разрешены в IP-адресах.</span><span class="sxs-lookup"><span data-stu-id="ba378-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="ba378-245">Символ тильды (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="ba378-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="ba378-246">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="ba378-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="ba378-247">Например `~contoso.com` , включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="ba378-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="ba378-248">URL-адреса, содержащие протоколы (например,, `http://` `https://` или `ftp://` ), завершатся неуспешно, так как записи URL-адресов применяются ко всем протоколам.</span><span class="sxs-lookup"><span data-stu-id="ba378-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="ba378-249">Имя пользователя или пароль не поддерживаются или не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="ba378-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="ba378-250">Кавычки (' или ") являются недопустимыми символами.</span><span class="sxs-lookup"><span data-stu-id="ba378-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="ba378-251">URL-адрес должен включать все перенаправления, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="ba378-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="ba378-252">Сценарии ввода URL-адресов</span><span class="sxs-lookup"><span data-stu-id="ba378-252">URL entry scenarios</span></span>

<span data-ttu-id="ba378-253">Допустимые записи URL-адреса и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ba378-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="ba378-254">Сценарий: без подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="ba378-254">Scenario: No wildcards</span></span>

<span data-ttu-id="ba378-255">**Запись**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ba378-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="ba378-256">**Разрешить согласование**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="ba378-257">**Разрешить не сопоставляемые**:</span><span class="sxs-lookup"><span data-stu-id="ba378-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="ba378-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-258">abc-contoso.com</span></span>
  - <span data-ttu-id="ba378-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ba378-259">contoso.com/a</span></span>
  - <span data-ttu-id="ba378-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="ba378-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="ba378-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ba378-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-263">www.contoso.com</span></span>
  - <span data-ttu-id="ba378-264">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ba378-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="ba378-265">**Согласование блока**:</span><span class="sxs-lookup"><span data-stu-id="ba378-265">**Block match**:</span></span>

  - <span data-ttu-id="ba378-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-266">contoso.com</span></span>
  - <span data-ttu-id="ba378-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ba378-267">contoso.com/a</span></span>
  - <span data-ttu-id="ba378-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="ba378-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="ba378-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ba378-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-271">www.contoso.com</span></span>
  - <span data-ttu-id="ba378-272">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ba378-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ba378-273">**Блок не сопоставлен**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="ba378-274">Сценарий: левый подстановочный знак (поддомен)</span><span class="sxs-lookup"><span data-stu-id="ba378-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="ba378-275">**Запись**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ba378-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="ba378-276">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="ba378-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ba378-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-277">www.contoso.com</span></span>
  - <span data-ttu-id="ba378-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ba378-279">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="ba378-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ba378-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-280">123contoso.com</span></span>
  - <span data-ttu-id="ba378-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-281">contoso.com</span></span>
  - <span data-ttu-id="ba378-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="ba378-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ba378-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="ba378-284">Сценарий: подстановочный знак "справа" в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="ba378-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="ba378-285">**Запись**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="ba378-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="ba378-286">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="ba378-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ba378-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="ba378-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="ba378-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ba378-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ba378-289">Contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="ba378-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="ba378-290">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="ba378-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ba378-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-291">contoso.com</span></span>
  - <span data-ttu-id="ba378-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ba378-292">contoso.com/a</span></span>
  - <span data-ttu-id="ba378-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-293">www.contoso.com</span></span>
  - <span data-ttu-id="ba378-294">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ba378-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="ba378-295">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="ba378-295">Scenario: Left tilde</span></span>

<span data-ttu-id="ba378-296">**Запись**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ba378-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="ba378-297">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="ba378-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ba378-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-298">contoso.com</span></span>
  - <span data-ttu-id="ba378-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-299">www.contoso.com</span></span>
  - <span data-ttu-id="ba378-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ba378-301">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="ba378-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ba378-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-302">123contoso.com</span></span>
  - <span data-ttu-id="ba378-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ba378-303">contoso.com/abc</span></span>
  - <span data-ttu-id="ba378-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ba378-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="ba378-305">Сценарий: правый подстановочный суффикс</span><span class="sxs-lookup"><span data-stu-id="ba378-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="ba378-306">**Запись**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ba378-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="ba378-307">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="ba378-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ba378-308">Contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="ba378-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="ba378-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ba378-309">contoso.com/a</span></span>
  - <span data-ttu-id="ba378-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ba378-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ba378-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ba378-311">contoso.com/ab</span></span>
  - <span data-ttu-id="ba378-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ba378-312">contoso.com/b</span></span>
  - <span data-ttu-id="ba378-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ba378-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ba378-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ba378-314">contoso.com/ba</span></span>

- <span data-ttu-id="ba378-315">**Разрешить не сопоставляемые** и непарные **блоки**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="ba378-316">Сценарий: левый и правый суффиксы для поддоменов подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="ba378-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="ba378-317">**Запись**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ba378-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="ba378-318">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="ba378-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ba378-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ba378-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="ba378-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ba378-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ba378-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ba378-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="ba378-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ba378-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ba378-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ba378-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="ba378-324">**Разрешить не сопоставляемые** и непарные **блоки**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ba378-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="ba378-325">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="ba378-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="ba378-326">**Запись**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="ba378-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="ba378-327">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="ba378-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ba378-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-328">contoso.com</span></span>
  - <span data-ttu-id="ba378-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ba378-329">contoso.com/a</span></span>
  - <span data-ttu-id="ba378-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-330">www.contoso.com</span></span>
  - <span data-ttu-id="ba378-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ba378-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="ba378-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ba378-333">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="ba378-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ba378-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-334">123contoso.com</span></span>
  - <span data-ttu-id="ba378-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="ba378-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="ba378-336">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="ba378-336">Scenario: IP address</span></span>

<span data-ttu-id="ba378-337">**Запись**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="ba378-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="ba378-338">**Разрешить ПОИСКПОЗ** и **блокировать ПОИСКПОЗ**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ba378-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="ba378-339">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="ba378-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ba378-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ba378-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="ba378-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ba378-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="ba378-342">IP-адрес с подстановкой по правому краю</span><span class="sxs-lookup"><span data-stu-id="ba378-342">IP address with right wildcard</span></span>

<span data-ttu-id="ba378-343">**Запись**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="ba378-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="ba378-344">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="ba378-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ba378-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="ba378-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="ba378-346">1.2.3.4/баааа</span><span class="sxs-lookup"><span data-stu-id="ba378-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="ba378-347">Примеры недопустимых записей</span><span class="sxs-lookup"><span data-stu-id="ba378-347">Examples of invalid entries</span></span>

<span data-ttu-id="ba378-348">Следующие записи недопустимы:</span><span class="sxs-lookup"><span data-stu-id="ba378-348">The following entries are invalid:</span></span>

- <span data-ttu-id="ba378-349">**Отсутствующие или недопустимые значения домена**:</span><span class="sxs-lookup"><span data-stu-id="ba378-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="ba378-350">компанией</span><span class="sxs-lookup"><span data-stu-id="ba378-350">contoso</span></span>
  - <span data-ttu-id="ba378-351">\*компанией.\*</span><span class="sxs-lookup"><span data-stu-id="ba378-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="ba378-352">\*. com</span><span class="sxs-lookup"><span data-stu-id="ba378-352">\*.com</span></span>
  - <span data-ttu-id="ba378-353">\*PDF</span><span class="sxs-lookup"><span data-stu-id="ba378-353">\*.pdf</span></span>

- <span data-ttu-id="ba378-354">**Подстановочный знак для текста или без пробелов**:</span><span class="sxs-lookup"><span data-stu-id="ba378-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="ba378-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba378-355">\*contoso.com</span></span>
  - <span data-ttu-id="ba378-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="ba378-356">contoso.com\*</span></span>
  - <span data-ttu-id="ba378-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ba378-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="ba378-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="ba378-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="ba378-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="ba378-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="ba378-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="ba378-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="ba378-361">**IP-адреса с портами**:</span><span class="sxs-lookup"><span data-stu-id="ba378-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="ba378-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="ba378-362">contoso.com:443</span></span>
  - <span data-ttu-id="ba378-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="ba378-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="ba378-364">**Подстановочные знаки, не являющиеся описательными**:</span><span class="sxs-lookup"><span data-stu-id="ba378-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="ba378-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="ba378-365">\*.\*</span></span>

- <span data-ttu-id="ba378-366">**Посрединные подстановочные знаки**:</span><span class="sxs-lookup"><span data-stu-id="ba378-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="ba378-367">Конто \* so.com</span><span class="sxs-lookup"><span data-stu-id="ba378-367">conto\*so.com</span></span>
  - <span data-ttu-id="ba378-368">Конто ~ so. com</span><span class="sxs-lookup"><span data-stu-id="ba378-368">conto~so.com</span></span>

- <span data-ttu-id="ba378-369">**Знаки подстановки двойной замены**</span><span class="sxs-lookup"><span data-stu-id="ba378-369">**Double wildcards**</span></span>

  - <span data-ttu-id="ba378-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="ba378-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="ba378-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="ba378-371">contoso.com/\*/\*</span></span>
