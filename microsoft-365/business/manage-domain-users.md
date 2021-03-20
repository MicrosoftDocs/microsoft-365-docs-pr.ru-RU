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
description: Синхронизировать пользователей, управляемых доменом, с Microsoft 365 для бизнеса.
ms.openlocfilehash: 1c939dec7229f02991b15f08c48f184efecaddb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913261"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Синхронизация пользователей домена с Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Подготовка к синхронизации каталогов 

Прежде чем синхронизировать пользователей и компьютеры с локального домена Active Directory, просмотрите подготовку к синхронизации каталогов с [Microsoft 365.](../enterprise/prepare-for-directory-synchronization.md) В частности:

   - Убедитесь, что в каталоге не существует дубликатов для следующих атрибутов: **почты,** **proxyAddresses** и **userPrincipalName.** Эти значения должны быть уникальными, и любые дубликаты должны быть удалены.
   
   - Рекомендуется настроить атрибут **userPrincipalName** (UPN) для каждой учетной записи локального пользователя, чтобы соответствовать основному адресу электронной почты, соответствующему лицензированным пользователю Microsoft 365. Например: *mary.shelley@contoso.com,* *а не mary@contoso.local*
   
   - Если домен Active Directory заканчивается суффиксом без маршрутизации, например *.local* или *.lan,* вместо суффикса для маршрутизации интернета, например *.com* или *.org,* сначала настройтесь на суффикс учетных записей локальных пользователей, как описано в "Подготовка ненаправимого домена для синхронизации каталогов". [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md) 

Запуск **IdFix** в шаге 4 (4) ниже, также убедитесь, что локальное Active Directory готово к синхронизации каталогов.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Установка и настройка Подключения Azure AD

Чтобы синхронизировать пользователей, группы и контакты из локального Active Directory в Azure Active Directory, установите Azure Active Directory Connect и установите синхронизацию каталогов. 

 1. В центре [администрирования](https://go.microsoft.com/fwlink/p/?linkid=2024339)выберите **Установку** в левом nav.

 2. В **соответствии с входом и безопасностью** выберите **Просмотр**  под синхронизацией пользователей **из каталога вашей организации**.

 3. На странице Sync пользователи со страницы **каталога** вашей организации выберите **Начало работы.**

 4. На первом этапе запустите средство IdFix для подготовки к синхронизации Каталог.

 5. Выполните действия мастера, чтобы скачать Azure AD Connect и использовать его для синхронизации пользователей, управляемых доменом, с Microsoft 365.


Дополнительные данные см. в дополнительных подробной информации о синхронизации каталогов [для Microsoft 365.](../enterprise/set-up-directory-synchronization.md)

При настройке параметров Azure AD Connect рекомендуется включить синхронизацию паролей, бесшовную одновокую запись и функцию записи паролей, которая также поддерживается в Microsoft 365 для бизнеса. 

> [!NOTE]
> Есть несколько дополнительных действий для списания пароля за пределами контрольного окна в Azure AD Connect. Дополнительные сведения см. в [статью How-to: настройка записи пароля.](/azure/active-directory/authentication/howto-sspr-writeback) 

Если вы также хотите управлять устройствами Windows 10, присоединив к домену, см. в статью Включить устройства Windows 10, которые будут управляться Microsoft [365 Business Premium,](manage-windows-devices.md) чтобы создать гибридную службу Azure AD Join.