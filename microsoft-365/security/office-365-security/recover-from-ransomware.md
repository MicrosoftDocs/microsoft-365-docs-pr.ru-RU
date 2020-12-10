---
title: Восстановление после атаки программы-шантажиста
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Администраторы Microsoft 365 могут узнать, как восстановить систему от атак с помощью функции "атаки с помощью функции".
ms.openlocfilehash: ad3f044e338abeb56046538bdda8df7b8510be0e
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615904"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="29592-103">Восстановление при атаке программой "шантажистом" в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29592-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="29592-104">Даже если вы предпримете все меры предосторожности для защиты вашей организации, вы по-прежнему можете жертвой атакой от атаки с помощью [атаки](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) с помощью</span><span class="sxs-lookup"><span data-stu-id="29592-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="29592-105">Эта атака является большим предприятием, а атаки очень сложны.</span><span class="sxs-lookup"><span data-stu-id="29592-105">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="29592-106">Действия, описанные в этой статье, помогут вам в восстановлении данных и остановке внутреннего распространения заражения.</span><span class="sxs-lookup"><span data-stu-id="29592-106">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="29592-107">Прежде чем приступать к его созданию, учтите следующие факторы:</span><span class="sxs-lookup"><span data-stu-id="29592-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="29592-108">Нет гарантии, что оплата Рансом возвратит доступ к вашим файлам.</span><span class="sxs-lookup"><span data-stu-id="29592-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="29592-109">На самом деле, оплата Рансом может сделать целевой для дополнительной атаки.</span><span class="sxs-lookup"><span data-stu-id="29592-109">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="29592-110">Если вы уже оплачиваете, но вы восстановили ее без использования вредоносного средства, обратитесь в банк, чтобы узнать, можно ли заблокировать эту транзакцию.</span><span class="sxs-lookup"><span data-stu-id="29592-110">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="29592-111">Кроме того, рекомендуется сообщать об атаке с помощью средства "мошенническое использование" для правоохранительных и мошеннических веб-сайтов, а также Майкрософт, как описано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="29592-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="29592-112">Очень важно быстро реагировать на атаку и ее последствия.</span><span class="sxs-lookup"><span data-stu-id="29592-112">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="29592-113">Чем больше время ожидания, тем менее вероятно, что вы можете восстановить затронутые данные.</span><span class="sxs-lookup"><span data-stu-id="29592-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="29592-114">Шаг 1: Проверка резервных копий</span><span class="sxs-lookup"><span data-stu-id="29592-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="29592-115">При наличии автономных резервных копий вы можете восстановить зашифрованные данные **после** удаления из вашей среды полезных данных программы-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="29592-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="29592-116">Если вы не обладаете резервными копиями, а также в том случае, если вы также затронули ее, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="29592-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="29592-117">Шаг 2: Отключение синхронизации Exchange ActiveSync и OneDrive</span><span class="sxs-lookup"><span data-stu-id="29592-117">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="29592-118">Ключевой момент здесь заключается в остановке распространения шифрования данных программой-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="29592-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="29592-119">Если вы подозреваете электронную почту в качестве целевого объекта для шифрования с помощью атаки, временно отключите доступ пользователей к почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="29592-119">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="29592-120">Exchange ActiveSync синхронизирует данные между устройствами и почтовыми ящиками Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="29592-120">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="29592-121">Чтобы отключить Exchange ActiveSync для почтового ящика, Узнайте, [как отключить Exchange ActiveSync для пользователей в Exchange Online](https://support.microsoft.com/help/2795303).</span><span class="sxs-lookup"><span data-stu-id="29592-121">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="29592-122">Чтобы отключить другие типы доступа к почтовому ящику, ознакомьтесь со статьей:</span><span class="sxs-lookup"><span data-stu-id="29592-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="29592-123">[Включение или отключение MAPI для почтового ящика](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="29592-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="29592-124">Включение или отключение доступа по протоколу POP3 или IMAP4 для пользователя</span><span class="sxs-lookup"><span data-stu-id="29592-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="29592-125">Приостановка синхронизации OneDrive поможет защитить облачные данные от обновления потенциально инфицированных устройств.</span><span class="sxs-lookup"><span data-stu-id="29592-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="29592-126">Для получения дополнительных сведений Узнайте, [как приостановить и возобновить синхронизацию в OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="29592-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="29592-127">Шаг 3: Удаление вредоносных программ с затронутых устройств</span><span class="sxs-lookup"><span data-stu-id="29592-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="29592-128">Выполнение полной и текущей антивирусной проверки на всех подозреваемых компьютерах и устройствах для обнаружения и удаления полезных данных, связанных с программой.</span><span class="sxs-lookup"><span data-stu-id="29592-128">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="29592-129">Не забудьте проверить устройства, являющиеся синхронизацией данных, или целевые объекты подключенных сетевых дисков.</span><span class="sxs-lookup"><span data-stu-id="29592-129">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="29592-130">В [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)можно использовать [Защитник Windows](https://www.microsoft.com/windows/comprehensive-security) или (для старых клиентов).</span><span class="sxs-lookup"><span data-stu-id="29592-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="29592-131">Кроме того, вы можете удалить программу-шантажистом или вредоносную программу с помощью [средства удаления вредоносных программ (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="29592-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="29592-132">Если эти параметры не работают, можно попробовать [Отключить Защитник Windows](https://support.microsoft.com/help/17466) или [устранить неполадки, связанные с обнаружением и удалением вредоносных программ](https://support.microsoft.com/help/4466982).</span><span class="sxs-lookup"><span data-stu-id="29592-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="29592-133">Шаг 4: восстановление файлов на очищенном компьютере или устройстве</span><span class="sxs-lookup"><span data-stu-id="29592-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="29592-134">После выполнения предыдущего действия для удаления полезных данных программой-шантажистом из среды (что предотвратит шифрование и удаление файлов программой-шантажистом) можно использовать [историю файлов](https://support.microsoft.com/help/17128) в Windows 10 и Windows 8,1 или системы защиты системы в Windows 7, чтобы попытаться восстановить локальные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="29592-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="29592-135">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="29592-135">**Notes**:</span></span>

- <span data-ttu-id="29592-136">Некоторые средства защиты от вирусов также шифруют и удаляют версии резервных копий, поэтому для восстановления файлов невозможно использовать историю файлов или систему защиты системы.</span><span class="sxs-lookup"><span data-stu-id="29592-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="29592-137">В этом случае вам потребуется использовать резервные копии на внешних дисках или устройствах, которые не были затронуты программой "шантажистом" или OneDrive, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="29592-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="29592-138">Если папка синхронизирована с OneDrive и вы не используете последнюю версию Windows, то некоторые ограничения могут быть связаны с использованием истории файлов.</span><span class="sxs-lookup"><span data-stu-id="29592-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="29592-139">Шаг 5: восстановление файлов в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="29592-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="29592-140">Восстановление файлов в OneDrive для бизнеса позволяет восстановить в течение последних 30 дней весь OneDrive до предыдущего момента времени.</span><span class="sxs-lookup"><span data-stu-id="29592-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="29592-141">Дополнительные сведения см. в статье [Восстановление OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="29592-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="29592-142">Шаг 6: восстановление удаленной почты</span><span class="sxs-lookup"><span data-stu-id="29592-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="29592-143">В редких случаях, когда средство записи в систему удалило всю электронную почту, возможно, вы восстановите удаленные элементы.</span><span class="sxs-lookup"><span data-stu-id="29592-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="29592-144">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="29592-144">For more information, see:</span></span>

- [<span data-ttu-id="29592-145">Восстановление удаленных сообщений в почтовом ящике пользователя</span><span class="sxs-lookup"><span data-stu-id="29592-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="29592-146">Восстановление удаленных элементов в Outlook для Windows</span><span class="sxs-lookup"><span data-stu-id="29592-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="29592-147">Шаг 7: повторное включение синхронизации Exchange ActiveSync и OneDrive</span><span class="sxs-lookup"><span data-stu-id="29592-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="29592-148">После очистки компьютеров и устройств и восстановления данных можно повторно включить службу Exchange ActiveSync и синхронизацию OneDrive, которая была отключена на [шаге 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span><span class="sxs-lookup"><span data-stu-id="29592-148">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="29592-149">Шаг 8 (необязательно): блокировка синхронизации OneDrive для определенных расширений файлов</span><span class="sxs-lookup"><span data-stu-id="29592-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="29592-150">После восстановления вы можете запретить клиентам OneDrive для бизнеса синхронизировать типы файлов, затрагиваемые этой программой-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="29592-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="29592-151">Для получения дополнительных сведений см. [Set – SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="29592-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="29592-152">Сообщить об атаке</span><span class="sxs-lookup"><span data-stu-id="29592-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="29592-153">Принудительное применение правоохранительных лиц</span><span class="sxs-lookup"><span data-stu-id="29592-153">Contact law enforcement</span></span>

<span data-ttu-id="29592-154">Вы должны обратиться к местным или федеральным правоохранительным ведомствам.</span><span class="sxs-lookup"><span data-stu-id="29592-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="29592-155">Например, если вы используете США, вы можете связаться с [местным полем Office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) или [секретной службой](http://www.secretservice.gov/)ФБР.</span><span class="sxs-lookup"><span data-stu-id="29592-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="29592-156">Отправка отчета на веб-сайт мошенничества для отчетности в вашей стране</span><span class="sxs-lookup"><span data-stu-id="29592-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="29592-157">Веб-сайты для создания отчетов о мошенничестве содержат сведения о том, как предотвратить и избегать мошенничества.</span><span class="sxs-lookup"><span data-stu-id="29592-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="29592-158">Кроме того, они предоставляют механизмы для отчета, если вы стали жертвой мошенничества.</span><span class="sxs-lookup"><span data-stu-id="29592-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="29592-159">Австралия: [скамватч](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="29592-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="29592-160">Канада: [канадский (Канада) центр защиты от мошенничества](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="29592-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="29592-161">Франция: [аженце National сéкуритé des систèмес д'информатион](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="29592-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="29592-162">Германия: [бундесамт фüр сичерхеит в Der информатионстечник](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="29592-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="29592-163">Ирландия: [Гарда сíочáна](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="29592-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="29592-164">Новая Зеландия: [мошенничество по охране потребителей](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="29592-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="29592-165">Великобритания: [действие мошенничество](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="29592-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="29592-166">США: [в службе безопасности Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="29592-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="29592-167">Если ваша страна отсутствует в списке, обратитесь к местным или федеральным правоохранительным ведомствам.</span><span class="sxs-lookup"><span data-stu-id="29592-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="29592-168">Отправка сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="29592-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="29592-169">Вы можете сообщить о phishing-сообщениях, которые содержат средства для атаки, одним из нескольких способов.</span><span class="sxs-lookup"><span data-stu-id="29592-169">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="29592-170">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="29592-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="29592-171">См. также</span><span class="sxs-lookup"><span data-stu-id="29592-171">See also</span></span>

- [<span data-ttu-id="29592-172">Программой</span><span class="sxs-lookup"><span data-stu-id="29592-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="29592-173">Отклик от атаки программой-шантажистом — оплачивается или не оплачивается?</span><span class="sxs-lookup"><span data-stu-id="29592-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="29592-174">Норск Хидро реагирует на атаку с помощью команды "атаку" с прозрачностью</span><span class="sxs-lookup"><span data-stu-id="29592-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="29592-175">Обнаружение и восстановление файлов в OneDrive</span><span class="sxs-lookup"><span data-stu-id="29592-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="29592-176">Отчет Microsoft Security Intelligence</span><span class="sxs-lookup"><span data-stu-id="29592-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="29592-177">Включение и отключение макросов в файлах Office</span><span class="sxs-lookup"><span data-stu-id="29592-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="29592-178">Рекомендуемые параметры для EOP и Microsoft Defender для Office 365 Security</span><span class="sxs-lookup"><span data-stu-id="29592-178">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="29592-179">Обновление стоит: Следующая безопасность поколения для Windows 10 удостоверяется в устойчивости от эпидемий с помощью программы "размыкатель" в 2017</span><span class="sxs-lookup"><span data-stu-id="29592-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="29592-180">Нет МАС, Самас: что находится в этой модусе для атаки, операнди?</span><span class="sxs-lookup"><span data-stu-id="29592-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="29592-181">Блокировка вредоносных программ, счастливого, чтобы избежать</span><span class="sxs-lookup"><span data-stu-id="29592-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="29592-182">MSRT — Июль 2016: Цербер</span><span class="sxs-lookup"><span data-stu-id="29592-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="29592-183">Три головки Церберус, похожего на Цербер.</span><span class="sxs-lookup"><span data-stu-id="29592-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="29592-184">Тролдеш-шантажистом, на которые влияет код Da ВинЦи</span><span class="sxs-lookup"><span data-stu-id="29592-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
