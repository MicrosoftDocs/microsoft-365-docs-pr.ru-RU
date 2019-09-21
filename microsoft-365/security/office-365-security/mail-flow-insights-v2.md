---
title: Аналитика потока обработки почты в Центре безопасности и соответствия требованиям
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Администраторы могут ознакомиться с информационной панелью почтовых ящиков в центре безопасности & соответствия требованиям.
ms.openlocfilehash: a8bc8dbc2dcd25e3b26b35221cadf9534f9f668b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089999"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="9881d-103">Аналитика потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="9881d-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="9881d-104">Администраторы могут использовать панель мониторинга управления почтовыми ящиками в центре безопасности & соответствия требованиям для обнаружения тенденций, аналитических данных и выполнения действий по устранению проблем, связанных с процессом обработки почты в организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="9881d-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="9881d-105">В панели мониторинга почтовых ящиков доступны подробные сведения, отчеты и графические элементы:</span><span class="sxs-lookup"><span data-stu-id="9881d-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="9881d-106">Отчет о карте почтового процесса</span><span class="sxs-lookup"><span data-stu-id="9881d-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="9881d-107">Анализ состояния почтового процесса домена</span><span class="sxs-lookup"><span data-stu-id="9881d-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="9881d-108">Отчет по клиентам проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="9881d-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="9881d-109">Получение сведений о домене отправителя</span><span class="sxs-lookup"><span data-stu-id="9881d-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="9881d-110">Отчет о недоставке</span><span class="sxs-lookup"><span data-stu-id="9881d-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="9881d-111">Отчет о необслуживаемом домене</span><span class="sxs-lookup"><span data-stu-id="9881d-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="9881d-112">Поток обработки исходящей и входящей почты</span><span class="sxs-lookup"><span data-stu-id="9881d-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="9881d-113">Очереди и оповещения о них</span><span class="sxs-lookup"><span data-stu-id="9881d-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="9881d-114">Отчет по автоматически пересылаемым сообщениям</span><span class="sxs-lookup"><span data-stu-id="9881d-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="9881d-115">Аналитика почтового цикла</span><span class="sxs-lookup"><span data-stu-id="9881d-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="9881d-116">Отображение аналитики правил потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="9881d-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="9881d-117">Разрешения, необходимые для просмотра панели мониторинга для почтового процесса</span><span class="sxs-lookup"><span data-stu-id="9881d-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="9881d-118">Панель мониторинга для обработки почты доступна следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9881d-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="9881d-119">Члены роли **глобального администратора Office 365** .</span><span class="sxs-lookup"><span data-stu-id="9881d-119">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="9881d-120">Участники роли **администратора Exchange 365** .</span><span class="sxs-lookup"><span data-stu-id="9881d-120">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="9881d-121">Члены **роли администратора почтового процесса** в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9881d-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="9881d-122">Если эта роль явным образом назначена пользователю, который не является членом роли глобального администратора или администратора Exchange:</span><span class="sxs-lookup"><span data-stu-id="9881d-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="9881d-123">Пользователь должен войти в центр безопасности & соответствия требованиям непосредственно по адресу [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="9881d-123">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="9881d-124">Пользователь будет иметь разрешение только на чтение для панели мониторинга почтового процесса.</span><span class="sxs-lookup"><span data-stu-id="9881d-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="9881d-125">У пользователя не будет доступа к порталу администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="9881d-125">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="9881d-126">Более подробную информацию о роли глобального администратора Office 365 вы найдете в статье [сведения о ролях администратора office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="9881d-126">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="9881d-127">Сведения о назначении пользователям ролей центра обеспечения безопасности &, приведены в статье [предоставление пользователям доступа к центру безопасности & соответствия требованиям](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="9881d-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="9881d-128">Где найти панель мониторинга для почтового процесса</span><span class="sxs-lookup"><span data-stu-id="9881d-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="9881d-129">Перейдите в центр безопасности & соответствия требованиям по [https://protection.office.com](https://protection.office.com)адресу.</span><span class="sxs-lookup"><span data-stu-id="9881d-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="9881d-130">Разверните узел **почтовые ящики** и выберите **панель мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="9881d-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Панель мониторинга почтовых ящиков в центре безопасности Office 365 & соответствия требованиям](../media/mail-flow-dashboard-v2.png)
