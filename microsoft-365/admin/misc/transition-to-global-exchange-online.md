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
ms.openlocfilehash: 93eab2c4e0ab2f841359061ebdca69967d8d7d33
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363875"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="4041a-103">Обновление записей MX для перехода на глобальную Exchange Online службу</span><span class="sxs-lookup"><span data-stu-id="4041a-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="4041a-104">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com)и перейдите **в Параметры**  >  **домены**</span><span class="sxs-lookup"><span data-stu-id="4041a-104">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="4041a-105">Состояние будет показано справа для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="4041a-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="4041a-106">Если домены организации указывают на microsoft Cloud Germany Exchange Online, вам потребуется обновить запись MX.</span><span class="sxs-lookup"><span data-stu-id="4041a-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="4041a-107">Щелкните домен, а затем щелкните обнаруженные ошибки **DNS, щелкните здесь, чтобы просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="4041a-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="4041a-108">На этой странице будут указаны инструкции по исправлению записи MX.</span><span class="sxs-lookup"><span data-stu-id="4041a-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="4041a-109">Если регистратор домена использует [домен Подключение,](../setup/add-domain.md#registrars-with-domain-connect)вы можете нажать кнопку "Исправление записей" сверху.</span><span class="sxs-lookup"><span data-stu-id="4041a-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="4041a-110">В противном случае вы можете  следовать ссылке мастера на пошаговую инструкцию для регистратора.</span><span class="sxs-lookup"><span data-stu-id="4041a-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>