---
title: Управление Microsoft 365 с помощью Windows PowerShell партнеров по DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Как партнеры по синдикации и поставщику облачных решений (CSP) могут использовать Windows PowerShell для управления клиентами Microsoft 365.
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909530"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a>Управление Microsoft 365 с помощью Windows PowerShell партнеров по делегированию разрешений доступа

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Партнеры по делегированным правам доступа (DAP)  партнеры по синдикации и поставщики облачных решений (CSP). Многие из них являются сетевыми или телекоммуникационными поставщиками. Они пакет microsoft 365 подписки в свои предложения службы. Когда они продают подписку Microsoft 365, они автоматически получают разрешения администрирования от имени (AOBO) для клиентов, чтобы они могли администрировать и сообщать об этих tenancies. Эти задачи трудно выполнять в центре администрирования Microsoft 365. Гораздо проще использовать PowerShell для Microsoft 365 для выполнения административных задач, таких как:
- Список всех клиентов **TenantIds** и их доменов 
- Определение всех пользователей в клиентской аренде и их назначенных лицензий
> [!NOTE]
> Некоторые административные задачи можно выполнять только в PowerShell.

В следующих статьях покажите, как партнеры По синдикации и CSP используют PowerShell для администрирования своих клиентов:
  
- [Управление клиентами Microsoft 365 с помощью Windows PowerShell партнеров по делегированию разрешений доступа (DAP)](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [Добавление домена к аренде клиента с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [Подключение к PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [Получение отчетных данных пользовательских клиентов с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
