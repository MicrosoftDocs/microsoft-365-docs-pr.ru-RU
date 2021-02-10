---
title: Восстановление после атаки программы-шантажиста
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы Microsoft 365 могут узнать, как восстановиться после атаки программы-вымогателя.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b834adb3d9ba5f85984e09b4bb1e4b48673c32f2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166907"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="c91e6-103">Восстановление после атаки программы-вымогателя в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c91e6-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c91e6-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="c91e6-104">**Applies to**</span></span>
- [<span data-ttu-id="c91e6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c91e6-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="c91e6-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="c91e6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c91e6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c91e6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c91e6-108">Даже если вы принимаете все меры предосторожности для защиты своей организации, вы все равно можете стать жертвой атаки [программы-вымогателя.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="c91e6-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="c91e6-109">Программы-выкупы — это большой бизнес, и атаки очень сложные.</span><span class="sxs-lookup"><span data-stu-id="c91e6-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="c91e6-110">Действия, которые необходимо предпринять в этой статье, дают вам наилучшие возможности для восстановления данных и остановки внутреннего распространения заражения.</span><span class="sxs-lookup"><span data-stu-id="c91e6-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="c91e6-111">Прежде чем приступать к его созданию, учтите следующие факторы:</span><span class="sxs-lookup"><span data-stu-id="c91e6-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="c91e6-112">Не гарантируется, что выплата выкупа возвратит доступ к вашим файлам.</span><span class="sxs-lookup"><span data-stu-id="c91e6-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="c91e6-113">На самом деле, оплата выкупа может сделать вас целью для дополнительных программ-вымогателей.</span><span class="sxs-lookup"><span data-stu-id="c91e6-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="c91e6-114">Если вы уже оплатили операцию, но не воспользовались решением злоумышленника, обратитесь в банк, чтобы узнать, могут ли они заблокировать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="c91e6-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="c91e6-115">Мы также рекомендуем сообщить о атаке программы-вымогателя правоохранительным органам, веб-сайтам отчетов о схимах и Корпорации Майкрософт, как описано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c91e6-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="c91e6-116">Важно быстро реагировать на атаку и ее последствия.</span><span class="sxs-lookup"><span data-stu-id="c91e6-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="c91e6-117">Чем дольше вы будете ждать, тем меньше вероятность того, что вы сможете восстановить затронутые данные.</span><span class="sxs-lookup"><span data-stu-id="c91e6-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="c91e6-118">Шаг 1. Проверка резервных копий</span><span class="sxs-lookup"><span data-stu-id="c91e6-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="c91e6-119">Если у вас есть автономные резервные копии,  возможно, вы сможете восстановить зашифрованные данные после удаления полезной нагрузки программы-вымогателя (вредоносных программ) из среды.</span><span class="sxs-lookup"><span data-stu-id="c91e6-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="c91e6-120">Если у вас нет резервных копий или резервные копии также были затронуты программами-вымогателями, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="c91e6-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="c91e6-121">Шаг 2. Отключение синхронизации Exchange ActiveSync и OneDrive</span><span class="sxs-lookup"><span data-stu-id="c91e6-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="c91e6-122">Ключевой момент здесь — остановить распространение шифрования данных программами-вымогателями.</span><span class="sxs-lookup"><span data-stu-id="c91e6-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="c91e6-123">Если вы подозреваете, что электронная почта является целью шифрования программ-вымогателей, временно отключайте доступ пользователей к почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="c91e6-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="c91e6-124">Exchange ActiveSync синхронизирует данные между устройствами и почтовыми ящиками Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c91e6-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="c91e6-125">Чтобы отключить Exchange ActiveSync для почтового ящика, см. Exchange ActiveSync [для пользователей в Exchange Online.](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="c91e6-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="c91e6-126">Чтобы отключить доступ к почтовому ящику других типов, см. в:</span><span class="sxs-lookup"><span data-stu-id="c91e6-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="c91e6-127">[Включить или отключить MAPI для почтового ящика.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="c91e6-127">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="c91e6-128">Включить или отключить доступ по pop3 или IMAP4 для пользователя</span><span class="sxs-lookup"><span data-stu-id="c91e6-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="c91e6-129">Приочная синхронизация OneDrive поможет защитить облачные данные от обновления с помощью потенциально зараженных устройств.</span><span class="sxs-lookup"><span data-stu-id="c91e6-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="c91e6-130">Дополнительные сведения см. в сведениях о [приостановки и возобновлении синхронизации в OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="c91e6-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="c91e6-131">Шаг 3. Удаление вредоносной программы с затронутых устройств</span><span class="sxs-lookup"><span data-stu-id="c91e6-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="c91e6-132">Запустите полную и текущую антивирусную проверку на всех подозрительных компьютерах и устройствах, чтобы обнаружить и удалить полезное оборудование, связанное с программой-вымогателями.</span><span class="sxs-lookup"><span data-stu-id="c91e6-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="c91e6-133">Не забудьте сканировать устройства, которые синхронизируют данные, или целевые объекты сетевых дисков.</span><span class="sxs-lookup"><span data-stu-id="c91e6-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="c91e6-134">Вы можете [использовать](https://www.microsoft.com/windows/comprehensive-security) Защитник Windows или (для старых клиентов) [Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)</span><span class="sxs-lookup"><span data-stu-id="c91e6-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="c91e6-135">Альтернативным средством удаления вредоносных программ (MSRT) является средство удаления вредоносных программ [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="c91e6-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="c91e6-136">Если эти параметры не работают, [](https://support.microsoft.com/help/17466) вы можете попробовать Защитник Windows автономном режиме или устранить проблемы с обнаружением и удалением [вредоносных программ.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="c91e6-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="c91e6-137">Шаг 4. Восстановление файлов на очищенных компьютерах или устройствах</span><span class="sxs-lookup"><span data-stu-id="c91e6-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="c91e6-138">После завершения предыдущего шага для удаления полезной нагрузки программы-вымогателя из среды (которая не позволит [](https://support.microsoft.com/help/17128) программам-вымогателям шифровать или удалять файлы), вы можете использовать историю файлов в Windows 10 и Windows 8.1 или System Protection в Windows 7, чтобы попытаться восстановить локальные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="c91e6-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="c91e6-139">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="c91e6-139">**Notes**:</span></span>

- <span data-ttu-id="c91e6-140">Некоторые программы-вымодеры также шифруют или удаляют резервные версии, поэтому для восстановления файлов нельзя использовать функцию "История файлов" или "Защита системы".</span><span class="sxs-lookup"><span data-stu-id="c91e6-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="c91e6-141">В этом случае необходимо использовать резервные копии на внешних дисках или устройствах, которые не были затронуты программами-вымогателями или OneDrive, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="c91e6-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="c91e6-142">Если папка синхронизируется с OneDrive и вы не используете последнюю версию Windows, с помощью истории файлов могут быть некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="c91e6-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="c91e6-143">Шаг 5. Восстановление файлов в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c91e6-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="c91e6-144">Восстановление файлов в OneDrive для бизнеса позволяет восстановить все хранилище OneDrive до предыдущего момента в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c91e6-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="c91e6-145">Дополнительные сведения см. в [теме "Восстановление OneDrive".](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="c91e6-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="c91e6-146">Шаг 6. Восстановление удаленной электронной почты</span><span class="sxs-lookup"><span data-stu-id="c91e6-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="c91e6-147">В редких случаях, когда программа-вымогаатель удалила всю электронную почту, вы, вероятно, сможете восстановить удаленные элементы.</span><span class="sxs-lookup"><span data-stu-id="c91e6-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="c91e6-148">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="c91e6-148">For more information, see:</span></span>

- [<span data-ttu-id="c91e6-149">Восстановление удаленных сообщений в почтовом ящике пользователя</span><span class="sxs-lookup"><span data-stu-id="c91e6-149">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="c91e6-150">Восстановление удаленных элементов в Outlook для Windows</span><span class="sxs-lookup"><span data-stu-id="c91e6-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="c91e6-151">Шаг 7. Повторное Exchange ActiveSync синхронизации OneDrive</span><span class="sxs-lookup"><span data-stu-id="c91e6-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="c91e6-152">После очистки компьютеров и устройств и восстановления данных вы можете повторно включить синхронизацию Exchange ActiveSync и OneDrive, ранее отключенную на шаге [2.](#step-2-disable-exchange-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="c91e6-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="c91e6-153">Шаг 8 (необязательно). Блокировка синхронизации OneDrive для определенных расширений файлов</span><span class="sxs-lookup"><span data-stu-id="c91e6-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="c91e6-154">После восстановления вы можете запретить клиентам OneDrive для бизнеса синхронизировать типы файлов, затронутые программой-выкупом.</span><span class="sxs-lookup"><span data-stu-id="c91e6-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="c91e6-155">Дополнительные сведения см. в подстройки [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="c91e6-155">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="c91e6-156">Сообщение о атаке</span><span class="sxs-lookup"><span data-stu-id="c91e6-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="c91e6-157">Обратитесь в правоохранительные органы</span><span class="sxs-lookup"><span data-stu-id="c91e6-157">Contact law enforcement</span></span>

<span data-ttu-id="c91e6-158">Обратитесь в местные или федеральные правоохранительные органы.</span><span class="sxs-lookup"><span data-stu-id="c91e6-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="c91e6-159">Например, если вы находитесь в США, [](https://www.fbi.gov/contact-us/field)вы можете связаться с локальным офисом ВЕОИБ, [IC3](http://www.ic3.gov/complaint/default.aspx) или службой [секретов.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="c91e6-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="c91e6-160">Отправка отчета на веб-сайт отчетов об афере в вашей стране</span><span class="sxs-lookup"><span data-stu-id="c91e6-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="c91e6-161">На веб-сайтах отчетов о мошенничествох можно найти сведения о том, как предотвращать и избегать мошенничества.</span><span class="sxs-lookup"><span data-stu-id="c91e6-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="c91e6-162">Они также предоставляют механизмы для отчетов о том, что вы стали жертвой аферы.</span><span class="sxs-lookup"><span data-stu-id="c91e6-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="c91e6-163">Австралия: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="c91e6-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="c91e6-164">Канада: [Канадский центр по борьбе с мошенничеством](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="c91e6-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="c91e6-165">Франция: [agence nationale de la sécurité des systémes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="c91e6-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="c91e6-166">Германия: [Сичерхейт в der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="c91e6-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="c91e6-167">Ирландия: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="c91e6-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="c91e6-168">Новая Зеландия: [мошенничество с потребительскими вопросами](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="c91e6-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="c91e6-169">Соединенное Королевство: [мошенничество с действиями](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="c91e6-169">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="c91e6-170">США: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="c91e6-170">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="c91e6-171">Если ваша страна не указана в списке, попросите местные или федеральные правоохранительные органы.</span><span class="sxs-lookup"><span data-stu-id="c91e6-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="c91e6-172">Отправка сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c91e6-172">Submit email messages to Microsoft</span></span>

<span data-ttu-id="c91e6-173">Вы можете сообщить о фишинговых сообщениях, содержащих программы-вымогателя, одним из нескольких методов.</span><span class="sxs-lookup"><span data-stu-id="c91e6-173">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="c91e6-174">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c91e6-174">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c91e6-175">См. также</span><span class="sxs-lookup"><span data-stu-id="c91e6-175">See also</span></span>

- [<span data-ttu-id="c91e6-176">Программы-программы-вымогателя</span><span class="sxs-lookup"><span data-stu-id="c91e6-176">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="c91e6-177">Ответ программы-вымогателя — оплата или невыплата?</span><span class="sxs-lookup"><span data-stu-id="c91e6-177">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="c91e6-178">Norsk Вайс реагирует на атаки программы-вымогателя с прозрачностью</span><span class="sxs-lookup"><span data-stu-id="c91e6-178">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="c91e6-179">Обнаружение программ-вымогателей и восстановление файлов в OneDrive</span><span class="sxs-lookup"><span data-stu-id="c91e6-179">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="c91e6-180">Отчет по аналитике безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c91e6-180">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="c91e6-181">Включить или отключить макрос в файлах Office</span><span class="sxs-lookup"><span data-stu-id="c91e6-181">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="c91e6-182">Рекомендуемые параметры для EOP и Microsoft Defender для безопасности Office 365</span><span class="sxs-lookup"><span data-stu-id="c91e6-182">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="c91e6-183">Надежное обновление: безопасность следующего поколения в Windows 10 подтверждает устойчивость к вспышкам программ-вымогателей в 2017 г.</span><span class="sxs-lookup"><span data-stu-id="c91e6-183">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="c91e6-184">Нет мас, Samas: что в модусе операди этого программы-вымогателя?</span><span class="sxs-lookup"><span data-stu-id="c91e6-184">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="c91e6-185">Блокировка вредоносных программ, чтобы избежать ее</span><span class="sxs-lookup"><span data-stu-id="c91e6-185">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="c91e6-186">MSRT июль 2016 г.: программа-программа-вымогаатель Cerber</span><span class="sxs-lookup"><span data-stu-id="c91e6-186">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="c91e6-187">Три заголовок программы-вымогателя Cerber, похожей на Cerber</span><span class="sxs-lookup"><span data-stu-id="c91e6-187">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="c91e6-188">Программа-программа-программа-вымогателя, на которые влияет код daАА</span><span class="sxs-lookup"><span data-stu-id="c91e6-188">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
