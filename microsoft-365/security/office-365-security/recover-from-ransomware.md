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
description: Администраторы Microsoft 365 могут узнать, как восстановиться после атаки программы-вымогателя.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 120dd9ae71f04d6921fae95965f56f0a08f1280c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289309"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Восстановление после атаки программы-вымогателя в Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Даже если вы принимаете все меры предосторожности для защиты своей организации, вы все равно можете стать жертвой атаки [программы-вымогателя.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) Программы-выкупы — это большой бизнес, а атаки очень сложные.

Действия, которые необходимо предпринять в этой статье, дают вам наилучшие возможности для восстановления данных и остановки внутреннего распространения заражения. Прежде чем приступать к его созданию, учтите следующие факторы:

- Нет гарантии, что выплата выкупа возвратит доступ к вашим файлам. На самом деле, оплата выкупа может сделать вас целью для дополнительных программ-вымогателей.

  Если вы уже оплатили транзакцию, но не воспользовались решением злоумышленника, обратитесь в банк, чтобы узнать, могут ли они заблокировать транзакцию.

  Мы также рекомендуем сообщить о атаке программы-вымогателя правоохранительным органам, веб-сайтам отчетов о схимах и Корпорации Майкрософт, как описано далее в этой статье.

- Важно быстро реагировать на атаки и их последствия. Чем дольше вы будете ждать, тем меньше вероятность того, что вы сможете восстановить затронутые данные.

## <a name="step-1-verify-your-backups"></a>Шаг 1. Проверка резервных копий

Если у вас есть автономные резервные копии,  возможно, вы сможете восстановить зашифрованные данные после удаления полезной нагрузки программы-вымогателя (вредоносных программ) из среды.

Если у вас нет резервных копий или резервные копии также были затронуты программами-вымогателями, этот шаг можно пропустить.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Шаг 2. Отключение синхронизации Exchange ActiveSync и OneDrive

Ключевой момент здесь — остановить распространение шифрования данных программами-вымогателями.

Если вы подозреваете, что электронная почта является целью шифрования программ-вымогателей, временно отключайте доступ пользователей к почтовым ящикам. Exchange ActiveSync синхронизирует данные между устройствами и почтовыми ящиками Exchange Online.

