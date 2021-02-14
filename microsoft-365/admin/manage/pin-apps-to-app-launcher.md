---
title: Закрепление приложений в запуске приложений пользователей
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Как глобальный администратор вы можете закрепить до трех приложений в запуске приложений пользователей.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310879"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Закрепление приложений в запуске приложений пользователей

Элементы управления на портале Azure Active Directory можно использовать для закрепления до трех приложений для Office.com и средства запуска приложений для всех пользователей в организации. Вы также можете организовать группы приложений. Любое приложение, которое вы добавляете, может быть в любое время открепить пользователем. Чтобы закрепить приложение для пользователей, необходимо быть администратором облачных приложений, администратором приложений в Azure Active Directory или глобальным администратором в Office 365. Дополнительные сведения о ролях администраторов см. в ролях администратора [в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) и ролях администратора [в Microsoft 365.](../add-users/about-admin-roles.md) 

Дополнительные сведения о запуске и Office.com приложений [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) см. в статье о запуске приложений и обновлениях для office.com и статье блога о запуске приложений [Office 365.](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Закрепление приложений с помощью портала Azure Active Directory

1. Перейдите в Центр администрирования Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> по
2. In the left nav, choose **Show all**, and under **Admin centers,** choose **Azure Active Directory**.
3. В **Azure Active Directory выберите** параметры пользователя   >  **корпоративных приложений.**
4. В разделе **"Параметры Office 365"** выберите **"Добавить приложение".**
5. Выберите приложения, которые вы хотите закрепить в запуске приложений пользователей, а затем выберите **"Добавить".**

:::image type="content" source="../../media/add-apps.png" alt-text="Параметры Microsoft 365 для закрепления приложений.":::

### <a name="pin-a-custom-app"></a>Закрепление пользовательского приложения

> [!NOTE]
> В пользовательском интерфейсе будет указано, нужно ли приобрести дополнительные лицензии Azure AD для использования этой функции. Дополнительные сведения [см. в ценах Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)

1. В **Azure Active Directory** выберите новое приложение **для** корпоративных приложений в верхней части страницы  >   **"Все приложения".**
2. На странице **"Добавление приложения"** выберите приложение  не из коллекции или создайте собственное приложение, если вы находитесь в предварительной версии Azure Active Directory.  
3. Введите имя приложения и назначьте пользователя на вкладке **"Пользователи и группы".**
4. Вкладка **"Свойства"** используется для отправки значка приложения.
5. Чтобы назначить **URL-адрес** приложению, на вкладке  "Единый вход" выберите "Связанный" и введите URL-адрес.
6. Нажмите **Сохранить**.

## <a name="create-application-collections"></a>Создание коллекций приложений

Вы также можете создавать коллекции приложений для пользователей в организации. Инструкции см. в создании коллекций на портале [My Apps на портале Azure.](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)