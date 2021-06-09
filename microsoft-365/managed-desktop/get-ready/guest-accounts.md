---
title: Предварительные требования для гостевых учетных записей
description: Рекомендации по настройке учетных записей гостей и их корректировка
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694249"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="fd41d-104">Предварительные требования для гостевых учетных записей</span><span class="sxs-lookup"><span data-stu-id="fd41d-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="fd41d-105">компьютеры, управляемые Майкрософт необходимы следующие параметры в организации Azure AD для доступа к учетной записи гостей.</span><span class="sxs-lookup"><span data-stu-id="fd41d-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="fd41d-106">Эти параметры можно настроить на портале [Azure](https://portal.azure.com) в соответствии с настройками внешних удостоверений **и внешних параметров совместной работы:**</span><span class="sxs-lookup"><span data-stu-id="fd41d-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration settings**:</span></span>

-   <span data-ttu-id="fd41d-107">Для **приглашенных приглашений** ограничения, установленные для пользователей-членов и пользователей, назначенных на определенные роли администратора, могут приглашать гостевых пользователей, включая гостей **с разрешениями участников.**</span><span class="sxs-lookup"><span data-stu-id="fd41d-107">For **Guest invite restrictions** set to **Member users and users assigned to specific admin roles can invite guest users including guests with member permissions**</span></span>
-   <span data-ttu-id="fd41d-108">Для **ограничений для совместной работы** выберите любой из этих параметров:</span><span class="sxs-lookup"><span data-stu-id="fd41d-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="fd41d-109">Если вы **выбираете Разрешить приглашения, которые будут отправлены** в любой домен (наиболее включительный), никакой другой конфигурации не требуется.</span><span class="sxs-lookup"><span data-stu-id="fd41d-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="fd41d-110">Если вы выберите **отказ в** приглашениях на указанные домены, убедитесь, что Microsoft.com не указаны в целевых доменах.</span><span class="sxs-lookup"><span data-stu-id="fd41d-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="fd41d-111">Если вы выберите Разрешить приглашения только в указанные домены **(наиболее** ограничительные), убедитесь, что Microsoft.com указаны в целевых доменах. </span><span class="sxs-lookup"><span data-stu-id="fd41d-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="fd41d-112">Если вы устанавливаете ограничения, взаимодействующие с этими настройками, не забудьте исключить Azure Active Directory учетные записи служб на **рабочем месте.**</span><span class="sxs-lookup"><span data-stu-id="fd41d-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="fd41d-113">Например, если у вас есть политика условного доступа, которая не позволяет гостевых учетным записям получать доступ к порталу Intune, исключите группу **учетных** записей служб на современном рабочем месте из этой политики.</span><span class="sxs-lookup"><span data-stu-id="fd41d-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="fd41d-114">Действия, которые необходимо сделать, чтобы быть готовыми</span><span class="sxs-lookup"><span data-stu-id="fd41d-114">Steps to get ready</span></span>

1. <span data-ttu-id="fd41d-115">См. [предварительные условия для компьютеров, управляемых Майкрософт](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="fd41d-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="fd41d-116">Используйте [средства оценки готовности](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="fd41d-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="fd41d-117">[Необходимые условия для учетных записей гостей](guest-accounts.md) (Эта статья)</span><span class="sxs-lookup"><span data-stu-id="fd41d-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="fd41d-118">Конфигурация сети для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fd41d-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="fd41d-119">Подготовка сертификатов и сетевых профилей для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fd41d-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="fd41d-120">Подготовка доступа к локальным ресурсам для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fd41d-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="fd41d-121">Приложения на компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fd41d-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="fd41d-122">Подготовка подключенных дисков для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fd41d-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="fd41d-123">Подготовка ресурсов печати для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fd41d-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
