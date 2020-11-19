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
ms.openlocfilehash: a1369e64821902e3c2a3061acd1bbebeeb6c85ac
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357101"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Восстановление при атаке программой "шантажистом" в Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Даже если вы предпримете все меры предосторожности для защиты вашей организации, вы по-прежнему можете жертвой атакой от атаки с помощью [атаки](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) с помощью Эта атака является большим предприятием, а атаки очень сложны.

Действия, описанные в этой статье, помогут вам в восстановлении данных и остановке внутреннего распространения заражения. Прежде чем приступать к его созданию, учтите следующие факторы:

- Нет гарантии, что оплата Рансом возвратит доступ к вашим файлам. На самом деле, оплата Рансом может сделать целевой для дополнительной атаки.

  Если вы уже оплачиваете, но вы восстановили ее без использования вредоносного средства, обратитесь в банк, чтобы узнать, можно ли заблокировать эту транзакцию.

  Кроме того, рекомендуется сообщать об атаке с помощью средства "мошенническое использование" для правоохранительных и мошеннических веб-сайтов, а также Майкрософт, как описано далее в этой статье.

- Очень важно быстро реагировать на атаку и ее последствия. Чем больше время ожидания, тем менее вероятно, что вы можете восстановить затронутые данные.

## <a name="step-1-verify-your-backups"></a>Шаг 1: Проверка резервных копий

При наличии автономных резервных копий вы можете восстановить зашифрованные данные **после** удаления из вашей среды полезных данных программы-шантажистом.

Если вы не обладаете резервными копиями, а также в том случае, если вы также затронули ее, вы можете пропустить этот шаг.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Шаг 2: Отключение синхронизации Exchange ActiveSync и OneDrive

Ключевой момент здесь заключается в остановке распространения шифрования данных программой-шантажистом.

Если вы подозреваете электронную почту в качестве целевого объекта для шифрования с помощью атаки, временно отключите доступ пользователей к почтовым ящикам. Exchange ActiveSync синхронизирует данные между устройствами и почтовыми ящиками Exchange Online.