Чтобы отключить Exchange ActiveSync для почтового ящика, см. Exchange ActiveSync [для пользователей в Exchange Online.](https://support.microsoft.com/help/2795303)

Чтобы отключить доступ к почтовому ящику других типов, см. в:

- [Включить или отключить MAPI для почтового ящика.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [Enable or Disable POP3 or IMAP4 access for a user](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Приочная синхронизация OneDrive поможет защитить облачные данные от обновления потенциально зараженными устройствами. Дополнительные сведения см. в сведениях о [приостановки и возобновлении синхронизации в OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Шаг 3. Удаление вредоносной программы с затронутых устройств

Запустите полную и текущую антивирусную проверку на всех подозрительных компьютерах и устройствах, чтобы обнаружить и удалить полезной нагрузки, связанные с программой-вымогателями.

Не забудьте сканировать устройства, которые синхронизируют данные, или целевые объекты сетевых дисков.

Вы можете [использовать](https://www.microsoft.com/windows/comprehensive-security) Защитник Windows или (для старых клиентов) [Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)

Альтернативой для удаления программ-вымогателей или вредоносных программ является средство удаления вредоносных программ [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Если эти параметры не работают, [](https://support.microsoft.com/help/17466) вы можете попробовать Защитник Windows автономном режиме или устранить проблемы с обнаружением и удалением [вредоносных программ.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Шаг 4. Восстановление файлов на очищенных компьютерах или устройствах

После завершения предыдущего шага для удаления полезной нагрузки программы-вымогателя из среды (которая не позволит [](https://support.microsoft.com/help/17128) программам-вымогателям шифровать или удалять файлы), вы можете использовать историю файлов в Windows 10 и Windows 8.1 или System Protection в Windows 7, чтобы попытаться восстановить локальные файлы и папки.

**Примечания**.

- Некоторые программы-вымодеры также шифруют или удаляют резервные версии, поэтому нельзя использовать для восстановления файлов файлы с помощью функции "История файлов" или "Защита системы". В этом случае необходимо использовать резервные копии на внешних дисках или устройствах, которые не были затронуты программами-вымогателями или OneDrive, как описано в следующем разделе.

- Если папка синхронизируется с OneDrive и вы не используете последнюю версию Windows, с помощью истории файлов могут быть некоторые ограничения.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Шаг 5. Восстановление файлов в OneDrive для бизнеса

Восстановление файлов в OneDrive для бизнеса позволяет восстановить все хранилище OneDrive до предыдущего момента в течение последних 30 дней. Дополнительные сведения см. в [теме "Восстановление OneDrive".](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>Шаг 6. Восстановление удаленной электронной почты

В редких случаях, когда программа-вымогаатель удалила всю электронную почту, вы, вероятно, сможете восстановить удаленные элементы. Дополнительные сведения см. в указанных ниже статьях.

- [Восстановление удаленных сообщений в почтовом ящике пользователя](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Восстановление удаленных элементов в Outlook для Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Шаг 7. Повторное Exchange ActiveSync синхронизации OneDrive

После очистки компьютеров и устройств и восстановления данных вы можете повторно включить синхронизацию Exchange ActiveSync и OneDrive, ранее отключенную на шаге [2.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Шаг 8 (необязательно). Блокировка синхронизации OneDrive для определенных расширений файлов

После восстановления вы можете запретить клиентам OneDrive для бизнеса синхронизировать типы файлов, затронутые программой-выкупом. Дополнительные сведения см. в [подстройки Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Сообщение о атаке

### <a name="contact-law-enforcement"></a>Обратитесь в правоохранительные органы

Обратитесь в местные или федеральные правоохранительные органы. Например, если вы находитесь в СОЕДИНЕННЫх Штатах, вы можете связаться с локальным офисом ПОЛЕЙ ИК3 ( [IC3)](http://www.ic3.gov/complaint/default.aspx) или службой [секретов](http://www.secretservice.gov/) [(IC3).](https://www.fbi.gov/contact-us/field)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Отправка отчета на веб-сайт отчетов об афере в вашей стране

На веб-сайтах отчетов о мошенничествох можно найти сведения о том, как предотвращать и избегать мошенничества. Они также предоставляют механизмы для отчетов о том, что вы стали жертвой аферы.

- Австралия: [SCAMwatch](http://www.scamwatch.gov.au/)

- Канада: [Канадский центр по борьбе с мошенничеством](http://www.antifraudcentre-centreantifraude.ca/)

- Франция: [agence nationale de la sécurité des systémes d'information](http://www.ssi.gouv.fr/)

- Германия: [Сичерхейт für für в der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Ирландия: [Garda Síochána](http://www.garda.ie/)

- Новая Зеландия: [мошенничество с потребительскими вопросами](http://www.consumeraffairs.govt.nz/scams)

- Соединенное Королевство: [мошенничество с действиями](http://www.actionfraud.police.uk/)

- США: [On Guard Online](http://www.onguardonline.gov/)

Если ваша страна не указана в списке, попросите местные или федеральные правоохранительные органы.

### <a name="submit-email-messages-to-microsoft"></a>Отправка сообщений электронной почты в корпорацию Майкрософт

Вы можете сообщить о фишинговых сообщениях, содержащих программы-вымогателя, одним из нескольких методов. Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>См. также

- [Программы-программы-вымогателя](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Ответ программы-вымогателя — оплата или невыплата?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Вайс реагирует на атаки программы-вымогателя с прозрачностью](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Обнаружение программ-вымогателей и восстановление файлов в OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Отчет по аналитике безопасности (Майкрософт)](https://www.microsoft.com/securityinsights/)

- [Включить или отключить макрос в файлах Office](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Рекомендуемые параметры для EOP и Microsoft Defender для безопасности Office 365](recommended-settings-for-eop-and-office365-atp.md)

- [Надежное обновление: безопасность следующего поколения в Windows 10 подтверждает устойчивость к вспышкам программ-вымогателей в 2017 г.](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Нет мас, Samas: что в модусе операди этого программы-вымогателя?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Блокировка вредоносных программ, чтобы избежать ее](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT июль 2016 г.: программа-программа-вымогателе Cerber](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Три заголовок программы-вымогателя Cerber, похожей на Cerber](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Программа-программа-программа-вымогателя, на которые влияет код daАА](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
