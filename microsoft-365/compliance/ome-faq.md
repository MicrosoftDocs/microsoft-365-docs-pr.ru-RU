---
title: FaQ шифрования сообщений
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Возникает вопрос о том, как работают новые возможности защиты сообщений? Здесь вы можете получить ответ.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdfcc2e7454b1243016754ba32dcc2622b876672
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927757"
---
# <a name="message-encryption-faq"></a>FaQ шифрования сообщений

Возникает вопрос о том, как работают новые возможности защиты сообщений? Здесь вы можете получить ответ. Кроме того, посмотрите на часто задамые вопросы о защите данных в [Azure Information Protection](/information-protection/get-started/faqs-rms) для ответов на вопросы о службе защиты данных Azure Rights Management в Azure Information Protection.

## <a name="what-is-office-365-message-encryption-ome"></a>Что такое шифрование сообщений Office 365 (OME)?

OME объединяет возможности шифрования электронной почты и управления правами. Возможности управления правами на питание от Azure Information Protection.

## <a name="who-can-use-ome"></a>Кто может использовать OME?

Новые возможности для OME можно использовать при следующих условиях:
  
- Если вы никогда не устанавливали OME или IRM для Exchange Online в Office 365.

- Если вы настроили OME и IRM, вы можете использовать эти действия, если используете службу управления правами Azure из Azure Information Protection.

- Если вы используете Exchange Online со службой управления правами Active Directory (AD RMS), вы не можете сразу включить эти новые возможности. Вместо этого сначала необходимо перенести [AD RMS в Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) После завершения миграции можно успешно настроить OME.

  Если вы решите продолжать использовать локальное AD RMS с Exchange Online вместо перехода в Azure Information Protection, вы не сможете использовать эти новые возможности.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>Какие подписки необходимы для использования новых возможностей OME?

Чтобы использовать новые возможности OME, вам потребуется один из следующих планов:
  
- Шифрование сообщений Office 365 предлагается в рамках Office 365 Enterprise E3 и E5, Microsoft Enterprise E3 и E5, Microsoft 365 Business Premium, Office 365 A1, A3 и A5 и Office 365 government G3 и G5. Клиенты не нуждаются в дополнительных лицензиях, чтобы получить новые возможности защиты с помощью Azure Information Protection.

- Вы также можете добавить План 1 по защите информации Azure к следующим планам получения новых возможностей шифрования сообщений Office 365: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard или Office 365 Enterprise E1.

- Каждый пользователь, пользующийся шифрованием сообщений Office 365, должен иметь лицензию, чтобы она была охвачена этой функцией.

- Полный список см. в описаниях [служб Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) для шифрования сообщений Office 365.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Могу ли я использовать Exchange Online с помощью собственного ключа (BYOK) в Azure Information Protection?

Да! Корпорация Майкрософт рекомендует выполнить действия по настройкам BYOK перед настройками OME.
  
Дополнительные сведения о BYOK см. в [сведениях Planning and implementing your Azure Information Protection tenant key.](/information-protection/plan-design/plan-implement-tenant-key)
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Изменит ли OME и BYOK с Azure Information Protection подход Корпорации Майкрософт к сторонним запросам данных, таким как повестки?

