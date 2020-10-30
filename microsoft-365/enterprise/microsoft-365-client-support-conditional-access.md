---
title: 'Поддержка клиентских приложений Microsoft 365: условный доступ'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: В этой статье рассказывается о том, какие платформы, клиенты и модули PowerShell поддерживают условный доступ для Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc187a26cd3aa644888312327b07fc9a116950cc
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806686"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Поддержка клиентских приложений Microsoft 365: условный доступ

На современном рабочем месте пользователи могут получить доступ к ресурсам Организации с помощью различных устройств и приложений из любого места. Таким образом, просто сосредоточиться на том, кто может получить доступ к ресурсу, больше не хватает. Организация также должна поддерживать способ и место доступа к ресурсу в инфраструктуре управления доступом.

С помощью устройства, расположения и условного доступа с использованием многофакторной проверки подлинности Azure Active Directory вы можете удовлетворить это новое требование. Условный доступ — это возможность Azure Active Directory, которая позволяет принудительно применять элементы управления для доступа к приложениям в вашей среде, в зависимости от конкретных условий и управления ими из центрального расположения.

Узнайте больше о [условном доступе к Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-clients--platforms"></a>Поддерживаемые клиенты & платформы

Последние версии следующих клиентов и платформ поддерживают условный доступ. Дополнительные сведения о поддержке платформ в Microsoft 365 приведены в разделе [требования к системе для microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

<br>
<br>

| Клиенты | Android | iOS | "Mac";| Windows 10; <br> Современные приложения| Windows 10; <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Администратор Azure Active Directory | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Доступ | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Администратор Azure | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Корпоративный портал | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Потребляет | Календар | Календар | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
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
| Power Apps | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Календар | Н/Д |
| Power Automate | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Power BI | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| PowerPoint | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Project | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Publisher | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Skype для бизнеса | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д ||
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
