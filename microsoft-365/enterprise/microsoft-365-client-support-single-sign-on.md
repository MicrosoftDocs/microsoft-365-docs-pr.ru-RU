---
title: 'Поддержка клиентских приложений Microsoft 365: один Sign-On'
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
description: В этой статье рассказывается о том, какие платформы, клиенты и модули PowerShell поддерживают единый вход для Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b70f0c1ec4a6e94651b987830c8b29993732a3c2
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806671"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Поддержка клиентских приложений Microsoft 365: один Sign-On

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Единый вход (SSO) обеспечивает безопасность и удобство при входе пользователей в приложения в Azure Active Directory. При использовании единого входа пользователи могут войти в систему один раз с одной учетной записью, чтобы получить доступ к локальным доменным службам Active Directory (AD DS), программному обеспечению и приложениям в виде службы (SaaS) и веб-приложениям.

Дополнительные сведения об использовании [единого входа](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-clients--platforms"></a>Поддерживаемые клиенты & платформы

Последние версии следующих клиентов и платформ поддерживают единый вход. Дополнительные сведения о поддержке платформ в Microsoft 365 приведены в разделе [требования к системе для microsoft 365](https://products.office.com/office-system-requirements).
<br>
<br>

| Клиенты | Android | iOS | "Mac";| Windows 10; <br> Современные приложения| Windows 10; <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Доступ | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Корпоративный портал | Н/Д | ![Поддерживается](../media/check-mark.png) | Календар | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Потребляет | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Delve | Календар | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Microsoft Edge | ![Поддерживается](../media/check-mark.png) | Календар | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Excel | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Kaizala | ![Поддерживается](../media/check-mark.png) | Календар | Н/Д | Н/Д | Н/Д |
| Office Lens| ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Office Mobile | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Портал Office | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| OneDrive | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Календар | ![Поддерживается](../media/check-mark.png) | Календар |
| OneNote | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Календар |
| Outlook | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Календар | ![Поддерживается](../media/check-mark.png) |
| Планировщик | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Power Apps | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Календар | Н/Д |
| Power Automate | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Power BI | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | Календар |
| PowerPoint | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Project | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Publisher | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Skype для бизнеса | Календар | Календар | Н/Д | Н/Д | Н/Д |
| SharePoint | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Клейкие заметки | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Stream | Календар | Календар | Н/Д | Н/Д | Н/Д |
| Sway | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Teams | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Календар | Н/Д | Календар |
| To-Do | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Visio | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Доска | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Word | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Yammer | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Календар |

## <a name="supported-powershell-modules"></a>Поддерживаемые модули PowerShell

- [PowerShell Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell в SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
