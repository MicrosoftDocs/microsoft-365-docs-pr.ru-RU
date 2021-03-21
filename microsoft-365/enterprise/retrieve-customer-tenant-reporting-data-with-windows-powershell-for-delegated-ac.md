---
title: Извлечение данных отчетности клиента Windows PowerShell для партнеров DAP
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
ms.openlocfilehash: 8ea5f9834bfcc0d517fc1e0938c3547d88d1d8a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927220"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Получение отчетных данных пользовательских клиентов с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Используйте удаленные Windows PowerShell для Microsoft Exchange Online для получения отчетов от отдельных клиентов- клиентов.
  
Партнеры по синдикации и поставщику облачных решений (CSP) могут получать доступ к данным, которые составляет отчеты клиента об клиентах непосредственно через удаленные Windows PowerShell для Exchange Online PowerShell. Это позволяет партнерам собирать и сохранять данные отчетов, а затем выполнять на них другие операции. После открытия удаленного подключения сбор данных отчетов о клиентской аренде идентичен запуску любого комлета в отношении клиента.
  
В этой статье вы используете удаленные Windows PowerShell Exchange Online для подключения к одному клиенту и получения отчета. По умолчанию Windows PowerShell не поддерживает агрегирование данных отчетности из нескольких клиентских тенанций. Отчеты, которые вы извлекаете  с помощью этой процедуры, являются только для делегирования, к который вы подключались.
  
 
## <a name="before-you-begin"></a>Перед началом работы

- Для подключения к клиенту Exchange Online необходимо использовать удаленный сеанс Windows PowerShell. Указания см. в статье [Подключение к клиентам Exchange Online с помощью удаленного сеанса Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)](/powershell/exchange/connect-to-exchange-online-powershell)
    
## <a name="run-the-get-stalemailboxreport-sample"></a>Запуск примера Get-StaleMailboxReport

Открыв удаленный сеанс с Exchange Online, выполните эту команду, чтобы получить **Get-StaleMailboxReport** для диапазона дат с 25.03.2015 по 31.03.2015.
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Вам доступно много других командлетов для создания отчетов в Exchange Online, Lync Online и SharePoint Online, а также для трассировки сообщений. Дополнительные сведения о доступных командлетах создания отчетов и веб-службе отчетов Office 365 см. в статьях из следующего раздела.
  
## <a name="see-also"></a>См. также

#### 

[Веб-служба отчетов Office 365](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))
  
[Командлеты отчетов в Exchange Online](/powershell/module/exchange/get-csclientdevicedetailreport)
  
[Справка для партнеров](https://go.microsoft.com/fwlink/p/?LinkID=533477)