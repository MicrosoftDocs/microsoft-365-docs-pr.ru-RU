---
title: Поддержка клиентских приложений Microsoft 365 — единый вход
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
ms.openlocfilehash: 6f6398736c8ead072374fbc14ee04eec63d3ad18
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546414"
---
# <a name="microsoft-365-client-app-support--single-sign-on"></a>Поддержка клиентских приложений Microsoft 365 — единый вход

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Единый вход (SSO) обеспечивает безопасность и удобство при входе пользователей в приложения в Azure Active Directory (Azure AD). При использовании единого входа пользователи могут войти в систему с одной учетной записью, чтобы получить доступ к устройствам, связанным с доменом, ресурсам компании, программному обеспечению и веб-приложениям.

Дополнительные сведения об использовании [единого входа](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-platforms"></a>Поддерживаемые платформы

 - Windows 10 Desktop<sup>2</sup>
 - Современные приложения Windows 10
 - Веб-браузеры
 - Android<sup>3</sup>
 - iOS<sup>1</sup>
 - macOS<sup>4</sup>

Дополнительные сведения о поддержке платформ в Microsoft 365 приведены в разделе [требования к системе для microsoft 365](https://products.office.com/office-system-requirements).

## <a name="supported-clients"></a>Поддерживаемые клиенты

Последние версии следующих клиентов поддерживают единый вход:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Значок Access](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Значок портала компании](../media/o365-microsoft-64x64.png) <br> [Корпоративный <br> портал<sup>3, 4</sup>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Значок delve](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Значок пограничного сервера](../media/o365-edge-64x64.png) <br> [Edge<sup>1</sup>](https://www.microsoft.com/windows/microsoft-edge) | ![Значок Excel](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) 
| ![Значок Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala<sup>1</sup>](https://products.office.com/en/business/microsoft-kaizala) | ![Значок Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Значок лупы](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Значок OneDrive для бизнеса](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) | ![Значок OneNote](../media/o365-OneNote-64x64.png) <br> [OneNote<sup>2</sup>](https://products.office.com/onenote) 
| ![Значок Outlook](../media/o365-outlook-64x64.png) <br> [Outlook<sup>4</sup>](https://products.office.com/outlook) | ![Значок Планировщика](../media/o365-planner-64x64.png) <br> [Планировщик](https://products.office.com/business/task-management-software) | ![Значок автоматизированного управления питанием](../media/o365-flow-64x64.png) <br> [Автоматизация управления питанием <br>](https://flow.microsoft.com) | ![Значок PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI<sup>2</sup>](https://powerbi.microsoft.com)| ![Значок PowerPoint](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Значок Project](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Значок Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![Значок SharePoint](../media/o365-sharepoint-64x64.png) <br> [SharePoint](https://products.office.com/sharepoint) | ![Значок клейких заметок](../media/o365-stickynotes-64x64.png) <br> [Клейкие заметки](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw)  | ![Значок Sway](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) 
| ![Значок Teams](../media/o365-teams-64x64.png) <br> [Teams<sup>2, 4</sup>](https://products.office.com/microsoft-teams/group-chat-software) | ![Значок "to do"](../media/o365-todo-64x64.png) <br> [To-Do](https://todo.microsoft.com) | ![Значок Visio](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Значок Доски](../media/o365-whiteboard-64x64.png) <br> [Доска<sup>3</sup>](https://whiteboard.microsoft.com/) | ![Значок Word](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) 
| ![Значок Yammer](../media/o365-yammer-64x64.png) <br> [Yammer<sup>2</sup>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a>Поддерживаемые модули PowerShell

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Значок Azure](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Значок Exchange](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![Значок SharePoint](../media/o365-sharepoint-64x64.png) <br> [PowerShell в SharePoint Online <br>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> в ближайшее время доступна поддержка EDGE и Kaizala в iOS. <br>
> <sup>2</sup> поддержка OneNote, PowerBI, Teams и Yammer на рабочем столе Windows 10 доступна в ближайшее время. <br>
> <sup>3</sup> поддержка доски в Android скоро доступна. <br>
> <sup>4</sup> Поддержка Outlook, Teams и корпоративного портала в macOS скоро доступна. <br>

## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)
