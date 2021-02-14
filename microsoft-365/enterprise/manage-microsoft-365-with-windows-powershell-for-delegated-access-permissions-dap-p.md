---
title: Управление Microsoft 365 с помощью Windows PowerShell для партнеров DAP
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
description: Как партнеры по синдикации и поставщики облачных решений (CSP) могут использовать Windows PowerShell для управления клиентами Microsoft 365.
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429882"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a>Управление Microsoft 365 с помощью Windows PowerShell для партнеров с разрешениями делегирования доступа

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Партнеры по делегированным правам доступа (DAP)  партнеры по синдикации и поставщики облачных решений (CSP). Многие из них являются поставщиками сети или телекоммуникационных услуг. Они объединены в пакет подписок Microsoft 365 в свои предложения по обслуживанию. При продаже подписки На Microsoft 365 им автоматически ируются разрешения на администрирование от имени (AOBO) для клиентов клиента, чтобы они могли администрировать эти клиенты и сообщать о них. Эти задачи сложно выполнять в Центре администрирования Microsoft 365. С помощью PowerShell для Microsoft 365 гораздо проще выполнять такие задачи администрирования, как:
- Список всех customer **TenantIds** и их доменов 
- Определение всех пользователей в клиенте и их лицензий
> [!NOTE]
> Некоторые административные задачи можно выполнять только в PowerShell.

В следующих статьях покажем, как партнеры по синдикации и CSP используют PowerShell для администрирования своих клиентов:
  
- [Управление клиентами Microsoft 365 с помощью Windows PowerShell для партнеров службы разрешений делегирования доступа (DAP)](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [Добавление домена к аренде клиента с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [Подключение к PowerShell Exchange Online](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [Получение отчетных данных пользовательских клиентов с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   