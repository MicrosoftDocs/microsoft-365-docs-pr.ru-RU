---
title: Синхронизация пользователей домена с Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Синхронизировать пользователей, управляемых доменом, с Microsoft 365 для бизнеса.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578414"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Синхронизация пользователей домена с Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Подготовка к синхронизации каталогов 

Прежде чем синхронизировать пользователей и [компьютеры](../enterprise/prepare-for-directory-synchronization.md)с локального домена Active Directory, просмотрите подготовку к синхронизации каталогов с Microsoft 365 . В частности:

   - Убедитесь, что в каталоге не существует дубликатов для следующих атрибутов: **почты,** **proxyAddresses** и **userPrincipalName.** Эти значения должны быть уникальными, и любые дубликаты должны быть удалены.
   
   - Рекомендуется настроить атрибут **userPrincipalName** (UPN) для каждой учетной записи локального пользователя, чтобы соответствовать основному адресу электронной почты, соответствующему лицензированной Microsoft 365 пользователю. Например: *mary.shelley@contoso.com,* *а не mary@contoso.local*
   
   - Если домен Active Directory заканчивается суффиксом без маршрутизации, например *.local* или *.lan,* вместо суффикса для маршрутизации интернета, например *.com* или *.org,* сначала настройтесь на суффикс учетных записей локальных пользователей, как описано в "Подготовка ненаправимого домена для синхронизации каталогов". [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md) 

Запуск **IdFix** в шаге 4 (4) ниже, также убедитесь, что локальное Active Directory готово к синхронизации каталогов.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Установка и настройка Azure AD Подключение

Чтобы синхронизировать пользователей, группы и контакты из локального Active Directory в Azure Active Directory, установите Azure Active Directory Подключение и установите синхронизацию каталогов. 

 1. В центре [администрирования](https://go.microsoft.com/fwlink/p/?linkid=2024339)выберите **Установку** в левом nav.

 2. В **соответствии с входом и безопасностью** выберите **Просмотр**  под синхронизацией пользователей **из каталога вашей организации**.

 3. На странице Sync пользователи со страницы **каталога** вашей организации выберите **Начало работы.**

 4. На первом этапе запустите средство IdFix для подготовки к синхронизации Каталог.

 5. Выполните действия мастера, чтобы скачать azure AD Подключение и использовать его для синхронизации пользователей, управляемых доменом, для Microsoft 365.


Дополнительные [дополнительные данные](../enterprise/set-up-directory-synchronization.md) см. в Microsoft 365 синхронизации каталогов.

При настройке параметров Azure AD Подключение рекомендуется включить синхронизацию паролей, бесшовную одновокую запись и функцию списания паролей, которая также поддерживается Microsoft 365 для бизнеса.   

> [!NOTE]
> Существует несколько дополнительных действий для списания пароля за пределами контрольного окна в Azure AD Подключение. Дополнительные сведения см. в [статью How-to: настройка записи пароля.](/azure/active-directory/authentication/howto-sspr-writeback) 

Если вы также хотите управлять устройствами с Windows 10 [](manage-windows-devices.md) доменами, см. в Windows 10 включить устройства с Windows 10, управляемыми Microsoft 365 бизнес премиум, чтобы настроить гибридную службу Azure AD Join.