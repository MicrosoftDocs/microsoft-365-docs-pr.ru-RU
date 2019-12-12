---
title: Сведения об устранении неполадок и поддержке
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
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: В этом разделе описаны действия по устранению неполадок для пользователей и администраторов, а также приведены сведения о том, как обратиться за помощью в службу технической поддержки.
ms.openlocfilehash: a6a4b94db3e34442d326942641b10db15d104d71
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971627"
---
# <a name="troubleshooting-and-support-information"></a>Сведения об устранении неполадок и поддержке

В этом разделе описаны действия по устранению неполадок для пользователей и администраторов, а также приведены сведения о том, как обратиться за помощью в службу технической поддержки.

## <a name="troubleshooting-for-users"></a>Устранение неполадок пользователями

Иногда могут возникнуть проблемы с Microsoft Outlook после добавления надстройки создания отчетов о нежелательной почте. Ниже перечислены возможные проблемы, а также советы по их устранению.

- После нажатия кнопки **Сообщить о нежелательной почте** ничего не происходит.

- Служба Outlook не отвечает на запросы после вашего выбора сообщения электронной почты.

- Вследствие отказа в доставке не удается доставить нежелательные сообщения, в отношении которых отправлен отчет.

Чтобы устранить эту проблему, выполните указанные ниже действия.

1. Закройте и перезапустите Outlook.

2. Убедитесь, что вы можете создать и отправить проверочное сообщение. Для этого можно отправить проверочное сообщение на другую принадлежащую вам учетную запись электронной почты, а затем проверить, получено ли данное сообщение.

Если проблема не исчезнет, обратитесь к администратору.

> [!TIP]
> Нежелательные сообщения можно также отправлять непосредственно корпорации Майкрософт по адресу электронной почты [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com). Отчеты о ложном срабатывании в отношении сообщений можно отправлять по адресу [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com). Подробнее см. в разделе [Отправка обычных, нежелательных и фишинговых сообщений в корпорацию Майкрософт для анализа](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="troubleshooting-for-administrators"></a>Устранение неполадок администраторами

Как администратор, вы можете столкнуться с проблемами с пользователями, использующими надстройку создания отчетов о нежелательной почте для Outlook. Ниже представлены некоторые рекомендации по разрешению возможных проблем.

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>Проблема: сообщение об ошибке с вопросом о том, что пользователям необходимо постоянно обращаться к системному администратору

1. Установите для следующего раздела реестра значение Verbose.

   - **32 разрядная версия Outlook, установленная в 32 разрядной операционной системе**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **32 разрядная версия Outlook, установленная в 64 разрядной операционной системе**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **64 разрядная версия Outlook (всегда устанавливается в 64-разрядной операционной системе)**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. Перезапустите Outlook и попросите пользователей отправить отчет о сообщении об ошибке.

3. Соберите сведения журнала в следующем расположении.

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Обратитесь в службу технической поддержки Exchange Online Protection и предоставьте ее сотрудникам сведения журнала.

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>Проблема: пользователи не получают подтверждения при отсылке сообщения электронной почты как нежелательного и теперь хотят их восстановить.

1. Задайте для следующего раздела реестра значение "true": `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`.

2. Перезапустите Outlook.

## <a name="support-information"></a>Сведения о поддержке

Если вам нужна помощь по установке, настройке или удалению надстройки, обратитесь в службу технической поддержки, используя ссылку создать запрос на обслуживание на странице Поддержка в центре администрирования Microsoft 365. Дополнительные параметры, включая отправку запроса на обслуживание через телефонную связь и параметры самостоятельной поддержки, приведены в статье [Справка и поддержка для EOP](help-and-support-for-eop.md).

## <a name="for-more-information"></a>Дополнительные сведения

[Включение надстройки Report Message](enable-the-report-message-add-in.md)

[Отправка отчетов о нежелательных сообщениях корпорации Майкрософт](report-junk-email-messages-to-microsoft.md)
