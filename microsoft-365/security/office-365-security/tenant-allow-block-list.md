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
ROBOTS: NOINDEX, NOFOLLOW
description: Администраторы могут научиться настраивать URL-адреса и записи файлов в списке разрешенных и запрещенных клиентов в центре безопасности & соответствия требованиям.
ms.openlocfilehash: b3a25458bbde2b3a78cfecc60ccb75fe298013f7
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419272"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-103">Управление URL-адресами и файлами в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="54d8f-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="54d8f-104">Функции, описанные в этой статье, в предварительной версии, могут быть изменены и недоступны во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="54d8f-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="54d8f-105">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или в автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не противовниманияию фильтра EOP вредоносности.</span><span class="sxs-lookup"><span data-stu-id="54d8f-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="54d8f-106">Например, хорошее сообщение может быть помечено как плохое (ложный положительный результат), или может быть разрешено неправильное сообщение (ложное отрицательное).</span><span class="sxs-lookup"><span data-stu-id="54d8f-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="54d8f-107">Список разрешенных и заблокированных клиентов в центре безопасности & соответствия требованиям позволяет вручную переопределить вердиктс фильтрации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="54d8f-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="54d8f-108">Список разрешенных и заблокированных клиентов используется во время процесса обработки почты и при нажатии пользователем.</span><span class="sxs-lookup"><span data-stu-id="54d8f-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="54d8f-109">Вы можете указать URL-адреса и файлы, которые будут разрешены или заблокированы в списке разрешенных или запрещенных клиентов.</span><span class="sxs-lookup"><span data-stu-id="54d8f-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="54d8f-110">В этом разделе описывается, как настроить записи в списке разрешенных и запрещенных клиентов в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="54d8f-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="54d8f-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="54d8f-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="54d8f-112">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="54d8f-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="54d8f-113">Чтобы перейти непосредственно на страницу **списка разрешенных и заблокированных клиентов** , используйте <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="54d8f-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="54d8f-114">Вы указываете файлы, используя значение хэша SHA256 файла.</span><span class="sxs-lookup"><span data-stu-id="54d8f-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="54d8f-115">Чтобы найти хэш-значение SHA256 файла в Windows, выполните следующую команду в командной строки:</span><span class="sxs-lookup"><span data-stu-id="54d8f-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="54d8f-116">Пример значения: `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="54d8f-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="54d8f-117">Значения хэша перцептуал (Фаш) не допускаются.</span><span class="sxs-lookup"><span data-stu-id="54d8f-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="54d8f-118">Доступные значения URL-адреса описаны в [синтаксисе URL-адреса для списка разрешений/блокировок клиентов](#url-syntax-for-the-tenant-allowblock-list) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="54d8f-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="54d8f-119">В списке разрешенных и запрещенных клиентов можно указать не более 500 записей для URL-адресов и 500 записей для хэшей файлов.</span><span class="sxs-lookup"><span data-stu-id="54d8f-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="54d8f-120">Запись должна быть активна в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="54d8f-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="54d8f-121">Записи блокировки имеют приоритет над разрешающими записями.</span><span class="sxs-lookup"><span data-stu-id="54d8f-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="54d8f-122">По умолчанию срок действия записей в списке разрешений/блокировок клиентов истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="54d8f-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="54d8f-123">Вы можете указать дату или запретить срок ее действия.</span><span class="sxs-lookup"><span data-stu-id="54d8f-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="54d8f-124">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="54d8f-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="54d8f-125">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="54d8f-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="54d8f-126">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="54d8f-126">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="54d8f-127">Чтобы добавить или удалить значения из списка разрешенных и заблокированных клиентов, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="54d8f-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="54d8f-128">Для доступа только для чтения к списку разрешенных и запрещенных клиентов необходимо быть участником группы ролей " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="54d8f-128">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="54d8f-129">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="54d8f-129">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-130">Использование центра безопасности & соответствия требованиям для создания записей URL-адресов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="54d8f-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="54d8f-131">Для получения подробных сведений о синтаксисе для записей URL-адресов просмотрите [синтаксис URL-адресов для списка разрешенных и заблокированных адресов](#url-syntax-for-the-tenant-allowblock-list) в разделе далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="54d8f-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="54d8f-132">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="54d8f-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="54d8f-133">На странице **списка разрешенных и заблокированных клиентов** убедитесь, что выбрана вкладка **URL-адреса** , а затем нажмите кнопку **добавить** .</span><span class="sxs-lookup"><span data-stu-id="54d8f-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="54d8f-134">В появившемся всплывающем окне **Добавление новых URL-адресов** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="54d8f-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="54d8f-135">**Добавьте URL-адреса с подстановочными знаками**: введите один URL-адрес в строке длиной не более 20.</span><span class="sxs-lookup"><span data-stu-id="54d8f-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="54d8f-136">**Блокировать/Разрешить**: укажите, хотите ли вы **Разрешить** или **запретить** указанные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="54d8f-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="54d8f-137">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="54d8f-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="54d8f-138">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и в поле **истечение срока действия** указан срок действия для записей.</span><span class="sxs-lookup"><span data-stu-id="54d8f-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="54d8f-139">или</span><span class="sxs-lookup"><span data-stu-id="54d8f-139">or</span></span>

     - <span data-ttu-id="54d8f-140">Переместите переключатель вправо, чтобы задать срок действия бессрочных записей:</span><span class="sxs-lookup"><span data-stu-id="54d8f-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="54d8f-142">.</span><span class="sxs-lookup"><span data-stu-id="54d8f-142">.</span></span>

   - <span data-ttu-id="54d8f-143">**Необязательное примечание**: введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="54d8f-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="54d8f-144">По завершении нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-145">Использование центра безопасности & соответствия требованиям для создания записей файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="54d8f-145">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="54d8f-146">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="54d8f-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="54d8f-147">На странице " **список разрешений/блокировок клиентов** " выберите вкладку **файлы** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-147">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="54d8f-148">В появившемся всплывающем окне **Добавление новых файлов** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="54d8f-148">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="54d8f-149">**Добавить хэши файлов**: введите одно значение хэша SHA256 на строку длиной не более 20.</span><span class="sxs-lookup"><span data-stu-id="54d8f-149">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="54d8f-150">**Блокировать/Разрешить**: укажите, хотите ли вы **Разрешить** или **запретить** указанные файлы.</span><span class="sxs-lookup"><span data-stu-id="54d8f-150">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="54d8f-151">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="54d8f-151">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="54d8f-152">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и в поле **истечение срока действия** указан срок действия для записей.</span><span class="sxs-lookup"><span data-stu-id="54d8f-152">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="54d8f-153">или</span><span class="sxs-lookup"><span data-stu-id="54d8f-153">or</span></span>

     - <span data-ttu-id="54d8f-154">Переместите переключатель вправо, чтобы задать срок действия бессрочных записей:</span><span class="sxs-lookup"><span data-stu-id="54d8f-154">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="54d8f-156">.</span><span class="sxs-lookup"><span data-stu-id="54d8f-156">.</span></span>

   - <span data-ttu-id="54d8f-157">**Необязательное примечание**: введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="54d8f-157">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="54d8f-158">По завершении нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-158">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-159">Использование центра безопасности & соответствия требованиям для просмотра записей URL-адресов и файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="54d8f-159">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="54d8f-160">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="54d8f-160">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="54d8f-161">Перейдите на вкладку " **URL-адреса** " или " **файлы** ".</span><span class="sxs-lookup"><span data-stu-id="54d8f-161">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="54d8f-162">Щелкните следующие заголовки столбцов, чтобы отсортировать их по возрастанию или убыванию:</span><span class="sxs-lookup"><span data-stu-id="54d8f-162">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="54d8f-163">**Значение**: URL-адрес или хэш файла.</span><span class="sxs-lookup"><span data-stu-id="54d8f-163">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="54d8f-164">**Действие**: **блокировать** или **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-164">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="54d8f-165">**Дата последнего обновления**</span><span class="sxs-lookup"><span data-stu-id="54d8f-165">**Last updated date**</span></span>
- <span data-ttu-id="54d8f-166">**Дата истечения срока действия**</span><span class="sxs-lookup"><span data-stu-id="54d8f-166">**Expiration date**</span></span>
- <span data-ttu-id="54d8f-167">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="54d8f-167">**Note**</span></span>

<span data-ttu-id="54d8f-168">Щелкните **Group (Группа** ), чтобы сгруппировать записи по **действию** (**блокировать** или **Разрешить**) или **нет**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-168">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="54d8f-169">Нажмите кнопку **Поиск**, введите полностью или частично URL-адрес или значение файла, а затем нажмите клавишу ВВОД, чтобы найти конкретное значение.</span><span class="sxs-lookup"><span data-stu-id="54d8f-169">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="54d8f-170">По завершении нажмите кнопку **очистить** поиск ![ Очистить поиск значок ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="54d8f-170">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="54d8f-171">Нажмите кнопку **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-171">Click **Filter**.</span></span> <span data-ttu-id="54d8f-172">В появившемся всплывающем окне **фильтра** настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="54d8f-172">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="54d8f-173">**Действие**: выберите **Разрешить**, **блокировать** или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="54d8f-173">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="54d8f-174">**Никогда не истечет**: выберите Выключить (выключить ![ ](../../media/scc-toggle-off.png) ) или включить (включить ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="54d8f-174">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="54d8f-175">**Последнее обновление**: выберите дату начала (**from**), конечную дату (конечную) или и**то, и**другое.</span><span class="sxs-lookup"><span data-stu-id="54d8f-175">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="54d8f-176">**Дата окончания срока действия**: выберите дату начала (**от**), конечную дату (**до**) или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="54d8f-176">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="54d8f-177">Когда все будет готово, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-177">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="54d8f-178">Чтобы очистить существующие фильтры, нажмите кнопку **Фильтр**, а затем в появившемся всплывающем окне **фильтра** щелкните **Очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-178">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-179">Используйте центр соответствия требованиям & безопасности для изменения URL-адресов и записей файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="54d8f-179">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="54d8f-180">Невозможно изменить URL-адрес или значение файла.</span><span class="sxs-lookup"><span data-stu-id="54d8f-180">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="54d8f-181">Вместо этого необходимо удалить запись и создать ее повторно.</span><span class="sxs-lookup"><span data-stu-id="54d8f-181">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="54d8f-182">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="54d8f-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="54d8f-183">Перейдите на вкладку " **URL-адреса** " или " **файлы** ".</span><span class="sxs-lookup"><span data-stu-id="54d8f-183">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="54d8f-184">Выберите запись, которую необходимо изменить, а затем щелкните **изменить** ![ значок редактирования ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="54d8f-184">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="54d8f-185">В появившемся всплывающем меню настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="54d8f-185">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="54d8f-186">**Блокировать/Разрешить**: выберите **Разрешить** или **заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-186">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="54d8f-187">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="54d8f-187">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="54d8f-188">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и укажите срок действия для записи, используя поле **срок действия** .</span><span class="sxs-lookup"><span data-stu-id="54d8f-188">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="54d8f-189">или</span><span class="sxs-lookup"><span data-stu-id="54d8f-189">or</span></span>

     - <span data-ttu-id="54d8f-190">Переместите переключатель вправо, чтобы задать срок действия бессрочной записи:</span><span class="sxs-lookup"><span data-stu-id="54d8f-190">Move the toggle to the right to configure the entry to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="54d8f-192">.</span><span class="sxs-lookup"><span data-stu-id="54d8f-192">.</span></span>

   - <span data-ttu-id="54d8f-193">**Необязательное примечание**: введите описательный текст для записи.</span><span class="sxs-lookup"><span data-stu-id="54d8f-193">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="54d8f-194">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-194">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-195">Использование центра безопасности & соответствия требованиям для удаления записей URL и файлов из списка разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="54d8f-195">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="54d8f-196">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="54d8f-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="54d8f-197">Перейдите на вкладку " **URL-адреса** " или " **файлы** ".</span><span class="sxs-lookup"><span data-stu-id="54d8f-197">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="54d8f-198">Выберите запись, которую нужно удалить, и нажмите кнопку **Удалить** ![ значок удаления ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="54d8f-198">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="54d8f-199">В появившемся диалоговом окне предупреждения нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="54d8f-199">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-200">Настройка списка разрешений/блокировок клиентов с помощью Exchange Online PowerShell или изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="54d8f-200">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-201">Добавление URL-адресов и записей файлов в список разрешений/блокировок клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="54d8f-201">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="54d8f-202">Чтобы добавить URL-адреса и записи файлов в список разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="54d8f-202">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="54d8f-203">В этом примере добавляется запись блока URL-адреса для contoso.com и всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="54d8f-203">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="54d8f-204">Так как мы не использовали параметры ExpirationDate или параметру expiration, срок действия записи истечет через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="54d8f-204">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="54d8f-205">В этом примере показано, как добавить в файл запись разрешения для указанных файлов, срок действия которых не ограничен.</span><span class="sxs-lookup"><span data-stu-id="54d8f-205">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="54d8f-206">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="54d8f-206">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-207">Использование PowerShell для просмотра записей URL-адресов и файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="54d8f-207">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="54d8f-208">Чтобы просмотреть записи URL-адресов и файлов в списке разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="54d8f-208">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="54d8f-209">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="54d8f-209">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="54d8f-210">В этом примере возвращаются сведения о указанном хэш-значении файла.</span><span class="sxs-lookup"><span data-stu-id="54d8f-210">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="54d8f-211">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="54d8f-211">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-212">Использование PowerShell для изменения записей URL-адресов и файлов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="54d8f-212">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="54d8f-213">Невозможно изменить URL-адрес или значение файла.</span><span class="sxs-lookup"><span data-stu-id="54d8f-213">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="54d8f-214">Вместо этого необходимо удалить запись и создать ее повторно.</span><span class="sxs-lookup"><span data-stu-id="54d8f-214">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="54d8f-215">Чтобы изменить URL-адреса и записи файлов в списке разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="54d8f-215">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="54d8f-216">В этом примере изменяется дата окончания срока действия указанной записи.</span><span class="sxs-lookup"><span data-stu-id="54d8f-216">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="54d8f-217">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="54d8f-217">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-218">Удаление URL-адресов и записей файлов из списка разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="54d8f-218">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="54d8f-219">Чтобы удалить URL-адреса и записи файлов из списка разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="54d8f-219">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="54d8f-220">В этом примере из списка разрешенных и запрещенных клиентов удаляется указанная запись URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="54d8f-220">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="54d8f-221">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="54d8f-221">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="54d8f-222">Синтаксис URL-адреса для списка разрешений/блокировок клиентов</span><span class="sxs-lookup"><span data-stu-id="54d8f-222">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="54d8f-223">IP4v и IPv6-адреса разрешены, но порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="54d8f-223">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="54d8f-224">Расширения имен файлов не допускаются (например, Test. PDF).</span><span class="sxs-lookup"><span data-stu-id="54d8f-224">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="54d8f-225">Юникод не поддерживается, но Punycode — Punycode.</span><span class="sxs-lookup"><span data-stu-id="54d8f-225">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="54d8f-226">Имена узлов разрешены, если выполняются все приведенные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="54d8f-226">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="54d8f-227">Имя узла содержит точку.</span><span class="sxs-lookup"><span data-stu-id="54d8f-227">The hostname contains a period.</span></span>
  - <span data-ttu-id="54d8f-228">Слева от точки есть по крайней мере один символ.</span><span class="sxs-lookup"><span data-stu-id="54d8f-228">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="54d8f-229">Справа от точки есть по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="54d8f-229">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="54d8f-230">Например, `t.co` разрешено; `.com` или `contoso.` не разрешено.</span><span class="sxs-lookup"><span data-stu-id="54d8f-230">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="54d8f-231">Вложенные пути не являются подразумеваемыми.</span><span class="sxs-lookup"><span data-stu-id="54d8f-231">Subpaths are not implied.</span></span>

  <span data-ttu-id="54d8f-232">Например, не `contoso.com` включается `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="54d8f-232">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="54d8f-233">Подстановочные знаки (\*) разрешены в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="54d8f-233">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="54d8f-234">За левым подстановочным знаком должен следовать точка для указания поддомена.</span><span class="sxs-lookup"><span data-stu-id="54d8f-234">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="54d8f-235">Например, `*.contoso.com` разрешено; запрещено `*contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="54d8f-235">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="54d8f-236">Для указания пути должен следовать символу подстановки (/).</span><span class="sxs-lookup"><span data-stu-id="54d8f-236">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="54d8f-237">Например, `contoso.com/*` разрешено; `contoso.com*` или `contoso.com/ab*` не разрешено.</span><span class="sxs-lookup"><span data-stu-id="54d8f-237">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="54d8f-238">Все подпути не подразумеваются с помощью подстановочного знака справа.</span><span class="sxs-lookup"><span data-stu-id="54d8f-238">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="54d8f-239">Например, не `contoso.com/*` включается `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="54d8f-239">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="54d8f-240">`*.com*`недействителен (не является разрешимым доменом, а правильный подстановочный знак не следует за косой чертой).</span><span class="sxs-lookup"><span data-stu-id="54d8f-240">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="54d8f-241">Подстановочные знаки не разрешены в IP-адресах.</span><span class="sxs-lookup"><span data-stu-id="54d8f-241">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="54d8f-242">Символ тильды (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="54d8f-242">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="54d8f-243">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="54d8f-243">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="54d8f-244">Например `~contoso.com` , включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="54d8f-244">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="54d8f-245">URL-адреса, содержащие протоколы (например,, `http://` `https://` или `ftp://` ), завершатся неуспешно, так как записи URL-адресов применяются ко всем протоколам.</span><span class="sxs-lookup"><span data-stu-id="54d8f-245">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="54d8f-246">Имя пользователя или пароль не поддерживаются или не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="54d8f-246">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="54d8f-247">Кавычки (' или ") являются недопустимыми символами.</span><span class="sxs-lookup"><span data-stu-id="54d8f-247">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="54d8f-248">URL-адрес должен включать все перенаправления, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="54d8f-248">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="54d8f-249">Сценарии ввода URL-адресов</span><span class="sxs-lookup"><span data-stu-id="54d8f-249">URL entry scenarios</span></span>

<span data-ttu-id="54d8f-250">Допустимые записи URL-адреса и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="54d8f-250">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="54d8f-251">Сценарий: без подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="54d8f-251">Scenario: No wildcards</span></span>

<span data-ttu-id="54d8f-252">**Запись**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="54d8f-252">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="54d8f-253">**Разрешить согласование**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-253">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="54d8f-254">**Разрешить не сопоставляемые**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-254">**Allow not matched**:</span></span>

  - <span data-ttu-id="54d8f-255">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-255">abc-contoso.com</span></span>
  - <span data-ttu-id="54d8f-256">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="54d8f-256">contoso.com/a</span></span>
  - <span data-ttu-id="54d8f-257">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-257">payroll.contoso.com</span></span>
  - <span data-ttu-id="54d8f-258">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-258">test.com/contoso.com</span></span>
  - <span data-ttu-id="54d8f-259">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-259">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="54d8f-260">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-260">www.contoso.com</span></span>
  - <span data-ttu-id="54d8f-261">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="54d8f-261">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="54d8f-262">**Согласование блока**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-262">**Block match**:</span></span>

  - <span data-ttu-id="54d8f-263">contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-263">contoso.com</span></span>
  - <span data-ttu-id="54d8f-264">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="54d8f-264">contoso.com/a</span></span>
  - <span data-ttu-id="54d8f-265">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-265">payroll.contoso.com</span></span>
  - <span data-ttu-id="54d8f-266">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-266">test.com/contoso.com</span></span>
  - <span data-ttu-id="54d8f-267">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-267">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="54d8f-268">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-268">www.contoso.com</span></span>
  - <span data-ttu-id="54d8f-269">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="54d8f-269">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="54d8f-270">**Блок не сопоставлен**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-270">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="54d8f-271">Сценарий: левый подстановочный знак (поддомен)</span><span class="sxs-lookup"><span data-stu-id="54d8f-271">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="54d8f-272">**Запись**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="54d8f-272">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="54d8f-273">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-273">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="54d8f-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-274">www.contoso.com</span></span>
  - <span data-ttu-id="54d8f-275">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-275">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="54d8f-276">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-276">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="54d8f-277">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-277">123contoso.com</span></span>
  - <span data-ttu-id="54d8f-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-278">contoso.com</span></span>
  - <span data-ttu-id="54d8f-279">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-279">test.com/contoso.com</span></span>
  - <span data-ttu-id="54d8f-280">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="54d8f-280">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="54d8f-281">Сценарий: подстановочный знак "справа" в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="54d8f-281">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="54d8f-282">**Запись**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="54d8f-282">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="54d8f-283">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-283">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="54d8f-284">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="54d8f-284">contoso.com/a/b</span></span>
  - <span data-ttu-id="54d8f-285">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="54d8f-285">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="54d8f-286">Contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="54d8f-286">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="54d8f-287">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-287">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="54d8f-288">contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-288">contoso.com</span></span>
  - <span data-ttu-id="54d8f-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="54d8f-289">contoso.com/a</span></span>
  - <span data-ttu-id="54d8f-290">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-290">www.contoso.com</span></span>
  - <span data-ttu-id="54d8f-291">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="54d8f-291">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="54d8f-292">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="54d8f-292">Scenario: Left tilde</span></span>

<span data-ttu-id="54d8f-293">**Запись**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="54d8f-293">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="54d8f-294">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-294">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="54d8f-295">contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-295">contoso.com</span></span>
  - <span data-ttu-id="54d8f-296">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-296">www.contoso.com</span></span>
  - <span data-ttu-id="54d8f-297">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-297">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="54d8f-298">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-298">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="54d8f-299">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-299">123contoso.com</span></span>
  - <span data-ttu-id="54d8f-300">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="54d8f-300">contoso.com/abc</span></span>
  - <span data-ttu-id="54d8f-301">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="54d8f-301">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="54d8f-302">Сценарий: правый подстановочный суффикс</span><span class="sxs-lookup"><span data-stu-id="54d8f-302">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="54d8f-303">**Запись**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="54d8f-303">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="54d8f-304">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-304">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="54d8f-305">Contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="54d8f-305">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="54d8f-306">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="54d8f-306">contoso.com/a</span></span>
  - <span data-ttu-id="54d8f-307">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="54d8f-307">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="54d8f-308">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="54d8f-308">contoso.com/ab</span></span>
  - <span data-ttu-id="54d8f-309">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="54d8f-309">contoso.com/b</span></span>
  - <span data-ttu-id="54d8f-310">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="54d8f-310">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="54d8f-311">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="54d8f-311">contoso.com/ba</span></span>

- <span data-ttu-id="54d8f-312">**Разрешить не сопоставляемые** и непарные **блоки**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-312">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="54d8f-313">Сценарий: левый и правый суффиксы для поддоменов подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="54d8f-313">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="54d8f-314">**Запись**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="54d8f-314">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="54d8f-315">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-315">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="54d8f-316">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="54d8f-316">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="54d8f-317">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="54d8f-317">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="54d8f-318">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="54d8f-318">www.contoso.com/a</span></span>
  - <span data-ttu-id="54d8f-319">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="54d8f-319">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="54d8f-320">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="54d8f-320">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="54d8f-321">**Разрешить не сопоставляемые** и непарные **блоки**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="54d8f-321">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="54d8f-322">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="54d8f-322">Scenario: Left and right tilde</span></span>

<span data-ttu-id="54d8f-323">**Запись**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="54d8f-323">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="54d8f-324">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="54d8f-325">contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-325">contoso.com</span></span>
  - <span data-ttu-id="54d8f-326">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="54d8f-326">contoso.com/a</span></span>
  - <span data-ttu-id="54d8f-327">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-327">www.contoso.com</span></span>
  - <span data-ttu-id="54d8f-328">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="54d8f-328">www.contoso.com/b</span></span>
  - <span data-ttu-id="54d8f-329">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-329">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="54d8f-330">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-330">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="54d8f-331">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-331">123contoso.com</span></span>
  - <span data-ttu-id="54d8f-332">contoso.org</span><span class="sxs-lookup"><span data-stu-id="54d8f-332">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="54d8f-333">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="54d8f-333">Scenario: IP address</span></span>

<span data-ttu-id="54d8f-334">**Запись**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="54d8f-334">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="54d8f-335">**Разрешить ПОИСКПОЗ** и **блокировать ПОИСКПОЗ**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="54d8f-335">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="54d8f-336">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-336">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="54d8f-337">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="54d8f-337">1.2.3.4/a</span></span>
  - <span data-ttu-id="54d8f-338">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="54d8f-338">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="54d8f-339">IP-адрес с подстановкой по правому краю</span><span class="sxs-lookup"><span data-stu-id="54d8f-339">IP address with right wildcard</span></span>

<span data-ttu-id="54d8f-340">**Запись**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="54d8f-340">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="54d8f-341">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-341">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="54d8f-342">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="54d8f-342">1.2.3.4/b</span></span>
  - <span data-ttu-id="54d8f-343">1.2.3.4/баааа</span><span class="sxs-lookup"><span data-stu-id="54d8f-343">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="54d8f-344">Примеры недопустимых записей</span><span class="sxs-lookup"><span data-stu-id="54d8f-344">Examples of invalid entries</span></span>

<span data-ttu-id="54d8f-345">Следующие записи недопустимы:</span><span class="sxs-lookup"><span data-stu-id="54d8f-345">The following entries are invalid:</span></span>

- <span data-ttu-id="54d8f-346">**Отсутствующие или недопустимые значения домена**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-346">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="54d8f-347">компанией</span><span class="sxs-lookup"><span data-stu-id="54d8f-347">contoso</span></span>
  - <span data-ttu-id="54d8f-348">\*компанией.\*</span><span class="sxs-lookup"><span data-stu-id="54d8f-348">\*.contoso.\*</span></span>
  - <span data-ttu-id="54d8f-349">\*. com</span><span class="sxs-lookup"><span data-stu-id="54d8f-349">\*.com</span></span>
  - <span data-ttu-id="54d8f-350">\*PDF</span><span class="sxs-lookup"><span data-stu-id="54d8f-350">\*.pdf</span></span>

- <span data-ttu-id="54d8f-351">**Подстановочный знак для текста или без пробелов**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-351">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="54d8f-352">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-352">\*contoso.com</span></span>
  - <span data-ttu-id="54d8f-353">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="54d8f-353">contoso.com\*</span></span>
  - <span data-ttu-id="54d8f-354">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="54d8f-354">\*1.2.3.4</span></span>
  - <span data-ttu-id="54d8f-355">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="54d8f-355">1.2.3.4\*</span></span>
  - <span data-ttu-id="54d8f-356">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="54d8f-356">contoso.com/a\*</span></span>
  - <span data-ttu-id="54d8f-357">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="54d8f-357">contoso.com/ab\*</span></span>

- <span data-ttu-id="54d8f-358">**IP-адреса с портами**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-358">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="54d8f-359">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="54d8f-359">contoso.com:443</span></span>
  - <span data-ttu-id="54d8f-360">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="54d8f-360">abc.contoso.com:25</span></span>

- <span data-ttu-id="54d8f-361">**Подстановочные знаки, не являющиеся описательными**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-361">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="54d8f-362">\*.\*</span><span class="sxs-lookup"><span data-stu-id="54d8f-362">\*.\*</span></span>

- <span data-ttu-id="54d8f-363">**Посрединные подстановочные знаки**:</span><span class="sxs-lookup"><span data-stu-id="54d8f-363">**Middle wildcards**:</span></span>

  - <span data-ttu-id="54d8f-364">Конто \* so.com</span><span class="sxs-lookup"><span data-stu-id="54d8f-364">conto\*so.com</span></span>
  - <span data-ttu-id="54d8f-365">Конто ~ so. com</span><span class="sxs-lookup"><span data-stu-id="54d8f-365">conto~so.com</span></span>

- <span data-ttu-id="54d8f-366">**Знаки подстановки двойной замены**</span><span class="sxs-lookup"><span data-stu-id="54d8f-366">**Double wildcards**</span></span>

  - <span data-ttu-id="54d8f-367">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="54d8f-367">contoso.com/\*\*</span></span>
  - <span data-ttu-id="54d8f-368">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="54d8f-368">contoso.com/\*/\*</span></span>
