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
description: Администраторы могут узнать, как использовать правила потока обработки почты (также называемые правилами транспорта) для получения копий сообщений, подказываемых пользователями в корпорацию Майкрософт.
ms.openlocfilehash: 1612adeefff21fa9f149de6537917dd9b8c50b00
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827389"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователи могут сообщать в корпорацию Майкрософт для анализа сообщения для анализа в соответствии с описанием в [отчетах о сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)

Вы можете создать правило потока обработки почты (также называемое правилом транспорта), которое будет искать сообщения, о которых пользователи передавают отчеты в корпорацию Майкрософт, и настроить получателей в поле "СК" на получение копий этих сообщений.

Вы можете создать правило потока обработки почты в Центре администрирования Exchange и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономная оболочка PowerShell EOP для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Для выполнения этих процедур необходимы права в Exchange Online или EOP. В частности, вам должна быть назначена роль **правил транспорта,** которая по умолчанию назначается **ролям управления**организацией, **Compliance Management** **управлением** соответствием требованиям и записями. Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Сведения о том, как открыть [Центр администрирования Exchange, см. в Центре администрирования Exchange в](https://docs.microsoft.com/Exchange/exchange-admin-center) Exchange Online или Центре администрирования Exchange в [автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о правилах для потока обработки почты в Exchange Online и автономной службе EOP см. в следующих разделах:

  - [Правила потока обработки почты (правила транспорта) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения (предикаты) правил потока обработки почты в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правил обработки почтового потока в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Создание правила потока обработки почты для получения копий отчетных сообщений с помощью Центра администрирования Exchange

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Нажмите **кнопку** ![ "Добавить ](../../media/ITPro-EAC-AddIcon.png) значок "Добавить" и **выберите пункт "Создать правило".**

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Имя:** введите уникальное, понятное имя правила. Например, "Отправленные копии сообщения, отправленные в корпорацию Майкрософт".

   - Нажмите кнопку **Дополнительные параметры**.

   - **Правило применяется, если:** **выберите** адрес получателя, который содержит любое из следующих слов: в появившемся диалоговом окне "Укажите слова или фразы" введите одно из \> **address includes any of these words**следующих значений, нажмите **кнопку Добавить** **Specify words or phrases** ![ ](../../media/ITPro-EAC-AddIcon.png) значок и повторяйте, пока не введите все значения.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Чтобы изменить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования. Чтобы удалить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-DeleteIcon.png) "Удалить".

     После этого нажмите кнопку **ОК**.

   - **Выполните следующие действия:** выберите **"Добавить** \> **получателей в поле "СК".** В появившемся диалоговом окне найдите и выберите нужных получателей. После этого нажмите кнопку **ОК**.

4. Можно выбрать дополнительные параметры для аудита и проверки правила, его активации в течение определенного периода, а также настроить другие параметры. Рекомендуется протестировать правило перед его применением.

5. Выполнив необходимые действия, нажмите кнопку **Сохранить**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Создание правила потока обработки почты для получения копий отчетов с помощью PowerShell

В этом примере показано, как создать новое правило для потока обработки почты, «Bcc Messages Reported to Microsoft», которое ищет электронные сообщения, о которых сообщаются корпорации Майкрософт, по средством, описанным в этой статье, а затем пользователи laura@contoso.com и julia@contoso.com в качестве получателей с книжкой.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы настроили правила потока обработки почты для получения копий сообщений из них, выполните одно из указанных ниже действий.

- В Центре администрирования Exchange перейдите в раздел **"Правила** \> **потока обработки** \> почты" и \> выберите правило на значок **Edit** ![ "Изменить ](../../media/ITPro-EAC-EditIcon.png) изменить" и проверьте параметры.

- В PowerShell выполните следующую команду, чтобы проверить параметры:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Отправьте тестовые сообщения на один из электронных адресов в отчетах и проверьте результаты.
