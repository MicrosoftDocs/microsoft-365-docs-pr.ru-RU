---
title: 'Microsoft 365 Поддержка клиентских приложений: проверка подлинности на основе сертификатов'
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
description: В этой статье сведения о поддержке Microsoft 365 приложений для проверки подлинности на основе сертификатов.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5ebef7c10aa61ba28c8fb841468be244f6e8542
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904999"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 Поддержка клиентских приложений: проверка подлинности на основе сертификатов

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Современная проверка подлинности — это общий термин для сочетания методов проверки подлинности и авторизации. К ним относятся:

- **Методы проверки подлинности:** многофакторная проверка подлинности; Проверка подлинности на основе сертификата клиента.
- **Методы авторизации:** реализация Microsoft open Authorization (OAuth).

Современная проверка подлинности включена с помощью библиотеки проверки подлинности, например Библиотеки проверки подлинности Active Directory (ADAL) или Microsoft Authentication Library (MSAL). Современная проверка подлинности — это то, что клиенты используют для проверки подлинности и авторизации доступа к Microsoft 365 ресурсам. Современная проверка подлинности использует OAuth и предоставляет клиентам безопасный механизм доступа к Microsoft 365, не требуя доступа к учетным данным пользователей. При входе пользователь сдает проверку подлинности непосредственно с помощью Azure Active Directory и получает взамен пару маркеров доступа и обновления. Маркер доступа предоставляет клиенту доступ к соответствующим ресурсам в Microsoft 365 клиента. Маркер обновления используется для получения нового доступа или обновления пары маркеров по истечении срока действия текущего маркера доступа.

Современная проверка подлинности поддерживает различные механизмы проверки подлинности, например проверку подлинности на основе сертификатов. Клиенты на Windows, Android или устройствах iOS могут использовать проверку подлинности на основе сертификатов (CBA) для проверки подлинности Azure Active Directory с помощью клиентского сертификата на устройстве. Вместо обычного имени пользователя или пароля сертификат используется для получения пары маркеров доступа и обновления из Azure Active Directory.

Дополнительные справки [о проверке подлинности на основе сертификатов.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Поддерживаемые & платформы

Последние версии следующих клиентов и платформ поддерживают проверку подлинности на основе сертификатов при входе Azure Active Directory учетных записей в клиенте (например, при добавлении учетной записи в приложение). Дополнительные сведения о поддержке платформы в Microsoft 365 см. в [Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

>[!NOTE]
>Edge для iOS и Android поддерживает проверку подлинности на основе сертификатов во время добавления потоков учетной записи. Edge для iOS и Android не поддерживает проверку подлинности на основе сертификатов при выполнении проверки подлинности на веб-сайтах, которые обычно являются интрасетными сайтами. <br><br>  В этом случае пользователь переходит на веб-сайт (обычно на интрасети), где веб-сайт требует от пользователя проверки подлинности с помощью сертификата. Это вовсе не включает современную проверку подлинности и не использует библиотеку проверки подлинности Майкрософт. Это связано с ограничением для iOS: iOS не позволяет сторонним приложениям получать доступ к системной брекетке, где хранятся сертификаты (доступ к системной брекшетке могут получить только приложения Apple и контроллер веб-просмотров [Safari).](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) <br><br> Так как Edge использует рамки [WebKit](https://developer.apple.com/documentation/webkit) для отрисовки веб-сайтов, Edge не может получить доступ к системной клавише и предоставить пользователю выбор сертификата. Это, к сожалению, обусловлено архитектурой Apple.

## <a name="supported-powershell-modules"></a>Поддерживаемые модули PowerShell

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell в SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

