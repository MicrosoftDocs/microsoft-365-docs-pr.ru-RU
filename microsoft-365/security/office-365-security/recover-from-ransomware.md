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
ms.openlocfilehash: 242a4a2f43bd91d75caeaeaa0488f23a5ba4319d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205765"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Восстановление после атаки вымогателей в Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Даже если вы принимаете все меры предосторожности для защиты организации, вы все равно можете стать жертвой атаки [вымогателей.](/windows/security/threat-protection/intelligence/ransomware-malware) Вымогателей это большой бизнес, и атаки очень сложные.

Действия в этой статье дают вам наилучшие возможности для восстановления данных и остановки внутреннего распространения инфекции. Прежде чем приступать к его созданию, учтите следующие факторы:

- Нет никакой гарантии, что оплата выкупа возвращает доступ к вашим файлам. На самом деле, оплата выкупа может сделать вас мишенью для более вымогателей.

  Если вы уже заплатили, но вы вернулись без использования решения злоумышленника, обратитесь в банк, чтобы узнать, могут ли они заблокировать транзакцию.

  Мы также рекомендуем сообщать об атаке вымогателей в правоохранительные органы, веб-сайты отчетов о мошенничестве и Microsoft, как описано выше в этой статье.

- Важно быстро реагировать на атаку и ее последствия. Чем дольше вы будете ждать, тем меньше вероятность восстановления затронутых данных.

## <a name="step-1-verify-your-backups"></a>Шаг 1. Проверка резервных копий

Если у вас есть автономные резервные копии,  вы, вероятно, сможете восстановить зашифрованные данные после удаления полезной нагрузки вымогателей (вредоносных программ) из среды.

Если у вас нет резервных копий или резервные копии также пострадали от программ-вымогателей, вы можете пропустить этот шаг.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Шаг 2. Отключение синхронизации Exchange ActiveSync и OneDrive

Ключевой момент здесь — остановить распространение шифрования данных программ-вымогателей.

Если вы подозреваете, что электронная почта является объектом шифрования программ-вымогателей, временно отключайте доступ пользователей к почтовым ящикам. Exchange ActiveSync синхронизирует данные между устройствами и почтовыми ящиками Exchange Online.