Нет. OME и возможность предоставления и управления собственными ключами шифрования, называемыми BYOK, из Azure Information Protection не были предназначены для ответа на запросы правоохранительных органов. OME с помощью BYOK для Azure Information Protection была разработана для клиентов, ориентированных на соответствие требованиям. Корпорация Майкрософт очень серьезно относится к сторонним запросам на данные клиентов. Как поставщик облачных служб мы всегда выступаем за конфиденциальность данных клиентов. В случае, если мы получаем повестку, мы всегда стараемся перенаправить сторонную сторону клиенту для получения информации. (Ознакомьтесь с блогом Брэда Смита: Защита данных клиентов [от правительственных снупов).](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) Мы периодически публикуем подробные сведения о получаемом запросе. Дополнительные сведения о сторонних запросах [](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) на данные см. в ответе на запросы правительства и правоохранительных органов о доступе к данным клиентов в Центре доверия Майкрософт. Также см. в руб. "Раскрытие данных клиентов" в [термине Online Services Terms (OST).](https://www.microsoft.com/Licensing/product-licensing/products.aspx)
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>Как эта функция связана с устаревшими функциями шифрования сообщений Office 365 (OME) и управления правами на информацию (IRM)?

Новые возможности шифрования сообщений Office 365 являются эволюцией существующих решений IRM и устаревших OME. В следующей таблице приводится более подробная информация.
  
**Сравнение устаревших возможностей OME, IRM и новых OME**

| Возможность | Предыдущие версии OME | IRM | Новые возможности OME |
|:-----|:-----|:-----|:-----|
|**Отправка зашифрованной электронной почты**|Только с помощью правил потока почты Exchange|End-user initiated from Outlook for Windows, Outlook for Mac, or Outlook on the web; или с помощью правил потока почты Exchange|End-user initiated from Outlook for Windows, Outlook for Mac, or Outlook on the web; или с помощью правил потока почты|
|**Управление правами на доступ**|-|Не перенадвигать параметры и настраиваемые шаблоны|Не перенадвигать параметр, только шифрование, по умолчанию и настраиваемые шаблоны|
|**Поддерживаемый тип получателя**|Только внешние получатели|Только внутренние получатели|Внутренние и внешние получатели|
|**Опыт для получателя**|Внешние получатели получили HTML-сообщение, которое они скачали и открыли в браузере или скачали мобильное приложение.|Внутренние получатели получали зашифрованную электронную почту только в Outlook для Windows, Outlook для Mac и Outlook в Интернете.|Внутренние и внешние получатели получают электронную почту в Outlook для Windows, Outlook для Mac, Outlook в Интернете, Outlook для Android и Outlook для iOS или через веб-портал, независимо от того, находятся ли они в одной организации или в любой организации. Портал OME не требует отдельной загрузки.|
|**Поддержка собственных ключевых элементов**|Недоступно|Недоступно| Поддержка BYOK|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>Как включить новые возможности OME для организации?

Подробнее о новых возможностях шифрования сообщений [Office 365](set-up-new-message-encryption-capabilities.md)см. в сообщении.
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>Будет ли обесценена предыдущая версия OME?

Вы по-прежнему можете использовать предыдущую версию OME, она не будет обесценив в это время. Однако мы настоятельно рекомендуем организациям использовать новое и улучшенное решение OME. Клиенты, которые еще не развернули OME, не могут настроить новое развертывание предыдущей версии OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Моя организация использует управление правами Active Directory, могу ли я использовать эти функции?

Нет. Если вы используете Exchange Online со службой управления правами Active Directory (AD RMS), вы не можете сразу включить эти новые возможности. Вместо этого сначала необходимо перенести [AD RMS в Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>В моей организации имеется гибридное развертывание Exchange. Можно ли использовать эту функцию?

Локально пользователи могут отправлять зашифрованную почту с помощью правил потока почты Exchange Online. Для этого необходимо отправить электронную почту через Exchange Online. Дополнительные сведения см. в части 2. Настройка почты для потока с сервера электронной почты [в Microsoft 365.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>Какой клиент электронной почты необходимо использовать для создания зашифрованного сообщения OME? Какие приложения поддерживаются для отправки защищенных сообщений?

Можно создавать защищенные сообщения из Outlook 2016, Outlook 2013 для Windows и Mac и Outlook в Интернете. Дополнительные сведения об отправке зашифрованных сообщений см. в сообщении [Send, view и reply to encrypted messages in Outlook for PC.](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>Какие клиенты электронной почты могут читать и отвечать на защищенные сообщения?

Пользователи Microsoft 365 могут читать и отвечать на них из Outlook для Windows и Mac (2013 и 2016), Outlook в Интернете и Outlook mobile (Android и iOS). Вы также можете использовать собственный почтовый клиент iOS, если это позволяет ваша организация. Если вы не пользователь Microsoft 365, вы можете читать и отвечать на зашифрованные сообщения в Интернете через веб-браузер.

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>Какие клиенты электронной почты поддерживают защищенные только шифрованием сообщения?

Пользователи Microsoft 365 могут использовать Outlook для pc-версий 2019 и Microsoft 365 для создания почты, защищенной только для шифрования.  Это означает, что сообщения, которые применяются только для шифрования, можно читать непосредственно в Outlook в Интернете, в Outlook для iOS и Android, а теперь Outlook для PC версий 2019 и Microsoft 365.

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>Существует ли ограничение размера сообщений, которые можно отправлять с помощью OME?

Да. Максимальный размер сообщения, который можно отправить с помощью OME, включая вложения, — 25 МБ. Дополнительные сведения см. в [тексте Ограничения сообщения.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>Какие типы файлов поддерживаются в качестве вложений в защищенных сообщениях электронной почты? Наследуют ли вложения политики защиты, связанные с защищенными электронными письмами?

Вы можете прикрепить любой тип файла к защищенной почте. За одним исключением политики защиты применяются только к форматам файлов, указанным в типах Файлов, поддерживаемых [клиентом Azure Information Protection.](/information-protection/rms-client/client-admin-guide-file-types) OME не поддерживает версии 97-2003 следующих программ Office: Word (.doc), Excel (.xls) и PowerPoint (.ppt).

Если поддерживается формат файла, например файл Word, Excel или PowerPoint, файл всегда защищен, даже после загрузки вложения получателем. Например, скажите, что вложение защищено do Not Forward. Исходный получатель скачивает файл, создает сообщение новому получателю и прикрепит файл. Когда новый получатель получит файл, получатель не сможет открыть защищенный файл.
  
## <a name="are-pdf-file-attachments-supported"></a>Поддерживаются ли вложения pdf-файлов?

Краткий ответ — да! Шифрование PDF позволяет защищать конфиденциальные документы PDF с помощью безопасной связи или безопасной совместной работы. При отправке электронной почты служба Office 365 шифрует вложения pdf-файлов, а не клиент Outlook.

Для Outlook в Интернете, Outlook для iOS и Outlook для Android можно шифровать отправимые PDF без каких-либо дополнительных действий. Эти клиенты поддерживают шифрование PDF.

Рабочий стол Outlook не поддерживает шифрование вложений pdf-файлов. Вместо этого необходимо настроить правила потока почты Exchange или DLP, чтобы сначала применить шифрование к вложениям PDF. При отправке почты из Outlook Desktop с вложением PDF клиент сначала отправляет сообщение с вложением в службу. Когда служба получает файл, служба применяет защиту OME политики предотвращения потери данных (DLP) или правила потока почты в Exchange Online. Далее Exchange Online отправляет сообщение с защищенным файлом PDF-вложения.

Чтобы включить шифрование для вложений PDF, запустите следующую команду в [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

Шифрование PDF позволяет защищать конфиденциальные документы PDF с помощью безопасной связи или безопасной совместной работы. Для всех клиентов Outlook сообщения и незащищенные вложения PDF наследуют защиту OME политики предотвращения потери данных (DLP) или правила потока почты в Exchange Online. Кроме того, если Outlook веб-пользователя прикрепит незащищенный документ PDF и применяет защиту к сообщению, сообщение наследует защиту сообщения. Пользователи могут открывать зашифрованные вложения только в приложениях, поддерживаюх защищенные PDF (например, портал OME и viewer azure information Protection).

> [!IMPORTANT]
> Клиент рабочего стола Outlook не поддерживает шифрование PDF.

## <a name="are-onedrive-for-business-attachments-supported"></a>Поддерживаются ли вложения OneDrive для бизнеса?

Not yet. Вложения OneDrive для бизнеса не поддерживаются, и конечные пользователи не могут шифровать почту, содержаную облачную вложение OneDrive для бизнеса.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>Какие клиенты электронной почты поддерживают предварительный просмотр зашифрованных вложений в защищенных электронных письмах?

Когда вложения защищены защищенной почтой, клиенты Outlook предоставляют возможность предварительного просмотра документа напрямую. Outlook поддерживает предварительный просмотр документов Office (docx, xlsx, pptx, doc, xls, ppt). Outlook в Интернете поддерживает предварительный просмотр документов Office (docx, xlsx, pptx) и PDF.  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>Какие клиенты электронной почты поддерживают отзыв защищенных сообщений электронной почты?

Outlook в Интернете поддерживает отзыв защищенной почты.  Узнайте, [как отоискить зашифрованное сообщение, отправленное](revoke-ome-encrypted-mail.md#how-to-revoke-an-encrypted-message-that-you-sent) для подробных сведений.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>Можно ли автоматически шифровать сообщения путем настройки политик?

Да. Используйте правила потока почты в Exchange Online, чтобы автоматически шифровать сообщение на основе определенных условий. Например, можно создавать политики, основанные на ID получателя, домене получателя или контенте в теле или субъекте сообщения. См. определение правил потока почты для шифрования сообщений электронной [почты в Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>Могу ли я автоматически удалить шифрование входящих и исходящая почты?

Администраторы могут настроить правило потока почты, чтобы удалить шифрование исходяющих сообщений. Вы не можете настроить правило для удаления шифрования для входящих сообщений почты.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>Могу ли я автоматически шифровать сообщения путем настройки политик в центре защиты от потери данных (DLP) через &amp; Центр соответствия требованиям безопасности?

Да! Правила потока почты можно настроить в Exchange Online или с помощью DLP в Центре соответствия &amp; требованиям безопасности.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>Можно ли настроить зашифрованные сообщения с помощью фирменого бренда?

Да! Сведения о настройке сообщений электронной почты и портале OME см. в добавлении бренда организации к зашифрованным сообщениям. См. [добавление бренда организации в зашифрованные сообщения.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>Существуют ли какие-либо возможности или сведения об отчетах для зашифрованных сообщений электронной почты?

В Центре безопасности и соответствия требованиям есть отчет о шифровании. Просмотр [отчетов о безопасности электронной почты](../security/office-365-security/view-email-security-reports.md)в Центре & безопасности.
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>Можно ли использовать шифрование сообщений с такими функциями соответствия требованиям, как eDiscovery?

Да. Все зашифрованные сообщения электронной почты можно обнаружить с помощью функций соответствия требованиям Microsoft 365.

## <a name="can-i-remove-encryption-from-email"></a>Можно ли удалить шифрование из электронной почты?

Администраторы могут настроить правило потока почты для удаления шифрования. Вы не можете удалить шифрование с помощью правила потока почты из почты, применяемого другой организацией, если только почта не завихряется с помощью защиты только для шифрования.

## <a name="is-delegated-access-supported"></a>Поддерживается ли делегированная поддержка доступа?

Сейчас не работает.

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>Могу ли я отправлять в виде общего почтового ящика и шифровать сообщения электронной почты?

Когда кто-то отправляет сообщение электронной почты, которое соответствует правилу потока почты шифрования, оно шифруется перед отправкой.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>Можно ли открывать зашифрованные сообщения, отправленные в общий почтовый ящик?

Да! Зашифрованные сообщения поддерживаются для общего почтового ящика.

- Пользователи могут открывать защищенные почты в общем почтовом ящике, где общий почтовый ящик получал защищенную почту в составе группы рассылки.

- Пользователи могут просматривать вложения, которые наследуют защиту от электронной почты при использовании Outlook для Windows, Outlook для Mac и Outlook в Интернете.

В следующей таблице перечислены поддерживаемые клиенты для общих почтовых ящиков.

| Платформа | Чтение почты | Просмотр вложений электронной почты |
|----------|-----------|------------------------|
| Outlook в Интернете | Да | Да                |
| Outlook для Windows| Да | Да                |
| Outlook для Mac    | Да | Да                |
| Outlook для Android| Да | Нет                 |
| Outlook для iOS    | Да | Нет                 |
|

В настоящее время существует два известных ограничения:

- Нельзя открывать вложения к электронным письмам, которые вы получаете на мобильных устройствах с помощью мобильного телефона Outlook.

- Мы не поддерживаем назначение через группу безопасности с включенной электронной почтой. Мы поддерживаем доступ, предоставляемый только путем прямого назначения пользователя в общий почтовый ящик, и автомагистраля включена для Exchange Online. Автомаппирование включено по умолчанию для Exchange Online.

**Назначение пользователя в общий почтовый ящик**

1. [Подключение к Exchange Online с помощью удаленной powerShell](/powershell/exchange/connect-to-exchange-online-powershell?v=exchg.150).aspx).

2. Запустите Add-MailboxPermission с параметром Automapping. В этом примере Ayla предоставляет разрешения на полный доступ к почтовому ящику поддержки.

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```

## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>Можно ли открывать зашифрованные сообщения, отправленные в почтовый ящик другого пользователя с помощью Fullaccess?

Пользователи могут открывать зашифрованные сообщения до тех пор, пока им предоставляется прямой доступ и включена автомайка. Доступ запрещен, если доступ предоставляется через группу безопасности с поддержкой электронной почты.

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>Что делать, если после запроса не получается разовое код пропуска?

Сначала проверьте папку нежелательной почты или нежелательной почты в клиенте электронной почты. Параметры DKIM и DMARC для вашей организации могут привести к тому, что эти сообщения будут фильтроваться как спам.

Затем проверьте карантин в Центре & безопасности. Часто сообщения, содержащие разовое код пропуска, особенно первые, которые получает организация, заканчиваются карантином.