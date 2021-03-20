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
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910550"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Восстановление удаленной группы Microsoft 365

Если вы удалили группу, она будет храниться в течение 30 дней по умолчанию. Этот 30-дневный период считается "мягким удалением", так как можно восстановить группу. Через 30 дней группа и связанное с ней содержимое удаляются навсегда и не могут быть восстановлены.

Вместе с группой восстанавливается следующее содержимое:
  
- Объект, свойства и участники Azure Active Directory (AD) Microsoft 365 Groups.
    
- Адреса электронной почты группы.
    
- Exchange Online поделился почтовым ящиком и календарем.
    
- Сайт и файлы группы SharePoint Online.
    
- записная книжка OneNote;
    
- Planner.
    
- Teams

- Групповой и групповой контент Yammer (если группа Microsoft 365 была создана из Yammer)

> [!NOTE]
> В этой статье описывается восстановление только групп Microsoft 365. Все остальные группы не могут быть восстановлены после удаления.

## <a name="restore-a-group"></a>Восстановление группы

# <a name="outlook"></a>[Outlook](#tab/outlook)

Если вы владелец группы Microsoft 365, вы можете самостоятельно восстановить группу в Outlook в Интернете, следуя следующим шагам:

1. На странице [удаленные группы](https://outlook.office.com/people/group/deleted)выберите параметр **Управление** группами в узле **Группы,** а затем выберите **Удаленный**.

2. Щелкните **вкладку Восстановление** рядом с группой, необходимой для восстановления.

Если удаленная группа не появится здесь, обратитесь к администратору.

# <a name="admin-center"></a>[Центр администрирования](#tab/admin-center)

Если вы глобальный администратор или администратор групп, вы можете восстановить удаленную группу в центре администрирования Microsoft 365:

1. Перейдите в [Центр администрирования](https://admin.microsoft.com).
2. **Расширь** группы и нажмите **кнопку Удаленные группы.**
3. Выберите группу, которую необходимо восстановить, и нажмите кнопку **Восстановить группу**.

> [!NOTE]
> В некоторых случаях для восстановления группы и всех ее данных может потребоваться до 24 часов. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Есть вопросы о Группах Microsoft 365?

Посетите [техническое сообщество Майкрософт,](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) чтобы опубликовать вопросы и принять участие в беседах о группах Microsoft 365. 
  
## <a name="related-articles"></a>Статьи по теме

[Управление группами Microsoft 365 с помощью PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[Удаление групп с помощью командлета Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup)
  
[Управление параметрами сайта группы, подключенного к группе](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Удаление группы в Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)