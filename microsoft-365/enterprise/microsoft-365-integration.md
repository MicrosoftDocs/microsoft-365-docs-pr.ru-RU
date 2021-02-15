---
title: Интеграция Microsoft 365 с локальной средой
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
description: В этой статье вы узнаете, как интегрировать Microsoft 365 с существующими службами каталогов и локальной средой.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384862"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Интеграция Microsoft 365 с локальной средой

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Microsoft 365 можно интегрировать с существующими доменными службами Active Directory (AD DS) и с локальной установкой Exchange Server, Skype для бизнеса Server 2015 или SharePoint Server.
  
 - При интеграции AD DS можно синхронизировать учетные записи пользователей для обеих сред и управлять ими. Вы также можете добавить синхронизацию паролей с помощью PHS или единого входа, чтобы пользователи могли входить в обе среды с помощью своих учетных данных в локальной среде.
 - При интеграции с серверными продуктами локальной среды создается гибридная среда. Гибридная среда может помочь при переносе пользователей или сведений в Microsoft 365, а также по-прежнему иметь некоторых пользователей или некоторые сведения в локальной среде и в облаке. Дополнительные сведения о гибридных средах см. [в гибридном облаке.](../solutions/cloud-architecture-models.md#hybrid)

Вы также можете использовать консультантов Azure Active Directory (Azure AD) для настройки руководства по настройке в Центре администрирования Microsoft 365 (необходимо вошел в Microsoft 365):

- [Руководство по настройке Azure AD](https://aka.ms/aadpguidance)
- [Синхронизация пользователей из каталога организации](https://aka.ms/aadconnectpwsync)
- [Помощник по развертыванию служб федерации Active Directory (AD FS)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Прежде чем начать

Перед интеграцией Microsoft 365 и локальной среды необходимо также спланировать сеть [и настроить производительность.](network-planning-and-performance.md) Кроме того, вам необходимо ознакомиться с доступными [моделями удостоверений.](about-microsoft-365-identity.md) 

Список средств, которые можно использовать для управления учетной записью пользователя Microsoft [365,](manage-microsoft-365-accounts.md) см. в управлении учетной записью Microsoft 365. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Интеграция Microsoft 365 с AD DS

Если у вас уже есть учетные записи пользователей в AD DS, вы не хотите повторно создавать все эти учетные записи в Microsoft 365 и риск возникновения различий или ошибок между средами. Синхронизация каталогов позволяет зеркально отражать эти учетные записи между локальной и сетевой средами. При синхронизации каталогов пользователям не нужно запоминать новые сведения для каждой среды, и вам не нужно создавать или обновлять учетные записи дважды. Вам потребуется подготовить [свой локальной](prepare-for-directory-synchronization.md) каталог для синхронизации каталогов.
  
![Синхронизация каталогов для синхронизации локальной и сетевой учетных записей пользователей](../media/microsoft-365-integration/directory-synchronization.png)
  
Если вы хотите, чтобы пользователи могли входить в Microsoft 365 с помощью своих учетных данных в локальной сети, можно также настроить службу SSO. С помощью SSO Microsoft 365 настроен на доверие локальной среде для проверки подлинности пользователей.
  
![При едином входе одна и та же учетная запись доступна как в локальной, так и в сетевой средах.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Синхронизация каталогов с синхронизацией или без синхронизации с паролем или сквозной проверкой подлинности (PTA)

Пользователь входит в свою локальной среду с помощью своей учетной записи пользователя (домен\имя пользователя). При входе в Microsoft 365 им необходимо снова войти с помощью своей работы или учебной учетной записи (user@domain.com). Имя пользователя одинаково в обеих средах. При добавлении PHS или PTA пользователь имеет один и тот же пароль для обеих сред, но при входе в Microsoft 365 придется снова вводить эти учетные данные. Синхронизация каталогов с помощью PHS — это наиболее часто используемая синхронизация каталогов.

Чтобы настроить синхронизацию службы каталогов, используйте Azure AD Connect. Инструкции см. в настройках синхронизации службы каталогов [для Microsoft 365](set-up-directory-synchronization.md) и [Azure AD Connect с помощью экспресс-параметров.](https://go.microsoft.com/fwlink/p/?LinkId=698537)

Узнайте больше о [подготовке к синхронизации службы каталогов с Microsoft 365.](prepare-for-directory-synchronization.md)

### <a name="directory-synchronization-with-sso"></a>Синхронизация каталогов с SSO

Пользователь входит в свою локальной среду с помощью своей учетной записи. Когда пользователь входит в Microsoft 365, он либо входит в систему автоматически, либо использует те же учетные данные, что и для локальной среды (домен\имя пользователя).

Чтобы настроить службу SSO, также используйте Azure AD Connect. Инструкции см. в [настраиваемой установке Azure AD Connect.](https://go.microsoft.com/fwlink/p/?LinkID=698430)

Дополнительные сведения см. в [документе "Единый вход".](https://go.microsoft.com/fwlink/p/?LinkId=698604)

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect заменяет более старые версии средств интеграции удостоверений, таких как DirSync и Azure AD Sync. Если вы хотите обновить синхронизацию Azure Active Directory с Azure AD Connect, см. [инструкции по обновлению.](https://go.microsoft.com/fwlink/p/?LinkId=733240) 

## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)
