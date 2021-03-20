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
description: Узнайте о согласии пользователей на приложения и о том, как включить их, чтобы позволить сторонним приложениям получать доступ к данным Microsoft 365 пользователей.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914562"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="3a057-103">Управление согласием пользователей на приложения в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3a057-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="3a057-104">Этот параметр позволяет определить, могут ли пользователи давать такое согласие приложениям, которые используют OpenID Connect и OAuth 2.0 для входов и запросов на доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="3a057-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="3a057-105">Приложение может быть создано из вашей организации или из другой организации Office 365 или сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="3a057-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="3a057-106">Если вы включите этот параметр, эти приложения будут просить у пользователей разрешения на доступ к данным организации, и пользователи могут выбрать, разрешить ли это.</span><span class="sxs-lookup"><span data-stu-id="3a057-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="3a057-107">Если вы отключите этот параметр, администраторы должны дать согласие на эти приложения, прежде чем пользователи смогут их использовать.</span><span class="sxs-lookup"><span data-stu-id="3a057-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="3a057-108">В этом случае рассмотрите возможность настройки рабочего процесса согласия администратора на портале Azure, чтобы пользователи могли отправлять запрос на утверждение администратора для использования любого заблокированного приложения.</span><span class="sxs-lookup"><span data-stu-id="3a057-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="3a057-109">Пользователь может предоставить доступ только тем приложениям, которые уже имеют доступ к их данным Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a057-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="3a057-110">Предоставить доступ к другой информации пользователя невозможно.</span><span class="sxs-lookup"><span data-stu-id="3a057-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="3a057-111">Включение или отключение согласия пользователя</span><span class="sxs-lookup"><span data-stu-id="3a057-111">Turning user consent on or off</span></span>
<span data-ttu-id="3a057-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="3a057-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="3a057-113">Вот как включить или отключить согласие пользователя на приложения.</span><span class="sxs-lookup"><span data-stu-id="3a057-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="3a057-114">В центре администрирования перейдите на страницу **Службы** параметров \> **параметров Org,** а затем выберите  >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) согласие пользователя **на приложения.**</span><span class="sxs-lookup"><span data-stu-id="3a057-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="3a057-115">На странице **Согласие пользователя на приложения** выберите вариант, чтобы включить или отключить согласие пользователя.</span><span class="sxs-lookup"><span data-stu-id="3a057-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="3a057-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3a057-116">More info</span></span>
<span data-ttu-id="3a057-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="3a057-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="3a057-118">Подробнее о настройке параметров согласия в активном каталоге Azure читайте в материале Настройка рабочего процесса согласия [администратора.](/azure/active-directory/manage-apps/configure-admin-consent-workflow)</span><span class="sxs-lookup"><span data-stu-id="3a057-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="3a057-119">Чтобы узнать об управлении согласием пользователей на приложения, ознакомьтесь с управлением согласием приложений и [оценкой запросов на согласие.](/azure/active-directory/manage-apps/manage-consent-requests)</span><span class="sxs-lookup"><span data-stu-id="3a057-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests).</span></span>