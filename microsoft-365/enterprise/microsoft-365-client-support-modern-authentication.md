---
title: 'Поддержка клиентских приложений Microsoft 365: современная проверка подлинности'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: В этой статье рассказывается о том, какие платформы, клиенты и модули PowerShell поддерживают современные проверки подлинности для Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 290a151e127b05e984b9d262c3b429b561201545
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806672"
---
# <a name="microsoft-365-client-app-support-modern-authentication"></a>Поддержка клиентских приложений Microsoft 365: современная проверка подлинности

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Современная проверка подлинности включает вход на основе библиотеки проверки подлинности Active Directory (ADAL) для клиентских приложений Office на разных платформах. Это включает функции входа, такие как многофакторная проверка подлинности (MFA), смарт-карта и проверка подлинности на основе сертификатов.

Узнайте больше о [многофакторной проверке подлинности](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) и [проверке подлинности на основе сертификатов](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Поддерживаемые клиенты & платформы

Последние версии следующих клиентов и платформ поддерживают современные проверки подлинности. Дополнительные сведения о поддержке платформ в Microsoft 365 приведены в разделе [требования к системе для microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Клиенты | Android | iOS | "Mac";| Windows 10; <br> Современные приложения| Windows 10; <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Администратор Azure Active Directory | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Доступ | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Администратор Azure | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Корпоративный портал | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Потребляет | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Delve | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Microsoft Edge | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Excel | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Администратор Exchange Online | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Forms | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Администратор Office 365 | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |  |
| Kaizala | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Office Lens| ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Office Mobile | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Портал Office | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| OneDrive | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| OneNote | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Outlook | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Планировщик | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Power Apps | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Power Automate | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Power BI | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| PowerPoint | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Project | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Publisher | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Skype для бизнеса | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Администратор Skype для бизнеса | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| SharePoint | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Администратор SharePoint Online | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Клейкие заметки | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Stream | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Sway | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Teams | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) |
| To-Do | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Visio | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Доска | Календар | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Word | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Анализ рабочей области | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Yammer | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Поддерживаемые модули PowerShell

- [PowerShell Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell в SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)