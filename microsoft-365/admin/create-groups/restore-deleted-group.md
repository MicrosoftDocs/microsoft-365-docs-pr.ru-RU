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

Если вы удалили группу, она будет храниться по умолчанию в течение 30 дней. Этот 30-дневный период считается "мягким удалением", так как вы по-прежнему можете восстановить группу. Через 30 дней группа и связанное с ней содержимое окончательно удаляются и не могут быть восстановлены.

Вместе с группой восстанавливается следующее содержимое:
  
- Объект, свойства и члены групп Microsoft 365 Azure Active Directory (AD).
    
- Адреса электронной почты группы.
    
- Общие почтовые ящики и календарь Exchange Online.
    
- Сайт и файлы группы SharePoint Online.
    
- записная книжка OneNote;
    
- Planner.
    
- Teams

- Содержимое групп и групп Yammer (если группа Microsoft 365 была создана из Yammer)

> [!NOTE]
> В этой статье описывается восстановление только групп Microsoft 365. Все остальные группы невозможно восстановить после удаления.

## <a name="restore-a-group"></a>Восстановление группы

# <a name="outlook"></a>[Outlook](#tab/outlook)

Если вы владелец группы Microsoft 365, вы можете самостоятельно восстановить группу в Outlook в Интернете, вы можете сделать следующее:

1. На странице ["Удаленные группы"](https://outlook.office.com/people/group/deleted)выберите **параметр** "Управление группами" в узле "Группы" и выберите **"Удалено".** 

2. Щелкните **вкладку "Восстановление"** рядом с группой, которая вы хотите восстановить.

Если удаленная группа не появляется здесь, обратитесь к администратору.

# <a name="admin-center"></a>[Центр администрирования](#tab/admin-center)

Если вы глобальный администратор или администратор групп, вы можете восстановить удаленную группу в Центре администрирования Microsoft 365:

1. Перейдите в [Центр администрирования](https://admin.microsoft.com).
2. Раз **развернуть группы** и щелкнуть **"Удаленные группы".**
3. Выберите группу, которую нужно восстановить, и нажмите кнопку **"Восстановить группу".**

> [!NOTE]
> В некоторых случаях восстановление группы и всех ее данных может занять до 24 часов. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Возникли вопросы о группах Microsoft 365?

Посетите сообщество [Microsoft Tech Community,](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) чтобы задавать вопросы и участвовать в беседах о группах Microsoft 365. 
  
## <a name="related-articles"></a>Статьи по теме

[Управление группами Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Удаление групп с помощью командлета Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Управление параметрами сайта группы, подключенного к группе](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Удаление группы в Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
