---
title: Предварительные требования для гостевых учетных записей
description: Рекомендации по настройке гостевых учетных записей и их настройке
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
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="3369b-104">Предварительные требования для гостевых учетных записей</span><span class="sxs-lookup"><span data-stu-id="3369b-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="3369b-105">Для доступа к гостевой учетной записи в организации Azure AD требуются следующие параметры компьютера, управляемого Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3369b-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="3369b-106">Вы можете настроить эти параметры на портале [Azure](https://portal.azure.com) в области **"Внешние удостоверения/ Внешняя совместная работа":**</span><span class="sxs-lookup"><span data-stu-id="3369b-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="3369b-107">**Администраторы и пользователи в роли приглашенного гостя могут приглашать** гостей со значением **"Да"**</span><span class="sxs-lookup"><span data-stu-id="3369b-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="3369b-108">Для **ограничений совместной работы** выберите один из указанных вариантов.</span><span class="sxs-lookup"><span data-stu-id="3369b-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="3369b-109">Если выбрано **разрешение на отправление** приглашений на любой домен (включительно), прочие настройки не требуются.</span><span class="sxs-lookup"><span data-stu-id="3369b-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="3369b-110">При выборе **запрета приглашений** на указанные домены убедитесь, что Microsoft.com в целевых доменах нет.</span><span class="sxs-lookup"><span data-stu-id="3369b-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="3369b-111">Если выбрано разрешение приглашений только для указанных доменов **(наиболее**  строгих), убедитесь, что Microsoft.com указаны в целевых доменах.</span><span class="sxs-lookup"><span data-stu-id="3369b-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="3369b-112">Если вы устанавливаете ограничения, взаимодействующие с этими настройками, не забудьте исключить учетные записи современных рабочих служб Azure Active **Directory.**</span><span class="sxs-lookup"><span data-stu-id="3369b-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="3369b-113">Например, если у вас есть политика условного доступа, которая не позволяет гостевых  учетным записям получать доступ к порталу Intune, исключите группу "Учетные записи современных рабочих мест" из этой политики.</span><span class="sxs-lookup"><span data-stu-id="3369b-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

