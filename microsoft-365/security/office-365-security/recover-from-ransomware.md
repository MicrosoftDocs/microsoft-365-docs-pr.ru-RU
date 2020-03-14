---
title: Восстановление после атаки программы-шантажиста
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
description: Администраторы Office 365 могут узнать, как восстановить систему от атак с помощью функции "атаки с помощью системы".
ms.openlocfilehash: aa606ea3bf3f549645fe26a4aa95066568132243
ms.sourcegitcommit: 72983702a42552a29228d387bb279e8ff2ab59b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "42640021"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a><span data-ttu-id="0cf0b-103">Восстановление после атаки с помощью функции "шантажистом" в Office 365</span><span class="sxs-lookup"><span data-stu-id="0cf0b-103">Recover from a ransomware attack in Office 365</span></span>

<span data-ttu-id="0cf0b-104">Даже если вы предпримете все меры предосторожности для защиты вашей организации Office 365, вы по-прежнему можете жертвой атакой от атаки [программой-шантажистом](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) .</span><span class="sxs-lookup"><span data-stu-id="0cf0b-104">Even if you take every precaution to protect your Office 365 organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="0cf0b-105">Эта атака является большим предприятием, а атаки — проверены.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="0cf0b-106">Действия, описанные в этом разделе, помогут вам в восстановлении данных, зашифрованных программой «шантажистом», и приостановить распространение заражения в организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your Office 365 organization.</span></span> <span data-ttu-id="0cf0b-107">Прежде чем приступать к его созданию, учтите следующие факторы:</span><span class="sxs-lookup"><span data-stu-id="0cf0b-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="0cf0b-108">Нет гарантии, что оплата Рансом возвратит доступ к вашим файлам.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="0cf0b-109">На самом деле, оплата Рансом может сделать целевой для дополнительной атаки.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="0cf0b-110">Если вы уже оплачиваете, но можете успешно восстановить файлы, не используя разрешение злоумышленника, следует позвонить в банк, чтобы узнать, можно ли заблокировать эту транзакцию.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="0cf0b-111">Кроме того, рекомендуется сообщить о том, что атака с помощью средства-шантажистом посвящена законным и мошенническим веб-сайтам Майкрософт, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="0cf0b-112">Очень важно быстро реагировать на атаку и ее последствия.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="0cf0b-113">Чем больше время ожидания, тем менее вероятно, что вы можете восстановить затронутые данные.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="0cf0b-114">Шаг 1: Проверка резервных копий</span><span class="sxs-lookup"><span data-stu-id="0cf0b-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="0cf0b-115">При наличии автономных резервных копий вы можете восстановить зашифрованные данные **после** удаления из вашей среды полезных данных программы-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="0cf0b-116">Если вы не обладаете резервными копиями, а также в том случае, если вы также затронули ее, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="0cf0b-117">Шаг 2: Отключение синхронизации ActiveSync и OneDrive</span><span class="sxs-lookup"><span data-stu-id="0cf0b-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="0cf0b-118">Ключевой момент здесь заключается в остановке распространения шифрования данных программой-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="0cf0b-119">Если вы подозреваете, что электронная почта является целевой, необходимо временно отключить доступ пользователей к почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="0cf0b-120">Exchange ActiveSync используется мобильными устройствами для синхронизации данных между устройством и почтовым ящиком Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="0cf0b-121">Чтобы отключить ActiveSync для почтового ящика, Узнайте, [как отключить Exchange ActiveSync для пользователей в Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span></span>

