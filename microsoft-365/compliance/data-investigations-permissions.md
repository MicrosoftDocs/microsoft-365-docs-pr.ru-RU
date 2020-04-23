---
title: Назначение разрешений на расследования данных (Предварительная версия)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: В этой статье описывается, как настроить разрешения, необходимые для использования средства расследования данных в Microsoft 365.
ms.openlocfilehash: 47a7923d38cfa0ea3bad6c4c266f580f8104c429
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637761"
---
# <a name="assign-permissions-for-data-investigations-preview"></a><span data-ttu-id="eb6ba-103">Назначение разрешений на расследования данных (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="eb6ba-103">Assign permissions for Data Investigations (Preview)</span></span>

<span data-ttu-id="eb6ba-104">Для получения доступа к анализу данных в центре соответствия требованиям Office 365 или Microsoft 365 необходимо быть участником группы ролей Data Инвестигатор.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-104">To access a data investigation in the Office 365 or Microsoft 365 compliance center, you need be a member of the Data Investigator role group.</span></span> <span data-ttu-id="eb6ba-105">Чтобы добавить участников в группу ролей, необходимо быть членом группы ролей Управление организацией или назначить роль управления ролями в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-105">To add members to a role group, you must be a member of the Organization Management role group or assigned the Role Management role in the Security & Compliance Center.</span></span> <span data-ttu-id="eb6ba-106">После того как пользователь станет участником группы ролей Инвестигатор данных, он может создавать, получать доступ и проводить расследования при расследовании данных, участником которых вы являетесь.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-106">After a user becomes a member of the Data Investigator role group, they can create, access, and conduct investigations in the data investigations that you are a member of.</span></span>

<span data-ttu-id="eb6ba-107">Чтобы назначить разрешения на расследования данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-107">To assign data investigations permissions:</span></span>

1. <span data-ttu-id="eb6ba-108">Войдите в [https://protection.office.com](https://protection.office.com) систему и войдите, используя учетные данные для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-108">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="eb6ba-109">В центре безопасности & соответствия требованиям нажмите кнопку **разрешения**.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-109">In the Security & Compliance Center, click **Permissions**.</span></span>

3. <span data-ttu-id="eb6ba-110">Щелкните группу ролей **Инвестигатор данных** , а затем рядом с пунктом **элементы** в раскрывающейся странице щелкните **изменить**.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-110">Click the **Data Investigator** role group, and then next to **Members** on the flyout page, click **Edit**.</span></span>

4. <span data-ttu-id="eb6ba-111">Нажмите кнопку **выбрать участников** , а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-111">Click **Choose members** and then click **Add**.</span></span> <span data-ttu-id="eb6ba-112">Выберите пользователей, которых вы хотите добавить в качестве обучений данных, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-112">Select the users that you want to add as data investigators, and then click **Add**.</span></span>

5. <span data-ttu-id="eb6ba-113">Добавив всех пользователей, нажмите кнопку **Готово** , а затем — кнопку **сохранить** , чтобы сохранить изменения в группе ролей.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-113">After you've added all the users, click **Done** and then click **Save** to save the changes to the role group.</span></span>

> [!NOTE]
> <span data-ttu-id="eb6ba-114">Роль управления расследования данных, назначенная группе ролей Data Инвестигатор, предоставляет необходимые разрешения для доступа к средству расследования данных в центре соответствия требованиям Office 365 или Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-114">The Data Investigation Management role that is assigned to the Data Investigator role group provides the necessary permissions to access the Data Investigations tool in the Office 365 or Microsoft 365 compliance center.</span></span> <span data-ttu-id="eb6ba-115">По умолчанию эта роль не назначена группе ролей Управление организацией, что означает, что глобальные администраторы в организации могут не иметь доступа к средству расследования данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-115">By default, this role is not assigned to the Organization Management role group, which means that global admins in your organization may not be able to access the Data Investigations tool by default.</span></span> <span data-ttu-id="eb6ba-116">Чтобы устранить эту проблему, можно добавить глобальных администраторов в группу ролей Data Инвестигатор или добавить роль управления расследования данных в группу ролей Управление организацией.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-116">To fix this, you can add global admins to the Data Investigator role group or add the Data Investigation Management role to the Organization Management role group.</span></span> <span data-ttu-id="eb6ba-117">Третий вариант — создать настраиваемую группу ролей и назначить роль управления расследованиями данных (и другие роли), а затем добавить соответствующие элементы.</span><span class="sxs-lookup"><span data-stu-id="eb6ba-117">A third option would be to create a custom role group and assign the Data Investigation Management role (and other roles) and then add appropriate members.</span></span> <span data-ttu-id="eb6ba-118">Для получения дополнительных сведений о группах ролей и ролях обратитесь [к разделу разрешения в центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="eb6ba-118">For more information about role groups and roles, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>
