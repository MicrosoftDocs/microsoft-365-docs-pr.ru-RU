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
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Восстановление после атаки программ-шумо-служб в Microsoft 365

Даже в случае мероприятиях по защите организации вы можете отказаться от жертвов к атаке [программ-шумостей.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) Программа-шантажист является большим масштабным бизнес-процессом, и они проверяются на избыточном уровне.

В этом разделе представлена лучшая возможность восстановления данных, зашифрованных выкупом для пользователей, и прекратит расстановку заражения в организации. Прежде чем приступать к его созданию, учтите следующие факторы:

- Не гарантируется, что выплата выкуп за выкуп не даст вам доступа к вашим файлам. На самом деле платеж за выкуп за выкуп может принудить к вам более широкую техническую поддержку. Если вы уже оплачили, но вы успешно сможете восстановить файлы без использования их разрешения злоумышленника, следует вызвать банк, чтобы узнать, могут ли они блокировать транзакцию. Мы также рекомендуем сообщать об атаке программ-шантажистов вопросам о роботстве, создании масштабов и майкрософт, как описано далее в этом разделе.

- Очень важно быстро реагировать на атаки и последствия этого. Чем больше вы ожидаете, скорее всего, восстановление затронутых данных невозможно.

## <a name="step-1-verify-your-backups"></a>Этап 1. Проверка резервных копий

Если имеются автономные резервные копии, **after** вероятно, можно восстановить зашифрованные данные после того, как вы удалите вредоносные программы-шума (вредоносное ПО) из среды.

Если резервные копии не были затронуты или они также затронуты выдачей пользователей, это можно пропустить.

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>Шаг 2. Отключение синхронизации ActiveSync и OneDrive

Ключевой момент — остановить раскрытие шифрования данных от вымогателя.

Если вы подозреваете, что письмо является целью, необходимо временно отключить доступ пользователей к почтовым ящикам. Exchange ActiveSync используется мобильными устройствами для синхронизации данных между устройством и почтовым ящиком Exchange Online.

