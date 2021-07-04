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
ms.openlocfilehash: 8a244e1178e64d27d5e0f061d094dccd39bb8275
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290079"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Получение отчетных данных пользовательских клиентов с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Используйте удаленные Windows PowerShell для Microsoft Exchange Online для получения отчетов от отдельных клиентов.

Партнеры по синдикации и поставщик облачных решений (CSP) могут получать доступ к данным, которые составляет отчеты клиента клиента непосредственно через удаленные Windows PowerShell для Exchange Online PowerShell. Это позволяет партнерам собирать и сохранять данные отчетов, а затем выполнять на них другие операции. После открытия удаленного подключения сбор данных отчетов о клиентской аренде идентичен запуску любого комлета в отношении клиента.

В этой статье для подключения Windows PowerShell Exchange Online для подключения к одному клиенту и получения отчета. По умолчанию Windows PowerShell не поддерживает агрегирование данных отчетности из нескольких клиентов. Отчеты, которые вы извлекаете  с помощью этой процедуры, являются только для делегирования, к который вы подключались.

## <a name="before-you-begin"></a>Перед началом работы

- Для подключения к клиенту Exchange Online необходимо использовать удаленный сеанс Windows PowerShell. Указания см. в статье [Подключение к клиентам Exchange Online с помощью удаленного сеанса Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="run-the-get-stalemailboxreport-sample"></a>Запуск примера Get-StaleMailboxReport

Открыв удаленный сеанс с Exchange Online, выполните эту команду, чтобы получить **Get-StaleMailboxReport** для диапазона дат с 25.03.2015 по 31.03.2015.

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Вам доступно много других командлетов для создания отчетов в Exchange Online, Lync Online и SharePoint Online, а также для трассировки сообщений. Дополнительные сведения о доступных командлетах создания отчетов и веб-службе отчетов Office 365 см. в статьях из следующего раздела.

## <a name="see-also"></a>См. также

[Веб-служба отчетов Office 365](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))

[Командлеты отчетов в Exchange Online](/powershell/module/exchange/get-csclientdevicedetailreport)

[Справка для партнеров](https://go.microsoft.com/fwlink/p/?LinkID=533477)
