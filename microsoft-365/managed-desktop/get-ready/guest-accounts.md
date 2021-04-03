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
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574611"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="bade8-104">Предварительные требования для гостевых учетных записей</span><span class="sxs-lookup"><span data-stu-id="bade8-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="bade8-105">Для доступа к гостевой учетной записи Microsoft Managed Desktop требуются следующие параметры в организации Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bade8-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="bade8-106">Эти параметры можно настроить на портале Azure в [соответствии](https://portal.azure.com) с **внешними удостоверениями и внешним сотрудничеством:**</span><span class="sxs-lookup"><span data-stu-id="bade8-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="bade8-107">**Администраторы и пользователи в роли приглашенного приглашенного** гостя могут приглашать набор в **Да**</span><span class="sxs-lookup"><span data-stu-id="bade8-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="bade8-108">Для **ограничений для совместной работы** выберите любой из этих параметров:</span><span class="sxs-lookup"><span data-stu-id="bade8-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="bade8-109">Если вы **выбираете Разрешить приглашения, которые будут отправлены** в любой домен (наиболее включительный), никакой другой конфигурации не требуется.</span><span class="sxs-lookup"><span data-stu-id="bade8-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="bade8-110">Если вы выберите **отказ в** приглашениях на указанные домены, убедитесь, что Microsoft.com не указаны в целевых доменах.</span><span class="sxs-lookup"><span data-stu-id="bade8-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="bade8-111">Если вы выберите Разрешить приглашения только в указанные домены **(наиболее** ограничительные), убедитесь, что Microsoft.com указаны в целевых доменах. </span><span class="sxs-lookup"><span data-stu-id="bade8-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="bade8-112">Если вы устанавливаете ограничения, взаимодействующие с этими настройками, не забудьте исключить учетные записи службы служб Azure Active Directory **Modern Workplace Service Accounts.**</span><span class="sxs-lookup"><span data-stu-id="bade8-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="bade8-113">Например, если у вас есть политика условного доступа, которая не позволяет гостевых учетным записям получать доступ к порталу Intune, исключите группу **учетных** записей служб на современном рабочем месте из этой политики.</span><span class="sxs-lookup"><span data-stu-id="bade8-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="bade8-114">Действия, которые необходимо сделать, чтобы быть готовыми</span><span class="sxs-lookup"><span data-stu-id="bade8-114">Steps to get ready</span></span>

1. <span data-ttu-id="bade8-115">Просмотрите [необходимые условия для управляемого рабочего стола Майкрософт.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="bade8-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="bade8-116">Используйте [средства оценки готовности.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="bade8-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="bade8-117">[Необходимые условия для учетных записей гостей](guest-accounts.md) (Эта статья)</span><span class="sxs-lookup"><span data-stu-id="bade8-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="bade8-118">Конфигурация сети для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bade8-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="bade8-119">Подготовка сертификатов и сетевых профилей для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bade8-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="bade8-120">Подготовка доступа к локальным ресурсам для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bade8-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="bade8-121">Приложения на компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bade8-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="bade8-122">Подготовка подключенных дисков для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bade8-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="bade8-123">Подготовка ресурсов печати для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bade8-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)