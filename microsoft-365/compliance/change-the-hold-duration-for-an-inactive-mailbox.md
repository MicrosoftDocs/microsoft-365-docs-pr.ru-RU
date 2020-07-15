---
title: Изменение срока хранения неактивного почтового ящика
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Когда почтовый ящик Office 365 становится неактивным, измените срок хранения или политику хранения Office 365, назначенную неактивному почтовому ящику.
ms.openlocfilehash: 675e6eb36f762a50c3caafce07d09fda9ba9d98e
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126380"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Изменение срока хранения неактивного почтового ящика

Неактивный почтовый ящик используется для хранения электронной почты бывшего сотрудника после того, как он покидает организацию. Почтовый ящик становится неактивным, если хранение для судебного разбирательства, политика хранения на месте, политика хранения Microsoft 365 или удержание, связанное с вариантом обнаружения электронных данных, размещаются в почтовом ящике, а соответствующая учетная запись пользователя удаляется. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. Срок хранения определяет, как долго удерживаются элементы в папке "элементы с возможностью восстановления". По истечении срока хранения элемента в папке "элементы с возможностью восстановления" элемент удаляется из неактивного почтового ящика без возможности восстановления. После неактивного почтового ящика вы можете изменить продолжительность удержания или политики хранения Microsoft 365, назначенную неактивному почтовому ящику.
  
> [!IMPORTANT]
> Так как мы будем хранить содержимое почтового ящика разными способами, мы сообщаем выбытие на месте в центре администрирования Exchange. Это означает, что для создания неактивного почтового ящика следует использовать удержания для судебного разбирательства и политики хранения Microsoft 365. Начиная с 1 апреля, 2020 вы не сможете создавать новые удержания на месте в Exchange Online. Но вы по-прежнему можете изменить срок хранения на месте, включенный для неактивного почтового ящика. Однако, начиная с 1 июля, 2020, вы не сможете изменить срок хранения. Удаление неактивного почтового ящика позволит удалить удержание на месте. Существующие Неактивные почтовые ящики, которые включены в удержание на месте, будут сохранены до тех пор, пока не будет удалено удержание. Для получения дополнительных сведений о прекращении удержания на месте, ознакомьтесь со статьей [выбытие средств прежних версий электронных данных](legacy-ediscovery-retirement.md).
  
## <a name="connect-to-powershell"></a>Подключение к PowerShell

- You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox. You can't use the Exchange admin center (EAC). But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold. Вы можете использовать центр безопасности и соответствия требованиям или PowerShell центра безопасности & соответствия требованиям, чтобы изменить срок хранения для политики хранения Microsoft 365.
    
- Чтобы подключиться к PowerShell для Exchange Online или Security & центр соответствия требованиям, обратитесь к следующим разделам:
    
  - [Подключение к PowerShell Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=799771)
    
- Удержания, связанные с случаями обнаружения электронных данных, являются бесконечными удержаниями, что означает, что срок хранения можно изменить. Элементы хранятся бессрочно или до отмены удержания и удаления неактивного почтового ящика.
    
