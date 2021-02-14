---
title: Просмотр ошибок синхронизации службы каталогов в Microsoft 365
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
description: Узнайте, как просматривать ошибки синхронизации каталогов и возможные исправления в Центре администрирования Microsoft 365.
ms.openlocfilehash: 5103b1f8a8f0514ca30fd71b94dee2530f0b082f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693429"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="03707-103">Просмотр ошибок синхронизации службы каталогов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03707-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="03707-104">Ошибки синхронизации службы каталогов можно просмотреть в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03707-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="03707-105">Отображаются только ошибки объекта User.</span><span class="sxs-lookup"><span data-stu-id="03707-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="03707-106">Чтобы просмотреть ошибки с помощью PowerShell, см. раздел "Определение объектов [с помощью DirSyncProvisioningErrors".](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)</span><span class="sxs-lookup"><span data-stu-id="03707-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="03707-107">Просмотр ошибок синхронизации службы каталогов в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03707-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="03707-108">Чтобы просмотреть все ошибки в Центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="03707-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="03707-109">Во sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span><span class="sxs-lookup"><span data-stu-id="03707-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="03707-110">На **домашней** странице вы увидите карточку управления **"Пользователь".**</span><span class="sxs-lookup"><span data-stu-id="03707-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![Карточка управления "Пользователь" в Центре администрирования Microsoft 365](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="03707-112">На карточке выберите **ошибки** синхронизации в **Azure AD Connect,** чтобы увидеть ошибки на странице **ошибок синхронизации каталогов.**</span><span class="sxs-lookup"><span data-stu-id="03707-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![Пример страницы ошибок синхронизации каталогов](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="03707-114">Выберите любую из ошибок, чтобы отобразить в области сведений сведения об ошибке и советы по ее устранению.</span><span class="sxs-lookup"><span data-stu-id="03707-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![Пример ошибки синхронизации каталогов](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="03707-116">После просмотра см. устранение проблем с синхронизацией службы каталогов [для Microsoft 365,](fix-problems-with-directory-synchronization.md) чтобы устранить выявленные проблемы.</span><span class="sxs-lookup"><span data-stu-id="03707-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>

