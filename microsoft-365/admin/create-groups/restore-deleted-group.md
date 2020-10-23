---
title: Восстановление удаленной группы
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Узнайте, как восстановить удаленную группу Microsoft 365.
ms.openlocfilehash: 30e267a149bc18c2425d4ea38423b887116794c6
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681650"
---
# <a name="restore-a-deleted-group"></a>Восстановление удаленной группы

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

> [!NOTE]
> В этой статье описывается восстановление только групп Microsoft 365. После удаления все другие группы не могут быть восстановлены.

Если вы удалили группу, по умолчанию она будет храниться в течение 30 дней. Этот 30-дневный период считается "обратимым удалением", так как вы по-прежнему можете восстановить группу. По истечении 30 дней группа и связанное с ней содержимое безвозвратно удаляются и не могут быть восстановлены.

Вместе с группой восстанавливается следующее содержимое:
  
- Azure Active Directory (AD), Microsoft 365 группирует объект, свойства и элементы.
    
- Адреса электронной почты группы.
    
- Общие папки "Входящие" и "Календарь" в Exchange Online.
    
- Сайт группы SharePoint Online и файлы.
    
- записная книжка OneNote;
    
- Planner.
    
- Teams

- Группа Yammer и контент группы (если группа Microsoft 365 была создана из Yammer)

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a>Восстановление группы, которой владеет пользователь, с помощью Outlook в Интернете

Если вы являетесь владельцем группы Microsoft 365, вы можете восстановить эту группу в Outlook в Интернете, выполнив следующие действия:

1. На [странице удаленные группы](https://outlook.office.com/people/group/deleted)выберите пункт **Управление группами** в узле **группы** , а затем нажмите кнопку **Удалить**.

2. Щелкните вкладку **Восстановление** рядом с группой, которую требуется восстановить.

Если удаленная группа не отображается здесь, обратитесь к администратору.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Восстановление группы в центре администрирования Microsoft 365

Если вы являетесь глобальным администратором или администратором групп, вы можете восстановить удаленную группу в центре администрирования Microsoft 365:

1. Перейдите в [Центр администрирования](https://admin.microsoft.com).
2. Разверните узел **группы**, а затем щелкните **удаленные группы**.
3. Выберите группу, которую требуется восстановить, и нажмите кнопку **восстановить группу**.

> [!NOTE]
> В некоторых случаях восстановление группы и всех ее данных может занять до 24 часов. 
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Окончательное удаление группы Microsoft 365

Иногда может потребоваться окончательно очистить группу, не дожидаясь периода действия 30 дней для мягкого удаления. Для этого запустите PowerShell и выполните эту команду, чтобы получить идентификатор объекта группы:
  
```
Get-AzureADMSDeletedGroup
```

Запишите идентификатор объекта группы или групп, которые требуется окончательно удалить.
  
> [!CAUTION]
> При этом группа и все ее данные будут удалены навсегда. 
  
Чтобы окончательно удалить группу, в PowerShell выполните эту команду:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

Чтобы проверить, удалилась ли группа, снова запустите командлет  *Get-AzureADMSDeletedGroup*  и убедитесь, что группа отсутствует в списке обратимо удаленных. В некоторых случаях процесс полного окончательного удаления группы и всех ее данных может длиться до 24 часов. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>У вас есть вопросы по группам Microsoft 365?

Посетите [сообщество Майкрософт](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) для отправки вопросов и участия в беседах, посвященных группам Microsoft 365. 
  
## <a name="related-articles"></a>Статьи по теме

[Управление группами Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Удаление групп с помощью командлета Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Управление параметрами сайта группы, подключенного к группе](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Удаление группы в Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