Чтобы отключить Exchange ActiveSync для почтового ящика, Узнайте, [как отключить Exchange ActiveSync для пользователей в Exchange Online](https://support.microsoft.com/help/2795303).

Чтобы отключить другие типы доступа к почтовому ящику, ознакомьтесь со статьей:

- [Включение или отключение MAPI для почтового ящика](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Включение или отключение доступа по протоколу POP3 или IMAP4 для пользователя](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Приостановка синхронизации OneDrive поможет защитить облачные данные от обновления потенциально инфицированных устройств. Для получения дополнительных сведений Узнайте, [как приостановить и возобновить синхронизацию в OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Шаг 3: Удаление вредоносных программ с затронутых устройств

Выполнение полной и текущей антивирусной проверки на всех подозреваемых компьютерах и устройствах для обнаружения и удаления полезных данных, связанных с программой.

Не забудьте проверить устройства, являющиеся синхронизацией данных, или целевые объекты подключенных сетевых дисков.

В [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)можно использовать [Защитник Windows](https://www.microsoft.com/windows/comprehensive-security) или (для старых клиентов).

Кроме того, вы можете удалить программу-шантажистом или вредоносную программу с помощью [средства удаления вредоносных программ (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Если эти параметры не работают, можно попробовать [Отключить Защитник Windows](https://support.microsoft.com/help/17466) или [устранить неполадки, связанные с обнаружением и удалением вредоносных программ](https://support.microsoft.com/help/4466982).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Шаг 4: восстановление файлов на очищенном компьютере или устройстве

После выполнения предыдущего действия для удаления полезных данных программой-шантажистом из среды (что предотвратит шифрование и удаление файлов программой-шантажистом) можно использовать [историю файлов](https://support.microsoft.com/help/17128) в Windows 10 и Windows 8,1 или системы защиты системы в Windows 7, чтобы попытаться восстановить локальные файлы и папки.

**Примечания**:

- Некоторые средства защиты от вирусов также шифруют и удаляют версии резервных копий, поэтому для восстановления файлов невозможно использовать историю файлов или систему защиты системы. В этом случае вам потребуется использовать резервные копии на внешних дисках или устройствах, которые не были затронуты программой "шантажистом" или OneDrive, как описано в следующем разделе.

- Если папка синхронизирована с OneDrive и вы не используете последнюю версию Windows, то некоторые ограничения могут быть связаны с использованием истории файлов.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Шаг 5: восстановление файлов в OneDrive для бизнеса

Восстановление файлов в OneDrive для бизнеса позволяет восстановить в течение последних 30 дней весь OneDrive до предыдущего момента времени. Дополнительные сведения см. в статье [Восстановление OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Шаг 6: восстановление удаленной почты

В редких случаях, когда средство записи в систему удалило всю электронную почту, возможно, вы восстановите удаленные элементы. Дополнительные сведения см. в указанных ниже статьях.

- [Восстановление удаленных сообщений в почтовом ящике пользователя](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Восстановление удаленных элементов в Outlook для Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Шаг 7: повторное включение синхронизации Exchange ActiveSync и OneDrive

После очистки компьютеров и устройств и восстановления данных можно повторно включить службу Exchange ActiveSync и синхронизацию OneDrive, которая была отключена на [шаге 2](#step-2-disable-exchange-activesync-and-onedrive-sync).

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Шаг 8 (необязательно): блокировка синхронизации OneDrive для определенных расширений файлов

После восстановления вы можете запретить клиентам OneDrive для бизнеса синхронизировать типы файлов, затрагиваемые этой программой-шантажистом. Для получения дополнительных сведений см. [Set – SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Сообщить об атаке

### <a name="contact-law-enforcement"></a>Принудительное применение правоохранительных лиц

Вы должны обратиться к местным или федеральным правоохранительным ведомствам. Например, если вы используете США, вы можете связаться с [местным полем Office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) или [секретной службой](http://www.secretservice.gov/)ФБР.

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Отправка отчета на веб-сайт мошенничества для отчетности в вашей стране

Веб-сайты для создания отчетов о мошенничестве содержат сведения о том, как предотвратить и избегать мошенничества. Кроме того, они предоставляют механизмы для отчета, если вы стали жертвой мошенничества.

- Австралия: [скамватч](http://www.scamwatch.gov.au/)

- Канада: [канадский (Канада) центр защиты от мошенничества](http://www.antifraudcentre-centreantifraude.ca/)

- Франция: [аженце National сéкуритé des систèмес д'информатион](http://www.ssi.gouv.fr/)

- Германия: [бундесамт фüр сичерхеит в Der информатионстечник](https://www.bsi.bund.de/DE/Home/home_node.html)

- Ирландия: [Гарда сíочáна](http://www.garda.ie/)

- Новая Зеландия: [мошенничество по охране потребителей](http://www.consumeraffairs.govt.nz/scams)

- Великобритания: [действие мошенничество](http://www.actionfraud.police.uk/)

- США: [в службе безопасности Online](http://www.onguardonline.gov/)

Если ваша страна отсутствует в списке, обратитесь к местным или федеральным правоохранительным ведомствам.

### <a name="submit-email-messages-to-microsoft"></a>Отправка сообщений электронной почты в корпорацию Майкрософт

Вы можете сообщить о phishing-сообщениях, которые содержат средства для атаки, одним из нескольких способов. Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>См. также

- [Программой](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Отклик от атаки программой-шантажистом — оплачивается или не оплачивается?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Норск Хидро реагирует на атаку с помощью команды "атаку" с прозрачностью](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Обнаружение и восстановление файлов в OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Отчет Microsoft Security Intelligence](https://www.microsoft.com/securityinsights/)

- [Включение и отключение макросов в файлах Office](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Рекомендуемые параметры для EOP и Microsoft Defender для Office 365 Security](recommended-settings-for-eop-and-office365-atp.md)

- [Обновление стоит: Следующая безопасность поколения для Windows 10 удостоверяется в устойчивости от эпидемий с помощью программы "размыкатель" в 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Нет МАС, Самас: что находится в этой модусе для атаки, операнди?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Блокировка вредоносных программ, счастливого, чтобы избежать](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT — Июль 2016: Цербер](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Три головки Церберус, похожего на Цербер.](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Тролдеш-шантажистом, на которые влияет код Da ВинЦи](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
