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
description: Синхронизация управляемых доменом пользователей с Microsoft 365 для бизнеса.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841366"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Синхронизация пользователей домена с Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Подготовка к синхронизации каталогов 

Перед синхронизацией пользователей и компьютеров из локального домена Active Directory просмотрите подготовку к синхронизации службы каталогов [с Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization) В частности:

   - Убедитесь, что в каталоге нет дубликатов для следующих атрибутов: **mail,** **proxyAddresses** и **userPrincipalName.** Эти значения должны быть уникальными, и все дубликаты должны быть удалены.
   
   - Рекомендуется настроить атрибут **userPrincipalName** (UPN) для каждой локальной учетной записи пользователя на соответствие основному адресу электронной почты, соответствующему лицензируемому пользователю Microsoft 365. Например: *mary.shelley@contoso.com,* а *не mary@contoso.local*
   
   - Если домен Active Directory заканчивается суффиксом, который не является маршрутизируемым, например *.local* или *.lan,* а не суффиксом с возможностью маршрутизации через Интернет, например *.com* или *.org,* сначала скорректирует суффикс имени пользователя для локальных учетных записей пользователей, как описано в подготовьте ненастраиваемый домен для синхронизации службы каталогов. [](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization) 

The **Run IdFix** in step 4 (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Установка и настройка Azure AD Connect

Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, установите Azure Active Directory Connect и настроите синхронизацию службы каталогов. 

 1. В Центре [администрирования выберите](https://go.microsoft.com/fwlink/p/?linkid=2024339) **"Установка"** в левой области.

 2. Under **Sign-in and security**, choose **View**  under Sync users from **your org's directory**.

 3. На странице **"Синхронизация пользователей с** каталогом организации" выберите **"Начало работы".**

 4. На первом этапе запустите средство IdFix для подготовки к синхронизации каталогов.

 5. Следуйте шагам мастера, чтобы скачать Azure AD Connect и использовать его для синхронизации управляемых доменом пользователей с Microsoft 365.


Дополнительные данные см. в настройках синхронизации службы каталогов [для Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)

При настройке параметров Azure AD Connect рекомендуется включить синхронизацию паролей, единый  вход и функцию записи пароля, которая также поддерживается в Microsoft 365 для бизнеса.

> [!NOTE]
> Кроме этого, в Azure AD Connect необходимо предпринять некоторые дополнительные действия для записи паролей. Дополнительные сведения см. в [пошаговом ок.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) 

Если вы также хотите управлять устройствами с Windows 10, которые присоединились к домену, см. статью "Управление устройствами с Windows 10, которые присоединяются к домену, с помощью [Microsoft 365](manage-windows-devices.md) бизнес премиум", чтобы настроить гибридное присоединиться к Azure AD. 