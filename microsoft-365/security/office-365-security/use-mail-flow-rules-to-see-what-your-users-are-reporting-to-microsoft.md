---
title: Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать правила поток обработки почты (также называемые правилами транспорта), чтобы получать копии сообщений, отправляемых пользователями в корпорацию Майкрософт.
ms.openlocfilehash: d50a0f02dd3d65b8576261fc2332aba86d55df56
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616794"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты

В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователи могут отчитываться о сообщениях в Майкрософт для анализа, как описано в [статье Reports and Files to Microsoft](report-junk-email-messages-to-microsoft.md).

Вы можете создать правило для процесса обработки почты (также называемое правилом транспорта), которое будет искать сообщения, отправляемые пользователями в корпорацию Майкрософт, и настраивать получателей скрытой копии для получения копий этих сообщений.

Вы можете создать правило для почтового процесса в центре администрирования Exchange и PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Прежде чем выполнять эти процедуры, необходимо назначить разрешения в Exchange Online или EOP. В частности, необходимо назначить роль " **правила транспорта** ", которая назначается для ролей управления **организацией**, **управления соответствием требованиям**и управления **записями** по умолчанию. Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Чтобы открыть центр администрирования Exchange, ознакомьтесь со статьей [центр администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) или [центр администрирования Exchange в автономной EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о правилах обработки почтового ящика в Exchange Online и отдельном EOP содержатся в следующих разделах:

  - [Правила потока обработки почты (правила транспорта) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения правила для обработки почтового процесса (предикаты) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правил обработки почты в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Использование центра администрирования Exchange для создания правила обработки почтового ящика для получения копий отчетных сообщений

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Щелкните **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) , а затем выберите **создать новое правило**.

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Name**: введите уникальное описательное имя правила. Например, сообщения скрытой копии в корпорацию Майкрософт.

   - Нажмите кнопку **Дополнительные параметры**.

   - **Применять это правило, если**: выберите адрес **получателя** \> **содержит любое из этих слов**: в появившемся диалоговом окне **Укажите слова или фразы** введите одно из следующих значений, нажмите **Добавить** ![ значок "Добавить" ](../../media/ITPro-EAC-AddIcon.png) и повторяйте до тех пор, пока не ввели все значения.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Чтобы изменить запись, выберите ее и нажмите кнопку **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) . Чтобы удалить запись, выберите ее и нажмите кнопку **Удалить** ![ значок "Удалить" ](../../media/ITPro-EAC-DeleteIcon.png) .

     После этого нажмите кнопку **ОК**.

   - **Выполните следующие**действия: выберите **добавить получателей** \> **в поле "СК**". В появившемся диалоговом окне найдите и выберите получателей, которых вы хотите добавить. После этого нажмите кнопку **ОК**.

4. Вы можете выбрать дополнительные параметры для аудита правила, проверки правила, активации правила в течение определенного периода времени и других параметров. Рекомендуем проверить правило перед его применением.

5. Выполнив необходимые действия, нажмите кнопку **Сохранить**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Создание правила для обработки почтового сообщения для получения копий отчетов с помощью PowerShell

В этом примере создается правило для почтового процесса с именем BCC messages, отправленное в корпорацию Майкрософт, которое ищет сообщения электронной почты, сообщаемые в корпорацию Майкрософт, с помощью методов, описанных в этом разделе, и добавляет пользователей laura@contoso.com и julia@contoso.com как получателей скрытой копии.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы настроили правила обработки почты для получения копий сообщений, выполните одно из указанных ниже действий.

- В центре администрирования Exchange перейдите к разделу правила для обработки **почтового ящика** , \> **Rules** \> выберите правило \> щелкните **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) и проверьте параметры.

- В PowerShell выполните следующую команду, чтобы проверить параметры:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Отправьте тестовые сообщения на один из электронных адресов отчетов и проверьте результаты.
