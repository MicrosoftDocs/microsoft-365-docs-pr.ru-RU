---
title: Обновление записей MX для перехода на глобальную службу Exchange Online
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как перейти от Microsoft Cloud Германия Exchange Online к глобальной службе Exchange Online.
ms.openlocfilehash: 41628b3032f5b268d5e32501b393fef31663dfc3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399234"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="a4cf6-103">Обновление записей MX для перехода на глобальную службу Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a4cf6-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="a4cf6-104">Войдите на [портал администрирования Microsoft 365](https://admin.microsoft.com)и перейдите к разделу **Settings**  >  **домены** параметров</span><span class="sxs-lookup"><span data-stu-id="a4cf6-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="a4cf6-105">Состояние будет отображаться в правой части каждого домена.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="a4cf6-106">Если домены вашей организации указывают на Microsoft Cloud Германии Exchange Online, вам потребуется обновить запись MX.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="a4cf6-107">Щелкните домен, а затем щелкните **обнаруженные ошибки DNS, щелкните здесь, чтобы просмотреть его**.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="a4cf6-108">На этой странице будут представлены инструкции по исправлению записи MX.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="a4cf6-109">Если регистратор домена использует [Подключение к домену](../setup/add-domain.md#registrars-with-domain-connect), можно нажать кнопку "исправить мои записи" в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="a4cf6-110">В противном случае можно перейти по ссылке в мастере, чтобы получить пошаговые **инструкции** для регистратора.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>