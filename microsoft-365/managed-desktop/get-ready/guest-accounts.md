---
title: Необходимые условия для учетных записей гостя
description: Рекомендации по настройке учетных записей гостя и их корректировки
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073228"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="01227-104">Необходимые условия для учетных записей гостя</span><span class="sxs-lookup"><span data-stu-id="01227-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="01227-105">Для доступа к рабочему столу, управляемому Майкрософт, необходимы следующие параметры в Организации Azure AD для доступа к учетным записям гостей.</span><span class="sxs-lookup"><span data-stu-id="01227-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="01227-106">Эти параметры можно настроить на [портале Azure](https://portal.azure.com) в разделе **Внешние удостоверения/внешняя совместная работа**.</span><span class="sxs-lookup"><span data-stu-id="01227-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration** :</span></span>

-   <span data-ttu-id="01227-107">" **Администраторы" и "Пользователи" в роли гостя могут приглашать** установить значение **"Да"** .</span><span class="sxs-lookup"><span data-stu-id="01227-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="01227-108">Для **ограничений совместной работы** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="01227-108">For **Collaboration restrictions** , choose any of these options:</span></span>
    -   <span data-ttu-id="01227-109">Если выбран параметр **Разрешить отправку приглашений в любой домен (большинство включительно)** , другие настройки не требуются.</span><span class="sxs-lookup"><span data-stu-id="01227-109">If you select **Allow invitations to be sent to any domain (most inclusive)** , no other configuration required.</span></span>
    -   <span data-ttu-id="01227-110">Если выбран параметр **запретить приглашения для указанных доменов** , убедитесь, что Microsoft.com не указан в списке целевые домены.</span><span class="sxs-lookup"><span data-stu-id="01227-110">If you select **Deny invitations to the specified domains** , make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="01227-111">Если выбран параметр **Разрешить приглашения только для указанных доменов (наиболее ограниченный)** , убедитесь, *что Microsoft.com указан* в целевых доменах.</span><span class="sxs-lookup"><span data-stu-id="01227-111">If you select **Allow invitations only to the specified domains (most restrictive)** , make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="01227-112">Если вы задаете ограничения, которые взаимодействуют с этими параметрами, обязательно исключите **учетные записи службы современного рабочего места** Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="01227-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="01227-113">Например, если у вас есть политика условного доступа, которая предотвращает доступ гостевых учетных записей к порталу Intune, исключите группу **служебных учетных записей современного рабочего места** из этой политики.</span><span class="sxs-lookup"><span data-stu-id="01227-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

