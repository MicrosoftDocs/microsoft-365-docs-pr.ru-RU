---
title: Microsoft 365 интеграции с локальной средой
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: В этой статье узнайте, как интегрировать Microsoft 365 с существующими службами каталогов и локальной средой.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923970"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365 интеграции с локальной средой

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Можно интегрировать Microsoft 365 с существующими локально-доменными службами Active Directory (AD DS) и с локальной установкой Exchange Server, Skype для бизнеса Server 2015 или SharePoint Server.
  
 - При интеграции AD DS можно синхронизировать и управлять учетной записью пользователей для обеих сред. Вы также можете добавить синхронизацию с hash паролем (PHS) или один вход (SSO), чтобы пользователи могли войти в обе среды с учетными данными на месте.
 - При интеграции с локальной серверной продукцией создается гибридная среда. Гибридная среда может помочь при переносе пользователей или сведений в Microsoft 365, или вы можете продолжать иметь некоторых пользователей или некоторые сведения на локальной основе, а некоторые в облаке. Дополнительные сведения о гибридных средах см. в [гибридном облаке.](../solutions/cloud-architecture-models.md#hybrid)

Вы также можете использовать Azure Active Directory (Azure AD) для настраиваемых руководств по настройке в центре администрирования Microsoft 365 (вы должны быть подписаны в Microsoft 365):

- [Руководство по настройке Azure AD](https://aka.ms/aadpguidance)
- [Синхронизация пользователей из каталога вашей организации](https://aka.ms/aadconnectpwsync)
- [Советник по развертыванию служб Федерации Active Directory (AD FS)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Прежде чем начать

Перед интеграцией Microsoft 365 локальной среды необходимо также сделать планирование сети [и настройку производительности.](network-planning-and-performance.md) Кроме того, необходимо разобраться в доступных [моделях удостоверений.](about-microsoft-365-identity.md) 

См. [Microsoft 365 учетные записи](manage-microsoft-365-accounts.md) для списка средств, которые можно использовать для управления Microsoft 365 учетных записей пользователей. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Интеграция Microsoft 365 с AD DS

Если у вас есть существующие учетные записи пользователей в AD DS, вы не хотите повторно создавать все эти учетные записи в Microsoft 365 и рискуете ввести различия или ошибки между средами. Синхронизация каталогов позволяет зеркально отражать эти учетные записи между локальной и интернет-средой. При синхронизации каталогов пользователям не нужно запоминать новые сведения для каждой среды, и вам не нужно создавать или обновлять учетные записи дважды. Вам потребуется подготовить [локальное каталог](prepare-for-directory-synchronization.md) для синхронизации каталогов.
  
![Синхронизация каталогов используется для синхронизации сведений о учетных записях пользователей на локальной основе и учетных записях пользователей в Интернете.](../media/microsoft-365-integration/directory-synchronization.png)
  
Если вы хотите, чтобы пользователи могли войти в систему Microsoft 365 с учетными данными локального пользователя, можно также настроить SSO. С помощью SSO Microsoft 365 настраивается для доверия локальной среде для проверки подлинности пользователей.
  
![С одним входом одна учетная запись доступна как в локальной, так и в онлайн-среде.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Синхронизация каталогов с синхронизацией с хашированием или проверкой подлинности с помощью пароля или без него (PTA)

Пользователь входит в локальное окружение со своей учетной записью пользователя (domain\username). Когда они идут в Microsoft 365, они должны снова войти в систему со своей учетной записью работы или школы (user@domain.com). Имя пользователя одинаково в обеих средах. При добавлении PHS или PTA у пользователя есть один и тот же пароль для обеих сред, но при входе в систему Microsoft 365. Синхронизация каталогов с PHS является наиболее часто используемой синхронизацией каталогов.

Чтобы настроить синхронизацию каталогов, используйте Azure AD Подключение. Инструкции см. [в](set-up-directory-synchronization.md) инструкции Настройка синхронизации каталогов для Microsoft 365 [и Azure AD Подключение с экспресс-настройками.](/azure/active-directory/hybrid/how-to-connect-install-express)

Дополнительные данные [о подготовке к синхронизации каталогов с Microsoft 365](prepare-for-directory-synchronization.md).

### <a name="directory-synchronization-with-sso"></a>Синхронизация каталогов с SSO

Пользователь входит в локальное окружение со своей учетной записью пользователя. При входе в Microsoft 365 они автоматически включались в систему, либо войдут в систему с использованием тех же учетных данных, что и для локальной среды (domain\username).

Чтобы настроить SSO, вы также используете Azure AD Подключение. Инструкции см. в [специальной установке Azure AD Подключение.](/azure/active-directory/hybrid/how-to-connect-install-custom)

Дополнительные сведения см. [в одном входе.](/azure/active-directory/manage-apps/what-is-single-sign-on)

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Подключение старые версии средств интеграции удостоверений, таких как DirSync и Azure AD Sync. Если требуется обновить Azure Active Directory синхронизации с Azure AD Подключение, см. [инструкции по обновлению.](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started) 

## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)