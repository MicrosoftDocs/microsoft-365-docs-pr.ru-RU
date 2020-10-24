---
title: Восстановление удаленной группы Microsoft 365
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753247"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Восстановление удаленной группы Microsoft 365

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

> [!NOTE]
> В этой статье описывается восстановление только групп Microsoft 365. После удаления все другие группы не могут быть восстановлены.

## <a name="restore-a-group"></a>Восстановление группы

# <a name="outlook"></a>[Outlook](#tab/outlook)

Если вы являетесь владельцем группы Microsoft 365, вы можете восстановить эту группу в Outlook в Интернете, выполнив следующие действия:

1. На [странице удаленные группы](https://outlook.office.com/people/group/deleted)выберите пункт **Управление группами** в узле **группы** , а затем нажмите кнопку **Удалить**.

2. Щелкните вкладку **Восстановление** рядом с группой, которую требуется восстановить.

Если удаленная группа не отображается здесь, обратитесь к администратору.

# <a name="admin-center"></a>[Центр администрирования](#tab/admin-center)

Если вы являетесь глобальным администратором или администратором групп, вы можете восстановить удаленную группу в центре администрирования Microsoft 365:

1. Перейдите в [Центр администрирования](https://admin.microsoft.com).
2. Разверните узел **группы**, а затем щелкните **удаленные группы**.
3. Выберите группу, которую требуется восстановить, и нажмите кнопку **восстановить группу**.

> [!NOTE]
> В некоторых случаях восстановление группы и всех ее данных может занять до 24 часов. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>У вас есть вопросы по группам Microsoft 365?

Посетите [сообщество Майкрософт](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) для отправки вопросов и участия в беседах, посвященных группам Microsoft 365. 
  
## <a name="related-articles"></a>Статьи по теме

[Управление группами Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Удаление групп с помощью командлета Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Управление параметрами сайта группы, подключенного к группе](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Удаление группы в Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
