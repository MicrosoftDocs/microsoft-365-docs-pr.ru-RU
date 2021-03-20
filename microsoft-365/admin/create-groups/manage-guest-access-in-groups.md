---
title: Управление гостевых доступом в группах Microsoft 365
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
ms.openlocfilehash: 114fc1b5262f1632c7e7a8d1aa339c2470223288
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908610"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Управление гостевых доступом в группах Microsoft 365

По умолчанию для групп Microsoft 365 включен гостевой доступ для вашей организации. Администраторы могут контролировать, разрешить ли гостевой доступ к группам для всей организации или для отдельных групп.

После его включив, участники группы могут приглашать гостевых пользователей в группу Microsoft 365 через Outlook в Интернете. Приглашения отправляются владельцу группы для утверждения.

После утверждения гостевой пользователь добавляется в каталог и группу.

> [!Note]
> Сети Yammer Enterprise, которые находятся в родном режиме или [в Eu Geo,](/yammer/manage-security-and-compliance/manage-data-compliance) не поддерживают гостей сети.
> В настоящее время группы подключенных yammer Microsoft 365 не поддерживают гостевой доступ, но в сети Yammer можно создавать внешние группы, не связанные с подключением. Дополнительные инструкции см. в инструкциях По созданию и управлению внешними группами [в Yammer.](/yammer/work-with-external-users/create-and-manage-external-groups)

Гостевой доступ в группах часто используется в рамках более широкого сценария, который включает SharePoint или Teams. Эти службы имеют собственные параметры гостевых обменов. Полные инструкции по настройке гостевых обменов между группами, SharePoint и Teams см. в разделе:

- [Совместная работа с гостями на сайте](../../solutions/collaborate-in-site.md)
- [Совместная работа с гостями в команде](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Управление гостевом доступом групп

Если вы хотите включить или отключить гостевой доступ в группах, вы можете сделать это в центре администрирования Microsoft 365.

1. В центре администрирования  перейдите к демонстрации всех параметров параметров Org и на вкладке \>  \>  **Services** выберите **группы Microsoft 365.**
  
2. На странице **Microsoft 365 Groups** выберите, хотите ли вы позволить людям, не входим в ресурсы группы организации, или позволить владельцам групп добавлять людей за пределами организации в группы.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Добавление гостей в группу Microsoft 365 из центра администрирования

Если гость уже существует в каталоге, его можно добавить в группы из центра администрирования Microsoft 365. (Группы с динамическим членством должны управляться [в Azure Active Directory.)](/azure/active-directory/enterprise-users/groups-create-rule)
  
1. В центре администрирования перейдите на страницу **Группы**  >  **групп.**
  
2. Щелкните группу, в которая нужно добавить гостя, и выберите **Просмотр** всех участников и управление ими на **вкладке Члены.** 
  
4. Выберите **Добавить участников** и выбрать имя гостя, которого вы хотите добавить.
    
5. Нажмите **Сохранить**.

Если вы хотите напрямую добавить гостя в каталог, вы можете добавить пользователей совместной работы [Azure Active Directory B2B на портале Azure.](/azure/active-directory/b2b/add-users-administrator)

Если вы хотите изменить любую информацию гостя, вы можете добавить или обновить сведения о профиле пользователя с [помощью Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="see-also"></a>См. также

[Блокировка гостевых пользователей из определенной группы](../../solutions/per-group-guest-access.md)

[Управление членством в группе в центре администрирования Microsoft 365](add-or-remove-members-from-groups.md)
  
[Обзоры доступа к Azure Active Directory](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)