Сведения об отключении ActiveSync для почтового ящика см. в [статье Как отключить Exchange ActiveSync для пользователей в Exchange Online.](https://support.microsoft.com/help/2795303)

Чтобы отключить доступ других типов к почтовому ящику, см. следующие статьи:

- [Включение и отключение MAPI для почтового ящика.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [Включение или отключение доступа по протоколу POP3 или IMAP4 для пользователя](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Приостановка синхронизации OneDrive поможет защитить облачные данные от обновления данных потенциально зараженными устройствами. Дополнительные сведения см. в статье [Как приостановить и возобновить синхронизацию в OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Шаг 3. Удалите вредоносную программу из устройств, которые затрагивают

Запустите полную проверку на наличие вирусов с помощью последних обновлений на всех подозрительных компьютерах и устройствах, чтобы обнаружить и удалить полезные данные, связанные с программой-шантажистом. Не забывайте забашать устройства, которые синхронизируют данные, или на устройстве, на которые сопоставлены сетевые диски (компьютеры и устройства также должны быть сканированы).

Вы можете использовать [Защитник Windows](https://www.microsoft.com/windows/comprehensive-security) или (для клиентов предыдущих версий) [Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)

Альтернативным решением, помогающим устранить замканчивания от вредоносных программ или вредоносных [программ, является средство удаления вредоносных программ (MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Если эти параметры не работают, можно попробовать [автономный Защитник Windows](https://support.microsoft.com/help/17466) или устранить [неполадки с обнаружением и удалением вредоносных программ.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Шаг 4. Восстановление файлов на чистом компьютере или устройстве

После того как вы выполнили предыдущий шаг по удалению полезных данных программы-шантажиста (это предотвратит шифрование или удаление файлов программой-шантажистом), можно [попытаться](https://support.microsoft.com/help/17128) восстановить локальные файлы и папки с помощью журнала файлов в Windows 10, Windows 8.1 или System Protection в Windows 7.

**Примечания**:

- Некоторые программы-штаты также шифруют или удаляют резервные версии, поэтому восстановление файлов с помощью истории файлов или системной защиты невозможна. В этом случае потребуется выполнить резервное копирование на внешних дисках или устройствах, на которые не повлияют выкуп или служба OneDrive, как описано в следующем разделе.

- Если папка синхронизирована с OneDrive и вы не используете последнюю версию Windows, на использование журнала файлов могут нанестись некоторые ограничения.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Шаг 5. Восстановление файлов в OneDrive для бизнеса

Восстановление файлов в OneDrive для бизнеса позволяет восстановить всю среду OneDrive на момент времени в течение последних 30 дней. Дополнительные сведения см. в [статье "Восстановление OneDrive".](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>Шаг 6. Восстановление удаленной электронной почты

В редких случаях, когда программа-служба была удалена из всех сообщений электронной почты, можно восстановить удаленные элементы. Дополнительные сведения см. в статьях:

- [Восстановление удаленных сообщений в почтовом ящике пользователя](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Восстановление удаленных элементов в Outlook для Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Шаг 7. Повторное включение синхронизации Exchange ActiveSync и OneDrive

После очистки компьютеров и устройств и восстановления своих данных вы можете повторно включить синхронизацию ActiveSync и OneDrive, которую вы отключили на [шаге 2.](#step-2-disable-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Шаг 8 (необязательно). Блокировка синхронизации OneDrive для определенных расширений файлов

После восстановления можно запретить клиентам OneDrive для бизнеса синхронизировать типы файлов, на которые повлияло данная выкуп кантортами. Дополнительные сведения см. в [статье Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Сообщает об атаке

### <a name="contact-law-enforcement"></a>органа цепочки контакта

Вам следует обращаться к местным или федеральным органам управления органами. Например, если вы находятесь в США, вы можете связаться с локальным [офисом FBI,](https://www.fbi.gov/contact-us/field) [IC3 или секретным](http://www.ic3.gov/complaint/default.aspx) [секретным секретным секретом.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Отправка отчета на веб-сайт отчетов по стране вашей страны

В веб-сайтах отчетов в области Scam представлены сведения о том, как предотвращать и избегать помех. Они также предоставляют механизмы, о которых сообщается об имеющемся всю нумерацию.

- Австралия: [SCAMwatch](http://www.scamwatch.gov.au/)

- Канада: [канадский антивирусный срез](http://www.antifraudcentre-centreantifraude.ca/)

- Франция: [Агрессия nationale de la sécurité des systémes d'information](http://www.ssi.gouv.fr/)

- Германия: [Bundesamt fêr Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Ирландия: [An Garda Sêochána](http://www.garda.ie/)

- Нью-Зеландия: [пользователи, ладони](http://www.consumeraffairs.govt.nz/scams)

- Соединенное Коэффициент: [Мошенничество](http://www.actionfraud.police.uk/)

- США: [On Guard Online](http://www.onguardonline.gov/)

Если вашей страны нет в списке, попросите спросить местные или федеральные органы управления органами.

### <a name="submit-email-messages-to-microsoft"></a>Отправка сообщений электронной почты в Майкрософт

Можно сообщать о фишинговых сообщениях, содержащих программы-шантажисты, с помощью нескольких способов. Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>См. также

- [Вымоганизация](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Реакция с помощью выручки, плата или не заплатяемая?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro реагирует на атаки программ-шантажистов с прозрачностью](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Обнаружение программ-шумостей и восстановление файлов в OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence Report](https://www.microsoft.com/securityinsights/)

- [Включение и отключение макросов в файлах Office](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Рекомендуемые параметры для безопасности EOP и Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [Стойкое обновление: безопасность следующего поколения в Windows 10 подтверждает устойчивость от программ-шумостей в 2017 г.](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Нет массий, Samas. Что такое модули топунсы программ-](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Блокировка вредоносного ПО маскетрично, чтобы избежать этого](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT июль 2016 г.: кербер-программа](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Три заголовка cerberus как Cerberus-Rans- для Cerber-пользу](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Торговая программа-шантажист по влиянию на (код) Дв-Винки](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
