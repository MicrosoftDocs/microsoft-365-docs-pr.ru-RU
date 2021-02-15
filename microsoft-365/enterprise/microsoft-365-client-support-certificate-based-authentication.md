---
title: 'Поддержка клиентских приложений Microsoft 365: проверка подлинности на основе сертификатов'
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
description: В этой статье вы найдете сведения о поддержке проверки подлинности на основе сертификатов в клиентских приложениях Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7ab5e4a2575796e37a115b36a4f78add20414ef
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097262"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Поддержка клиентских приложений Microsoft 365: проверка подлинности на основе сертификатов

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Современная проверка подлинности является зонтичным термином для сочетания методов проверки подлинности и авторизации. Такие законодательные акты перечислены ниже.

- **Методы проверки подлинности:** многофакторная проверка подлинности; Проверка подлинности на основе сертификата клиента.
- **Методы авторизации:** реализация корпорацией Майкрософт open Authorization (OAuth).

Современная проверка подлинности включена с помощью библиотеки проверки подлинности, например библиотеки проверки подлинности Active Directory (ADAL) или microsoft Authentication Library (MSAL). Современная проверка подлинности — это то, что клиенты используют для проверки подлинности и авторизации доступа к ресурсам Microsoft 365. Современная проверка подлинности использует OAuth и обеспечивает безопасный механизм доступа клиентов к службам Microsoft 365 без необходимости доступа к учетным данным пользователя. При входе пользователь непосредственно в Azure Active Directory получает пару маркеров доступа и обновления. Маркер доступа предоставляет клиенту доступ к соответствующим ресурсам в клиенте Microsoft 365. Маркер обновления используется для получения новой пары маркеров доступа или обновления по истечении срока действия текущего маркера доступа.

Современная проверка подлинности поддерживает различные механизмы проверки подлинности, например проверку подлинности на основе сертификатов. Клиенты на устройствах с Windows, Android или iOS могут использовать проверку подлинности на основе сертификатов (CBA) для проверки подлинности в Azure Active Directory с помощью сертификата клиента на устройстве. Вместо обычного имени пользователя и пароля сертификат используется для получения пары маркеров доступа и обновления из Azure Active Directory.

Узнайте больше о [проверке подлинности на основе сертификатов.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Поддерживаемые клиенты & платформ

Последние версии следующих клиентов и платформ поддерживают проверку подлинности на основе сертификатов при входе в учетные записи Azure Active Directory в клиенте (например, при добавлении учетной записи в приложение). Дополнительные сведения о поддержке платформы в Microsoft 365 см. в требованиях к системе [для Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

| Клиенты | Android | iOS | "Mac";| Windows 10 <br> Современные приложения| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Администратор Azure Active Directory | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Access | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Администратор Azure | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Портал компании | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Кортана | Planned | Planned | Недоступно | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Delve | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Edge<sup>1</sup> | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Excel | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Администратор Exchange Online | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Forms | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Администратор Office 365 | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |  |
| Kaizala | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Office Lens| ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Office Mobile | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Портал Office | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Недоступно |
| OneDrive | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Planned | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
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
| Администратор SharePoint Online | Planned | Planned | Н/Д | Н/Д | Н/Д |
| Примечания | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Stream | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Sway | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Teams | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно | Planned |
| To Do | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Visio | Недоступно | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Доска | Planned | Planned | Недоступно | ![Поддерживается](../media/check-mark.png) | Недоступно |
| Word | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Рабочая аналитика | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Yammer | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Planned | Недоступно | Planned |

>[!NOTE]
><sup>1</sup> Edge для iOS и Android поддерживает проверку подлинности на основе сертификатов во время добавления потоков учетной записи. Edge для iOS и Android не поддерживает проверку подлинности на основе сертификатов при проверке подлинности на веб-сайтах, которые обычно являются сайтами интрасети. <br><br>  В этом сценарии пользователь переходит на веб-сайт (обычно в интрасети), где для веб-сайта требуется проверка подлинности с помощью сертификата. Это совсем не требует современной проверки подлинности и не использует библиотеку проверки подлинности Майкрософт. Это связано с ограничением iOS: iOS не позволяет сторонним приложениям получать доступ к системной сети ключей, в которой хранятся сертификаты (только приложения Apple и контроллер [веб-view Safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) могут получать доступ к системной ключевыхchain). <br><br> Так как для отрисовки веб-сайтов edge использует структуру [WebKit,](https://developer.apple.com/documentation/webkit) он не может получить доступ к системной сети ключей и предоставить пользователю возможность выбора сертификата. Это, к сожалению, обусловлено архитектурой Apple.

## <a name="supported-powershell-modules"></a>Поддерживаемые модули PowerShell

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell в SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

