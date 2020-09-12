---
title: Миграция почтовых ящиков Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: В этой статье представлен краткий обзор миграции почтовых ящиков Microsoft 365 и список командлетов, используемых для миграции.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63080643e4994d6b16e77298907725a827997cef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546802"
---
# <a name="microsoft-365-mailbox-migrations"></a><span data-ttu-id="0cb56-103">Миграция почтовых ящиков Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0cb56-103">Microsoft 365 mailbox migrations</span></span>

<span data-ttu-id="0cb56-104">С помощью гибридного развертывания на основе Exchange клиенты могут выбрать, как переместить локальные почтовые ящики Exchange в организацию [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) или переместить почтовые ящики Exchange Online в [локальную организацию Exchange](https://docs.microsoft.com/Exchange/exchange-server) .</span><span class="sxs-lookup"><span data-stu-id="0cb56-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="0cb56-105">Пакеты миграции используются при перемещении почтовых ящиков между локальной организацией и организацией Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0cb56-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span>

<span data-ttu-id="0cb56-106">Пользователи могут просматривать статистику и другие сведения о миграции почтовых ящиков с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="0cb56-106">Customers can review statistics and other information about mailbox migrations with the following cmdlets:</span></span>

- <span data-ttu-id="0cb56-107">[Get – MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): предоставляет статистику по умолчанию для почтового ящика пользователя, включающую состояние, размер почтового ящика, размер архивного почтового ящика и процент выполнения.</span><span class="sxs-lookup"><span data-stu-id="0cb56-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size, and percentage complete.</span></span>
- <span data-ttu-id="0cb56-108">[Get/Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): содержит сводный список объектов и атрибутов почтовых ящиков в Организации.</span><span class="sxs-lookup"><span data-stu-id="0cb56-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="0cb56-109">[Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): предоставляет список существующих объектов с включенной поддержкой почты, таких как почтовые ящики, почтовые пользователи, контакты и группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="0cb56-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts, and distribution groups.</span></span>
- <span data-ttu-id="0cb56-110">[Get – MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): предоставляет подробные сведения о состоянии текущей миграции почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="0cb56-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="0cb56-111">[Get – MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): сведения о перемещении и миграции почтовых ящиков пользователей.</span><span class="sxs-lookup"><span data-stu-id="0cb56-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="0cb56-112">[Get – MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): содержит сведения о состоянии текущего пакета миграции.</span><span class="sxs-lookup"><span data-stu-id="0cb56-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="0cb56-113">[Get – мигратионусерстатистикс](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): предоставляет подробные сведения о состоянии миграции для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="0cb56-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="0cb56-114">[Get – MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): предоставляет сведения о почтовых ящиках, например размер, количество сообщений и время последнего обращения.</span><span class="sxs-lookup"><span data-stu-id="0cb56-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="0cb56-115">Дополнительные сведения о командлетах приведены [в статье Move and Migration командлеты в Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0cb56-115">For more information about cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span></span>
