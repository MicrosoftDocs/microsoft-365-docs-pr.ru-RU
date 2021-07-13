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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Узнайте о согласии пользователей на приложения и о том, как включить их, чтобы позволить сторонним приложениям получать доступ к Microsoft 365 пользователям.
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391235"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="a51b9-103">Управление согласием пользователей на приложения в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a51b9-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="a51b9-104">Этот параметр позволяет определить, могут ли пользователи давать такое согласие приложениям, которые используют openID Подключение и OAuth 2.0 для входов и запросов на доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="a51b9-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="a51b9-105">Приложение может быть создано из вашей организации или из другой Office 365 или сторонних организаций.</span><span class="sxs-lookup"><span data-stu-id="a51b9-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="a51b9-106">Если вы включите этот параметр, эти приложения будут просить у пользователей разрешения на доступ к данным организации, и пользователи могут выбрать, разрешить ли это.</span><span class="sxs-lookup"><span data-stu-id="a51b9-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="a51b9-107">Если вы отключите этот параметр, администраторы должны дать согласие на эти приложения, прежде чем пользователи смогут их использовать.</span><span class="sxs-lookup"><span data-stu-id="a51b9-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="a51b9-108">В этом случае рассмотрите возможность настройки рабочего процесса согласия администратора на портале Azure, чтобы пользователи могли отправлять запрос на утверждение администратора для использования любого заблокированного приложения.</span><span class="sxs-lookup"><span data-stu-id="a51b9-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="a51b9-109">Пользователь может предоставить доступ только тем приложениям, которые уже имеют доступ к их данным Office 365.</span><span class="sxs-lookup"><span data-stu-id="a51b9-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="a51b9-110">Предоставить доступ к другой информации пользователя невозможно.</span><span class="sxs-lookup"><span data-stu-id="a51b9-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="a51b9-111">Включение или отключение согласия пользователя</span><span class="sxs-lookup"><span data-stu-id="a51b9-111">Turning user consent on or off</span></span>

<span data-ttu-id="a51b9-112">Вот как включить или отключить согласие пользователя на приложения.</span><span class="sxs-lookup"><span data-stu-id="a51b9-112">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="a51b9-113">В центре администрирования перейдите на **страницу Параметры** \> **параметров Org Services Services,** а затем выберите согласие  >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) пользователя на **приложения.**</span><span class="sxs-lookup"><span data-stu-id="a51b9-113">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="a51b9-114">На странице **Согласие пользователя на приложения** выберите вариант, чтобы включить или отключить согласие пользователя.</span><span class="sxs-lookup"><span data-stu-id="a51b9-114">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="related-content"></a><span data-ttu-id="a51b9-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="a51b9-115">Related content</span></span> 

<span data-ttu-id="a51b9-116">[Настройка рабочего процесса согласия администратора](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (статья)</span><span class="sxs-lookup"><span data-stu-id="a51b9-116">[Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (article)</span></span>\
<span data-ttu-id="a51b9-117">[Управление согласием на приложения и оценка](/azure/active-directory/manage-apps/manage-consent-requests) запросов на согласие (статья)</span><span class="sxs-lookup"><span data-stu-id="a51b9-117">[Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests) (article)</span></span>