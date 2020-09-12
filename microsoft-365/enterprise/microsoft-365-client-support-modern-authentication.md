---
title: Поддержка клиентских приложений Microsoft 365 — современная проверка подлинности
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
ms.openlocfilehash: d38b5c11a77af8691aaa5e14d288918b39c0d847
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546306"
---
# <a name="microsoft-365-client-app-support---modern-authentication"></a>Поддержка клиентских приложений Microsoft 365 — современная проверка подлинности

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Современная проверка подлинности включает вход на основе библиотеки проверки подлинности Active Directory (ADAL) для клиентских приложений Office на разных платформах. Это включает функции входа, такие как многофакторная проверка подлинности (MFA), смарт-карта и проверка подлинности на основе сертификатов.

Узнайте больше о [многофакторной проверке подлинности](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) и [проверке подлинности на основе сертификатов](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started).

## <a name="supported-platforms"></a>Поддерживаемые платформы

 - Windows 10 для настольных ПК
 - Современные приложения Windows 10
 - Веб-браузеры<sup>1</sup>
 - Android<sup>2</sup>
 - iOS
 - macOS

Дополнительные сведения о поддержке платформ в Microsoft 365 приведены в разделе [требования к системе для microsoft 365](https://products.office.com/office-system-requirements).

## <a name="supported-clients"></a>Поддерживаемые клиенты

Последние версии следующих клиентов поддерживают современные проверки подлинности:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Значок Access](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Значок Azure](../media/o365-azure-64x64.png) <br> [<br>Портал Azure](https://azure.microsoft.com/features/azure-portal/) | ![Значок портала компании](../media/o365-microsoft-64x64.png) <br> [Корпоративный <br> портал ](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Значок delve](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Значок Dynamics 365](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) 
| ![Значок пограничного сервера](../media/o365-edge-64x64.png) <br> [Кромки](https://www.microsoft.com/windows/microsoft-edge) | ![Значок Excel](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Значок Forms](../media/o365-forms-64x64.png) <br> [Forms](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) | ![Значок Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Значок Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) 
| ![Значок администратора Office 365](../media/o365-o365admin-64x64.png) <br> [Администратор Microsoft 365 <br>](https://products.office.com/business/manage-office-365-admin-app) | ![Значок лупы](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Значок OneDrive для бизнеса](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) |  ![Значок OneNote](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Значок Outlook](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) 
| ![Значок Планировщика](../media/o365-planner-64x64.png) <br> [Планировщик](https://products.office.com/business/task-management-software) | ![Значок PowerApps](../media/o365-powerapps-64x64.png) <br> [PowerApps ](https://powerapps.microsoft.com) | ![Значок автоматизированного управления питанием](../media/o365-flow-64x64.png) <br> [Автоматизация управления питанием <br>](https://flow.microsoft.com) | ![Значок PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com)| ![Значок PowerPoint](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Значок Project](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Значок Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![Значок SharePoint](../media/o365-sharepoint-64x64.png) <br> [SharePoint](https://products.office.com/sharepoint) | ![Значок Skype для бизнеса](../media/o365-skypeforbusiness-64x64.png) <br> [Skype для <br> бизнеса<sup>1</sup>](https://www.skype.com/business/) | ![Значок StaffHub](../media/o365-staffhub-64x64.png) <br> [StaffHub](https://products.office.com/microsoft-staffhub/staff-scheduling-software)
| ![Значок клейких заметок](../media/o365-stickynotes-64x64.png) <br> [Клейкие заметки](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Значок Stream](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Значок Sway](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Значок Teams](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) | ![Значок "to do"](../media/o365-todo-64x64.png) <br> [To-Do](https://todo.microsoft.com) 
| ![Значок Visio](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Значок Доски](../media/o365-whiteboard-64x64.png) <br> [Доска<sup>1</sup>,<sup>2</sup>](https://whiteboard.microsoft.com/) | ![Значок Word](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Значок Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview) | ![Значок Yammer](../media/o365-yammer-64x64.png) <br> [Уведомление об Yammer <br>](https://products.office.com/yammer/yammer-overview) |  |

## <a name="supported-powershell-modules"></a>Поддерживаемые модули PowerShell

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Значок Azure](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Значок Exchange](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![Значок SharePoint](../media/o365-sharepoint-64x64.png) <br> [PowerShell в SharePoint Online <br>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> в ближайшее время доступна поддержка досок и Skype для бизнеса в веб-приложении. <br>
> <sup>2</sup> поддержка доски в Android скоро доступна.

## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)
