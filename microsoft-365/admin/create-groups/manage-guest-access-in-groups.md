---
title: Управление гостевим доступом в группах Microsoft 365
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
description: Узнайте, как добавлять гостей в группу Microsoft 365, просматривать гостевых пользователей и управлять гостевим доступом с помощью PowerShell.
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753281"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Управление гостевим доступом в группах Microsoft 365

По умолчанию гостевой доступ для групп Microsoft 365 включен для вашей организации. Администраторы могут разрешить гостевой доступ к группам для всей организации или отдельных групп.

Если он включен, участники группы могут приглашать гостевых пользователей в группу Microsoft 365 через Outlook в Интернете. Владельцу группы на утверждение отправляются приглашения.

После утверждения гостевой пользователь добавляется в каталог и группу.

> [!Note]
> Сети Yammer Корпоративный, которые находятся в режиме native или в географическом режиме [ЕС,](https://go.microsoft.com/fwlink/?linkid=2107357) не поддерживают гостей сети.
> Подключенные к Microsoft 365 группы Yammer в настоящее время не поддерживают гостевой доступ, но вы можете создавать не подключенные внешние группы в сети Yammer. Инструкции см. в инструкциях по созданию и управлению внешними группами [в Yammer.](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups)

Гостевой доступ в группах часто используется в рамках более широкого сценария, включаемого в SharePoint или Teams. Эти службы имеют собственные параметры гостевого общего доступа. Полные инструкции по настройке гостевого общего доступа в группах, SharePoint и Teams см. в разделе:

- [Совместная работа с гостями на сайте](../../solutions/collaborate-in-site.md)
- [Совместная работа с гостями в команде](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Управление гостевим доступом групп

Если вы хотите включить или отключить гостевой доступ в группах, это можно сделать в Центре администрирования Microsoft 365.

1. В Центре администрирования выберите **"Показать** все параметры организации" и на вкладке "Службы" выберите группы \>  \>  **Microsoft 365.** 
  
2. На странице **"Группы Microsoft 365"** выберите, хотите ли вы позволить людям за пределами вашей организации получать доступ к ресурсам группы или позволить владельцам групп добавлять в группы людей за пределами организации.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Добавление гостей в группу Microsoft 365 из Центра администрирования

Если гость уже существует в вашем каталоге, вы можете добавить его в свои группы из Центра администрирования Microsoft 365.
  
1. В Центре администрирования перейдите на страницу   >  **"Группы групп".**
  
2. Щелкните группу, в которая нужно добавить гостя, и выберите **"Просмотреть всех** участников и управлять ими" на вкладке **"Участники".** 
  
4. Выберите **"Добавить участников"** и выберите имя гостя, которого вы хотите добавить.
    
5. Нажмите **Сохранить**.

Если вы хотите добавить гостя непосредственно в каталог, вы можете добавить пользователей совместной работы [Azure Active Directory B2B на портале Azure.](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)

Если вы хотите изменить какие-либо сведения гостя, вы можете добавить или обновить данные профиля пользователя с помощью [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="see-also"></a>См. также

[Блокировка гостевых пользователей из определенной группы](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Управление членством в группах в Центре администрирования Microsoft 365](add-or-remove-members-from-groups.md)
  
[Проверки доступа Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
