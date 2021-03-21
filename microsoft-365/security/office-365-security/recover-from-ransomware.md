---
title: Восстановление после атаки программы-шантажиста
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы Microsoft 365 могут узнать, как восстановиться после атаки вымогателей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21a6dc4cca2aac189740f2dba4ed10dc865792a6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922900"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="c98f8-103">Восстановление после атаки вымогателей в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c98f8-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c98f8-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="c98f8-104">**Applies to**</span></span>
- [<span data-ttu-id="c98f8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c98f8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c98f8-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="c98f8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c98f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c98f8-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c98f8-108">Даже если вы принимаете все меры предосторожности для защиты организации, вы все равно можете стать жертвой атаки [вымогателей.](/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="c98f8-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="c98f8-109">Вымогателей это большой бизнес, и атаки очень сложные.</span><span class="sxs-lookup"><span data-stu-id="c98f8-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="c98f8-110">Действия в этой статье дают вам наилучшие возможности для восстановления данных и остановки внутреннего распространения инфекции.</span><span class="sxs-lookup"><span data-stu-id="c98f8-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="c98f8-111">Прежде чем приступать к его созданию, учтите следующие факторы:</span><span class="sxs-lookup"><span data-stu-id="c98f8-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="c98f8-112">Нет никакой гарантии, что оплата выкупа возвращает доступ к вашим файлам.</span><span class="sxs-lookup"><span data-stu-id="c98f8-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="c98f8-113">На самом деле, оплата выкупа может сделать вас мишенью для более вымогателей.</span><span class="sxs-lookup"><span data-stu-id="c98f8-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="c98f8-114">Если вы уже заплатили, но вы вернулись без использования решения злоумышленника, обратитесь в банк, чтобы узнать, могут ли они заблокировать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="c98f8-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="c98f8-115">Мы также рекомендуем сообщать об атаке вымогателей в правоохранительные органы, веб-сайты отчетов о мошенничестве и Microsoft, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c98f8-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="c98f8-116">Важно быстро реагировать на атаку и ее последствия.</span><span class="sxs-lookup"><span data-stu-id="c98f8-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="c98f8-117">Чем дольше вы будете ждать, тем меньше вероятность восстановления затронутых данных.</span><span class="sxs-lookup"><span data-stu-id="c98f8-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="c98f8-118">Шаг 1. Проверка резервных копий</span><span class="sxs-lookup"><span data-stu-id="c98f8-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="c98f8-119">Если у вас есть автономные резервные копии,  вы, вероятно, сможете восстановить зашифрованные данные после удаления полезной нагрузки вымогателей (вредоносных программ) из среды.</span><span class="sxs-lookup"><span data-stu-id="c98f8-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="c98f8-120">Если у вас нет резервных копий или резервные копии также пострадали от программ-вымогателей, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="c98f8-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="c98f8-121">Шаг 2. Отключение синхронизации Exchange ActiveSync и OneDrive</span><span class="sxs-lookup"><span data-stu-id="c98f8-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="c98f8-122">Ключевой момент здесь — остановить распространение шифрования данных программ-вымогателей.</span><span class="sxs-lookup"><span data-stu-id="c98f8-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="c98f8-123">Если вы подозреваете, что электронная почта является объектом шифрования программ-вымогателей, временно отключайте доступ пользователей к почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="c98f8-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="c98f8-124">Exchange ActiveSync синхронизирует данные между устройствами и почтовыми ящиками Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c98f8-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="c98f8-125">Чтобы отключить Exchange ActiveSync для почтового ящика, см. в Exchange ActiveSync для пользователей [в Exchange Online.](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="c98f8-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="c98f8-126">Чтобы отключить другие типы доступа к почтовому ящику, см.:</span><span class="sxs-lookup"><span data-stu-id="c98f8-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="c98f8-127">[Включить или отключить MAPI для почтового ящика.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="c98f8-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="c98f8-128">Включить или отключить доступ к POP3 или IMAP4 для пользователя</span><span class="sxs-lookup"><span data-stu-id="c98f8-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="c98f8-129">Приочная синхронизация OneDrive поможет защитить облачные данные от обновления потенциально зараженными устройствами.</span><span class="sxs-lookup"><span data-stu-id="c98f8-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="c98f8-130">Дополнительные сведения см. в [сайте How to Pause and Resume sync in OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="c98f8-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="c98f8-131">Шаг 3. Удаление вредоносных программ с затронутых устройств</span><span class="sxs-lookup"><span data-stu-id="c98f8-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="c98f8-132">Запустите полное текущее антивирусное сканирование на всех подозрительных компьютерах и устройствах для обнаружения и удаления полезной нагрузки, связанной с программой-вымогателями.</span><span class="sxs-lookup"><span data-stu-id="c98f8-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="c98f8-133">Не забывайте проверять устройства, которые синхронизируют данные, или целевые объекты сетевых дисков.</span><span class="sxs-lookup"><span data-stu-id="c98f8-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="c98f8-134">Вы можете использовать [Защитник Windows](https://www.microsoft.com/windows/comprehensive-security) или (для более старых клиентов) [Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)</span><span class="sxs-lookup"><span data-stu-id="c98f8-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="c98f8-135">Альтернативой, которая также поможет удалить программы-вымогателей или вредоносные программы, является средство удаления вредоносного программного обеспечения [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="c98f8-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="c98f8-136">Если эти параметры не работают, [](https://support.microsoft.com/help/17466) вы можете попробовать Защитник Windows в автономном режиме или устранение неполадок с обнаружением и [удалением вредоносных программ.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="c98f8-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="c98f8-137">Шаг 4. Восстановление файлов на очищенных компьютерах или устройстве</span><span class="sxs-lookup"><span data-stu-id="c98f8-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="c98f8-138">После завершения предыдущего шага по удалению полезной нагрузки вымогателей из среды (что не позволит вымогателям шифровать или удалить файлы), вы можете использовать историю файлов в Windows 10 и Windows 8.1 или System Protection в Windows 7, чтобы попытаться восстановить локальные файлы и папки. [](https://support.microsoft.com/help/17128)</span><span class="sxs-lookup"><span data-stu-id="c98f8-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="c98f8-139">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="c98f8-139">**Notes**:</span></span>

- <span data-ttu-id="c98f8-140">Некоторые программы-вымогательы также шифруют или удаляют резервные версии, поэтому для восстановления файлов нельзя использовать историю файлов или систему защиты.</span><span class="sxs-lookup"><span data-stu-id="c98f8-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="c98f8-141">В этом случае необходимо использовать резервные копии на внешних дисках или устройствах, не затронутых программой-вымогателями или OneDrive, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="c98f8-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="c98f8-142">Если папка синхронизирована с OneDrive и вы не используете последнюю версию Windows, могут возникнуть некоторые ограничения с помощью истории файлов.</span><span class="sxs-lookup"><span data-stu-id="c98f8-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="c98f8-143">Шаг 5. Восстановление файлов в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c98f8-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="c98f8-144">Восстановление файлов в OneDrive для бизнеса позволяет восстановить весь OneDrive до предыдущей точки времени в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c98f8-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="c98f8-145">Дополнительные сведения см. в [сайте Восстановление OneDrive.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="c98f8-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="c98f8-146">Шаг 6. Восстановление удаленной электронной почты</span><span class="sxs-lookup"><span data-stu-id="c98f8-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="c98f8-147">В редких случаях, когда вымогателей удалили все сообщения электронной почты, вы, вероятно, сможете восстановить удаленные элементы.</span><span class="sxs-lookup"><span data-stu-id="c98f8-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="c98f8-148">Дополнительные сведения см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="c98f8-148">For more information, see:</span></span>

- [<span data-ttu-id="c98f8-149">Восстановление удаленных сообщений в почтовом ящике пользователя</span><span class="sxs-lookup"><span data-stu-id="c98f8-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="c98f8-150">Восстановление удаленных элементов в Outlook для Windows</span><span class="sxs-lookup"><span data-stu-id="c98f8-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="c98f8-151">Шаг 7. Повторное Exchange ActiveSync и синхронизация OneDrive</span><span class="sxs-lookup"><span data-stu-id="c98f8-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="c98f8-152">После очистки компьютеров и устройств и восстановления данных можно повторно включить синхронизацию Exchange ActiveSync OneDrive, отключенную ранее в шаге [2.](#step-2-disable-exchange-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="c98f8-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="c98f8-153">Шаг 8 (необязательный): блокировка синхронизации OneDrive для определенных расширений файлов</span><span class="sxs-lookup"><span data-stu-id="c98f8-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="c98f8-154">После восстановления можно запретить клиентам OneDrive для бизнеса синхронизировать типы файлов, затронутые этим программой-вымогателем.</span><span class="sxs-lookup"><span data-stu-id="c98f8-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="c98f8-155">Дополнительные сведения см. [в рубрезе Set-SPOTenantSyncClientRestriction.](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="c98f8-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="c98f8-156">Сообщение об атаке</span><span class="sxs-lookup"><span data-stu-id="c98f8-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="c98f8-157">Обратитесь в правоохранительные органы</span><span class="sxs-lookup"><span data-stu-id="c98f8-157">Contact law enforcement</span></span>

<span data-ttu-id="c98f8-158">Обратитесь в местные или федеральные правоохранительные органы.</span><span class="sxs-lookup"><span data-stu-id="c98f8-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="c98f8-159">Например, если вы находитесь в США, вы можете обратиться в местное полевой офис [ФБР,](https://www.fbi.gov/contact-us/field) [IC3 или](http://www.ic3.gov/complaint/default.aspx) [секретную службу.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="c98f8-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="c98f8-160">Отправка отчета на веб-сайт отчетности о мошенничестве в вашей стране</span><span class="sxs-lookup"><span data-stu-id="c98f8-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="c98f8-161">Веб-сайты отчетов о мошенничестве предоставляют сведения о том, как предотвратить и избежать мошенничества.</span><span class="sxs-lookup"><span data-stu-id="c98f8-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="c98f8-162">Они также предоставляют механизмы для отчета, если вы стали жертвой мошенников.</span><span class="sxs-lookup"><span data-stu-id="c98f8-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="c98f8-163">Австралия: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="c98f8-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="c98f8-164">Канада: [Канадский центр по борьбе с мошенничеством](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="c98f8-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="c98f8-165">Франция: [Agence Nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="c98f8-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="c98f8-166">Германия: [Bundesamt für Sicherheit в der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="c98f8-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="c98f8-167">Ирландия: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="c98f8-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="c98f8-168">Новая Зеландия: [мошенничество с потребительскими делами](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="c98f8-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="c98f8-169">Великобритания: [мошенничество с действиями](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="c98f8-169">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="c98f8-170">СОЕДИНЕННЫЕ Штаты: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="c98f8-170">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="c98f8-171">Если ваша страна не указана, попросите местные или федеральные правоохранительные органы.</span><span class="sxs-lookup"><span data-stu-id="c98f8-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="c98f8-172">Отправка сообщений электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c98f8-172">Submit email messages to Microsoft</span></span>

<span data-ttu-id="c98f8-173">Вы можете сообщать о фишинговых сообщениях, содержащих вымогателей, с помощью одного из нескольких методов.</span><span class="sxs-lookup"><span data-stu-id="c98f8-173">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="c98f8-174">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c98f8-174">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c98f8-175">См. также</span><span class="sxs-lookup"><span data-stu-id="c98f8-175">See also</span></span>

- [<span data-ttu-id="c98f8-176">Вымогателей</span><span class="sxs-lookup"><span data-stu-id="c98f8-176">Ransomware</span></span>](/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="c98f8-177">Ответ вымогателей — платить или не платить?</span><span class="sxs-lookup"><span data-stu-id="c98f8-177">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="c98f8-178">Norsk Hydro реагирует на атаки вымогателей с прозрачностью</span><span class="sxs-lookup"><span data-stu-id="c98f8-178">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="c98f8-179">Обнаружение и восстановление файлов в OneDrive</span><span class="sxs-lookup"><span data-stu-id="c98f8-179">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="c98f8-180">Отчет об аналитике безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c98f8-180">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="c98f8-181">Включить или отключить макрос в файлах Office</span><span class="sxs-lookup"><span data-stu-id="c98f8-181">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="c98f8-182">Рекомендуемые параметры безопасности EOP и Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="c98f8-182">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="c98f8-183">Достойное обновление: безопасность следующего поколения в Windows 10 доказала устойчивость к вспышкам вымогателей в 2017 г.</span><span class="sxs-lookup"><span data-stu-id="c98f8-183">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="c98f8-184">Нет мас, Samas: Что в modus operandi этого вымогателя?</span><span class="sxs-lookup"><span data-stu-id="c98f8-184">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="c98f8-185">Locky malware, lucky to avoid it</span><span class="sxs-lookup"><span data-stu-id="c98f8-185">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="c98f8-186">MSRT July 2016: Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="c98f8-186">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="c98f8-187">Три главы вируса-вымогателя Cerber, похожего на Cerber</span><span class="sxs-lookup"><span data-stu-id="c98f8-187">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="c98f8-188">Troldesh ransomware influenced by the () Da Vinci code</span><span class="sxs-lookup"><span data-stu-id="c98f8-188">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)