- Для получения дополнительных сведений о неактивных почтовых ящиках просмотрите [Неактивные почтовые ящики в Microsoft 365](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Этап 1. Определение инцидентов удержания для неактивного почтового ящика

Так как различные типы удержаний или одна или несколько политик хранения Microsoft 365 могут быть размещены на неактивном почтовом ящике, первым этапом является определение удержаний для неактивного почтового ящика.
  
Выполните следующую команду в PowerShell Exchange Online, чтобы отобразить сведения об удержании для всех неактивных почтовых ящиков в организации.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

Значение **True** свойства **LitigationHoldEnabled** указывает, что неактивный почтовый ящик находится на хранении для судебного разбирательства. Если для неактивного почтового ящика размещается удержание на месте, удержание eDiscovery или политика хранения Microsoft 365, то в качестве значения свойства **InPlaceHolds** отображается идентификатор GUID для удержания или политики хранения. Например, ниже показаны результаты для пяти неактивных почтовых ящиков. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

В следующей таблице перечислены пять типов удержания, использовавшиеся для отключения каждого почтового ящика.
  
|**Неактивный почтовый ящик**|**Тип удержания**|**Как определить удержание для неактивного почтового ящика**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Хранение для судебного разбирательства  <br/> |Свойство  *LitigationHoldEnabled*  имеет значение  `True`.  <br/> |
|Pilar Pinilla  <br/> |Удержание на месте  <br/> |The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox. You can tell this is an In-Place Hold because the ID doesn't start with a prefix.  <br/> С помощью команды  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` в Exchange Online PowerShell можно получить сведения об удержании на месте для неактивного почтового ящика.  <br/> |
|Mario Necaise  <br/> |Политика хранения Microsoft 365 для всей Организации в центре безопасности & соответствия требованиям  <br/> |Свойство  *InPlaceHolds*  не задано. Это означает, что к неактивному почтовому ящику применяется одна или несколько политик хранения Microsoft 365 (на уровне всей организации или на уровне Exchange). В этом случае можно выполнить `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` команду в Exchange Online PowerShell, чтобы получить список идентификаторов GUID для политик хранения Microsoft 365 на уровне всей Организации. GUID для политик хранения на уровне Организации, применяемых к почтовым ящикам Exchange, начинаются с `mbx` префикса, например `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> <br/>Чтобы определить политику хранения Microsoft 365, которая была применена к неактивному почтовому ящику, выполните следующую команду в консоли безопасности & центра соответствия требованиям PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Политика хранения Microsoft 365 в центре безопасности & соответствия требованиям, применяемых к определенным почтовым ящикам  <br/> |Свойство *InPlaceHolds* содержит GUID политики хранения Microsoft 365, которая применяется к неактивному почтовому ящику. То, что политика хранения применяется к определенному почтовому ящику, можно определить по префиксу GUID  `mbx`. Если идентификатор GUID политики хранения, примененный к неактивному почтовому ящику, запущен с `skp` префиксом, это указывает на то, что политика хранения применяется к беседам Skype для бизнеса.  <br/><br/> Чтобы определить политику хранения Microsoft 365, которая была применена к неактивному почтовому ящику, выполните следующую команду в консоли безопасности & центра соответствия требованиям PowerShell.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Не забудьте удалить префикс  `mbx` или  `skp` при выполнении этой команды.  <br/> |
|Abraham McMahon  <br/> |удержание дел обнаружения электронных данных в центре безопасности & соответствия требованиям  <br/> |The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  <br/> Вы можете использовать `Get-CaseHoldPolicy` командлет в PowerShell центра безопасности & соответствия требованиям, чтобы получить сведения о варианте обнаружения электронных данных, с которым связан удержание для неактивного почтового ящика. For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` при выполнении этой команды.  <br/><br/> Чтобы определить дело обнаружения электронных данных, с которым связано удержание для неактивного почтового ящика, выполните следующие команды.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Примечание:** Мы не рекомендуем использовать удержания электронных данных для неактивных почтовых ящиков. Это обусловлено тем, что варианты обнаружения электронных данных предназначены для определенных и ограниченных временных случаев, связанных с юридическим вопросом. В какой-то момент юридический случай, скорее всего, будет удален, и удержания, связанные с этим обращением, будут удалены, а ситуация обнаружения электронных данных будет закрыта (или удалена). На самом деле, если удержание, размещенное на неактивном почтовом ящике, связано с вариантом обнаружения электронных данных, а удержание отключено или закрыто или удалено, неактивный почтовый ящик будет безвозвратно удален. 

Дополнительные сведения о политиках хранения Microsoft 365 можно узнать в [статье сведения о политиках хранения и метках хранения](retention.md).
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Этап 2. Изменение срока удержания неактивного почтового ящика

После определения типа удержания и количества инцидентов удержания для неактивного почтового ящика следующий шаг  изменение срока удержания. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Изменение срока хранения для судебного разбирательства

Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox. You can't use the EAC. Run the following command to change the hold duration. In this example, the hold duration is changed to an unlimited period of time.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

В результате элементы в неактивном почтовом ящике хранятся бессрочно (до снятия удержания или изменения срока хранения).
  
> [!TIP]
> The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Изменение срока хранения на месте

 Для изменения срока удержания на месте можно использовать Центр администрирования Exchange или Exchange Online PowerShell. 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>Изменение срока хранения на месте с помощью EAC

1. Если вы знаете имя инцидента хранения на месте, который требуется изменить, можно перейти к следующему шагу. В противном случае выполните указанную ниже команду, чтобы получить имя инцидента хранения на месте для неактивного почтового ящика. Используйте идентификатор GUID хранения на месте, полученный на [шаге 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Выберите удержание на месте, которое нужно изменить, а затем нажмите кнопку **изменить** ![ значок редактирования ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. На странице свойств ** &amp; хранения для обнаружения электронных** данных на месте выберите **удержание на месте**. 
    
5. Выполните одно из следующих действий в зависимости от текущего срока хранения.
    
    1. Выберите пункт **хранить бессрочно** , чтобы хранить элементы в течение неограниченного периода времени. 
    
    2. Выберите **указать количество дней хранения элементов относительно даты их получения** для хранения элементов за определенный период. Type the number of days that you want to hold items for. 
    
    ![Снимок экрана: изменение длительности параметра хранения на месте.](../media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. Нажмите **Save** (Сохранить).
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Изменение срока хранения в PowerShell Exchange Online

1. Если вы знаете имя инцидента хранения на месте, который требуется изменить, можно перейти к следующему шагу. В противном случае выполните указанную ниже команду, чтобы получить имя инцидента хранения на месте для неактивного почтового ящика. Используйте идентификатор GUID хранения на месте, полученный на [шаге 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. Чтобы изменить срок хранения, выполните следующую команду. В этом примере срок хранения изменяется на 2 555 дней (примерно семь лет). 
    
    ```powershell
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     Чтобы изменить срок хранения на неограниченный период, используйте параметр  _-ItemHoldPeriod unlimited_.
  
## <a name="more-information"></a>Дополнительные сведения

- **How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created. 
    
- **Что происходит по истечении срока удержания?** По истечении срока хранения элемента в папке "Элементы с возможностью восстановления" он будет окончательно удален из неактивного почтового ящика. Если для удержания не указана длительность удержания для неактивного почтового ящика, элементы в папке "элементы с возможностью восстановления" никогда не очищаются (если не изменится срок хранения для неактивного почтового ящика). 
    
- **Is an Exchange retention policy still processed on inactive mailboxes?** If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox. That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires. Those items are then purged from the inactive mailbox when the hold duration for an item expires. 
    
    Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies. 
    
- **To check the new hold duration, run one of the following commands.** The first command is for Litigation Hold; the second is for In-Place Hold. 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```powershell
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **Помощник по обслуживанию управляемых папок (MFA) также обрабатывает неактивные почтовые ящики, как и обычные почтовые ящики.** В Exchange Online MFA обрабатывает почтовые ящики приблизительно один раз в семь дней. После изменения срока удержания для неактивного почтового ящика вы можете использовать командлет **Start-ManagedFolderAssistant** для немедленного запуска обработки нового срока удержания неактивного почтового ящика. Выполните следующую команду: 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Если для неактивного почтового ящика размещается много удержаний, будут отображены не все идентификаторы GUID удержания.** Чтобы просмотреть GUID всех удержаний (кроме хранения для судебного разбирательства), выполните следующую команду: 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