Чтобы отключить Exchange ActiveSync для почтового ящика, см. в Exchange ActiveSync для пользователей [в Exchange Online.](https://support.microsoft.com/help/2795303)

Чтобы отключить другие типы доступа к почтовому ящику, см.:

- [Включить или отключить MAPI для почтового ящика.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [Включить или отключить доступ к POP3 или IMAP4 для пользователя](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Приочная синхронизация OneDrive поможет защитить облачные данные от обновления потенциально зараженными устройствами. Дополнительные сведения см. в [сайте How to Pause and Resume sync in OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Шаг 3. Удаление вредоносных программ с затронутых устройств

Запустите полное текущее антивирусное сканирование на всех подозрительных компьютерах и устройствах для обнаружения и удаления полезной нагрузки, связанной с программой-вымогателями.

Не забывайте проверять устройства, которые синхронизируют данные, или целевые объекты сетевых дисков.

Вы можете использовать [Защитник Windows](https://www.microsoft.com/windows/comprehensive-security) или (для более старых клиентов) [Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)

Альтернативой, которая также поможет удалить программы-вымогателей или вредоносные программы, является средство удаления вредоносного программного обеспечения [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Если эти параметры не работают, [](https://support.microsoft.com/help/17466) вы можете попробовать Защитник Windows в автономном режиме или устранение неполадок с обнаружением и [удалением вредоносных программ.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Шаг 4. Восстановление файлов на очищенных компьютерах или устройстве

После завершения предыдущего шага по удалению полезной нагрузки вымогателей из среды (что не позволит вымогателям шифровать или удалить файлы), вы можете использовать историю файлов в Windows 10 и Windows 8.1 или System Protection в Windows 7, чтобы попытаться восстановить локальные файлы и папки. [](https://support.microsoft.com/help/17128)

**Примечания**:

- Некоторые программы-вымогательы также шифруют или удаляют резервные версии, поэтому для восстановления файлов нельзя использовать историю файлов или систему защиты. В этом случае необходимо использовать резервные копии на внешних дисках или устройствах, не затронутых программой-вымогателями или OneDrive, как описано в следующем разделе.

- Если папка синхронизирована с OneDrive и вы не используете последнюю версию Windows, могут возникнуть некоторые ограничения с помощью истории файлов.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Шаг 5. Восстановление файлов в OneDrive для бизнеса

Восстановление файлов в OneDrive для бизнеса позволяет восстановить весь OneDrive до предыдущей точки времени в течение последних 30 дней. Дополнительные сведения см. в [сайте Восстановление OneDrive.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>Шаг 6. Восстановление удаленной электронной почты

В редких случаях, когда вымогателей удалили все сообщения электронной почты, вы, вероятно, сможете восстановить удаленные элементы. Дополнительные сведения см. в указанных ниже статьях.

- [Восстановление удаленных сообщений в почтовом ящике пользователя](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Восстановление удаленных элементов в Outlook для Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Шаг 7. Повторное Exchange ActiveSync и синхронизация OneDrive

После очистки компьютеров и устройств и восстановления данных можно повторно включить синхронизацию Exchange ActiveSync OneDrive, отключенную ранее в шаге [2.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Шаг 8 (необязательный): блокировка синхронизации OneDrive для определенных расширений файлов

После восстановления можно запретить клиентам OneDrive для бизнеса синхронизировать типы файлов, затронутые этим программой-вымогателем. Дополнительные сведения см. [в рубрезе Set-SPOTenantSyncClientRestriction.](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Сообщение об атаке

### <a name="contact-law-enforcement"></a>Обратитесь в правоохранительные органы

Обратитесь в местные или федеральные правоохранительные органы. Например, если вы находитесь в США, вы можете обратиться в местное полевой офис [ФБР,](https://www.fbi.gov/contact-us/field) [IC3 или](http://www.ic3.gov/complaint/default.aspx) [секретную службу.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Отправка отчета на веб-сайт отчетности о мошенничестве в вашей стране

Веб-сайты отчетов о мошенничестве предоставляют сведения о том, как предотвратить и избежать мошенничества. Они также предоставляют механизмы для отчета, если вы стали жертвой мошенников.

- Австралия: [SCAMwatch](http://www.scamwatch.gov.au/)

- Канада: [Канадский центр по борьбе с мошенничеством](http://www.antifraudcentre-centreantifraude.ca/)

- Франция: [Agence Nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Германия: [Bundesamt für Sicherheit в der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Ирландия: [Garda Síochána](http://www.garda.ie/)

- Новая Зеландия: [мошенничество с потребительскими делами](http://www.consumeraffairs.govt.nz/scams)

- Великобритания: [мошенничество с действиями](http://www.actionfraud.police.uk/)

- СОЕДИНЕННЫЕ Штаты: [On Guard Online](http://www.onguardonline.gov/)

Если ваша страна не указана, попросите местные или федеральные правоохранительные органы.

### <a name="submit-email-messages-to-microsoft"></a>Отправка сообщений электронной почты в Корпорацию Майкрософт

Вы можете сообщать о фишинговых сообщениях, содержащих вымогателей, с помощью одного из нескольких методов. Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>См. также

- [Вымогателей](/windows/security/threat-protection/intelligence/ransomware-malware)

- [Ответ вымогателей — платить или не платить?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro реагирует на атаки вымогателей с прозрачностью](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Обнаружение и восстановление файлов в OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Отчет об аналитике безопасности Майкрософт](https://www.microsoft.com/securityinsights/)

- [Включить или отключить макрос в файлах Office](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Рекомендуемые параметры безопасности EOP и Microsoft Defender для Office 365](recommended-settings-for-eop-and-office365.md)

- [Достойное обновление: безопасность следующего поколения в Windows 10 доказала устойчивость к вспышкам вымогателей в 2017 г.](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Нет мас, Samas: Что в modus operandi этого вымогателя?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky malware, lucky to avoid it](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT July 2016: Cerber ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Три главы вируса-вымогателя Cerber, похожего на Cerber](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh ransomware influenced by the () Da Vinci code](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)