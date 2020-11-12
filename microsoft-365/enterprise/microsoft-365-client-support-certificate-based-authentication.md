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
description: В этой статье вы найдете сведения о поддержке клиентских приложений Microsoft 365 для проверки подлинности на основе сертификатов.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57ced47c268f4d0515acb26aa8f705fa6e9ae0f9
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999388"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Поддержка клиентских приложений Microsoft 365: проверка подлинности на основе сертификатов

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Современная проверка подлинности — это термин, который используется для сочетания методов проверки подлинности и авторизации. Они включают:

- **Способы проверки** подлинности: многофакторная проверка подлинности; Проверка подлинности на основе сертификата клиента.
- **Методы проверки подлинности** : реализация Open Authorization (OAuth) корпорации Майкрософт.

Современная проверка подлинности включена с помощью библиотеки проверки подлинности, например библиотеки проверки подлинности Active Directory (ADAL) или библиотеки проверки подлинности (Майкрософт) (MSAL). Современная проверка подлинности используется клиентами для проверки подлинности и авторизации доступа к ресурсам Microsoft 365. Современная проверка подлинности использует OAuth и обеспечивает безопасный механизм для доступа клиентов к службам Microsoft 365 без необходимости доступа к учетным данным пользователя. При входе пользователь выполняет проверку подлинности непосредственно с помощью Azure Active Directory и получает по возвращении лексему доступа и обновления. Маркер доступа предоставляет клиенту доступ к соответствующим ресурсам в клиенте Microsoft 365. Маркер обновления используется для получения новой связи маркера доступа или обновления при истечении срока действия текущего маркера доступа.

Современная проверка подлинности поддерживает различные механизмы проверки подлинности, например проверку подлинности на основе сертификатов. Клиенты на устройствах с Windows, Android или iOS могут использовать проверку подлинности на основе сертификатов (CBA) для проверки подлинности в Azure Active Directory с помощью сертификата клиента на устройстве. Вместо обычного имени пользователя и пароля сертификат используется для получения набора маркеров доступа и обновления из Azure Active Directory.

Узнайте больше о [проверке подлинности на основе сертификатов](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Поддерживаемые клиенты & платформы

Последние версии следующих клиентов и платформ поддерживают проверку подлинности на основе сертификатов при входе в учетные записи Azure Active Directory в клиенте (например, при добавлении учетной записи в приложение). Дополнительные сведения о поддержке платформ в Microsoft 365 приведены в разделе [требования к системе для microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Клиенты | Android | iOS | "Mac";| Windows 10 <br> Современные приложения| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Администратор Azure Active Directory | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Access | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Администратор Azure | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Корпоративный портал | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Потребляет | Календар | Календар | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Delve | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Edge<sup>1</sup> | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Excel | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Администратор Exchange Online | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Forms | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Администратор Office 365 | Н/Д | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |  |
| Kaizala | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Office Lens| ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Office Mobile | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Портал Office | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| OneDrive | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Календар | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
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
| Администратор SharePoint Online | Календар | Календар | Н/Д | Н/Д | Н/Д |
| Клейкие заметки | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Stream | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | Н/Д |
| Sway | Н/Д | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Teams | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д | Календар |
| To-Do | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Visio | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д | Н/Д | ![Поддерживается](../media/check-mark.png) |
| Доска | Календар | Календар | Н/Д | ![Поддерживается](../media/check-mark.png) | Н/Д |
| Word | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) |
| Анализ рабочей области | Н/Д | Н/Д | Н/Д | Н/Д | Н/Д |
| Yammer | ![Поддерживается](../media/check-mark.png) | ![Поддерживается](../media/check-mark.png) | Календар | Н/Д | Календар |

>[!NOTE]
><sup>1</sup> Edge для iOS и Android поддерживает проверку подлинности на основе сертификатов во время выполнения учетной записи Добавление потоков. EDGE для iOS и Android не поддерживает проверку подлинности на основе сертификатов при проверке подлинности на веб-сайтах, которые обычно являются сайтами интрасети. <br><br>  В этом сценарии пользователь переходит на веб-сайт (обычно в интрасети), где веб-сайт требует, чтобы пользователь прошел проверку подлинности с помощью сертификата. При этом не используется современная проверка подлинности и не используется библиотека проверки подлинности Майкрософт. Это связано с ограничением на iOS: iOS запрещают сторонним приложениям доступ к цепочке ключей системы, в которой хранятся сертификаты (только приложения Apple и [контроллер Safari вебвиев](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) могут получать доступ к цепочке ключей системы). <br><br> Как пограничный, пограничный сервер полагается на WebKit, пограничный сервер не может получить доступ к цепочке ключей системы и предоставить пользователю выбор сертификата. Это, к сожалению, разрабатывается в соответствии с архитектурой Apple.

## <a name="supported-powershell-modules"></a>Поддерживаемые модули PowerShell

- [PowerShell Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell в SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

