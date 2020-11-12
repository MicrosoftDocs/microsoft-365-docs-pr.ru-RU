---
title: Управление согласия пользователя для приложений в Microsoft 365
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
description: Узнайте о согласии пользователей для приложений и о том, как включить их, чтобы предоставить сторонним приложениям доступ к сведениям о пользователях Microsoft 365.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999587"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="6bf6e-103">Управление согласия пользователя для приложений в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6bf6e-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="6bf6e-104">Этот параметр определяет, могут ли пользователи предоставлять согласие на доступ к приложениям, использующим OpenID Connect и OAuth 2,0 для входа и запросов на доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="6bf6e-105">Приложение может быть создано из вашей организации или из другой организации Office 365 или стороннего производителя.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="6bf6e-106">Если включить этот параметр, эти приложения будут запрашивать у пользователей разрешение на доступ к данным вашей организации, а пользователи могут выбрать, следует ли разрешить их.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="6bf6e-107">Если отключить этот параметр, администраторы должны согласиться с этими приложениями, прежде чем пользователи смогут их использовать.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="6bf6e-108">В этом случае рекомендуется настроить рабочий процесс согласия администратора на портале Azure, чтобы пользователи могли отправлять запрос на утверждение администратором на использование любого заблокированного приложения.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="6bf6e-109">Пользователь может предоставить доступ только тем приложениям, которые уже имеют доступ к их данным Office 365.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="6bf6e-110">Предоставить доступ к другой информации пользователя невозможно.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="6bf6e-111">Включение и выключение согласия пользователя</span><span class="sxs-lookup"><span data-stu-id="6bf6e-111">Turning user consent on or off</span></span>
<span data-ttu-id="6bf6e-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="6bf6e-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="6bf6e-113">Вот как можно включить или отключить согласие пользователя на приложения.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="6bf6e-114">В центре администрирования перейдите на **Settings** \> страницу "службы **параметров организации параметров Организации** "  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) , а затем выберите **согласие пользователя для приложений**.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="6bf6e-115">На странице " **согласие пользователя — приложения** " выберите параметр для включения или отключения согласия пользователя.</span><span class="sxs-lookup"><span data-stu-id="6bf6e-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="6bf6e-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="6bf6e-116">More info</span></span>
<span data-ttu-id="6bf6e-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="6bf6e-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="6bf6e-118">Чтобы узнать, как настроить параметры согласия в Azure Active Directory, прочитайте статью [Настройка рабочего процесса разрешения администратора](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span><span class="sxs-lookup"><span data-stu-id="6bf6e-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="6bf6e-119">Чтобы узнать об управлении согласия пользователя для приложений, прочитайте о том, как [управлять согласиеми на приложения и оценивать запросы согласия](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span><span class="sxs-lookup"><span data-stu-id="6bf6e-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>