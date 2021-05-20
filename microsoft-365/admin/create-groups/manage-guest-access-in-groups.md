---
title: Управление доступом гостей в Microsoft 365 группах
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
description: Узнайте, как добавить гостей в группу Microsoft 365, просматривать гостевых пользователей и использовать PowerShell для управления доступом гостей.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571941"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Управление доступом гостей в Microsoft 365 группах

По умолчанию для вашей организации Microsoft 365 доступ для групп гостей. Администраторы могут контролировать, разрешать ли гостевой доступ к группам для всей организации или для отдельных групп.

Когда он включен, участники группы могут пригласить приглашенных пользователей в группу Microsoft 365 через Outlook в Интернете. Приглашения отправляются владельцу группы для утверждения.

После утверждения гостевой пользователь добавляется в каталог и группу.

> [!Note]
> Yammer корпоративный сети, на которые находятся в родном режиме [или EU Geo,](/yammer/manage-security-and-compliance/manage-data-compliance) не поддерживают гостей сети.
> Microsoft 365 Подключенные Yammer группы в настоящее время не поддерживают гостевой доступ, но вы можете создавать не связанные внешние группы в вашей Yammer сети. Для [получения инструкций можно просмотреть создание и управление Yammer группами](/yammer/work-with-external-users/create-and-manage-external-groups) в других местах.

Доступ гостей в группы часто используется как часть более широкого сценария, который включает в себя SharePoint или Teams. Эти службы имеют свои собственные настройки совместного использования гостей. Для получения полных инструкций по настройке совместного использования гостей между группами, SharePoint и Teams см.:

- [Совместная работа с гостями на сайте](../../solutions/collaborate-in-site.md)
- [Совместная работа с гостями в команде](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Управление гостевым доступом групп

Если вы хотите включить или отключить доступ гостей в группах, вы можете сделать это в Microsoft 365-центра.

1. В центре администратора перейдите на показ **всех настроек** org Параметры org и \>  \>  на **вкладке Услуги,** **выберите Microsoft 365 группы.**
  
2. На странице **Microsoft 365 групп выберите,** хотите ли вы, чтобы люди за пределами вашей организации доступ к групповым ресурсам или позволить владельцам групп добавлять людей за пределами вашей организации в группы.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Добавление гостей в Microsoft 365 группу из админ-центра

Если гость уже существует в вашем каталоге, вы можете добавить их в свои группы из Microsoft 365 центра. (Группы с динамичным членством [должны управляться в Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. В центре администратора перейдите на страницу **групп.**  >  
  
2. Нажмите на группу, в которую вы хотите добавить гостя, и **выберите Просмотр всех участников и управление ими** во **вкладке «Члены».** 
  
4. Выберите **Add членов** и выберите имя гостя, который вы хотите добавить.
    
5. Нажмите **Сохранить**.

Если вы хотите добавить гостя в каталог напрямую, [вы можете добавить Azure Active Directory пользователей совместной работы B2B на портале Azure.](/azure/active-directory/b2b/add-users-administrator)

Если вы хотите отредактировать какую-либо информацию о госте, вы можете добавить [или обновить информацию о профиле пользователя, используя Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="related-content"></a>См. также:

[Блокировка гостевых пользователей из определенной группы](../../solutions/per-group-guest-access.md) (статья)

[Управление членством в группе Microsoft 365 центре (статья)](add-or-remove-members-from-groups.md)
  
[Azure Active Directory обзоры доступа](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (статья)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (статья)