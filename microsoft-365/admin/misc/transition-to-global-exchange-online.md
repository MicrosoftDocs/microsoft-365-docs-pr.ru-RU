---
title: Обновление записей MX для перехода на глобальную Exchange Online службу
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как перейти от Microsoft Cloud Germany Exchange Online к глобальной Exchange Online службе
ms.openlocfilehash: 8de64e30205b07a0c20a8ae4f7cdedbf6cc6824f
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644859"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="0593f-103">Обновление записей MX для перехода на глобальную Exchange Online службу</span><span class="sxs-lookup"><span data-stu-id="0593f-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="0593f-104">Войдите в [Microsoft 365 портал администрирования](https://admin.microsoft.com)и перейдите **в Параметры**  >  **домены**</span><span class="sxs-lookup"><span data-stu-id="0593f-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="0593f-105">Состояние будет показано справа для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="0593f-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="0593f-106">Если домены организации указывают на microsoft Cloud Germany Exchange Online, вам потребуется обновить запись MX.</span><span class="sxs-lookup"><span data-stu-id="0593f-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="0593f-107">Щелкните домен, а затем щелкните обнаруженные ошибки **DNS, щелкните здесь, чтобы просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="0593f-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="0593f-108">На этой странице будут указаны инструкции по исправлению записи MX.</span><span class="sxs-lookup"><span data-stu-id="0593f-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="0593f-109">Если регистратор домена использует [домен Подключение,](../setup/add-domain.md#registrars-with-domain-connect)вы можете нажать кнопку "Исправление записей" сверху.</span><span class="sxs-lookup"><span data-stu-id="0593f-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="0593f-110">В противном случае вы можете  следовать ссылке мастера на пошаговую инструкцию для регистратора.</span><span class="sxs-lookup"><span data-stu-id="0593f-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>