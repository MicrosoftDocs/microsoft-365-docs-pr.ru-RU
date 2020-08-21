---
title: Восстановление после атаки программы-шантажиста
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы Microsoft 365 могут узнать, как восстановить систему защиты от атак программ-шумостей.
ms.openlocfilehash: 2f8e5f5deb18cadfaea7acc1cffe73abbc43010b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827837"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="0bc4d-103">Восстановление после атаки программ-шумо-служб в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0bc4d-103">Recover from a ransomware attack in Microsoft 365</span></span>

<span data-ttu-id="0bc4d-104">Даже в случае мероприятиях по защите организации вы можете отказаться от жертвов к атаке [программ-шумостей.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="0bc4d-105">Программа-шантажист является большим масштабным бизнес-процессом, и они проверяются на избыточном уровне.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="0bc4d-106">В этом разделе представлена лучшая возможность восстановления данных, зашифрованных выкупом для пользователей, и прекратит расстановку заражения в организации.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your organization.</span></span> <span data-ttu-id="0bc4d-107">Прежде чем приступать к его созданию, учтите следующие факторы:</span><span class="sxs-lookup"><span data-stu-id="0bc4d-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="0bc4d-108">Не гарантируется, что выплата выкуп за выкуп не даст вам доступа к вашим файлам.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="0bc4d-109">На самом деле платеж за выкуп за выкуп может принудить к вам более широкую техническую поддержку.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="0bc4d-110">Если вы уже оплачили, но вы успешно сможете восстановить файлы без использования их разрешения злоумышленника, следует вызвать банк, чтобы узнать, могут ли они блокировать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="0bc4d-111">Мы также рекомендуем сообщать об атаке программ-шантажистов вопросам о роботстве, создании масштабов и майкрософт, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="0bc4d-112">Очень важно быстро реагировать на атаки и последствия этого.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="0bc4d-113">Чем больше вы ожидаете, скорее всего, восстановление затронутых данных невозможно.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="0bc4d-114">Этап 1. Проверка резервных копий</span><span class="sxs-lookup"><span data-stu-id="0bc4d-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="0bc4d-115">Если имеются автономные резервные копии, **after** вероятно, можно восстановить зашифрованные данные после того, как вы удалите вредоносные программы-шума (вредоносное ПО) из среды.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="0bc4d-116">Если резервные копии не были затронуты или они также затронуты выдачей пользователей, это можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="0bc4d-117">Шаг 2. Отключение синхронизации ActiveSync и OneDrive</span><span class="sxs-lookup"><span data-stu-id="0bc4d-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="0bc4d-118">Ключевой момент — остановить раскрытие шифрования данных от вымогателя.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="0bc4d-119">Если вы подозреваете, что письмо является целью, необходимо временно отключить доступ пользователей к почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="0bc4d-120">Exchange ActiveSync используется мобильными устройствами для синхронизации данных между устройством и почтовым ящиком Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="0bc4d-121">Сведения об отключении ActiveSync для почтового ящика см. в [статье Как отключить Exchange ActiveSync для пользователей в Exchange Online.](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="0bc4d-122">Чтобы отключить доступ других типов к почтовому ящику, см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="0bc4d-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="0bc4d-123">[Включение и отключение MAPI для почтового ящика.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="0bc4d-124">Включение или отключение доступа по протоколу POP3 или IMAP4 для пользователя</span><span class="sxs-lookup"><span data-stu-id="0bc4d-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="0bc4d-125">Приостановка синхронизации OneDrive поможет защитить облачные данные от обновления данных потенциально зараженными устройствами.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="0bc4d-126">Дополнительные сведения см. в статье [Как приостановить и возобновить синхронизацию в OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="0bc4d-127">Шаг 3. Удалите вредоносную программу из устройств, которые затрагивают</span><span class="sxs-lookup"><span data-stu-id="0bc4d-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="0bc4d-128">Запустите полную проверку на наличие вирусов с помощью последних обновлений на всех подозрительных компьютерах и устройствах, чтобы обнаружить и удалить полезные данные, связанные с программой-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="0bc4d-129">Не забывайте забашать устройства, которые синхронизируют данные, или на устройстве, на которые сопоставлены сетевые диски (компьютеры и устройства также должны быть сканированы).</span><span class="sxs-lookup"><span data-stu-id="0bc4d-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="0bc4d-130">Вы можете использовать [Защитник Windows](https://www.microsoft.com/windows/comprehensive-security) или (для клиентов предыдущих версий) [Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="0bc4d-131">Альтернативным решением, помогающим устранить замканчивания от вредоносных программ или вредоносных [программ, является средство удаления вредоносных программ (MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="0bc4d-132">Если эти параметры не работают, можно попробовать [автономный Защитник Windows](https://support.microsoft.com/help/17466) или устранить [неполадки с обнаружением и удалением вредоносных программ.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="0bc4d-133">Шаг 4. Восстановление файлов на чистом компьютере или устройстве</span><span class="sxs-lookup"><span data-stu-id="0bc4d-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="0bc4d-134">После того как вы выполнили предыдущий шаг по удалению полезных данных программы-шантажиста (это предотвратит шифрование или удаление файлов программой-шантажистом), можно [попытаться](https://support.microsoft.com/help/17128) восстановить локальные файлы и папки с помощью журнала файлов в Windows 10, Windows 8.1 или System Protection в Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="0bc4d-135">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="0bc4d-135">**Notes**:</span></span>

- <span data-ttu-id="0bc4d-136">Некоторые программы-штаты также шифруют или удаляют резервные версии, поэтому восстановление файлов с помощью истории файлов или системной защиты невозможна.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="0bc4d-137">В этом случае потребуется выполнить резервное копирование на внешних дисках или устройствах, на которые не повлияют выкуп или служба OneDrive, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="0bc4d-138">Если папка синхронизирована с OneDrive и вы не используете последнюю версию Windows, на использование журнала файлов могут нанестись некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="0bc4d-139">Шаг 5. Восстановление файлов в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0bc4d-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="0bc4d-140">Восстановление файлов в OneDrive для бизнеса позволяет восстановить всю среду OneDrive на момент времени в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="0bc4d-141">Дополнительные сведения см. в [статье "Восстановление OneDrive".](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="0bc4d-142">Шаг 6. Восстановление удаленной электронной почты</span><span class="sxs-lookup"><span data-stu-id="0bc4d-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="0bc4d-143">В редких случаях, когда программа-служба была удалена из всех сообщений электронной почты, можно восстановить удаленные элементы.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="0bc4d-144">Дополнительные сведения см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="0bc4d-144">For more information, see:</span></span>

- [<span data-ttu-id="0bc4d-145">Восстановление удаленных сообщений в почтовом ящике пользователя</span><span class="sxs-lookup"><span data-stu-id="0bc4d-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="0bc4d-146">Восстановление удаленных элементов в Outlook для Windows</span><span class="sxs-lookup"><span data-stu-id="0bc4d-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="0bc4d-147">Шаг 7. Повторное включение синхронизации Exchange ActiveSync и OneDrive</span><span class="sxs-lookup"><span data-stu-id="0bc4d-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="0bc4d-148">После очистки компьютеров и устройств и восстановления своих данных вы можете повторно включить синхронизацию ActiveSync и OneDrive, которую вы отключили на [шаге 2.](#step-2-disable-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="0bc4d-149">Шаг 8 (необязательно). Блокировка синхронизации OneDrive для определенных расширений файлов</span><span class="sxs-lookup"><span data-stu-id="0bc4d-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="0bc4d-150">После восстановления можно запретить клиентам OneDrive для бизнеса синхронизировать типы файлов, на которые повлияло данная выкуп кантортами.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="0bc4d-151">Дополнительные сведения см. в [статье Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="0bc4d-152">Сообщает об атаке</span><span class="sxs-lookup"><span data-stu-id="0bc4d-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="0bc4d-153">органа цепочки контакта</span><span class="sxs-lookup"><span data-stu-id="0bc4d-153">Contact law enforcement</span></span>

<span data-ttu-id="0bc4d-154">Вам следует обращаться к местным или федеральным органам управления органами.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="0bc4d-155">Например, если вы находятесь в США, вы можете связаться с локальным [офисом FBI,](https://www.fbi.gov/contact-us/field) [IC3 или секретным](http://www.ic3.gov/complaint/default.aspx) [секретным секретным секретом.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="0bc4d-156">Отправка отчета на веб-сайт отчетов по стране вашей страны</span><span class="sxs-lookup"><span data-stu-id="0bc4d-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="0bc4d-157">В веб-сайтах отчетов в области Scam представлены сведения о том, как предотвращать и избегать помех.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="0bc4d-158">Они также предоставляют механизмы, о которых сообщается об имеющемся всю нумерацию.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="0bc4d-159">Австралия: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="0bc4d-160">Канада: [канадский антивирусный срез](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="0bc4d-161">Франция: [Агрессия nationale de la sécurité des systémes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="0bc4d-162">Германия: [Bundesamt fêr Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="0bc4d-163">Ирландия: [An Garda Sêochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="0bc4d-164">Нью-Зеландия: [пользователи, ладони](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="0bc4d-165">Соединенное Коэффициент: [Мошенничество](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="0bc4d-166">США: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="0bc4d-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="0bc4d-167">Если вашей страны нет в списке, попросите спросить местные или федеральные органы управления органами.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="0bc4d-168">Отправка сообщений электронной почты в Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0bc4d-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="0bc4d-169">Можно сообщать о фишинговых сообщениях, содержащих программы-шантажисты, с помощью нескольких способов.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-169">You can report phishing message that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="0bc4d-170">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="0bc4d-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0bc4d-171">См. также</span><span class="sxs-lookup"><span data-stu-id="0bc4d-171">See also</span></span>

- [<span data-ttu-id="0bc4d-172">Вымоганизация</span><span class="sxs-lookup"><span data-stu-id="0bc4d-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="0bc4d-173">Реакция с помощью выручки, плата или не заплатяемая?</span><span class="sxs-lookup"><span data-stu-id="0bc4d-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="0bc4d-174">Norsk Hydro реагирует на атаки программ-шантажистов с прозрачностью</span><span class="sxs-lookup"><span data-stu-id="0bc4d-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="0bc4d-175">Обнаружение программ-шумостей и восстановление файлов в OneDrive</span><span class="sxs-lookup"><span data-stu-id="0bc4d-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="0bc4d-176">Microsoft Security Intelligence Report</span><span class="sxs-lookup"><span data-stu-id="0bc4d-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="0bc4d-177">Включение и отключение макросов в файлах Office</span><span class="sxs-lookup"><span data-stu-id="0bc4d-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="0bc4d-178">Рекомендуемые параметры для безопасности EOP и Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="0bc4d-178">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="0bc4d-179">Стойкое обновление: безопасность следующего поколения в Windows 10 подтверждает устойчивость от программ-шумостей в 2017 г.</span><span class="sxs-lookup"><span data-stu-id="0bc4d-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="0bc4d-180">Нет массий, Samas. Что такое модули топунсы программ-</span><span class="sxs-lookup"><span data-stu-id="0bc4d-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="0bc4d-181">Блокировка вредоносного ПО маскетрично, чтобы избежать этого</span><span class="sxs-lookup"><span data-stu-id="0bc4d-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="0bc4d-182">MSRT июль 2016 г.: кербер-программа</span><span class="sxs-lookup"><span data-stu-id="0bc4d-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="0bc4d-183">Три заголовка cerberus как Cerberus-Rans- для Cerber-пользу</span><span class="sxs-lookup"><span data-stu-id="0bc4d-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="0bc4d-184">Торговая программа-шантажист по влиянию на (код) Дв-Винки</span><span class="sxs-lookup"><span data-stu-id="0bc4d-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
