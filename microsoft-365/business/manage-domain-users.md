---
title: Синхронизация пользователей домена с Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Синхронизация пользователей, контролируемых доменом, с помощью Microsoft 365 для бизнеса.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841366"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Синхронизация пользователей домена с Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Подготовка к синхронизации службы каталогов 

Перед синхронизацией пользователей и компьютеров из локального домена Active Directory просмотрите статью [Подготовка к синхронизации службы каталогов в Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization). В частности:

   - Убедитесь, что в каталоге нет дубликатов для следующих атрибутов: **mail** , **proxyAddresses** и **userPrincipalName** . Эти значения должны быть уникальными и все дубликаты должны быть удалены.
   
   - Рекомендуется настроить атрибут **userPrincipalName** (UPN) для каждой учетной записи локального пользователя, чтобы она соответствовала основному адресу электронной почты, соответствующему лицензированному пользователю Microsoft 365. Например: *Mary.Shelley@contoso.com* , а не *Mary@contoso. local*
   
   - Если домен Active Directory завершается в немаршрутизируемый суффиксе, например. *Local* или *. LAN* , вместо суффикса, поддерживающего маршрутизацию в Интернете, например *. com* или *. org* , сначала измените суффикс UPN локальных учетных записей пользователей, как описано в статье [Подготовка домена, не поддерживающего маршрутизацию, для синхронизации службы каталогов](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

В разделе **Run IdFix** (4), приведенном ниже, также необходимо убедиться, что локальный Active Directory готов к синхронизации службы каталогов.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Установка и настройка Azure AD Connect

Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, установите Azure Active Directory Connect и настройте синхронизацию службы каталогов. 

 1. В [центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=2024339)выберите пункт **Настройка** в левой панели навигации.

 2. В разделе **Вход и безопасность** выберите пункт **Просмотр**  в разделе **синхронизация пользователей из каталога вашей организации** .

 3. На странице **синхронизация пользователей из каталога вашей организации** нажмите кнопку **Начало работы** .

 4. На первом шаге запустите средство IdFix, чтобы подготовиться к синхронизации службы каталогов.

 5. Следуйте указаниям мастера, чтобы скачать Azure AD Connect и использовать его для синхронизации пользователей с управлением домена с Microsoft 365.


Более подробную информацию можно узнать в статье [Настройка синхронизации каталогов для Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) .

При настройке параметров для Azure AD Connect рекомендуется включить **синхронизацию паролей** , **единый вход** и функцию **обратной записи паролей** , которая также поддерживается в Microsoft 365 для бизнеса.

> [!NOTE]
> Существует несколько дополнительных действий для обратной записи пароля за пределами флажка в службе Azure AD Connect. Дополнительные сведения см. [в статье Настройка обратной записи пароля](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

Если вы также хотите управлять устройствами с Windows 10, присоединенные к домену, ознакомьтесь со [статьей включение поддержки подключенных к домену устройств с Windows 10 с помощью Microsoft 365 Business Premium](manage-windows-devices.md) , чтобы настроить гибридное соединение Azure AD. 