---
title: 'Поддержка клиентских приложений Microsoft 365: многофакторная проверка подлинности'
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
description: В этой статье вы узнаете, какие платформы, клиенты и модули PowerShell поддерживают многофакторную проверку подлинности для Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097484"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Поддержка клиентских приложений Microsoft 365: многофакторная проверка подлинности

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Чтобы обеспечить дополнительный уровень безопасности для входов, клиенты могут быть настроены на использование многофакторной проверки подлинности (MFA), которая использует как пароль пользователя, так и дополнительный метод проверки пользователя на основе:

- Что-то в их распоряжении, которое не так просто дублировать, например смартфон.
- Что-то, что есть у пользователя однозначно и однозначно, например отпечатки пальцев, лица или другой биометрический атрибут

Узнайте больше о [многофакторной проверке подлинности.](/azure/active-directory/authentication/multi-factor-authentication)

## <a name="supported-clients--platforms"></a>Поддерживаемые клиенты & платформ

Последние версии следующих клиентов и платформ поддерживают многофакторную проверку подлинности. Дополнительные сведения о поддержке платформы в Microsoft 365 см. в требованиях к системе [для Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

| Клиенты | Android | iOS | "Mac";| Windows 10 <br> Современные приложения| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Администратор Azure Active Directory | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Access | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Администратор Azure | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Портал компании | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Кортана | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Delve | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Microsoft Edge | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Excel | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Администратор Exchange Online | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Forms | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Администратор Office 365 | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |  |
| Kaizala | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Office Lens| ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Office Mobile | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Портал Office | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Недоступно |
| OneDrive | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| OneNote | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Outlook | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Планировщик | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Power Apps | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Power Automate | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Power BI | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| PowerPoint | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Project | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Publisher | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Skype для бизнеса | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно | ![Поддерживается](../media/check-mark.png) |
| Администратор Skype для бизнеса | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| SharePoint | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Администратор SharePoint Online | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Примечания | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Stream | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Sway | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Teams | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно | ![Поддерживается](../media/check-mark.png) |
| To Do | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Visio | Недоступно | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Доска | Planned | ![Поддерживается](../media/check-mark.png) | Недоступно | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Word | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Рабочая аналитика | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Yammer | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно | ![Поддерживается](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Поддерживаемые модули PowerShell

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell в SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)