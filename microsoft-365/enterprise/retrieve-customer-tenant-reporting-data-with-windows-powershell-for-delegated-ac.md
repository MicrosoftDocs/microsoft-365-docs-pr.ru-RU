---
title: Извлечение данных отчетов клиента с Windows PowerShell для партнеров DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: Сводка. Получайте отчеты от отдельных клиентов, используя удаленный сеанс Windows PowerShell для Microsoft Exchange Online.
ms.openlocfilehash: 24d56fffa60232c4ea39f4fe7769131cab23be2f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693021"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Получение отчетных данных пользовательских клиентов с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Используйте удаленные Windows PowerShell для Microsoft Exchange Online для получения отчетов от отдельных клиентов клиента.
  
Партнеры по синдикации и поставщики облачных решений (CSP) могут получать доступ к данным, которые составляет отчеты клиента, непосредственно через удаленные Windows PowerShell для Exchange Online PowerShell. Это позволяет партнерам собирать и сохранять данные отчетов, а затем выполнять с ней другие операции. После открытия удаленного подключения получить данные отчетов о клиенте клиента идентично запуску любого cmdlet в клиенте клиента.
  
В этой статье вы используете удаленные Windows PowerShell exchange Online, чтобы подключиться к одному клиенту и получить отчет. По умолчанию Windows PowerShell не поддерживает агрегирование данных отчетов из нескольких клиентов. Отчеты, полученные с помощью этой процедуры, можно получить только для  _делегатаOrg,_ к который вы подключаетсяе.
  
 
## <a name="before-you-begin"></a>Перед началом работы

- Для подключения к клиенту Exchange Online необходимо использовать удаленный сеанс Windows PowerShell. Указания см. в статье [Подключение к клиентам Exchange Online с помощью удаленного сеанса Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
## <a name="run-the-get-stalemailboxreport-sample"></a>Запуск примера Get-StaleMailboxReport

Открыв удаленный сеанс с Exchange Online, выполните эту команду, чтобы получить **Get-StaleMailboxReport** для диапазона дат с 25.03.2015 по 31.03.2015.
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Вам доступно много других командлетов для создания отчетов в Exchange Online, Lync Online и SharePoint Online, а также для трассировки сообщений. Дополнительные сведения о доступных командлетах создания отчетов и веб-службе отчетов Office 365 см. в статьях из следующего раздела.
  
## <a name="see-also"></a>См. также

#### 

[Веб-служба отчетов Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532777)
  
[Командлеты отчетов в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=526430)
  
[Справка для партнеров](https://go.microsoft.com/fwlink/p/?LinkID=533477)

