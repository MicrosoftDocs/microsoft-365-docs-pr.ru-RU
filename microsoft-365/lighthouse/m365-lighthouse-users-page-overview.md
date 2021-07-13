---
title: Microsoft 365 Lighthouse Обзор страницы пользователей
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Для поставщиков управляемых служб (MSP) с помощью Microsoft 365 Lighthouse, узнайте о странице Пользователи.
ms.openlocfilehash: 795e387850bd2945c4019cbb467de87fecc15f86
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395313"
---
# <a name="microsoft-365-lighthouse-users-page-overview"></a><span data-ttu-id="30678-103">Microsoft 365 Lighthouse Обзор страницы пользователей</span><span class="sxs-lookup"><span data-stu-id="30678-103">Microsoft 365 Lighthouse Users page overview</span></span> 

> [!NOTE]
> <span data-ttu-id="30678-104">Функции, описанные в этой статье, подлежат изменениям и доступны только партнерам, которые соответствуют [требованиям.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="30678-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="30678-105">Если в организации нет Microsoft 365 Lighthouse, [см.](m365-lighthouse-sign-up.md)в Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="30678-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="30678-106">Microsoft 365 Lighthouse позволяет управлять пользователями во всех учетных  записях клиента, выбрав пользователей в левой области навигации, чтобы открыть страницу Пользователи.</span><span class="sxs-lookup"><span data-stu-id="30678-106">Microsoft 365 Lighthouse lets you manage users across tenant accounts by selecting **Users** in the left navigation pane to open the Users page.</span></span> <span data-ttu-id="30678-107">На этой странице можно искать пользователей, оценивать состояние безопасности учетных записей пользователей и действовать в них.</span><span class="sxs-lookup"><span data-stu-id="30678-107">From this page, you can search for users and assess and act on the security state of your user accounts.</span></span> <span data-ttu-id="30678-108">Вы также можете просмотреть сведения о рискованных пользователях и состоянии многофакторной проверки подлинности и сброса пароля самообслуживления.</span><span class="sxs-lookup"><span data-stu-id="30678-108">You can also view insights into risky users and the status of multifactor authentication and self-service password reset.</span></span>  
  
## <a name="search-users-tab"></a><span data-ttu-id="30678-109">Вкладка "Пользователи поиска"</span><span class="sxs-lookup"><span data-stu-id="30678-109">Search users tab</span></span>  
  
<span data-ttu-id="30678-110">На вкладке Пользователи поиска можно быстро искать клиентов для определенных пользователей и выполнять основные действия по управлению пользователями, такие как сброс пароля учетной записи.</span><span class="sxs-lookup"><span data-stu-id="30678-110">From the Search users tab, you can quickly search across tenants for specific users and perform basic user management actions such as resetting an account password.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="Снимок экрана вкладки пользователей поиска.":::

## <a name="risky-users-tab"></a><span data-ttu-id="30678-112">Вкладка "Рискованные пользователи"</span><span class="sxs-lookup"><span data-stu-id="30678-112">Risky users tab</span></span>

<span data-ttu-id="30678-113">На вкладке "Рискованные пользователи" показаны учетные записи пользователей в клиентах, помеченные для рискованного поведения.</span><span class="sxs-lookup"><span data-stu-id="30678-113">The Risky Users tab shows user accounts across your tenants that have been flagged for risky behavior.</span></span> <span data-ttu-id="30678-114">Выберите любого из пользователей, чтобы просмотреть дополнительные сведения об обнаруженом риске или смягчить риск, сбросив пароль пользователя или заблокировав вход.</span><span class="sxs-lookup"><span data-stu-id="30678-114">Select any of the users to view more information on a detected risk or to mitigate a risk by resetting a user's password or blocking sign-in.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="Снимок экрана вкладки Рискованные пользователи.":::

## <a name="multifactor-authentication-tab"></a><span data-ttu-id="30678-116">Вкладка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="30678-116">Multifactor Authentication tab</span></span>

<span data-ttu-id="30678-117">Вкладка Многофакторной проверки подлинности предоставляет подробные сведения о состоянии многофакторной проверки подлинности (MFA) для клиентов.</span><span class="sxs-lookup"><span data-stu-id="30678-117">The Multifactor Authentication tab provides detailed information on the status of multifactor authentication (MFA) enablement across your tenants.</span></span> <span data-ttu-id="30678-118">Выберите любого клиента в списке, чтобы узнать дополнительные сведения для этого клиента, в том числе, какие политики условного доступа, требующие MFA, уже настроены и какие пользователи еще не зарегистрированы для MFA.</span><span class="sxs-lookup"><span data-stu-id="30678-118">Select any tenant in the list to see more details for that tenant, including which Conditional Access policies requiring MFA are already configured and which users have not yet registered for MFA.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="Снимок экрана вкладки Многофакторной проверки подлинности.":::

## <a name="password-reset-tab"></a><span data-ttu-id="30678-120">Вкладка сброса пароля</span><span class="sxs-lookup"><span data-stu-id="30678-120">Password reset tab</span></span>

<span data-ttu-id="30678-121">На вкладке Сброс пароля показаны подробные сведения о состоянии сбросить пароль самообслуживления для клиентов.</span><span class="sxs-lookup"><span data-stu-id="30678-121">The Password reset tab shows detailed information on the status of self-service password reset enablement across your tenants.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="Снимок экрана вкладки сброса пароля.":::

## <a name="related-content"></a><span data-ttu-id="30678-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="30678-123">Related content</span></span>

<span data-ttu-id="30678-124">[Microsoft 365 Lighthouse страницы соответствия требованиям устройств](m365-lighthouse-device-compliance-page-overview.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="30678-124">[Microsoft 365 Lighthouse device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="30678-125">[Microsoft 365 Lighthouse (статья)](m365-lighthouse-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="30678-125">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
