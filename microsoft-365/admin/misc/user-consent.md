---
title: Управление согласием пользователей на приложения в Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Узнайте о согласии пользователей на доступ к приложениям и о том, как включить их, чтобы разрешить сторонним приложениям доступ к данным пользователей Microsoft 365.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999587"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="06fd0-103">Управление согласием пользователей на приложения в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06fd0-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="06fd0-104">Этот параметр управляет тем, могут ли пользователи давать это согласие приложениям, которые используют OpenID Connect и OAuth 2.0 для входов и запросов на доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="06fd0-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="06fd0-105">Приложение может быть создано из вашей организации или из другой организации Office 365 или сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="06fd0-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="06fd0-106">Если вы включите этот параметр, эти приложения запросят у пользователей разрешение на доступ к данным вашей организации, и пользователи смогут выбрать, разрешит ли этот параметр.</span><span class="sxs-lookup"><span data-stu-id="06fd0-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="06fd0-107">Если вы отключите этот параметр, администраторы должны дать согласие на использование этих приложений, прежде чем пользователи смогут их использовать.</span><span class="sxs-lookup"><span data-stu-id="06fd0-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="06fd0-108">В этом случае рассмотрите возможность настройки рабочего процесса согласия администратора на портале Azure, чтобы пользователи могли отправлять запрос на утверждение администратора на использование любого заблокированного приложения.</span><span class="sxs-lookup"><span data-stu-id="06fd0-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="06fd0-109">Пользователь может предоставить доступ только тем приложениям, которые уже имеют доступ к их данным Office 365.</span><span class="sxs-lookup"><span data-stu-id="06fd0-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="06fd0-110">Предоставить доступ к другой информации пользователя невозможно.</span><span class="sxs-lookup"><span data-stu-id="06fd0-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="06fd0-111">Включение и отключение согласия пользователя</span><span class="sxs-lookup"><span data-stu-id="06fd0-111">Turning user consent on or off</span></span>
<span data-ttu-id="06fd0-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="06fd0-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="06fd0-113">Вот как включить или отключить согласие пользователя на приложения.</span><span class="sxs-lookup"><span data-stu-id="06fd0-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="06fd0-114">В Центре администрирования перейдите на **страницу** "Службы параметров организации" и выберите согласие \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) пользователя **на приложения.**</span><span class="sxs-lookup"><span data-stu-id="06fd0-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="06fd0-115">На странице **согласия пользователя на приложения** выберите параметр, чтобы включить или отключить согласие пользователя.</span><span class="sxs-lookup"><span data-stu-id="06fd0-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="06fd0-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="06fd0-116">More info</span></span>
<span data-ttu-id="06fd0-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="06fd0-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="06fd0-118">Чтобы узнать, как настроить параметры согласия в Azure Active Directory, прочитайте статью "Настройка рабочего процесса согласия [администратора".](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)</span><span class="sxs-lookup"><span data-stu-id="06fd0-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="06fd0-119">Чтобы узнать об управлении согласием пользователей на приложения, ознакомьтесь с управлением согласием для приложений и оценкой запросов [на получение согласия.](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)</span><span class="sxs-lookup"><span data-stu-id="06fd0-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>