<span data-ttu-id="0cf0b-122">Чтобы отключить другие типы доступа к почтовому ящику, ознакомьтесь со статьей:</span><span class="sxs-lookup"><span data-stu-id="0cf0b-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="0cf0b-123">[Включение или отключение MAPI для почтового ящика](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="0cf0b-124">Включение или отключение доступа по протоколу POP3 или IMAP4 для пользователя</span><span class="sxs-lookup"><span data-stu-id="0cf0b-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="0cf0b-125">Приостановка синхронизации OneDrive поможет защитить облачные данные от обновления потенциально инфицированных устройств.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="0cf0b-126">Для получения дополнительных сведений Узнайте, [как приостановить и возобновить синхронизацию в OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="0cf0b-127">Шаг 3: Удаление вредоносных программ с затронутых устройств</span><span class="sxs-lookup"><span data-stu-id="0cf0b-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="0cf0b-128">Запустите полную антивирусную проверку с последними обновлениями на всех подозреваемых компьютерах и устройствах, чтобы обнаружить и удалить полезную нагрузку, связанную с программой.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="0cf0b-129">Не забывайте устройства, являющиеся синхронизацией данных, или целевые диски с подключенными сетевыми дисками (эти компьютеры и устройства необходимо проверить).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="0cf0b-130">В [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)можно использовать [Защитник Windows](https://www.microsoft.com/windows/comprehensive-security) или (для старых клиентов).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="0cf0b-131">Кроме того, вы можете удалить программу-шантажистом или вредоносную программу с помощью [средства удаления вредоносных программ (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="0cf0b-132">Если эти параметры не работают, можно попробовать [Отключить Защитник Windows](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) или [устранить неполадки, связанные с обнаружением и удалением вредоносных программ](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="0cf0b-133">Шаг 4: восстановление файлов на очищенном компьютере или устройстве</span><span class="sxs-lookup"><span data-stu-id="0cf0b-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="0cf0b-134">После выполнения предыдущего действия для удаления полезных данных программой-шантажистом из среды (что предотвратит шифрование и удаление файлов программой-шантажистом) можно использовать [историю файлов](https://support.microsoft.com/help/17128/windows-8-file-history) в Windows 10 и Windows 8,1 или системы защиты системы в Windows 7, чтобы попытаться восстановить локальные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="0cf0b-135">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="0cf0b-135">**Notes**:</span></span>

- <span data-ttu-id="0cf0b-136">Некоторые средства защиты от вирусов также шифруют и удаляют версии резервных копий, поэтому для восстановления файлов невозможно использовать историю файлов или систему защиты системы.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="0cf0b-137">В этом случае вам потребуется использовать резервные копии на внешних дисках или устройствах, которые не были затронуты программой "шантажистом" или OneDrive, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="0cf0b-138">Если папка синхронизирована с OneDrive и вы не используете последнюю версию Windows, то некоторые ограничения могут быть связаны с использованием истории файлов.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="0cf0b-139">Шаг 5: восстановление файлов в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0cf0b-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="0cf0b-140">Восстановление файлов в OneDrive для бизнеса позволяет восстановить в течение последних 30 дней весь OneDrive до предыдущего момента времени.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="0cf0b-141">Дополнительные сведения см. в статье [Восстановление OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-141">For more information, see [Restore your OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="0cf0b-142">Шаг 6: восстановление удаленной почты</span><span class="sxs-lookup"><span data-stu-id="0cf0b-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="0cf0b-143">В редких случаях, когда средство записи в систему удалило всю электронную почту, возможно, вы восстановите удаленные элементы.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="0cf0b-144">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-144">For more information, see:</span></span>

- [<span data-ttu-id="0cf0b-145">Восстановление удаленных сообщений в почтовом ящике пользователя</span><span class="sxs-lookup"><span data-stu-id="0cf0b-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="0cf0b-146">Восстановление удаленных элементов в Outlook для Windows</span><span class="sxs-lookup"><span data-stu-id="0cf0b-146">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="0cf0b-147">Шаг 7: повторное включение синхронизации Exchange ActiveSync и OneDrive</span><span class="sxs-lookup"><span data-stu-id="0cf0b-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="0cf0b-148">После очистки компьютеров и устройств и восстановления данных можно повторно включить ActiveSync и синхронизацию OneDrive, которые вы ранее отключили в [действии 2](#step-2-disable-activesync-and-onedrive-sync).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="0cf0b-149">Шаг 8 (необязательно): блокировка синхронизации OneDrive для определенных расширений файлов</span><span class="sxs-lookup"><span data-stu-id="0cf0b-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="0cf0b-150">После восстановления вы можете запретить клиентам OneDrive для бизнеса синхронизировать типы файлов, затрагиваемые этой программой-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="0cf0b-151">Для получения дополнительных сведений см. [Set – SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="0cf0b-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="0cf0b-152">Сообщить об атаке</span><span class="sxs-lookup"><span data-stu-id="0cf0b-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="0cf0b-153">Принудительное применение правоохранительных лиц</span><span class="sxs-lookup"><span data-stu-id="0cf0b-153">Contact law enforcement</span></span>

<span data-ttu-id="0cf0b-154">Вы должны обратиться к местным или федеральным правоохранительным ведомствам.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="0cf0b-155">Например, если вы используете США, вы можете связаться с [местным полем Office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) или [секретной службой](http://www.secretservice.gov/)ФБР.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="0cf0b-156">Отправка отчета на веб-сайт мошенничества для отчетности в вашей стране</span><span class="sxs-lookup"><span data-stu-id="0cf0b-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="0cf0b-157">Веб-сайты для создания отчетов о мошенничестве содержат сведения о том, как предотвратить и избегать мошенничества.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="0cf0b-158">Кроме того, они предоставляют механизмы для отчета, если вы стали жертвой мошенничества.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="0cf0b-159">Австралия: [скамватч](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="0cf0b-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="0cf0b-160">Канада: [канадский (Канада) центр защиты от мошенничества](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="0cf0b-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="0cf0b-161">Франция: [аженце National сéкуритé des систèмес д'информатион](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="0cf0b-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="0cf0b-162">Германия: [бундесамт фüр сичерхеит в Der информатионстечник](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="0cf0b-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="0cf0b-163">Ирландия: [Гарда сíочáна](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="0cf0b-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="0cf0b-164">Новая Зеландия: [мошенничество по охране потребителей](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="0cf0b-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="0cf0b-165">Великобритания: [действие мошенничество](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="0cf0b-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="0cf0b-166">США: [в службе безопасности Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="0cf0b-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="0cf0b-167">Если ваша страна отсутствует в списке, обратитесь к местным или федеральным правоохранительным ведомствам.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="0cf0b-168">Отправка сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0cf0b-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="0cf0b-169">Вы можете сообщить о phishing-сообщениях с программой-шантажистом, следуя инструкциям в статье [Отправка спама, нежелательной почты и фишинговых сообщений в корпорацию Майкрософт для анализа](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).</span><span class="sxs-lookup"><span data-stu-id="0cf0b-169">You can report phishing message that contain ransomware by following the instructions in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).</span></span>

## <a name="see-also"></a><span data-ttu-id="0cf0b-170">См. также</span><span class="sxs-lookup"><span data-stu-id="0cf0b-170">See also</span></span>

- [<span data-ttu-id="0cf0b-171">Программой</span><span class="sxs-lookup"><span data-stu-id="0cf0b-171">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="0cf0b-172">Отклик от атаки программой-шантажистом — оплачивается или не оплачивается?</span><span class="sxs-lookup"><span data-stu-id="0cf0b-172">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="0cf0b-173">Норск Хидро реагирует на атаку с помощью команды "атаку" с прозрачностью</span><span class="sxs-lookup"><span data-stu-id="0cf0b-173">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="0cf0b-174">Обнаружение и восстановление файлов в OneDrive</span><span class="sxs-lookup"><span data-stu-id="0cf0b-174">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="0cf0b-175">Отчет Microsoft Security Intelligence</span><span class="sxs-lookup"><span data-stu-id="0cf0b-175">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="0cf0b-176">Включение и отключение макросов в файлах Office</span><span class="sxs-lookup"><span data-stu-id="0cf0b-176">Enable or disable macros in Office files</span></span>](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="0cf0b-177">Рекомендуемые параметры для EOP и безопасности ATP 365 для Office</span><span class="sxs-lookup"><span data-stu-id="0cf0b-177">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="0cf0b-178">Обновление стоит: Следующая безопасность поколения для Windows 10 удостоверяется в устойчивости от эпидемий с помощью программы "размыкатель" в 2017</span><span class="sxs-lookup"><span data-stu-id="0cf0b-178">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="0cf0b-179">Нет МАС, Самас: что находится в этой модусе для атаки, операнди?</span><span class="sxs-lookup"><span data-stu-id="0cf0b-179">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="0cf0b-180">Блокировка вредоносных программ, счастливого, чтобы избежать</span><span class="sxs-lookup"><span data-stu-id="0cf0b-180">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="0cf0b-181">MSRT — Июль 2016: Цербер</span><span class="sxs-lookup"><span data-stu-id="0cf0b-181">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="0cf0b-182">Три головки Церберус, похожего на Цербер.</span><span class="sxs-lookup"><span data-stu-id="0cf0b-182">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="0cf0b-183">Тролдеш-шантажистом, на которые влияет код Da ВинЦи</span><span class="sxs-lookup"><span data-stu-id="0cf0b-183">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
