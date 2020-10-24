---
title: Управление гостевым доступом в группах Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Узнайте, как добавлять гостей в группу Microsoft 365, просматривать гостевых пользователей и использовать PowerShell для управления гостевым доступом.
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753281"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Управление гостевым доступом в группах Microsoft 365

По умолчанию для вашей организации включен гостевой доступ для групп Microsoft 365. Администраторы могут контролировать, разрешено ли гостевой доступ к группам для всей организации или для отдельных групп.

Когда она включена, участники группы могут приглашать гостевых пользователей в группу Microsoft 365 с помощью Outlook в Интернете. Приглашения отправляются владельцу группы для утверждения.

После утверждения пользователь-гость добавляется в каталог и группу.

> [!Note]
> Сети Yammer Enterprise, которые находятся в собственном режиме или в [географическом формате ЕС](https://go.microsoft.com/fwlink/?linkid=2107357) , не поддерживают гостевые сети.
> Microsoft 365 подключенные группы Yammer в настоящее время не поддерживают гостевой доступ, но вы можете создавать неподключенные внешние группы в сети Yammer. Инструкции по [созданию и управлению внешними группами в Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) .

Гостевой доступ в группах часто используется в составе более широкого сценария, включающего SharePoint или Teams. Эти службы имеют собственные параметры общего доступа к гостям. Для получения полных инструкций по настройке общего доступа к гостевым компьютерам в группах, SharePoint и Teams, ознакомьтесь со статьей:

- [Совместная работа с гостями на сайте](../../solutions/collaborate-in-site.md)
- [Совместная работа с гостями в команде](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Управление группами гостевого доступа

Если вы хотите включить или отключить гостевой доступ в группах, это можно сделать в центре администрирования Microsoft 365.

1. В центре администрирования перейдите в раздел **Показать все** \> **Параметры** \> **организационных параметров** и на вкладке **службы** выберите пункт **Microsoft 365 группы**.
  
2. На странице " **группы Microsoft 365** " выберите, следует ли разрешить пользователям, не входящим в организацию, получать доступ к ресурсам группы или разрешить владельцам групп добавлять людей вне Организации в группы.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Добавление гостей в группу Microsoft 365 из центра администрирования

Если гость уже существует в вашем каталоге, вы можете добавить их в свои группы из центра администрирования Microsoft 365.
  
1. В центре администрирования перейдите на **Groups**  >  страницу**группы** группы.
  
2. Щелкните группу, в которую требуется добавить гостя, и выберите **Просмотреть все и управлять участниками** на вкладке **Участники** . 
  
4. Нажмите кнопку **Добавить участников**и выберите имя гостя, которого вы хотите добавить.
    
5. Нажмите кнопку **Сохранить**.

Если вы хотите добавить гостя в каталог напрямую, вы можете [Добавить пользователей службы совместной работы Azure Active Directory на портале Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Если вы хотите изменить любую информацию гостя, вы можете [Добавить или обновить сведения о профиле пользователя с помощью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="see-also"></a>Дополнительные ресурсы:

[Блокировка гостевых пользователей из определенной группы](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Управление членством в группах в центре администрирования Microsoft 365](add-or-remove-members-from-groups.md)
  
[Проверка доступа Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set — AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
