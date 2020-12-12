---
title: Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться использовать правила потока почты (также известные как правила транспорта) для получения копий сообщений, которые пользователи сообщают корпорации Майкрософт.
ms.openlocfilehash: 0f3046c9d1962366ffd75353347b6cf7b72afd14
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659860"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


В организациях Microsoft 365 с почтовыми ящиками в Организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online существует несколько способов передачи сообщений в корпорацию Майкрософт для анализа, как описано в отчете о сообщениях и файлах в [корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)

Можно создать правило потока почты (также известное как правило транспорта), которое ищет сообщения, которые пользователи сообщают корпорации Майкрософт, и настроить получателей копии этих сообщений.

Правило потока обработки почты можно создать в Центре администрирования Exchange (EAC) и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Для этого необходимы соответствующие разрешения в Exchange Online или Exchange Online Protection. В частности, необходима  роль правил транспорта, назначенная по умолчанию группам ролей "Управление  организацией", "Управление соответствием требованиям" **(глобальным** администраторам) и "Управление записями".

  Дополнительную информацию см. в следующих статьях:

  - [Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Разрешения в автономном EOP](feature-permissions-in-eop.md)
  - [Изменение списка участников в группах ролей с помощью EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Чтобы открыть Центр администрирования Exchange в Exchange Online, см. центр [администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Чтобы открыть Центр администрирования Exchange в режиме автономных EOP, см. центр администрирования [Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о правилах потока почты в Exchange Online и автономных EOP см. в следующих темах:
  - [Правила потока обработки почты (правила транспорта) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Условия и исключения правил потока почты (предикаты) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Действия правил потока почты в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Создание правила потока почты для получения копий сообщений с помощью EAC

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Нажмите **значок** ![ "Добавить", а затем выберите ](../../media/ITPro-EAC-AddIcon.png) **"Создать новое правило".**

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Name**: Enter a unique, descriptive name for the rule. Например, "Сообщения в ск", которые были подались в корпорацию Майкрософт.

   - Нажмите кнопку **Дополнительные параметры**.

   - Примените это правило, если **:** **Выберите** адрес получателя включает любое из этих слов: в отображемом диалоговом окке "Укажите слова или фразы" введите одно из следующих значений, нажмите кнопку "Добавить значок добавления" и повторите это, пока не введите все \>    ![ ](../../media/ITPro-EAC-AddIcon.png) значения.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Чтобы изменить запись, выберите  ее и нажмите значок ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования. Чтобы удалить запись, выберите ее и нажмите **значок "Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) удалить".

     После этого нажмите кнопку **ОК**.

   - **Сделайте следующее:** выберите **"Добавить получателей** \> **в поле "СК".** В отобратом диалоговом окте найдите и выберите получателей, которые нужно добавить. После этого нажмите кнопку **ОК**.

4. Можно выбрать дополнительные параметры для аудита правила, проверки правила, активации правила в течение определенного периода времени и других параметров. Мы рекомендуем тестировать правило перед его выполнением.

5. Выполнив необходимые действия, нажмите кнопку **Сохранить**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Создание правила потока почты для получения копий сообщений с помощью PowerShell

В этом примере создается новое правило потока почты с именем Bcc Messages Reported to Microsoft, которое ищет сообщения электронной почты, которые сообщаются корпорации Майкрософт с помощью методов, описанных в этой статье, и добавляет пользователей laura@contoso.com и julia@contoso.com в качестве получателей ск.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы настроили правила потока почты для получения копий сообщений, сделайте следующее:

- В EAC перейдите к **правилу потока** обработки почты, выберите правило, щелкните значок редактирования и проверьте \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) параметры.

- В PowerShell запустите следующую команду, чтобы проверить параметры:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Отправьте тестовые сообщения на один из адресов электронной почты отчетов и проверьте результаты.
