---
title: Восстановление удаленной Microsoft 365 группы
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Удаленная группа сохраняется в течение 30 дней, и вы все еще можете восстановить группу. Через 30 дней группа и ее содержимое будут удалены навсегда.
ms.openlocfilehash: ddc3da57c05b7c5f54c10a0cc429c9a3f24b859c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394055"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Восстановление удаленной Microsoft 365 группы

Если вы удалили группу, она будет храниться в течение 30 дней по умолчанию. Этот 30-дневный период считается "мягким удалением", так как можно восстановить группу. Через 30 дней группа и связанное с ней содержимое удаляются навсегда и не могут быть восстановлены.

Вместе с группой восстанавливается следующее содержимое:
  
- Azure Active Directory (AD) Microsoft 365, свойств и членов групп.
    
- Адреса электронной почты группы.
    
- Exchange Online общий почтовый ящик и календарь.
    
- SharePoint Веб-сайт и файлы команды в Интернете.
    
- записная книжка OneNote;
    
- Planner.
    
- Teams

- Yammer группового и группового контента (если Microsoft 365 группа была создана из Yammer)

> [!NOTE]
> В этой статье описывается восстановление только Microsoft 365 групп. Все остальные группы не могут быть восстановлены после удаления.

## <a name="restore-a-group"></a>Восстановление группы

# <a name="outlook"></a>[Outlook](#tab/outlook)

Если вы владелец группы Microsoft 365, вы можете восстановить группу самостоятельно в Outlook в Интернете, следуя следующим шагам:

1. На странице [удаленные группы](https://outlook.office.com/people/group/deleted)выберите параметр **Управление** группами в узле **Группы,** а затем выберите **Удаленный**.

2. Щелкните **вкладку Восстановление** рядом с группой, необходимой для восстановления.

Если удаленная группа не появится здесь, обратитесь к администратору.

# <a name="admin-center"></a>[Центр администрирования](#tab/admin-center)

Если вы глобальный администратор или администратор групп, вы можете восстановить удаленную группу в Центр администрирования Microsoft 365:

1. Перейдите в [Центр администрирования](https://admin.microsoft.com).
2. **Расширь** группы и нажмите **кнопку Удаленные группы.**
3. Выберите группу, которую необходимо восстановить, и нажмите кнопку **Восстановить группу**.

> [!NOTE]
> В некоторых случаях для восстановления группы и всех ее данных может потребоваться до 24 часов. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Есть вопросы о Microsoft 365 группах?

Посетите [веб-сайт Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) для публикации вопросов и участия в беседах о Microsoft 365 группах. 
  
## <a name="related-content"></a>См. также:

[Управление Microsoft 365 группами с помощью PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (статья)\
[Удаление групп с Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) (статья)\
[Управление настройками веб-сайтов группы](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) с подключением к группе (статья)\
[Удаление группы в Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (статья)