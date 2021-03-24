---
title: Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать правила потока почты (также известные как правила транспорта) для получения копий сообщений, которые пользователи сообщают Корпорации Майкрософт.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069934"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователи могут отправлять сообщения в Корпорацию Майкрософт для анализа, как описано в сообщениях и файлах Отчета в [Microsoft](report-junk-email-messages-to-microsoft.md).

Можно создать правило потока почты (также известное как правило транспорта), которое ищет сообщения, которые пользователи сообщают Корпорации Майкрософт, и можно настроить получателей Bcc для получения копий этих сообщений.

Правило потока почты можно создать в центре администрирования Exchange (EAC) и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Вам необходимо получить разрешения в Exchange Online или Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье. В частности, вам  нужна роль Правил транспорта, которая по умолчанию назначена группам  ролей **"Управление** организацией",  "Управление соответствием требованиям" (глобальные администраторы) и "Управление записями".

  Дополнительную информацию см. в следующих статьях:

  - [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Разрешения в автономном EOP](feature-permissions-in-eop.md)
  - [Использование EAC измените список участников в группах ролей](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Чтобы открыть центр администрирования в Exchange Online, см. в центре [администрирования Exchange в Exchange Online.](/Exchange/exchange-admin-center) Чтобы открыть EAC в автономных EOP, см. в центре администрирования Exchange в режиме [автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о правилах потока почты в Exchange Online и автономных EOP см. в следующих темах:
  - [Правила потока обработки почты (правила транспорта) в Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Условия и исключения правил потока почты (предикаты) в Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Действия правила потока почты в Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Используйте EAC для создания правила потока почты для получения копий сообщений

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Нажмите **кнопку Добавить** ![ значок Добавить, ](../../media/ITPro-EAC-AddIcon.png) а затем выберите Создать новое **правило**.

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Имя.** Введите уникальное, описательное имя для правила. Например, Bcc Messages Reported to Microsoft.

   - Нажмите кнопку **Дополнительные параметры**.

   - Применяйте это правило, если : Выберите адрес получателя включает любое из этих слов. В диалоговом окантовке "Укажите слова или фразы", введите одно из следующих значений, нажмите кнопку Добавить значок добавить и повторите, пока не введите все  \>    ![ ](../../media/ITPro-EAC-AddIcon.png) значения.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Чтобы изменить запись, выберите ее и нажмите **кнопку Изменить значок Изменить** ![ ](../../media/ITPro-EAC-EditIcon.png) . Чтобы удалить запись, выберите ее и нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

     После этого нажмите кнопку **ОК**.

   - **Сделайте следующее:** **Выберите добавление получателей** \> **в поле Bcc**. В диалоговом окантове, который отображается, найдите и выберите получателей, которые необходимо добавить. После этого нажмите кнопку **ОК**.

4. Вы можете сделать дополнительные выборы для аудита правила, проверки правила, активации правила в течение определенного периода времени и других параметров. Мы рекомендуем тестировать правило перед его выполнением.

5. Когда закончите, нажмите кнопку **Сохранить**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Использование PowerShell для создания правила потока почты для получения копий сообщений с сообщениями

В этом примере создается новое правило потока почты с именем Bcc Messages Reported to Microsoft, которое ищет сообщения электронной почты, которые сообщаются Корпорации Майкрософт с помощью методов, описанных в этой статье, и добавляет пользователей laura@contoso.com и julia@contoso.com в качестве получателей Bcc.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы настроили правила потока почты для получения копий сообщений, сделайте все следующие действия:

- В EAC перейдите к **правилу потока почты** выберите правило \>  \> \> нажмите кнопку Изменить значок **Редактирование** ![ и проверьте ](../../media/ITPro-EAC-EditIcon.png) параметры.

- В PowerShell запустите следующую команду для проверки параметров:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Отправьте тестовые сообщения на один из адресов электронной почты отчетов и убедитесь в результатах.