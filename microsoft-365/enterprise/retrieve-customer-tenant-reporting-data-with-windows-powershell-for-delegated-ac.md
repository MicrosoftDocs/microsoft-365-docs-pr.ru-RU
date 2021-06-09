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
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="2f345-103">Получение отчетных данных пользовательских клиентов с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="2f345-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="2f345-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="2f345-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2f345-105">Используйте удаленные Windows PowerShell для Microsoft Exchange Online для получения отчетов от отдельных клиентов.</span><span class="sxs-lookup"><span data-stu-id="2f345-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>
  
<span data-ttu-id="2f345-106">Партнеры по синдикации и поставщик облачных решений (CSP) могут получать доступ к данным, которые составляет отчеты клиента клиента непосредственно через удаленные Windows PowerShell для Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f345-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="2f345-107">Это позволяет партнерам собирать и сохранять данные отчетов, а затем выполнять на них другие операции.</span><span class="sxs-lookup"><span data-stu-id="2f345-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="2f345-108">После открытия удаленного подключения сбор данных отчетов о клиентской аренде идентичен запуску любого комлета в отношении клиента.</span><span class="sxs-lookup"><span data-stu-id="2f345-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>
  
<span data-ttu-id="2f345-109">В этой статье для подключения Windows PowerShell Exchange Online для подключения к одному клиенту и получения отчета.</span><span class="sxs-lookup"><span data-stu-id="2f345-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="2f345-110">По умолчанию Windows PowerShell не поддерживает агрегирование данных отчетности из нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="2f345-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="2f345-111">Отчеты, которые вы извлекаете  с помощью этой процедуры, являются только для делегирования, к который вы подключались.</span><span class="sxs-lookup"><span data-stu-id="2f345-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>
  
 
## <a name="before-you-begin"></a><span data-ttu-id="2f345-112">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="2f345-112">Before you begin</span></span>

- <span data-ttu-id="2f345-p103">Для подключения к клиенту Exchange Online необходимо использовать удаленный сеанс Windows PowerShell. Указания см. в статье [Подключение к клиентам Exchange Online с помощью удаленного сеанса Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="2f345-p103">You need to connect to your Exchange Online tenant by using remote Windows PowerShell. For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](/powershell/exchange/connect-to-exchange-online-powershell)</span></span>
    
## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="2f345-115">Запуск примера Get-StaleMailboxReport</span><span class="sxs-lookup"><span data-stu-id="2f345-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="2f345-116">Открыв удаленный сеанс с Exchange Online, выполните эту команду, чтобы получить **Get-StaleMailboxReport** для диапазона дат с 25.03.2015 по 31.03.2015.</span><span class="sxs-lookup"><span data-stu-id="2f345-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="2f345-p104">Вам доступно много других командлетов для создания отчетов в Exchange Online, Lync Online и SharePoint Online, а также для трассировки сообщений. Дополнительные сведения о доступных командлетах создания отчетов и веб-службе отчетов Office 365 см. в статьях из следующего раздела.</span><span class="sxs-lookup"><span data-stu-id="2f345-p104">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use. To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f345-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2f345-119">See also</span></span>

#### 

<span data-ttu-id="2f345-120">[Веб-служба отчетов Office 365](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="2f345-120">[Office 365 Reporting web service](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span></span>
  
[<span data-ttu-id="2f345-121">Командлеты отчетов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2f345-121">Reporting cmdlets in Exchange Online</span></span>](/powershell/module/exchange/get-csclientdevicedetailreport)
  
[<span data-ttu-id="2f345-122">Справка для партнеров</span><span class="sxs-lookup"><span data-stu-id="2f345-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)