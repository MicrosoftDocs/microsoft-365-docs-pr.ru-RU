---
title: Просмотр ошибок синхронизации каталогов в Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: Узнайте, как просматривать ошибки синхронизации каталогов и возможные исправления в Microsoft 365 центре администрирования.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907508"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="73d65-103">Просмотр ошибок синхронизации каталогов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73d65-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="73d65-104">Ошибки синхронизации каталогов можно просматривать в Microsoft 365 центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="73d65-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="73d65-105">Отображаются только ошибки объекта Пользователя.</span><span class="sxs-lookup"><span data-stu-id="73d65-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="73d65-106">Чтобы просмотреть ошибки в PowerShell, см. раздел Определение объектов [с помощью DirSyncProvisioningErrors.](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)</span><span class="sxs-lookup"><span data-stu-id="73d65-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="73d65-107">Просмотр ошибок синхронизации каталогов в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73d65-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="73d65-108">Чтобы просмотреть все ошибки в центре администрирования Microsoft 365 администратора:</span><span class="sxs-lookup"><span data-stu-id="73d65-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="73d65-109">Во входе в [Microsoft 365 центр администрирования](https://admin.microsoft.com) с глобальной учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="73d65-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="73d65-110">На **домашней** странице вы увидите карточку управления **пользователем.**</span><span class="sxs-lookup"><span data-stu-id="73d65-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![Карточка управления пользователем в центре Microsoft 365 администрирования](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="73d65-112">На карте выберите ошибки **синхронизации** в **Azure AD Подключение** чтобы увидеть ошибки на странице ошибки синхронизации **Directory.**</span><span class="sxs-lookup"><span data-stu-id="73d65-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![Пример страницы ошибки синхронизации Directory](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="73d65-114">Выберите любую из ошибок для отображения области сведений с информацией об ошибке и советами по ее исправлению.</span><span class="sxs-lookup"><span data-stu-id="73d65-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![Пример сведений об ошибке синхронизации каталогов](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="73d65-116">После просмотра см. [в обзоре](fix-problems-with-directory-synchronization.md) устранение проблем с синхронизацией каталогов для Microsoft 365 устранения выявленных проблем.</span><span class="sxs-lookup"><span data-stu-id="73d65-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>