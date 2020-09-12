---
title: Поддержка клиентских приложений Microsoft 365 — условный доступ
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
ms.openlocfilehash: fd4dcaeda27f12427f3175b7ec52e2fdb0c153da
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546516"
---
# <a name="microsoft-365-client-app-support--conditional-access"></a>Поддержка клиентских приложений Microsoft 365 — условный доступ

На современном рабочем месте пользователи могут получить доступ к ресурсам Организации с помощью различных устройств и приложений из любого места. Таким образом, просто сосредоточиться на том, кто может получить доступ к ресурсу, больше не хватает. Организация также должна поддерживать способ и место доступа к ресурсу в инфраструктуре управления доступом.

С помощью устройства, местоположения и условного доступа на основе многофакторной проверки подлинности с помощью Azure Active Directory (Azure AD) вы можете удовлетворить это новое требование. Условный доступ — это возможность Azure AD, позволяющая применять элементы управления при доступе к приложениям в вашей среде в зависимости от конкретных условий и управлять ими централизованно.

Узнайте больше об [условном доступе Azure AD](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-platforms"></a>Поддерживаемые платформы

 - Windows 10 для настольных ПК
 - Современные приложения Windows 10
 - Веб-браузеры
 - Android
 - iOS
 - macOS<sup>1</sup>

Дополнительные сведения о поддержке платформ в Microsoft 365 приведены в разделе [требования к системе для microsoft 365](https://products.office.com/office-system-requirements).

## <a name="supported-clients"></a>Поддерживаемые клиенты

Последние версии следующих клиентов поддерживают условный доступ:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Значок Azure](../media/o365-azure-64x64.png) <br> [Портал Azure AD <br>](https://azure.microsoft.com/features/azure-portal/) | ![Значок Access](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Значок портала компании](../media/o365-microsoft-64x64.png) <br> [Корпоративный <br> портал ](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal)  | ![Значок кортаны](../media/o365-cortana-64x64.png) <br> [Потребляет](https://www.microsoft.com/cortana) | ![Значок delve](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) 
| ![Значок Dynamics 365](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) | ![Значок пограничного сервера](../media/o365-edge-64x64.png) <br> [Кромки](https://www.microsoft.com/windows/microsoft-edge) | ![Значок Exchange](../media/o365-exchange-64x64.png) <br> [Exchange](https://products.office.com/exchange/exchange-online) | ![Значок Excel](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Значок Forms](../media/o365-forms-64x64.png) <br> [Forms](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) 
| ![Значок Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Значок Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Значок лупы](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Значок администратора Office 365](../media/o365-o365admin-64x64.png) <br> [Администратор Microsoft 365 <br>](https://products.office.com/business/manage-office-365-admin-app) | ![Значок OneDrive для бизнеса](../media/o365-OneDrive-64x64.png) <br> [OneDrive<sup>1</sup>](https://products.office.com/onedrive-for-business/online-cloud-storage) 
| ![Значок OneNote](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Значок Outlook](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) | ![Значок Планировщика](../media/o365-planner-64x64.png) <br> [Планировщик](https://products.office.com/business/task-management-software) | ![Значок PowerApps](../media/o365-powerapps-64x64.png) <br> [PowerApps](https://powerapps.microsoft.com) | ![Значок автоматизированного управления питанием](../media/o365-flow-64x64.png) <br> [Автоматизация управления питанием <br>](https://flow.microsoft.com)
| ![Значок PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com) | ![Значок PowerPoint](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) | ![Значок Project](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Значок Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![Значок SharePoint](../media/o365-sharepoint-64x64.png) <br> [SharePoint](https://products.office.com/sharepoint) 
| ![Значок Skype для бизнеса](../media/o365-skypeforbusiness-64x64.png) <br> [Skype для <br> бизнеса](https://www.skype.com/business/) | ![Значок клейких заметок](../media/o365-stickynotes-64x64.png) <br> [Клейкие заметки](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Значок Stream](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Значок Sway](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Значок Teams](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) 
| ![Значок "to do"](../media/o365-todo-64x64.png) <br> [To-Do](https://todo.microsoft.com) | ![Значок Visio](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Значок Word](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Значок Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview)

## <a name="supported-powershell-modules"></a>Поддерживаемые модули PowerShell

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Значок Azure](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Значок Exchange](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![Значок SharePoint](../media/o365-sharepoint-64x64.png) <br> [PowerShell в SharePoint Online <br>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> поддержка OneDrive в macOS доступна в ближайшее время.

## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)
