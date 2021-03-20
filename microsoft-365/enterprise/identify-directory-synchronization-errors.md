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
description: Узнайте, как просматривать ошибки синхронизации каталогов и возможные исправления в центре администрирования Microsoft 365.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907508"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Просмотр ошибок синхронизации каталогов в Microsoft 365

Ошибки синхронизации каталогов можно просматривать в центре администрирования Microsoft 365. Отображаются только ошибки объекта Пользователя. Чтобы просмотреть ошибки в PowerShell, см. раздел Определение объектов [с помощью DirSyncProvisioningErrors.](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Просмотр ошибок синхронизации каталогов в центре администрирования Microsoft 365

Чтобы просмотреть ошибки в центре администрирования Microsoft 365:
  
1. Вопишитесь в [центр администрирования Microsoft 365](https://admin.microsoft.com) с глобальной учетной записью администратора. 
    
2. На **домашней** странице вы увидите карточку управления **пользователем.** 
    
    ![Карточка управления пользователем в центре администрирования Microsoft 365](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. На карте выберите ошибки **синхронизации** в **Azure AD Connect,** чтобы увидеть ошибки на странице ошибки синхронизации Каталог.    
    
    ![Пример страницы ошибки синхронизации Directory](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Выберите любую из ошибок для отображения области сведений с информацией об ошибке и советами по ее исправлению.

   ![Пример сведений об ошибке синхронизации каталогов](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
После просмотра см. исправление проблем с синхронизацией каталогов [для Microsoft 365](fix-problems-with-directory-synchronization.md) для устранения выявленных проблем.